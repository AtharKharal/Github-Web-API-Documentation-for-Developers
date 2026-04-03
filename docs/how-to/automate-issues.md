# How to Automate Issues

!!! abstract "Goal"
    Create issues, apply labels, add comments, and perform bulk label updates across a repository using the GitHub REST API. All endpoints are sourced from the `repos` section of the Postman collection.

## Prerequisites

| Requirement | Detail |
| --- | --- |
| PAT Scopes | `repo` (write access to issues) |
| Repository | Must exist; use `{owner}` and `{repo}` as path parameters throughout |

---

## Create an Issue

`POST /repos/{owner}/{repo}/issues`

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      -H "X-GitHub-Api-Version: 2022-11-28" \
      https://api.github.com/repos/{owner}/{repo}/issues \
      -d '{
        "title": "Found a critical bug",
        "body": "Steps to reproduce...",
        "labels": ["bug", "priority: high"],
        "assignees": ["username"]
      }'
    ```

=== "Python (Requests)"

    ```python
    import os, requests

    OWNER, REPO = "your-username", "your-repo"
    headers = {
        "Accept": "application/vnd.github+json",
        "Authorization": f"Bearer {os.environ['GITHUB_TOKEN']}",
        "X-GitHub-Api-Version": "2022-11-28",
    }

    issue = requests.post(
        f"https://api.github.com/repos/{OWNER}/{REPO}/issues",
        headers=headers,
        json={
            "title": "Found a critical bug",
            "body": "Steps to reproduce...",
            "labels": ["bug", "priority: high"],
            "assignees": ["username"],
        }
    ).json()

    print("Created issue #", issue["number"], "→", issue["html_url"])
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({ auth: process.env.GITHUB_TOKEN });

    const { data } = await octokit.request("POST /repos/{owner}/{repo}/issues", {
      owner: "your-username",
      repo: "your-repo",
      title: "Found a critical bug",
      body: "Steps to reproduce...",
      labels: ["bug", "priority: high"],
      assignees: ["username"],
    });

    console.log(`Created issue #${data.number}`);
    ```

**Success:** `HTTP 201 Created`. Capture `data.number` for use in subsequent comment and label operations.

---

## Add a Comment to an Issue

`POST /repos/{owner}/{repo}/issues/{issue_number}/comments`

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      https://api.github.com/repos/{owner}/{repo}/issues/42/comments \
      -d '{"body": "This is confirmed. Fix is in progress."}'
    ```

=== "Python (Requests)"

    ```python
    ISSUE_NUMBER = 42

    comment = requests.post(
        f"https://api.github.com/repos/{OWNER}/{REPO}/issues/{ISSUE_NUMBER}/comments",
        headers=headers,
        json={"body": "This is confirmed. Fix is in progress."}
    ).json()

    print("Comment ID:", comment["id"])
    ```

=== "JavaScript (Octokit)"

    ```javascript
    await octokit.request("POST /repos/{owner}/{repo}/issues/{issue_number}/comments", {
      owner: "your-username",
      repo: "your-repo",
      issue_number: 42,
      body: "This is confirmed. Fix is in progress.",
    });
    ```

---

## Bulk-Update Labels Across Open Issues

The GitHub API does not provide a single bulk-label endpoint. The pattern is: list → filter → update in sequence.

```python
import os, requests, time

OWNER, REPO = "your-org", "your-repo"
TARGET_LABEL = "needs-triage"
ADD_LABEL    = "triaged"

headers = {
    "Accept": "application/vnd.github+json",
    "Authorization": f"Bearer {os.environ['GITHUB_TOKEN']}",
    "X-GitHub-Api-Version": "2022-11-28",
}
BASE = f"https://api.github.com/repos/{OWNER}/{REPO}"

# 1. Paginate through all open issues
page, all_issues = 1, []
while True:
    batch = requests.get(
        f"{BASE}/issues",
        headers=headers,
        params={"state": "open", "labels": TARGET_LABEL, "per_page": 100, "page": page}
    ).json()
    if not batch:
        break
    all_issues.extend(batch)
    page += 1

print(f"Found {len(all_issues)} issues with '{TARGET_LABEL}'")

# 2. Add the new label to each issue
for issue in all_issues:
    if issue.get("pull_request"):
        continue  # skip pull requests
    number = issue["number"]
    resp = requests.post(
        f"{BASE}/issues/{number}/labels",
        headers=headers,
        json={"labels": [ADD_LABEL]}
    )
    print(f"  #{number} → {resp.status_code}")
    time.sleep(0.1)  # respect secondary rate limits
```

!!! warning
    The secondary rate limit applies to the number of API write requests per minute, not just per hour. Insert `time.sleep(0.1)` between sequential write calls to avoid `HTTP 429` responses during bulk operations.

---

## Close an Issue

`PATCH /repos/{owner}/{repo}/issues/{issue_number}` with `state: "closed"`.

=== "cURL"

    ```bash
    curl -L \
      -X PATCH \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      https://api.github.com/repos/{owner}/{repo}/issues/42 \
      -d '{"state": "closed", "state_reason": "completed"}'
    ```

=== "Python (Requests)"

    ```python
    requests.patch(
        f"https://api.github.com/repos/{OWNER}/{REPO}/issues/42",
        headers=headers,
        json={"state": "closed", "state_reason": "completed"}
    )
    ```

The `state_reason` field accepts `completed`, `not_planned`, or `reopened`. It is stored separately from `state` and surfaced in issue timeline events.

---

## Related Reference Pages

- [Repositories API Reference](../api-reference/repos.md)
- [Rate Limiting Explanation](../explanations/rate-limiting.md)
