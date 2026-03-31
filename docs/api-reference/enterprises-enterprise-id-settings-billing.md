# enterprises/{enterprise id}/settings/billing API


## Get GitHub Actions billing for an enterprise

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/enterprises/{enterprise_id}/settings/billing/actions</span>
</div>

**Warning:** The Billing API is currently in public beta and subject to change.

Gets the summary of the free and paid GitHub Actions minutes used.

Paid minutes only apply to workflows in private repositories that use GitHub-hosted runners. Minutes used is listed for each GitHub-hosted runner operating system. Any job re-runs are also included in the usage. The usage does not include the multiplier for macOS and Windows runners and is not rounded up to the nearest whole minute. For more information, see "[Managing billing for GitHub Actions](https://help.github.com/github/setting-up-and-managing-billing-and-payments-on-github/managing-billing-for-github-actions)".

The authenticated user must be an enterprise admin.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{enterprise_id}` | `string` | Yes | (Required) Unique identifier of the GitHub Enterprise Cloud instance. | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/enterprises/{enterprise_id}/settings/billing/actions
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/enterprises/{enterprise_id}/settings/billing/actions', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /enterprises/{enterprise_id}/settings/billing/actions', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Get GitHub Packages billing for an enterprise

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/enterprises/{enterprise_id}/settings/billing/packages</span>
</div>

**Warning:** The Billing API is currently in public beta and subject to change.

Gets the free and paid storage used for GitHub Packages in gigabytes.

Paid minutes only apply to packages stored for private repositories. For more information, see "[Managing billing for GitHub Packages](https://help.github.com/github/setting-up-and-managing-billing-and-payments-on-github/managing-billing-for-github-packages)."

The authenticated user must be an enterprise admin.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{enterprise_id}` | `string` | Yes | (Required) Unique identifier of the GitHub Enterprise Cloud instance. | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/enterprises/{enterprise_id}/settings/billing/packages
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/enterprises/{enterprise_id}/settings/billing/packages', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /enterprises/{enterprise_id}/settings/billing/packages', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "total_gigabytes_bandwidth_used": 50,
  "total_paid_gigabytes_bandwidth_used": 40,
  "included_gigabytes_bandwidth": 10
}
```



---


## Get shared storage billing for an enterprise

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/enterprises/{enterprise_id}/settings/billing/shared-storage</span>
</div>

**Warning:** The Billing API is currently in public beta and subject to change.

Gets the estimated paid and estimated total storage used for GitHub Actions and Github Packages.

Paid minutes only apply to packages stored for private repositories. For more information, see "[Managing billing for GitHub Packages](https://help.github.com/github/setting-up-and-managing-billing-and-payments-on-github/managing-billing-for-github-packages)."

The authenticated user must be an enterprise admin.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{enterprise_id}` | `string` | Yes | (Required) Unique identifier of the GitHub Enterprise Cloud instance. | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/enterprises/{enterprise_id}/settings/billing/shared-storage
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/enterprises/{enterprise_id}/settings/billing/shared-storage', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /enterprises/{enterprise_id}/settings/billing/shared-storage', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "days_left_in_billing_cycle": 20,
  "estimated_paid_storage_for_month": 15,
  "estimated_storage_for_month": 40
}
```



---

