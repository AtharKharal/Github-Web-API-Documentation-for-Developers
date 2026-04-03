# How-to: Manage GitHub Actions

This guide provides direct, recipe-based instructions for managing GitHub Actions artifacts, secrets, and self-hosted runners using the REST API. These tasks assume you have an active repository and a valid Personal Access Token (PAT).

## Prerequisites

- [Quick Start](../quickstart.md) complete.
- `workflow` and `actions:write` scopes granted to your PAT.

---

## 1. Create a Repository Secret

GitHub repository secrets must be encrypted using the `libsodium` library before submission.

1. **Get the Public Key**:
   `GET /repos/{owner}/{repo}/actions/secrets/public-key`
2. **Encrypt the Secret**:
   Use a library like `pynacl` (Python) or `libsodium.js` (Node) to encrypt the message using the key provided.
3. **Submit the Secret**:
   `PUT /repos/{owner}/{repo}/actions/secrets/{secret_name}`

```bash
curl -L \
  -X PUT \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer $GITHUB_TOKEN" \
  https://api.github.com/repos/OWNER/REPO/actions/secrets/MY_SECRET \
  -d '{"encrypted_value":"ENCRYPTED_STRING","key_id":"KEY_ID"}'
```

---

## 2. Trigger a Workflow Dispatch

Trigger a manual workflow execution using the `workflow_dispatch` event.

```python
import requests

def trigger_workflow(owner, repo, workflow_id, inputs, token):
    url = f"https://api.github.com/repos/{owner}/{repo}/actions/workflows/{workflow_id}/dispatches"
    headers = {"Authorization": f"Bearer {token}", "Accept": "application/vnd.github+json"}
    data = {"ref": "main", "inputs": inputs}
    return requests.post(url, headers=headers, json=data)
```

---

## 3. Register a Self-Hosted Runner

To automate CI/CD on your own infrastructure, generate a registration token to link a machine to your repository.

```bash
curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer $GITHUB_TOKEN" \
  https://api.github.com/repos/OWNER/REPO/actions/runners/registration-token
```

> [!CAUTION]
> The registration token expires after 60 minutes. It must be generated immediately before configuring the runner on the destination machine.

---

## Next Steps

- [Security Hardening](../tutorials/security-hardening.md)
- [API Reference: Actions](../api-reference/repos.md)
