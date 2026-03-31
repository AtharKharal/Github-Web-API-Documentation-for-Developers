# orgs/{org} API


=== "GET Get a self-hosted runner for an organization"

    **Warning:** The self-hosted runners API for organizations is currently in public beta and subject to change.

    Gets a specific self-hosted runner for an organization. You must authenticate using an access token with the `admin:org` scope to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:runner_id` | `string` | Yes | (Required) runner_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/runners/:runner_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/actions/runners/:runner_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/actions/runners/{runner_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 23,
      "name": "MBP",
      "os": "macos",
      "status": "online"
    }
    ```

    


=== "DELETE Delete a self-hosted runner from an organization"

    **Warning:** The self-hosted runners API for organizations is currently in public beta and subject to change.

    Forces the removal of a self-hosted runner from an organization. You can use this endpoint to completely remove the runner when the machine you were using no longer exists. You must authenticate using an access token with the `admin:org` scope to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:runner_id` | `string` | Yes | (Required) runner_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/runners/:runner_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/actions/runners/:runner_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/actions/runners/{runner_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List self-hosted runners for an organization"

    **Warning:** The self-hosted runners API for organizations is currently in public beta and subject to change.

    Lists all self-hosted runners for an organization. You must authenticate using an access token with the `admin:org` scope to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/runners?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/actions/runners?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/actions/runners?per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "total_count": 2,
      "runners": [
        {
          "id": 23,
          "name": "MBP",
          "os": "macos",
          "status": "online"
        },
        {
          "id": 24,
          "name": "iMac",
          "os": "macos",
          "status": "offline"
        }
      ]
    }
    ```

    


=== "GET List runner applications for an organization"

    **Warning:** The self-hosted runners API for organizations is currently in public beta and subject to change.

    Lists binaries for the runner application that you can download and run. You must authenticate using an access token with the `admin:org` scope to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/runners/downloads
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/actions/runners/downloads', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/actions/runners/downloads', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
        "os": "osx",
        "architecture": "x64",
        "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-osx-x64-2.164.0.tar.gz",
        "filename": "actions-runner-osx-x64-2.164.0.tar.gz"
      },
      {
        "os": "linux",
        "architecture": "x64",
        "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-linux-x64-2.164.0.tar.gz",
        "filename": "actions-runner-linux-x64-2.164.0.tar.gz"
      },
      {
        "os": "linux",
        "architecture": "arm",
        "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-linux-arm-2.164.0.tar.gz",
        "filename": "actions-runner-linux-arm-2.164.0.tar.gz"
      },
      {
        "os": "win",
        "architecture": "x64",
        "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-win-x64-2.164.0.zip",
        "filename": "actions-runner-win-x64-2.164.0.zip"
      },
      {
        "os": "linux",
        "architecture": "arm64",
        "download_url": "https://github.com/actions/runner/releases/download/v2.164.0/actions-runner-linux-arm64-2.164.0.tar.gz",
        "filename": "actions-runner-linux-arm64-2.164.0.tar.gz"
      }
    ]
    ```

    


=== "POST Create a registration token for an organization"

    **Warning:** The self-hosted runners API for organizations is currently in public beta and subject to change.


    Returns a token that you can pass to the `config` script. The token expires after one hour. You must authenticate
    using an access token with the `admin:org` scope to use this endpoint.

    #### Example using registration token

    Configure your self-hosted runner, replacing `TOKEN` with the registration token provided by this endpoint.

    ```
    ./config.sh --url https://github.com/octo-org --token TOKEN
    ```

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/runners/registration-token
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.post('https://api.github.com/orgs/:org/actions/runners/registration-token', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/actions/runners/registration-token', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "token": "LLBF3JGZDX3P5PMEXLND6TS6FCWO6",
      "expires_at": "2020-01-22T12:13:35.123-08:00"
    }
    ```

    


