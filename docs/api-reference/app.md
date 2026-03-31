# app API


=== "PUT Suspend an app installation"

    **Note:** Suspending a GitHub App installation is currently in beta and subject to change. Before you can suspend a GitHub App, the app owner must enable suspending installations for the app by opting-in to the beta. For more information, see "[Suspending a GitHub App installation](https://developer.github.com/apps/managing-github-apps/suspending-a-github-app-installation/)."

    Suspends a GitHub App on a user, organization, or business account, which blocks the app from accessing the account's resources. When a GitHub App is suspended, the app's access to the GitHub API or webhook events is blocked for that account.

    To suspend a GitHub App, you must be an account owner or have admin permissions in the repository or organization where the app is installed.

    You must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:installation_id` | `string` | Yes | (Required) installation_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PUT \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/app/installations/:installation_id/suspended
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.put('https://api.github.com/app/installations/:installation_id/suspended', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PUT /app/installations/{installation_id}/suspended', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "DELETE Unsuspend an app installation"

    **Note:** Suspending a GitHub App installation is currently in beta and subject to change. Before you can suspend a GitHub App, the app owner must enable suspending installations for the app by opting-in to the beta. For more information, see "[Suspending a GitHub App installation](https://developer.github.com/apps/managing-github-apps/suspending-a-github-app-installation/)."

    Removes a GitHub App installation suspension.

    To unsuspend a GitHub App, you must be an account owner or have admin permissions in the repository or organization where the app is installed and suspended.

    You must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:installation_id` | `string` | Yes | (Required) installation_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/app/installations/:installation_id/suspended
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/app/installations/:installation_id/suspended', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /app/installations/{installation_id}/suspended', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET Get an installation for the authenticated app"

    Enables an authenticated GitHub App to find an installation's information using the installation id. The installation's account type (`target_type`) will be either an organization or a user account, depending which account the repository belongs to.

    You must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:installation_id` | `string` | Yes | (Required) installation_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/app/installations/:installation_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/app/installations/:installation_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /app/installations/{installation_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 1,
      "account": {
        "login": "octocat",
        "id": 1,
        "node_id": "MDQ6VXNlcjE=",
        "avatar_url": "https://github.com/images/error/octocat_happy.gif",
        "gravatar_id": "",
        "url": "https://api.github.com/users/octocat",
        "html_url": "https://github.com/octocat",
        "followers_url": "https://api.github.com/users/octocat/followers",
        "following_url": "https://api.github.com/users/octocat/following{/other_user}",
        "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
        "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
        "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
        "organizations_url": "https://api.github.com/users/octocat/orgs",
        "repos_url": "https://api.github.com/users/octocat/repos",
        "events_url": "https://api.github.com/users/octocat/events{/privacy}",
        "received_events_url": "https://api.github.com/users/octocat/received_events",
        "type": "User",
        "site_admin": false
      },
      "access_tokens_url": "https://api.github.com/installations/1/access_tokens",
      "repositories_url": "https://api.github.com/installation/repositories",
      "html_url": "https://github.com/organizations/github/settings/installations/1",
      "app_id": 1,
      "target_id": 1,
      "target_type": "Organization",
      "permissions": {
        "checks": "write",
        "metadata": "read",
        "contents": "read"
      },
      "events": [
        "push",
        "pull_request"
      ],
      "single_file_name": "config.yml",
      "repository_selection": "selected",
      "created_at": "2017-07-08T16:18:44-04:00",
      "updated_at": "2017-07-08T16:18:44-04:00",
      "app_slug": "github-actions"
    }
    ```

    


