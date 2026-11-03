# 9. Próximos passos

Este curso para no HTML pronto. Quando o time estiver seguro com ele, os próximos passos são:

## Publicar com link fixo

Hoje você envia o `.html` por e-mail ou chat. O passo seguinte é publicar e compartilhar
só o link, sempre atualizado. Isso tem seção própria:
**[11. Publicar o HTML](11-publicar.md)** (Vercel, GitHub Pages e Artifact do Claude).

## Usar sempre o mesmo modelo

Guarde o HTML que ficou bom. Na próxima vez, mande o arquivo antigo junto com os dados novos e
peça: "mantenha este layout e troque só os dados". O relatório sai parecido com o anterior, só
com os números atualizados.

## Automatizar

Ligar a IA direto nas fontes (TFS, BI, Google Sheets) para o relatório sair com um comando,
sem copiar e colar. Esse é o salto maior e vem depois de o time estar confortável com os
passos 1 a 8.

!!! note "Um passo de cada vez"
    Primeiro, todo mundo gera o HTML com confiança. Publicar e automatizar vêm depois.

## Monte o prompt desta sessão

**Pergunta desta sessão:** como reaproveitar o relatório da semana passada?

**Quando usar:** na semana seguinte, numa conversa nova. Anexe o HTML que ficou bom, em vez do template.

!!! example "O prompt"
    ```text
    [FORMATO]
    Mantenha exatamente o layout do relatorio-semana-anterior.html (anexado).
    Troque só os textos e os números pelos dados abaixo. Não mude cores, ordem nem seções.

    [CONTEXTO]
    - Período: de 10/11 a 14/11/2026

    [DADOS]
    <!-- cole aqui os dados da nova semana -->
    [FIM DOS DADOS]
    ```

Os blocos `[PAPEL]`, `[ESCOPO]` e `[OBJETIVO]` continuam iguais aos do prompt base. Mudam o `[FORMATO]` (o molde agora é o seu relatório antigo), o período e os dados.
