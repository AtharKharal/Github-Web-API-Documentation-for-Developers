# How to Manage Repositories

!!! abstract "Goal"
    Create, update, configure, and delete GitHub repositories using the REST API. All operations in this guide are verifiable against the `repos` section of the Postman collection.

## Prerequisites

| Requirement | Detail |
| --- | --- |
| PAT Scopes | `repo` for private repos; `public_repo` for public repos only |
| Organization Admin | Required for operations on org-owned repositories |

---

## Create a Repository

`POST /user/repos` creates a repository under the authenticated user account.

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      -H "X-GitHub-Api-Version: 2022-11-28" \
      https://api.github.com/user/repos \
      -d '{
        "name": "my-new-repo",
        "description": "Created via the GitHub REST API",
        "private": false,
        "auto_init": true
      }'
    ```

=== "Python (Requests)"

    ```python
    import os, requests

    headers = {
        "Accept": "application/vnd.github+json",
        "Authorization": f"Bearer {os.environ['GITHUB_TOKEN']}",
        "X-GitHub-Api-Version": "2022-11-28",
    }

    payload = {
        "name": "my-new-repo",
        "description": "Created via the GitHub REST API",
        "private": False,
        "auto_init": True,
    }

    response = requests.post(
        "https://api.github.com/user/repos",
        headers=headers,
        json=payload
    )
    print(response.status_code, response.json()["html_url"])
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({ auth: process.env.GITHUB_TOKEN });

    const { data } = await octokit.request("POST /user/repos", {
      name: "my-new-repo",
      description: "Created via the GitHub REST API",
      private: false,
      auto_init: true,
      headers: { "X-GitHub-Api-Version": "2022-11-28" },
    });

    console.log("Created:", data.html_url);
    ```

**Success:** `HTTP 201 Created`. The response body contains the full repository object; capture `data.id` and `data.full_name` for subsequent calls.

!!! warning
    Setting `auto_init: true` creates an initial commit on the default branch. If you intend to push an existing local repository, omit `auto_init` or you will encounter a non-fast-forward push error.

---

## Update Repository Metadata

`PATCH /repos/{owner}/{repo}` modifies any combination of mutable metadata fields.

=== "cURL"

    ```bash
    curl -L \
      -X PATCH \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      -H "X-GitHub-Api-Version: 2022-11-28" \
      https://api.github.com/repos/your-username/my-new-repo \
      -d '{"description": "Updated description", "has_wiki": false}'
    ```

=== "Python (Requests)"

    ```python
    response = requests.patch(
        "https://api.github.com/repos/your-username/my-new-repo",
        headers=headers,
        json={"description": "Updated description", "has_wiki": False}
    )
    print(response.status_code)
    ```

=== "JavaScript (Octokit)"

    ```javascript
    await octokit.request("PATCH /repos/{owner}/{repo}", {
      owner: "your-username",
      repo: "my-new-repo",
      description: "Updated description",
      has_wiki: false,
    });
    ```

Only include the fields you want to change. Unspecified fields retain their current values.

---

## Create a Repository for an Organization

`POST /orgs/{org}/repos` creates a repository owned by an organization. Requires `admin:org` or `repo` scope.

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      -H "X-GitHub-Api-Version: 2022-11-28" \
      https://api.github.com/orgs/your-org/repos \
      -d '{
        "name": "org-repo",
        "private": true,
        "visibility": "private"
      }'
    ```

=== "Python (Requests)"

    ```python
    response = requests.post(
        "https://api.github.com/orgs/your-org/repos",
        headers=headers,
        json={"name": "org-repo", "private": True, "visibility": "private"}
    )
    print(response.json()["full_name"])
    ```

=== "JavaScript (Octokit)"

    ```javascript
    await octokit.request("POST /orgs/{org}/repos", {
      org: "your-org",
      name: "org-repo",
      private: true,
      visibility: "private",
    });
    ```

---

## List Repositories for a User or Org

=== "cURL"

    ```bash
    # Authenticated user's own repos
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      "https://api.github.com/user/repos?type=owner&sort=updated&per_page=30"
    ```

=== "Python (Requests)"

    ```python
    repos = requests.get(
        "https://api.github.com/user/repos",
        headers=headers,
        params={"type": "owner", "sort": "updated", "per_page": 30}
    ).json()

    for repo in repos:
        print(repo["full_name"], "—", repo["visibility"])
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { data } = await octokit.request("GET /user/repos", {
      type: "owner",
      sort: "updated",
      per_page: 30,
    });
    data.forEach(r => console.log(r.full_name));
    ```

For paginated results, use the `Link` response header to detect and follow additional pages. The `per_page` maximum is `100`.

---

## Delete a Repository

`DELETE /repos/{owner}/{repo}` permanently removes the repository. This action is irreversible.

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      -H "X-GitHub-Api-Version: 2022-11-28" \
      https://api.github.com/repos/your-username/my-new-repo
    ```

=== "Python (Requests)"

    ```python
    response = requests.delete(
        "https://api.github.com/repos/your-username/my-new-repo",
        headers=headers
    )
    # HTTP 204 No Content indicates success
    print(response.status_code)
    ```

**Success:** `HTTP 204 No Content`. The response body is empty.

!!! warning
    Deletion requires the `delete_repo` scope on your PAT in addition to `repo`. The API returns `HTTP 403` if the scope is absent, even if the token owns the repository.

---

## Related Reference Pages

- [Repositories API Reference](../api-reference/repos.md)
- [Authentication Explanation](../explanations/authentication.md)
