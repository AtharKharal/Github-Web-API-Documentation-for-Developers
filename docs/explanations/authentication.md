# Authentication

This page explains how the GitHub REST API authenticates requests, what credential types exist, how scopes determine access, and what the API returns when authentication fails or is insufficient.

---

## Authentication Methods

The GitHub REST API supports three authentication mechanisms, each suited to a different integration context.

### Personal Access Token (PAT)

A PAT is a string that substitutes for a user password. It is passed via the `Authorization` header:

```http
Authorization: Bearer ghp_your_token_here
```

Two PAT subtypes exist:

| Subtype | Prefix | Scope Model | Recommended Use |
| --- | --- | --- | --- |
| Classic | `ghp_` | Broad category-level scopes | Legacy integrations |
| Fine-grained | `github_pat_` | Repository- and permission-level grants | All new integrations |

Fine-grained PATs allow you to limit a token to specific repositories and specific permissions (e.g., read-only access to `issues` on one repository), reducing the blast radius of a compromised token.

### GitHub App Installation Token

GitHub Apps authenticate in two stages:

1. The App authenticates as itself using a **JSON Web Token (JWT)** signed with its private key:

    ```http
    Authorization: Bearer {jwt}
    ```

    The JWT is short-lived (maximum 10 minutes) and can only call App-level endpoints (e.g., `GET /app`).

2. The App obtains an **installation access token** by calling `POST /app/installations/{installation_id}/access_tokens`. This token is then used for all resource operations:

    ```http
    Authorization: Bearer {installation_access_token}
    ```

    Installation tokens expire after 1 hour.

!!! note
    GitHub Apps are the recommended mechanism for integrations that act on behalf of an organization or across many repositories. They have higher rate limits than PATs and do not depend on a specific user's account.

### OAuth App Token

OAuth Apps implement the standard authorization code flow. The resulting token is passed identically to a PAT:

```http
Authorization: Bearer gho_your_oauth_token
```

OAuth App tokens have the same rate limits as PATs and inherit the scopes granted during the authorization flow.

---

## Token Scopes

Scopes define what a token is permitted to do. They are set at token creation and cannot be expanded without reauthorization.

| Scope | Grants |
| --- | --- |
| `repo` | Full read/write access to public and private repositories |
| `public_repo` | Read/write access to public repositories only |
| `read:org` | Read-only access to org membership and team membership |
| `admin:org` | Full administrative access to organization settings |
| `delete_repo` | Permission to delete repositories (additive to `repo`) |
| `read:user` | Read access to profile data |
| `user:email` | Read access to primary email address |
| `gist` | Create and modify Gists |
| `notifications` | Read access to notifications |

!!! warning
    The `repo` scope grants **full read and write access to all repositories**, including private ones. Always grant the minimum scope required by the integration.

---

## How Authentication Affects Rate Limits

| Authentication State | Requests per Hour |
| --- | --- |
| Unauthenticated | 60 |
| Authenticated (PAT or OAuth) | 5,000 |
| GitHub App installation token | Up to 15,000 (scales with org size) |

The current limit state is always reflected in response headers:

```http
X-RateLimit-Limit: 5000
X-RateLimit-Remaining: 4987
X-RateLimit-Used: 13
X-RateLimit-Reset: 1711929600
```

See [Rate Limiting](rate-limiting.md) for full header semantics and secondary limits.

---

## Authentication Failure Responses

| HTTP Status | Cause | Resolution |
| --- | --- | --- |
| `401 Unauthorized` | Missing or malformed `Authorization` header | Provide a valid `Bearer {token}` header |
| `403 Forbidden` | Token is valid but lacks required scope | Regenerate token with the required scope |
| `403 Forbidden` | Rate limit exhausted | Wait for `X-RateLimit-Reset` timestamp |
| `404 Not Found` | Resource exists but token lacks read access | Grant `repo` scope or ensure repo visibility |

!!! note
    GitHub returns `404 Not Found` (not `403`) for private resources when the token lacks read access. This is intentional — it prevents disclosure of whether a private resource exists.

---

## Best Practices

- Store tokens in environment variables, never in source code.
- Rotate tokens on a schedule; use expiring tokens where supported.
- Use fine-grained PATs scoped to the minimum required repository set.
- For server-to-server integrations acting on behalf of an organization, use a GitHub App rather than a PAT tied to an individual user account.
- Validate token scopes programmatically via `GET /rate_limit` — the response includes scope information in the `X-OAuth-Scopes` header for OAuth tokens.

---

## References

- [Quick Start](../quickstart.md)
- [Apps API Reference](../api-reference/app.md)
- [Rate Limiting](rate-limiting.md)
