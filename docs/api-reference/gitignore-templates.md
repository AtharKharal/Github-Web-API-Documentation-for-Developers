# gitignore/templates API


=== "GET Get all gitignore templates"

    List all templates available to pass as an option when [creating a repository](https://developer.github.com/v3/repos/#create-a-repository-for-the-authenticated-user).

    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/gitignore/templates
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/gitignore/templates', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /gitignore/templates', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    [
      "Actionscript",
      "Android",
      "AppceleratorTitanium",
      "Autotools",
      "Bancha",
      "C",
      "C++"
    ]
    ```

    


=== "GET Get a gitignore template"

    The API also allows fetching the source of a single template.
    Use the raw [media type](https://developer.github.com/v3/media/) to get the raw contents.

    
    #### Parameters

    | Parameter | Type | Required | Description | Example |
    | --- | --- | --- | --- | --- |
    | `:name` | `string` | Yes | (Required) name parameter | `<string>` |
    
    

    

    
    #### Request Examples

    === "cURL"

        ```bash
        curl -L \
          -X GET \
          -H "Accept: application/vnd.github+json" \
          -H "Authorization: Bearer <YOUR-TOKEN>" \
          https://api.github.com/gitignore/templates/:name
        ```

    === "Python (Requests)"

        ```python
        import requests

        headers = {
          'Accept': 'application/vnd.github+json',
          'Authorization': 'Bearer <YOUR-TOKEN>'
        }

        response = requests.get('https://api.github.com/gitignore/templates/:name', headers=headers)
        print(response.json())
        ```

    === "JavaScript (Octokit)"

        ```javascript
        const { Octokit } = require("@octokit/rest");
        const octokit = new Octokit({
          auth: 'YOUR-TOKEN'
        });

        await octokit.request('GET /gitignore/templates/{name}', {
          headers: {
            'X-GitHub-Api-Version': '2022-11-28'
          }
        });
        ```
    

    #### Response Example
    
    ```json
    {
      "name": "C",
      "source": "# Object files\n*.o\n\n# Libraries\n*.lib\n*.a\n\n# Shared objects (inc. Windows DLLs)\n*.dll\n*.so\n*.so.*\n*.dylib\n\n# Executables\n*.exe\n*.out\n*.app\n"
    }
    ```

    

