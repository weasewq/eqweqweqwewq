# Conectores e skills

Configuração das 5 ferramentas do vídeo ("5 GitHub essenciais") e do Graphify.

## 1. Conectores do claude.ai (você precisa fazer login)

Em **claude.ai → Settings → Connectors**, conecte:

| Ferramenta | Conector |
|---|---|
| HyperFrames (edição de vídeo) | **HyperFrames by HeyGen** |
| Google Workspace | **Gmail**, **Google Drive**, **Google Calendar**, **Google Docs**, **Google Sheets**, **Google Slides** |
| Apify (dados externos) | Adicione um conector personalizado com a URL `https://mcp.apify.com` (o login é por OAuth) |

Depois, ative cada um no menu de conectores do chat.

## 2. Claude Code (este repositório)

O `.mcp.json` já registra:

- **apify**: `https://mcp.apify.com` (OAuth; ou cabeçalho `Authorization: Bearer <APIFY_TOKEN>`)
- **playwright**: `npx -y @playwright/mcp@latest`

O Claude Code pede aprovação na primeira vez que usa cada servidor.

## 3. Skills (rode na sua máquina)

```bash
# HyperFrames: edição de vídeo em HTML
npx hyperframes skills update

# Playwright CLI: prova e teste no navegador
npm install -g @playwright/cli@latest
playwright-cli install --skills

# Agent Skills (Anthropic): o método
claude plugin marketplace add anthropics/skills

# Graphify: mapa do código em grafo de conhecimento
uv tool install graphifyy   # ou: pipx install graphifyy
graphify install
```

Depois, use no Claude Code: `/hyperframes`, `/graphify .`, `playwright-cli ...`.
