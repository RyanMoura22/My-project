---
name: omniroute
description: Opera um gateway de IA OmniRoute — verificar saúde, listar provedores e modelos, gerenciar combos/roteamento, compressão, cache e uso — pelas ferramentas MCP do omniroute, pelo comando `omniroute` ou pela API REST. Use quando o usuário mencionar OmniRoute, o gateway local na porta 20128, fallback entre provedores, combos, ou uso de tokens/custos entre provedores.
---

# OmniRoute

O OmniRoute é um gateway de IA auto-hospedado: um único endpoint compatível com OpenAI/Anthropic (`http://localhost:20128/v1` por padrão) que roteia para vários provedores com fallback, compressão e controle de uso.

Responda ao usuário em português.

## Escolha a interface

1. **Ferramentas MCP (preferido)** — este plugin registra um servidor MCP `omniroute` em `$OMNIROUTE_URL/api/mcp/stream` usando `OMNIROUTE_API_KEY`. Se as ferramentas estiverem disponíveis, use-as para provedores, combos, roteamento, cache, compressão, memória e auditoria.
2. **Linha de comando** — se `omniroute` estiver no PATH: `omniroute health`, `omniroute providers list`, `omniroute combo list`, `omniroute models`, `omniroute usage`, `omniroute mcp status`, `omniroute doctor`.
3. **REST** — `curl $OMNIROUTE_URL/api/health`, `curl $OMNIROUTE_URL/v1/models -H "Authorization: Bearer $OMNIROUTE_API_KEY"`.

## Solução de problemas

- Ferramentas MCP ausentes → o transporte HTTP vem desativado: `omniroute mcp enable --transport streamable-http` e reinicie o Claude Code.
- Erros 401 → `OMNIROUTE_API_KEY` não definida ou sem o escopo necessário.
- Conexão recusada → o servidor não está rodando; inicie com `omniroute` (ou `npx omniroute`).

## Regras

- Nunca mostre chaves de API ou credenciais de provedores ao usuário nem as grave em arquivos.
- Pergunte antes de mudanças que afetam o roteamento de todos (apagar provedores/combos, mudar a estratégia padrão, limpar caches).
