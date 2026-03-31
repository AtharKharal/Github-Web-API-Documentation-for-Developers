# marketplace listing API


## List plans

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/marketplace_listing/plans</span>
</div>

Lists all plans that are part of your GitHub Marketplace listing.

GitHub Apps must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint. OAuth Apps must use [basic authentication](https://developer.github.com/v3/auth/#basic-authentication) with their client ID and client secret to access this endpoint.


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
      https://api.github.com/marketplace_listing/plans?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/marketplace_listing/plans?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /marketplace_listing/plans?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
[
  {
    "url": "https://api.github.com/marketplace_listing/plans/1313",
    "accounts_url": "https://api.github.com/marketplace_listing/plans/1313/accounts",
    "id": 1313,
    "number": 3,
    "name": "Pro",
    "description": "A professional-grade CI solution",
    "monthly_price_in_cents": 1099,
    "yearly_price_in_cents": 11870,
    "price_model": "flat-rate",
    "has_free_trial": true,
    "unit_name": null,
    "state": "published",
    "bullets": [
      "Up to 25 private repositories",
      "11 concurrent builds"
    ]
  }
]
```



---


## List accounts for a plan

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/marketplace_listing/plans/{plan_id}/accounts</span>
</div>

Returns user and organization accounts associated with the specified plan, including free plans. For per-seat pricing, you see the list of accounts that have purchased the plan, including the number of seats purchased. When someone submits a plan change that won't be processed until the end of their billing cycle, you will also see the upcoming pending change.

GitHub Apps must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint. OAuth Apps must use [basic authentication](https://developer.github.com/v3/auth/#basic-authentication) with their client ID and client secret to access this endpoint.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `sort` | `string` | Yes | One of `created` (when the repository was starred) or `updated` (when it was last pushed to). | `created` |
| `direction` | `string` | Yes | To return the oldest accounts first, set to `asc`. Can be one of `asc` or `desc`. Ignored without the `sort` parameter. | `<string>` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{plan_id}` | `string` | Yes | (Required) plan_id parameter | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/marketplace_listing/plans/{plan_id}/accounts?sort=created&direction=<string>&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/marketplace_listing/plans/{plan_id}/accounts?sort=created&direction=<string>&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /marketplace_listing/plans/{plan_id}/accounts?sort=created&direction=<string>&per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
[
  {
    "url": "https://api.github.com/orgs/github",
    "type": "Organization",
    "id": 4,
    "login": "github",
    "organization_billing_email": "billing@github.com",
    "marketplace_pending_change": {
      "effective_date": "2017-11-11T00:00:00Z",
      "unit_count": null,
      "id": 77,
      "plan": {
        "url": "https://api.github.com/marketplace_listing/plans/1111",
        "accounts_url": "https://api.github.com/marketplace_listing/plans/1111/accounts",
        "id": 1111,
        "number": 2,
        "name": "Startup",
        "description": "A professional-grade CI solution",
        "monthly_price_in_cents": 699,
        "yearly_price_in_cents": 7870,
        "price_model": "flat-rate",
        "has_free_trial": true,
        "state": "published",
        "unit_name": null,
        "bullets": [
          "Up to 10 private repositories",
          "3 concurrent builds"
        ]
      }
    },
    "marketplace_purchase": {
      "billing_cycle": "monthly",
      "next_billing_date": "2017-11-11T00:00:00Z",
      "unit_count": null,
      "on_free_trial": true,
      "free_trial_ends_on": "2017-11-11T00:00:00Z",
      "updated_at": "2017-11-02T01:12:12Z",
      "plan": {
        "url": "https://api.github.com/marketplace_listing/plans/1313",
        "accounts_url": "https://api.github.com/marketplace_listing/plans/1313/accounts",
        "id": 1313,
        "number": 3,
        "name": "Pro",
        "description": "A professional-grade CI solution",
        "monthly_price_in_cents": 1099,
        "yearly_price_in_cents": 11870,
        "price_model": "flat-rate",
        "has_free_trial": true,
        "unit_name": null,
        "state": "published",
        "bullets": [
          "Up to 25 private repositories",
          "11 concurrent builds"
        ]
      }
    }
  }
]
```



---


## List plans (stubbed)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/marketplace_listing/stubbed/plans</span>
</div>

Lists all plans that are part of your GitHub Marketplace listing.

GitHub Apps must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint. OAuth Apps must use [basic authentication](https://developer.github.com/v3/auth/#basic-authentication) with their client ID and client secret to access this endpoint.


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
      https://api.github.com/marketplace_listing/stubbed/plans?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/marketplace_listing/stubbed/plans?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /marketplace_listing/stubbed/plans?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
[
  {
    "url": "https://api.github.com/marketplace_listing/plans/1313",
    "accounts_url": "https://api.github.com/marketplace_listing/plans/1313/accounts",
    "id": 1313,
    "number": 3,
    "name": "Pro",
    "description": "A professional-grade CI solution",
    "monthly_price_in_cents": 1099,
    "yearly_price_in_cents": 11870,
    "price_model": "flat-rate",
    "has_free_trial": true,
    "unit_name": null,
    "state": "published",
    "bullets": [
      "Up to 25 private repositories",
      "11 concurrent builds"
    ]
  }
]
```



---


## List accounts for a plan (stubbed)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/marketplace_listing/stubbed/plans/{plan_id}/accounts</span>
</div>

Returns repository and organization accounts associated with the specified plan, including free plans. For per-seat pricing, you see the list of accounts that have purchased the plan, including the number of seats purchased. When someone submits a plan change that won't be processed until the end of their billing cycle, you will also see the upcoming pending change.

GitHub Apps must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint. OAuth Apps must use [basic authentication](https://developer.github.com/v3/auth/#basic-authentication) with their client ID and client secret to access this endpoint.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `sort` | `string` | Yes | One of `created` (when the repository was starred) or `updated` (when it was last pushed to). | `created` |
| `direction` | `string` | Yes | To return the oldest accounts first, set to `asc`. Can be one of `asc` or `desc`. Ignored without the `sort` parameter. | `<string>` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{plan_id}` | `string` | Yes | (Required) plan_id parameter | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/marketplace_listing/stubbed/plans/{plan_id}/accounts?sort=created&direction=<string>&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/marketplace_listing/stubbed/plans/{plan_id}/accounts?sort=created&direction=<string>&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /marketplace_listing/stubbed/plans/{plan_id}/accounts?sort=created&direction=<string>&per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
[
  {
    "url": "https://api.github.com/orgs/github",
    "type": "Organization",
    "id": 4,
    "login": "github",
    "organization_billing_email": "billing@github.com",
    "marketplace_pending_change": {
      "effective_date": "2017-11-11T00:00:00Z",
      "unit_count": null,
      "id": 77,
      "plan": {
        "url": "https://api.github.com/marketplace_listing/plans/1111",
        "accounts_url": "https://api.github.com/marketplace_listing/plans/1111/accounts",
        "id": 1111,
        "number": 2,
        "name": "Startup",
        "description": "A professional-grade CI solution",
        "monthly_price_in_cents": 699,
        "yearly_price_in_cents": 7870,
        "price_model": "flat-rate",
        "has_free_trial": true,
        "state": "published",
        "unit_name": null,
        "bullets": [
          "Up to 10 private repositories",
          "3 concurrent builds"
        ]
      }
    },
    "marketplace_purchase": {
      "billing_cycle": "monthly",
      "next_billing_date": "2017-11-11T00:00:00Z",
      "unit_count": null,
      "on_free_trial": true,
      "free_trial_ends_on": "2017-11-11T00:00:00Z",
      "updated_at": "2017-11-02T01:12:12Z",
      "plan": {
        "url": "https://api.github.com/marketplace_listing/plans/1313",
        "accounts_url": "https://api.github.com/marketplace_listing/plans/1313/accounts",
        "id": 1313,
        "number": 3,
        "name": "Pro",
        "description": "A professional-grade CI solution",
        "monthly_price_in_cents": 1099,
        "yearly_price_in_cents": 11870,
        "price_model": "flat-rate",
        "has_free_trial": true,
        "unit_name": null,
        "state": "published",
        "bullets": [
          "Up to 25 private repositories",
          "11 concurrent builds"
        ]
      }
    }
  }
]
```



---


## Get a subscription plan for an account (stubbed)

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/marketplace_listing/stubbed/accounts/{account_id}</span>
</div>

Shows whether the user or organization account actively subscribes to a plan listed by the authenticated GitHub App. When someone submits a plan change that won't be processed until the end of their billing cycle, you will also see the upcoming pending change.

GitHub Apps must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint. OAuth Apps must use [basic authentication](https://developer.github.com/v3/auth/#basic-authentication) with their client ID and client secret to access this endpoint.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{account_id}` | `string` | Yes | (Required) account_id parameter | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/marketplace_listing/stubbed/accounts/{account_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/marketplace_listing/stubbed/accounts/{account_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /marketplace_listing/stubbed/accounts/{account_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "url": "https://api.github.com/orgs/github",
  "type": "Organization",
  "id": 4,
  "login": "github",
  "organization_billing_email": "billing@github.com",
  "marketplace_pending_change": {
    "effective_date": "2017-11-11T00:00:00Z",
    "unit_count": null,
    "id": 77,
    "plan": {
      "url": "https://api.github.com/marketplace_listing/plans/1111",
      "accounts_url": "https://api.github.com/marketplace_listing/plans/1111/accounts",
      "id": 1111,
      "number": 2,
      "name": "Startup",
      "description": "A professional-grade CI solution",
      "monthly_price_in_cents": 699,
      "yearly_price_in_cents": 7870,
      "price_model": "flat-rate",
      "has_free_trial": true,
      "state": "published",
      "unit_name": null,
      "bullets": [
        "Up to 10 private repositories",
        "3 concurrent builds"
      ]
    }
  },
  "marketplace_purchase": {
    "billing_cycle": "monthly",
    "next_billing_date": "2017-11-11T00:00:00Z",
    "unit_count": null,
    "on_free_trial": true,
    "free_trial_ends_on": "2017-11-11T00:00:00Z",
    "updated_at": "2017-11-02T01:12:12Z",
    "plan": {
      "url": "https://api.github.com/marketplace_listing/plans/1313",
      "accounts_url": "https://api.github.com/marketplace_listing/plans/1313/accounts",
      "id": 1313,
      "number": 3,
      "name": "Pro",
      "description": "A professional-grade CI solution",
      "monthly_price_in_cents": 1099,
      "yearly_price_in_cents": 11870,
      "price_model": "flat-rate",
      "has_free_trial": true,
      "unit_name": null,
      "state": "published",
      "bullets": [
        "Up to 25 private repositories",
        "11 concurrent builds"
      ]
    }
  }
}
```



---


## Get a subscription plan for an account

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/marketplace_listing/accounts/{account_id}</span>
</div>

Shows whether the user or organization account actively subscribes to a plan listed by the authenticated GitHub App. When someone submits a plan change that won't be processed until the end of their billing cycle, you will also see the upcoming pending change.

GitHub Apps must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint. OAuth Apps must use [basic authentication](https://developer.github.com/v3/auth/#basic-authentication) with their client ID and client secret to access this endpoint.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{account_id}` | `string` | Yes | (Required) account_id parameter | `<integer>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/marketplace_listing/accounts/{account_id}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/marketplace_listing/accounts/{account_id}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /marketplace_listing/accounts/{account_id}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "url": "https://api.github.com/orgs/github",
  "type": "Organization",
  "id": 4,
  "login": "github",
  "organization_billing_email": "billing@github.com",
  "marketplace_pending_change": {
    "effective_date": "2017-11-11T00:00:00Z",
    "unit_count": null,
    "id": 77,
    "plan": {
      "url": "https://api.github.com/marketplace_listing/plans/1111",
      "accounts_url": "https://api.github.com/marketplace_listing/plans/1111/accounts",
      "id": 1111,
      "number": 2,
      "name": "Startup",
      "description": "A professional-grade CI solution",
      "monthly_price_in_cents": 699,
      "yearly_price_in_cents": 7870,
      "price_model": "flat-rate",
      "has_free_trial": true,
      "state": "published",
      "unit_name": null,
      "bullets": [
        "Up to 10 private repositories",
        "3 concurrent builds"
      ]
    }
  },
  "marketplace_purchase": {
    "billing_cycle": "monthly",
    "next_billing_date": "2017-11-11T00:00:00Z",
    "unit_count": null,
    "on_free_trial": true,
    "free_trial_ends_on": "2017-11-11T00:00:00Z",
    "updated_at": "2017-11-02T01:12:12Z",
    "plan": {
      "url": "https://api.github.com/marketplace_listing/plans/1313",
      "accounts_url": "https://api.github.com/marketplace_listing/plans/1313/accounts",
      "id": 1313,
      "number": 3,
      "name": "Pro",
      "description": "A professional-grade CI solution",
      "monthly_price_in_cents": 1099,
      "yearly_price_in_cents": 11870,
      "price_model": "flat-rate",
      "has_free_trial": true,
      "unit_name": null,
      "state": "published",
      "bullets": [
        "Up to 25 private repositories",
        "11 concurrent builds"
      ]
    }
  }
}
```



---

