# 1. Por que padronizar

Hoje cada pessoa pede relatório à IA de um jeito. O resultado muda toda vez:

- uma vez vem em texto, outra em tabela, outra em slide;
- as cores e as fontes não seguem o padrão do Governo;
- os números às vezes saem errados, porque a IA preencheu o que faltava;
- quem recebe não sabe de onde veio cada dado.

## O que muda com um padrão

| Sem padrão | Com padrão |
|---|---|
| Cada relatório tem uma cara | Todos seguem o Design System de MS |
| A IA inventa o que falta | A IA só usa os dados que você entregou |
| Você reescreve o pedido toda vez | Você copia o prompt base e troca os dados |
| Texto solto no chat | Um arquivo `.html` pronto para abrir e enviar |

## A ideia central

> A IA é rápida para montar. **Você** é responsável pelo que está escrito.

O padrão serve para a IA fazer a parte repetitiva (layout, cores, organização) e você ficar com a
parte que importa: escolher os dados e conferir o resultado.

## Monte o prompt desta sessão

**Pergunta desta sessão:** o que acontece quando eu peço do jeito de sempre?

**O que entra no prompt:** o pedido solto, do jeito que quase todo mundo começa. Ele é o ponto de partida do curso.

!!! example "Como ficou — linhas novas marcadas com ◀ novo"
    ```text
    Faz um relatório das tarefas da semana.  ◀ novo
    ```

O que falta nele: **quem lê**, **qual dado usar** e **qual formato**. A IA vai chutar as três coisas. Nas próximas sessões, cada lacuna vira um bloco do prompt.
