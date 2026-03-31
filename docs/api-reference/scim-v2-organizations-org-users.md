# scim/v2/organizations/{org}/Users API


## Get SCIM provisioning information for a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/scim/v2/organizations/{org}/Users/{scim_user_id}</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{org}` | `string` | Yes | (Required)  | `<string>` |
| `{scim_user_id}` | `string` | Yes | (Required) scim_user_id parameter | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/scim/v2/organizations/{org}/Users/{scim_user_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/scim/v2/organizations/{org}/Users/{scim_user_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /scim/v2/organizations/{org}/Users/{scim_user_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "id": "edefdfedf-050c-11e7-8d32",
  "externalId": "a7d0f98382",
  "userName": "mona.octocat@okta.example.com",
  "displayName": "Monalisa Octocat",
  "name": {
    "givenName": "Monalisa",
    "familyName": "Octocat",
    "formatted": "Monalisa Octocat"
  },
  "emails": [
    {
      "value": "mona.octocat@okta.example.com",
      "primary": true
    },
    {
      "value": "monalisa@octocat.github.com"
    }
  ],
  "active": true,
  "meta": {
    "resourceType": "User",
    "created": "2017-03-09T16:11:13-05:00",
    "lastModified": "2017-03-09T16:11:13-05:00",
    "location": "https://api.github.com/scim/v2/organizations/octo-org/Users/edefdfedf-050c-11e7-8d32"
  }
}
```



---


## Update a provisioned organization membership

<div class="api-method-banner">
  <span class="api-method method-put">PUT</span> <span class="api-path">/scim/v2/organizations/{org}/Users/{scim_user_id}</span>
</div>

Replaces an existing provisioned user's information. You must provide all the information required for the user as if you were provisioning them for the first time. Any existing user information that you don't provide will be removed. If you want to only update a specific attribute, use the [Update an attribute for a SCIM user](https://developer.github.com/v3/scim/#update-an-attribute-for-a-scim-user) endpoint instead.

You must at least provide the required values for the user: `userName`, `name`, and `emails`.

**Warning:** Setting `active: false` removes the user from the organization, deletes the external identity, and deletes the associated `{scim_user_id}`.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{org}` | `string` | Yes | (Required)  | `<string>` |
| `{scim_user_id}` | `string` | Yes | (Required) scim_user_id parameter | `<string>` |




### Request Body

```json
{
  "userName": "<string>",
  "name": {
    "givenName": "<string>",
    "familyName": "<string>",
    "formatted": "<string>"
  },
  "emails": [
    {
      "value": "<string>",
      "type": "<string>",
      "primary": "<boolean>"
    }
  ],
  "schemas": [
    "<string>",
    "<string>"
  ],
  "displayName": "<string>",
  "externalId": "<string>",
  "groups": [
    "<string>",
    "<string>"
  ],
  "active": "<boolean>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PUT \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/scim/v2/organizations/{org}/Users/{scim_user_id} \
      -d '{
      "userName": "<string>",
      "name": {
        "givenName": "<string>",
        "familyName": "<string>",
        "formatted": "<string>"
      },
      "emails": [
        {
          "value": "<string>",
          "type": "<string>",
          "primary": "<boolean>"
        }
      ],
      "schemas": [
        "<string>",
        "<string>"
      ],
      "displayName": "<string>",
      "externalId": "<string>",
      "groups": [
        "<string>",
        "<string>"
      ],
      "active": "<boolean>"
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
      "userName": "<string>",
      "name": {
        "givenName": "<string>",
        "familyName": "<string>",
        "formatted": "<string>"
      },
      "emails": [
        {
          "value": "<string>",
          "type": "<string>",
          "primary": "<boolean>"
        }
      ],
      "schemas": [
        "<string>",
        "<string>"
      ],
      "displayName": "<string>",
      "externalId": "<string>",
      "groups": [
        "<string>",
        "<string>"
      ],
      "active": "<boolean>"
    }

    response = requests.put('https://api.github.com/scim/v2/organizations/{org}/Users/{scim_user_id}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PUT /scim/v2/organizations/{org}/Users/{scim_user_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "userName": "<string>",
        "name": {
          "givenName": "<string>",
          "familyName": "<string>",
          "formatted": "<string>"
        },
        "emails": [
          {
            "value": "<string>",
            "type": "<string>",
            "primary": "<boolean>"
          }
        ],
        "schemas": [
          "<string>",
          "<string>"
        ],
        "displayName": "<string>",
        "externalId": "<string>",
        "groups": [
          "<string>",
          "<string>"
        ],
        "active": "<boolean>"
      }
    });
    ```


### Response Example

```json
{
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "id": "edefdfedf-050c-11e7-8d32",
  "externalId": "a7d0f98382",
  "userName": "mona.octocat@okta.example.com",
  "displayName": "Monalisa Octocat",
  "name": {
    "givenName": "Monalisa",
    "familyName": "Octocat",
    "formatted": "Monalisa Octocat"
  },
  "emails": [
    {
      "value": "mona.octocat@okta.example.com",
      "primary": true
    },
    {
      "value": "monalisa@octocat.github.com"
    }
  ],
  "active": true,
  "meta": {
    "resourceType": "User",
    "created": "2017-03-09T16:11:13-05:00",
    "lastModified": "2017-03-09T16:11:13-05:00",
    "location": "https://api.github.com/scim/v2/organizations/octo-org/Users/edefdfedf-050c-11e7-8d32"
  }
}
```



---


## Update an attribute for a SCIM user

<div class="api-method-banner">
  <span class="api-method method-patch">PATCH</span> <span class="api-path">/scim/v2/organizations/{org}/Users/{scim_user_id}</span>
</div>

Allows you to change a provisioned user's individual attributes. To change a user's values, you must provide a specific `Operations` JSON format that contains at least one of the `add`, `remove`, or `replace` operations. For examples and more information on the SCIM operations format, see the [SCIM specification](https://tools.ietf.org/html/rfc7644#section-3.5.2).

> [!NOTE]
> Complicated SCIM `path` selectors that include filters are not supported. For example, a `path` selector defined as `"path": "emails[type eq \"work\"]"` will not work.

**Warning:** If you set `active:false` using the `replace` operation (as shown in the JSON example below), it removes the user from the organization, deletes the external identity, and deletes the associated `:scim_user_id`.

```
{
  "Operations":[{
    "op":"replace",
    "value":{
      "active":false
    }
  }]
}
```


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{org}` | `string` | Yes | (Required)  | `<string>` |
| `{scim_user_id}` | `string` | Yes | (Required) scim_user_id parameter | `<string>` |




### Request Body

```json
{
  "Operations": [
    {
      "op": "<string>",
      "path": "<string>",
      "value": {
        "active": "<boolean>",
        "userName": "<string>",
        "externalId": "<string>",
        "givenName": "<string>",
        "familyName": "<string>"
      }
    }
  ],
  "schemas": [
    "<string>",
    "<string>"
  ]
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X PATCH \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/scim/v2/organizations/{org}/Users/{scim_user_id} \
      -d '{
      "Operations": [
        {
          "op": "<string>",
          "path": "<string>",
          "value": {
            "active": "<boolean>",
            "userName": "<string>",
            "externalId": "<string>",
            "givenName": "<string>",
            "familyName": "<string>"
          }
        }
      ],
      "schemas": [
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
      "Operations": [
        {
          "op": "<string>",
          "path": "<string>",
          "value": {
            "active": "<boolean>",
            "userName": "<string>",
            "externalId": "<string>",
            "givenName": "<string>",
            "familyName": "<string>"
          }
        }
      ],
      "schemas": [
        "<string>",
        "<string>"
      ]
    }

    response = requests.patch('https://api.github.com/scim/v2/organizations/{org}/Users/{scim_user_id}', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('PATCH /scim/v2/organizations/{org}/Users/{scim_user_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "Operations": [
          {
            "op": "<string>",
            "path": "<string>",
            "value": {
              "active": "<boolean>",
              "userName": "<string>",
              "externalId": "<string>",
              "givenName": "<string>",
              "familyName": "<string>"
            }
          }
        ],
        "schemas": [
          "<string>",
          "<string>"
        ]
      }
    });
    ```


### Response Example

```json
{
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "id": "edefdfedf-050c-11e7-8d32",
  "externalId": "a7d0f98382",
  "userName": "mona.octocat@okta.example.com",
  "displayName": "Monalisa Octocat",
  "name": {
    "givenName": "Monalisa",
    "familyName": "Octocat",
    "formatted": "Monalisa Octocat"
  },
  "emails": [
    {
      "value": "mona.octocat@okta.example.com",
      "primary": true
    },
    {
      "value": "monalisa@octocat.github.com"
    }
  ],
  "active": true,
  "meta": {
    "resourceType": "User",
    "created": "2017-03-09T16:11:13-05:00",
    "lastModified": "2017-03-09T16:11:13-05:00",
    "location": "https://api.github.com/scim/v2/organizations/octo-org/Users/edefdfedf-050c-11e7-8d32"
  }
}
```



---


## Delete a SCIM user from an organization

<div class="api-method-banner">
  <span class="api-method method-delete">DELETE</span> <span class="api-path">/scim/v2/organizations/{org}/Users/{scim_user_id}</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{org}` | `string` | Yes | (Required)  | `<string>` |
| `{scim_user_id}` | `string` | Yes | (Required) scim_user_id parameter | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X DELETE \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/scim/v2/organizations/{org}/Users/{scim_user_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.delete('https://api.github.com/scim/v2/organizations/{org}/Users/{scim_user_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('DELETE /scim/v2/organizations/{org}/Users/{scim_user_id}', {
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


## List SCIM provisioned identities

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/scim/v2/organizations/{org}/Users</span>
</div>

Retrieves a paginated list of all provisioned organization members, including pending invitations. If you provide the `filter` parameter, the resources for all matching provisions members are returned.

When a user with a SAML-provisioned external identity leaves (or is removed from) an organization, the account's metadata is immediately removed. However, the returned list of user accounts might not always match the organization or enterprise member list you see on GitHub. This can happen in certain cases where an external identity associated with an organization will not match an organization member:
  - When a user with a SCIM-provisioned external identity is removed from an organization, the account's metadata is preserved to allow the user to re-join the organization in the future.
  - When inviting a user to join an organization, you can expect to see their external identity in the results before they accept the invitation, or if the invitation is cancelled (or never accepted).
  - When a user is invited over SCIM, an external identity is created that matches with the invitee's email address. However, this identity is only linked to a user account when the user accepts the invitation by going through SAML SSO.

The returned list of external identities can include an entry for a `null` user. These are unlinked SAML identities that are created when a user goes through the following Single Sign-On (SSO) process but does not sign in to their GitHub account after completing SSO:

1. The user is granted access by the IdP and is not a member of the GitHub organization.

1. The user attempts to access the GitHub organization and initiates the SAML SSO process, and is not currently signed in to their GitHub account.

1. After successfully authenticating with the SAML SSO IdP, the `null` external identity entry is created and the user is prompted to sign in to their GitHub account:
   - If the user signs in, their GitHub account is linked to this entry.
   - If the user does not sign in (or does not create a new account when prompted), they are not added to the GitHub organization, and the external identity `null` entry remains in place.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `startIndex` | `string` | Yes | Used for pagination: the index of the first result to return. | `<integer>` |
| `count` | `string` | Yes | Used for pagination: the number of results to return. | `<integer>` |
| `filter` | `string` | Yes | Filters results using the equals query parameter operator (`eq`). You can filter results that are equal to `id`, `userName`, `emails`, and `external_id`. For example, to search for an identity with the `userName` Octocat, you would use this query:<br><br>`?filter=userName%20eq%20\"Octocat\"`.<br><br>To filter results for for the identity with the email `octocat@github.com`, you would use this query:<br><br>`?filter=emails%20eq%20\"octocat@github.com\"`. | `<string>` |
| `{org}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/scim/v2/organizations/{org}/Users?startIndex=<integer>&count=<integer>&filter=<string>
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/scim/v2/organizations/{org}/Users?startIndex=<integer>&count=<integer>&filter=<string>', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /scim/v2/organizations/{org}/Users?startIndex=<integer>&count=<integer>&filter=<string>', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "schemas": [
    "urn:ietf:params:scim:api:messages:2.0:ListResponse"
  ],
  "totalResults": 1,
  "itemsPerPage": 1,
  "startIndex": 1,
  "Resources": [
    {
      "schemas": [
        "urn:ietf:params:scim:schemas:core:2.0:User"
      ],
      "id": "5fc0c238-1112-11e8-8e45-920c87bdbd75",
      "externalId": "00u1dhhb1fkIGP7RL1d8",
      "userName": "octocat@github.com",
      "displayName": "Mona Octocat",
      "name": {
        "givenName": "Mona",
        "familyName": "Octocat",
        "formatted": "Mona Octocat"
      },
      "emails": [
        {
          "value": "octocat@github.com",
          "primary": true
        }
      ],
      "active": true,
      "meta": {
        "resourceType": "User",
        "created": "2018-02-13T15:05:24.000-08:00",
        "lastModified": "2018-02-13T15:05:55.000-08:00",
        "location": "https://api.github.com/scim/v2/organizations/octo-org/Users/5fc0c238-1112-11e8-8e45-920c87bdbd75"
      }
    }
  ]
}
```



---


## Provision and invite a SCIM user

<div class="api-method-banner">
  <span class="api-method method-post">POST</span> <span class="api-path">/scim/v2/organizations/{org}/Users</span>
</div>

Provision organization membership for a user, and send an activation email to the email address.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{org}` | `string` | Yes | (Required)  | `<string>` |




### Request Body

```json
{
  "userName": "<string>",
  "name": {
    "givenName": "<string>",
    "familyName": "<string>",
    "formatted": "<string>"
  },
  "emails": [
    {
      "value": "<string>",
      "primary": "<boolean>",
      "type": "<string>"
    }
  ],
  "displayName": "<string>",
  "schemas": [
    "<string>",
    "<string>"
  ],
  "externalId": "<string>",
  "groups": [
    "<string>",
    "<string>"
  ],
  "active": "<boolean>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/scim/v2/organizations/{org}/Users \
      -d '{
      "userName": "<string>",
      "name": {
        "givenName": "<string>",
        "familyName": "<string>",
        "formatted": "<string>"
      },
      "emails": [
        {
          "value": "<string>",
          "primary": "<boolean>",
          "type": "<string>"
        }
      ],
      "displayName": "<string>",
      "schemas": [
        "<string>",
        "<string>"
      ],
      "externalId": "<string>",
      "groups": [
        "<string>",
        "<string>"
      ],
      "active": "<boolean>"
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
      "userName": "<string>",
      "name": {
        "givenName": "<string>",
        "familyName": "<string>",
        "formatted": "<string>"
      },
      "emails": [
        {
          "value": "<string>",
          "primary": "<boolean>",
          "type": "<string>"
        }
      ],
      "displayName": "<string>",
      "schemas": [
        "<string>",
        "<string>"
      ],
      "externalId": "<string>",
      "groups": [
        "<string>",
        "<string>"
      ],
      "active": "<boolean>"
    }

    response = requests.post('https://api.github.com/scim/v2/organizations/{org}/Users', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('POST /scim/v2/organizations/{org}/Users', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "userName": "<string>",
        "name": {
          "givenName": "<string>",
          "familyName": "<string>",
          "formatted": "<string>"
        },
        "emails": [
          {
            "value": "<string>",
            "primary": "<boolean>",
            "type": "<string>"
          }
        ],
        "displayName": "<string>",
        "schemas": [
          "<string>",
          "<string>"
        ],
        "externalId": "<string>",
        "groups": [
          "<string>",
          "<string>"
        ],
        "active": "<boolean>"
      }
    });
    ```


### Response Example

```json
{
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "id": "edefdfedf-050c-11e7-8d32",
  "externalId": "a7d0f98382",
  "userName": "mona.octocat@okta.example.com",
  "displayName": "Monalisa Octocat",
  "name": {
    "givenName": "Monalisa",
    "familyName": "Octocat",
    "formatted": "Monalisa Octocat"
  },
  "emails": [
    {
      "value": "mona.octocat@okta.example.com",
      "primary": true
    },
    {
      "value": "monalisa@octocat.github.com"
    }
  ],
  "active": true,
  "meta": {
    "resourceType": "User",
    "created": "2017-03-09T16:11:13-05:00",
    "lastModified": "2017-03-09T16:11:13-05:00",
    "location": "https://api.github.com/scim/v2/organizations/octo-org/Users/edefdfedf-050c-11e7-8d32"
  }
}
```



---

