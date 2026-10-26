# 4. O prompt base

Copie o texto abaixo, preencha o que está entre `[colchetes]` e cole os dados no fim.
Funciona no ChatGPT, no Claude, no Gemini ou no Copilot.

```text
Você vai montar um relatório em HTML para a Secretaria-Executiva de Transformação Digital
(SETDIG), do Governo de Mato Grosso do Sul.

# Contexto
- Quem vai ler: [quem]
- Para quê: [objetivo]
- Decisão que o relatório apoia: [decisão]
- Período: [período]
- O que aparece primeiro: [o mais importante]

# Regras
1. Use SÓ os dados que estão em "Dados", no fim. Não invente número, nome ou data.
   Se faltar algo, escreva "a confirmar" e me avise no fim da resposta.
2. Linguagem simples: frases curtas, voz ativa, sem jargão.
3. Devolva UM arquivo HTML completo, com o CSS dentro de <style>. Sem JavaScript.
4. Siga o Design System de MS: use só as variáveis CSS abaixo para cor, espaço e raio.
   Não use outra cor.
5. Fontes: Mulish nos títulos e Open Sans no texto, carregadas do Google Fonts.
6. Todo link abre em nova aba: target="_blank" rel="noopener".
7. Precisa funcionar no celular (largura de 375px) sem rolagem lateral.
8. Rodapé: "Secretaria-Executiva de Transformação Digital — SETDIG".

# Estrutura
1. Faixa azul no topo com o título, o período e de 2 a 4 números-resumo.
2. "Destaques": até 5 itens, em cards numerados.
3. Detalhe: listas ou tabela agrupadas por tema.
4. "Atenção": riscos ou pendências, se houver.
5. Rodapé.

# Variáveis do Design System (cole no :root)
--ds-color-primary-600:#004f9f; --ds-color-primary-800:#002f5f; --ds-color-primary-50:#f5f8fb;
--ds-color-primary-100:#e6edf5; --ds-color-neutral-0:#ffffff; --ds-color-neutral-100:#f9f9f9;
--ds-color-neutral-200:#d5d5d5; --ds-color-neutral-700:#686867; --ds-color-neutral-900:#30302e;
--ds-color-tertiary-500:#ffd500; --ds-color-green-100:#eaf6ed; --ds-color-green-800:#18622e;
--ds-color-orange-100:#fff3ea; --ds-color-orange-800:#994f1a; --ds-color-red-100:#fbe9ea;
--ds-color-red-700:#a91e23; --ds-radius-sm:8px; --ds-radius-md:12px;
--ds-spacing-8:.5rem; --ds-spacing-16:1rem; --ds-spacing-24:1.5rem; --ds-spacing-32:2rem;

# Dados
[cole aqui a tabela, a lista ou o texto com os dados]
```

## Por que cada parte existe

| Parte | Para que serve |
|---|---|
| Contexto | A IA escreve para a pessoa certa e começa pelo que importa. |
| Regra 1 | Evita número inventado. É a regra mais importante. |
| Regra 3 | Você recebe um arquivo, não um texto para montar. |
| Regras 4 e 5 | O relatório sai com a cara do Governo de MS. |
| Estrutura | Todos os relatórios do time ficam parecidos e fáceis de ler. |

!!! tip "Pediu ajuste?"
    Peça mudanças pequenas, uma por vez: "troque a ordem das seções", "deixe os cards em duas
    colunas". Não peça para "melhorar tudo", porque a IA pode mexer nos números.
