# Siglata MCP

Software para a sua IA: arquivos, planilhas e regras da empresa, com acesso por pessoa e histórico.

A Siglata é feita pela Siglata Tecnologia Ltda, de Franca (SP). Ela dá à sua IA (o ChatGPT, o Codex, o Claude Code ou qualquer agente compatível com MCP) os arquivos, as planilhas e as exportações do ERP da empresa. A sua IA consulta as células das planilhas, busca texto em PDF, Word e PowerPoint e salva as mudanças nas planilhas como uma nova edição do arquivo, mantendo a anterior. A Siglata lê as exportações do ERP e não se conecta ao ERP nem grava nada nele.

Este repositório guarda a página pública do servidor: o manifesto do registro e o guia de conexão. O servidor é hospedado pela Siglata e o código dele não está aqui.

## Conectar

| | |
| :-- | :-- |
| Endereço do servidor | `https://www.siglata.com/v1/mcp` |
| Transporte | Streamable HTTP |
| Autenticação | OAuth 2.0 com código de autorização e PKCE (S256); Client ID Metadata Documents ou registro dinâmico de cliente |
| Nome no registro | `com.siglata/mcp` |
| Versão | 3.0.1 |

Cole o endereço no seu cliente e entre quando ele abrir o navegador. Os passos e os escopos estão em [docs/oauth.md](docs/oauth.md); cada ferramenta está na [documentação](https://www.siglata.com/docs/agents/mcp).

- ChatGPT: [Conectar o ChatGPT](https://www.siglata.com/docs/agents/install/chatgpt)
- Codex: [Conectar o Codex](https://www.siglata.com/docs/agents/install/codex)
- Claude Code: [Conectar o Claude Code](https://www.siglata.com/docs/agents/install/claude-code)

## O que a sua IA recebe

Uma ferramenta por operação. Cada ferramenta tem um título e diz se só lê ou se altera algo. O `tools/list` mostra só as ferramentas que a sua autorização permite.

- Enviar, encontrar, ler, renomear, mover e mandar para a lixeira arquivos e pastas, e criar links de download de uso único.
- Consultar as células das planilhas com SQL e salvar as mudanças como uma nova edição do arquivo.
- Buscar e ler documentos em PDF, Word e PowerPoint.
- Guardar registros nas tabelas da empresa, com revisões e histórico.
- Convidar pessoas e gerenciar os papéis na organização.

A sua IA trabalha com o acesso da pessoa que entrou, e cada passo fica registrado. Cada conexão vale para uma organização e uma pessoa, e expira depois de 30 dias sem uso.

## Descoberta

- Server card: `https://www.siglata.com/.well-known/mcp/server-card.json`
- Metadados OAuth: `https://www.siglata.com/.well-known/oauth-authorization-server` e `/.well-known/oauth-protected-resource`

## Suporte e termos

- Documentação: https://www.siglata.com/docs/agents/mcp
- Suporte: https://www.siglata.com/contact
- Privacidade: https://www.siglata.com/privacy
- Termos: https://www.siglata.com/terms

Read in English: [README.md](README.md).