=== "DELETE Delete an installation for the authenticated app"

    Uninstalls a GitHub App on a user, organization, or business account. If you prefer to temporarily suspend an app's access to your account's resources, then we recommend the "[Suspend an app installation](https://developer.github.com/v3/apps/#suspend-an-app-installation)" endpoint.

    You must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:installation_id` | `string` | Yes | (Required) installation_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/app/installations/:installation_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/app/installations/:installation_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /app/installations/{installation_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "POST Create an installation access token for an app"

    Creates an installation access token that enables a GitHub App to make authenticated API requests for the app's installation on an organization or individual account. Installation tokens expire one hour from the time you create them. Using an expired token produces a status code of `401 - Unauthorized`, and requires creating a new installation token. By default the installation token has access to all repositories that the installation can access. To restrict the access to specific repositories, you can provide the `repository_ids` when creating the token. When you omit `repository_ids`, the response does not contain the `repositories` key.

    You must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:installation_id` | `string` | Yes | (Required) installation_id parameter | `<integer>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "repositories": [
        "<string>",
        "<string>"
      ],
      "repository_ids": [
        "<integer>",
        "<integer>"
      ],
      "permissions": {
        "contents": "<string>",
        "issues": "<string>",
        "deployments": "<string>",
        "single_file": "<string>",
        "def_not_a_repo": "<string>"
      }
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/app/installations/:installation_id/access_tokens \
          -d '{
          "repositories": [
            "<string>",
            "<string>"
          ],
          "repository_ids": [
            "<integer>",
            "<integer>"
          ],
          "permissions": {
            "contents": "<string>",
            "issues": "<string>",
            "deployments": "<string>",
            "single_file": "<string>",
            "def_not_a_repo": "<string>"
          }
        }'
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        import json

        data = {
          "repositories": [
            "<string>",
            "<string>"
          ],
          "repository_ids": [
            "<integer>",
            "<integer>"
          ],
          "permissions": {
            "contents": "<string>",
            "issues": "<string>",
            "deployments": "<string>",
            "single_file": "<string>",
            "def_not_a_repo": "<string>"
          }
        }

        response = requests.post('https://api.github.com/app/installations/:installation_id/access_tokens', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /app/installations/{installation_id}/access_tokens', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "repositories": [
              "<string>",
              "<string>"
            ],
            "repository_ids": [
              "<integer>",
              "<integer>"
            ],
            "permissions": {
              "contents": "<string>",
              "issues": "<string>",
              "deployments": "<string>",
              "single_file": "<string>",
              "def_not_a_repo": "<string>"
            }
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "token": "v1.1f699f1069f60xxx",
      "expires_at": "2016-07-11T22:14:10Z",
      "permissions": {
        "issues": "write",
        "contents": "read"
      },
      "repository_selection": "selected",
      "repositories": [
        {
          "id": 1296269,
          "node_id": "MDEwOlJlcG9zaXRvcnkxMjk2MjY5",
          "name": "Hello-World",
          "full_name": "octocat/Hello-World",
          "owner": {
            "login": "octocat",
            "id": 1,
            "node_id": "MDQ6VXNlcjE=",
            "avatar_url": "https://github.com/images/error/octocat_happy.gif",
            "gravatar_id": "",
            "url": "https://api.github.com/users/octocat",
            "html_url": "https://github.com/octocat",
            "followers_url": "https://api.github.com/users/octocat/followers",
            "following_url": "https://api.github.com/users/octocat/following{/other_user}",
            "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
            "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
            "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
            "organizations_url": "https://api.github.com/users/octocat/orgs",
            "repos_url": "https://api.github.com/users/octocat/repos",
            "events_url": "https://api.github.com/users/octocat/events{/privacy}",
            "received_events_url": "https://api.github.com/users/octocat/received_events",
            "type": "User",
            "site_admin": false
          },
          "private": false,
          "html_url": "https://github.com/octocat/Hello-World",
          "description": "This your first repo!",
          "fork": false,
          "url": "https://api.github.com/repos/octocat/Hello-World",
          "archive_url": "https://api.github.com/repos/octocat/Hello-World/{archive_format}{/ref}",
          "assignees_url": "https://api.github.com/repos/octocat/Hello-World/assignees{/user}",
          "blobs_url": "https://api.github.com/repos/octocat/Hello-World/git/blobs{/sha}",
          "branches_url": "https://api.github.com/repos/octocat/Hello-World/branches{/branch}",
          "collaborators_url": "https://api.github.com/repos/octocat/Hello-World/collaborators{/collaborator}",
          "comments_url": "https://api.github.com/repos/octocat/Hello-World/comments{/number}",
          "commits_url": "https://api.github.com/repos/octocat/Hello-World/commits{/sha}",
          "compare_url": "https://api.github.com/repos/octocat/Hello-World/compare/{base}...{head}",
          "contents_url": "https://api.github.com/repos/octocat/Hello-World/contents/{+path}",
          "contributors_url": "https://api.github.com/repos/octocat/Hello-World/contributors",
          "deployments_url": "https://api.github.com/repos/octocat/Hello-World/deployments",
          "downloads_url": "https://api.github.com/repos/octocat/Hello-World/downloads",
          "events_url": "https://api.github.com/repos/octocat/Hello-World/events",
          "forks_url": "https://api.github.com/repos/octocat/Hello-World/forks",
          "git_commits_url": "https://api.github.com/repos/octocat/Hello-World/git/commits{/sha}",
          "git_refs_url": "https://api.github.com/repos/octocat/Hello-World/git/refs{/sha}",
          "git_tags_url": "https://api.github.com/repos/octocat/Hello-World/git/tags{/sha}",
          "git_url": "git:github.com/octocat/Hello-World.git",
          "issue_comment_url": "https://api.github.com/repos/octocat/Hello-World/issues/comments{/number}",
          "issue_events_url": "https://api.github.com/repos/octocat/Hello-World/issues/events{/number}",
          "issues_url": "https://api.github.com/repos/octocat/Hello-World/issues{/number}",
          "keys_url": "https://api.github.com/repos/octocat/Hello-World/keys{/key_id}",
          "labels_url": "https://api.github.com/repos/octocat/Hello-World/labels{/name}",
          "languages_url": "https://api.github.com/repos/octocat/Hello-World/languages",
          "merges_url": "https://api.github.com/repos/octocat/Hello-World/merges",
          "milestones_url": "https://api.github.com/repos/octocat/Hello-World/milestones{/number}",
          "notifications_url": "https://api.github.com/repos/octocat/Hello-World/notifications{?since,all,participating}",
          "pulls_url": "https://api.github.com/repos/octocat/Hello-World/pulls{/number}",
          "releases_url": "https://api.github.com/repos/octocat/Hello-World/releases{/id}",
          "ssh_url": "git@github.com:octocat/Hello-World.git",
          "stargazers_url": "https://api.github.com/repos/octocat/Hello-World/stargazers",
          "statuses_url": "https://api.github.com/repos/octocat/Hello-World/statuses/{sha}",
          "subscribers_url": "https://api.github.com/repos/octocat/Hello-World/subscribers",
          "subscription_url": "https://api.github.com/repos/octocat/Hello-World/subscription",
          "tags_url": "https://api.github.com/repos/octocat/Hello-World/tags",
          "teams_url": "https://api.github.com/repos/octocat/Hello-World/teams",
          "trees_url": "https://api.github.com/repos/octocat/Hello-World/git/trees{/sha}",
          "clone_url": "https://github.com/octocat/Hello-World.git",
          "mirror_url": "git:git.example.com/octocat/Hello-World",
          "hooks_url": "https://api.github.com/repos/octocat/Hello-World/hooks",
          "svn_url": "https://svn.github.com/octocat/Hello-World",
          "homepage": "https://github.com",
          "language": null,
          "forks_count": 9,
          "stargazers_count": 80,
          "watchers_count": 80,
          "size": 108,
          "default_branch": "master",
          "open_issues_count": 0,
          "is_template": true,
          "topics": [
            "octocat",
            "atom",
            "electron",
            "api"
          ],
          "has_issues": true,
          "has_projects": true,
          "has_wiki": true,
          "has_pages": false,
          "has_downloads": true,
          "archived": false,
          "disabled": false,
          "visibility": "public",
          "pushed_at": "2011-01-26T19:06:43Z",
          "created_at": "2011-01-26T19:01:12Z",
          "updated_at": "2011-01-26T19:14:43Z",
          "permissions": {
            "admin": false,
            "push": false,
            "pull": true
          },
          "allow_rebase_merge": true,
          "template_repository": null,
          "temp_clone_token": "ABTLWHOULUVAXGTRYU7OC2876QJ2O",
          "allow_squash_merge": true,
          "delete_branch_on_merge": true,
          "allow_merge_commit": true,
          "subscribers_count": 42,
          "network_count": 0,
          "license": {
            "key": "mit",
            "name": "MIT License",
            "url": "https://api.github.com/licenses/mit",
            "spdx_id": "MIT",
            "node_id": "MDc6TGljZW5zZW1pdA==",
            "html_url": "https://github.com/licenses/mit"
          },
          "forks": 1,
          "open_issues": 1,
          "watchers": 1
        }
      ]
    }
    ```

    


