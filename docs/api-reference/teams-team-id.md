# teams/{team id} API


## List reactions for a team discussion comment (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}/reactions</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`List reactions for a team discussion comment`](https://developer.github.com/v3/reactions/#list-reactions-for-a-team-discussion-comment) endpoint.

List the reactions to a [team discussion comment](https://developer.github.com/v3/teams/discussion_comments/). OAuth access tokens require the `read:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `content` | `string` | Yes | Returns a single [reaction type](https://developer.github.com/v3/reactions/#reaction-types). Omit this parameter to list all reactions to a team discussion comment. | `<string>` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{discussion_number}` | `string` | Yes | (Required)  | `<integer>` |
| `{comment_number}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}/reactions?content=<string>&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}/reactions?content=<string>&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}/reactions?content=<string>&per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Create reaction for a team discussion comment (Legacy)

<div class="api-method-banner">
  <span class="api-method method-post">POST</span> <span class="api-path">/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}/reactions</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`Create reaction for a team discussion comment`](https://developer.github.com/v3/reactions/#create-reaction-for-a-team-discussion-comment) endpoint.

Create a reaction to a [team discussion comment](https://developer.github.com/v3/teams/discussion_comments/). OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/). A response with a `Status: 200 OK` means that you already added the reaction type to this team discussion comment.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{discussion_number}` | `string` | Yes | (Required)  | `<integer>` |
| `{comment_number}` | `string` | Yes | (Required)  | `<integer>` |




### Request Body

```json
{
  "content": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}/reactions \
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

    response = requests.post('https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}/reactions', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('POST /teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}/reactions', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "content": "<string>"
      }
    });
    ```


### Response Example

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



---


## Get a discussion comment (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Get a discussion comment](https://developer.github.com/v3/teams/discussion_comments/#get-a-discussion-comment) endpoint.

Get a specific comment on a team discussion. OAuth access tokens require the `read:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{discussion_number}` | `string` | Yes | (Required)  | `<integer>` |
| `{comment_number}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Update a discussion comment (Legacy)

<div class="api-method-banner">
  <span class="api-method method-patch">PATCH</span> <span class="api-path">/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Update a discussion comment](https://developer.github.com/v3/teams/discussion_comments/#update-a-discussion-comment) endpoint.

Edits the body text of a discussion comment. OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{discussion_number}` | `string` | Yes | (Required)  | `<integer>` |
| `{comment_number}` | `string` | Yes | (Required)  | `<integer>` |




### Request Body

```json
{
  "body": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PATCH \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number} \
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

    response = requests.patch('https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PATCH /teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "body": "<string>"
      }
    });
    ```


### Response Example

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



---


## Delete a discussion comment (Legacy)

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Delete a discussion comment](https://developer.github.com/v3/teams/discussion_comments/#delete-a-discussion-comment) endpoint.

Deletes a comment on a team discussion. OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{discussion_number}` | `string` | Yes | (Required)  | `<integer>` |
| `{comment_number}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /teams/{team_id}/discussions/{discussion_number}/comments/{comment_number}', {
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


## List discussion comments (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/discussions/{discussion_number}/comments</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [List discussion comments](https://developer.github.com/v3/teams/discussion_comments/#list-discussion-comments) endpoint.

List all comments on a team discussion. OAuth access tokens require the `read:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `direction` | `string` | Yes | One of `asc` (ascending) or `desc` (descending). | `desc` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{discussion_number}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments?direction=desc&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments?direction=desc&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/discussions/{discussion_number}/comments?direction=desc&per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Create a discussion comment (Legacy)

<div class="api-method-banner">
  <span class="api-method method-post">POST</span> <span class="api-path">/teams/{team_id}/discussions/{discussion_number}/comments</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Create a discussion comment](https://developer.github.com/v3/teams/discussion_comments/#create-a-discussion-comment) endpoint.

Creates a new comment on a team discussion. OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

This endpoint triggers [notifications](https://help.github.com/articles/about-notifications/). Creating content too quickly using this endpoint may result in abuse rate limiting. See "[Abuse rate limits](https://developer.github.com/v3/#abuse-rate-limits)" and "[Dealing with abuse rate limits](https://developer.github.com/v3/guides/best-practices-for-integrators/#dealing-with-abuse-rate-limits)" for details.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{discussion_number}` | `string` | Yes | (Required)  | `<integer>` |




### Request Body

```json
{
  "body": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments \
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

    response = requests.post('https://api.github.com/teams/{team_id}/discussions/{discussion_number}/comments', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('POST /teams/{team_id}/discussions/{discussion_number}/comments', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "body": "<string>"
      }
    });
    ```


### Response Example

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



---


## List reactions for a team discussion (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/discussions/{discussion_number}/reactions</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`List reactions for a team discussion`](https://developer.github.com/v3/reactions/#list-reactions-for-a-team-discussion) endpoint.

List the reactions to a [team discussion](https://developer.github.com/v3/teams/discussions/). OAuth access tokens require the `read:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `content` | `string` | Yes | Returns a single [reaction type](https://developer.github.com/v3/reactions/#reaction-types). Omit this parameter to list all reactions to a team discussion. | `<string>` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{discussion_number}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions/{discussion_number}/reactions?content=<string>&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/discussions/{discussion_number}/reactions?content=<string>&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/discussions/{discussion_number}/reactions?content=<string>&per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Create reaction for a team discussion (Legacy)

<div class="api-method-banner">
  <span class="api-method method-post">POST</span> <span class="api-path">/teams/{team_id}/discussions/{discussion_number}/reactions</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`Create reaction for a team discussion`](https://developer.github.com/v3/reactions/#create-reaction-for-a-team-discussion) endpoint.

Create a reaction to a [team discussion](https://developer.github.com/v3/teams/discussions/). OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/). A response with a `Status: 200 OK` means that you already added the reaction type to this team discussion.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{discussion_number}` | `string` | Yes | (Required)  | `<integer>` |




### Request Body

```json
{
  "content": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions/{discussion_number}/reactions \
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

    response = requests.post('https://api.github.com/teams/{team_id}/discussions/{discussion_number}/reactions', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('POST /teams/{team_id}/discussions/{discussion_number}/reactions', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "content": "<string>"
      }
    });
    ```


### Response Example

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



---


## Get a discussion (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/discussions/{discussion_number}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Get a discussion](https://developer.github.com/v3/teams/discussions/#get-a-discussion) endpoint.

Get a specific discussion on a team's page. OAuth access tokens require the `read:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{discussion_number}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions/{discussion_number}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/discussions/{discussion_number}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/discussions/{discussion_number}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Update a discussion (Legacy)

<div class="api-method-banner">
  <span class="api-method method-patch">PATCH</span> <span class="api-path">/teams/{team_id}/discussions/{discussion_number}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Update a discussion](https://developer.github.com/v3/teams/discussions/#update-a-discussion) endpoint.

Edits the title and body text of a discussion post. Only the parameters you provide are updated. OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{discussion_number}` | `string` | Yes | (Required)  | `<integer>` |




### Request Body

```json
{
  "title": "<string>",
  "body": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PATCH \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions/{discussion_number} \
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

    response = requests.patch('https://api.github.com/teams/{team_id}/discussions/{discussion_number}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PATCH /teams/{team_id}/discussions/{discussion_number}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "title": "<string>",
        "body": "<string>"
      }
    });
    ```


### Response Example

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



---


## Delete a discussion (Legacy)

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/teams/{team_id}/discussions/{discussion_number}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`Delete a discussion`](https://developer.github.com/v3/teams/discussions/#delete-a-discussion) endpoint.

Delete a discussion from a team's page. OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{discussion_number}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions/{discussion_number}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/teams/{team_id}/discussions/{discussion_number}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /teams/{team_id}/discussions/{discussion_number}', {
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


## List discussions (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/discussions</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`List discussions`](https://developer.github.com/v3/teams/discussions/#list-discussions) endpoint.

List all discussions on a team's page. OAuth access tokens require the `read:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `direction` | `string` | Yes | One of `asc` (ascending) or `desc` (descending). | `desc` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions?direction=desc&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/discussions?direction=desc&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/discussions?direction=desc&per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Create a discussion (Legacy)

<div class="api-method-banner">
  <span class="api-method method-post">POST</span> <span class="api-path">/teams/{team_id}/discussions</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`Create a discussion`](https://developer.github.com/v3/teams/discussions/#create-a-discussion) endpoint.

Creates a new discussion post on a team's page. OAuth access tokens require the `write:discussion` [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/).

This endpoint triggers [notifications](https://help.github.com/articles/about-notifications/). Creating content too quickly using this endpoint may result in abuse rate limiting. See "[Abuse rate limits](https://developer.github.com/v3/#abuse-rate-limits)" and "[Dealing with abuse rate limits](https://developer.github.com/v3/guides/best-practices-for-integrators/#dealing-with-abuse-rate-limits)" for details.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |




### Request Body

```json
{
  "title": "<string>",
  "body": "<string>",
  "private": false
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/discussions \
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

    response = requests.post('https://api.github.com/teams/{team_id}/discussions', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('POST /teams/{team_id}/discussions', {
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


### Response Example

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



---


## Get team member (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/members/{username}</span>
</div>

The "Get team member" endpoint (described below) is deprecated.

We recommend using the [Get team membership for a user](https://developer.github.com/v3/teams/members/#get-team-membership-for-a-user) endpoint instead. It allows you to get both active and pending memberships.

To list members in a team, the team must be visible to the authenticated user.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/members/{username}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/members/{username}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/members/{username}', {
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


## Add team member (Legacy)

<div class="api-method-banner">
  <span class="api-method method-put">PUT</span> <span class="api-path">/teams/{team_id}/members/{username}</span>
</div>

The "Add team member" endpoint (described below) is deprecated.

We recommend using the [Add or update team membership for a user](https://developer.github.com/v3/teams/members/#add-or-update-team-membership-for-a-user) endpoint instead. It allows you to invite new organization members to your teams.

Team synchronization is available for organizations using GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products) in the GitHub Help documentation.

To add someone to a team, the authenticated user must be an organization owner or a team maintainer in the team they're changing. The person being added to the team must be a member of the team's organization.

> [!NOTE]
> When you have team synchronization set up for a team with your organization's identity provider (IdP), you will see an error if you attempt to use the API for making changes to the team's membership. If you have access to manage group membership in your IdP, you can manage GitHub team membership through your identity provider, which automatically adds and removes team members in an organization. For more information, see "[Synchronizing teams between your identity provider and GitHub](https://help.github.com/articles/synchronizing-teams-between-your-identity-provider-and-github/)."

Note that you'll need to set `Content-Length` to zero when calling out to this endpoint. For more information, see "[HTTP verbs](https://developer.github.com/v3/#http-verbs)."


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PUT \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/members/{username}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.put('https://api.github.com/teams/{team_id}/members/{username}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PUT /teams/{team_id}/members/{username}', {
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


## Remove team member (Legacy)

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/teams/{team_id}/members/{username}</span>
</div>

The "Remove team member" endpoint (described below) is deprecated.

We recommend using the [Remove team membership for a user](https://developer.github.com/v3/teams/members/#remove-team-membership-for-a-user) endpoint instead. It allows you to remove both active and pending memberships.

Team synchronization is available for organizations using GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products) in the GitHub Help documentation.

To remove a team member, the authenticated user must have 'admin' permissions to the team or be an owner of the org that the team is associated with. Removing a team member does not delete the user, it just removes them from the team.

> [!NOTE]
> When you have team synchronization set up for a team with your organization's identity provider (IdP), you will see an error if you attempt to use the API for making changes to the team's membership. If you have access to manage group membership in your IdP, you can manage GitHub team membership through your identity provider, which automatically adds and removes team members in an organization. For more information, see "[Synchronizing teams between your identity provider and GitHub](https://help.github.com/articles/synchronizing-teams-between-your-identity-provider-and-github/)."


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/members/{username}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/teams/{team_id}/members/{username}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /teams/{team_id}/members/{username}', {
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


## List team members (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/members</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`List team members`](https://developer.github.com/v3/teams/members/#list-team-members) endpoint.

Team members will include the members of child teams.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `role` | `string` | Yes | Filters members returned by their role in the team. Can be one of:  <br>\* `member` - normal members of the team.  <br>\* `maintainer` - team maintainers.  <br>\* `all` - all members of the team. | `all` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/members?role=all&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/members?role=all&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/members?role=all&per_page=30&page=1', {
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


## Get team membership for a user (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/memberships/{username}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Get team membership for a user](https://developer.github.com/v3/teams/members/#get-team-membership-for-a-user) endpoint.

Team members will include the members of child teams.

To get a user's membership with a team, the team must be visible to the authenticated user.

> [!NOTE]
> The `role` for organization owners returns as `maintainer`. For more information about `maintainer` roles, see [Create a team](https://developer.github.com/v3/teams/#create-a-team).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/memberships/{username}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/memberships/{username}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/memberships/{username}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "url": "https://api.github.com/teams/1/memberships/octocat",
  "role": "member",
  "state": "active"
}
```



---


## Add or update team membership for a user (Legacy)

<div class="api-method-banner">
  <span class="api-method method-put">PUT</span> <span class="api-path">/teams/{team_id}/memberships/{username}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Add or update team membership for a user](https://developer.github.com/v3/teams/members/#add-or-update-team-membership-for-a-user) endpoint.

Team synchronization is available for organizations using GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products) in the GitHub Help documentation.

If the user is already a member of the team's organization, this endpoint will add the user to the team. To add a membership between an organization member and a team, the authenticated user must be an organization owner or a team maintainer.

> [!NOTE]
> When you have team synchronization set up for a team with your organization's identity provider (IdP), you will see an error if you attempt to use the API for making changes to the team's membership. If you have access to manage group membership in your IdP, you can manage GitHub team membership through your identity provider, which automatically adds and removes team members in an organization. For more information, see "[Synchronizing teams between your identity provider and GitHub](https://help.github.com/articles/synchronizing-teams-between-your-identity-provider-and-github/)."

If the user is unaffiliated with the team's organization, this endpoint will send an invitation to the user via email. This newly-created membership will be in the "pending" state until the user accepts the invitation, at which point the membership will transition to the "active" state and the user will be added as a member of the team. To add a membership between an unaffiliated user and a team, the authenticated user must be an organization owner.

If the user is already a member of the team, this endpoint will update the role of the team member's role. To update the membership of a team member, the authenticated user must be an organization owner or a team maintainer.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |




### Request Body

```json
{
  "role": "member"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PUT \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/memberships/{username} \
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

    response = requests.put('https://api.github.com/teams/{team_id}/memberships/{username}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PUT /teams/{team_id}/memberships/{username}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "role": "member"
      }
    });
    ```


### Response Example

```json
{
  "url": "https://api.github.com/teams/1/memberships/octocat",
  "role": "member",
  "state": "active"
}
```



---


## Remove team membership for a user (Legacy)

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/teams/{team_id}/memberships/{username}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Remove team membership for a user](https://developer.github.com/v3/teams/members/#remove-team-membership-for-a-user) endpoint.

Team synchronization is available for organizations using GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products) in the GitHub Help documentation.

To remove a membership between a user and a team, the authenticated user must have 'admin' permissions to the team or be an owner of the organization that the team is associated with. Removing team membership does not delete the user, it just removes their membership from the team.

> [!NOTE]
> When you have team synchronization set up for a team with your organization's identity provider (IdP), you will see an error if you attempt to use the API for making changes to the team's membership. If you have access to manage group membership in your IdP, you can manage GitHub team membership through your identity provider, which automatically adds and removes team members in an organization. For more information, see "[Synchronizing teams between your identity provider and GitHub](https://help.github.com/articles/synchronizing-teams-between-your-identity-provider-and-github/)."


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/memberships/{username}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/teams/{team_id}/memberships/{username}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /teams/{team_id}/memberships/{username}', {
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


## Check team permissions for a project (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/projects/{project_id}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Check team permissions for a project](https://developer.github.com/v3/teams/#check-team-permissions-for-a-project) endpoint.

Checks whether a team has `read`, `write`, or `admin` permissions for an organization project. The response includes projects inherited from a parent team.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{project_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/projects/{project_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/projects/{project_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/projects/{project_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Add or update team project permissions (Legacy)

<div class="api-method-banner">
  <span class="api-method method-put">PUT</span> <span class="api-path">/teams/{team_id}/projects/{project_id}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Add or update team project permissions](https://developer.github.com/v3/teams/#add-or-update-team-project-permissions) endpoint.

Adds an organization project to a team. To add a project to a team or update the team's permission on a project, the authenticated user must have `admin` permissions for the project. The project and team must be part of the same organization.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{project_id}` | `string` | Yes | (Required)  | `<integer>` |




### Request Body

```json
{
  "permission": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PUT \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/projects/{project_id} \
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

    response = requests.put('https://api.github.com/teams/{team_id}/projects/{project_id}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PUT /teams/{team_id}/projects/{project_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "permission": "<string>"
      }
    });
    ```


### Response Example

```json
{}
```



---


## Remove a project from a team (Legacy)

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/teams/{team_id}/projects/{project_id}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Remove a project from a team](https://developer.github.com/v3/teams/#remove-a-project-from-a-team) endpoint.

Removes an organization project from a team. An organization owner or a team maintainer can remove any project from the team. To remove a project from a team as an organization member, the authenticated user must have `read` access to both the team and project, or `admin` access to the team or project. > [!NOTE]
> This endpoint removes the project from the team, but does not delete it.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{project_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/projects/{project_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/teams/{team_id}/projects/{project_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /teams/{team_id}/projects/{project_id}', {
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


## List team projects (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/projects</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`List team projects`](https://developer.github.com/v3/teams/#list-team-projects) endpoint.

Lists the organization projects for a team.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/projects?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/projects?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/projects?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Check team permissions for a repository (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/repos/{owner}/{repo}</span>
</div>

**Note**: Repositories inherited through a parent team will also be checked.

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Check team permissions for a repository](https://developer.github.com/v3/teams/#check-team-permissions-for-a-repository) endpoint.

You can also get information about the specified repository, including what permissions the team grants on it, by passing the following custom [media type](https://developer.github.com/v3/media/) via the `Accept` header:


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{owner}` | `string` | Yes | (Required)  | `<string>` |
| `{repo}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/repos/{owner}/{repo}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/repos/{owner}/{repo}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/repos/{owner}/{repo}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Add or update team repository permissions (Legacy)

<div class="api-method-banner">
  <span class="api-method method-put">PUT</span> <span class="api-path">/teams/{team_id}/repos/{owner}/{repo}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Add or update team repository permissions](https://developer.github.com/v3/teams/#add-or-update-team-repository-permissions) endpoint.

To add a repository to a team or update the team's permission on a repository, the authenticated user must have admin access to the repository, and must be able to see the team. The repository must be owned by the organization, or a direct fork of a repository owned by the organization. You will get a `422 Unprocessable Entity` status if you attempt to add a repository to a team that is not owned by the organization.

Note that, if you choose not to pass any parameters, you'll need to set `Content-Length` to zero when calling out to this endpoint. For more information, see "[HTTP verbs](https://developer.github.com/v3/#http-verbs)."


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{owner}` | `string` | Yes | (Required)  | `<string>` |
| `{repo}` | `string` | Yes | (Required)  | `<string>` |




### Request Body

```json
{
  "permission": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PUT \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/repos/{owner}/{repo} \
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

    response = requests.put('https://api.github.com/teams/{team_id}/repos/{owner}/{repo}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PUT /teams/{team_id}/repos/{owner}/{repo}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "permission": "<string>"
      }
    });
    ```


### Response Example

```json
{}
```



---


## Remove a repository from a team (Legacy)

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/teams/{team_id}/repos/{owner}/{repo}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Remove a repository from a team](https://developer.github.com/v3/teams/#remove-a-repository-from-a-team) endpoint.

If the authenticated user is an organization owner or a team maintainer, they can remove any repositories from the team. To remove a repository from a team as an organization member, the authenticated user must have admin access to the repository and must be able to see the team. NOTE: This does not delete the repository, it just removes it from the team.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |
| `{owner}` | `string` | Yes | (Required)  | `<string>` |
| `{repo}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/repos/{owner}/{repo}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/teams/{team_id}/repos/{owner}/{repo}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /teams/{team_id}/repos/{owner}/{repo}', {
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


## List team repositories (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/repos</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [List team repositories](https://developer.github.com/v3/teams/#list-team-repositories) endpoint.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/repos?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/repos?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/repos?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## List IdP groups for a team (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/team-sync/group-mappings</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`List IdP groups for a team`](https://developer.github.com/v3/teams/team_sync/#list-idp-groups-for-a-team) endpoint.

Team synchronization is available for organizations using GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products) in the GitHub Help documentation.

List IdP groups connected to a team on GitHub.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/team-sync/group-mappings
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/team-sync/group-mappings', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/team-sync/group-mappings', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Create or update IdP group connections (Legacy)

<div class="api-method-banner">
  <span class="api-method method-patch">PATCH</span> <span class="api-path">/teams/{team_id}/team-sync/group-mappings</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`Create or update IdP group connections`](https://developer.github.com/v3/teams/team_sync/#create-or-update-idp-group-connections) endpoint.

Team synchronization is available for organizations using GitHub Enterprise Cloud. For more information, see [GitHub's products](https://help.github.com/github/getting-started-with-github/githubs-products) in the GitHub Help documentation.

Creates, updates, or removes a connection between a team and an IdP group. When adding groups to a team, you must include all new and existing groups to avoid replacing existing groups with the new ones. Specifying an empty `groups` array will remove all connections for a team.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |




### Request Body

```json
{
  "groups": [
    {
      "group_id": "<string>",
      "group_name": "<string>",
      "group_description": "<string>",
      "id": "<string>",
      "name": "<string>",
      "description": "<string>"
    },
    {
      "group_id": "<string>",
      "group_name": "<string>",
      "group_description": "<string>",
      "id": "<string>",
      "name": "<string>",
      "description": "<string>"
    }
  ],
  "synced_at": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PATCH \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/team-sync/group-mappings \
      -d '{
      "groups": [
        {
          "group_id": "<string>",
          "group_name": "<string>",
          "group_description": "<string>",
          "id": "<string>",
          "name": "<string>",
          "description": "<string>"
        },
        {
          "group_id": "<string>",
          "group_name": "<string>",
          "group_description": "<string>",
          "id": "<string>",
          "name": "<string>",
          "description": "<string>"
        }
      ],
      "synced_at": "<string>"
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
          "group_description": "<string>",
          "id": "<string>",
          "name": "<string>",
          "description": "<string>"
        },
        {
          "group_id": "<string>",
          "group_name": "<string>",
          "group_description": "<string>",
          "id": "<string>",
          "name": "<string>",
          "description": "<string>"
        }
      ],
      "synced_at": "<string>"
    }

    response = requests.patch('https://api.github.com/teams/{team_id}/team-sync/group-mappings', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PATCH /teams/{team_id}/team-sync/group-mappings', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "groups": [
          {
            "group_id": "<string>",
            "group_name": "<string>",
            "group_description": "<string>",
            "id": "<string>",
            "name": "<string>",
            "description": "<string>"
          },
          {
            "group_id": "<string>",
            "group_name": "<string>",
            "group_description": "<string>",
            "id": "<string>",
            "name": "<string>",
            "description": "<string>"
          }
        ],
        "synced_at": "<string>"
      }
    });
    ```


### Response Example

```json
{
  "groups": [
    {
      "group_id": "123",
      "group_name": "Octocat admins",
      "group_description": "The people who configure your octoworld."
    }
  ]
}
```



---


## Get a team (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the [Get a team by name](https://developer.github.com/v3/teams/#get-a-team-by-name) endpoint.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Update a team (Legacy)

<div class="api-method-banner">
  <span class="api-method method-patch">PATCH</span> <span class="api-path">/teams/{team_id}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Update a team](https://developer.github.com/v3/teams/#update-a-team) endpoint.

To edit a team, the authenticated user must either be an organization owner or a team maintainer.

> [!NOTE]
> With nested teams, the `privacy` for parent teams cannot be `secret`.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |




### Request Body

```json
{
  "name": "<string>",
  "description": "<string>",
  "privacy": "<string>",
  "permission": "pull",
  "parent_team_id": "<integer>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PATCH \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id} \
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

    response = requests.patch('https://api.github.com/teams/{team_id}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PATCH /teams/{team_id}', {
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


### Response Example

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



---


## Delete a team (Legacy)

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/teams/{team_id}</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [Delete a team](https://developer.github.com/v3/teams/#delete-a-team) endpoint.

To delete a team, the authenticated user must be an organization owner or team maintainer.

If you are an organization owner, deleting a parent team will delete all of its child teams as well.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/teams/{team_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /teams/{team_id}', {
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


## List pending team invitations (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/invitations</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`List pending team invitations`](https://developer.github.com/v3/teams/members/#list-pending-team-invitations) endpoint.

The return hash contains a `role` field which refers to the Organization Invitation role and will be one of the following values: `direct_member`, `admin`, `billing_manager`, `hiring_manager`, or `reinstate`. If the invitee is not a GitHub member, the `login` field in the return hash will be `null`.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/invitations?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/invitations?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/invitations?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## List child teams (Legacy)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/teams/{team_id}/teams</span>
</div>

**Deprecation Notice:** This endpoint route is deprecated and will be removed from the Teams API. We recommend migrating your existing code to use the new [`List child teams`](https://developer.github.com/v3/teams/#list-child-teams) endpoint.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{team_id}` | `string` | Yes | (Required)  | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/teams/{team_id}/teams?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/teams/{team_id}/teams?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /teams/{team_id}/teams?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---

