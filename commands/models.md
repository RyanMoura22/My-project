---
description: Lista os modelos disponíveis pelo OmniRoute
argument-hint: "[filtro]"
allowed-tools: Bash(curl:*)
---

Liste os modelos expostos pelo endpoint compatível com OpenAI do OmniRoute.

Execute `curl -s -m 10 "${OMNIROUTE_URL:-http://localhost:20128}/v1/models" -H "Authorization: Bearer $OMNIROUTE_API_KEY"` e resuma os ids dos modelos agrupados pelo prefixo do provedor (a parte antes da `/`).

Se o usuário passou um filtro (`$ARGUMENTS`), mostre só os ids que o contêm. Nunca mostre a chave de API. Responda em português.
