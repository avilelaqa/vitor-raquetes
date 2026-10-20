# Vitor Raquetes — site

Site estático (um único `index.html`, com as fotos embutidas) do catálogo do @vitor_raquetes.

## Publicar no GitHub Pages (uma vez)

1. Crie o repositório público `vitor-raquetes` na conta `avilelaqa` e suba estes arquivos na branch `main`
   (pela interface web: *Add file → Upload files*; ou pelo terminal, dentro desta pasta):

   ```bash
   git init
   git add .
   git commit -m "Site Vitor Raquetes"
   gh repo create vitor-raquetes --public --source=. --push
   ```

2. No repositório: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: main / (root) → Save**.
   Pelo terminal, o mesmo passo é:

   ```bash
   gh api -X POST repos/avilelaqa/vitor-raquetes/pages -f "source[branch]=main" -f "source[path]=/"
   ```

3. Em 1–2 minutos o site fica no ar em **https://avilelaqa.github.io/vitor-raquetes/**

## Atualizar o catálogo

Troque o `index.html` pelo novo arquivo gerado e faça um novo commit (`git add . && git commit -m "Atualiza catálogo" && git push`). O GitHub Pages republica sozinho.

## Domínio próprio (opcional)

Registre o domínio (ex.: `vitorraquetes.com.br` no Registro.br), crie um arquivo `CNAME` com o domínio, aponte o DNS
(`CNAME www → avilelaqa.github.io`; registros `A` do apex para os IPs do GitHub Pages) e informe o domínio em *Settings → Pages → Custom domain*.
Depois troque `https://avilelaqa.github.io/vitor-raquetes/` pelas novas URLs nas tags `canonical`, `og:url`, `og:image` e `twitter:image` do `index.html`.

## Arquivos

- `index.html` — a página inteira (catálogo, filtros, WhatsApp, bolas, encordoamento, acessórios, compra/troca)
- `og-image.png` — imagem de prévia quando o link é compartilhado no WhatsApp, Instagram etc.
- `favicon.svg`, `favicon-32.png`, `apple-touch-icon.png` — ícones da aba e da tela inicial do celular
- `.nojekyll` — diz ao GitHub Pages para publicar os arquivos como estão