=== "POST Create a remove token for an organization"

    **Warning:** The self-hosted runners API for organizations is currently in public beta and subject to change.


    Returns a token that you can pass to the `config` script to remove a self-hosted runner from an organization. The
    token expires after one hour. You must authenticate using an access token with the `admin:org` scope to use this
    endpoint.

    #### Example using remove token

    To remove your self-hosted runner from an organization, replace `TOKEN` with the remove token provided by this
    endpoint.

    ```
    ./config.sh remove --token TOKEN
    ```

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/runners/remove-token
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.post('https://api.github.com/orgs/:org/actions/runners/remove-token', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/actions/runners/remove-token', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "token": "AABF3JGZDX3P5PMEXLND6TS6FCWO6",
      "expires_at": "2020-01-29T12:13:35.123-08:00"
    }
    ```

    


=== "PUT Add selected repository to an organization secret"

    Adds a repository to an organization secret when the `visibility` for repository access is set to `selected`. The visibility is set when you [Create or update an organization secret](https://developer.github.com/v3/actions/secrets/#create-or-update-an-organization-secret). You must authenticate using an access token with the `admin:org` scope to use this endpoint. GitHub Apps must have the `secrets` organization permission to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:secret_name` | `string` | Yes | (Required) secret_name parameter | `<string>` |
    | `:repository_id` | `string` | Yes | (Required) repository_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PUT \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/secrets/:secret_name/repositories/:repository_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.put('https://api.github.com/orgs/:org/actions/secrets/:secret_name/repositories/:repository_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PUT /orgs/{org}/actions/secrets/{secret_name}/repositories/{repository_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "DELETE Remove selected repository from an organization secret"

    Removes a repository from an organization secret when the `visibility` for repository access is set to `selected`. The visibility is set when you [Create or update an organization secret](https://developer.github.com/v3/actions/secrets/#create-or-update-an-organization-secret). You must authenticate using an access token with the `admin:org` scope to use this endpoint. GitHub Apps must have the `secrets` organization permission to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:secret_name` | `string` | Yes | (Required) secret_name parameter | `<string>` |
    | `:repository_id` | `string` | Yes | (Required) repository_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/secrets/:secret_name/repositories/:repository_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/actions/secrets/:secret_name/repositories/:repository_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/actions/secrets/{secret_name}/repositories/{repository_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List selected repositories for an organization secret"

    Lists all repositories that have been selected when the `visibility` for repository access to a secret is set to `selected`. You must authenticate using an access token with the `admin:org` scope to use this endpoint. GitHub Apps must have the `secrets` organization permission to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:secret_name` | `string` | Yes | (Required) secret_name parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/secrets/:secret_name/repositories
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/actions/secrets/:secret_name/repositories', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/actions/secrets/{secret_name}/repositories', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "total_count": 1,
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
          "hooks_url": "http://api.github.com/repos/octocat/Hello-World/hooks"
        }
      ]
    }
    ```

    


=== "PUT Set selected repositories for an organization secret"

    Replaces all repositories for an organization secret when the `visibility` for repository access is set to `selected`. The visibility is set when you [Create or update an organization secret](https://developer.github.com/v3/actions/secrets/#create-or-update-an-organization-secret). You must authenticate using an access token with the `admin:org` scope to use this endpoint. GitHub Apps must have the `secrets` organization permission to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:secret_name` | `string` | Yes | (Required) secret_name parameter | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "selected_repository_ids": [
        "<integer>",
        "<integer>"
      ]
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PUT \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/secrets/:secret_name/repositories \
          -d '{
          "selected_repository_ids": [
            "<integer>",
            "<integer>"
          ]
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
          "selected_repository_ids": [
            "<integer>",
            "<integer>"
          ]
        }

        response = requests.put('https://api.github.com/orgs/:org/actions/secrets/:secret_name/repositories', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PUT /orgs/{org}/actions/secrets/{secret_name}/repositories', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "selected_repository_ids": [
              "<integer>",
              "<integer>"
            ]
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET Get an organization secret"

    Gets a single organization secret without revealing its encrypted value. You must authenticate using an access token with the `admin:org` scope to use this endpoint. GitHub Apps must have the `secrets` organization permission to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:secret_name` | `string` | Yes | (Required) secret_name parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/secrets/:secret_name
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/actions/secrets/:secret_name', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/actions/secrets/{secret_name}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "name": "GH_TOKEN",
      "created_at": "2019-08-10T14:59:22Z",
      "updated_at": "2020-01-10T14:59:22Z",
      "visibility": "selected",
      "selected_repositories_url": "https://api.github.com/orgs/octo-org/actions/secrets/SUPER_SECRET/repositories"
    }
    ```

    


=== "PUT Create or update an organization secret"

    Creates or updates an organization secret with an encrypted value. Encrypt your secret using
    [LibSodium](https://libsodium.gitbook.io/doc/bindings_for_other_languages). You must authenticate using an access
    token with the `admin:org` scope to use this endpoint. GitHub Apps must have the `secrets` organization permission to
    use this endpoint.

    #### Example encrypting a secret using Node.js

    Encrypt your secret using the [tweetsodium](https://github.com/github/tweetsodium) library.

    ```
    const sodium = require('tweetsodium');

    const key = "base64-encoded-public-key";
    const value = "plain-text-secret";

    // Convert the message and key to Uint8Array's (Buffer implements that interface)
    const messageBytes = Buffer.from(value);
    const keyBytes = Buffer.from(key, 'base64');

    // Encrypt using LibSodium.
    const encryptedBytes = sodium.seal(messageBytes, keyBytes);

    // Base64 the encrypted secret
    const encrypted = Buffer.from(encryptedBytes).toString('base64');

    console.log(encrypted);
    ```


    #### Example encrypting a secret using Python

    Encrypt your secret using [pynacl](https://pynacl.readthedocs.io/en/stable/public/#nacl-public-sealedbox) with Python 3.

    ```
    from base64 import b64encode
    from nacl import encoding, public

    def encrypt(public_key: str, secret_value: str) -> str:
      """Encrypt a Unicode string using the public key."""
      public_key = public.PublicKey(public_key.encode("utf-8"), encoding.Base64Encoder())
      sealed_box = public.SealedBox(public_key)
      encrypted = sealed_box.encrypt(secret_value.encode("utf-8"))
      return b64encode(encrypted).decode("utf-8")
    ```

    #### Example encrypting a secret using C#

    Encrypt your secret using the [Sodium.Core](https://www.nuget.org/packages/Sodium.Core/) package.

    ```
    var secretValue = System.Text.Encoding.UTF8.GetBytes("mySecret");
    var publicKey = Convert.FromBase64String("2Sg8iYjAxxmI2LvUXpJjkYrMxURPc8r+dB7TJyvvcCU=");

    var sealedPublicKeyBox = Sodium.SealedPublicKeyBox.Create(secretValue, publicKey);

    Console.WriteLine(Convert.ToBase64String(sealedPublicKeyBox));
    ```

    #### Example encrypting a secret using Ruby

    Encrypt your secret using the [rbnacl](https://github.com/RubyCrypto/rbnacl) gem.

    ```ruby
    require "rbnacl"
    require "base64"

    key = Base64.decode64("+ZYvJDZMHUfBkJdyq5Zm9SKqeuBQ4sj+6sfjlH4CgG0=")
    public_key = RbNaCl::PublicKey.new(key)

    box = RbNaCl::Boxes::Sealed.from_public_key(public_key)
    encrypted_secret = box.encrypt("my_secret")

    # Print the base64 encoded secret
    puts Base64.strict_encode64(encrypted_secret)
    ```

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:secret_name` | `string` | Yes | (Required) secret_name parameter | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "encrypted_value": "<string>",
      "key_id": "<string>",
      "visibility": "<string>",
      "selected_repository_ids": [
        "<string>",
        "<string>"
      ]
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PUT \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/secrets/:secret_name \
          -d '{
          "encrypted_value": "<string>",
          "key_id": "<string>",
          "visibility": "<string>",
          "selected_repository_ids": [
            "<string>",
            "<string>"
          ]
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
          "encrypted_value": "<string>",
          "key_id": "<string>",
          "visibility": "<string>",
          "selected_repository_ids": [
            "<string>",
            "<string>"
          ]
        }

        response = requests.put('https://api.github.com/orgs/:org/actions/secrets/:secret_name', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PUT /orgs/{org}/actions/secrets/{secret_name}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "encrypted_value": "<string>",
            "key_id": "<string>",
            "visibility": "<string>",
            "selected_repository_ids": [
              "<string>",
              "<string>"
            ]
          }
        });
        ```
    

    #### Response Example
    
    ```json
    
    ```

    


=== "DELETE Delete an organization secret"

    Deletes a secret in an organization using the secret name. You must authenticate using an access token with the `admin:org` scope to use this endpoint. GitHub Apps must have the `secrets` organization permission to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:secret_name` | `string` | Yes | (Required) secret_name parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/secrets/:secret_name
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/actions/secrets/:secret_name', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/actions/secrets/{secret_name}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List organization secrets"

    Lists all secrets available in an organization without revealing their encrypted values. You must authenticate using an access token with the `admin:org` scope to use this endpoint. GitHub Apps must have the `secrets` organization permission to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/secrets?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/actions/secrets?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/actions/secrets?per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "total_count": 3,
      "secrets": [
        {
          "name": "GIST_ID",
          "created_at": "2019-08-10T14:59:22Z",
          "updated_at": "2020-01-10T14:59:22Z",
          "visibility": "private"
        },
        {
          "name": "DEPLOY_TOKEN",
          "created_at": "2019-08-10T14:59:22Z",
          "updated_at": "2020-01-10T14:59:22Z",
          "visibility": "all"
        },
        {
          "name": "GH_TOKEN",
          "created_at": "2019-08-10T14:59:22Z",
          "updated_at": "2020-01-10T14:59:22Z",
          "visibility": "selected",
          "selected_repositories_url": "https://api.github.com/orgs/octo-org/actions/secrets/SUPER_SECRET/repositories"
        }
      ]
    }
    ```

    


=== "GET Get an organization public key"

    Gets your public key, which you need to encrypt secrets. You need to encrypt a secret before you can create or update secrets. You must authenticate using an access token with the `admin:org` scope to use this endpoint. GitHub Apps must have the `secrets` organization permission to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/actions/secrets/public-key
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/actions/secrets/public-key', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/actions/secrets/public-key', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "key_id": "012345678912345678",
      "key": "2Sg8iYjAxxmI2LvUXpJjkYrMxURPc8r+dB7TJyvv1234"
    }
    ```

    


=== "GET Check if a user is blocked by an organization"

    No description.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/blocks/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/blocks/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/blocks/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "PUT Block a user from an organization"

    No description.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PUT \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/blocks/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.put('https://api.github.com/orgs/:org/blocks/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PUT /orgs/{org}/blocks/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "DELETE Unblock a user from an organization"

    No description.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/blocks/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/blocks/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/blocks/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List users blocked by an organization"

    List the users blocked by an organization.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/blocks
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/blocks', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/blocks', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
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
      }
    ]
    ```

    


=== "GET List SAML SSO authorizations for an organization"

    Listing and deleting credential authorizations is available to organizations with GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products).

    An authenticated organization owner with the `read:org` scope can list all credential authorizations for an organization that uses SAML single sign-on (SSO). The credentials are either personal access tokens or SSH keys that organization members have authorized for the organization. For more information, see [About authentication with SAML single sign-on](https://help.github.com/en/articles/about-authentication-with-saml-single-sign-on).

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/credential-authorizations
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/credential-authorizations', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/credential-authorizations', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
        "login": "octocat",
        "credential_id": 161195,
        "credential_type": "personal access token",
        "token_last_eight": "71c3fc11",
        "credential_authorized_at": "2011-01-26T19:06:43Z",
        "scopes": [
          "user",
          "repo"
        ]
      },
      {
        "login": "hubot",
        "credential_id": 161196,
        "credential_type": "personal access token",
        "token_last_eight": "12345678",
        "credential_authorized_at": "2019-03-29T19:06:43Z",
        "scopes": [
          "repo"
        ]
      }
    ]
    ```

    


=== "DELETE Remove a SAML SSO authorization for an organization"

    Listing and deleting credential authorizations is available to organizations with GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products).

    An authenticated organization owner with the `admin:org` scope can remove a credential authorization for an organization that uses SAML SSO. Once you remove someone's credential authorization, they will need to create a new personal access token or SSH key and authorize it for the organization they want to access.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:credential_id` | `string` | Yes | (Required) credential_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/credential-authorizations/:credential_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/credential-authorizations/:credential_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/credential-authorizations/{credential_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET Get an organization webhook"

    No description.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:hook_id` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/hooks/:hook_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/hooks/:hook_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/hooks/{hook_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 1,
      "url": "https://api.github.com/orgs/octocat/hooks/1",
      "ping_url": "https://api.github.com/orgs/octocat/hooks/1/pings",
      "name": "web",
      "events": [
        "push",
        "pull_request"
      ],
      "active": true,
      "config": {
        "url": "http://example.com",
        "content_type": "json"
      },
      "updated_at": "2011-09-06T20:39:23Z",
      "created_at": "2011-09-06T17:26:27Z",
      "type": "Organization"
    }
    ```

    


=== "PATCH Update an organization webhook"

    No description.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:hook_id` | `string` | Yes | (Required)  | `<integer>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "config": {
        "url": "<string>",
        "content_type": "<string>",
        "secret": "<string>",
        "insecure_ssl": "<string>"
      },
      "events": [
        "push"
      ],
      "active": true,
      "name": "<string>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PATCH \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/hooks/:hook_id \
          -d '{
          "config": {
            "url": "<string>",
            "content_type": "<string>",
            "secret": "<string>",
            "insecure_ssl": "<string>"
          },
          "events": [
            "push"
          ],
          "active": true,
          "name": "<string>"
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
          "config": {
            "url": "<string>",
            "content_type": "<string>",
            "secret": "<string>",
            "insecure_ssl": "<string>"
          },
          "events": [
            "push"
          ],
          "active": true,
          "name": "<string>"
        }

        response = requests.patch('https://api.github.com/orgs/:org/hooks/:hook_id', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PATCH /orgs/{org}/hooks/{hook_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "config": {
              "url": "<string>",
              "content_type": "<string>",
              "secret": "<string>",
              "insecure_ssl": "<string>"
            },
            "events": [
              "push"
            ],
            "active": true,
            "name": "<string>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 1,
      "url": "https://api.github.com/orgs/octocat/hooks/1",
      "ping_url": "https://api.github.com/orgs/octocat/hooks/1/pings",
      "name": "web",
      "events": [
        "pull_request"
      ],
      "active": true,
      "config": {
        "url": "http://example.com",
        "content_type": "json"
      },
      "updated_at": "2011-09-06T20:39:23Z",
      "created_at": "2011-09-06T17:26:27Z",
      "type": "Organization"
    }
    ```

    


=== "DELETE Delete an organization webhook"

    No description.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:hook_id` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/hooks/:hook_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/hooks/:hook_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/hooks/{hook_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "POST Ping an organization webhook"

    This will trigger a [ping event](https://developer.github.com/webhooks/#ping-event) to be sent to the hook.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:hook_id` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/hooks/:hook_id/pings
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.post('https://api.github.com/orgs/:org/hooks/:hook_id/pings', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/hooks/{hook_id}/pings', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List organization webhooks"

    No description.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/hooks?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/hooks?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/hooks?per_page=30&page=1', {
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
        "url": "https://api.github.com/orgs/octocat/hooks/1",
        "ping_url": "https://api.github.com/orgs/octocat/hooks/1/pings",
        "name": "web",
        "events": [
          "push",
          "pull_request"
        ],
        "active": true,
        "config": {
          "url": "http://example.com",
          "content_type": "json"
        },
        "updated_at": "2011-09-06T20:39:23Z",
        "created_at": "2011-09-06T17:26:27Z",
        "type": "Organization"
      }
    ]
    ```

    


=== "POST Create an organization webhook"

    Here's how you can create a hook that posts payloads in JSON format:

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "name": "<string>",
      "config": {
        "url": "<string>",
        "content_type": "<string>",
        "secret": "<string>",
        "insecure_ssl": "<string>",
        "username": "<string>",
        "password": "<string>"
      },
      "events": [
        "push"
      ],
      "active": true
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/hooks \
          -d '{
          "name": "<string>",
          "config": {
            "url": "<string>",
            "content_type": "<string>",
            "secret": "<string>",
            "insecure_ssl": "<string>",
            "username": "<string>",
            "password": "<string>"
          },
          "events": [
            "push"
          ],
          "active": true
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
          "name": "<string>",
          "config": {
            "url": "<string>",
            "content_type": "<string>",
            "secret": "<string>",
            "insecure_ssl": "<string>",
            "username": "<string>",
            "password": "<string>"
          },
          "events": [
            "push"
          ],
          "active": true
        }

        response = requests.post('https://api.github.com/orgs/:org/hooks', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/hooks', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "name": "<string>",
            "config": {
              "url": "<string>",
              "content_type": "<string>",
              "secret": "<string>",
              "insecure_ssl": "<string>",
              "username": "<string>",
              "password": "<string>"
            },
            "events": [
              "push"
            ],
            "active": true
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 1,
      "url": "https://api.github.com/orgs/octocat/hooks/1",
      "ping_url": "https://api.github.com/orgs/octocat/hooks/1/pings",
      "name": "web",
      "events": [
        "push",
        "pull_request"
      ],
      "active": true,
      "config": {
        "url": "http://example.com",
        "content_type": "json"
      },
      "updated_at": "2011-09-06T20:39:23Z",
      "created_at": "2011-09-06T17:26:27Z",
      "type": "Organization"
    }
    ```

    


=== "GET Get interaction restrictions for an organization"

    Shows which group of GitHub users can interact with this organization and when the restriction expires. If there are no restrictions, you will see an empty response.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/interaction-limits
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/interaction-limits', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/interaction-limits', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "limit": "collaborators_only",
      "origin": "organization",
      "expires_at": "2018-08-17T04:18:39Z"
    }
    ```

    


=== "PUT Set interaction restrictions for an organization"

    Temporarily restricts interactions to certain GitHub users in any public repository in the given organization. You must be an organization owner to set these restrictions.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "limit": "<string>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PUT \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/interaction-limits \
          -d '{
          "limit": "<string>"
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
          "limit": "<string>"
        }

        response = requests.put('https://api.github.com/orgs/:org/interaction-limits', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PUT /orgs/{org}/interaction-limits', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "limit": "<string>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "limit": "collaborators_only",
      "origin": "organization",
      "expires_at": "2018-08-17T04:18:39Z"
    }
    ```

    


=== "DELETE Remove interaction restrictions for an organization"

    Removes all interaction restrictions from public repositories in the given organization. You must be an organization owner to remove restrictions.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/interaction-limits
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/interaction-limits', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/interaction-limits', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List pending organization invitations"

    The return hash contains a `role` field which refers to the Organization Invitation role and will be one of the following values: `direct_member`, `admin`, `billing_manager`, `hiring_manager`, or `reinstate`. If the invitee is not a GitHub member, the `login` field in the return hash will be `null`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/invitations?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/invitations?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/invitations?per_page=30&page=1', {
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
        "login": "monalisa",
        "email": "octocat@github.com",
        "role": "direct_member",
        "created_at": "2016-11-30T06:46:10-08:00",
        "inviter": {
          "login": "other_user",
          "id": 1,
          "node_id": "MDQ6VXNlcjE=",
          "avatar_url": "https://github.com/images/error/other_user_happy.gif",
          "gravatar_id": "",
          "url": "https://api.github.com/users/other_user",
          "html_url": "https://github.com/other_user",
          "followers_url": "https://api.github.com/users/other_user/followers",
          "following_url": "https://api.github.com/users/other_user/following{/other_user}",
          "gists_url": "https://api.github.com/users/other_user/gists{/gist_id}",
          "starred_url": "https://api.github.com/users/other_user/starred{/owner}{/repo}",
          "subscriptions_url": "https://api.github.com/users/other_user/subscriptions",
          "organizations_url": "https://api.github.com/users/other_user/orgs",
          "repos_url": "https://api.github.com/users/other_user/repos",
          "events_url": "https://api.github.com/users/other_user/events{/privacy}",
          "received_events_url": "https://api.github.com/users/other_user/received_events",
          "type": "User",
          "site_admin": false
        },
        "team_count": 2,
        "invitation_team_url": "https://api.github.com/organizations/2/invitations/1/teams"
      }
    ]
    ```

    


=== "POST Create an organization invitation"

    Invite people to an organization by using their GitHub user ID or their email address. In order to create invitations in an organization, the authenticated user must be an organization owner.

    This endpoint triggers [notifications](https://help.github.com/articles/about-notifications/). Creating content too quickly using this endpoint may result in abuse rate limiting. See "[Abuse rate limits](https://developer.github.com/v3/#abuse-rate-limits)" and "[Dealing with abuse rate limits](https://developer.github.com/v3/guides/best-practices-for-integrators/#dealing-with-abuse-rate-limits)" for details.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "invitee_id": "<integer>",
      "email": "<string>",
      "role": "direct_member",
      "team_ids": [
        "<integer>",
        "<integer>"
      ]
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/invitations \
          -d '{
          "invitee_id": "<integer>",
          "email": "<string>",
          "role": "direct_member",
          "team_ids": [
            "<integer>",
            "<integer>"
          ]
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
          "invitee_id": "<integer>",
          "email": "<string>",
          "role": "direct_member",
          "team_ids": [
            "<integer>",
            "<integer>"
          ]
        }

        response = requests.post('https://api.github.com/orgs/:org/invitations', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/invitations', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "invitee_id": "<integer>",
            "email": "<string>",
            "role": "direct_member",
            "team_ids": [
              "<integer>",
              "<integer>"
            ]
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 1,
      "login": "monalisa",
      "email": "octocat@github.com",
      "role": "direct_member",
      "created_at": "2016-11-30T06:46:10-08:00",
      "inviter": {
        "login": "other_user",
        "id": 1,
        "node_id": "MDQ6VXNlcjE=",
        "avatar_url": "https://github.com/images/error/other_user_happy.gif",
        "gravatar_id": "",
        "url": "https://api.github.com/users/other_user",
        "html_url": "https://github.com/other_user",
        "followers_url": "https://api.github.com/users/other_user/followers",
        "following_url": "https://api.github.com/users/other_user/following{/other_user}",
        "gists_url": "https://api.github.com/users/other_user/gists{/gist_id}",
        "starred_url": "https://api.github.com/users/other_user/starred{/owner}{/repo}",
        "subscriptions_url": "https://api.github.com/users/other_user/subscriptions",
        "organizations_url": "https://api.github.com/users/other_user/orgs",
        "repos_url": "https://api.github.com/users/other_user/repos",
        "events_url": "https://api.github.com/users/other_user/events{/privacy}",
        "received_events_url": "https://api.github.com/users/other_user/received_events",
        "type": "User",
        "site_admin": false
      },
      "team_count": 2,
      "invitation_team_url": "https://api.github.com/organizations/2/invitations/1/teams"
    }
    ```

    


=== "GET List organization invitation teams"

    List all teams associated with an invitation. In order to see invitations in an organization, the authenticated user must be an organization owner.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:invitation_id` | `string` | Yes | (Required) invitation_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/invitations/:invitation_id/teams?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/invitations/:invitation_id/teams?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/invitations/{invitation_id}/teams?per_page=30&page=1', {
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
        "node_id": "MDQ6VGVhbTE=",
        "url": "https://api.github.com/teams/1",
        "html_url": "https://api.github.com/teams/justice-league",
        "name": "Justice League",
        "slug": "justice-league",
        "description": "A great team.",
        "privacy": "closed",
        "permission": "admin",
        "members_url": "https://api.github.com/teams/1/members{/member}",
        "repositories_url": "https://api.github.com/teams/1/repos",
        "parent": null
      }
    ]
    ```

    


=== "GET Check organization membership for a user"

    Check if a user is, publicly or privately, a member of the organization.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/members/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/members/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/members/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "DELETE Remove an organization member"

    Removing a user from this list will remove them from all teams and they will no longer have any access to the organization's repositories.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/members/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/members/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/members/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List organization members"

    List all users who are members of an organization. If the authenticated user is also a member of this organization then both concealed and public members will be returned.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `filter` | `string` | Yes | Filter members returned in the list. Can be one of:  <br>\* `2fa_disabled` - Members without [two-factor authentication](https://github.com/blog/1614-two-factor-authentication) enabled. Available for organization owners.  <br>\* `all` - All members the authenticated user can see. | `all` |
    | `role` | `string` | Yes | Filter members returned by their role. Can be one of:  <br>\* `all` - All members of the organization, regardless of role.  <br>\* `admin` - Organization owners.  <br>\* `member` - Non-owner organization members. | `all` |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/members?filter=all&role=all&per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/members?filter=all&role=all&per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/members?filter=all&role=all&per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
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
      }
    ]
    ```

    


=== "GET Get organization membership for a user"

    In order to get a user's membership with an organization, the authenticated user must be an organization member.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/memberships/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/memberships/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/memberships/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "url": "https://api.github.com/orgs/octocat/memberships/defunkt",
      "state": "active",
      "role": "admin",
      "organization_url": "https://api.github.com/orgs/octocat",
      "organization": {
        "login": "github",
        "id": 1,
        "node_id": "MDEyOk9yZ2FuaXphdGlvbjE=",
        "url": "https://api.github.com/orgs/github",
        "repos_url": "https://api.github.com/orgs/github/repos",
        "events_url": "https://api.github.com/orgs/github/events",
        "hooks_url": "https://api.github.com/orgs/github/hooks",
        "issues_url": "https://api.github.com/orgs/github/issues",
        "members_url": "https://api.github.com/orgs/github/members{/member}",
        "public_members_url": "https://api.github.com/orgs/github/public_members{/member}",
        "avatar_url": "https://github.com/images/error/octocat_happy.gif",
        "description": "A great organization"
      },
      "user": {
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
      }
    }
    ```

    


=== "PUT Set organization membership for a user"

    Only authenticated organization owners can add a member to the organization or update the member's role.

    *   If the authenticated user is _adding_ a member to the organization, the invited user will receive an email inviting them to the organization. The user's [membership status](https://developer.github.com/v3/orgs/members/#get-organization-membership-for-a-user) will be `pending` until they accept the invitation.
        
    *   Authenticated users can _update_ a user's membership by passing the `role` parameter. If the authenticated user changes a member's role to `admin`, the affected user will receive an email notifying them that they've been made an organization owner. If the authenticated user changes an owner's role to `member`, no email will be sent.

    **Rate limits**

    To prevent abuse, the authenticated user is limited to 50 organization invitations per 24 hour period. If the organization is more than one month old or on a paid plan, the limit is 500 invitations per 24 hour period.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "role": "member"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PUT \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/memberships/:username \
          -d '{
          "role": "member"
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
          "role": "member"
        }

        response = requests.put('https://api.github.com/orgs/:org/memberships/:username', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PUT /orgs/{org}/memberships/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "role": "member"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "url": "https://api.github.com/orgs/invitocat/memberships/defunkt",
      "state": "pending",
      "role": "admin",
      "organization_url": "https://api.github.com/orgs/invitocat",
      "organization": {
        "login": "github",
        "id": 1,
        "node_id": "MDEyOk9yZ2FuaXphdGlvbjE=",
        "url": "https://api.github.com/orgs/github",
        "repos_url": "https://api.github.com/orgs/github/repos",
        "events_url": "https://api.github.com/orgs/github/events",
        "hooks_url": "https://api.github.com/orgs/github/hooks",
        "issues_url": "https://api.github.com/orgs/github/issues",
        "members_url": "https://api.github.com/orgs/github/members{/member}",
        "public_members_url": "https://api.github.com/orgs/github/public_members{/member}",
        "avatar_url": "https://github.com/images/error/octocat_happy.gif",
        "description": "A great organization"
      },
      "user": {
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
      }
    }
    ```

    


=== "DELETE Remove organization membership for a user"

    In order to remove a user's membership with an organization, the authenticated user must be an organization owner.

    If the specified user is an active member of the organization, this will remove them from the organization. If the specified user has been invited to the organization, this will cancel their invitation. The specified user will receive an email notification in both cases.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/memberships/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/memberships/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/memberships/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET Download an organization migration archive"

    Fetches the URL to a migration archive.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:migration_id` | `string` | Yes | (Required) migration_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/migrations/:migration_id/archive
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/migrations/:migration_id/archive', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/migrations/{migration_id}/archive', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "DELETE Delete an organization migration archive"

    Deletes a previous migration archive. Migration archives are automatically deleted after seven days.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:migration_id` | `string` | Yes | (Required) migration_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/migrations/:migration_id/archive
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/migrations/:migration_id/archive', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/migrations/{migration_id}/archive', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET Get an organization migration status"

    Fetches the status of a migration.

    The `state` of a migration can be one of the following values:

    *   `pending`, which means the migration hasn't started yet.
    *   `exporting`, which means the migration is in progress.
    *   `exported`, which means the migration finished successfully.
    *   `failed`, which means the migration failed.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:migration_id` | `string` | Yes | (Required) migration_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/migrations/:migration_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/migrations/:migration_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/migrations/{migration_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 79,
      "node_id": "MDEyOk9yZ2FuaXphdGlvbjE=",
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
      "guid": "0b989ba4-242f-11e5-81e1-c7b6966d2516",
      "state": "exported",
      "lock_repositories": true,
      "exclude_attachments": false,
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
            "html_url": "https://api.github.com/licenses/mit"
          },
          "forks": 1,
          "open_issues": 1,
          "watchers": 1
        }
      ],
      "url": "https://api.github.com/orgs/octo-org/migrations/79",
      "created_at": "2015-07-06T15:33:38-07:00",
      "updated_at": "2015-07-06T15:33:38-07:00"
    }
    ```

    


=== "DELETE Unlock an organization repository"

    Unlocks a repository that was locked for migration. You should unlock each migrated repository and [delete them](https://developer.github.com/v3/repos/#delete-a-repository) when the migration is complete and you no longer need the source data.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:migration_id` | `string` | Yes | (Required) migration_id parameter | `<integer>` |
    | `:repo_name` | `string` | Yes | (Required) repo_name parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/migrations/:migration_id/repos/:repo_name/lock
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/migrations/:migration_id/repos/:repo_name/lock', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/migrations/{migration_id}/repos/{repo_name}/lock', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List repositories in an organization migration"

    List all the repositories for this organization migration.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:migration_id` | `string` | Yes | (Required) migration_id parameter | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/migrations/:migration_id/repositories?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/migrations/:migration_id/repositories?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/migrations/{migration_id}/repositories?per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
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
        "template_repository": "octocat/template",
        "temp_clone_token": "ABTLWHOULUVAXGTRYU7OC2876QJ2O",
        "delete_branch_on_merge": true,
        "subscribers_count": 42,
        "network_count": 0,
        "license": {
          "key": "mit",
          "name": "MIT License",
          "spdx_id": "MIT",
          "url": "https://api.github.com/licenses/mit",
          "node_id": "MDc6TGljZW5zZW1pdA=="
        }
      }
    ]
    ```

    


=== "GET List organization migrations"

    Lists the most recent migrations.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/migrations?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/migrations?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/migrations?per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
        "id": 79,
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
        "guid": "0b989ba4-242f-11e5-81e1-c7b6966d2516",
        "state": "pending",
        "lock_repositories": true,
        "exclude_attachments": false,
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
              "html_url": "https://api.github.com/licenses/mit"
            },
            "forks": 1,
            "open_issues": 1,
            "watchers": 1
          }
        ],
        "url": "https://api.github.com/orgs/octo-org/migrations/79",
        "created_at": "2015-07-06T15:33:38-07:00",
        "updated_at": "2015-07-06T15:33:38-07:00",
        "node_id": "MDQ6VXNlcjE="
      }
    ]
    ```

    


=== "POST Start an organization migration"

    Initiates the generation of a migration archive.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "repositories": [
        "<string>",
        "<string>"
      ],
      "lock_repositories": false,
      "exclude_attachments": false,
      "exclude": [
        "<string>",
        "<string>"
      ]
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/migrations \
          -d '{
          "repositories": [
            "<string>",
            "<string>"
          ],
          "lock_repositories": false,
          "exclude_attachments": false,
          "exclude": [
            "<string>",
            "<string>"
          ]
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
          "lock_repositories": false,
          "exclude_attachments": false,
          "exclude": [
            "<string>",
            "<string>"
          ]
        }

        response = requests.post('https://api.github.com/orgs/:org/migrations', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/migrations', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "repositories": [
              "<string>",
              "<string>"
            ],
            "lock_repositories": false,
            "exclude_attachments": false,
            "exclude": [
              "<string>",
              "<string>"
            ]
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 79,
      "node_id": "MDEyOk9yZ2FuaXphdGlvbjE=",
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
      "guid": "0b989ba4-242f-11e5-81e1-c7b6966d2516",
      "state": "pending",
      "lock_repositories": true,
      "exclude_attachments": false,
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
            "html_url": "https://api.github.com/licenses/mit"
          },
          "forks": 1,
          "open_issues": 1,
          "watchers": 1
        }
      ],
      "url": "https://api.github.com/orgs/octo-org/migrations/79",
      "created_at": "2015-07-06T15:33:38-07:00",
      "updated_at": "2015-07-06T15:33:38-07:00"
    }
    ```

    


