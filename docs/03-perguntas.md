# 3. As perguntas antes de abrir a IA

Responda por escrito, em uma linha cada. Essas respostas entram no prompt.

| Pergunta | Exemplo |
|---|---|
| **Quem vai ler?** | A Superintendente, na reunião de segunda. |
| **Para quê?** | Saber o que o time vai fazer na semana. |
| **Qual decisão ele ajuda a tomar?** | O que priorizar e o que pode esperar. |
| **Qual período?** | De 26 a 30/10/2026. |
| **Qual o tamanho?** | Uma tela, sem rolar muito. |
| **O que precisa aparecer primeiro?** | As prioridades. |
| **Onde o relatório vai ser aberto?** | No navegador do computador, às vezes no celular. |

!!! warning "Se você não sabe responder"
    Pare antes de abrir a IA. Pergunte a quem pediu o relatório. A IA não adivinha o objetivo.

## Exercício

Pense num relatório que você fez no último mês e responda as sete perguntas acima.

## Monte o prompt desta sessão

**Pergunta desta sessão:** para quem é o relatório e que decisão ele apoia?

**O que entra no prompt:** o bloco `[CONTEXTO]`, com as respostas às perguntas desta página. O pedido solto sai: agora o contexto diz o que antes ficava subentendido.

??? quote "Como estava (fim da sessão anterior)"
    ```text
    [PAPEL]

    [ESCOPO]

    [CONTEXTO]

    [OBJETIVO]

    [FORMATO]

    [DADOS]

    Faz um relatório das tarefas da semana.
    ```

!!! example "Como ficou — linhas novas marcadas com ◀ novo"
    ```text
    [PAPEL]

    [ESCOPO]

    [CONTEXTO]
    - Quem vai ler: a Superintendente, na reunião de segunda  ◀ novo
    - Para quê: saber o que o time faz na semana  ◀ novo
    - Decisão que o relatório apoia: o que priorizar e o que pode esperar  ◀ novo
    - Período: de 03/11 a 07/11/2026  ◀ novo
    - Fonte: TFS, tarefas abertas do time, exportadas em 03/11  ◀ novo

    [OBJETIVO]

    [FORMATO]

    [DADOS]
    ```
