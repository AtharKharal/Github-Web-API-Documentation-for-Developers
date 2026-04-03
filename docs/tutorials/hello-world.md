# Tutorial: Hello World — Your First Authenticated API Call

!!! info "Learning Objective"
    By the end of this tutorial, you will have made a verified, authenticated call to the GitHub REST API and will understand the request-response lifecycle, token mechanics, and response structure well enough to navigate any endpoint in the API reference.

## What You Will Build

A working script that:

1. Authenticates using a Personal Access Token
2. Retrieves metadata for the `octocat/Hello-World` repository
3. Reads and interprets the rate-limit headers from the response

This tutorial uses `GET /repos/{owner}/{repo}`, documented in full in [Repositories API Reference](../api-reference/repos.md).

---

## Prerequisites

- A GitHub account
- A Personal Access Token with the `public_repo` scope (see [Quick Start → Step 1](../quickstart.md#step-1-generate-a-personal-access-token))
- Python 3.8+ with `requests` installed, or cURL

---

## Anatomy of a GitHub API Request

Every request to the GitHub REST API shares a common structure:

```
{METHOD} https://api.github.com/{path}
Headers:
  Accept: application/vnd.github+json
  Authorization: Bearer {token}
  X-GitHub-Api-Version: 2022-11-28
```

| Component | Purpose |
| --- | --- |
| `Accept` header | Instructs GitHub to return JSON formatted per its current media type specification |
| `Authorization` header | Binds the request to your account, enabling private resource access and raising rate limits to 5,000 req/hr |
| `X-GitHub-Api-Version` | Pins the API version to a known contract; GitHub guarantees backward compatibility within a version |

---

## Step 1: Set Your Token

```bash
export GITHUB_TOKEN="ghp_your_token_here"
```

!!! warning
    Never hard-code a token in source code. Environment variables are the minimum acceptable approach.

---

## Step 2: Retrieve Repository Metadata

=== "cURL"

    ```bash
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      -H "X-GitHub-Api-Version: 2022-11-28" \
      https://api.github.com/repos/octocat/Hello-World
    ```

=== "Python (Requests)"

    ```python
    import os
    import requests

    TOKEN = os.environ["GITHUB_TOKEN"]

    headers = {
        "Accept": "application/vnd.github+json",
        "Authorization": f"Bearer {TOKEN}",
        "X-GitHub-Api-Version": "2022-11-28",
    }

    url = "https://api.github.com/repos/octocat/Hello-World"
    response = requests.get(url, headers=headers)

    print("Status:", response.status_code)
    print("Rate limit remaining:", response.headers.get("X-RateLimit-Remaining"))
    print("Repo name:", response.json()["full_name"])
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");

    const octokit = new Octokit({ auth: process.env.GITHUB_TOKEN });

    const response = await octokit.request("GET /repos/{owner}/{repo}", {
      owner: "octocat",
      repo: "Hello-World",
      headers: { "X-GitHub-Api-Version": "2022-11-28" },
    });

    console.log("Repo ID:", response.data.id);
    console.log("Default branch:", response.data.default_branch);
    ```

---

## Step 3: Read the Response

A successful response returns `HTTP 200` with a JSON body. Key fields:

```json
{
  "id": 1296269,
  "full_name": "octocat/Hello-World",
  "description": "My first repository on GitHub!",
  "private": false,
  "fork": false,
  "default_branch": "master",
  "stargazers_count": 2345,
  "watchers_count": 2345,
  "forks_count": 1830,
  "open_issues_count": 563,
  "owner": {
    "login": "octocat",
    "id": 583231,
    "type": "User"
  }
}
```

| Field | What It Signals |
| --- | --- |
| `id` | The permanent numerical identifier. Use this in webhook payloads and event streams — `full_name` can change if a repo is renamed. |
| `default_branch` | The branch HEAD. The Contents API and Git API use this as the implicit ref unless you specify one. |
| `open_issues_count` | Cumulative count of open issues *and* pull requests; GitHub uses a single counter for both. |
| `owner.type` | Either `User` or `Organization` — determines which authentication scopes are required for write operations. |

---

## Step 4: Interpret Rate-Limit Headers

Every response contains:

```
X-RateLimit-Limit: 5000
X-RateLimit-Remaining: 4997
X-RateLimit-Reset: 1711929600
X-RateLimit-Used: 3
```

To convert `X-RateLimit-Reset` to a human-readable time in Python:

```python
import datetime
reset_epoch = int(response.headers["X-RateLimit-Reset"])
reset_time = datetime.datetime.utcfromtimestamp(reset_epoch)
print("Rate limit resets at (UTC):", reset_time)
```

---

## What You Learned

- The invariant three-header structure of every GitHub REST API request
- How the `X-GitHub-Api-Version` header provides contract stability
- How to interpret core repository fields and their operational implications
- How to read rate-limit headers to avoid `HTTP 429` errors

---

## Next Steps

- Follow the [Resource Interlinking Tutorial](resource-interlinking.md) to chain Repos → Issues → Search
- Visit the [Repositories API Reference](../api-reference/repos.md) for the full endpoint catalogue
- See [Rate Limiting](../explanations/rate-limiting.md) for primary vs. secondary limit mechanics
