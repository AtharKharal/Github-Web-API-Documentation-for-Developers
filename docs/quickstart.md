# Quick Start

This guide takes you from zero to a verified GitHub API response in under 10 minutes. No prior knowledge of the GitHub API is assumed.

## Prerequisites

| Requirement | Details |
| --- | --- |
| GitHub Account | Required to generate a Personal Access Token (PAT) |
| HTTP Client | cURL, Python `requests`, or Node.js with `@octokit/rest` |
| Network Access | Direct access to `https://api.github.com` |

---

## Step 1: Generate a Personal Access Token

1. Go to **GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens**.
2. Click **Generate new token**.
3. Set a name, expiration, and grant the `repo` scope at minimum.
4. Copy the token immediately — it will not be shown again.

!!! warning
    Store your token in an environment variable. Never embed it in source code.

    ```bash
    export GITHUB_TOKEN="your_token_here"
    ```

---

## Step 2: Verify Authentication

Call the authenticated user endpoint to confirm your token is valid.

=== "cURL"

    ```bash
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      -H "X-GitHub-Api-Version: 2022-11-28" \
      https://api.github.com/user
    ```

=== "Python (Requests)"

    ```python
    import os
    import requests

    headers = {
        "Accept": "application/vnd.github+json",
        "Authorization": f"Bearer {os.environ['GITHUB_TOKEN']}",
        "X-GitHub-Api-Version": "2022-11-28",
    }

    response = requests.get("https://api.github.com/user", headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");

    const octokit = new Octokit({ auth: process.env.GITHUB_TOKEN });

    const { data } = await octokit.request("GET /user", {
      headers: { "X-GitHub-Api-Version": "2022-11-28" },
    });

    console.log(data);
    ```

**Expected Response (truncated)**

```json
{
  "login": "your-username",
  "id": 1234567,
  "type": "User",
  "site_admin": false
}
```

---

## Step 3: Make Your First Resource Request

Retrieve metadata for any public repository. Replace `{owner}` and `{repo}` with real values.

=== "cURL"

    ```bash
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      https://api.github.com/repos/octocat/Hello-World
    ```

=== "Python (Requests)"

    ```python
    response = requests.get(
        "https://api.github.com/repos/octocat/Hello-World",
        headers=headers
    )
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { data } = await octokit.request("GET /repos/{owner}/{repo}", {
      owner: "octocat",
      repo: "Hello-World",
    });
    console.log(data);
    ```

**Key fields in the response:**

| Field | Type | Meaning |
| --- | --- | --- |
| `id` | integer | Unique repository identifier |
| `full_name` | string | `owner/repo` path used in subsequent requests |
| `default_branch` | string | Branch name for HEAD; used in Contents and Git APIs |
| `private` | boolean | Determines which token scopes are required |

---

## Step 4: Understand Rate Limits

Every response includes rate-limit headers.

```
X-RateLimit-Limit: 5000
X-RateLimit-Remaining: 4998
X-RateLimit-Reset: 1711929600
X-RateLimit-Used: 2
```

- `X-RateLimit-Limit`: Maximum requests per hour for authenticated calls.
- `X-RateLimit-Remaining`: Requests left in the current window.
- `X-RateLimit-Reset`: UTC epoch timestamp when the window resets.

See the [Rate Limiting explanation](explanations/rate-limiting.md) for full details on primary and secondary limits.

---

## Next Steps

| Goal | Guide |
| --- | --- |
| Understand authentication flows | [Authentication](explanations/authentication.md) |
| Create and manage repositories | [Manage Repositories](how-to/manage-repositories.md) |
| Automate issue workflows | [Automate Issues](how-to/automate-issues.md) |
| Learn Resource Interlinking | [Tutorial: Resource Interlinking](tutorials/resource-interlinking.md) |
| Full endpoint reference | [API Reference](api-reference/repos.md) |
