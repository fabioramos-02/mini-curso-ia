# 4. O prompt base

A IA só devolve um relatório bom se receber **três coisas** na mesma conversa:

1. O **prompt base** (texto abaixo) — explica para a IA quem ela é, para que o relatório
   serve e as regras que ela não pode quebrar.
2. O **template HTML** — esqueleto com os espaços `{{...}}` que a IA preenche. Garante
   que o visual sai no padrão do Governo de MS.
3. Os **seus dados** — colados no fim do prompt.

!!! tip "Baixe os dois arquivos agora"
    - [:material-download: Baixar o prompt (.txt)](assets/downloads/prompt-base.txt){ download="prompt-relatorio-setdig.txt" .md-button }
    - [:material-download: Baixar o template (.html)](assets/downloads/template-relatorio.html){ download="template-relatorio-setdig.html" .md-button }

    Os mesmos arquivos estão no slide **"Prompt base"** da apresentação, com um botão
    extra de **Copiar**.

## Como usar

1. Abra o chat da IA (ChatGPT, Claude, Gemini ou Copilot).
2. Cole o **prompt** (texto abaixo).
3. **Anexe** o template HTML.
4. Cole seus **dados** no bloco `[DADOS]` do prompt.
5. A IA vai perguntar antes de responder se faltar contexto. Responda e ela devolve
   o HTML pronto.

