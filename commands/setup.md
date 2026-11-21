---
description: Guia para conectar o Claude Code ao OmniRoute e ativar as ferramentas MCP
---

Ajude o usuário a conectar o Claude Code ao OmniRoute. Explique em português e ofereça-se para fazer cada passo:

1. **Instalar / iniciar o OmniRoute**: `npm install -g omniroute` e depois `omniroute` (painel em http://localhost:20128).
2. **Criar uma chave de API** no painel (com escopo de gerenciamento, se quiser que as ferramentas MCP alterem configurações).
3. **Ativar o MCP via HTTP**: `omniroute mcp enable --transport streamable-http`.
4. **Definir as variáveis de ambiente do servidor MCP deste plugin** (no perfil do shell ou em `~/.claude/settings.json`, na seção `env`):
   - `OMNIROUTE_URL` (opcional, padrão `http://localhost:20128`)
   - `OMNIROUTE_API_KEY` — a chave do passo 2
5. **Opcional — enviar o tráfego de modelo do próprio Claude Code pelo OmniRoute**: execute `omniroute launch`, ou defina `ANTHROPIC_BASE_URL` com a raiz do gateway (sem `/v1` no final) e `ANTHROPIC_AUTH_TOKEN` com a chave de API. `omniroute setup-claude` cria perfis por modelo.
6. Reinicie o Claude Code (as variáveis de ambiente são lidas na inicialização) e execute `/omniroute:status`.

Nunca grave a chave de API do usuário em um arquivo que vá para o git.
