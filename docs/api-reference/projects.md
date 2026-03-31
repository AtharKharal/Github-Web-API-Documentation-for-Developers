# projects API


## Get a project card

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/projects/columns/cards/{card_id}</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{card_id}` | `string` | Yes | (Required) card_id parameter | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/columns/cards/{card_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/projects/columns/cards/{card_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /projects/columns/cards/{card_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "url": "https://api.github.com/projects/columns/cards/1478",
  "id": 1478,
  "node_id": "MDExOlByb2plY3RDYXJkMTQ3OA==",
  "note": "Add payload for delete Project column",
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
  "created_at": "2016-09-05T14:21:06Z",
  "updated_at": "2016-09-05T14:20:22Z",
  "archived": false,
  "column_url": "https://api.github.com/projects/columns/367",
  "content_url": "https://api.github.com/repos/api-playground/projects-test/issues/3",
  "project_url": "https://api.github.com/projects/120"
}
```



---


## Update an existing project card

<div class="api-method-banner">
  <span class="api-method method-patch">PATCH</span> <span class="api-path">/projects/columns/cards/{card_id}</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{card_id}` | `string` | Yes | (Required) card_id parameter | `<integer>` |




### Request Body

```json
{
  "note": "<string>",
  "archived": "<boolean>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PATCH \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/columns/cards/{card_id} \
      -d '{
      "note": "<string>",
      "archived": "<boolean>"
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
      "note": "<string>",
      "archived": "<boolean>"
    }

    response = requests.patch('https://api.github.com/projects/columns/cards/{card_id}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PATCH /projects/columns/cards/{card_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "note": "<string>",
        "archived": "<boolean>"
      }
    });
    ```


### Response Example

```json
{
  "url": "https://api.github.com/projects/columns/cards/1478",
  "id": 1478,
  "node_id": "MDExOlByb2plY3RDYXJkMTQ3OA==",
  "note": "Add payload for delete Project column",
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
  "created_at": "2016-09-05T14:21:06Z",
  "updated_at": "2016-09-05T14:20:22Z",
  "archived": false,
  "column_url": "https://api.github.com/projects/columns/367",
  "content_url": "https://api.github.com/repos/api-playground/projects-test/issues/3",
  "project_url": "https://api.github.com/projects/120"
}
```



---


## Delete a project card

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/projects/columns/cards/{card_id}</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{card_id}` | `string` | Yes | (Required) card_id parameter | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/columns/cards/{card_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/projects/columns/cards/{card_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /projects/columns/cards/{card_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{}
```



---


## Move a project card

<div class="api-method-banner">
  <span class="api-method method-post">POST</span> <span class="api-path">/projects/columns/cards/{card_id}/moves</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{card_id}` | `string` | Yes | (Required) card_id parameter | `<integer>` |




### Request Body

```json
{
  "position": "<string>",
  "column_id": "<integer>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/columns/cards/{card_id}/moves \
      -d '{
      "position": "<string>",
      "column_id": "<integer>"
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
      "position": "<string>",
      "column_id": "<integer>"
    }

    response = requests.post('https://api.github.com/projects/columns/cards/{card_id}/moves', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('POST /projects/columns/cards/{card_id}/moves', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "position": "<string>",
        "column_id": "<integer>"
      }
    });
    ```


### Response Example

```json
{}
```



---


## List project cards

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/projects/columns/{column_id}/cards</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `archived_state` | `string` | Yes | Filters the project cards that are returned by the card's state. Can be one of `all`,`archived`, or `not_archived`. | `not_archived` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{column_id}` | `string` | Yes | (Required) column_id parameter | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/columns/{column_id}/cards?archived_state=not_archived&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/projects/columns/{column_id}/cards?archived_state=not_archived&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /projects/columns/{column_id}/cards?archived_state=not_archived&per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
[
  {
    "url": "https://api.github.com/projects/columns/cards/1478",
    "id": 1478,
    "node_id": "MDExOlByb2plY3RDYXJkMTQ3OA==",
    "note": "Add payload for delete Project column",
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
    "created_at": "2016-09-05T14:21:06Z",
    "updated_at": "2016-09-05T14:20:22Z",
    "archived": false,
    "column_url": "https://api.github.com/projects/columns/367",
    "content_url": "https://api.github.com/repos/api-playground/projects-test/issues/3",
    "project_url": "https://api.github.com/projects/120"
  }
]
```



---


## Create a project card

<div class="api-method-banner">
  <span class="api-method method-post">POST</span> <span class="api-path">/projects/columns/{column_id}/cards</span>
</div>

**Note**: GitHub's REST API v3 considers every pull request an issue, but not every issue is a pull request. For this reason, "Issues" endpoints may return both issues and pull requests in the response. You can identify pull requests by the `pull_request` key.

Be aware that the `id` of a pull request returned from "Issues" endpoints will be an _issue id_. To find out the pull request id, use the "[List pull requests](https://developer.github.com/v3/pulls/#list-pull-requests)" endpoint.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{column_id}` | `string` | Yes | (Required) column_id parameter | `<integer>` |




### Request Body

```json
{
  "note": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/columns/{column_id}/cards \
      -d '{
      "note": "<string>"
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
      "note": "<string>"
    }

    response = requests.post('https://api.github.com/projects/columns/{column_id}/cards', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('POST /projects/columns/{column_id}/cards', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "note": "<string>"
      }
    });
    ```


### Response Example

```json
{
  "url": "https://api.github.com/projects/columns/cards/1478",
  "id": 1478,
  "node_id": "MDExOlByb2plY3RDYXJkMTQ3OA==",
  "note": "Add payload for delete Project column",
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
  "created_at": "2016-09-05T14:21:06Z",
  "updated_at": "2016-09-05T14:20:22Z",
  "archived": false,
  "column_url": "https://api.github.com/projects/columns/367",
  "content_url": "https://api.github.com/repos/api-playground/projects-test/issues/3",
  "project_url": "https://api.github.com/projects/120"
}
```



---


## Get a project column

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/projects/columns/{column_id}</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{column_id}` | `string` | Yes | (Required) column_id parameter | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/columns/{column_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/projects/columns/{column_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /projects/columns/{column_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "url": "https://api.github.com/projects/columns/367",
  "project_url": "https://api.github.com/projects/120",
  "cards_url": "https://api.github.com/projects/columns/367/cards",
  "id": 367,
  "node_id": "MDEzOlByb2plY3RDb2x1bW4zNjc=",
  "name": "To Do",
  "created_at": "2016-09-05T14:18:44Z",
  "updated_at": "2016-09-05T14:22:28Z"
}
```



---


## Update an existing project column

<div class="api-method-banner">
  <span class="api-method method-patch">PATCH</span> <span class="api-path">/projects/columns/{column_id}</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{column_id}` | `string` | Yes | (Required) column_id parameter | `<integer>` |




### Request Body

```json
{
  "name": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PATCH \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/columns/{column_id} \
      -d '{
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
      "name": "<string>"
    }

    response = requests.patch('https://api.github.com/projects/columns/{column_id}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PATCH /projects/columns/{column_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "name": "<string>"
      }
    });
    ```


### Response Example

```json
{
  "url": "https://api.github.com/projects/columns/367",
  "project_url": "https://api.github.com/projects/120",
  "cards_url": "https://api.github.com/projects/columns/367/cards",
  "id": 367,
  "node_id": "MDEzOlByb2plY3RDb2x1bW4zNjc=",
  "name": "To Do",
  "created_at": "2016-09-05T14:18:44Z",
  "updated_at": "2016-09-05T14:22:28Z"
}
```



---


## Delete a project column

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/projects/columns/{column_id}</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{column_id}` | `string` | Yes | (Required) column_id parameter | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/columns/{column_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/projects/columns/{column_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /projects/columns/{column_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{}
```



---


## Move a project column

<div class="api-method-banner">
  <span class="api-method method-post">POST</span> <span class="api-path">/projects/columns/{column_id}/moves</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{column_id}` | `string` | Yes | (Required) column_id parameter | `<integer>` |




### Request Body

```json
{
  "position": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/columns/{column_id}/moves \
      -d '{
      "position": "<string>"
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
      "position": "<string>"
    }

    response = requests.post('https://api.github.com/projects/columns/{column_id}/moves', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('POST /projects/columns/{column_id}/moves', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "position": "<string>"
      }
    });
    ```


### Response Example

```json
{}
```



---


## Add project collaborator

<div class="api-method-banner">
  <span class="api-method method-put">PUT</span> <span class="api-path">/projects/{project_id}/collaborators/{username}</span>
</div>

Adds a collaborator to an organization project and sets their permission level. You must be an organization owner or a project `admin` to add a collaborator.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{project_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |




### Request Body

```json
{
  "permission": "write"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PUT \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/{project_id}/collaborators/{username} \
      -d '{
      "permission": "write"
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
      "permission": "write"
    }

    response = requests.put('https://api.github.com/projects/{project_id}/collaborators/{username}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PUT /projects/{project_id}/collaborators/{username}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "permission": "write"
      }
    });
    ```


### Response Example

```json
{}
```



---


## Remove user as a collaborator

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/projects/{project_id}/collaborators/{username}</span>
</div>

Removes a collaborator from an organization project. You must be an organization owner or a project `admin` to remove a collaborator.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{project_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/{project_id}/collaborators/{username}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/projects/{project_id}/collaborators/{username}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /projects/{project_id}/collaborators/{username}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{}
```



---


## Get project permission for a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/projects/{project_id}/collaborators/{username}/permission</span>
</div>

Returns the collaborator's permission level for an organization project. Possible values for the `permission` key: `admin`, `write`, `read`, `none`. You must be an organization owner or a project `admin` to review a user's permission level.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{project_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/{project_id}/collaborators/{username}/permission
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/projects/{project_id}/collaborators/{username}/permission', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /projects/{project_id}/collaborators/{username}/permission', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "permission": "admin",
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



---


## List project collaborators

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/projects/{project_id}/collaborators</span>
</div>

Lists the collaborators for an organization project. For a project, the list of collaborators includes outside collaborators, organization members that are direct collaborators, organization members with access through team memberships, organization members with access through default organization permissions, and organization owners. You must be an organization owner or a project `admin` to list collaborators.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `affiliation` | `string` | Yes | Filters the collaborators by their affiliation. Can be one of:  <br>\* `outside`: Outside collaborators of a project that are not a member of the project's organization.  <br>\* `direct`: Collaborators with permissions to a project, regardless of organization membership status.  <br>\* `all`: All collaborators the authenticated user can see. | `all` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{project_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/{project_id}/collaborators?affiliation=all&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/projects/{project_id}/collaborators?affiliation=all&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /projects/{project_id}/collaborators?affiliation=all&per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## List project columns

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/projects/{project_id}/columns</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{project_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/{project_id}/columns?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/projects/{project_id}/columns?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /projects/{project_id}/columns?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
[
  {
    "url": "https://api.github.com/projects/columns/367",
    "project_url": "https://api.github.com/projects/120",
    "cards_url": "https://api.github.com/projects/columns/367/cards",
    "id": 367,
    "node_id": "MDEzOlByb2plY3RDb2x1bW4zNjc=",
    "name": "To Do",
    "created_at": "2016-09-05T14:18:44Z",
    "updated_at": "2016-09-05T14:22:28Z"
  }
]
```



---


## Create a project column

<div class="api-method-banner">
  <span class="api-method method-post">POST</span> <span class="api-path">/projects/{project_id}/columns</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{project_id}` | `string` | Yes | (Required)  | `<integer>` |




### Request Body

```json
{
  "name": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/{project_id}/columns \
      -d '{
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
      "name": "<string>"
    }

    response = requests.post('https://api.github.com/projects/{project_id}/columns', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('POST /projects/{project_id}/columns', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "name": "<string>"
      }
    });
    ```


### Response Example

```json
{
  "url": "https://api.github.com/projects/columns/367",
  "project_url": "https://api.github.com/projects/120",
  "cards_url": "https://api.github.com/projects/columns/367/cards",
  "id": 367,
  "node_id": "MDEzOlByb2plY3RDb2x1bW4zNjc=",
  "name": "To Do",
  "created_at": "2016-09-05T14:18:44Z",
  "updated_at": "2016-09-05T14:22:28Z"
}
```



---


## Get a project

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/projects/{project_id}</span>
</div>

Gets a project by its `id`. Returns a `404 Not Found` status if projects are disabled. If you do not have sufficient privileges to perform this action, a `401 Unauthorized` or `410 Gone` status is returned.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{project_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/{project_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/projects/{project_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /projects/{project_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "owner_url": "https://api.github.com/repos/api-playground/projects-test",
  "url": "https://api.github.com/projects/1002604",
  "html_url": "https://github.com/api-playground/projects-test/projects/1",
  "columns_url": "https://api.github.com/projects/1002604/columns",
  "id": 1002604,
  "node_id": "MDc6UHJvamVjdDEwMDI2MDQ=",
  "name": "Projects Documentation",
  "body": "Developer documentation project for the developer site.",
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
  "created_at": "2011-04-10T20:09:31Z",
  "updated_at": "2014-03-03T18:58:10Z"
}
```



---


## Update a project

<div class="api-method-banner">
  <span class="api-method method-patch">PATCH</span> <span class="api-path">/projects/{project_id}</span>
</div>

Updates a project board's information. Returns a `404 Not Found` status if projects are disabled. If you do not have sufficient privileges to perform this action, a `401 Unauthorized` or `410 Gone` status is returned.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{project_id}` | `string` | Yes | (Required)  | `<integer>` |




### Request Body

```json
{
  "name": "<string>",
  "body": "<string>",
  "state": "<string>",
  "organization_permission": "<string>",
  "private": "<boolean>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PATCH \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/{project_id} \
      -d '{
      "name": "<string>",
      "body": "<string>",
      "state": "<string>",
      "organization_permission": "<string>",
      "private": "<boolean>"
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
      "body": "<string>",
      "state": "<string>",
      "organization_permission": "<string>",
      "private": "<boolean>"
    }

    response = requests.patch('https://api.github.com/projects/{project_id}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PATCH /projects/{project_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "name": "<string>",
        "body": "<string>",
        "state": "<string>",
        "organization_permission": "<string>",
        "private": "<boolean>"
      }
    });
    ```


### Response Example

```json
{
  "owner_url": "https://api.github.com/repos/api-playground/projects-test",
  "url": "https://api.github.com/projects/1002604",
  "html_url": "https://github.com/api-playground/projects-test/projects/1",
  "columns_url": "https://api.github.com/projects/1002604/columns",
  "id": 1002604,
  "node_id": "MDc6UHJvamVjdDEwMDI2MDQ=",
  "name": "Projects Documentation",
  "body": "Developer documentation project for the developer site.",
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
  "created_at": "2011-04-10T20:09:31Z",
  "updated_at": "2014-03-03T18:58:10Z"
}
```



---


## Delete a project

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/projects/{project_id}</span>
</div>

Deletes a project board. Returns a `404 Not Found` status if projects are disabled.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{project_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/projects/{project_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/projects/{project_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /projects/{project_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{}
```



---

