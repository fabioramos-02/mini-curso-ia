# 11. Publicar o HTML

O arquivo `.html` que a IA devolveu abre no navegador, mas enviar o arquivo por e-mail tem
problema: cada pessoa baixa uma cópia, ninguém sabe qual é a última, e no celular alguns
clientes nem abrem.

A saída é publicar. O relatório ganha um endereço fixo (`https://...`) que você compartilha
no Teams, no e-mail ou no WhatsApp. Quem clica vê sempre a versão mais recente.

Três caminhos, do mais fácil para o mais técnico.

## Opção A — Vercel (recomendado)

Vercel publica o arquivo em menos de 1 minuto, de graça, com HTTPS. Serve bem para relatório
que o time quer compartilhar fora da SETDIG.

### Passo a passo (sem código)

1. Entre em **[vercel.com](https://vercel.com){ target="_blank" }** e crie conta com o seu
   GitHub (ou com e-mail institucional).
2. Clique em **"Add New... → Project"**.
3. Em vez de ligar a um repositório, escolha **"Deploy without Git"** e arraste a pasta que
   tem o seu `.html`.
4. Dê um nome (por exemplo `relatorio-semana-45-sgd`). Clique em **Deploy**.
5. Em alguns segundos, a Vercel mostra o endereço. Algo como
   `https://relatorio-semana-45-sgd.vercel.app`. Copie e compartilhe.

### Passo a passo (com linha de comando)

Para quem já usa terminal, dá uma linha só:

```bash
npm i -g vercel     # só na primeira vez
cd pasta-do-html
vercel              # faz login e pergunta duas coisas
```

O endereço `.vercel.app` sai na tela. Pronto.

### Domínio próprio (opcional)

Quando o relatório virar algo recorrente, dá para apontar um subdomínio institucional (ex:
`relatorios.setdig.ms.gov.br`) para a Vercel. Precisa de pedido no DNS da SETDIG. Deixe isso
para a 2ª rodada; comece com a URL `.vercel.app` mesmo.

## Opção B — GitHub Pages

Se o relatório já mora em um repositório do GitHub da SETDIG, é só ligar o Pages nas
configurações do repo. Grátis, HTTPS, bom para relatório **recorrente que fica num repo**.

Passos resumidos:

1. `Settings → Pages` no repositório.
2. Em **Source**, escolha o branch `main` e a pasta (`/` ou `/docs`).
3. Salvar. Em cerca de 1 minuto, o endereço `https://<org>.github.io/<repo>/` fica no ar.

Vale quando o relatório é parte de um projeto que já existe (como este próprio curso, que
está no GitHub Pages).

## Opção C — Artifact do Claude

Quando você gera o HTML dentro do Claude, há um botão **"Publish"** no artifact. Clicou, sai
um endereço `https://claude.ai/public/artifacts/...`. É o caminho mais rápido quando o
relatório vai durar uma semana e some.

Bom para: compartilhar na hora. Não bom para: manter arquivo histórico ou endereço fixo que
dura mais que uns dias.

## Antes de clicar em publicar

!!! danger "Sigilo"
    **A URL do Vercel é pública por padrão.** Qualquer pessoa com o link entra. Antes de
    publicar, abra o `.html` num editor de texto e procure por:

    - CPF, RG, matrícula de servidor
    - E-mail e telefone de cidadão
    - Nome de pessoa que não deveria aparecer no relatório
    - Qualquer dado de saúde, judicial ou de assistência social

    Se achar, apague ou troque por `[dado interno]` antes de subir. Se o relatório **precisa**
    desses dados para fazer sentido, não publique na Vercel pública — use GitHub Pages num
    repo privado ou mande o `.html` por canal institucional.

## Checklist de 1 minuto antes de compartilhar o link

- [ ] O HTML não tem dado pessoal (CPF, matrícula, e-mail de cidadão).
- [ ] A fonte dos números está citada no próprio relatório.
- [ ] O rodapé diz "Secretaria-Executiva de Transformação Digital — SETDIG".
- [ ] A URL foi anotada no vault / no card do TFS / no canal do Teams.
- [ ] O relatório abre bem no celular (teste no seu).

Com os cinco OK, pode mandar.