=== "GET List installations for the authenticated app"

    You must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint.

    The permissions the installation has are included under the `permissions` key.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `since` | `string` | Yes | Only show notifications updated after the given time. This is a timestamp in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format: `YYYY-MM-DDTHH:MM:SSZ`. | `<string>` |
    | `outdated` | `string` | Yes | No description. | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/app/installations?per_page=30&page=1&since=<string>&outdated=<string>
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/app/installations?per_page=30&page=1&since=<string>&outdated=<string>', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /app/installations?per_page=30&page=1&since=<string>&outdated=<string>', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
        "id": 1,
        "account": {
          "login": "octocat",
          "id": 1,
          "node_id": "MDQ6VXNlcjE=",
          "avatar_url": "https://github.com/images/error/octocat_happy.gif",
          "gravatar_id": "",
          "url": "https://api.github.com/users/octocat",
          "html_url": "https://github.com/octocat",
          "followers_url": "https://api.github.com/users/octocat/followers",
          "following_url": "https://api.github.com/users/octocat/following{/other_user}",
          "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
          "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
          "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
          "organizations_url": "https://api.github.com/users/octocat/orgs",
          "repos_url": "https://api.github.com/users/octocat/repos",
          "events_url": "https://api.github.com/users/octocat/events{/privacy}",
          "received_events_url": "https://api.github.com/users/octocat/received_events",
          "type": "User",
          "site_admin": false
        },
        "access_tokens_url": "https://api.github.com/installations/1/access_tokens",
        "repositories_url": "https://api.github.com/installation/repositories",
        "html_url": "https://github.com/organizations/github/settings/installations/1",
        "app_id": 1,
        "target_id": 1,
        "target_type": "Organization",
        "permissions": {
          "checks": "write",
          "metadata": "read",
          "contents": "read"
        },
        "events": [
          "push",
          "pull_request"
        ],
        "single_file_name": "config.yml",
        "repository_selection": "selected",
        "created_at": "2017-07-08T16:18:44-04:00",
        "updated_at": "2017-07-08T16:18:44-04:00",
        "app_slug": "github-actions"
      }
    ]
    ```

    


=== "GET Get the authenticated app"

    Returns the GitHub App associated with the authentication credentials used. To see how many app installations are associated with this GitHub App, see the `installations_count` in the response. For more details about your app's installations, see the "[List installations for the authenticated app](https://developer.github.com/v3/apps/#list-installations-for-the-authenticated-app)" endpoint.

    You must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint.

    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/app
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/app', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /app', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 1,
      "slug": "octoapp",
      "node_id": "MDExOkludGVncmF0aW9uMQ==",
      "owner": {
        "login": "github",
        "id": 1,
        "node_id": "MDEyOk9yZ2FuaXphdGlvbjE=",
        "url": "https://api.github.com/orgs/github",
        "repos_url": "https://api.github.com/orgs/github/repos",
        "events_url": "https://api.github.com/orgs/github/events",
        "avatar_url": "https://github.com/images/error/octocat_happy.gif",
        "gravatar_id": "",
        "html_url": "https://github.com/octocat",
        "followers_url": "https://api.github.com/users/octocat/followers",
        "following_url": "https://api.github.com/users/octocat/following{/other_user}",
        "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
        "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
        "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
        "organizations_url": "https://api.github.com/users/octocat/orgs",
        "received_events_url": "https://api.github.com/users/octocat/received_events",
        "type": "User",
        "site_admin": true
      },
      "name": "Octocat App",
      "description": "",
      "external_url": "https://example.com",
      "html_url": "https://github.com/apps/octoapp",
      "created_at": "2017-07-08T16:18:44-04:00",
      "updated_at": "2017-07-08T16:18:44-04:00",
      "permissions": {
        "metadata": "read",
        "contents": "read",
        "issues": "write",
        "single_file": "write"
      },
      "events": [
        "push",
        "pull_request"
      ]
    }
    ```

    

