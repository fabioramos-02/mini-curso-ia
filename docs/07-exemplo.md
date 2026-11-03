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

## 6. Outros exemplos com o time da SGD

Dois casos novos, montados a partir de insumos reais do time, para você ver o antes e o
depois:

- **[Demandas da semana — relato do Antônio](exemplos/antes-demanda-antonio.md)**: texto
  corrido virou relatório com bloqueio em destaque.
- **[Cartas de serviço revisadas](exemplos/antes-cartas-sgd.md)**: planilha de 13 linhas
  virou foco para a próxima rodada em 3 serviços.

Os dois aplicam a mesma estrutura do exemplo acima, com uma frase-âncora no topo que já
entrega a conclusão.

## Monte o prompt desta sessão

**Pergunta desta sessão:** como fica o prompt inteiro, pronto para colar?

**Quando usar:** é o prompt que gerou o relatório desta página. Ele é o prompt base com o contexto e os dados do exemplo já preenchidos.

!!! example "O prompt"
    ```text
    [PAPEL]
    Aja como um analista sênior de dados da SETDIG — Governo de MS. Especialista em
    transformar dado bruto em relatório gerencial curto, honesto e acionável.

    [ESCOPO DO QUE VOCÊ PODE USAR]
    Use SOMENTE o conteúdo entre [DADOS] e [FIM DOS DADOS] NESTA mensagem, mais o que
    eu confirmar neste chat. É proibido usar memória de outras conversas, buscar na web
    ou supor que a demanda é continuação de alguma anterior. Se [DADOS] estiver vazio
    ou com placeholder, a primeira coisa que você faz é PEDIR OS DADOS.

    [CONTEXTO]
    - Quem vai ler: a Superintendente, na reunião de segunda
    - Para quê: saber o que o time faz na semana
    - Decisão que o relatório apoia: o que priorizar e o que pode esperar
    - Período: de 03/11 a 07/11/2026
    - Fonte: TFS, tarefas abertas do time, exportadas em 03/11

    [OBJETIVO]
    Gere um relatório com:
    1. Frase-âncora com o resultado principal.
    2. KPIs com evidência numérica real.
    3. Tendências e destaques positivos.
    4. Gargalos/bloqueios no topo da seção "Atenção", com impacto e decisão sugerida.
    5. 2 a 4 recomendações práticas.

    Regras obrigatórias:
    - Use SOMENTE o que estiver entre [DADOS] e [FIM DOS DADOS].
    - Linguagem simples, sem jargão.
    - Sem dado pessoal sensível (CPF, matrícula, e-mail de cidadão).
    - Divergência numérica NUNCA é "erro" sem confirmação. Trate como "a conciliar".
    - Se faltar informação, PARE E PERGUNTE antes de responder.

    [FORMATO]
    Preencha o template-relatorio.html (anexado). Substitua {{...}} pelo conteúdo real.
    Não altere paleta nem estrutura. Rodapé: SETDIG.

    [DADOS]
    Fonte: TFS, tarefas abertas do time, exportadas em 03/11.

    | id | título | estado | frente |
    |---|---|---|---|
    | 101 | Conferir os números de atendimento de setembro | Em andamento | Painéis e dados |
    | 102 | Publicar o painel de atendimentos | A fazer | Painéis e dados |
    | 104 | Revisar 12 cartas com linguagem simples | Em andamento | Cartas de serviço |
    | 103 | Marcar a turma de novembro dos pontos focais | A fazer | Capacitação |

    Concluídas: 108 Relatório de outubro enviado.
    [FIM DOS DADOS]
    ```

Compare com o [prompt base](04-prompt-base.md): a parte fixa é igual. Mudam só o `[CONTEXTO]` e os `[DADOS]`. É isso que você troca a cada relatório.
