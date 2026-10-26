# 6. A estrutura no Design System

O Design System de MS ([designsystem.digital.ms.gov.br](https://designsystem.digital.ms.gov.br/){ target="_blank" })
define as cores, as fontes e os espaços do Governo. O relatório usa as mesmas variáveis.

## O esqueleto

```text
┌────────────────────────────────────────┐
│ Faixa azul: título · período · números  │
├────────────────────────────────────────┤
│ Destaques (cards numerados)            │
│ Detalhe (listas ou tabela por tema)    │
│ Atenção (riscos e pendências)          │
├────────────────────────────────────────┤
│ Rodapé SETDIG                          │
└────────────────────────────────────────┘
```

## As cores e o que significam

| Variável | Cor | Uso |
|---|---|---|
| `--ds-color-primary-600` | Azul do Governo | Faixa do topo, links, números de destaque |
| `--ds-color-primary-50` | Azul bem claro | Fundo dos cards de destaque |
| `--ds-color-neutral-900` | Cinza escuro | Texto |
| `--ds-color-neutral-700` | Cinza médio | Texto de apoio |
| `--ds-color-tertiary-500` | Amarelo do brasão | Contorno de foco do teclado |
| `--ds-color-green-100` / `-800` | Verde | Concluído |
| `--ds-color-orange-100` / `-800` | Laranja | Em andamento, atenção |
| `--ds-color-red-100` / `-700` | Vermelho | Bloqueado, risco |

!!! tip "Uma regra só"
    Toda cor vem de uma variável `--ds-*`. Se a IA escreveu uma cor solta (`#ff0000`, `red`),
    peça para trocar pela variável certa.

## Acessibilidade mínima

- Um só título principal (`<h1>`); as seções usam `<h2>`.
- Contraste bom: texto escuro em fundo claro, texto branco só sobre o azul.
- Links com texto que diz para onde vão ("ver no TFS"), não "clique aqui".
- Funciona com o teclado: dá para chegar em todos os links com a tecla Tab.
