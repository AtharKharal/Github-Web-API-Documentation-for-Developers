# users API


## List events for the authenticated user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/events</span>
</div>

If you are authenticated as the given user, you will see your private events. Otherwise, you'll only see public events.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/events?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/events?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/events?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## List organization events for the authenticated user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/events/orgs/{org}</span>
</div>

This is the user's organization dashboard. You must be authenticated as the user to view this.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |
| `{org}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/events/orgs/{org}?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/events/orgs/{org}?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/events/orgs/{org}?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## List public events for a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/events/public</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/events/public?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/events/public?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/events/public?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## List the people a user follows

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/following</span>
</div>

Lists the people who the specified user follows.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/following?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/following?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/following?per_page=30&page=1', {
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


## Check if a user follows another user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/following/{target_user}</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{username}` | `string` | Yes | (Required)  | `<string>` |
| `{target_user}` | `string` | Yes | (Required) target_user parameter | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/following/{target_user}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/following/{target_user}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/following/{target_user}', {
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


## List events received by the authenticated user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/received_events</span>
</div>

These are events that you've received by watching repos and following users. If you are authenticated as the given user, you will see private events. Otherwise, you'll only see public events.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/received_events?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/received_events?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/received_events?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## List public events received by a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/received_events/public</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/received_events/public?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/received_events/public?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/received_events/public?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## Get GitHub Actions billing for a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/settings/billing/actions</span>
</div>

**Warning:** The Billing API is currently in public beta and subject to change.

Gets the summary of the free and paid GitHub Actions minutes used.

Paid minutes only apply to workflows in private repositories that use GitHub-hosted runners. Minutes used is listed for each GitHub-hosted runner operating system. Any job re-runs are also included in the usage. The usage does not include the multiplier for macOS and Windows runners and is not rounded up to the nearest whole minute. For more information, see "[Managing billing for GitHub Actions](https://help.github.com/github/setting-up-and-managing-billing-and-payments-on-github/managing-billing-for-github-actions)".

