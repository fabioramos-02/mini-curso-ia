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

## Por que cada parte existe

| Parte | Para que serve |
|---|---|
| **Papel** | A IA assume um ponto de vista claro (analista sênior SETDIG). Respostas ficam mais acionáveis e menos genéricas. |
| **Escopo** | Impede a IA de usar memória de outra conversa, buscar na web ou "lembrar" dados antigos. Se o [DADOS] vier vazio, ela pede antes de inventar. |
| **Contexto** | A IA escreve para a pessoa certa e começa pelo que importa. |
| **Objetivo** | Define o que o relatório precisa entregar: frase-âncora, KPIs com evidência, atenção, recomendações. |
| **Regra "só use [DADOS]"** | Evita número inventado. É a regra mais importante. |
| **Formato com template** | A IA não precisa inventar HTML nem cor — só preencher. Resultado padronizado. |
| **"Pergunte antes"** | Se o contexto está raso, a IA não "chuta". Pergunta primeiro e volta com o relatório certo. |

!!! tip "Pediu ajuste?"
    Peça mudanças pequenas, uma por vez: "troque a ordem das seções", "mova a Atenção
    para o topo", "junte os KPIs em 2 colunas". Não peça para "melhorar tudo" — a IA
    pode mexer nos números.

!!! warning "Antes de enviar o relatório"
    Passe pelo [checklist](08-checklist.md). Confira se cada número está nos dados
    originais, se não sobrou nenhum `{{PLACEHOLDER}}` e se o rodapé está correto.
