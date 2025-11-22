# Luxe Nails — Como atualizar produtos e rodar localmente

Este repositório contém um site simples (HTML/CSS/JS) que carrega produtos de `produtos.json`.

Passos rápidos para desenvolvimento local

1. Abra a pasta do projeto:

```bash
cd /home/well/Documentos/manicure
```

2. Inicie um servidor estático (Python):

```bash
python3 -m http.server 8000
```

3. Abra no navegador:

- Site: `http://localhost:8000/index.html`
- Painel de edição de produtos: `http://localhost:8000/admin_produtos.html`

Editar produtos (workflow)

- Use `admin_produtos.html` para carregar `produtos.json`, editar localmente e então clicar em **Download JSON**.
- Substitua o arquivo `produtos.json` no servidor com o JSON baixado para que as mudanças fiquem permanentes.
  - Se o site estiver hospedado em um servidor simples, faça upload do novo `produtos.json` para a pasta do site.
  - Se estiver usando um repositório git, faça commit do novo `produtos.json` e faça deploy.

Salvando editado apenas no navegador

- `admin_produtos.html` também permite salvar em `localStorage` (chave `produtos_admin`) — útil para testes rápidos sem alterar o arquivo no servidor.

Deploy

- Se o site estiver hospedado por FTP/hosting simples: substitua `produtos.json` no servidor pelo novo arquivo.
- Se estiver usando GitHub Pages ou similar: atualize `produtos.json` no branch, commit e faça push; a página será atualizada conforme o processo do host.

Notas técnicas

- As imagens de produto são carregadas dinamicamente a partir do campo `img` em `produtos.json`.
- O `index.html` usa IntersectionObserver para lazy-loading de imagens (fallback carrega tudo caso não suportado).
- Use imagens otimizadas (webp/jpg) para melhor performance.

Se quiser, eu posso gerar um script simples (Node/Python) que faça upload automático do `produtos.json` para seu servidor via SFTP/rsync — me diga qual método de deploy você usa e eu preparo o script.