Access tokens must have the `user` scope.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/settings/billing/actions
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/settings/billing/actions', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/settings/billing/actions', {
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


## Get GitHub Packages billing for a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/settings/billing/packages</span>
</div>

**Warning:** The Billing API is currently in public beta and subject to change.

Gets the free and paid storage used for GitHub Packages in gigabytes.

Paid minutes only apply to packages stored for private repositories. For more information, see "[Managing billing for GitHub Packages](https://help.github.com/github/setting-up-and-managing-billing-and-payments-on-github/managing-billing-for-github-packages)."

Access tokens must have the `user` scope.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/settings/billing/packages
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/settings/billing/packages', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/settings/billing/packages', {
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


## Get shared storage billing for a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/settings/billing/shared-storage</span>
</div>

**Warning:** The Billing API is currently in public beta and subject to change.

Gets the estimated paid and estimated total storage used for GitHub Actions and Github Packages.

Paid minutes only apply to packages stored for private repositories. For more information, see "[Managing billing for GitHub Packages](https://help.github.com/github/setting-up-and-managing-billing-and-payments-on-github/managing-billing-for-github-packages)."

Access tokens must have the `user` scope.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/settings/billing/shared-storage
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/settings/billing/shared-storage', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/settings/billing/shared-storage', {
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


## Get a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}</span>
</div>

Provides publicly available information about someone with a GitHub account.

GitHub Apps with the `Plan` user permission can use this endpoint to retrieve information about a user's GitHub plan. The GitHub App must be authenticated as a user. See "[Identifying and authorizing users for GitHub Apps](https://developer.github.com/apps/building-github-apps/identifying-and-authorizing-users-for-github-apps/)" for details about authentication. For an example response, see "[Response with GitHub plan information](https://developer.github.com/v3/users/#response-with-github-plan-information)."

The `email` key in the following response is the publicly visible email address from your GitHub [profile page](https://github.com/settings/profile). When setting up your profile, you can select a primary email address to be “public” which provides an email entry for this endpoint. If you do not set a public email address for `email`, then it will have a value of `null`. You only see publicly visible email addresses when authenticated with GitHub. For more information, see [Authentication](https://developer.github.com/v3/#authentication).

The Emails API enables you to list all of your email addresses, and toggle a primary email to be visible publicly. For more information, see "[Emails API](https://developer.github.com/v3/users/emails/)".


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
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
  "site_admin": false,
  "name": "monalisa octocat",
  "company": "GitHub",
  "blog": "https://github.com/blog",
  "location": "San Francisco",
  "email": "octocat@github.com",
  "hireable": false,
  "bio": "There once was...",
  "twitter_username": "monatheoctocat",
  "public_repos": 2,
  "public_gists": 1,
  "followers": 20,
  "following": 0,
  "created_at": "2008-01-14T04:33:35Z",
  "updated_at": "2008-01-14T04:33:35Z"
}
```



---


## List followers of a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/followers</span>
</div>

Lists the people following the specified user.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/followers?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/followers?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/followers?per_page=30&page=1', {
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


## List gists for a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/gists</span>
</div>

Lists public gists for the specified user:


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `since` | `string` | Yes | Only show notifications updated after the given time. This is a timestamp in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format: `YYYY-MM-DDTHH:MM:SSZ`. | `<string>` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/gists?since=<string>&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/gists?since=<string>&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/gists?since=<string>&per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
[
  {
    "url": "https://api.github.com/gists/aa5a315d61ae9438b18d",
    "forks_url": "https://api.github.com/gists/aa5a315d61ae9438b18d/forks",
    "commits_url": "https://api.github.com/gists/aa5a315d61ae9438b18d/commits",
    "id": "aa5a315d61ae9438b18d",
    "node_id": "MDQ6R2lzdGFhNWEzMTVkNjFhZTk0MzhiMThk",
    "git_pull_url": "https://gist.github.com/aa5a315d61ae9438b18d.git",
    "git_push_url": "https://gist.github.com/aa5a315d61ae9438b18d.git",
    "html_url": "https://gist.github.com/aa5a315d61ae9438b18d",
    "files": {
      "hello_world.rb": {
        "filename": "hello_world.rb",
        "type": "application/x-ruby",
        "language": "Ruby",
        "raw_url": "https://gist.githubusercontent.com/octocat/6cad326836d38bd3a7ae/raw/db9c55113504e46fa076e7df3a04ce592e2e86d8/hello_world.rb",
        "size": 167
      }
    },
    "public": true,
    "created_at": "2010-04-14T02:15:15Z",
    "updated_at": "2011-06-20T11:34:15Z",
    "description": "Hello World Examples",
    "comments": 0,
    "user": null,
    "comments_url": "https://api.github.com/gists/aa5a315d61ae9438b18d/comments/",
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
    "truncated": false
  }
]
```



---


## List GPG keys for a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/gpg_keys</span>
</div>

Lists the GPG keys for a user. This information is accessible by anyone.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/gpg_keys?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/gpg_keys?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/gpg_keys?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
[
  {
    "id": 3,
    "primary_key_id": 2,
    "key_id": "3262EFF25BA0D270",
    "public_key": "xsBNBFayYZ...",
    "emails": [
      {
        "email": "mastahyeti@users.noreply.github.com",
        "verified": true
      }
    ],
    "subkeys": [
      {
        "id": 4,
        "primary_key_id": 3,
        "key_id": "4A595D4C72EE49C7",
        "public_key": "zsBNBFayYZ...",
        "emails": [],
        "subkeys": [],
        "can_sign": false,
        "can_encrypt_comms": true,
        "can_encrypt_storage": true,
        "can_certify": false,
        "created_at": "2016-03-24T11:31:04-06:00",
        "expires_at": "2016-03-24T11:31:04-07:00"
      }
    ],
    "can_sign": true,
    "can_encrypt_comms": false,
    "can_encrypt_storage": false,
    "can_certify": true,
    "created_at": "2016-03-24T11:31:04-06:00",
    "expires_at": "2016-03-24T11:31:04-07:00",
    "raw_key": "string"
  }
]
```



---


## Get contextual information for a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/hovercard</span>
</div>

Provides hovercard information when authenticated through basic auth or OAuth with the `repo` scope. You can find out more about someone in relation to their pull requests, issues, repositories, and organizations.

The `subject_type` and `subject_id` parameters provide context for the person's hovercard, which returns more information than without the parameters. For example, if you wanted to find out more about `octocat` who owns the `Spoon-Knife` repository via cURL, it would look like this:

```shell
 curl -u username:token
  https://api.github.com/users/octocat/hovercard?subject_type=repository&subject_id=1300192
```


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `subject_type` | `string` | Yes | Identifies which additional information you'd like to receive about the person's hovercard. Can be `organization`, `repository`, `issue`, `pull_request`. **Required** when using `subject_id`. | `<string>` |
| `subject_id` | `string` | Yes | Uses the ID for the `subject_type` you specified. **Required** when using `subject_type`. | `<string>` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/hovercard?subject_type=<string>&subject_id=<string>
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/hovercard?subject_type=<string>&subject_id=<string>', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/hovercard?subject_type=<string>&subject_id=<string>', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
{
  "contexts": [
    {
      "message": "Owns this repository",
      "octicon": "repo"
    }
  ]
}
```



---


## Get a user installation for the authenticated app

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/installation</span>
</div>

Enables an authenticated GitHub App to find the user’s installation information.

> [!IMPORTANT]
> You must use a [JWT](https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/#authenticating-as-a-github-app) to access this endpoint.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/installation
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/installation', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/installation', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

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



---


## List public keys for a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/keys</span>
</div>

Lists the _verified_ public SSH keys for a user. This is accessible by anyone.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/keys?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/keys?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/keys?per_page=30&page=1', {
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
    "key": "ssh-rsa AAA..."
  }
]
```



---


## List organizations for a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/orgs</span>
</div>

List [public organization memberships](https://help.github.com/articles/publicizing-or-concealing-organization-membership) for the specified user.

This method only lists _public_ memberships, regardless of authentication. If you need to fetch all of the organization memberships (public and private) for the authenticated user, use the [List organizations for the authenticated user](https://developer.github.com/v3/orgs/#list-organizations-for-the-authenticated-user) API instead.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/orgs?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/orgs?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/orgs?per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
[
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
    "description": "A great organization"
  }
]
```



---


## List user projects

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/projects</span>
</div>

No description.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `state` | `string` | Yes | Indicates the state of the projects to return. Can be either `open`, `closed`, or `all`. | `open` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/projects?state=open&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/projects?state=open&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/projects?state=open&per_page=30&page=1', {
      headers: {
        'X-GitHub-Api-Version': '2022-11-28'
      }
    });
    ```


### Response Example

```json
[
  {
    "owner_url": "https://api.github.com/users/octocat",
    "url": "https://api.github.com/projects/1002603",
    "html_url": "https://github.com/users/octocat/projects/1",
    "columns_url": "https://api.github.com/projects/1002603/columns",
    "id": 1002603,
    "node_id": "MDc6UHJvamVjdDEwMDI2MDM=",
    "name": "My Projects",
    "body": "A board to manage my personal projects.",
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
]
```



---


## List repositories for a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/repos</span>
</div>

Lists public repositories for the specified user.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `type` | `string` | Yes | Can be one of `all`, `owner`, `member`. | `owner` |
| `sort` | `string` | Yes | Can be one of `created`, `updated`, `pushed`, `full_name`. | `full_name` |
| `direction` | `string` | Yes | Can be one of `asc` or `desc`. Default: `asc` when using `full_name`, otherwise `desc` | `<string>` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/repos?type=owner&sort=full_name&direction=<string>&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/repos?type=owner&sort=full_name&direction=<string>&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/repos?type=owner&sort=full_name&direction=<string>&per_page=30&page=1', {
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


## List repositories starred by a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/starred</span>
</div>

Lists repositories a user has starred.

You can also find out _when_ stars were created by passing the following custom [media type](https://developer.github.com/v3/media/) via the `Accept` header:


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `sort` | `string` | Yes | One of `created` (when the repository was starred) or `updated` (when it was last pushed to). | `created` |
| `direction` | `string` | Yes | One of `asc` (ascending) or `desc` (descending). | `desc` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/starred?sort=created&direction=desc&per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/starred?sort=created&direction=desc&per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/starred?sort=created&direction=desc&per_page=30&page=1', {
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
```



---


## List repositories watched by a user

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users/{username}/subscriptions</span>
</div>

Lists repositories a user is watching.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |
| `page` | `string` | Yes | Page number of the results to fetch. | `1` |
| `{username}` | `string` | Yes | (Required)  | `<string>` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users/{username}/subscriptions?per_page=30&page=1
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users/{username}/subscriptions?per_page=30&page=1', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users/{username}/subscriptions?per_page=30&page=1', {
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


## List users

<div class="api-method-banner">
  <span class="api-method method-get">GET</span> <span class="api-path">/users</span>
</div>

Lists all users, in the order that they signed up on GitHub. This list includes personal user accounts and organization accounts.

Note: Pagination is powered exclusively by the `since` parameter. Use the [Link header](https://developer.github.com/v3/#link-header) to get the URL for the next page of users.


### Parameters

| Parameter | Type | Required | Description | Example |
| --- | --- | --- | --- | --- |
| `since` | `string` | Yes | Only show notifications updated after the given time. This is a timestamp in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format: `YYYY-MM-DDTHH:MM:SSZ`. | `<string>` |
| `per_page` | `string` | Yes | Results per page (max 100) | `30` |






### Request Examples

=== "cURL"

    ```bash
    curl -L \
      -X GET \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer <YOUR-TOKEN>" \
      https://api.github.com/users?since=<string>&per_page=30
    ```

=== "Python (Requests)"

    ```python
    import requests

    headers = {
      'Accept': 'application/vnd.github+json',
      'Authorization': 'Bearer <YOUR-TOKEN>'
    }

    response = requests.get('https://api.github.com/users?since=<string>&per_page=30', headers=headers)
    print(response.json())
    ```

=== "JavaScript (Octokit)"

    ```javascript
    const { Octokit } = require("@octokit/rest");
    const octokit = new Octokit({
      auth: 'YOUR-TOKEN'
    });

    await octokit.request('GET /users?since=<string>&per_page=30', {
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

