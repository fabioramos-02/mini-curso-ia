# 5. Os dados

A IA só é tão boa quanto o dado que recebe.

## De onde tirar

| Fonte | Como levar para a IA |
|---|---|
| Planilha (Excel, Google Sheets) | Copie as colunas que importam e cole como tabela. |
| TFS | Exporte a consulta em CSV e cole as colunas de título, estado e responsável. |
| Painel de BI | Anote os números da tela, com a data em que você olhou. |
| E-mail ou ata | Cole só o trecho com a informação. |

## Antes de colar

- **Recorte o período.** Só os dados do período do relatório.
- **Tire o que não importa.** Menos colunas = menos erro.
- **Dê nome às colunas.** `estado`, `responsável`, `data`, não `col1`, `col2`.
- **Diga a fonte e a data.** "Dados do TFS, exportados em 26/10/2026."

## O que NUNCA enviar à IA

!!! danger "Dado pessoal e sigiloso fica de fora"
    - CPF, RG, telefone, endereço ou e-mail de cidadão.
    - Senha, token, chave de API.
    - Dado de saúde ou de processo sigiloso.
    - Qualquer coisa que você não mandaria por e-mail para fora do Governo.

    Se o relatório precisa do número, mande o **total**, não a lista de pessoas.
    "1.240 pedidos" em vez da planilha com o nome de cada pessoa.

## Formato que funciona bem

```text
Fonte: TFS, consulta "Tarefas da SGD", exportada em 26/10/2026.

| id | título | estado | responsável |
|---|---|---|---|
| 101 | Pedir a chave do assinador | A fazer | Fabio |
| 102 | Homologar as cartas no CMS | Em andamento | Daniele |
```
