# CLAUDE.md — Projeto Site Mibusca

Contexto e convenções para o Claude Code continuar este projeto.

## O que é

Site institucional da **Mibusca**, agência de marketing focada em **delivery e restaurantes**,
que gerencia lojas dentro do **iFood** e da **99Food** para aumentar o faturamento dos clientes
e reduzir dependência de taxas e descontos.

O site foi reconstruído com foco em **SEO** e **design**, substituindo a versão WordPress/Elementor
antiga (mibusca.com.br) que tinha problemas de SEO (title com erro "delivey", H1 duplicado,
contadores "0+" zerados, conteúdo fino) e de design.

## Stack

- **HTML/CSS/JS estático**, sem framework e sem build. Funciona abrindo o `index.html`.
- Uma única folha de estilo (`assets/css/styles.css`) com design system (variáveis CSS).
- JS leve e sem dependências (`assets/js/main.js`): menu mobile, FAQ, contadores, reveal on scroll.
- Fonte: Plus Jakarta Sans (Google Fonts). Ícones: SVG inline.

## Estrutura

```
index.html        Home (hero, serviços, planos, cases, depoimentos, FAQ, CTA)
servicos.html     Serviços (âncoras por serviço)
planos.html       Planos + tabela comparativa
cases.html        Resultados / cases
sobre.html        Sobre a agência
contato.html      Contato + formulário que abre WhatsApp
assets/css/styles.css
assets/js/main.js
favicon.svg · site.webmanifest · sitemap.xml · robots.txt
.github/workflows/deploy.yml   Deploy automático no GitHub Pages a cada push
```

## Convenções (seguir ao editar/criar páginas)

- Atuar como **SEO sênior + especialista em design de sites**.
- **1 único `<h1>` por página.** Hierarquia h1 → h2 → h3 correta.
- Cada página tem: `title` único, `meta description`, `canonical`, Open Graph e `theme-color`.
- Dados estruturados **JSON-LD** por página (Organization/LocalBusiness, FAQPage, Product/Offer,
  Service, BreadcrumbList, ContactPage). Manter válidos ao alterar conteúdo.
- Conteúdo em **pt-BR**, sempre citando **iFood e 99Food** (não só iFood).
- Header, footer e botão flutuante de WhatsApp são repetidos em todas as páginas — manter idênticos.
- CTA principal = WhatsApp `+55 71 98248-9443`. E-mail: `contact@mibusca.com.br`.
- Paleta: `--brand #ff4d2d`, `--brand-2 #ff9100`, tinta `#0e1116`. Não introduzir cores fora do tema.
- Responsivo (breakpoints 980px e 760px). Acessibilidade: `aria-*`, foco visível, `prefers-reduced-motion`.

## Git e deploy

- Repositório já iniciado; branch **main**. Commits em pt-BR, curtos e descritivos.
- Deploy = **GitHub Pages via GitHub Actions** (`.github/workflows/deploy.yml`), automático a cada push.
- Rotina pedida pelo dono: **a cada alteração, fazer commit e push** (o Pages publica sozinho).

## Pendências

1. Conectar ao GitHub e dar push (`git remote add origin ...` + `git push -u origin main`).
2. Ativar Pages: Settings → Pages → Source: **GitHub Actions**.
3. Adicionar `assets/img/og-cover.jpg` (1200×630) e `logo.png` para compartilhamento social.
4. Revisar números de estatísticas/cases para refletirem dados reais.
5. (Opcional) Apontar domínio `mibusca.com.br` para o Pages — só quando for substituir o WordPress atual.

Mais detalhes em `README.md` e `DEPLOY-GITHUB.md`.
