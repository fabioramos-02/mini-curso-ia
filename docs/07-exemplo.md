# 7. Um exemplo do começo ao fim

Um relatório semanal do time, feito com as quatro premissas. Os dados são **fictícios**.

## 1. Perguntas respondidas

- **Quem vai ler:** a Superintendente, na reunião de segunda.
- **Para quê:** saber o que o time faz na semana.
- **Decisão:** o que priorizar.
- **Período:** 3 a 7/11.
- **Primeiro:** as prioridades.

## 2. Dados

```text
Fonte: TFS, tarefas abertas do time, exportadas em 03/11.

Prioridades: fechar o painel de atendimentos (101, 102); treinar os pontos focais (103);
revisar 12 cartas de serviço (104).

| id | título | estado | frente |
|---|---|---|---|
| 101 | Conferir os números de atendimento de setembro | Em andamento | Painéis e dados |
| 102 | Publicar o painel de atendimentos | A fazer | Painéis e dados |
| 105 | Atualizar a planilha de serviços digitais | A fazer | Painéis e dados |
| 104 | Revisar 12 cartas com linguagem simples | Em andamento | Cartas de serviço |
| 106 | Responder as dúvidas do órgão sobre o cadastro | A fazer | Cartas de serviço |
| 103 | Marcar a turma de novembro dos pontos focais | A fazer | Capacitação |
| 107 | Preparar o material do mini curso | Em andamento | Capacitação |

Concluídas: 108 Relatório de outubro enviado; 109 Reunião de alinhamento com o órgão.
```

## 3. Prompt

O [prompt base](04-prompt-base.md), com o contexto acima e os dados colados no fim.

## 4. Resultado

A IA devolveu um arquivo HTML. Ele está aqui:
**[abrir o relatório de exemplo](exemplos/relatorio-semanal.html){ target="_blank" }**.

O que conferir nele:

- a faixa azul com o período e os números-resumo;
- as prioridades numeradas, na ordem pedida;
- as pendências agrupadas por frente, com "em andamento" em destaque;
- as concluídas em verde;
- nenhuma cor fora do Design System.

## 5. Conferência

Antes de enviar, passe pelo [checklist](08-checklist.md). No exemplo: 7 pendências na lista,
7 nos dados. Bateu.
