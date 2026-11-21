# Plugin OmniRoute para o Claude Code

Conecta o Claude Code a um gateway [OmniRoute](https://github.com/cheaper-inference/OmniRoute).

## O que tem dentro

| Parte | O que faz |
| --- | --- |
| `.mcp.json` | Registra o servidor MCP do OmniRoute (`/api/mcp/stream`, ~110 ferramentas) |
| `/omniroute:status` | Verifica a saúde do gateway e do MCP |
| `/omniroute:models [filtro]` | Lista os modelos disponíveis pelo gateway |
| `/omniroute:setup` | Configuração guiada (chave de API, MCP, roteamento opcional via `ANTHROPIC_BASE_URL`) |
| skill `omniroute` | Ensina o Claude quando e como usar as ferramentas MCP / linha de comando / API REST |

## Requisitos

- Node.js instalado
- OmniRoute rodando (`npm i -g omniroute && omniroute`)
- `omniroute mcp enable --transport streamable-http`
- Variáveis de ambiente: `OMNIROUTE_API_KEY` (obrigatória), `OMNIROUTE_URL` (opcional, padrão `http://localhost:20128`)

## Instalação

No Claude Code, execute:

```
/plugin marketplace add RyanMoura22/My-project
/plugin install omniroute@omniroute-local
```

Ou, para testar só numa sessão, clone o repositório e aponte para a pasta:

```
git clone https://github.com/RyanMoura22/My-project.git
claude --plugin-dir ./My-project
```
