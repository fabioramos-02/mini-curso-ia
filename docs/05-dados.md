# 5. Os dados

A IA só é tão boa quanto o dado que recebe.

## De onde tirar

| Fonte | Como levar para a IA |
|---|---|
| Planilha (Excel, Google Sheets) | Copie as colunas que importam e cole como tabela. |
| TFS | Exporte a consulta em CSV e cole as colunas de título, estado e responsável. |
| Painel de BI | Anote os números da tela, com a data em que você olhou. |
| E-mail ou ata | Cole só o trecho com a informação. |

## Antes de colar

- **Recorte o período.** Só os dados do período do relatório.
- **Tire o que não importa.** Menos colunas = menos erro.
- **Dê nome às colunas.** `estado`, `responsável`, `data`, não `col1`, `col2`.
- **Diga a fonte e a data.** "Dados do TFS, exportados em 26/10/2026."

## O que NUNCA enviar à IA

!!! danger "Dado pessoal e sigiloso fica de fora"
    - CPF, RG, telefone, endereço ou e-mail de cidadão.
    - Senha, token, chave de API.
    - Dado de saúde ou de processo sigiloso.
    - Qualquer coisa que você não mandaria por e-mail para fora do Governo.

    Se o relatório precisa do número, mande o **total**, não a lista de pessoas.
    "1.240 pedidos" em vez da planilha com o nome de cada pessoa.

## Formato que funciona bem

```text
Fonte: TFS, consulta "Tarefas da SGD", exportada em 26/10/2026.

| id | título | estado | responsável |
|---|---|---|---|
| 101 | Pedir a chave do assinador | A fazer | Fabio |
| 102 | Homologar as cartas no CMS | Em andamento | Daniele |
```

## Monte o prompt desta sessão

**Pergunta desta sessão:** que dado a IA pode usar, e de onde ele veio?

**O que entra no prompt:** o bloco `[DADOS]`, já recortado: só o período, só as colunas úteis, com a fonte e a data.

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

    [DADOS]
    Fonte: TFS, tarefas abertas do time, exportadas em 03/11.  ◀ novo

    | id | título | estado | frente |  ◀ novo
    |---|---|---|---|  ◀ novo
    | 101 | Conferir os números de atendimento de setembro | Em andamento | Painéis e dados |  ◀ novo
    | 102 | Publicar o painel de atendimentos | A fazer | Painéis e dados |  ◀ novo
    | 104 | Revisar 12 cartas com linguagem simples | Em andamento | Cartas de serviço |  ◀ novo
    | 103 | Marcar a turma de novembro dos pontos focais | A fazer | Capacitação |  ◀ novo

    Concluídas: 108 Relatório de outubro enviado.  ◀ novo
    [FIM DOS DADOS]
    ```
