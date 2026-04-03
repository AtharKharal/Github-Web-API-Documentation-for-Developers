# Rate Limiting

This page explains how the GitHub REST API enforces usage limits, what the relevant response headers mean, how primary and secondary limits differ, and how to implement safe retry logic.

---

## Two Independent Limit Systems

GitHub enforces **two independent** rate-limiting systems. Both can independently trigger a `HTTP 403` or `HTTP 429` response. They must be handled separately.

### Primary Rate Limit

The primary rate limit controls the total number of requests per hour per authentication identity.

| Authentication State | Requests per Hour |
| --- | --- |
| Unauthenticated | 60 |
| Authenticated (PAT or OAuth) | 5,000 |
| GitHub App installation token | Up to 15,000 |
| GitHub App (organization with 20+ seats) | 15,000 + 50 per seat up to 12,500 additional |

The primary limit is tracked per token. Multiple concurrent processes using the same token share the same counter.

### Secondary Rate Limit

The secondary rate limit prevents high-frequency bursts that are individually permitted by the primary limit. It is enforced against:

- Too many concurrent requests
- Too many write requests (`POST`, `PATCH`, `PUT`, `DELETE`) in a short window
- Too many requests to a single endpoint in rapid succession

The secondary limit does **not** publish a fixed numerical threshold. It is enforced adaptively.

---

## Rate-Limit Response Headers

Every API response includes the following headers:

| Header | Type | Description |
| --- | --- | --- |
| `X-RateLimit-Limit` | integer | Maximum requests allowed in the current window |
| `X-RateLimit-Remaining` | integer | Requests remaining in the current window |
| `X-RateLimit-Used` | integer | Requests consumed in the current window |
| `X-RateLimit-Reset` | integer | UTC epoch timestamp when the window resets |
| `X-RateLimit-Resource` | string | The limit category: `core`, `search`, `graphql`, `code_scanning_upload` |

The `X-RateLimit-Resource` field identifies which limit pool the request consumed from. A single session may be simultaneously approaching distinct limits (e.g., `core` and `search`).

### Interpreting `X-RateLimit-Reset`

The reset timestamp is a **Unix epoch integer** in UTC seconds. To convert:

**Python:**

```python
import datetime
reset_epoch = int(response.headers["X-RateLimit-Reset"])
reset_utc = datetime.datetime.utcfromtimestamp(reset_epoch)
seconds_remaining = reset_epoch - int(datetime.datetime.utcnow().timestamp())
print(f"Resets at {reset_utc} UTC ({seconds_remaining}s from now)")
```

**JavaScript:**

```javascript
const resetEpoch = parseInt(response.headers["x-ratelimit-reset"], 10);
const resetDate = new Date(resetEpoch * 1000);
const secondsRemaining = Math.round((resetDate - Date.now()) / 1000);
console.log(`Resets at ${resetDate.toUTCString()} (${secondsRemaining}s)`);
```

---

## Separate Limits by Resource Category

The Search API, GraphQL API, and code scanning upload endpoint each maintain **independent** windows:

| Resource | Authenticated Limit |
| --- | --- |
| `core` (REST API main) | 5,000 req/hr |
| `search` | 30 req/min |
| `graphql` | 5,000 points/hr |
| `code_scanning_upload` | 1,000 req/hr |

Use `GET /rate_limit` to inspect all current limits without consuming quota:

```bash
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer $GITHUB_TOKEN" \
  https://api.github.com/rate_limit
```

The response includes a `resources` object with entries for each limit category, each containing `limit`, `used`, `remaining`, and `reset` fields.

---

## What Happens When a Limit Is Exceeded

### Primary limit exceeded

The API returns `HTTP 403 Forbidden` with:

```json
{
  "message": "API rate limit exceeded for your-username.",
  "documentation_url": "https://docs.github.com/rest/overview/resources-in-the-rest-api#rate-limiting"
}
```

The `X-RateLimit-Remaining` header will be `0` and `X-RateLimit-Reset` identifies when to retry.

### Secondary limit exceeded

The API returns `HTTP 429 Too Many Requests` or `HTTP 403 Forbidden` with a `Retry-After` header:

```http
Retry-After: 60
```

The value is in seconds. **Do not retry before this interval expires.** Retrying sooner will extend the back-off period.

---

## Safe Retry Pattern

Use the following pattern for any production consumer of the GitHub API:

```python
import time
import requests

def api_request_with_retry(url, headers, params=None, max_retries=5):
    delay = 1  # initial back-off in seconds
    for attempt in range(max_retries):
        response = requests.get(url, headers=headers, params=params)

        if response.status_code == 200:
            return response.json()

        if response.status_code in (403, 429):
            retry_after = response.headers.get("Retry-After")
            if retry_after:
                wait = int(retry_after)
            else:
                # Primary rate limit: wait until reset
                reset_epoch = int(response.headers.get("X-RateLimit-Reset", time.time() + 60))
                wait = max(0, reset_epoch - int(time.time())) + 1

            print(f"Rate limited. Waiting {wait}s (attempt {attempt + 1}/{max_retries})")
            time.sleep(wait)
            delay = min(delay * 2, 300)  # cap at 5 minutes
        else:
            response.raise_for_status()

    raise Exception(f"Failed after {max_retries} retries: {url}")
```

---

## Operational Recommendations

- Read `X-RateLimit-Remaining` on every response; log when it drops below 100.
- For bulk operations, insert `time.sleep(0.1)` between sequential write calls to avoid secondary limits.
- Call `GET /rate_limit` at the start of batch jobs to confirm available quota before beginning.
- Use conditional requests (`If-None-Match` with `ETag`) for polling endpoints — a `304 Not Modified` response does not consume primary rate limit quota.
- Use GitHub Apps for integrations that need 15,000+ requests per hour.

---

## References

- [Quick Start → Step 4](../quickstart.md#step-4-understand-rate-limits)
- [Authentication Explanation](authentication.md)
- [Search and Discover How-to](../how-to/search-and-discover.md)
