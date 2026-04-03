# How to Search and Discover

!!! abstract "Goal"
    Use the GitHub Search API to query repositories, code, issues, pull requests, users, and topics from a single, unified interface. All endpoints are sourced from the `search` section of the Postman collection.

## Prerequisites

| Requirement | Detail |
| --- | --- |
| PAT Scopes | None for public data; `repo` to include private repositories in results |
| Rate Limit | Authenticated: 30 req/min. Unauthenticated: 10 req/min. Separate from the core 5,000/hr limit. |

---

## Understand the Search Query Syntax

All Search API endpoints accept a `q` parameter that uses GitHub's qualifier-based query language:

| Qualifier | Example | Matches |
| --- | --- | --- |
| `in:name` | `github in:name` | Repos with "github" in the name |
| `in:description` | `api in:description` | Repos with "api" in description |
| `language:` | `language:python` | Repos written in Python |
| `stars:>N` | `stars:>1000` | Repos with more than 1,000 stars |
| `user:` | `user:octocat` | Resources owned by `octocat` |
| `org:` | `org:github` | Resources owned by the `github` org |
| `is:open` | `is:open` | Open issues or pull requests |
| `label:` | `label:bug` | Issues with the `bug` label |
| `created:>YYYY-MM-DD` | `created:>2023-01-01` | Items created after a date |

Combine qualifiers with spaces (implicit AND) or `OR` keyword:

```text
topic:machine-learning language:python stars:>500
```

---

## Search Repositories

`GET /search/repositories`

=== "cURL"

    ```bash
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      -H "X-GitHub-Api-Version: 2022-11-28" \
      "https://api.github.com/search/repositories?q=topic%3Agithub-api+language%3Apython&sort=stars&order=desc&per_page=10"
    ```

=== "Python (Requests)"

    ```python
    import os, requests

    HEADERS = {
        "Accept": "application/vnd.github+json",
        "Authorization": f"Bearer {os.environ['GITHUB_TOKEN']}",
        "X-GitHub-Api-Version": "2022-11-28",
    }

    results = requests.get(
        "https://api.github.com/search/repositories",
        headers=HEADERS,
        params={
            "q": "topic:github-api language:python",
            "sort": "stars",
            "order": "desc",
            "per_page": 10,
        }
    ).json()

    print(f"Total matches: {results['total_count']}")
    for item in results["items"]:
        print(f"  {item['full_name']} — {item['stargazers_count']} stars")
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({ auth: process.env.GITHUB_TOKEN });

    const { data } = await octokit.request("GET /search/repositories", {
      q: "topic:github-api language:python",
      sort: "stars",
      order: "desc",
      per_page: 10,
    });

    console.log(`Total: ${data.total_count}`);
    data.items.forEach(r => console.log(r.full_name, r.stargazers_count));
    ```

The response `total_count` reflects the full number of matches, not just the current page. The API caps results at 1,000 items regardless of `total_count`.

---

## Search Issues and Pull Requests

`GET /search/issues` searches both issues and pull requests in a single endpoint. Use `is:issue` or `is:pr` qualifiers to narrow results.

=== "cURL"

    ```bash
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      "https://api.github.com/search/issues?q=is%3Aissue+is%3Aopen+label%3Abug+repo%3Aoctocat%2FHello-World"
    ```

=== "Python (Requests)"

    ```python
    issues = requests.get(
        "https://api.github.com/search/issues",
        headers=HEADERS,
        params={"q": "is:issue is:open label:bug repo:octocat/Hello-World"}
    ).json()

    for issue in issues["items"]:
        print(f"  #{issue['number']} {issue['title']}")
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { data } = await octokit.request("GET /search/issues", {
      q: "is:issue is:open label:bug repo:octocat/Hello-World",
    });
    data.items.forEach(i => console.log(`#${i.number} ${i.title}`));
    ```

---

## Search Code

`GET /search/code` searches file contents across all repositories accessible to the authenticated user.

=== "cURL"

    ```bash
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      "https://api.github.com/search/code?q=addClass+in%3Afile+language%3Ajavascript+repo%3Ajquery%2Fjquery"
    ```

=== "Python (Requests)"

    ```python
    code_results = requests.get(
        "https://api.github.com/search/code",
        headers=HEADERS,
        params={"q": "addClass in:file language:javascript repo:jquery/jquery"}
    ).json()

    for match in code_results["items"]:
        print(f"  {match['path']} in {match['repository']['full_name']}")
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { data } = await octokit.request("GET /search/code", {
      q: "addClass in:file language:javascript repo:jquery/jquery",
    });
    data.items.forEach(m => console.log(m.path, m.repository.full_name));
    ```

!!! warning
    Code search requires authentication. Unauthenticated requests to `GET /search/code` return `HTTP 422 Unprocessable Entity`. The `repo:` qualifier is strongly recommended to scope results and avoid rate-limit exhaustion.

---

## Search Users

`GET /search/users`

=== "cURL"

    ```bash
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      "https://api.github.com/search/users?q=type%3Aorg+location%3ASan+Francisco"
    ```

=== "Python (Requests)"

    ```python
    users = requests.get(
        "https://api.github.com/search/users",
        headers=HEADERS,
        params={"q": "type:org location:San Francisco"}
    ).json()

    for user in users["items"]:
        print(user["login"], "—", user["type"])
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { data } = await octokit.request("GET /search/users", {
      q: "type:org location:San Francisco",
    });
    data.items.forEach(u => console.log(u.login, u.type));
    ```

---

## Handle Search Rate Limits

The Search API enforces a separate, stricter rate limit:

| Authentication | Limit |
| --- | --- |
| Authenticated | 30 requests per minute |
| Unauthenticated | 10 requests per minute |

When this limit is exceeded, the API returns `HTTP 429 Too Many Requests` with a `Retry-After` header indicating the number of seconds to wait. Implement exponential back-off for production consumers.

```python
import time

def search_with_backoff(url, params, headers, max_retries=3):
    for attempt in range(max_retries):
        response = requests.get(url, headers=headers, params=params)
        if response.status_code == 429:
            wait = int(response.headers.get("Retry-After", 60))
            print(f"Rate limited. Waiting {wait}s...")
            time.sleep(wait)
        else:
            return response.json()
    raise Exception("Search rate limit exceeded after retries")
```

See [Rate Limiting Explanation](../explanations/rate-limiting.md) for full details.

---

## Related Reference Pages

- [Search API Reference](../api-reference/search.md)
- [Rate Limiting Explanation](../explanations/rate-limiting.md)
