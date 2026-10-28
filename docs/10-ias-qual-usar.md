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
