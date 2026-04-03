# Tutorial: Security Hardening

This tutorial guides you through identifying, auditing, and remediating security alerts across your GitHub repositories using the REST API. You will build a workflow that identifies open Dependabot alerts and triggers a repository-wide security scan.

## Learning Objectives

- Authenticate with `security-events` and `repo` scopes.
- Navigate the `secret-scanning` and `dependabot` API namespaces.
- Automate remediation by enabling branch protection for critical alerts.

---

## Step 1: List Dependabot Alerts

The first step is to identify vulnerabilities in your repository's dependencies.

=== "cURL"

    ```bash
    curl -L \
      -H "Accept: application/vnd.github+json" \
      -H "Authorization: Bearer $GITHUB_TOKEN" \
      -H "X-GitHub-Api-Version: 2022-11-28" \
      https://api.github.com/repos/OWNER/REPO/dependabot/alerts
    ```

=== "Python"

    ```python
    import requests

    def get_security_alerts(owner, repo, token):
        url = f"https://api.github.com/repos/{owner}/{repo}/dependabot/alerts"
        headers = {"Authorization": f"Bearer {token}", "Accept": "application/vnd.github+json"}
        return requests.get(url, headers=headers).json()
    ```

---

## Step 2: Audit Secret Scanning

Identify if any cryptographic keys or tokens have been accidentally committed to the repository history.

```javascript
const { data } = await octokit.request("GET /repos/{owner}/{repo}/secret-scanning/alerts", {
  owner: "octocat",
  repo: "Hello-World",
  state: "open",
});
```

> [!TIP]
> Use the `resolution` field to filter for "false_positive" vs "revoked" alerts to prioritize your remediation effort.

---

## Step 3: Enforce Branch Protection

To prevent further security regressions, enable branch protection on the `main` branch to require a pull request review before merging.

```bash
curl -L \
  -X PUT \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer $GITHUB_TOKEN" \
  https://api.github.com/repos/OWNER/REPO/branches/main/protection \
  -d '{"required_status_checks":null,"enforce_admins":true,"required_pull_request_reviews":{"dismissal_restrictions":{},"dismiss_stale_reviews":true,"require_code_owner_reviews":true,"required_approving_review_count":2},"restrictions":null}'
```

---

## Conclusion

You have successfully:
1. Audited dependency vulnerabilities.
2. Verified secret scanning status.
3. Implemented a preventive build gate via branch protection.

See the [Security API Reference](../api-reference/repos.md) for a full list of related endpoints.
