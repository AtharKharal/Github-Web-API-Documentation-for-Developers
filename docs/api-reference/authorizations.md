# authorizations API


## Get-or-create an authorization for a specific app

<div class="api-method-banner">
  <span class="api-method method-put">PUT</span> <span class="api-path">/authorizations/clients/{client_id}</span>
</div>

**Deprecation Notice:** GitHub will discontinue the [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/), which is used by integrations to create personal access tokens and OAuth tokens, and you must now create these tokens using our [web application flow](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow). The [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/) will be removed on November, 13, 2020. For more information, including scheduled brownouts, see the [blog post](https://developer.github.com/changes/2020-02-14-deprecating-oauth-auth-endpoint/).

**Warning:** Apps must use the [web application flow](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow) to obtain OAuth tokens that work with GitHub SAML organizations. OAuth tokens created using the Authorizations API will be unable to access GitHub SAML organizations. For more information, see the [blog post](https://developer.github.com/changes/2019-11-05-deprecated-passwords-and-authorizations-api).

Creates a new authorization for the specified OAuth application, only if an authorization for that application doesn't already exist for the user. The URL includes the 20 character client ID for the OAuth app that is requesting the token. It returns the user's existing authorization for the application if one is present. Otherwise, it creates and returns a new one.

If you have two-factor authentication setup, Basic Authentication for this endpoint requires that you use a one-time password (OTP) and your username and password instead of tokens. For more information, see "[Working with two-factor authentication](https://developer.github.com/v3/auth/#working-with-two-factor-authentication)."

**Deprecation Notice:** GitHub will discontinue the [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/), which is used by integrations to create personal access tokens and OAuth tokens, and you must now create these tokens using our [web application flow](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow). The [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/) will be removed on November, 13, 2020. For more information, including scheduled brownouts, see the [blog post](https://developer.github.com/changes/2020-02-14-deprecating-oauth-auth-endpoint/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{client_id}` | `string` | Yes | (Required)  | `<string>` |




### Request Body

```json
{
  "client_secret": "<string>",
  "scopes": [
    "<string>",
    "<string>"
  ],
  "note": "<string>",
  "note_url": "<string>",
  "fingerprint": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PUT \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/authorizations/clients/{client_id} \
      -d '{
      "client_secret": "<string>",
      "scopes": [
        "<string>",
        "<string>"
      ],
      "note": "<string>",
      "note_url": "<string>",
      "fingerprint": "<string>"
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
      "client_secret": "<string>",
      "scopes": [
        "<string>",
        "<string>"
      ],
      "note": "<string>",
      "note_url": "<string>",
      "fingerprint": "<string>"
    }

    response = requests.put('https://api.github.com/authorizations/clients/{client_id}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PUT /authorizations/clients/{client_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "client_secret": "<string>",
        "scopes": [
          "<string>",
          "<string>"
        ],
        "note": "<string>",
        "note_url": "<string>",
        "fingerprint": "<string>"
      }
    });
    ```


### Response Example

```json
{
  "id": 1,
  "url": "https://api.github.com/authorizations/1",
  "scopes": [
    "public_repo"
  ],
  "token": "",
  "token_last_eight": "12345678",
  "hashed_token": "25f94a2a5c7fbaf499c665bc73d67c1c87e496da8985131633ee0a95819db2e8",
  "app": {
    "url": "http://my-github-app.com",
    "name": "my github app",
    "client_id": "abcde12345fghij67890"
  },
  "note": "optional note",
  "note_url": "http://optional/note/url",
  "updated_at": "2011-09-06T20:39:23Z",
  "created_at": "2011-09-06T17:26:27Z",
  "fingerprint": ""
}
```



---


## Get-or-create an authorization for a specific app and fingerprint

<div class="api-method-banner">
  <span class="api-method method-put">PUT</span> <span class="api-path">/authorizations/clients/{client_id}/{fingerprint}</span>
</div>

**Deprecation Notice:** GitHub will discontinue the [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/), which is used by integrations to create personal access tokens and OAuth tokens, and you must now create these tokens using our [web application flow](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow). The [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/) will be removed on November, 13, 2020. For more information, including scheduled brownouts, see the [blog post](https://developer.github.com/changes/2020-02-14-deprecating-oauth-auth-endpoint/).

**Warning:** Apps must use the [web application flow](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow) to obtain OAuth tokens that work with GitHub SAML organizations. OAuth tokens created using the Authorizations API will be unable to access GitHub SAML organizations. For more information, see the [blog post](https://developer.github.com/changes/2019-11-05-deprecated-passwords-and-authorizations-api).

This method will create a new authorization for the specified OAuth application, only if an authorization for that application and fingerprint do not already exist for the user. The URL includes the 20 character client ID for the OAuth app that is requesting the token. `fingerprint` is a unique string to distinguish an authorization from others created for the same client ID and user. It returns the user's existing authorization for the application if one is present. Otherwise, it creates and returns a new one.

If you have two-factor authentication setup, Basic Authentication for this endpoint requires that you use a one-time password (OTP) and your username and password instead of tokens. For more information, see "[Working with two-factor authentication](https://developer.github.com/v3/auth/#working-with-two-factor-authentication)."


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{client_id}` | `string` | Yes | (Required)  | `<string>` |
| `{fingerprint}` | `string` | Yes | (Required) fingerprint parameter | `<string>` |




### Request Body

```json
{
  "client_secret": "<string>",
  "scopes": [
    "<string>",
    "<string>"
  ],
  "note": "<string>",
  "note_url": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PUT \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/authorizations/clients/{client_id}/{fingerprint} \
      -d '{
      "client_secret": "<string>",
      "scopes": [
        "<string>",
        "<string>"
      ],
      "note": "<string>",
      "note_url": "<string>"
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
      "client_secret": "<string>",
      "scopes": [
        "<string>",
        "<string>"
      ],
      "note": "<string>",
      "note_url": "<string>"
    }

    response = requests.put('https://api.github.com/authorizations/clients/{client_id}/{fingerprint}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PUT /authorizations/clients/{client_id}/{fingerprint}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "client_secret": "<string>",
        "scopes": [
          "<string>",
          "<string>"
        ],
        "note": "<string>",
        "note_url": "<string>"
      }
    });
    ```


### Response Example

```json
{
  "id": 1,
  "url": "https://api.github.com/authorizations/1",
  "scopes": [
    "public_repo"
  ],
  "token": "",
  "token_last_eight": "12345678",
  "hashed_token": "25f94a2a5c7fbaf499c665bc73d67c1c87e496da8985131633ee0a95819db2e8",
  "app": {
    "url": "http://my-github-app.com",
    "name": "my github app",
    "client_id": "abcde12345fghij67890"
  },
  "note": "optional note",
  "note_url": "http://optional/note/url",
  "updated_at": "2011-09-06T20:39:23Z",
  "created_at": "2011-09-06T17:26:27Z",
  "fingerprint": "jklmnop12345678"
}
```



---


## Get a single authorization

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/authorizations/{authorization_id}</span>
</div>

**Deprecation Notice:** GitHub will discontinue the [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/), which is used by integrations to create personal access tokens and OAuth tokens, and you must now create these tokens using our [web application flow](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow). The [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/) will be removed on November, 13, 2020. For more information, including scheduled brownouts, see the [blog post](https://developer.github.com/changes/2020-02-14-deprecating-oauth-auth-endpoint/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{authorization_id}` | `string` | Yes | (Required) authorization_id parameter | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/authorizations/{authorization_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/authorizations/{authorization_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /authorizations/{authorization_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "id": 1,
  "url": "https://api.github.com/authorizations/1",
  "scopes": [
    "public_repo"
  ],
  "token": "",
  "token_last_eight": "12345678",
  "hashed_token": "25f94a2a5c7fbaf499c665bc73d67c1c87e496da8985131633ee0a95819db2e8",
  "app": {
    "url": "http://my-github-app.com",
    "name": "my github app",
    "client_id": "abcde12345fghij67890"
  },
  "note": "optional note",
  "note_url": "http://optional/note/url",
  "updated_at": "2011-09-06T20:39:23Z",
  "created_at": "2011-09-06T17:26:27Z",
  "fingerprint": "jklmnop12345678"
}
```



---


## Update an existing authorization

<div class="api-method-banner">
  <span class="api-method method-patch">PATCH</span> <span class="api-path">/authorizations/{authorization_id}</span>
</div>

**Deprecation Notice:** GitHub will discontinue the [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/), which is used by integrations to create personal access tokens and OAuth tokens, and you must now create these tokens using our [web application flow](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow). The [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/) will be removed on November, 13, 2020. For more information, including scheduled brownouts, see the [blog post](https://developer.github.com/changes/2020-02-14-deprecating-oauth-auth-endpoint/).

If you have two-factor authentication setup, Basic Authentication for this endpoint requires that you use a one-time password (OTP) and your username and password instead of tokens. For more information, see "[Working with two-factor authentication](https://developer.github.com/v3/auth/#working-with-two-factor-authentication)."

You can only send one of these scope keys at a time.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{authorization_id}` | `string` | Yes | (Required) authorization_id parameter | `<integer>` |




### Request Body

```json
{
  "scopes": [
    "<string>",
    "<string>"
  ],
  "add_scopes": [
    "<string>",
    "<string>"
  ],
  "remove_scopes": [
    "<string>",
    "<string>"
  ],
  "note": "<string>",
  "note_url": "<string>",
  "fingerprint": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PATCH \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/authorizations/{authorization_id} \
      -d '{
      "scopes": [
        "<string>",
        "<string>"
      ],
      "add_scopes": [
        "<string>",
        "<string>"
      ],
      "remove_scopes": [
        "<string>",
        "<string>"
      ],
      "note": "<string>",
      "note_url": "<string>",
      "fingerprint": "<string>"
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
      "scopes": [
        "<string>",
        "<string>"
      ],
      "add_scopes": [
        "<string>",
        "<string>"
      ],
      "remove_scopes": [
        "<string>",
        "<string>"
      ],
      "note": "<string>",
      "note_url": "<string>",
      "fingerprint": "<string>"
    }

    response = requests.patch('https://api.github.com/authorizations/{authorization_id}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PATCH /authorizations/{authorization_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "scopes": [
          "<string>",
          "<string>"
        ],
        "add_scopes": [
          "<string>",
          "<string>"
        ],
        "remove_scopes": [
          "<string>",
          "<string>"
        ],
        "note": "<string>",
        "note_url": "<string>",
        "fingerprint": "<string>"
      }
    });
    ```


### Response Example

```json
{
  "id": 1,
  "url": "https://api.github.com/authorizations/1",
  "scopes": [
    "public_repo"
  ],
  "token": "",
  "token_last_eight": "12345678",
  "hashed_token": "25f94a2a5c7fbaf499c665bc73d67c1c87e496da8985131633ee0a95819db2e8",
  "app": {
    "url": "http://my-github-app.com",
    "name": "my github app",
    "client_id": "abcde12345fghij67890"
  },
  "note": "optional note",
  "note_url": "http://optional/note/url",
  "updated_at": "2011-09-06T20:39:23Z",
  "created_at": "2011-09-06T17:26:27Z",
  "fingerprint": "jklmnop12345678"
}
```



---


## Delete an authorization

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/authorizations/{authorization_id}</span>
</div>

**Deprecation Notice:** GitHub will discontinue the [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/), which is used by integrations to create personal access tokens and OAuth tokens, and you must now create these tokens using our [web application flow](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow). The [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/) will be removed on November, 13, 2020. For more information, including scheduled brownouts, see the [blog post](https://developer.github.com/changes/2020-02-14-deprecating-oauth-auth-endpoint/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{authorization_id}` | `string` | Yes | (Required) authorization_id parameter | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/authorizations/{authorization_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/authorizations/{authorization_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /authorizations/{authorization_id}', {
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


## List your authorizations

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/authorizations</span>
</div>

**Deprecation Notice:** GitHub will discontinue the [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/), which is used by integrations to create personal access tokens and OAuth tokens, and you must now create these tokens using our [web application flow](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow). The [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/) will be removed on November, 13, 2020. For more information, including scheduled brownouts, see the [blog post](https://developer.github.com/changes/2020-02-14-deprecating-oauth-auth-endpoint/).


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/authorizations?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/authorizations?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /authorizations?per_page=30&page=1', {
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
    "url": "https://api.github.com/authorizations/1",
    "scopes": [
      "public_repo"
    ],
    "token": "",
    "token_last_eight": "12345678",
    "hashed_token": "25f94a2a5c7fbaf499c665bc73d67c1c87e496da8985131633ee0a95819db2e8",
    "app": {
      "url": "http://my-github-app.com",
      "name": "my github app",
      "client_id": "abcde12345fghij67890"
    },
    "note": "optional note",
    "note_url": "http://optional/note/url",
    "updated_at": "2011-09-06T20:39:23Z",
    "created_at": "2011-09-06T17:26:27Z",
    "fingerprint": "jklmnop12345678"
  }
]
```



---


## Create a new authorization

<div class="api-method-banner">
  <span class="api-method method-post">POST</span> <span class="api-path">/authorizations</span>
</div>

**Deprecation Notice:** GitHub will discontinue the [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/), which is used by integrations to create personal access tokens and OAuth tokens, and you must now create these tokens using our [web application flow](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow). The [OAuth Authorizations API](https://developer.github.com/v3/oauth_authorizations/) will be removed on November, 13, 2020. For more information, including scheduled brownouts, see the [blog post](https://developer.github.com/changes/2020-02-14-deprecating-oauth-auth-endpoint/).

**Warning:** Apps must use the [web application flow](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow) to obtain OAuth tokens that work with GitHub SAML organizations. OAuth tokens created using the Authorizations API will be unable to access GitHub SAML organizations. For more information, see the [blog post](https://developer.github.com/changes/2019-11-05-deprecated-passwords-and-authorizations-api).

Creates OAuth tokens using [Basic Authentication](https://developer.github.com/v3/auth#basic-authentication). If you have two-factor authentication setup, Basic Authentication for this endpoint requires that you use a one-time password (OTP) and your username and password instead of tokens. For more information, see "[Working with two-factor authentication](https://developer.github.com/v3/auth/#working-with-two-factor-authentication)."

To create tokens for a particular OAuth application using this endpoint, you must authenticate as the user you want to create an authorization for and provide the app's client ID and secret, found on your OAuth application's settings page. If your OAuth application intends to create multiple tokens for one user, use `fingerprint` to differentiate between them.

You can also create tokens on GitHub from the [personal access tokens settings](https://github.com/settings/tokens) page. Read more about these tokens in [the GitHub Help documentation](https://help.github.com/articles/creating-an-access-token-for-command-line-use).

Organizations that enforce SAML SSO require personal access tokens to be allowed. Read more about allowing tokens in [the GitHub Help documentation](https://help.github.com/articles/about-identity-and-access-management-with-saml-single-sign-on).




### Request Body

```json
{
  "scopes": [
    "<string>",
    "<string>"
  ],
  "note": "<string>",
  "note_url": "<string>",
  "client_id": "<string>",
  "client_secret": "<string>",
  "fingerprint": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/authorizations \
      -d '{
      "scopes": [
        "<string>",
        "<string>"
      ],
      "note": "<string>",
      "note_url": "<string>",
      "client_id": "<string>",
      "client_secret": "<string>",
      "fingerprint": "<string>"
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
      "scopes": [
        "<string>",
        "<string>"
      ],
      "note": "<string>",
      "note_url": "<string>",
      "client_id": "<string>",
      "client_secret": "<string>",
      "fingerprint": "<string>"
    }

    response = requests.post('https://api.github.com/authorizations', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('POST /authorizations', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "scopes": [
          "<string>",
          "<string>"
        ],
        "note": "<string>",
        "note_url": "<string>",
        "client_id": "<string>",
        "client_secret": "<string>",
        "fingerprint": "<string>"
      }
    });
    ```


### Response Example

```json
{
  "id": 1,
  "url": "https://api.github.com/authorizations/1",
  "scopes": [
    "public_repo"
  ],
  "token": "abcdefgh12345678",
  "token_last_eight": "12345678",
  "hashed_token": "25f94a2a5c7fbaf499c665bc73d67c1c87e496da8985131633ee0a95819db2e8",
  "app": {
    "url": "http://my-github-app.com",
    "name": "my github app",
    "client_id": "abcde12345fghij67890"
  },
  "note": "optional note",
  "note_url": "http://optional/note/url",
  "updated_at": "2011-09-06T20:39:23Z",
  "created_at": "2011-09-06T17:26:27Z",
  "fingerprint": ""
}
```



---

