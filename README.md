# Fatias Espetaculares — Landing Page

Site estático pronto para hospedagem. Não precisa de build, servidor Node, nem instalação — é só HTML, CSS (Tailwind via CDN) e imagens.

## Estrutura

```
public/
  index.html       -> a página inteira
  assets/          -> todas as imagens usadas no site
```

Tudo dentro de `public/` é o que precisa ir para o servidor. A pasta `assets/` tem que ficar sempre ao lado do `index.html`, mantendo os mesmos nomes de arquivo (o HTML referencia as imagens por caminho relativo, ex. `./assets/logo.png`).

## Como hospedar

Qualquer hospedagem de site estático funciona. Algumas opções comuns:

### Netlify / Vercel (mais simples)
1. Arraste a pasta `public/` inteira para o painel de deploy (drag-and-drop) do Netlify, ou
2. Suba a pasta para um repositório Git e conecte no Vercel/Netlify, configurando `public` como diretório de publicação (**Publish directory**).

### Hospedagem tradicional (cPanel, FTP, etc.)
1. Acesse o gerenciador de arquivos ou um cliente FTP.
2. Envie todo o conteúdo de dentro de `public/` (o `index.html` e a pasta `assets/`) para a pasta pública do seu domínio (geralmente `public_html/` ou `www/`).
3. Não envie a pasta `public` em si — envie o que está **dentro** dela, direto na raiz do domínio.

### GitHub Pages
1. Suba o conteúdo de `public/` para a raiz do repositório (ou para uma pasta `docs/`).
2. Ative o GitHub Pages nas configurações do repositório, apontando para essa pasta.

## Antes de publicar

Revise estes pontos que dependem dos seus dados reais:
- Link do botão de checkout (está como `#` em vários lugares — trocar pelo link real da plataforma de pagamento)
- Domínio: se quiser trocar a URL canônica/Open Graph, procure por `fatiasespetaculares.com.br` dentro do `index.html` e ajuste
- Analytics/pixel de rastreamento (Meta Ads, Google Ads): ainda não está configurado — adicionar dentro da tag `<head>` se for usar

## Observações técnicas
- O site usa Tailwind CSS via CDN (carregado direto do `<script>` no `<head>`) — não precisa instalar nada, mas exige conexão com a internet para carregar esse script.
- Não há processo de build: qualquer edição no `index.html` já reflete direto ao subir o arquivo.
