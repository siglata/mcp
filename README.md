# Siglata MCP

Software for your AI: company files, spreadsheets and rules, with per-person access and history.

Siglata is made by Siglata Tecnologia Ltda, based in Franca, Brazil. It gives your AI (ChatGPT, Codex, Claude Code or any MCP-compatible agent) the company's files, spreadsheets and ERP exports. Your AI queries workbook cells, searches PDF, Word and PowerPoint text, and saves spreadsheet changes as a new edition of the file, keeping the previous one.

This repository holds the public listing for the server: the registry manifest and the setup guide. The server itself is hosted by Siglata and its code is not published here.

## Connect

|  |  |
| :-- | :-- |
| Server URL | `https://www.siglata.com/v1/mcp` |
| Transport | Streamable HTTP |
| Authentication | OAuth 2.0 authorization code with PKCE (S256); Client ID Metadata Documents or dynamic client registration |
| Registry name | `com.siglata/mcp` |
| Version | 3.0.1 |

Add the URL to your client and sign in when it opens the browser. See [docs/oauth.md](docs/oauth.md) for the steps and the scopes, and the [documentation](https://www.siglata.com/docs/agents/mcp) for every tool.

- ChatGPT: [Connect ChatGPT](https://www.siglata.com/docs/en-US/agents/install/chatgpt)
- Codex: [Connect Codex](https://www.siglata.com/docs/en-US/agents/install/codex)
- Claude Code: [Connect Claude Code](https://www.siglata.com/docs/en-US/agents/install/claude-code)

## What the agent gets

One tool per operation. Each tool has a title and says whether it only reads or changes something. `tools/list` shows only the tools your grant may call.

- Upload, find, read, rename, move and trash files and folders, and create one-time download links.
- Query workbook cells with SQL and save changes as a new edition of the file.
- Search and read PDF, Word and PowerPoint documents.
- Keep records in the company's tables, with revisions and history.
- Invite people and manage roles in the organization.

Your AI works with the access of the person who signed in, and every step is recorded.

Each connection is bound to one organization and one person. It expires after 30 days without a call.

## Discovery

- Server card: `https://www.siglata.com/.well-known/mcp/server-card.json`
- OAuth metadata: `https://www.siglata.com/.well-known/oauth-authorization-server` and `/.well-known/oauth-protected-resource`

## Support and legal

- Documentation: https://www.siglata.com/docs/agents/mcp
- Support: https://www.siglata.com/contact
- Privacy: https://www.siglata.com/privacy
- Terms: https://www.siglata.com/terms

Leia em português: [README.pt-BR.md](README.pt-BR.md).
