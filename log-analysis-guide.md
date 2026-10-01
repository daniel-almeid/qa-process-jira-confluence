# Guia de análise de logs para QA
**Quando usar:** ao investigar uma falha que a tela não explica.

1. Anote o horário exato do erro e o ID da requisição ou do usuário.
2. Filtre o log por esse ID ou janela de tempo.
3. Procure o primeiro `ERROR` ou `WARN`, pois os seguintes costumam ser consequência.
4. Identifique o tipo: validação (4xx), falha do servidor (5xx), timeout, dependência externa.
5. Anexe ao bug o trecho relevante, sem dados pessoais ou credenciais.

```bash
grep -n "ERROR" app.log | tail -20
grep "req-id=abc123" app.log
```
**Dica:** compare com um log de execução bem-sucedida do mesmo fluxo para ver onde o caminho diverge.
