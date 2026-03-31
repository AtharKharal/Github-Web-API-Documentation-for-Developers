# markdown API


## Render a Markdown document

<div class="api-method-banner">
  <span class="api-method method-post">POST</span> <span class="api-path">/markdown</span>
</div>

No description.




### Request Body

```json
{
  "text": "<string>",
  "mode": "markdown",
  "context": "<string>"
}
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/markdown \
      -d '{
      "text": "<string>",
      "mode": "markdown",
      "context": "<string>"
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
      "text": "<string>",
      "mode": "markdown",
      "context": "<string>"
    }

    response = requests.post('https://api.github.com/markdown', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('POST /markdown', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ...{
        "text": "<string>",
        "mode": "markdown",
        "context": "<string>"
      }
    });
    ```


### Response Example

```json

```



---


## Render a Markdown document in raw mode

<div class="api-method-banner">
  <span class="api-method method-post">POST</span> <span class="api-path">/markdown/raw</span>
</div>

You must send Markdown as plain text (using a `Content-Type` header of `text/plain` or `text/x-markdown`) to this endpoint, rather than using JSON format. In raw mode, [GitHub Flavored Markdown](https://github.github.com/gfm/) is not supported and Markdown will be rendered in plain format like a README.md file. Markdown content must be 400 KB or less.




### Request Body

```json
"<string>"
```



### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X POST \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/markdown/raw \
      -d '"<string>"'
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    import json

    data = "<string>"

    response = requests.post('https://api.github.com/markdown/raw', headers=headers, data=json.dumps(data))
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('POST /markdown/raw', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      },
      ..."<string>"
    });
    ```


### Response Example

```json
anim
```



---

