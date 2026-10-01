# Fluxo de bug no Jira
**Estados:** Aberto → Em análise → Em correção → Pronto para teste → Em validação → Fechado (ou Reaberto)

**Campos obrigatórios do bug:** resumo claro, passos, resultado atual e esperado, ambiente, severidade, evidência (print, vídeo ou log).

**Severidade:** Crítica (sistema parado ou perda de dados), Alta (fluxo principal quebrado), Média (fluxo secundário ou com contorno), Baixa (cosmético).

## JQL úteis
```
project = APP AND issuetype = Bug AND status != Closed ORDER BY priority DESC
project = APP AND issuetype = Bug AND created >= -7d
project = APP AND status = "Pronto para teste" AND assignee = currentUser()
project = APP AND issuetype = Bug AND status = Reopened
```
**Métricas para acompanhar:** bugs abertos por severidade, taxa de reabertura, tempo médio de correção, bugs achados em produção vs. antes da release.
