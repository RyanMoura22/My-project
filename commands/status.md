---
description: Verifica se o gateway OmniRoute e o servidor MCP estão no ar
allowed-tools: Bash(curl:*), Bash(omniroute:*)
---

Verifique o gateway OmniRoute em `${OMNIROUTE_URL:-http://localhost:20128}` (use a variável de ambiente `OMNIROUTE_URL` se estiver definida).

1. Execute `curl -s -m 5 "$OMNIROUTE_URL/api/health"` (use `http://localhost:20128` se não estiver definida) e informe o resultado.
2. Se o comando `omniroute` estiver no PATH, execute também `omniroute mcp status` e `omniroute health`.
3. Se o servidor não responder, diga isso e sugira `npx omniroute` (ou `omniroute serve`) para iniciá-lo.
4. Se o MCP via HTTP estiver desativado, diga ao usuário para executar `omniroute mcp enable --transport streamable-http` e reiniciar o Claude Code.

Responda em português, em poucas linhas: gateway no ar/fora, MCP ativo/número de ferramentas, o que estiver falhando.
