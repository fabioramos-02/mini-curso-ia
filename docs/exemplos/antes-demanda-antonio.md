# Exemplo 1 — Demandas da semana (antes × depois)

Caso real. O Antônio, da SGD, entregou o relato das demandas da semana num `.pdf` escrito
corrido: cinco blocos separados por linha de hífens, com o status e a descrição.

A pergunta é: **como esse mesmo conteúdo fica num HTML que a Superintendente lê em 30
segundos e decide o que fazer na segunda?**

## Para quem fala

**Público:** gestor (Superintendente de Governo Digital).
**Pergunta de negócio:** o que avançou, o que travou, o que precisa de decisão da chefia
nesta semana?
**Decisão que o relatório apoia:** desbloquear o que está parado, priorizar a semana
seguinte.

## 1. O "antes" (dado bruto)

Texto exato como veio no PDF. Observe que não dá para bater o olho e tirar a conclusão.

```text
totalmente concluido
Foi feita o levantamento dos dados de como funciona, quais a difenrenças, seus componetes e
recomendações de quais e como utilizar, sobre os agentes IAs que iram ser implementados.
Nomes das IAs
- qwen3.8:27b (Recomendado para chat geral, raciocínio e desenvolvimento de código)
- nemotron-cascade-2:latest
- gpt-oss:20b
- qwen3-embedding:8b (Embeddings para busca vetorial / RAG)
------------------------------------------------------------------------------------------------
totalmente concluido
Envio dos SiteMaps para o google search console. Identificação de um sitemap que continha um
html, portanto fiz o envio para o Pedro para refazer o sitemap.
------------------------------------------------------------------------------------------------
tarefa bloqueada por falta da API KEY.
Criação do ChatBot
- Estudo sobre criações de ChatBot
- Criar um plano de execução
- Ajuste no plano
- desenvolvimento do ChatBot - falta
------------------------------------------------------------------------------------------------
participação do meeting sobre os modulos da X-via
------------------------------------------------------------------------------------------------
Homologação da carta de serviço
```

Cinco demandas misturadas, status solto no começo de cada bloco, nenhuma hierarquia.

## 2. O prompt

Usa o [prompt base](../04-prompt-base.md), com três ajustes:

- **Decisão que o relatório apoia:** desbloquear o ChatBot (API KEY) e priorizar a próxima
  semana.
- **O que aparece primeiro:** o número-resumo (quantas entregues, quantas bloqueadas) e o
  bloqueio em destaque — a chefia precisa ver *em primeiro* o que precisa dela.
- **Estrutura "Atenção":** card vermelho/laranja com o bloqueio, nome da pessoa que
  depende da ação, o que falta.

Trecho adicional de contexto colado no fim do prompt:

```text
# Contexto
- Quem vai ler: Superintendente de Governo Digital (Maria Eduarda / "Duda"), na reunião de segunda.
- Para quê: ver o que o Antônio entregou e decidir o que destravar.
- Decisão que o relatório apoia: destravar o ChatBot (API KEY) e priorizar a próxima semana.
- Período: semana de 20 a 24/10.
- O que aparece primeiro: o resumo (concluídas × bloqueadas) e o item bloqueado.

# Observação
Agrupe por status: Concluídas · Bloqueadas · Em andamento. Dentro de cada grupo, uma linha por
demanda, com título curto e 1 frase de descrição. Para a bloqueada, deixe claro **o que a
chefia precisa fazer**.
```

## 3. O resultado

A IA devolveu o arquivo HTML.
**[Abrir o relatório de demandas da semana](relatorio-demanda-semana.html){ target="_blank" }**.

O que mudou em relação ao PDF:

- **Frase-âncora no topo:** "2 entregues, 1 bloqueada, 2 em andamento". A chefia já tem a
  foto da semana antes de ler o resto.
- **Bloqueio em destaque laranja:** ChatBot aguarda a API KEY. Nome do responsável, o que
  falta e o que depende de decisão.
- **Linguagem simples no texto visível:** "Levantamento de IAs" em vez do nome dos modelos
  (que entraram num detalhe secundário).
- **Rodapé com honestidade:** data de corte do dado ("relato até 24/10, 17h").

## 4. O que você aprende aqui

- **Dado cru não é relatório.** O PDF do Antônio tem todos os números, mas obriga a chefia a
  trabalhar para extrair a decisão. O HTML entrega a decisão primeiro.
- **Bloqueio vai sempre em destaque.** Se tem algo parado, é o item que mais interessa pro
  gestor. Nunca enterre no meio.
- **Público decide o formato.** O mesmo dado, para a chefia, vira o relatório ao lado. Para
  o próprio Antônio planejar a semana, viraria uma lista de tarefas (outro formato).