=== "PUT Convert an organization member to outside collaborator"

    When an organization member is converted to an outside collaborator, they'll only have access to the repositories that their current team membership allows. The user will no longer be a member of the organization. For more information, see "[Converting an organization member to an outside collaborator](https://help.github.com/articles/converting-an-organization-member-to-an-outside-collaborator/)".

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PUT \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/outside_collaborators/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.put('https://api.github.com/orgs/:org/outside_collaborators/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PUT /orgs/{org}/outside_collaborators/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "DELETE Remove outside collaborator from an organization"

    Removing a user from this list will remove them from all the organization's repositories.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/outside_collaborators/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/outside_collaborators/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/outside_collaborators/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List outside collaborators for an organization"

    List all users who are outside collaborators of an organization.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `filter` | `string` | Yes | Filter the list of outside collaborators. Can be one of:  <br>\* `2fa_disabled`: Outside collaborators without [two-factor authentication](https://github.com/blog/1614-two-factor-authentication) enabled.  <br>\* `all`: All outside collaborators. | `all` |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/outside_collaborators?filter=all&per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/outside_collaborators?filter=all&per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/outside_collaborators?filter=all&per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
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
      }
    ]
    ```

    


=== "GET List organization projects"

    Lists the projects in an organization. Returns a `404 Not Found` status if projects are disabled in the organization. If you do not have sufficient privileges to perform this action, a `401 Unauthorized` or `410 Gone` status is returned.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `state` | `string` | Yes | Indicates the state of the projects to return. Can be either `open`, `closed`, or `all`. | `open` |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/projects?state=open&per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/projects?state=open&per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/projects?state=open&per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
        "owner_url": "https://api.github.com/orgs/octocat",
        "url": "https://api.github.com/projects/1002605",
        "html_url": "https://github.com/orgs/api-playground/projects/1",
        "columns_url": "https://api.github.com/projects/1002605/columns",
        "id": 1002605,
        "node_id": "MDc6UHJvamVjdDEwMDI2MDU=",
        "name": "Organization Roadmap",
        "body": "High-level roadmap for the upcoming year.",
        "number": 1,
        "state": "open",
        "creator": {
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
        "created_at": "2011-04-11T20:09:31Z",
        "updated_at": "2014-03-04T18:58:10Z"
      }
    ]
    ```

    


=== "POST Create an organization project"

    Creates an organization project board. Returns a `404 Not Found` status if projects are disabled in the organization. If you do not have sufficient privileges to perform this action, a `401 Unauthorized` or `410 Gone` status is returned.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "name": "<string>",
      "body": "<string>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/projects \
          -d '{
          "name": "<string>",
          "body": "<string>"
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
          "name": "<string>",
          "body": "<string>"
        }

        response = requests.post('https://api.github.com/orgs/:org/projects', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/projects', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "name": "<string>",
            "body": "<string>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "owner_url": "https://api.github.com/orgs/octocat",
      "url": "https://api.github.com/projects/1002605",
      "html_url": "https://github.com/orgs/api-playground/projects/1",
      "columns_url": "https://api.github.com/projects/1002605/columns",
      "id": 1002605,
      "node_id": "MDc6UHJvamVjdDEwMDI2MDU=",
      "name": "Organization Roadmap",
      "body": "High-level roadmap for the upcoming year.",
      "number": 1,
      "state": "open",
      "creator": {
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
      "created_at": "2011-04-11T20:09:31Z",
      "updated_at": "2014-03-04T18:58:10Z"
    }
    ```

    


=== "GET Check public organization membership for a user"

    No description.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/public_members/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/public_members/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/public_members/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "PUT Set public organization membership for the authenticated user"

    The user can publicize their own membership. (A user cannot publicize the membership for another user.)

    Note that you'll need to set `Content-Length` to zero when calling out to this endpoint. For more information, see "[HTTP verbs](https://developer.github.com/v3/#http-verbs)."

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PUT \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/public_members/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.put('https://api.github.com/orgs/:org/public_members/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PUT /orgs/{org}/public_members/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "DELETE Remove public organization membership for the authenticated user"

    No description.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/public_members/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/public_members/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/public_members/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List public organization members"

    Members of an organization can choose to have their membership publicized or not.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/public_members?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/public_members?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/public_members?per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
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
      }
    ]
    ```

    


=== "GET List organization repositories"

    Lists repositories for the specified organization.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `type` | `string` | Yes | Specifies the types of repositories you want returned. Can be one of `all`, `public`, `private`, `forks`, `sources`, `member`, `internal`. Default: `all`. If your organization is associated with an enterprise account using GitHub Enterprise Cloud or GitHub Enterprise Server 2.20+, `type` can also be `internal`. | `<string>` |
    | `sort` | `string` | Yes | Can be one of `created`, `updated`, `pushed`, `full_name`. | `created` |
    | `direction` | `string` | Yes | Can be one of `asc` or `desc`. Default: when using `full_name`: `asc`, otherwise `desc` | `<string>` |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/repos?type=<string>&sort=created&direction=<string>&per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/repos?type=<string>&sort=created&direction=<string>&per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/repos?type=<string>&sort=created&direction=<string>&per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
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
        "template_repository": "octocat/template",
        "temp_clone_token": "ABTLWHOULUVAXGTRYU7OC2876QJ2O",
        "delete_branch_on_merge": true,
        "subscribers_count": 42,
        "network_count": 0,
        "license": {
          "key": "mit",
          "name": "MIT License",
          "spdx_id": "MIT",
          "url": "https://api.github.com/licenses/mit",
          "node_id": "MDc6TGljZW5zZW1pdA=="
        }
      }
    ]
    ```

    


=== "POST Create an organization repository"

    Creates a new repository in the specified organization. The authenticated user must be a member of the organization.

    **OAuth scope requirements**

    When using [OAuth](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/), authorizations must include:

    *   `public_repo` scope or `repo` scope to create a public repository
    *   `repo` scope to create a private repository

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "name": "<string>",
      "description": "<string>",
      "homepage": "<string>",
      "private": false,
      "visibility": "<string>",
      "has_issues": true,
      "has_projects": true,
      "has_wiki": true,
      "is_template": false,
      "team_id": "<integer>",
      "auto_init": false,
      "gitignore_template": "<string>",
      "license_template": "<string>",
      "allow_squash_merge": true,
      "allow_merge_commit": true,
      "allow_rebase_merge": true,
      "delete_branch_on_merge": false
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/repos \
          -d '{
          "name": "<string>",
          "description": "<string>",
          "homepage": "<string>",
          "private": false,
          "visibility": "<string>",
          "has_issues": true,
          "has_projects": true,
          "has_wiki": true,
          "is_template": false,
          "team_id": "<integer>",
          "auto_init": false,
          "gitignore_template": "<string>",
          "license_template": "<string>",
          "allow_squash_merge": true,
          "allow_merge_commit": true,
          "allow_rebase_merge": true,
          "delete_branch_on_merge": false
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
          "name": "<string>",
          "description": "<string>",
          "homepage": "<string>",
          "private": false,
          "visibility": "<string>",
          "has_issues": true,
          "has_projects": true,
          "has_wiki": true,
          "is_template": false,
          "team_id": "<integer>",
          "auto_init": false,
          "gitignore_template": "<string>",
          "license_template": "<string>",
          "allow_squash_merge": true,
          "allow_merge_commit": true,
          "allow_rebase_merge": true,
          "delete_branch_on_merge": false
        }

        response = requests.post('https://api.github.com/orgs/:org/repos', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/repos', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "name": "<string>",
            "description": "<string>",
            "homepage": "<string>",
            "private": false,
            "visibility": "<string>",
            "has_issues": true,
            "has_projects": true,
            "has_wiki": true,
            "is_template": false,
            "team_id": "<integer>",
            "auto_init": false,
            "gitignore_template": "<string>",
            "license_template": "<string>",
            "allow_squash_merge": true,
            "allow_merge_commit": true,
            "allow_rebase_merge": true,
            "delete_branch_on_merge": false
          }
        });
        ```
    

    #### Response Example
    
    ```json
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
      "forks": 9,
      "forks_count": 9,
      "stargazers_count": 80,
      "watchers_count": 80,
      "watchers": 80,
      "size": 108,
      "default_branch": "master",
      "open_issues": 0,
      "open_issues_count": 0,
      "is_template": true,
      "license": {
        "key": "mit",
        "name": "MIT License",
        "url": "https://api.github.com/licenses/mit",
        "spdx_id": "MIT",
        "node_id": "MDc6TGljZW5zZW1pdA==",
        "html_url": "https://api.github.com/licenses/mit"
      },
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
      "network_count": 0
    }
    ```

    


=== "GET Get GitHub Actions billing for an organization"

    **Warning:** The Billing API is currently in public beta and subject to change.

    Gets the summary of the free and paid GitHub Actions minutes used.

    Paid minutes only apply to workflows in private repositories that use GitHub-hosted runners. Minutes used is listed for each GitHub-hosted runner operating system. Any job re-runs are also included in the usage. The usage does not include the multiplier for macOS and Windows runners and is not rounded up to the nearest whole minute. For more information, see "[Managing billing for GitHub Actions](https://help.github.com/github/setting-up-and-managing-billing-and-payments-on-github/managing-billing-for-github-actions)".

    Access tokens must have the `read:org` scope.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/settings/billing/actions
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/settings/billing/actions', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/settings/billing/actions', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "total_minutes_used": 305,
      "total_paid_minutes_used": 0,
      "included_minutes": 3000,
      "minutes_used_breakdown": {
        "UBUNTU": 205,
        "MACOS": 10,
        "WINDOWS": 90
      }
    }
    ```

    


=== "GET Get GitHub Packages billing for an organization"

    **Warning:** The Billing API is currently in public beta and subject to change.

    Gets the free and paid storage usued for GitHub Packages in gigabytes.

    Paid minutes only apply to packages stored for private repositories. For more information, see "[Managing billing for GitHub Packages](https://help.github.com/github/setting-up-and-managing-billing-and-payments-on-github/managing-billing-for-github-packages)."

    Access tokens must have the `read:org` scope.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/settings/billing/packages
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/settings/billing/packages', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/settings/billing/packages', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "total_gigabytes_bandwidth_used": 50,
      "total_paid_gigabytes_bandwidth_used": 40,
      "included_gigabytes_bandwidth": 10
    }
    ```

    


=== "GET Get shared storage billing for an organization"

    **Warning:** The Billing API is currently in public beta and subject to change.

    Gets the estimated paid and estimated total storage used for GitHub Actions and Github Packages.

    Paid minutes only apply to packages stored for private repositories. For more information, see "[Managing billing for GitHub Packages](https://help.github.com/github/setting-up-and-managing-billing-and-payments-on-github/managing-billing-for-github-packages)."

    Access tokens must have the `read:org` scope.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/settings/billing/shared-storage
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/settings/billing/shared-storage', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/settings/billing/shared-storage', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "days_left_in_billing_cycle": 20,
      "estimated_paid_storage_for_month": 15,
      "estimated_storage_for_month": 40
    }
    ```

    


=== "GET List reactions for a team discussion comment"

    List the reactions to a [team discussion comment](https://developer.github.com/v3/teams/discussion_comments/). OAuth access tokens require the `read:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/:org_id/team/:team_id/discussions/:discussion_number/comments/:comment_number/reactions`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `content` | `string` | Yes | Returns a single [reaction type](https://developer.github.com/v3/reactions/#reaction-types). Omit this parameter to list all reactions to a team discussion comment. | `<string>` |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    | `:comment_number` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments/:comment_number/reactions?content=<string>&per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments/:comment_number/reactions?content=<string>&per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}/comments/{comment_number}/reactions?content=<string>&per_page=30&page=1', {
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
        "node_id": "MDg6UmVhY3Rpb24x",
        "user": {
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
        "content": "heart",
        "created_at": "2016-05-20T20:09:31Z"
      }
    ]
    ```

    


=== "POST Create reaction for a team discussion comment"

    Create a reaction to a [team discussion comment](https://developer.github.com/v3/teams/discussion_comments/). OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/). A response with a `Status: 200 OK` means that you already added the reaction type to this team discussion comment.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `POST /organizations/:org_id/team/:team_id/discussions/:discussion_number/comments/:comment_number/reactions`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    | `:comment_number` | `string` | Yes | (Required)  | `<integer>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "content": "<string>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments/:comment_number/reactions \
          -d '{
          "content": "<string>"
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
          "content": "<string>"
        }

        response = requests.post('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments/:comment_number/reactions', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}/comments/{comment_number}/reactions', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "content": "<string>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 1,
      "node_id": "MDg6UmVhY3Rpb24x",
      "user": {
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
      "content": "heart",
      "created_at": "2016-05-20T20:09:31Z"
    }
    ```

    


=== "DELETE Delete team discussion comment reaction"

    **Note:** You can also specify a team or organization with `team_id` and `org_id` using the route `DELETE /organizations/:org_id/team/:team_id/discussions/:discussion_number/comments/:comment_number/reactions/:reaction_id`.

    Delete a reaction to a [team discussion comment](https://developer.github.com/v3/teams/discussion_comments/). OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    | `:comment_number` | `string` | Yes | (Required)  | `<integer>` |
    | `:reaction_id` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments/:comment_number/reactions/:reaction_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments/:comment_number/reactions/:reaction_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}/comments/{comment_number}/reactions/{reaction_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET Get a discussion comment"

    Get a specific comment on a team discussion. OAuth access tokens require the `read:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}/discussions/{discussion_number}/comments/{comment_number}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    | `:comment_number` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments/:comment_number
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments/:comment_number', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}/comments/{comment_number}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "author": {
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
      "body": "Do you like apples?",
      "body_html": "<p>Do you like apples?</p>",
      "body_version": "5eb32b219cdc6a5a9b29ba5d6caa9c51",
      "created_at": "2018-01-15T23:53:58Z",
      "last_edited_at": null,
      "discussion_url": "https://api.github.com/teams/2403582/discussions/1",
      "html_url": "https://github.com/orgs/github/teams/justice-league/discussions/1/comments/1",
      "node_id": "MDIxOlRlYW1EaXNjdXNzaW9uQ29tbWVudDE=",
      "number": 1,
      "updated_at": "2018-01-15T23:53:58Z",
      "url": "https://api.github.com/teams/2403582/discussions/1/comments/1",
      "reactions": {
        "url": "https://api.github.com/teams/2403582/discussions/1/reactions",
        "total_count": 5,
        "+1": 3,
        "-1": 1,
        "laugh": 0,
        "confused": 0,
        "heart": 1,
        "hooray": 0,
        "eyes": 1,
        "rocket": 1
      }
    }
    ```

    


=== "PATCH Update a discussion comment"

    Edits the body text of a discussion comment. OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `PATCH /organizations/{org_id}/team/{team_id}/discussions/{discussion_number}/comments/{comment_number}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    | `:comment_number` | `string` | Yes | (Required)  | `<integer>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "body": "<string>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PATCH \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments/:comment_number \
          -d '{
          "body": "<string>"
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
          "body": "<string>"
        }

        response = requests.patch('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments/:comment_number', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PATCH /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}/comments/{comment_number}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "body": "<string>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "author": {
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
      "body": "Do you like pineapples?",
      "body_html": "<p>Do you like pineapples?</p>",
      "body_version": "e6907b24d9c93cc0c5024a7af5888116",
      "created_at": "2018-01-15T23:53:58Z",
      "last_edited_at": "2018-01-26T18:22:20Z",
      "discussion_url": "https://api.github.com/teams/2403582/discussions/1",
      "html_url": "https://github.com/orgs/github/teams/justice-league/discussions/1/comments/1",
      "node_id": "MDIxOlRlYW1EaXNjdXNzaW9uQ29tbWVudDE=",
      "number": 1,
      "updated_at": "2018-01-26T18:22:20Z",
      "url": "https://api.github.com/teams/2403582/discussions/1/comments/1",
      "reactions": {
        "url": "https://api.github.com/teams/2403582/discussions/1/reactions",
        "total_count": 5,
        "+1": 3,
        "-1": 1,
        "laugh": 0,
        "confused": 0,
        "heart": 1,
        "hooray": 0,
        "eyes": 1,
        "rocket": 1
      }
    }
    ```

    


=== "DELETE Delete a discussion comment"

    Deletes a comment on a team discussion. OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `DELETE /organizations/{org_id}/team/{team_id}/discussions/{discussion_number}/comments/{comment_number}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    | `:comment_number` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments/:comment_number
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments/:comment_number', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}/comments/{comment_number}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List discussion comments"

    List all comments on a team discussion. OAuth access tokens require the `read:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}/discussions/{discussion_number}/comments`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `direction` | `string` | Yes | One of `asc` (ascending) or `desc` (descending). | `desc` |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments?direction=desc&per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments?direction=desc&per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}/comments?direction=desc&per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
        "author": {
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
        "body": "Do you like apples?",
        "body_html": "<p>Do you like apples?</p>",
        "body_version": "5eb32b219cdc6a5a9b29ba5d6caa9c51",
        "created_at": "2018-01-15T23:53:58Z",
        "last_edited_at": null,
        "discussion_url": "https://api.github.com/teams/2403582/discussions/1",
        "html_url": "https://github.com/orgs/github/teams/justice-league/discussions/1/comments/1",
        "node_id": "MDIxOlRlYW1EaXNjdXNzaW9uQ29tbWVudDE=",
        "number": 1,
        "updated_at": "2018-01-15T23:53:58Z",
        "url": "https://api.github.com/teams/2403582/discussions/1/comments/1",
        "reactions": {
          "url": "https://api.github.com/teams/2403582/discussions/1/reactions",
          "total_count": 5,
          "+1": 3,
          "-1": 1,
          "laugh": 0,
          "confused": 0,
          "heart": 1,
          "hooray": 0,
          "eyes": 1,
          "rocket": 1
        }
      }
    ]
    ```

    


