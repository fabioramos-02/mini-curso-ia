# Exemplo 2 — Cartas de serviço revisadas (antes × depois)

Dados **fictícios**, mas o cenário é real: a Lei nº 15.263/2025 obriga toda carta de serviço
publicada no portal a estar em linguagem simples. A SGD acompanha a revisão em 4 órgãos.

A pergunta é: **onde a chefia precisa concentrar a próxima rodada de revisão?**

## Para quem fala

**Público:** gestor (Superintendente de Governo Digital / Secretário-Executivo).
**Pergunta de negócio:** quais órgãos estão em dia e quais ficaram abaixo do padrão de
linguagem simples?
**Decisão que o relatório apoia:** onde o time precisa gastar hora na próxima semana.

## 1. O "antes" (planilha crua)

A planilha veio assim do time de linguagem simples. Nota de 0 a 10 (meta ≥ 7, conforme
padrão interno da SGD).

```text
Fonte: planilha "cartas-revisao-outubro.xlsx", exportada em 24/10. Dados fictícios.

| órgão    | serviço                                   | status      | nota | pendência                        |
|---       |---                                        |---          | ---  |---                               |
| SES-MS   | Agendar consulta no SUS                   | Revisada    | 8,0  | —                                |
| SES-MS   | Pedir cartão SUS                          | Revisada    | 7,5  | —                                |
| SES-MS   | Marcar exame de imagem                    | Em revisão  | 5,5  | Reduzir termos técnicos          |
| SED-MS   | Matrícula na rede estadual                | Revisada    | 8,5  | —                                |
| SED-MS   | Transferência de escola                   | Revisada    | 7,0  | —                                |
| SED-MS   | Pedir histórico escolar                   | Em revisão  | 6,5  | Reescrever introdução            |
| DETRAN   | Transferir veículo                        | Revisada    | 7,0  | —                                |
| DETRAN   | Renovar CNH                               | Revisada    | 8,0  | —                                |
| DETRAN   | Segunda via de CRLV                       | Revisada    | 7,5  | —                                |
| DETRAN   | Recorrer multa                            | Em revisão  | 4,5  | Linguagem jurídica demais        |
| SEJUSP   | Boletim de ocorrência eletrônico          | Revisada    | 7,5  | —                                |
| SEJUSP   | Antecedentes criminais                    | Revisada    | 7,0  | —                                |
| SEJUSP   | Atestado de bons antecedentes             | Em revisão  | 5,0  | Faltam exemplos para o cidadão   |

Meta de nota mínima: 7,0. Órgãos acompanhados: SES-MS, SED-MS, DETRAN-MS, SEJUSP-MS.
Rodada: outubro / 2025.
```

Dá para ler, mas não dá para decidir. Ninguém bateu o olho e disse: "foca em DETRAN e SES
semana que vem".

## 2. O prompt

Mesmo [prompt base](../04-prompt-base.md), com os ajustes:

```text
# Contexto
- Quem vai ler: Superintendente de Governo Digital e Secretário-Executivo da SETDIG.
- Para quê: ver em que órgão a revisão está em dia e onde ainda falta chegar na meta (nota ≥ 7).
- Decisão que o relatório apoia: onde direcionar o time de linguagem simples na próxima rodada.
- Período: outubro / 2025.
- O que aparece primeiro: a frase-âncora (quantas no padrão × quantas abaixo) e os 3 serviços
  mais baixos.

# Observação
- Nota mínima da meta: 7,0. Marque abaixo disso como "abaixo do padrão".
- Agrupe por órgão. Para cada órgão, mostre quantas cartas estão no padrão e a nota média.
- No topo, destaque os 3 serviços de menor nota (independente do órgão).
- Linguagem simples: nada de "KPI", "benchmark", "performance". Fale como se fosse para o
  cidadão entender também.
```

## 3. O resultado

**[Abrir o relatório de cartas de serviço](relatorio-cartas-sgd.html){ target="_blank" }**.

O que mudou em relação à planilha:

- **Frase-âncora no topo:** "10 cartas no padrão, 3 abaixo da meta". A chefia já sabe de
  cara que o grosso está em dia e tem 3 pontos de atenção.
- **Os 3 pontos baixos em destaque:** nome do serviço, nota, o que falta. Pronto para virar
  tarefa da próxima rodada.
- **Por órgão:** quantas cartas e nota média. SES-MS e DETRAN-MS aparecem como focos.
- **Honestidade:** o relatório diz que a nota é a avaliação interna do time de linguagem
  simples. Não é pesquisa com cidadão (seria outra conversa).

## 4. O que você aprende aqui

- **Tabela não é relatório.** 13 linhas de planilha viram 3 pontos de ação na frase-âncora.
- **Meta explícita vira cor.** "Nota ≥ 7" permite marcar o que está abaixo. Sem meta, a cor
  vira enfeite.
- **Linguagem simples no próprio relatório sobre linguagem simples.** Nada de "KPI de
  compliance textual". Se o relatório fala para a chefia decidir, fala em português do dia a
  dia.