## O prompt

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
- Quem vai ler: [QUEM]
- Para quê: [OBJETIVO DO LEITOR]
- Decisão que o relatório apoia: [DECISÃO]
- Período: de [INÍCIO] a [FIM]
- Fonte: [FONTE]

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
<!-- cole aqui -->
[FIM DOS DADOS]
```

## Os 6 blocos, um por um

O prompt é uma ficha. Cada bloco responde a uma pergunta. Se você souber responder as seis, sabe
montar qualquer prompt, não só este.

### `[PAPEL]` — quem a IA é

- **Para que serve:** dá à IA um ponto de vista. Ela responde como especialista, e não de um jeito genérico.
- **Como construir:** pergunte *"quem eu contrataria para fazer isto?"* e diga o ofício, o nível e o foco.
- **Fraco:** `Você é uma IA.`
- **Forte:** `Aja como analista sênior de dados da SETDIG. Transforme dado bruto em relatório curto, honesto e acionável.`

### `[ESCOPO]` — o que a IA pode usar

- **Para que serve:** cerca a IA. Impede número inventado, memória de outra conversa e busca na web.
- **Como construir:** pergunte *"de onde ela pode tirar informação, e o que faz se faltar?"*
- **Fraco:** `Use seus conhecimentos.`
- **Forte:** `Use SÓ o que estiver entre [DADOS] e [FIM DOS DADOS]. Se estiver vazio, peça os dados antes.`

### `[CONTEXTO]` — quem lê e para quê

- **Para que serve:** diz para quem a IA escreve e qual decisão o relatório apoia.
- **Como construir:** responda as [perguntas da sessão 3](03-perguntas.md).
- **Fraco:** `É para a chefia.`
- **Forte:** `Quem lê: a Superintendente, na segunda. Decisão: o que priorizar de 03 a 07/11.`

### `[OBJETIVO]` — o que entregar, e em que ordem

- **Para que serve:** define as partes do relatório e a ordem. A conclusão (frase-âncora) vem antes do número.
- **Como construir:** pergunte *"o que o leitor precisa ver primeiro, e o que é proibido?"* Liste as partes e as regras.
- **Fraco:** `Faça um resumo.`
- **Forte:** `1. Frase-âncora. 2. KPIs com evidência. 3. Atenção, com a decisão sugerida. Se faltar algo, pergunte.`

### `[FORMATO]` — o molde

- **Para que serve:** fixa a forma. A IA preenche, sem inventar cor nem layout.
- **Como construir:** pergunte *"qual molde ela preenche?"*, anexe o template e proíba mexer na estrutura.
- **Fraco:** `Faça bonito.`
- **Forte:** `Preencha o template-relatorio.html anexado. Troque só os {{...}}. Não altere paleta nem estrutura.`

### `[DADOS]` — a matéria-prima

- **Para que serve:** entrega o que a IA pode usar, já recortado.
- **Como construir:** pergunte *"que período, que colunas, que fonte e que data?"* Veja [os dados](05-dados.md).
- **Fraco:** a planilha inteira, com todas as abas.
- **Forte:** a tabela com 4 colunas, só do período, com a fonte e a data no topo.

!!! tip "A regra mais importante mora no `[ESCOPO]`"
    "Use só os dados que eu entreguei." Sem ela, a IA completa o que falta, e o erro vai com a sua assinatura.

!!! tip "Pediu ajuste?"
    Peça mudanças pequenas, uma por vez: "troque a ordem das seções", "mova a Atenção
    para o topo", "junte os KPIs em 2 colunas". Não peça para "melhorar tudo" — a IA
    pode mexer nos números.

!!! warning "Antes de enviar o relatório"
    Passe pelo [checklist](08-checklist.md). Confira se cada número está nos dados
    originais, se não sobrou nenhum `{{PLACEHOLDER}}` e se o rodapé está correto.

## Monte o prompt desta sessão

**Pergunta desta sessão:** quem a IA é, o que ela pode usar e o que ela entrega?

**O que entra no prompt:** os blocos `[PAPEL]`, `[ESCOPO]` e `[OBJETIVO]`, explicados um por um acima.

??? quote "Como estava (fim da sessão anterior)"
    ```text
    [PAPEL]

    [ESCOPO]

    [CONTEXTO]
    - Quem vai ler: a Superintendente, na reunião de segunda
    - Para quê: saber o que o time faz na semana
    - Decisão que o relatório apoia: o que priorizar e o que pode esperar
    - Período: de 03/11 a 07/11/2026
    - Fonte: TFS, tarefas abertas do time, exportadas em 03/11

    [OBJETIVO]

    [FORMATO]

    [DADOS]
    ```

!!! example "Como ficou — linhas novas marcadas com ◀ novo"
    ```text
    [PAPEL]
    Aja como um analista sênior de dados da SETDIG — Governo de MS. Especialista em  ◀ novo
    transformar dado bruto em relatório gerencial curto, honesto e acionável.  ◀ novo

    [ESCOPO DO QUE VOCÊ PODE USAR]
    Use SOMENTE o conteúdo entre [DADOS] e [FIM DOS DADOS] NESTA mensagem, mais o que  ◀ novo
    eu confirmar neste chat. É proibido usar memória de outras conversas, buscar na web  ◀ novo
    ou supor que a demanda é continuação de alguma anterior. Se [DADOS] estiver vazio  ◀ novo
    ou com placeholder, a primeira coisa que você faz é PEDIR OS DADOS.  ◀ novo

    [CONTEXTO]
    - Quem vai ler: a Superintendente, na reunião de segunda
    - Para quê: saber o que o time faz na semana
    - Decisão que o relatório apoia: o que priorizar e o que pode esperar
    - Período: de 03/11 a 07/11/2026
    - Fonte: TFS, tarefas abertas do time, exportadas em 03/11

    [OBJETIVO]
    Gere um relatório com:  ◀ novo
    1. Frase-âncora com o resultado principal.  ◀ novo
    2. KPIs com evidência numérica real.  ◀ novo
    3. Tendências e destaques positivos.  ◀ novo
    4. Gargalos/bloqueios no topo da seção "Atenção", com impacto e decisão sugerida.  ◀ novo
    5. 2 a 4 recomendações práticas.  ◀ novo

    Regras obrigatórias:  ◀ novo
    - Use SOMENTE o que estiver entre [DADOS] e [FIM DOS DADOS].  ◀ novo
    - Linguagem simples, sem jargão.  ◀ novo
    - Sem dado pessoal sensível (CPF, matrícula, e-mail de cidadão).  ◀ novo
    - Divergência numérica NUNCA é "erro" sem confirmação. Trate como "a conciliar".  ◀ novo
    - Se faltar informação, PARE E PERGUNTE antes de responder.  ◀ novo

    [FORMATO]

    [DADOS]
    ```