=== "POST Create a discussion comment"

    Creates a new comment on a team discussion. OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    This endpoint triggers [notifications](https://help.github.com/articles/about-notifications/). Creating content too quickly using this endpoint may result in abuse rate limiting. See "[Abuse rate limits](https://developer.github.com/v3/#abuse-rate-limits)" and "[Dealing with abuse rate limits](https://developer.github.com/v3/guides/best-practices-for-integrators/#dealing-with-abuse-rate-limits)" for details.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `POST /organizations/{org_id}/team/{team_id}/discussions/{discussion_number}/comments`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "body": "<string>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments \
          -d '{
          "body": "<string>"
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
          "body": "<string>"
        }

        response = requests.post('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/comments', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}/comments', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "body": "<string>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "author": {
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
      "body": "Do you like apples?",
      "body_html": "<p>Do you like apples?</p>",
      "body_version": "5eb32b219cdc6a5a9b29ba5d6caa9c51",
      "created_at": "2018-01-15T23:53:58Z",
      "last_edited_at": null,
      "discussion_url": "https://api.github.com/teams/2403582/discussions/1",
      "html_url": "https://github.com/orgs/github/teams/justice-league/discussions/1/comments/1",
      "node_id": "MDIxOlRlYW1EaXNjdXNzaW9uQ29tbWVudDE=",
      "number": 1,
      "updated_at": "2018-01-15T23:53:58Z",
      "url": "https://api.github.com/teams/2403582/discussions/1/comments/1",
      "reactions": {
        "url": "https://api.github.com/teams/2403582/discussions/1/reactions",
        "total_count": 5,
        "+1": 3,
        "-1": 1,
        "laugh": 0,
        "confused": 0,
        "heart": 1,
        "hooray": 0,
        "eyes": 1,
        "rocket": 1
      }
    }
    ```

    


=== "GET List reactions for a team discussion"

    List the reactions to a [team discussion](https://developer.github.com/v3/teams/discussions/). OAuth access tokens require the `read:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/:org_id/team/:team_id/discussions/:discussion_number/reactions`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `content` | `string` | Yes | Returns a single [reaction type](https://developer.github.com/v3/reactions/#reaction-types). Omit this parameter to list all reactions to a team discussion. | `<string>` |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/reactions?content=<string>&per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/reactions?content=<string>&per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}/reactions?content=<string>&per_page=30&page=1', {
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
        "node_id": "MDg6UmVhY3Rpb24x",
        "user": {
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
        "content": "heart",
        "created_at": "2016-05-20T20:09:31Z"
      }
    ]
    ```

    


=== "POST Create reaction for a team discussion"

    Create a reaction to a [team discussion](https://developer.github.com/v3/teams/discussions/). OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/). A response with a `Status: 200 OK` means that you already added the reaction type to this team discussion.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `POST /organizations/:org_id/team/:team_id/discussions/:discussion_number/reactions`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "content": "<string>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/reactions \
          -d '{
          "content": "<string>"
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
          "content": "<string>"
        }

        response = requests.post('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/reactions', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}/reactions', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "content": "<string>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 1,
      "node_id": "MDg6UmVhY3Rpb24x",
      "user": {
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
      "content": "heart",
      "created_at": "2016-05-20T20:09:31Z"
    }
    ```

    


=== "DELETE Delete team discussion reaction"

    **Note:** You can also specify a team or organization with `team_id` and `org_id` using the route `DELETE /organizations/:org_id/team/:team_id/discussions/:discussion_number/reactions/:reaction_id`.

    Delete a reaction to a [team discussion](https://developer.github.com/v3/teams/discussions/). OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    | `:reaction_id` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/reactions/:reaction_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number/reactions/:reaction_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}/reactions/{reaction_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET Get a discussion"

    Get a specific discussion on a team's page. OAuth access tokens require the `read:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}/discussions/{discussion_number}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "author": {
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
      "body": "Hi! This is an area for us to collaborate as a team.",
      "body_html": "<p>Hi! This is an area for us to collaborate as a team</p>",
      "body_version": "0d495416a700fb06133c612575d92bfb",
      "comments_count": 0,
      "comments_url": "https://api.github.com/teams/2343027/discussions/1/comments",
      "created_at": "2018-01-25T18:56:31Z",
      "last_edited_at": null,
      "html_url": "https://github.com/orgs/github/teams/justice-league/discussions/1",
      "node_id": "MDE0OlRlYW1EaXNjdXNzaW9uMQ==",
      "number": 1,
      "pinned": false,
      "private": false,
      "team_url": "https://api.github.com/teams/2343027",
      "title": "Our first team post",
      "updated_at": "2018-01-25T18:56:31Z",
      "url": "https://api.github.com/teams/2343027/discussions/1",
      "reactions": {
        "url": "https://api.github.com/teams/2343027/discussions/1/reactions",
        "total_count": 5,
        "+1": 3,
        "-1": 1,
        "laugh": 0,
        "confused": 0,
        "heart": 1,
        "hooray": 0,
        "eyes": 1,
        "rocket": 1
      }
    }
    ```

    


=== "PATCH Update a discussion"

    Edits the title and body text of a discussion post. Only the parameters you provide are updated. OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `PATCH /organizations/{org_id}/team/{team_id}/discussions/{discussion_number}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "title": "<string>",
      "body": "<string>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PATCH \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number \
          -d '{
          "title": "<string>",
          "body": "<string>"
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
          "title": "<string>",
          "body": "<string>"
        }

        response = requests.patch('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PATCH /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "title": "<string>",
            "body": "<string>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "author": {
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
      "body": "Hi! This is an area for us to collaborate as a team.",
      "body_html": "<p>Hi! This is an area for us to collaborate as a team</p>",
      "body_version": "0d495416a700fb06133c612575d92bfb",
      "comments_count": 1,
      "comments_url": "https://api.github.com/teams/2343027/discussions/1/comments",
      "created_at": "2018-01-25T18:56:31Z",
      "last_edited_at": "2018-01-26T18:22:20Z",
      "html_url": "https://github.com/orgs/github/teams/justice-league/discussions/1",
      "node_id": "MDE0OlRlYW1EaXNjdXNzaW9uMQ==",
      "number": 1,
      "pinned": false,
      "private": false,
      "team_url": "https://api.github.com/teams/2343027",
      "title": "Welcome to our first team post",
      "updated_at": "2018-01-26T18:22:20Z",
      "url": "https://api.github.com/teams/2343027/discussions/1",
      "reactions": {
        "url": "https://api.github.com/teams/2343027/discussions/1/reactions",
        "total_count": 5,
        "+1": 3,
        "-1": 1,
        "laugh": 0,
        "confused": 0,
        "heart": 1,
        "hooray": 0,
        "eyes": 1,
        "rocket": 1
      }
    }
    ```

    


=== "DELETE Delete a discussion"

    Delete a discussion from a team's page. OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `DELETE /organizations/{org_id}/team/{team_id}/discussions/{discussion_number}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:discussion_number` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/teams/:team_slug/discussions/:discussion_number', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List discussions"

    List all discussions on a team's page. OAuth access tokens require the `read:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}/discussions`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `direction` | `string` | Yes | One of `asc` (ascending) or `desc` (descending). | `desc` |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions?direction=desc&per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/discussions?direction=desc&per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/discussions?direction=desc&per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
        "author": {
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
        "body": "Hi! This is an area for us to collaborate as a team.",
        "body_html": "<p>Hi! This is an area for us to collaborate as a team</p>",
        "body_version": "0d495416a700fb06133c612575d92bfb",
        "comments_count": 0,
        "comments_url": "https://api.github.com/teams/2343027/discussions/1/comments",
        "created_at": "2018-01-25T18:56:31Z",
        "last_edited_at": null,
        "html_url": "https://github.com/orgs/github/teams/justice-league/discussions/1",
        "node_id": "MDE0OlRlYW1EaXNjdXNzaW9uMQ==",
        "number": 1,
        "pinned": false,
        "private": false,
        "team_url": "https://api.github.com/teams/2343027",
        "title": "Our first team post",
        "updated_at": "2018-01-25T18:56:31Z",
        "url": "https://api.github.com/teams/2343027/discussions/1",
        "reactions": {
          "url": "https://api.github.com/teams/2343027/discussions/1/reactions",
          "total_count": 5,
          "+1": 3,
          "-1": 1,
          "laugh": 0,
          "confused": 0,
          "heart": 1,
          "hooray": 0,
          "eyes": 1,
          "rocket": 1
        }
      }
    ]
    ```

    


=== "POST Create a discussion"

    Creates a new discussion post on a team's page. OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

    This endpoint triggers [notifications](https://help.github.com/articles/about-notifications/). Creating content too quickly using this endpoint may result in abuse rate limiting. See "[Abuse rate limits](https://developer.github.com/v3/#abuse-rate-limits)" and "[Dealing with abuse rate limits](https://developer.github.com/v3/guides/best-practices-for-integrators/#dealing-with-abuse-rate-limits)" for details.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `POST /organizations/{org_id}/team/{team_id}/discussions`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "title": "<string>",
      "body": "<string>",
      "private": false
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/discussions \
          -d '{
          "title": "<string>",
          "body": "<string>",
          "private": false
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
          "title": "<string>",
          "body": "<string>",
          "private": false
        }

        response = requests.post('https://api.github.com/orgs/:org/teams/:team_slug/discussions', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/teams/{team_slug}/discussions', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "title": "<string>",
            "body": "<string>",
            "private": false
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "author": {
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
      "body": "Hi! This is an area for us to collaborate as a team.",
      "body_html": "<p>Hi! This is an area for us to collaborate as a team</p>",
      "body_version": "0d495416a700fb06133c612575d92bfb",
      "comments_count": 0,
      "comments_url": "https://api.github.com/teams/2343027/discussions/1/comments",
      "created_at": "2018-01-25T18:56:31Z",
      "last_edited_at": null,
      "html_url": "https://github.com/orgs/github/teams/justice-league/discussions/1",
      "node_id": "MDE0OlRlYW1EaXNjdXNzaW9uMQ==",
      "number": 1,
      "pinned": false,
      "private": false,
      "team_url": "https://api.github.com/teams/2343027",
      "title": "Our first team post",
      "updated_at": "2018-01-25T18:56:31Z",
      "url": "https://api.github.com/teams/2343027/discussions/1",
      "reactions": {
        "url": "https://api.github.com/teams/2343027/discussions/1/reactions",
        "total_count": 5,
        "+1": 3,
        "-1": 1,
        "laugh": 0,
        "confused": 0,
        "heart": 1,
        "hooray": 0,
        "eyes": 1,
        "rocket": 1
      }
    }
    ```

    


=== "GET Get team membership for a user"

    Team members will include the members of child teams.

    To get a user's membership with a team, the team must be visible to the authenticated user.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}/memberships/{username}`.

    **Note:** The `role` for organization owners returns as `maintainer`. For more information about `maintainer` roles, see [Create a team](https://developer.github.com/v3/teams/#create-a-team).

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/memberships/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/memberships/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/memberships/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "url": "https://api.github.com/teams/1/memberships/octocat",
      "role": "member",
      "state": "active"
    }
    ```

    


=== "PUT Add or update team membership for a user"

    Team synchronization is available for organizations using GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products) in the GitHub Help documentation.

    Adds an organization member to a team. An authenticated organization owner or team maintainer can add organization members to a team.

    **Note:** When you have team synchronization set up for a team with your organization's identity provider (IdP), you will see an error if you attempt to use the API for making changes to the team's membership. If you have access to manage group membership in your IdP, you can manage GitHub team membership through your identity provider, which automatically adds and removes team members in an organization. For more information, see "[Synchronizing teams between your identity provider and GitHub](https://help.github.com/articles/synchronizing-teams-between-your-identity-provider-and-github/)."

    An organization owner can add someone who is not part of the team's organization to a team. When an organization owner adds someone to a team who is not an organization member, this endpoint will send an invitation to the person via email. This newly-created membership will be in the "pending" state until the person accepts the invitation, at which point the membership will transition to the "active" state and the user will be added as a member of the team.

    If the user is already a member of the team, this endpoint will update the role of the team member's role. To update the membership of a team member, the authenticated user must be an organization owner or a team maintainer.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `PUT /organizations/{org_id}/team/{team_id}/memberships/{username}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "role": "member"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PUT \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/memberships/:username \
          -d '{
          "role": "member"
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
          "role": "member"
        }

        response = requests.put('https://api.github.com/orgs/:org/teams/:team_slug/memberships/:username', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PUT /orgs/{org}/teams/{team_slug}/memberships/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "role": "member"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "url": "https://api.github.com/teams/1/memberships/octocat",
      "role": "member",
      "state": "active"
    }
    ```

    


=== "DELETE Remove team membership for a user"

    Team synchronization is available for organizations using GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products) in the GitHub Help documentation.

    To remove a membership between a user and a team, the authenticated user must have 'admin' permissions to the team or be an owner of the organization that the team is associated with. Removing team membership does not delete the user, it just removes their membership from the team.

    **Note:** When you have team synchronization set up for a team with your organization's identity provider (IdP), you will see an error if you attempt to use the API for making changes to the team's membership. If you have access to manage group membership in your IdP, you can manage GitHub team membership through your identity provider, which automatically adds and removes team members in an organization. For more information, see "[Synchronizing teams between your identity provider and GitHub](https://help.github.com/articles/synchronizing-teams-between-your-identity-provider-and-github/)."

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `DELETE /organizations/{org_id}/team/{team_id}/memberships/{username}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:username` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/memberships/:username
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/teams/:team_slug/memberships/:username', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/teams/{team_slug}/memberships/{username}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET Check team permissions for a project"

    Checks whether a team has `read`, `write`, or `admin` permissions for an organization project. The response includes projects inherited from a parent team.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}/projects/{project_id}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:project_id` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/projects/:project_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/projects/:project_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/projects/{project_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "owner_url": "https://api.github.com/orgs/octocat",
      "url": "https://api.github.com/projects/1002605",
      "html_url": "https://github.com/orgs/api-playground/projects/1",
      "columns_url": "https://api.github.com/projects/1002605/columns",
      "id": 1002605,
      "node_id": "MDc6UHJvamVjdDEwMDI2MDU=",
      "name": "Organization Roadmap",
      "body": "High-level roadmap for the upcoming year.",
      "number": 1,
      "state": "open",
      "creator": {
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
      "created_at": "2011-04-11T20:09:31Z",
      "updated_at": "2014-03-04T18:58:10Z",
      "organization_permission": "write",
      "private": false,
      "permissions": {
        "read": true,
        "write": true,
        "admin": false
      }
    }
    ```

    


=== "PUT Add or update team project permissions"

    Adds an organization project to a team. To add a project to a team or update the team's permission on a project, the authenticated user must have `admin` permissions for the project. The project and team must be part of the same organization.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `PUT /organizations/{org_id}/team/{team_id}/projects/{project_id}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:project_id` | `string` | Yes | (Required)  | `<integer>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "permission": "<string>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PUT \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/projects/:project_id \
          -d '{
          "permission": "<string>"
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
          "permission": "<string>"
        }

        response = requests.put('https://api.github.com/orgs/:org/teams/:team_slug/projects/:project_id', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PUT /orgs/{org}/teams/{team_slug}/projects/{project_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "permission": "<string>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "DELETE Remove a project from a team"

    Removes an organization project from a team. An organization owner or a team maintainer can remove any project from the team. To remove a project from a team as an organization member, the authenticated user must have `read` access to both the team and project, or `admin` access to the team or project. This endpoint removes the project from the team, but does not delete the project.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `DELETE /organizations/{org_id}/team/{team_id}/projects/{project_id}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:project_id` | `string` | Yes | (Required)  | `<integer>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/projects/:project_id
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/teams/:team_slug/projects/:project_id', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/teams/{team_slug}/projects/{project_id}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List team projects"

    Lists the organization projects for a team.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}/projects`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/projects?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/projects?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/projects?per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
        "owner_url": "https://api.github.com/orgs/octocat",
        "url": "https://api.github.com/projects/1002605",
        "html_url": "https://github.com/orgs/api-playground/projects/1",
        "columns_url": "https://api.github.com/projects/1002605/columns",
        "id": 1002605,
        "node_id": "MDc6UHJvamVjdDEwMDI2MDU=",
        "name": "Organization Roadmap",
        "body": "High-level roadmap for the upcoming year.",
        "number": 1,
        "state": "open",
        "creator": {
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
        "created_at": "2011-04-11T20:09:31Z",
        "updated_at": "2014-03-04T18:58:10Z",
        "organization_permission": "write",
        "private": false,
        "permissions": {
          "read": true,
          "write": true,
          "admin": false
        }
      }
    ]
    ```

    


=== "GET Check team permissions for a repository"

    Checks whether a team has `admin`, `push`, `maintain`, `triage`, or `pull` permission for a repository. Repositories inherited through a parent team will also be checked.

    You can also get information about the specified repository, including what permissions the team grants on it, by passing the following custom [media type](https://developer.github.com/v3/media/) via the `application/vnd.github.v3.repository+json` accept header.

    If a team doesn't have permission for the repository, you will receive a `404 Not Found` response status.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}/repos/{owner}/{repo}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:owner` | `string` | Yes | (Required)  | `<string>` |
    | `:repo` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/repos/:owner/:repo
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/repos/:owner/:repo', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/repos/{owner}/{repo}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
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
        "html_url": "https://api.github.com/licenses/mit"
      },
      "forks": 1,
      "open_issues": 1,
      "watchers": 1
    }
    ```

    


=== "PUT Add or update team repository permissions"

    To add a repository to a team or update the team's permission on a repository, the authenticated user must have admin access to the repository, and must be able to see the team. The repository must be owned by the organization, or a direct fork of a repository owned by the organization. You will get a `422 Unprocessable Entity` status if you attempt to add a repository to a team that is not owned by the organization. Note that, if you choose not to pass any parameters, you'll need to set `Content-Length` to zero when calling out to this endpoint. For more information, see "[HTTP verbs](https://developer.github.com/v3/#http-verbs)."

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `PUT /organizations/{org_id}/team/{team_id}/repos/{owner}/{repo}`.

    For more information about the permission levels, see "[Repository permission levels for an organization](https://help.github.com/en/github/setting-up-and-managing-organizations-and-teams/repository-permission-levels-for-an-organization#permission-levels-for-repositories-owned-by-an-organization)".

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:owner` | `string` | Yes | (Required)  | `<string>` |
    | `:repo` | `string` | Yes | (Required)  | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "permission": "<string>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PUT \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/repos/:owner/:repo \
          -d '{
          "permission": "<string>"
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
          "permission": "<string>"
        }

        response = requests.put('https://api.github.com/orgs/:org/teams/:team_slug/repos/:owner/:repo', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PUT /orgs/{org}/teams/{team_slug}/repos/{owner}/{repo}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "permission": "<string>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "DELETE Remove a repository from a team"

    If the authenticated user is an organization owner or a team maintainer, they can remove any repositories from the team. To remove a repository from a team as an organization member, the authenticated user must have admin access to the repository and must be able to see the team. This does not delete the repository, it just removes it from the team.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `DELETE /organizations/{org_id}/team/{team_id}/repos/{owner}/{repo}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    | `:owner` | `string` | Yes | (Required)  | `<string>` |
    | `:repo` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/repos/:owner/:repo
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/teams/:team_slug/repos/:owner/:repo', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/teams/{team_slug}/repos/{owner}/{repo}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List team repositories"

    Lists a team's repositories visible to the authenticated user.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}/repos`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/repos?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/repos?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/repos?per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
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
        "template_repository": "octocat/template",
        "temp_clone_token": "ABTLWHOULUVAXGTRYU7OC2876QJ2O",
        "delete_branch_on_merge": true,
        "subscribers_count": 42,
        "network_count": 0,
        "license": {
          "key": "mit",
          "name": "MIT License",
          "spdx_id": "MIT",
          "url": "https://api.github.com/licenses/mit",
          "node_id": "MDc6TGljZW5zZW1pdA=="
        }
      }
    ]
    ```

    


=== "GET List IdP groups for a team"

    Team synchronization is available for organizations using GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products) in the GitHub Help documentation.

    List IdP groups connected to a team on GitHub.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}/team-sync/group-mappings`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/team-sync/group-mappings
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/team-sync/group-mappings', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/team-sync/group-mappings', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "groups": [
        {
          "group_id": "123",
          "group_name": "Octocat admins",
          "group_description": "The people who configure your octoworld."
        },
        {
          "group_id": "456",
          "group_name": "Octocat docs members",
          "group_description": "The people who make your octoworld come to life."
        }
      ]
    }
    ```

    


=== "PATCH Create or update IdP group connections"

    Team synchronization is available for organizations using GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products) in the GitHub Help documentation.

    Creates, updates, or removes a connection between a team and an IdP group. When adding groups to a team, you must include all new and existing groups to avoid replacing existing groups with the new ones. Specifying an empty `groups` array will remove all connections for a team.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `PATCH /organizations/{org_id}/team/{team_id}/team-sync/group-mappings`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "groups": [
        {
          "group_id": "<string>",
          "group_name": "<string>",
          "group_description": "<string>"
        },
        {
          "group_id": "<string>",
          "group_name": "<string>",
          "group_description": "<string>"
        }
      ]
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PATCH \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/team-sync/group-mappings \
          -d '{
          "groups": [
            {
              "group_id": "<string>",
              "group_name": "<string>",
              "group_description": "<string>"
            },
            {
              "group_id": "<string>",
              "group_name": "<string>",
              "group_description": "<string>"
            }
          ]
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
          "groups": [
            {
              "group_id": "<string>",
              "group_name": "<string>",
              "group_description": "<string>"
            },
            {
              "group_id": "<string>",
              "group_name": "<string>",
              "group_description": "<string>"
            }
          ]
        }

        response = requests.patch('https://api.github.com/orgs/:org/teams/:team_slug/team-sync/group-mappings', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PATCH /orgs/{org}/teams/{team_slug}/team-sync/group-mappings', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "groups": [
              {
                "group_id": "<string>",
                "group_name": "<string>",
                "group_description": "<string>"
              },
              {
                "group_id": "<string>",
                "group_name": "<string>",
                "group_description": "<string>"
              }
            ]
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "groups": [
        {
          "group_id": "123",
          "group_name": "Octocat admins",
          "group_description": "The people who configure your octoworld."
        },
        {
          "group_id": "456",
          "group_name": "Octocat docs members",
          "group_description": "The people who make your octoworld come to life."
        }
      ]
    }
    ```

    


