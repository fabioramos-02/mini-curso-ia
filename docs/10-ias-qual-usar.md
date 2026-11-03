# 10. Qual IA usar

Não existe "a melhor IA". Existe a IA certa para a tarefa. Esta página mostra as mais usadas
pelo time, para que serve cada uma e quando escolher qual.

## Panorama

| IA | Forte em | Fraco em | Custo |
|---|---|---|---|
| **ChatGPT** (OpenAI) | Rascunho rápido, idéias soltas, texto curto, imagens. | Documentos muito longos. Guarda menos contexto por conversa. | Grátis no básico; Plus US$ 20/mês. |
| **Claude** (Anthropic) | Documento longo, análise de dado sensível, código. Lê PDF e planilha grandes sem perder detalhe. | Não gera imagem. Menos popular, menos tutoriais em português. | Grátis no básico; Pro US$ 20/mês. |
| **Gemini** (Google) | Integração com Gmail, Drive, Docs. Resposta com busca na web. | Formato de resposta menos previsível. | Grátis; Advanced US$ 20/mês. |
| **Copilot** (GitHub / Microsoft) | Código dentro do VS Code. Autocompletar e sugerir função. | Fora do editor é só um ChatGPT travado. | US$ 10/mês (grátis para servidor público em alguns planos). |
| **Ollama** (local) | Roda no seu computador, sem internet, sem mandar dado para fora. Bom para teste e dado sigiloso. | Precisa máquina com GPU boa. Qualidade abaixo das pagas. | Grátis. Modelos abertos (qwen3, gpt-oss, nemotron). |

## Regra prática

- **Rascunho rápido, idéia solta** → ChatGPT.
- **Documento longo (ata, relatório, análise de PDF) ou dado sensível de governo** → Claude.
- **Dentro do VS Code, escrevendo código** → Copilot.
- **Dado 100% sigiloso que não pode sair da máquina** → Ollama local.
- **Precisa buscar na internet dentro da conversa** → Gemini ou ChatGPT com busca.

Para o relatório HTML deste curso, qualquer uma das quatro primeiras funciona. A diferença
aparece no volume: se o dado bruto é grande (PDF de 20 páginas, planilha de 500 linhas),
**Claude** costuma ler melhor sem perder detalhe.

## Para que o time já usa cada uma

- **Relatório semanal, ata de reunião, revisão de texto** → ChatGPT ou Claude.
- **Revisar carta de serviço pela Lei 15.263/2025** → Claude (contexto longo + sigilo).
- **Código do portal, componentes do Design System** → Copilot (no VS Code) + Claude (fora).
- **ChatBot do portal, busca interna, agentes privados** → Ollama rodando qwen3 e gpt-oss
  no servidor do time (levantamento feito por Antônio, SGD).

!!! warning "Cuidado comum às quatro"
    **Nunca cole CPF, matrícula de servidor, e-mail de cidadão ou dado médico em prompt de IA
    pública.** Vale para ChatGPT, Claude, Gemini e Copilot. Se o dado é sensível, use Ollama
    local ou peça para a chefia liberar uma conta corporativa com contrato de sigilo.

!!! tip "Dica de troca"
    Se uma IA travou numa resposta ("não consigo", "muito longo"), copie o mesmo prompt e cole
    em outra. O resultado costuma mudar bem. Nenhuma IA é a dona da verdade.

## Monte o prompt desta sessão

**Pergunta desta sessão:** o prompt muda de uma IA para outra?

**Quando usar:** em qualquer uma das quatro. O texto é o mesmo. O que muda é como o template chega à IA.

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

| IA | Como entregar o template |
|---|---|
| ChatGPT | Clipe de papel → anexar o `.html` |
| Claude | Arrastar o `.html` para a conversa |
| Gemini | Botão **+** → enviar arquivo |
| Copilot | Colar o conteúdo do `.html` no fim, depois de `[FIM DOS DADOS]` |
