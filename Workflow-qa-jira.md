# Workflow de QA no Jira

Este documento descreve o fluxo de trabalho sugerido para o time de QA utilizando o Jira, incluindo os status e transições.

## 1. Estados principais da issue

| Status | Descrição | Categoria |
|--------|-----------|-----------|
|To Do / Backlog|Item recém-criado, aguardando priorização.|Tarefas Pendentes|
|In Progress|Desenvolvedores estão trabalhando na implementação.|Em Andamento|
|Code Review|Aguardando revisão de código.|Em Andamento|
|Ready for QA|Entregue para o time de QA iniciar testes.|Em Andamento|
|In Testing|QA executando casos de teste (funcionais, regressão, automatizados).|Em Andamento|
|Blocked|Testes não podem prosseguir (dependência, ambiente, dados).|Tarefas Pendentes|
|Failed / Reopened|Bug encontrado, issue retorna para desenvolvimento.|Tarefas Pendentes|
|Passed / Done|Testes concluídos com sucesso, item pronto para release.|Concluída|
|Released|Funcionalidade já em produção.|Concluída|

## 2. Transições entre estados

|De|Para|Descrição|
|--|----|---------|
|To Do|In Progress|Quando dev inicia trabalho.|
|In Progress|Code Review|Pull request aberto.|
|Code Review|Ready for QA|Merge aprovado.|
|Ready for QA|In Testing|QA inicia execução.|
|In Testing|Passed|Se tudo ok.|
|In Testing|Failed/Reopened|Se bug encontrado.|
|Failed/Reopened|In Progress|Issue retorna para desenvolvimento para correção.|
|In Testing|Blocked|Quando testes não podem prosseguir por dependências, ambiente ou dados.|
|Blocked|In Testing|Quando o bloqueio é resolvido e os testes podem continuar.|
|Passed|Released|Após deploy validado.|