=== "GET Get a team by name"

    Gets a team using the team's `slug`. GitHub generates the `slug` from the team `name`.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 1,
      "node_id": "MDQ6VGVhbTE=",
      "url": "https://api.github.com/teams/1",
      "html_url": "https://api.github.com/teams/justice-league",
      "name": "Justice League",
      "slug": "justice-league",
      "description": "A great team.",
      "privacy": "closed",
      "permission": "admin",
      "members_url": "https://api.github.com/teams/1/members{/member}",
      "repositories_url": "https://api.github.com/teams/1/repos",
      "parent": null,
      "members_count": 3,
      "repos_count": 10,
      "created_at": "2017-07-14T16:53:42Z",
      "updated_at": "2017-08-17T12:37:15Z",
      "organization": {
        "login": "github",
        "id": 1,
        "node_id": "MDEyOk9yZ2FuaXphdGlvbjE=",
        "url": "https://api.github.com/orgs/github",
        "repos_url": "https://api.github.com/orgs/github/repos",
        "events_url": "https://api.github.com/orgs/github/events",
        "hooks_url": "https://api.github.com/orgs/github/hooks",
        "issues_url": "https://api.github.com/orgs/github/issues",
        "members_url": "https://api.github.com/orgs/github/members{/member}",
        "public_members_url": "https://api.github.com/orgs/github/public_members{/member}",
        "avatar_url": "https://github.com/images/error/octocat_happy.gif",
        "description": "A great organization",
        "name": "github",
        "company": "GitHub",
        "blog": "https://github.com/blog",
        "location": "San Francisco",
        "email": "octocat@github.com",
        "is_verified": true,
        "has_organization_projects": true,
        "has_repository_projects": true,
        "public_repos": 2,
        "public_gists": 1,
        "followers": 20,
        "following": 0,
        "html_url": "https://github.com/octocat",
        "created_at": "2008-01-14T04:33:35Z",
        "updated_at": "2017-08-17T12:37:15Z",
        "type": "Organization"
      }
    }
    ```

    


=== "PATCH Update a team"

    To edit a team, the authenticated user must either be an organization owner or a team maintainer.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `PATCH /organizations/{org_id}/team/{team_id}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "name": "<string>",
      "description": "<string>",
      "privacy": "<string>",
      "permission": "pull",
      "parent_team_id": "<integer>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PATCH \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug \
          -d '{
          "name": "<string>",
          "description": "<string>",
          "privacy": "<string>",
          "permission": "pull",
          "parent_team_id": "<integer>"
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
          "name": "<string>",
          "description": "<string>",
          "privacy": "<string>",
          "permission": "pull",
          "parent_team_id": "<integer>"
        }

        response = requests.patch('https://api.github.com/orgs/:org/teams/:team_slug', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PATCH /orgs/{org}/teams/{team_slug}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "name": "<string>",
            "description": "<string>",
            "privacy": "<string>",
            "permission": "pull",
            "parent_team_id": "<integer>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 1,
      "node_id": "MDQ6VGVhbTE=",
      "url": "https://api.github.com/teams/1",
      "html_url": "https://api.github.com/teams/justice-league",
      "name": "Justice League",
      "slug": "justice-league",
      "description": "A great team.",
      "privacy": "closed",
      "permission": "admin",
      "members_url": "https://api.github.com/teams/1/members{/member}",
      "repositories_url": "https://api.github.com/teams/1/repos",
      "parent": null,
      "members_count": 3,
      "repos_count": 10,
      "created_at": "2017-07-14T16:53:42Z",
      "updated_at": "2017-08-17T12:37:15Z",
      "organization": {
        "login": "github",
        "id": 1,
        "node_id": "MDEyOk9yZ2FuaXphdGlvbjE=",
        "url": "https://api.github.com/orgs/github",
        "repos_url": "https://api.github.com/orgs/github/repos",
        "events_url": "https://api.github.com/orgs/github/events",
        "hooks_url": "https://api.github.com/orgs/github/hooks",
        "issues_url": "https://api.github.com/orgs/github/issues",
        "members_url": "https://api.github.com/orgs/github/members{/member}",
        "public_members_url": "https://api.github.com/orgs/github/public_members{/member}",
        "avatar_url": "https://github.com/images/error/octocat_happy.gif",
        "description": "A great organization",
        "name": "github",
        "company": "GitHub",
        "blog": "https://github.com/blog",
        "location": "San Francisco",
        "email": "octocat@github.com",
        "is_verified": true,
        "has_organization_projects": true,
        "has_repository_projects": true,
        "public_repos": 2,
        "public_gists": 1,
        "followers": 20,
        "following": 0,
        "html_url": "https://github.com/octocat",
        "created_at": "2008-01-14T04:33:35Z",
        "updated_at": "2017-08-17T12:37:15Z",
        "type": "Organization"
      }
    }
    ```

    


=== "DELETE Delete a team"

    To delete a team, the authenticated user must be an organization owner or team maintainer.

    If you are an organization owner, deleting a parent team will delete all of its child teams as well.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `DELETE /organizations/{org_id}/team/{team_id}`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X DELETE \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.delete('https://api.github.com/orgs/:org/teams/:team_slug', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('DELETE /orgs/{org}/teams/{team_slug}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {}
    ```

    


=== "GET List pending team invitations"

    The return hash contains a `role` field which refers to the Organization Invitation role and will be one of the following values: `direct_member`, `admin`, `billing_manager`, `hiring_manager`, or `reinstate`. If the invitee is not a GitHub member, the `login` field in the return hash will be `null`.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}/invitations`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/invitations?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/invitations?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/invitations?per_page=30&page=1', {
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
        "login": "monalisa",
        "email": "octocat@github.com",
        "role": "direct_member",
        "created_at": "2016-11-30T06:46:10-08:00",
        "inviter": {
          "login": "other_user",
          "id": 1,
          "node_id": "MDQ6VXNlcjE=",
          "avatar_url": "https://github.com/images/error/other_user_happy.gif",
          "gravatar_id": "",
          "url": "https://api.github.com/users/other_user",
          "html_url": "https://github.com/other_user",
          "followers_url": "https://api.github.com/users/other_user/followers",
          "following_url": "https://api.github.com/users/other_user/following{/other_user}",
          "gists_url": "https://api.github.com/users/other_user/gists{/gist_id}",
          "starred_url": "https://api.github.com/users/other_user/starred{/owner}{/repo}",
          "subscriptions_url": "https://api.github.com/users/other_user/subscriptions",
          "organizations_url": "https://api.github.com/users/other_user/orgs",
          "repos_url": "https://api.github.com/users/other_user/repos",
          "events_url": "https://api.github.com/users/other_user/events{/privacy}",
          "received_events_url": "https://api.github.com/users/other_user/received_events",
          "type": "User",
          "site_admin": false
        },
        "team_count": 2,
        "invitation_team_url": "https://api.github.com/organizations/2/invitations/1/teams"
      }
    ]
    ```

    


=== "GET List team members"

    Team members will include the members of child teams.

    To list members in a team, the team must be visible to the authenticated user.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `role` | `string` | Yes | Filters members returned by their role in the team. Can be one of:  <br>\* `member` - normal members of the team.  <br>\* `maintainer` - team maintainers.  <br>\* `all` - all members of the team. | `all` |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/members?role=all&per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/members?role=all&per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/members?role=all&per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
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
      }
    ]
    ```

    


=== "GET List child teams"

    Lists the child teams of the team specified by `{team_slug}`.

    **Note:** You can also specify a team by `org_id` and `team_id` using the route `GET /organizations/{org_id}/team/{team_id}/teams`.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    | `:team_slug` | `string` | Yes | (Required) team_slug parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams/:team_slug/teams?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams/:team_slug/teams?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams/{team_slug}/teams?per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
        "id": 2,
        "node_id": "MDQ6VGVhbTI=",
        "url": "https://api.github.com/teams/2",
        "name": "Original Roster",
        "slug": "original-roster",
        "description": "Started it all.",
        "privacy": "closed",
        "permission": "admin",
        "members_url": "https://api.github.com/teams/2/members{/member}",
        "repositories_url": "https://api.github.com/teams/2/repos",
        "parent": {
          "id": 1,
          "node_id": "MDQ6VGVhbTE=",
          "url": "https://api.github.com/teams/1",
          "html_url": "https://api.github.com/teams/justice-league",
          "name": "Justice League",
          "slug": "justice-league",
          "description": "A great team.",
          "privacy": "closed",
          "permission": "admin",
          "members_url": "https://api.github.com/teams/1/members{/member}",
          "repositories_url": "https://api.github.com/teams/1/repos"
        },
        "html_url": "https://github.com/orgs/rails/teams/core"
      }
    ]
    ```

    


=== "GET List teams"

    Lists all teams in an organization that are visible to the authenticated user.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/teams?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/teams?per_page=30&page=1', {
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
        "node_id": "MDQ6VGVhbTE=",
        "url": "https://api.github.com/teams/1",
        "html_url": "https://api.github.com/teams/justice-league",
        "name": "Justice League",
        "slug": "justice-league",
        "description": "A great team.",
        "privacy": "closed",
        "permission": "admin",
        "members_url": "https://api.github.com/teams/1/members{/member}",
        "repositories_url": "https://api.github.com/teams/1/repos",
        "parent": null
      }
    ]
    ```

    


=== "POST Create a team"

    To create a team, the authenticated user must be a member or owner of `{org}`. By default, organization members can create teams. Organization owners can limit team creation to organization owners. For more information, see "[Setting team creation permissions](https://help.github.com/en/articles/setting-team-creation-permissions-in-your-organization)."

    When you create a new team, you automatically become a team maintainer without explicitly adding yourself to the optional array of `maintainers`. For more information, see "[About teams](https://help.github.com/en/github/setting-up-and-managing-organizations-and-teams/about-teams)".

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "name": "<string>",
      "description": "<string>",
      "maintainers": [
        "<string>",
        "<string>"
      ],
      "repo_names": [
        "<string>",
        "<string>"
      ],
      "privacy": "<string>",
      "permission": "pull",
      "parent_team_id": "<integer>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X POST \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/teams \
          -d '{
          "name": "<string>",
          "description": "<string>",
          "maintainers": [
            "<string>",
            "<string>"
          ],
          "repo_names": [
            "<string>",
            "<string>"
          ],
          "privacy": "<string>",
          "permission": "pull",
          "parent_team_id": "<integer>"
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
          "name": "<string>",
          "description": "<string>",
          "maintainers": [
            "<string>",
            "<string>"
          ],
          "repo_names": [
            "<string>",
            "<string>"
          ],
          "privacy": "<string>",
          "permission": "pull",
          "parent_team_id": "<integer>"
        }

        response = requests.post('https://api.github.com/orgs/:org/teams', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('POST /orgs/{org}/teams', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "name": "<string>",
            "description": "<string>",
            "maintainers": [
              "<string>",
              "<string>"
            ],
            "repo_names": [
              "<string>",
              "<string>"
            ],
            "privacy": "<string>",
            "permission": "pull",
            "parent_team_id": "<integer>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "id": 1,
      "node_id": "MDQ6VGVhbTE=",
      "url": "https://api.github.com/teams/1",
      "html_url": "https://api.github.com/teams/justice-league",
      "name": "Justice League",
      "slug": "justice-league",
      "description": "A great team.",
      "privacy": "closed",
      "permission": "admin",
      "members_url": "https://api.github.com/teams/1/members{/member}",
      "repositories_url": "https://api.github.com/teams/1/repos",
      "parent": null,
      "members_count": 3,
      "repos_count": 10,
      "created_at": "2017-07-14T16:53:42Z",
      "updated_at": "2017-08-17T12:37:15Z",
      "organization": {
        "login": "github",
        "id": 1,
        "node_id": "MDEyOk9yZ2FuaXphdGlvbjE=",
        "url": "https://api.github.com/orgs/github",
        "repos_url": "https://api.github.com/orgs/github/repos",
        "events_url": "https://api.github.com/orgs/github/events",
        "hooks_url": "https://api.github.com/orgs/github/hooks",
        "issues_url": "https://api.github.com/orgs/github/issues",
        "members_url": "https://api.github.com/orgs/github/members{/member}",
        "public_members_url": "https://api.github.com/orgs/github/public_members{/member}",
        "avatar_url": "https://github.com/images/error/octocat_happy.gif",
        "description": "A great organization",
        "name": "github",
        "company": "GitHub",
        "blog": "https://github.com/blog",
        "location": "San Francisco",
        "email": "octocat@github.com",
        "is_verified": true,
        "has_organization_projects": true,
        "has_repository_projects": true,
        "public_repos": 2,
        "public_gists": 1,
        "followers": 20,
        "following": 0,
        "html_url": "https://github.com/octocat",
        "created_at": "2008-01-14T04:33:35Z",
        "updated_at": "2017-08-17T12:37:15Z",
        "type": "Organization"
      }
    }
    ```

    


