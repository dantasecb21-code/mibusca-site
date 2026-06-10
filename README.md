# Mibusca — Site (versão otimizada)

Site estático multi-páginas, focado em SEO e design, para a Mibusca (agência de marketing para delivery — iFood e 99Food).

## Estrutura

```
Site/
├── index.html          Home
├── servicos.html       Serviços (com âncoras por serviço)
├── planos.html         Planos + tabela comparativa
├── cases.html          Resultados / cases
├── sobre.html          Sobre a agência
├── contato.html        Contato + formulário que abre o WhatsApp
├── assets/
│   ├── css/styles.css   Design system completo
│   ├── js/main.js       Menu mobile, FAQ, contadores, animações
│   └── img/             (coloque aqui og-cover.jpg e logo.png)
├── favicon.svg
├── site.webmanifest
├── sitemap.xml
└── robots.txt
```

## Como publicar

É um site estático: funciona em qualquer hospedagem.
- **Mais simples:** arraste a pasta para [Netlify Drop](https://app.netlify.com/drop) ou faça deploy na **Vercel**.
- **Hospedagem própria/Hostinger:** suba todos os arquivos para a pasta pública (`public_html`), mantendo a estrutura de pastas.

Para testar localmente, basta abrir `index.html` no navegador.

## O que melhorou em relação ao site atual

**SEO**
- Title único e correto em cada página (o atual tinha erro "delivey" e título gigante).
- Meta description, canonical, Open Graph e theme-color em todas as páginas.
- Um único `<h1>` por página (o atual repetia o H1).
- Dados estruturados JSON-LD: Organization/ProfessionalService, LocalBusiness, FAQPage, Product/Offer (planos), Service, BreadcrumbList, ContactPage.
- `sitemap.xml` + `robots.txt`.
- Conteúdo único por página e inclusão da **99Food** (o atual só citava iFood e Google).
- HTML semântico (header, main, section, article, nav, footer).

**Design e performance**
- Identidade visual consistente (paleta, tipografia, espaçamentos).
- 100% responsivo, com menu mobile.
- Sem números "0+" zerados — contadores animam até valores reais.
- Ícones em SVG inline e fonte única → carregamento leve, bom para Core Web Vitals.
- CTAs de WhatsApp claros em toda a jornada + botão flutuante.

## Antes de ir ao ar (recomendado)

1. Adicione `assets/img/og-cover.jpg` (1200×630) e `assets/img/logo.png` — usados no compartilhamento em redes e no JSON-LD.
2. Revise os **números** das estatísticas/cases para refletirem dados reais e verificáveis.
3. Confirme o e-mail: o site usa `contact@mibusca.com.br` (no site atual aparecia assim).
4. Configure o domínio e gere o certificado SSL (https).
5. Cadastre o site no **Google Search Console** e envie o `sitemap.xml`.
