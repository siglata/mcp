# OAuth setup

The Siglata MCP server at `https://www.siglata.com/v1/mcp` uses OAuth 2.0. An unauthenticated request answers `401` with a `WWW-Authenticate` header whose `resource_metadata` points to the protected-resource document. Clients that follow the MCP authorization flow need no manual setup.

## Metadata

| Document | URL |
| :-- | :-- |
| Protected resource | `https://www.siglata.com/.well-known/oauth-protected-resource` |
| Authorization server | `https://www.siglata.com/.well-known/oauth-authorization-server` |
| Issuer | `https://www.siglata.com/auth` |
| Authorization endpoint | `https://www.siglata.com/auth/oauth2/authorize` |
| Token endpoint | `https://www.siglata.com/auth/oauth2/token` |
| Registration endpoint | `https://www.siglata.com/auth/oauth2/register` |

## Client registration

- Client ID Metadata Document: use an https URL as `client_id`. The server advertises `client_id_metadata_document_supported`.
- Dynamic client registration: post to the registration endpoint.

Grant types are `authorization_code` and `refresh_token`. PKCE with `S256` is required. Public clients use `token_endpoint_auth_method: none`. The authorization response carries the issuer (RFC 9207). DPoP is optional.

## Scopes

`openid`, `profile`, `email`, `offline_access`, `organizations:read`, `organizations:write`, `members:read`, `members:write`, `files:read`, `files:write`.

`tools/list` shows only the tools the granted scopes allow.

## Sign-in and consent

1. Add `https://www.siglata.com/v1/mcp` to your client.
2. The client opens the browser. Sign in with an email magic link.
3. Choose the organization. Each grant is bound to exactly one organization.
4. Review the scopes and approve.

Each approval is an independent connection bound to you and that organization. It expires after 30 days without an MCP call, and each call renews the window. Browser logout does not end it. To use another organization, connect again and choose that organization.

## Clients

- ChatGPT: https://www.siglata.com/docs/en-US/agents/install/chatgpt
- Codex: https://www.siglata.com/docs/en-US/agents/install/codex
- Claude Code: https://www.siglata.com/docs/en-US/agents/install/claude-code

## Support

https://www.siglata.com/contact
