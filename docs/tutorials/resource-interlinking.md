# Tutorial: Resource Interlinking — Repos, Issues, and Search

!!! info "Learning Objective"
    By the end of this tutorial you will understand how GitHub's REST API organizes resources as a graph, not a flat list. You will build a chained workflow that moves from a repository → its issues → cross-repository search, using the output of each call as input to the next.

## The Resource Interlinking Mental Model

GitHub API resources are interconnected. The `id` or `full_name` of one resource is virtually always a required parameter for a related resource:

```
Repository (GET /repos/{owner}/{repo})
  └── Issues       (GET /repos/{owner}/{repo}/issues)
        └── Comments  (GET /repos/{owner}/{repo}/issues/{issue_number}/comments)
              └── Reactions (GET /repos/{owner}/{repo}/issues/comments/{comment_id}/reactions)

User (GET /user)
  └── Organizations (GET /user/orgs)
        └── Members   (GET /orgs/{org}/members)
              └── Repos (GET /users/{username}/repos)
```

This is not a side effect — it is the deliberate design. Every write operation (`POST`, `PATCH`, `DELETE`) requires you to first identify the resource via a read (`GET`). Understanding this graph eliminates the most common integration error: calling write endpoints without valid resource identifiers.

---

## Prerequisites

- Completed [Hello World tutorial](hello-world.md)
- A Personal Access Token with `repo` and `read:org` scopes
- Python 3.8+ with `requests`

---

## Step 1: Identify the Repository

```python
import os
import requests

TOKEN = os.environ["GITHUB_TOKEN"]
HEADERS = {
    "Accept": "application/vnd.github+json",
    "Authorization": f"Bearer {TOKEN}",
    "X-GitHub-Api-Version": "2022-11-28",
}
BASE = "https://api.github.com"

# Step 1: Get the repository
repo = requests.get(f"{BASE}/repos/octocat/Hello-World", headers=HEADERS).json()

owner = repo["owner"]["login"]   # "octocat"
repo_name = repo["name"]         # "Hello-World"
default_branch = repo["default_branch"]

print(f"Repository: {owner}/{repo_name}, default branch: {default_branch}")
```

The `owner.login` and `name` from this response become the path parameters for every subsequent call in this chain.

---

## Step 2: List Open Issues

```python
# Step 2: List open issues for that repository
issues_url = f"{BASE}/repos/{owner}/{repo_name}/issues"
params = {"state": "open", "per_page": 5}

issues = requests.get(issues_url, headers=HEADERS, params=params).json()

for issue in issues:
    print(f"  #{issue['number']} — {issue['title']}")
```

!!! note
    `GET /repos/{owner}/{repo}/issues` returns both issues and pull requests by default. To exclude pull requests, filter by checking that `issue.get("pull_request")` is `None`.

---

## Step 3: Read Comments on a Specific Issue

```python
# Step 3: Get comments for the first issue
if issues:
    issue_number = issues[0]["number"]
    comments_url = f"{BASE}/repos/{owner}/{repo_name}/issues/{issue_number}/comments"
    comments = requests.get(comments_url, headers=HEADERS).json()

    print(f"\nComments on issue #{issue_number}:")
    for comment in comments:
        print(f"  [{comment['user']['login']}]: {comment['body'][:80]}")
```

The `id` from the comment object is used to interact with reactions:
`POST /repos/{owner}/{repo}/issues/comments/{comment_id}/reactions`

---

## Step 4: Cross-Repository Search

Having explored a single repository, extend across GitHub using the Search API. The `full_name` from Step 1 anchors the query.

```python
# Step 4: Search for related repositories by topic
search_url = f"{BASE}/search/repositories"
params = {
    "q": "topic:github-api language:python",
    "sort": "stars",
    "order": "desc",
    "per_page": 5,
}

results = requests.get(search_url, headers=HEADERS, params=params).json()

print("\nRelated repositories:")
for item in results.get("items", []):
    print(f"  {item['full_name']} — {item['stargazers_count']} stars")
```

!!! warning
    The Search API enforces a separate rate limit: **30 requests per minute** for authenticated users, irrespective of the primary 5,000/hr limit. The header `X-RateLimit-Remaining` reflects the active limit for the current endpoint category.

---

## What You Learned

- GitHub API resources form a **directed graph** — the output of one call is the input of the next
- The `owner/repo` pair is the central join key across the entire REST API surface
- Issues and pull requests share the same endpoint; use field-level filtering to distinguish
- The Search API operates under a separate, stricter rate limit than the core REST API

---

## Next Steps

- [Manage Repositories: How-to Guide](../how-to/manage-repositories.md)
- [Automate Issue Workflows](../how-to/automate-issues.md)
- [Search API Reference](../api-reference/search.md)
