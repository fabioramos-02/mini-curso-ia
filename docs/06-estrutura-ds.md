# 6. A estrutura no Design System

O Design System de MS ([designsystem.digital.ms.gov.br](https://designsystem.digital.ms.gov.br/){ target="_blank" })
define as cores, as fontes e os espaços do Governo. O relatório usa as mesmas variáveis.

## O esqueleto

```text
┌────────────────────────────────────────┐
│ Faixa azul: título · período · números  │
├────────────────────────────────────────┤
│ Destaques (cards numerados)            │
│ Detalhe (listas ou tabela por tema)    │
│ Atenção (riscos e pendências)          │
├────────────────────────────────────────┤
│ Rodapé SETDIG                          │
└────────────────────────────────────────┘
```

## As cores e o que significam

| Variável | Cor | Uso |
|---|---|---|
| `--ds-color-primary-600` | Azul do Governo | Faixa do topo, links, números de destaque |
| `--ds-color-primary-50` | Azul bem claro | Fundo dos cards de destaque |
| `--ds-color-neutral-900` | Cinza escuro | Texto |
| `--ds-color-neutral-700` | Cinza médio | Texto de apoio |
| `--ds-color-tertiary-500` | Amarelo do brasão | Contorno de foco do teclado |
| `--ds-color-green-100` / `-800` | Verde | Concluído |
| `--ds-color-orange-100` / `-800` | Laranja | Em andamento, atenção |
| `--ds-color-red-100` / `-700` | Vermelho | Bloqueado, risco |

!!! tip "Uma regra só"
    Toda cor vem de uma variável `--ds-*`. Se a IA escreveu uma cor solta (`#ff0000`, `red`),
    peça para trocar pela variável certa.

## Acessibilidade mínima

- Um só título principal (`<h1>`); as seções usam `<h2>`.
- Contraste bom: texto escuro em fundo claro, texto branco só sobre o azul.
- Links com texto que diz para onde vão ("ver no TFS"), não "clique aqui".
- Funciona com o teclado: dá para chegar em todos os links com a tecla Tab.

## Monte o prompt desta sessão

**Pergunta desta sessão:** em que molde a IA entrega?

**O que entra no prompt:** o bloco `[FORMATO]`, que aponta para o template e proíbe mexer em cor e estrutura.

??? quote "Como estava (fim da sessão anterior)"
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

!!! example "Como ficou — linhas novas marcadas com ◀ novo"
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
    Preencha o template-relatorio.html (anexado). Substitua {{...}} pelo conteúdo real.  ◀ novo
    Não altere paleta nem estrutura. Rodapé: SETDIG.  ◀ novo

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
