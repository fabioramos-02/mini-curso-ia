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
Aja como um analista sênior de dados da Secretaria-Executiva de Transformação Digital
(SETDIG) do Governo de Mato Grosso do Sul. Você é especialista em transformar dado bruto
em relatório gerencial curto, honesto e acionável, no padrão visual do portal MS.

[CONTEXTO]
- Quem vai ler: [QUEM]
- Para quê: [OBJETIVO DO LEITOR]
- Decisão que o relatório apoia: [DECISÃO]
- Período da análise: de [DATA INICIAL] a [DATA FINAL]
- Fonte dos dados: [FONTE]
- Dados brutos: ver bloco [DADOS] no fim deste prompt.

[OBJETIVO / TAREFA]
Analise [DADOS] e gere um relatório gerencial com:
1. Visão geral: 1 frase-âncora com o resultado principal.
2. Indicadores (KPIs) com evidência numérica real.
3. Tendências e pontos de destaque positivos.
4. Gargalos ou itens bloqueados, no topo da seção "Atenção", com impacto e
   decisão sugerida à chefia.
5. De 2 a 4 recomendações práticas.

Regras obrigatórias:
- Use SOMENTE o que está em [DADOS]. Não atribua causa que o dado não comprove.
- Linguagem simples, sem jargão.
- Sem dado pessoal sensível (CPF, matrícula, e-mail de cidadão).
- Se faltar informação, PARE E PERGUNTE antes de responder.

[FORMATO]
- Devolva UM arquivo HTML completo, preenchendo o template anexado
  (template-relatorio.html). Substitua os placeholders {{...}}.
- NÃO altere a paleta nem a estrutura do template.
- Rodapé: "Secretaria-Executiva de Transformação Digital — SETDIG".

[PERGUNTE ANTES SE FALTAR]
- Quem é o leitor? Qual decisão apoia?
- Período, fonte e meta de referência dos KPIs?
- Há algum item bloqueado?

[DADOS]
[cole aqui]
```

## Por que cada parte existe

| Parte | Para que serve |
|---|---|
| **Papel** | A IA assume um ponto de vista claro (analista sênior SETDIG). Respostas ficam mais acionáveis e menos genéricas. |
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