=== "GET Get an organization"

    To see many of the organization response values, you need to be an authenticated organization owner with the `admin:org` scope. When the value of `two_factor_requirement_enabled` is `true`, the organization requires all members, billing managers, and outside collaborators to enable [two-factor authentication](https://help.github.com/articles/securing-your-account-with-two-factor-authentication-2fa/).

    GitHub Apps with the `Organization plan` permission can use this endpoint to retrieve information about an organization's GitHub plan. See "[Authenticating with GitHub Apps](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/)" for details. For an example response, see "[Response with GitHub plan information](https://developer.github.com/v3/orgs/#response-with-github-plan-information)."

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "login": "github",
      "id": 1,
      "node_id": "MDEyOk9yZ2FuaXphdGlvbjE=",
      "url": "https://api.github.com/orgs/github",
      "repos_url": "https://api.github.com/orgs/github/repos",
      "events_url": "https://api.github.com/orgs/github/events",
      "hooks_url": "https://api.github.com/orgs/github/hooks",
      "issues_url": "https://api.github.com/orgs/github/issues",
      "members_url": "https://api.github.com/orgs/github/members{/member}",
      "public_members_url": "https://api.github.com/orgs/github/public_members{/member}",
      "avatar_url": "https://github.com/images/error/octocat_happy.gif",
      "description": "A great organization",
      "name": "github",
      "company": "GitHub",
      "blog": "https://github.com/blog",
      "location": "San Francisco",
      "email": "octocat@github.com",
      "twitter_username": "github",
      "is_verified": true,
      "has_organization_projects": true,
      "has_repository_projects": true,
      "public_repos": 2,
      "public_gists": 1,
      "followers": 20,
      "following": 0,
      "html_url": "https://github.com/octocat",
      "created_at": "2008-01-14T04:33:35Z",
      "updated_at": "2014-03-03T18:58:10Z",
      "type": "Organization",
      "total_private_repos": 100,
      "owned_private_repos": 100,
      "private_gists": 81,
      "disk_usage": 10000,
      "collaborators": 8,
      "billing_email": "mona@github.com",
      "plan": {
        "name": "Medium",
        "space": 400,
        "private_repos": 20
      },
      "default_repository_permission": "read",
      "members_can_create_repositories": true,
      "two_factor_requirement_enabled": true,
      "members_allowed_repository_creation_type": "all",
      "members_can_create_public_repositories": false,
      "members_can_create_private_repositories": false,
      "members_can_create_internal_repositories": false
    }
    ```

    


=== "PATCH Update an organization"

    **Parameter Deprecation Notice:** GitHub will replace and discontinue `members_allowed_repository_creation_type` in favor of more granular permissions. The new input parameters are `members_can_create_public_repositories`, `members_can_create_private_repositories` for all organizations and `members_can_create_internal_repositories` for organizations associated with an enterprise account using GitHub Enterprise Cloud or GitHub Enterprise Server 2.20+. For more information, see the [blog post](https://developer.github.com/changes/2019-12-03-internal-visibility-changes).

    Enables an authenticated organization owner with the `admin:org` scope to update the organization's profile and member privileges.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    
    #### Request Body
    
    ```json
    {
      "billing_email": "<string>",
      "company": "<string>",
      "email": "<string>",
      "twitter_username": "<string>",
      "location": "<string>",
      "name": "<string>",
      "description": "<string>",
      "has_organization_projects": "<boolean>",
      "has_repository_projects": "<boolean>",
      "default_repository_permission": "read",
      "members_can_create_repositories": true,
      "members_can_create_internal_repositories": "<boolean>",
      "members_can_create_private_repositories": "<boolean>",
      "members_can_create_public_repositories": "<boolean>",
      "members_allowed_repository_creation_type": "<string>",
      "blog": "<string>"
    }
    ```
    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X PATCH \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org \
          -d '{
          "billing_email": "<string>",
          "company": "<string>",
          "email": "<string>",
          "twitter_username": "<string>",
          "location": "<string>",
          "name": "<string>",
          "description": "<string>",
          "has_organization_projects": "<boolean>",
          "has_repository_projects": "<boolean>",
          "default_repository_permission": "read",
          "members_can_create_repositories": true,
          "members_can_create_internal_repositories": "<boolean>",
          "members_can_create_private_repositories": "<boolean>",
          "members_can_create_public_repositories": "<boolean>",
          "members_allowed_repository_creation_type": "<string>",
          "blog": "<string>"
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
          "billing_email": "<string>",
          "company": "<string>",
          "email": "<string>",
          "twitter_username": "<string>",
          "location": "<string>",
          "name": "<string>",
          "description": "<string>",
          "has_organization_projects": "<boolean>",
          "has_repository_projects": "<boolean>",
          "default_repository_permission": "read",
          "members_can_create_repositories": true,
          "members_can_create_internal_repositories": "<boolean>",
          "members_can_create_private_repositories": "<boolean>",
          "members_can_create_public_repositories": "<boolean>",
          "members_allowed_repository_creation_type": "<string>",
          "blog": "<string>"
        }

        response = requests.patch('https://api.github.com/orgs/:org', headers=headers, data=json.dumps(data))
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('PATCH /orgs/{org}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          },
          ...{
            "billing_email": "<string>",
            "company": "<string>",
            "email": "<string>",
            "twitter_username": "<string>",
            "location": "<string>",
            "name": "<string>",
            "description": "<string>",
            "has_organization_projects": "<boolean>",
            "has_repository_projects": "<boolean>",
            "default_repository_permission": "read",
            "members_can_create_repositories": true,
            "members_can_create_internal_repositories": "<boolean>",
            "members_can_create_private_repositories": "<boolean>",
            "members_can_create_public_repositories": "<boolean>",
            "members_allowed_repository_creation_type": "<string>",
            "blog": "<string>"
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "login": "github",
      "id": 1,
      "node_id": "MDEyOk9yZ2FuaXphdGlvbjE=",
      "url": "https://api.github.com/orgs/github",
      "repos_url": "https://api.github.com/orgs/github/repos",
      "events_url": "https://api.github.com/orgs/github/events",
      "hooks_url": "https://api.github.com/orgs/github/hooks",
      "issues_url": "https://api.github.com/orgs/github/issues",
      "members_url": "https://api.github.com/orgs/github/members{/member}",
      "public_members_url": "https://api.github.com/orgs/github/public_members{/member}",
      "avatar_url": "https://github.com/images/error/octocat_happy.gif",
      "description": "A great organization",
      "name": "github",
      "company": "GitHub",
      "blog": "https://github.com/blog",
      "location": "San Francisco",
      "email": "octocat@github.com",
      "twitter_username": "github",
      "is_verified": true,
      "has_organization_projects": true,
      "has_repository_projects": true,
      "public_repos": 2,
      "public_gists": 1,
      "followers": 20,
      "following": 0,
      "html_url": "https://github.com/octocat",
      "created_at": "2008-01-14T04:33:35Z",
      "type": "Organization",
      "total_private_repos": 100,
      "owned_private_repos": 100,
      "private_gists": 81,
      "disk_usage": 10000,
      "collaborators": 8,
      "billing_email": "mona@github.com",
      "plan": {
        "name": "Medium",
        "space": 400,
        "private_repos": 20
      },
      "default_repository_permission": "read",
      "members_can_create_repositories": true,
      "two_factor_requirement_enabled": true,
      "members_allowed_repository_creation_type": "all",
      "members_can_create_public_repositories": false,
      "members_can_create_private_repositories": false,
      "members_can_create_internal_repositories": false,
      "updated_at": "2014-03-03T18:58:10Z"
    }
    ```

    


