# How to Manage Organizations

!!! abstract "Goal"
    List organization members, inspect teams, manage membership, and retrieve organization-level repository lists using the GitHub REST API. All endpoints are sourced from the `orgs/{org}` and `teams/{team id}` sections of the Postman collection.

## Prerequisites

| Requirement | Detail |
| --- | --- |
| PAT Scopes | `read:org` for read-only; `admin:org` for membership writes |
| Organization Role | Some operations require organization owner status |

---

## Get Organization Details

`GET /orgs/{org}` returns the public and (for members) private profile of an organization.

=== "cURL"

    ```bash
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      -H "X-GitHub-Api-Version: 2022-11-28" \
      https://api.github.com/orgs/your-org
    ```

=== "Python (Requests)"

    ```python
    import os, requests

    HEADERS = {
        "Accept": "application/vnd.github+json",
        "Authorization": f"Bearer {os.environ['GITHUB_TOKEN']}",
        "X-GitHub-Api-Version": "2022-11-28",
    }

    org = requests.get(
        "https://api.github.com/orgs/your-org",
        headers=HEADERS
    ).json()

    print(org["login"], "—", org["public_repos"], "public repos")
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({ auth: process.env.GITHUB_TOKEN });

    const { data } = await octokit.request("GET /orgs/{org}", {
      org: "your-org",
    });
    console.log(data.login, data.public_repos);
    ```

---

## List Organization Members

`GET /orgs/{org}/members` returns all public members of the organization.

=== "cURL"

    ```bash
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      "https://api.github.com/orgs/your-org/members?per_page=50"
    ```

=== "Python (Requests)"

    ```python
    members = requests.get(
        "https://api.github.com/orgs/your-org/members",
        headers=HEADERS,
        params={"per_page": 50}
    ).json()

    for member in members:
        print(member["login"], "—", member["type"])
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { data } = await octokit.request("GET /orgs/{org}/members", {
      org: "your-org",
      per_page: 50,
    });
    data.forEach(m => console.log(m.login));
    ```

!!! note
    This endpoint only returns members with **public** membership. Organization administrators can retrieve all members (including private members) by authenticating with the `admin:org` scope.

---

## List Organization Teams

`GET /orgs/{org}/teams` requires an authenticated member of the organization.

=== "cURL"

    ```bash
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      https://api.github.com/orgs/your-org/teams
    ```

=== "Python (Requests)"

    ```python
    teams = requests.get(
        "https://api.github.com/orgs/your-org/teams",
        headers=HEADERS
    ).json()

    for team in teams:
        print(f"  Team: {team['name']} (slug: {team['slug']}, members: {team['members_count']})")
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { data } = await octokit.request("GET /orgs/{org}/teams", {
      org: "your-org",
    });
    data.forEach(t => console.log(t.name, t.slug));
    ```

The `slug` field (not `name`) is the identifier used in all subsequent team-level endpoint paths.

---

## Add or Update a Team Member

`PUT /orgs/{org}/teams/{team_slug}/memberships/{username}` adds a user to a team or updates their role.

=== "cURL"

    ```bash
    curl -L \
      -X PUT \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      https://api.github.com/orgs/your-org/teams/backend-devs/memberships/new-developer \
      -d '{"role": "member"}'
    ```

=== "Python (Requests)"

    ```python
    response = requests.put(
        "https://api.github.com/orgs/your-org/teams/backend-devs/memberships/new-developer",
        headers=HEADERS,
        json={"role": "member"}
    )
    print(response.status_code, response.json().get("state"))
    ```

=== "JavaScript (Octokit)"

    ```javascript
    await octokit.request(
      "PUT /orgs/{org}/teams/{team_slug}/memberships/{username}",
      {
        org: "your-org",
        team_slug: "backend-devs",
        username: "new-developer",
        role: "member",
      }
    );
    ```

| `role` value | Effect |
| --- | --- |
| `member` | Standard team member with access to team repositories |
| `maintainer` | Can add/remove members and manage team settings |

The response `state` field will be `active` if the user is already a member, or `pending` if an invitation was sent.

---

## List Repositories for an Organization

`GET /orgs/{org}/repos` returns repositories accessible to the authenticated user within the organization.

=== "cURL"

    ```bash
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      "https://api.github.com/orgs/your-org/repos?type=all&sort=updated&per_page=30"
    ```

=== "Python (Requests)"

    ```python
    repos = requests.get(
        "https://api.github.com/orgs/your-org/repos",
        headers=HEADERS,
        params={"type": "all", "sort": "updated", "per_page": 30}
    ).json()

    for repo in repos:
        print(f"  {repo['full_name']} ({repo['visibility']})")
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { data } = await octokit.request("GET /orgs/{org}/repos", {
      org: "your-org",
      type: "all",
      sort: "updated",
      per_page: 30,
    });
    data.forEach(r => console.log(r.full_name, r.visibility));
    ```

The `type` parameter accepts: `all`, `public`, `private`, `forks`, `sources`, `member`. The `all` value is the broadest and requires the `read:org` scope to return private repositories.

---

## Related Reference Pages

- [Organizations API Reference](../api-reference/orgs-org.md)
- [Teams API Reference](../api-reference/teams-team-id.md)
- [Authentication Explanation](../explanations/authentication.md)