=== "GET List public organization events"

    No description.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/events?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/events?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/events?per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      {
        "id": "Duis",
        "type": "labore magna",
        "actor": {
          "id": 95373152,
          "login": "minim fugiat non",
          "gravatar_id": "est nisi dolor",
          "url": "elit dolor tempor in aliquip",
          "avatar_url": "anim officia pariatur nostrud ipsum",
          "display_login": "cillum Excepteur aute pariatur"
        },
        "repo": {
          "id": 7809622,
          "name": "sunt aliqua ipsum tempor",
          "url": "mollit nisi"
        },
        "payload": {
          "action": "enim in id dolore",
          "issue": {
            "assignee": {
              "avatar_url": "https://github.com/images/error/octocat_happy.gif",
              "events_url": "https://api.github.com/users/octocat/events{/privacy}",
              "followers_url": "https://api.github.com/users/octocat/followers",
              "following_url": "https://api.github.com/users/octocat/following{/other_user}",
              "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
              "gravatar_id": "",
              "html_url": "https://github.com/octocat",
              "id": 1,
              "node_id": "MDQ6VXNlcjE=",
              "login": "octocat",
              "organizations_url": "https://api.github.com/users/octocat/orgs",
              "received_events_url": "https://api.github.com/users/octocat/received_events",
              "repos_url": "https://api.github.com/users/octocat/repos",
              "site_admin": true,
              "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
              "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
              "type": "User",
              "url": "https://api.github.com/users/octocat",
              "starred_at": "\"2020-07-09T00:17:55Z\""
            },
            "closed_at": "Excepteur proident",
            "comments": 0,
            "comments_url": "https://api.github.com/repos/octocat/Hello-World/issues/1347/comments",
            "events_url": "https://api.github.com/repos/octocat/Hello-World/issues/1347/events",
            "html_url": "https://github.com/octocat/Hello-World/issues/1347",
            "id": 1,
            "node_id": "MDU6SXNzdWUx",
            "labels": [
              {
                "type": "boolean"
              },
              {
                "type": "boolean"
              }
            ],
            "labels_url": "https://api.github.com/repos/octocat/Hello-World/issues/1347/labels{/name}",
            "milestone": {
              "closed_issues": 8,
              "creator": {
                "value": "<Error: Too many levels of nesting to fake this schema>"
              },
              "description": "Tracking milestone for version 1.0",
              "due_on": "2012-10-09T23:39:01Z",
              "closed_at": "2013-02-12T13:22:01Z",
              "id": 1002604,
              "node_id": "MDk6TWlsZXN0b25lMTAwMjYwNA==",
              "labels_url": "https://api.github.com/repos/octocat/Hello-World/milestones/1/labels",
              "html_url": "https://github.com/octocat/Hello-World/milestones/v1.0",
              "number": 42,
              "open_issues": 4,
              "state": "open",
              "title": "v1.0",
              "url": "https://api.github.com/repos/octocat/Hello-World/milestones/1",
              "created_at": "2011-04-10T20:09:31Z",
              "updated_at": "2014-03-03T18:58:10Z"
            },
            "number": 1347,
            "repository_url": "https://api.github.com/repos/octocat/Hello-World",
            "state": "open",
            "locked": true,
            "title": "Found a bug",
            "url": "https://api.github.com/repos/octocat/Hello-World/issues/1347",
            "user": {
              "avatar_url": "https://github.com/images/error/octocat_happy.gif",
              "events_url": "https://api.github.com/users/octocat/events{/privacy}",
              "followers_url": "https://api.github.com/users/octocat/followers",
              "following_url": "https://api.github.com/users/octocat/following{/other_user}",
              "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
              "gravatar_id": "",
              "html_url": "https://github.com/octocat",
              "id": 1,
              "node_id": "MDQ6VXNlcjE=",
              "login": "octocat",
              "organizations_url": "https://api.github.com/users/octocat/orgs",
              "received_events_url": "https://api.github.com/users/octocat/received_events",
              "repos_url": "https://api.github.com/users/octocat/repos",
              "site_admin": true,
              "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
              "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
              "type": "User",
              "url": "https://api.github.com/users/octocat",
              "starred_at": "\"2020-07-09T00:17:55Z\""
            },
            "author_association": "in",
            "created_at": "2011-04-22T13:33:48Z",
            "updated_at": "2011-04-22T13:33:48Z",
            "body": "I'm having a problem with this.",
            "assignees": [
              {
                "avatar_url": "https://github.com/images/error/octocat_happy.gif",
                "events_url": "https://api.github.com/users/octocat/events{/privacy}",
                "followers_url": "https://api.github.com/users/octocat/followers",
                "following_url": "https://api.github.com/users/octocat/following{/other_user}",
                "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
                "gravatar_id": "",
                "html_url": "https://github.com/octocat",
                "id": 1,
                "node_id": "MDQ6VXNlcjE=",
                "login": "octocat",
                "organizations_url": "https://api.github.com/users/octocat/orgs",
                "received_events_url": "https://api.github.com/users/octocat/received_events",
                "repos_url": "https://api.github.com/users/octocat/repos",
                "site_admin": false,
                "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
                "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
                "type": "User",
                "url": "https://api.github.com/users/octocat",
                "starred_at": "\"2020-07-09T00:17:55Z\""
              },
              {
                "avatar_url": "https://github.com/images/error/octocat_happy.gif",
                "events_url": "https://api.github.com/users/octocat/events{/privacy}",
                "followers_url": "https://api.github.com/users/octocat/followers",
                "following_url": "https://api.github.com/users/octocat/following{/other_user}",
                "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
                "gravatar_id": "",
                "html_url": "https://github.com/octocat",
                "id": 1,
                "node_id": "MDQ6VXNlcjE=",
                "login": "octocat",
                "organizations_url": "https://api.github.com/users/octocat/orgs",
                "received_events_url": "https://api.github.com/users/octocat/received_events",
                "repos_url": "https://api.github.com/users/octocat/repos",
                "site_admin": false,
                "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
                "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
                "type": "User",
                "url": "https://api.github.com/users/octocat",
                "starred_at": "\"2020-07-09T00:17:55Z\""
              }
            ],
            "active_lock_reason": "too heated",
            "pull_request": {
              "diff_url": "incididunt adipisicing veniam qui",
              "html_url": "laborum",
              "patch_url": "minim ut",
              "url": "culpa Duis reprehenderit ut Excepteur",
              "merged_at": "esse et culpa"
            },
            "body_html": "labore",
            "body_text": "fugiat dolore consectetur",
            "timeline_url": "reprehenderit",
            "repository": {
              "archive_url": "http://api.github.com/repos/octocat/Hello-World/{archive_format}{/ref}",
              "assignees_url": "http://api.github.com/repos/octocat/Hello-World/assignees{/user}",
              "blobs_url": "http://api.github.com/repos/octocat/Hello-World/git/blobs{/sha}",
              "branches_url": "http://api.github.com/repos/octocat/Hello-World/branches{/branch}",
              "collaborators_url": "http://api.github.com/repos/octocat/Hello-World/collaborators{/collaborator}",
              "comments_url": "http://api.github.com/repos/octocat/Hello-World/comments{/number}",
              "commits_url": "http://api.github.com/repos/octocat/Hello-World/commits{/sha}",
              "compare_url": "http://api.github.com/repos/octocat/Hello-World/compare/{base}...{head}",
              "contents_url": "http://api.github.com/repos/octocat/Hello-World/contents/{+path}",
              "contributors_url": "http://api.github.com/repos/octocat/Hello-World/contributors",
              "deployments_url": "http://api.github.com/repos/octocat/Hello-World/deployments",
              "description": "This your first repo!",
              "downloads_url": "http://api.github.com/repos/octocat/Hello-World/downloads",
              "events_url": "http://api.github.com/repos/octocat/Hello-World/events",
              "fork": true,
              "forks_url": "http://api.github.com/repos/octocat/Hello-World/forks",
              "full_name": "octocat/Hello-World",
              "git_commits_url": "http://api.github.com/repos/octocat/Hello-World/git/commits{/sha}",
              "git_refs_url": "http://api.github.com/repos/octocat/Hello-World/git/refs{/sha}",
              "git_tags_url": "http://api.github.com/repos/octocat/Hello-World/git/tags{/sha}",
              "hooks_url": "http://api.github.com/repos/octocat/Hello-World/hooks",
              "html_url": "https://github.com/octocat/Hello-World",
              "id": 42,
              "node_id": "MDEwOlJlcG9zaXRvcnkxMjk2MjY5",
              "issue_comment_url": "http://api.github.com/repos/octocat/Hello-World/issues/comments{/number}",
              "issue_events_url": "http://api.github.com/repos/octocat/Hello-World/issues/events{/number}",
              "issues_url": "http://api.github.com/repos/octocat/Hello-World/issues{/number}",
              "keys_url": "http://api.github.com/repos/octocat/Hello-World/keys{/key_id}",
              "labels_url": "http://api.github.com/repos/octocat/Hello-World/labels{/name}",
              "languages_url": "http://api.github.com/repos/octocat/Hello-World/languages",
              "merges_url": "http://api.github.com/repos/octocat/Hello-World/merges",
              "milestones_url": "http://api.github.com/repos/octocat/Hello-World/milestones{/number}",
              "name": "Team Environment",
              "notifications_url": "http://api.github.com/repos/octocat/Hello-World/notifications{?since,all,participating}",
              "owner": {
                "avatar_url": "https://github.com/images/error/octocat_happy.gif",
                "events_url": "https://api.github.com/users/octocat/events{/privacy}",
                "followers_url": "https://api.github.com/users/octocat/followers",
                "following_url": "https://api.github.com/users/octocat/following{/other_user}",
                "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
                "gravatar_id": "",
                "html_url": "https://github.com/octocat",
                "id": 1,
                "node_id": "MDQ6VXNlcjE=",
                "login": "octocat",
                "organizations_url": "https://api.github.com/users/octocat/orgs",
                "received_events_url": "https://api.github.com/users/octocat/received_events",
                "repos_url": "https://api.github.com/users/octocat/repos",
                "site_admin": true,
                "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
                "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
                "type": "User",
                "url": "https://api.github.com/users/octocat",
                "starred_at": "\"2020-07-09T00:17:55Z\""
              },
              "private": false,
              "pulls_url": "http://api.github.com/repos/octocat/Hello-World/pulls{/number}",
              "releases_url": "http://api.github.com/repos/octocat/Hello-World/releases{/id}",
              "stargazers_url": "http://api.github.com/repos/octocat/Hello-World/stargazers",
              "statuses_url": "http://api.github.com/repos/octocat/Hello-World/statuses/{sha}",
              "subscribers_url": "http://api.github.com/repos/octocat/Hello-World/subscribers",
              "subscription_url": "http://api.github.com/repos/octocat/Hello-World/subscription",
              "tags_url": "http://api.github.com/repos/octocat/Hello-World/tags",
              "teams_url": "http://api.github.com/repos/octocat/Hello-World/teams",
              "trees_url": "http://api.github.com/repos/octocat/Hello-World/git/trees{/sha}",
              "url": "https://api.github.com/repos/octocat/Hello-World",
              "clone_url": "https://github.com/octocat/Hello-World.git",
              "default_branch": "master",
              "forks": 74059665,
              "forks_count": 9,
              "git_url": "git:github.com/octocat/Hello-World.git",
              "has_downloads": true,
              "has_issues": true,
              "has_projects": true,
              "has_wiki": true,
              "has_pages": true,
              "homepage": "https://github.com",
              "language": "irure aute commodo",
              "archived": false,
              "disabled": false,
              "mirror_url": "git:git.example.com/octocat/Hello-World",
              "open_issues": 3584172,
              "open_issues_count": 0,
              "license": {
                "value": "<Error: Too many levels of nesting to fake this schema>"
              },
              "pushed_at": "2011-01-26T19:06:43Z",
              "size": 108,
              "ssh_url": "git@github.com:octocat/Hello-World.git",
              "stargazers_count": 80,
              "svn_url": "https://svn.github.com/octocat/Hello-World",
              "watchers": 95751259,
              "watchers_count": 80,
              "created_at": "2011-01-26T19:01:12Z",
              "updated_at": "2011-01-26T19:14:43Z",
              "permissions": {
                "admin": true,
                "pull": true,
                "push": true,
                "triage": false,
                "maintain": true
              },
              "is_template": true,
              "topics": [
                "aute in",
                "do laborum fugiat dolore culpa"
              ],
              "visibility": "public",
              "allow_rebase_merge": true,
              "template_repository": {
                "id": -74448652,
                "node_id": "labore proident aliqua",
                "name": "reprehenderit cupidatat",
                "full_name": "Duis ipsum amet proident dolor",
                "owner": {
                  "login": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "id": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "node_id": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "avatar_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "gravatar_id": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "html_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "followers_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "following_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "gists_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "starred_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "subscriptions_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "organizations_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "repos_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "events_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "received_events_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "type": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "site_admin": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  }
                },
                "private": true,
                "html_url": "quis et",
                "description": "cupidatat enim Ut",
                "fork": true,
                "url": "anim quis Lorem do",
                "archive_url": "nulla sed fugiat Lorem",
                "assignees_url": "sit ut",
                "blobs_url": "ex ipsum voluptate",
                "branches_url": "ullamco amet sunt",
                "collaborators_url": "moll",
                "comments_url": "Duis aute eu",
                "commits_url": "labore fugiat",
                "compare_url": "quis id",
                "contents_url": "aute in minim",
                "contributors_url": "consequat Duis Lorem voluptate",
                "deployments_url": "ex ipsum minim",
                "downloads_url": "officia incididunt nisi Ut",
                "events_url": "qui",
                "forks_url": "in incididunt non",
                "git_commits_url": "dolor sint enim sed voluptate",
                "git_refs_url": "irure cupidatat aliquip voluptate",
                "git_tags_url": "commodo",
                "git_url": "quis anim nisi dolore deserunt",
                "issue_comment_url": "deserunt Excepteur occaecat",
                "issue_events_url": "fugiat laborum",
                "issues_url": "proident p",
                "keys_url": "sunt dolor enim amet",
                "labels_url": "ullamco laboris",
                "languages_url": "id aute voluptate",
                "merges_url": "nostrud paria",
                "milestones_url": "in officia",
                "notifications_url": "dolor qui deserunt tem",
                "pulls_url": "et aute",
                "releases_url": "ex",
                "ssh_url": "esse ut dolor",
                "stargazers_url": "ad dolore eu",
                "statuses_url": "id nisi eiusmod",
                "subscribers_url": "aute voluptate ullamco sed",
                "subscription_url": "tempor consequat qui elit",
                "tags_url": "in laborum",
                "teams_url": "eiusmod eu",
                "trees_url": "enim pariatur nulla in et",
                "clone_url": "sit pariatur dolore nisi",
                "mirror_url": "do",
                "hooks_url": "qui commodo consequat dolore elit",
                "svn_url": "ullamco sunt qui dolore eiusmod",
                "homepage": "Lorem aliquip",
                "language": "sunt sit",
                "forks_count": -6817855,
                "stargazers_count": -71285277,
                "watchers_count": -20279907,
                "size": 39472844,
                "default_branch": "officia et Excepteur do ex",
                "open_issues_count": 22674481,
                "is_template": true,
                "topics": [
                  {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  }
                ],
                "has_issues": false,
                "has_projects": false,
                "has_wiki": false,
                "has_pages": true,
                "has_downloads": true,
                "archived": true,
                "disabled": true,
                "visibility": "sunt commodo",
                "pushed_at": "tempor do ex culpa elit",
                "created_at": "veniam",
                "updated_at": "in quis cillum sunt",
                "permissions": {
                  "admin": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "push": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "pull": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  }
                },
                "allow_rebase_merge": false,
                "template_repository": "Excepteur sit elit mollit",
                "temp_clone_token": "nostrud magna dolore cupidatat",
                "allow_squash_merge": false,
                "delete_branch_on_merge": true,
                "allow_merge_commit": false,
                "subscribers_count": -65005951,
                "network_count": -69044006
              },
              "temp_clone_token": "labore dolore",
              "allow_squash_merge": true,
              "delete_branch_on_merge": false,
              "allow_merge_commit": true,
              "subscribers_count": -4318022,
              "network_count": -10810678,
              "master_branch": "id anim in",
              "starred_at": "\"2020-07-09T00:17:42Z\""
            },
            "performed_via_github_app": {
              "id": 37,
              "node_id": "MDExOkludGVncmF0aW9uMQ==",
              "owner": {
                "value": "<Error: Too many levels of nesting to fake this schema>"
              },
              "name": "Probot Owners",
              "description": "",
              "external_url": "https://example.com",
              "html_url": "https://github.com/apps/super-ci",
              "created_at": "2017-07-08T16:18:44-04:00",
              "updated_at": "2017-07-08T16:18:44-04:00",
              "permissions": {
                "issues": "read",
                "deployments": "write"
              },
              "events": [
                "label",
                "deployment"
              ],
              "slug": "probot-owners",
              "installations_count": 5,
              "client_id": "\"Iv1.25b5d1e65ffc4022\"",
              "client_secret": "\"1d4b2097ac622ba702d19de498f005747a8b21d3\"",
              "webhook_secret": "\"6fba8f2fc8a7e8f2cca5577eddd82ca7586b3b6b\"",
              "pem": "\"{{vault:rsa-private-key}}\\n\""
            }
          },
          "comment": {
            "id": 42,
            "node_id": "anim amet",
            "html_url": "ullamco proident elit dolore",
            "issue_url": "cupidatat id proident deserunt",
            "author_association": "eiusmod occaecat mollit",
            "user": {
              "avatar_url": "https://github.com/images/error/octocat_happy.gif",
              "events_url": "https://api.github.com/users/octocat/events{/privacy}",
              "followers_url": "https://api.github.com/users/octocat/followers",
              "following_url": "https://api.github.com/users/octocat/following{/other_user}",
              "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
              "gravatar_id": "",
              "html_url": "https://github.com/octocat",
              "id": 1,
              "node_id": "MDQ6VXNlcjE=",
              "login": "octocat",
              "organizations_url": "https://api.github.com/users/octocat/orgs",
              "received_events_url": "https://api.github.com/users/octocat/received_events",
              "repos_url": "https://api.github.com/users/octocat/repos",
              "site_admin": true,
              "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
              "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
              "type": "User",
              "url": "https://api.github.com/users/octocat",
              "starred_at": "\"2020-07-09T00:17:55Z\""
            },
            "url": "https://api.github.com/repositories/42/issues/comments/1",
            "created_at": "2011-04-14T16:00:49Z",
            "updated_at": "2011-04-14T16:00:49Z",
            "body": "What version of Safari were you using when you observed this bug?",
            "body_text": "deserunt Duis",
            "body_html": "Ut",
            "performed_via_github_app": {
              "id": 37,
              "node_id": "MDExOkludGVncmF0aW9uMQ==",
              "owner": {
                "value": "<Error: Too many levels of nesting to fake this schema>"
              },
              "name": "Probot Owners",
              "description": "",
              "external_url": "https://example.com",
              "html_url": "https://github.com/apps/super-ci",
              "created_at": "2017-07-08T16:18:44-04:00",
              "updated_at": "2017-07-08T16:18:44-04:00",
              "permissions": {
                "issues": "read",
                "deployments": "write"
              },
              "events": [
                "label",
                "deployment"
              ],
              "slug": "probot-owners",
              "installations_count": 5,
              "client_id": "\"Iv1.25b5d1e65ffc4022\"",
              "client_secret": "\"1d4b2097ac622ba702d19de498f005747a8b21d3\"",
              "webhook_secret": "\"6fba8f2fc8a7e8f2cca5577eddd82ca7586b3b6b\"",
              "pem": "\"{{vault:rsa-private-key}}\\n\""
            },
            "reactions": {
              "url": "Ut in sunt fugiat occaecat",
              "total_count": 19431373,
              "+1": -13368948,
              "-1": -90524562,
              "laugh": 17359216,
              "confused": 29335122,
              "heart": -66585006,
              "hooray": 75254661,
              "eyes": 58121707,
              "rocket": 51746123
            }
          },
          "pages": [
            {
              "page_name": "dolore ",
              "title": "exercitation",
              "summary": "et qui",
              "action": "proident laborum aute",
              "sha": "commodo sunt non",
              "html_url": "amet"
            },
            {
              "page_name": "commodo nisi proident",
              "title": "consequat reprehe",
              "summary": "nulla aute dolore tempor",
              "action": "magna consequat",
              "sha": "cillum esse in qui",
              "html_url": "qui sunt Duis"
            }
          ]
        },
        "public": false,
        "created_at": "incididunt u",
        "org": {
          "id": -35339806,
          "login": "quis aute",
          "gravatar_id": "qui dolore aliqu",
          "url": "nulla cillum est dolore magna",
          "avatar_url": "id",
          "display_login": "reprehenderit Duis"
        }
      },
      {
        "id": "minim aute qui enim Lorem",
        "type": "ipsum elit cupidatat sed",
        "actor": {
          "id": 84442394,
          "login": "ut",
          "gravatar_id": "dolore",
          "url": "labore in",
          "avatar_url": "mollit elit nulla",
          "display_login": "dolor occaecat"
        },
        "repo": {
          "id": -29038580,
          "name": "laborum adipisicing pariatur t",
          "url": "in"
        },
        "payload": {
          "action": "ex Excepteur vo",
          "issue": {
            "assignee": {
              "avatar_url": "https://github.com/images/error/octocat_happy.gif",
              "events_url": "https://api.github.com/users/octocat/events{/privacy}",
              "followers_url": "https://api.github.com/users/octocat/followers",
              "following_url": "https://api.github.com/users/octocat/following{/other_user}",
              "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
              "gravatar_id": "",
              "html_url": "https://github.com/octocat",
              "id": 1,
              "node_id": "MDQ6VXNlcjE=",
              "login": "octocat",
              "organizations_url": "https://api.github.com/users/octocat/orgs",
              "received_events_url": "https://api.github.com/users/octocat/received_events",
              "repos_url": "https://api.github.com/users/octocat/repos",
              "site_admin": false,
              "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
              "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
              "type": "User",
              "url": "https://api.github.com/users/octocat",
              "starred_at": "\"2020-07-09T00:17:55Z\""
            },
            "closed_at": "Excepteur",
            "comments": 0,
            "comments_url": "https://api.github.com/repos/octocat/Hello-World/issues/1347/comments",
            "events_url": "https://api.github.com/repos/octocat/Hello-World/issues/1347/events",
            "html_url": "https://github.com/octocat/Hello-World/issues/1347",
            "id": 1,
            "node_id": "MDU6SXNzdWUx",
            "labels": [
              {
                "type": "boolean"
              },
              {
                "type": "boolean"
              }
            ],
            "labels_url": "https://api.github.com/repos/octocat/Hello-World/issues/1347/labels{/name}",
            "milestone": {
              "closed_issues": 8,
              "creator": {
                "value": "<Error: Too many levels of nesting to fake this schema>"
              },
              "description": "Tracking milestone for version 1.0",
              "due_on": "2012-10-09T23:39:01Z",
              "closed_at": "2013-02-12T13:22:01Z",
              "id": 1002604,
              "node_id": "MDk6TWlsZXN0b25lMTAwMjYwNA==",
              "labels_url": "https://api.github.com/repos/octocat/Hello-World/milestones/1/labels",
              "html_url": "https://github.com/octocat/Hello-World/milestones/v1.0",
              "number": 42,
              "open_issues": 4,
              "state": "open",
              "title": "v1.0",
              "url": "https://api.github.com/repos/octocat/Hello-World/milestones/1",
              "created_at": "2011-04-10T20:09:31Z",
              "updated_at": "2014-03-03T18:58:10Z"
            },
            "number": 1347,
            "repository_url": "https://api.github.com/repos/octocat/Hello-World",
            "state": "open",
            "locked": true,
            "title": "Found a bug",
            "url": "https://api.github.com/repos/octocat/Hello-World/issues/1347",
            "user": {
              "avatar_url": "https://github.com/images/error/octocat_happy.gif",
              "events_url": "https://api.github.com/users/octocat/events{/privacy}",
              "followers_url": "https://api.github.com/users/octocat/followers",
              "following_url": "https://api.github.com/users/octocat/following{/other_user}",
              "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
              "gravatar_id": "",
              "html_url": "https://github.com/octocat",
              "id": 1,
              "node_id": "MDQ6VXNlcjE=",
              "login": "octocat",
              "organizations_url": "https://api.github.com/users/octocat/orgs",
              "received_events_url": "https://api.github.com/users/octocat/received_events",
              "repos_url": "https://api.github.com/users/octocat/repos",
              "site_admin": true,
              "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
              "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
              "type": "User",
              "url": "https://api.github.com/users/octocat",
              "starred_at": "\"2020-07-09T00:17:55Z\""
            },
            "author_association": "et tempor minim dolor",
            "created_at": "2011-04-22T13:33:48Z",
            "updated_at": "2011-04-22T13:33:48Z",
            "body": "I'm having a problem with this.",
            "assignees": [
              {
                "avatar_url": "https://github.com/images/error/octocat_happy.gif",
                "events_url": "https://api.github.com/users/octocat/events{/privacy}",
                "followers_url": "https://api.github.com/users/octocat/followers",
                "following_url": "https://api.github.com/users/octocat/following{/other_user}",
                "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
                "gravatar_id": "",
                "html_url": "https://github.com/octocat",
                "id": 1,
                "node_id": "MDQ6VXNlcjE=",
                "login": "octocat",
                "organizations_url": "https://api.github.com/users/octocat/orgs",
                "received_events_url": "https://api.github.com/users/octocat/received_events",
                "repos_url": "https://api.github.com/users/octocat/repos",
                "site_admin": true,
                "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
                "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
                "type": "User",
                "url": "https://api.github.com/users/octocat",
                "starred_at": "\"2020-07-09T00:17:55Z\""
              },
              {
                "avatar_url": "https://github.com/images/error/octocat_happy.gif",
                "events_url": "https://api.github.com/users/octocat/events{/privacy}",
                "followers_url": "https://api.github.com/users/octocat/followers",
                "following_url": "https://api.github.com/users/octocat/following{/other_user}",
                "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
                "gravatar_id": "",
                "html_url": "https://github.com/octocat",
                "id": 1,
                "node_id": "MDQ6VXNlcjE=",
                "login": "octocat",
                "organizations_url": "https://api.github.com/users/octocat/orgs",
                "received_events_url": "https://api.github.com/users/octocat/received_events",
                "repos_url": "https://api.github.com/users/octocat/repos",
                "site_admin": false,
                "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
                "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
                "type": "User",
                "url": "https://api.github.com/users/octocat",
                "starred_at": "\"2020-07-09T00:17:55Z\""
              }
            ],
            "active_lock_reason": "too heated",
            "pull_request": {
              "diff_url": "veniam nostrud ad reprehenderit",
              "html_url": "Excepteur magna minim inc",
              "patch_url": "labore consectetur exercitation fugiat",
              "url": "ex",
              "merged_at": "do dolor veniam quis"
            },
            "body_html": "non consectetur",
            "body_text": "ea quis in",
            "timeline_url": "do",
            "repository": {
              "archive_url": "http://api.github.com/repos/octocat/Hello-World/{archive_format}{/ref}",
              "assignees_url": "http://api.github.com/repos/octocat/Hello-World/assignees{/user}",
              "blobs_url": "http://api.github.com/repos/octocat/Hello-World/git/blobs{/sha}",
              "branches_url": "http://api.github.com/repos/octocat/Hello-World/branches{/branch}",
              "collaborators_url": "http://api.github.com/repos/octocat/Hello-World/collaborators{/collaborator}",
              "comments_url": "http://api.github.com/repos/octocat/Hello-World/comments{/number}",
              "commits_url": "http://api.github.com/repos/octocat/Hello-World/commits{/sha}",
              "compare_url": "http://api.github.com/repos/octocat/Hello-World/compare/{base}...{head}",
              "contents_url": "http://api.github.com/repos/octocat/Hello-World/contents/{+path}",
              "contributors_url": "http://api.github.com/repos/octocat/Hello-World/contributors",
              "deployments_url": "http://api.github.com/repos/octocat/Hello-World/deployments",
              "description": "This your first repo!",
              "downloads_url": "http://api.github.com/repos/octocat/Hello-World/downloads",
              "events_url": "http://api.github.com/repos/octocat/Hello-World/events",
              "fork": false,
              "forks_url": "http://api.github.com/repos/octocat/Hello-World/forks",
              "full_name": "octocat/Hello-World",
              "git_commits_url": "http://api.github.com/repos/octocat/Hello-World/git/commits{/sha}",
              "git_refs_url": "http://api.github.com/repos/octocat/Hello-World/git/refs{/sha}",
              "git_tags_url": "http://api.github.com/repos/octocat/Hello-World/git/tags{/sha}",
              "hooks_url": "http://api.github.com/repos/octocat/Hello-World/hooks",
              "html_url": "https://github.com/octocat/Hello-World",
              "id": 42,
              "node_id": "MDEwOlJlcG9zaXRvcnkxMjk2MjY5",
              "issue_comment_url": "http://api.github.com/repos/octocat/Hello-World/issues/comments{/number}",
              "issue_events_url": "http://api.github.com/repos/octocat/Hello-World/issues/events{/number}",
              "issues_url": "http://api.github.com/repos/octocat/Hello-World/issues{/number}",
              "keys_url": "http://api.github.com/repos/octocat/Hello-World/keys{/key_id}",
              "labels_url": "http://api.github.com/repos/octocat/Hello-World/labels{/name}",
              "languages_url": "http://api.github.com/repos/octocat/Hello-World/languages",
              "merges_url": "http://api.github.com/repos/octocat/Hello-World/merges",
              "milestones_url": "http://api.github.com/repos/octocat/Hello-World/milestones{/number}",
              "name": "Team Environment",
              "notifications_url": "http://api.github.com/repos/octocat/Hello-World/notifications{?since,all,participating}",
              "owner": {
                "avatar_url": "https://github.com/images/error/octocat_happy.gif",
                "events_url": "https://api.github.com/users/octocat/events{/privacy}",
                "followers_url": "https://api.github.com/users/octocat/followers",
                "following_url": "https://api.github.com/users/octocat/following{/other_user}",
                "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
                "gravatar_id": "",
                "html_url": "https://github.com/octocat",
                "id": 1,
                "node_id": "MDQ6VXNlcjE=",
                "login": "octocat",
                "organizations_url": "https://api.github.com/users/octocat/orgs",
                "received_events_url": "https://api.github.com/users/octocat/received_events",
                "repos_url": "https://api.github.com/users/octocat/repos",
                "site_admin": true,
                "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
                "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
                "type": "User",
                "url": "https://api.github.com/users/octocat",
                "starred_at": "\"2020-07-09T00:17:55Z\""
              },
              "private": false,
              "pulls_url": "http://api.github.com/repos/octocat/Hello-World/pulls{/number}",
              "releases_url": "http://api.github.com/repos/octocat/Hello-World/releases{/id}",
              "stargazers_url": "http://api.github.com/repos/octocat/Hello-World/stargazers",
              "statuses_url": "http://api.github.com/repos/octocat/Hello-World/statuses/{sha}",
              "subscribers_url": "http://api.github.com/repos/octocat/Hello-World/subscribers",
              "subscription_url": "http://api.github.com/repos/octocat/Hello-World/subscription",
              "tags_url": "http://api.github.com/repos/octocat/Hello-World/tags",
              "teams_url": "http://api.github.com/repos/octocat/Hello-World/teams",
              "trees_url": "http://api.github.com/repos/octocat/Hello-World/git/trees{/sha}",
              "url": "https://api.github.com/repos/octocat/Hello-World",
              "clone_url": "https://github.com/octocat/Hello-World.git",
              "default_branch": "master",
              "forks": -2768827,
              "forks_count": 9,
              "git_url": "git:github.com/octocat/Hello-World.git",
              "has_downloads": true,
              "has_issues": true,
              "has_projects": true,
              "has_wiki": true,
              "has_pages": false,
              "homepage": "https://github.com",
              "language": "irure adipisicing ullamco consectetur",
              "archived": false,
              "disabled": true,
              "mirror_url": "git:git.example.com/octocat/Hello-World",
              "open_issues": -70107099,
              "open_issues_count": 0,
              "license": {
                "value": "<Error: Too many levels of nesting to fake this schema>"
              },
              "pushed_at": "2011-01-26T19:06:43Z",
              "size": 108,
              "ssh_url": "git@github.com:octocat/Hello-World.git",
              "stargazers_count": 80,
              "svn_url": "https://svn.github.com/octocat/Hello-World",
              "watchers": 89851252,
              "watchers_count": 80,
              "created_at": "2011-01-26T19:01:12Z",
              "updated_at": "2011-01-26T19:14:43Z",
              "permissions": {
                "admin": false,
                "pull": false,
                "push": true,
                "triage": false,
                "maintain": false
              },
              "is_template": true,
              "topics": [
                "oc",
                "volupt"
              ],
              "visibility": "public",
              "allow_rebase_merge": true,
              "template_repository": {
                "id": -23559911,
                "node_id": "amet",
                "name": "ut proident ex quis",
                "full_name": "labore Duis",
                "owner": {
                  "login": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "id": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "node_id": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "avatar_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "gravatar_id": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "html_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "followers_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "following_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "gists_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "starred_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "subscriptions_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "organizations_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "repos_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "events_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "received_events_url": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "type": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "site_admin": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  }
                },
                "private": false,
                "html_url": "qui",
                "description": "sit est Duis enim consequat",
                "fork": true,
                "url": "non consectetur id",
                "archive_url": "",
                "assignees_url": "nisi amet dolor eiusmod dolore",
                "blobs_url": "cupidatat ex aliqua laboris",
                "branches_url": "fugiat incididunt cillum commodo",
                "collaborators_url": "eiusmod tempor voluptate aliqua",
                "comments_url": "sed veniam id",
                "commits_url": "sed amet",
                "compare_url": "ut aliqua ullamco mini",
                "contents_url": "in v",
                "contributors_url": "sit",
                "deployments_url": "consequat cillum tempor",
                "downloads_url": "occaecat reprehenderit",
                "events_url": "est",
                "forks_url": "sit",
                "git_commits_url": "officia in et non",
                "git_refs_url": "esse",
                "git_tags_url": "a",
                "git_url": "ut ",
                "issue_comment_url": "elit Duis Ut dolore exercitation",
                "issue_events_url": "sit voluptate",
                "issues_url": "non anim aliqua mollit",
                "keys_url": "in nostrud nulla Duis laborum",
                "labels_url": "sed",
                "languages_url": "dolor Duis Excepteur",
                "merges_url": "sunt irure",
                "milestones_url": "aute",
                "notifications_url": "consequat",
                "pulls_url": "quis elit ad Ut",
                "releases_url": "pariatur",
                "ssh_url": "Lorem ad velit esse",
                "stargazers_url": "amet ea",
                "statuses_url": "mollit",
                "subscribers_url": "tempor pariatur",
                "subscription_url": "quis a",
                "tags_url": "veniam in",
                "teams_url": "sint officia do laboris",
                "trees_url": "labore nisi cillum Ut",
                "clone_url": "in eiusmod nostrud quis in",
                "mirror_url": "deserunt culpa sunt",
                "hooks_url": "proident Excepteur ut exercitation",
                "svn_url": "non et consequat elit enim",
                "homepage": "aute voluptate",
                "language": "est qui",
                "forks_count": -44453726,
                "stargazers_count": -23546435,
                "watchers_count": 85435987,
                "size": 87085671,
                "default_branch": "ullamco",
                "open_issues_count": 8382001,
                "is_template": false,
                "topics": [
                  {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  }
                ],
                "has_issues": true,
                "has_projects": false,
                "has_wiki": true,
                "has_pages": true,
                "has_downloads": false,
                "archived": false,
                "disabled": false,
                "visibility": "est Lorem",
                "pushed_at": "id labore",
                "created_at": "aliqua",
                "updated_at": "sint proident",
                "permissions": {
                  "admin": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "push": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  },
                  "pull": {
                    "value": "<Error: Too many levels of nesting to fake this schema>"
                  }
                },
                "allow_rebase_merge": true,
                "template_repository": "non nisi laborum dolor enim",
                "temp_clone_token": "aliqua enim dolore labore",
                "allow_squash_merge": false,
                "delete_branch_on_merge": false,
                "allow_merge_commit": true,
                "subscribers_count": 71791566,
                "network_count": 73783930
              },
              "temp_clone_token": "officia pariatur nisi incididunt",
              "allow_squash_merge": true,
              "delete_branch_on_merge": false,
              "allow_merge_commit": true,
              "subscribers_count": 96412870,
              "network_count": 50789411,
              "master_branch": "occaeca",
              "starred_at": "\"2020-07-09T00:17:42Z\""
            },
            "performed_via_github_app": {
              "id": 37,
              "node_id": "MDExOkludGVncmF0aW9uMQ==",
              "owner": {
                "value": "<Error: Too many levels of nesting to fake this schema>"
              },
              "name": "Probot Owners",
              "description": "",
              "external_url": "https://example.com",
              "html_url": "https://github.com/apps/super-ci",
              "created_at": "2017-07-08T16:18:44-04:00",
              "updated_at": "2017-07-08T16:18:44-04:00",
              "permissions": {
                "issues": "read",
                "deployments": "write"
              },
              "events": [
                "label",
                "deployment"
              ],
              "slug": "probot-owners",
              "installations_count": 5,
              "client_id": "\"Iv1.25b5d1e65ffc4022\"",
              "client_secret": "\"1d4b2097ac622ba702d19de498f005747a8b21d3\"",
              "webhook_secret": "\"6fba8f2fc8a7e8f2cca5577eddd82ca7586b3b6b\"",
              "pem": "\"{{vault:rsa-private-key}}\\n\""
            }
          },
          "comment": {
            "id": 42,
            "node_id": "ad et",
            "html_url": "in Lorem",
            "issue_url": "est amet Lorem",
            "author_association": "sint aliquip dolor sunt elit",
            "user": {
              "avatar_url": "https://github.com/images/error/octocat_happy.gif",
              "events_url": "https://api.github.com/users/octocat/events{/privacy}",
              "followers_url": "https://api.github.com/users/octocat/followers",
              "following_url": "https://api.github.com/users/octocat/following{/other_user}",
              "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
              "gravatar_id": "",
              "html_url": "https://github.com/octocat",
              "id": 1,
              "node_id": "MDQ6VXNlcjE=",
              "login": "octocat",
              "organizations_url": "https://api.github.com/users/octocat/orgs",
              "received_events_url": "https://api.github.com/users/octocat/received_events",
              "repos_url": "https://api.github.com/users/octocat/repos",
              "site_admin": true,
              "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
              "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
              "type": "User",
              "url": "https://api.github.com/users/octocat",
              "starred_at": "\"2020-07-09T00:17:55Z\""
            },
            "url": "https://api.github.com/repositories/42/issues/comments/1",
            "created_at": "2011-04-14T16:00:49Z",
            "updated_at": "2011-04-14T16:00:49Z",
            "body": "What version of Safari were you using when you observed this bug?",
            "body_text": "quis dolore occaecat consequat",
            "body_html": "Duis exercitation",
            "performed_via_github_app": {
              "id": 37,
              "node_id": "MDExOkludGVncmF0aW9uMQ==",
              "owner": {
                "value": "<Error: Too many levels of nesting to fake this schema>"
              },
              "name": "Probot Owners",
              "description": "",
              "external_url": "https://example.com",
              "html_url": "https://github.com/apps/super-ci",
              "created_at": "2017-07-08T16:18:44-04:00",
              "updated_at": "2017-07-08T16:18:44-04:00",
              "permissions": {
                "issues": "read",
                "deployments": "write"
              },
              "events": [
                "label",
                "deployment"
              ],
              "slug": "probot-owners",
              "installations_count": 5,
              "client_id": "\"Iv1.25b5d1e65ffc4022\"",
              "client_secret": "\"1d4b2097ac622ba702d19de498f005747a8b21d3\"",
              "webhook_secret": "\"6fba8f2fc8a7e8f2cca5577eddd82ca7586b3b6b\"",
              "pem": "\"{{vault:rsa-private-key}}\\n\""
            },
            "reactions": {
              "url": "in amet dolor",
              "total_count": -99329732,
              "+1": -93375299,
              "-1": -63132563,
              "laugh": 84247895,
              "confused": -30251332,
              "heart": -25918793,
              "hooray": 65956382,
              "eyes": 66357128,
              "rocket": 23108649
            }
          },
          "pages": [
            {
              "page_name": "repreh",
              "title": "sed in",
              "summary": "veniam do ut",
              "action": "labore adipisicing irure in",
              "sha": "aute velit",
              "html_url": "officia nulla laboris sit"
            },
            {
              "page_name": "cillum consectetur exercitation ad Lorem",
              "title": "ut laboris anim",
              "summary": "officia irure vol",
              "action": "ea velit nisi",
              "sha": "dolor",
              "html_url": "Excepteur sunt Lorem "
            }
          ]
        },
        "public": false,
        "created_at": "labore id tempor",
        "org": {
          "id": 65537797,
          "login": "ipsum",
          "gravatar_id": "proident culpa",
          "url": "voluptate labore",
          "avatar_url": "aute exercitation in ut nostrud",
          "display_login": "eu velit nisi"
        }
      }
    ]
    ```

    


=== "GET Get an organization installation for the authenticated app"

    Enables an authenticated GitHub App to find the organization's installation information.

    You must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/installation
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/installation', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/installation', {
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
        "login": "github",
        "id": 1,
        "node_id": "MDEyOk9yZ2FuaXphdGlvbjE=",
        "avatar_url": "https://github.com/images/error/hubot_happy.gif",
        "gravatar_id": "",
        "url": "https://api.github.com/orgs/github",
        "html_url": "https://github.com/github",
        "followers_url": "https://api.github.com/users/github/followers",
        "following_url": "https://api.github.com/users/github/following{/other_user}",
        "gists_url": "https://api.github.com/users/github/gists{/gist_id}",
        "starred_url": "https://api.github.com/users/github/starred{/owner}{/repo}",
        "subscriptions_url": "https://api.github.com/users/github/subscriptions",
        "organizations_url": "https://api.github.com/users/github/orgs",
        "repos_url": "https://api.github.com/orgs/github/repos",
        "events_url": "https://api.github.com/orgs/github/events",
        "received_events_url": "https://api.github.com/users/github/received_events",
        "type": "Organization",
        "site_admin": false
      },
      "repository_selection": "all",
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
      "created_at": "2018-02-09T20:51:14Z",
      "updated_at": "2018-02-09T20:51:14Z",
      "single_file_name": null,
      "app_slug": "github-actions"
    }
    ```

    


=== "GET List app installations for an organization"

    Lists all GitHub Apps in an organization. The installation count includes all GitHub Apps installed on repositories in the organization. You must be an organization owner with `admin:read` scope to use this endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/installations?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/installations?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/installations?per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "total_count": 1,
      "installations": [
        {
          "id": 25381,
          "account": {
            "login": "octo-org",
            "id": 6811672,
            "node_id": "MDEyOk9yZ2FuaXphdGlvbjY4MTE2NzI=",
            "avatar_url": "https://avatars3.githubusercontent.com/u/6811672?v=4",
            "gravatar_id": "",
            "url": "https://api.github.com/users/octo-org",
            "html_url": "https://github.com/octo-org",
            "followers_url": "https://api.github.com/users/octo-org/followers",
            "following_url": "https://api.github.com/users/octo-org/following{/other_user}",
            "gists_url": "https://api.github.com/users/octo-org/gists{/gist_id}",
            "starred_url": "https://api.github.com/users/octo-org/starred{/owner}{/repo}",
            "subscriptions_url": "https://api.github.com/users/octo-org/subscriptions",
            "organizations_url": "https://api.github.com/users/octo-org/orgs",
            "repos_url": "https://api.github.com/users/octo-org/repos",
            "events_url": "https://api.github.com/users/octo-org/events{/privacy}",
            "received_events_url": "https://api.github.com/users/octo-org/received_events",
            "type": "Organization",
            "site_admin": false
          },
          "repository_selection": "selected",
          "access_tokens_url": "https://api.github.com/app/installations/25381/access_tokens",
          "repositories_url": "https://api.github.com/installation/repositories",
          "html_url": "https://github.com/organizations/octo-org/settings/installations/25381",
          "app_id": 2218,
          "target_id": 6811672,
          "target_type": "Organization",
          "permissions": {
            "deployments": "write",
            "metadata": "read",
            "pull_requests": "read",
            "statuses": "read"
          },
          "events": [
            "deployment",
            "deployment_status"
          ],
          "created_at": "2017-05-16T08:47:09.000-07:00",
          "updated_at": "2017-06-06T11:23:23.000-07:00",
          "single_file_name": null,
          "app_slug": "github-actions"
        }
      ]
    }
    ```

    


=== "GET List organization issues assigned to the authenticated user"

    List issues in an organization assigned to the authenticated user.

    **Note**: GitHub's REST API v3 considers every pull request an issue, but not every issue is a pull request. For this
    reason, "Issues" endpoints may return both issues and pull requests in the response. You can identify pull requests by
    the `pull_request` key. Be aware that the `id` of a pull request returned from "Issues" endpoints will be an _issue id_. To find out the pull
    request id, use the "[List pull requests](https://developer.github.com/v3/pulls/#list-pull-requests)" endpoint.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `filter` | `string` | Yes | Indicates which sorts of issues to return. Can be one of:  <br>\* `assigned`: Issues assigned to you  <br>\* `created`: Issues created by you  <br>\* `mentioned`: Issues mentioning you  <br>\* `subscribed`: Issues you're subscribed to updates for  <br>\* `all`: All issues the authenticated user can see, regardless of participation or creation | `assigned` |
    | `state` | `string` | Yes | Indicates the state of the issues to return. Can be either `open`, `closed`, or `all`. | `open` |
    | `labels` | `string` | Yes | A list of comma separated label names. Example: `bug,ui,@high` | `<string>` |
    | `sort` | `string` | Yes | What to sort results by. Can be either `created`, `updated`, `comments`. | `created` |
    | `direction` | `string` | Yes | One of `asc` (ascending) or `desc` (descending). | `desc` |
    | `since` | `string` | Yes | Only show notifications updated after the given time. This is a timestamp in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format: `YYYY-MM-DDTHH:MM:SSZ`. | `<string>` |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/issues?filter=assigned&state=open&labels=<string>&sort=created&direction=desc&since=<string>&per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/issues?filter=assigned&state=open&labels=<string>&sort=created&direction=desc&since=<string>&per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/issues?filter=assigned&state=open&labels=<string>&sort=created&direction=desc&since=<string>&per_page=30&page=1', {
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
        "node_id": "MDU6SXNzdWUx",
        "url": "https://api.github.com/repos/octocat/Hello-World/issues/1347",
        "repository_url": "https://api.github.com/repos/octocat/Hello-World",
        "labels_url": "https://api.github.com/repos/octocat/Hello-World/issues/1347/labels{/name}",
        "comments_url": "https://api.github.com/repos/octocat/Hello-World/issues/1347/comments",
        "events_url": "https://api.github.com/repos/octocat/Hello-World/issues/1347/events",
        "html_url": "https://github.com/octocat/Hello-World/issues/1347",
        "number": 1347,
        "state": "open",
        "title": "Found a bug",
        "body": "I'm having a problem with this.",
        "user": {
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
        "labels": [
          {
            "id": 208045946,
            "node_id": "MDU6TGFiZWwyMDgwNDU5NDY=",
            "url": "https://api.github.com/repos/octocat/Hello-World/labels/bug",
            "name": "bug",
            "description": "Something isn't working",
            "color": "f29513",
            "default": true
          }
        ],
        "assignee": {
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
        "assignees": [
          {
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
          }
        ],
        "milestone": {
          "url": "https://api.github.com/repos/octocat/Hello-World/milestones/1",
          "html_url": "https://github.com/octocat/Hello-World/milestones/v1.0",
          "labels_url": "https://api.github.com/repos/octocat/Hello-World/milestones/1/labels",
          "id": 1002604,
          "node_id": "MDk6TWlsZXN0b25lMTAwMjYwNA==",
          "number": 1,
          "state": "open",
          "title": "v1.0",
          "description": "Tracking milestone for version 1.0",
          "creator": {
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
          "open_issues": 4,
          "closed_issues": 8,
          "created_at": "2011-04-10T20:09:31Z",
          "updated_at": "2014-03-03T18:58:10Z",
          "closed_at": "2013-02-12T13:22:01Z",
          "due_on": "2012-10-09T23:39:01Z"
        },
        "locked": true,
        "active_lock_reason": "too heated",
        "comments": 0,
        "pull_request": {
          "url": "https://api.github.com/repos/octocat/Hello-World/pulls/1347",
          "html_url": "https://github.com/octocat/Hello-World/pull/1347",
          "diff_url": "https://github.com/octocat/Hello-World/pull/1347.diff",
          "patch_url": "https://github.com/octocat/Hello-World/pull/1347.patch"
        },
        "closed_at": null,
        "created_at": "2011-04-22T13:33:48Z",
        "updated_at": "2011-04-22T13:33:48Z",
        "repository": {
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
        },
        "author_association": "collaborator"
      }
    ]
    ```

    


=== "GET List IdP groups for an organization"

    Team synchronization is available for organizations using GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products) in the GitHub Help documentation.

    List IdP groups available in an organization. You can limit your page results using the `per_page` parameter. GitHub generates a url-encoded `page` token using a cursor value for where the next page begins. For more information on cursor pagination, see "[Offset and Cursor Pagination explained](https://dev.to/jackmarchant/offset-and-cursor-pagination-explained-b89)."

    The `per_page` parameter provides pagination for a list of IdP groups the authenticated user can access in an organization. For example, if the user `octocat` wants to see two groups per page in `octo-org` via cURL, it would look like this:

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `per_page` | `string` | Yes | Results per page (max 100) | `30` |
    | `page` | `string` | Yes | Page number of the results to fetch. | `1` |
    | `:org` | `string` | Yes | (Required)  | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/orgs/:org/team-sync/groups?per_page=30&page=1
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/orgs/:org/team-sync/groups?per_page=30&page=1', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /orgs/{org}/team-sync/groups?per_page=30&page=1', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "groups": [
        {
          "group_id": "123",
          "group_name": "Octocat admins",
          "group_description": "The people who configure your octoworld."
        },
        {
          "group_id": "456",
          "group_name": "Octocat docs members",
          "group_description": "The people who make your octoworld come to life."
        }
      ]
    }
    ```

    

