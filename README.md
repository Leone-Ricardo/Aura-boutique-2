# 🌿 Aura — Moda feminina com alma de bairro

Site institucional e vitrine digital da **Aura**, marca fictícia de moda feminina de bairro localizada na Vila Madalena, São Paulo. O projeto foi construído do zero com HTML5 semântico, CSS moderno e JavaScript vanilla — sem frameworks, sem dependências pesadas.

---

## 📖 Sumário

- [Sobre o projeto](#-sobre-o-projeto)
- [Demonstração](#-demonstração)
- [Funcionalidades](#-funcionalidades)
- [Estrutura de arquivos](#-estrutura-de-arquivos)
- [Como rodar localmente](#-como-rodar-localmente)
- [Design System](#-design-system)
- [Arquitetura do código](#-arquitetura-do-código)
- [Carrinho de compras](#-carrinho-de-compras)
- [Integração com WhatsApp](#-integração-com-whatsapp)
- [Cálculo de frete](#-cálculo-de-frete)
- [Acessibilidade](#-acessibilidade)
- [Performance](#-performance)
- [SEO](#-seo)
- [Responsividade](#-responsividade)
- [Personalização](#-personalização)
- [Roadmap](#-roadmap)
- [Licença](#-licença)

---

## 🌱 Sobre o projeto

A **Aura** é uma marca de moda feminina de bairro com alma local e acabamento editorial sofisticado. O site foi desenhado para:

- **Apresentar a marca** com tom próximo, elegante e sem esnobismo;
- **Gerar desejo** através de fotografia editorial, tipografia forte e espaço em branco generoso;
- **Facilitar o contato e a compra** com integração direta ao WhatsApp;
- **Ser memorável** visualmente, com microinterações sutis e animações suaves.

O projeto é **single-page** (SPA estática), com navegação por âncoras internas e um carrinho que persiste em `localStorage`.

---

## 🎬 Demonstração

O site completo é entregue em um único arquivo `index.html` autocontido (CSS e JS embutidos), pronto para:

- Colar no **CodePen**, **JSFiddle** ou **StackBlitz**;
- Publicar em **GitHub Pages**, **Netlify**, **Vercel** ou qualquer host estático;
- Abrir localmente no navegador sem build step.

---

## ✨ Funcionalidades

### Navegação e apresentação
- ✅ Header fixo com transição transparente → sólido com blur ao rolar
- ✅ Menu mobile em drawer lateral com trap de foco
- ✅ Painel de busca expansível no header
- ✅ Navegação ativa automática conforme a seção visível (`IntersectionObserver`)
- ✅ Marquee infinito com pausa no hover
- ✅ Scroll reveal suave com delays escalonados

### Seções da página
- ✅ Hero full-screen com indicador de scroll animado
- ✅ Manifesto da fundadora com foto e selo
- ✅ Grid de coleções (Vestidos, Alfaiataria, Casual, Acessórios)
- ✅ Lookbook em masonry com modal de detalhes
- ✅ Vitrine de produtos em destaque
- ✅ Sobre a loja com endereço, horário, mapa e CTA
- ✅ Depoimentos de clientes com avaliação
- ✅ Feed do Instagram
- ✅ Newsletter com validação
- ✅ Footer completo em 4 colunas

### E-commerce (WhatsApp)
- ✅ Carrinho lateral com persistência em `localStorage`
- ✅ Adição, remoção e ajuste de quantidade de itens
- ✅ Cálculo de subtotal, frete e total em tempo real
- ✅ Duas modalidades de entrega: **retirada na loja** (grátis) e **entrega por CEP**
- ✅ Frete grátis acima de R$ 399
- ✅ Mensagem formatada e enviada ao WhatsApp da loja com resumo completo do pedido

### Qualidade técnica
- ✅ 100% responsivo (mobile-first)
- ✅ Acessibilidade AA (foco visível, ARIA, `inert`, trap de foco)
- ✅ Suporte a `prefers-reduced-motion`
- ✅ Lazy loading em imagens
- ✅ Sem dependências externas (apenas Google Fonts)

---

## 📁 Estrutura de arquivos

O projeto é entregue em **arquivo único** para portabilidade máxima:

```
aura/
└── index.html      ← HTML + CSS embutido em <style> + JS embutido em <script>
```

Se preferir separar em arquivos (recomendado para produção):

```
aura/
├── index.html
├── assets/
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   └── script.js
│   └── img/           (opcional — imagens locais)
└── README.md
```

---

## 🚀 Como rodar localmente

### Opção 1 — Abrir direto no navegador
Basta fazer duplo clique no arquivo `index.html`. Nada de build, nada de instalação.

### Opção 2 — Servidor local (recomendado)
Alguns recursos (como `IntersectionObserver` + `localStorage`) funcionam melhor com um servidor local.

**Com Python 3:**
```bash
python -m http.server 3000
```

**Com Node.js:**
```bash
npx serve .
```

**Com PHP:**
```bash
php -S localhost:3000
```

Depois abra [http://localhost:3000](http://localhost:3000).

### Opção 3 — Deploy rápido

| Serviço | Comando |
|---|---|
| **Netlify** | Arraste a pasta para [app.netlify.com/drop](https://app.netlify.com/drop) |
| **Vercel** | `npx vercel` na raiz do projeto |
| **GitHub Pages** | Faça push para um repo e ative Pages nas configurações |

---

## 🎨 Design System

### Tipografia

| Uso | Fonte | Peso | Tamanho |
|---|---|---|---|
| Títulos | **Playfair Display** (serifada) | 500 / 600 / 700 | `clamp(2.5rem, 6vw, 5rem)` no H1 |
| Corpo/UI | **Inter** (sans-serif) | 300 / 400 / 500 / 600 | `1rem` base, `1.7` line-height |

### Paleta de cores

```css
--cor-fundo:      #FAF8F5   /* off-white quente */
--cor-texto:      #1A1A1A   /* quase preto */
--cor-texto-suave:#6B6B6B   /* cinza para textos secundários */
--cor-primaria:   #B76E79   /* rosé antigo (marca) */
--cor-secundaria: #2E2E2E   /* carvão para contraste */
--cor-destaque:   #C9A227   /* dourado discreto */
--cor-borda:      #E5E0DA   /* bege claro */
--cor-hover:      #9E5A64   /* rosé mais escuro no hover */
--cor-branco:     #FFFFFF
--cor-preto:      #0D0D0D
```

### Espaçamento e layout

- Container máximo: **1280px**
- Padding lateral: **1.5rem** (mobile) / **3rem** (desktop)
- Grid de 12 colunas, gap `1.5rem` / `2rem`
- Seções com padding vertical `clamp(4rem, 10vw, 8rem)`

### Efeitos

| Elemento | Valor |
|---|---|
| Sombras | `0 4px 20px rgba(0,0,0,.06)` / hover `0 12px 30px rgba(0,0,0,.10)` |
| Raios | `0.5rem` (cards) / `999px` (botões pill) |
| Transições | `all 0.3s cubic-bezier(.25,.46,.45,.94)` |
| Aspect ratio de produtos | `3/4` |
| Aspect ratio do hero | `16/9` (ou full-screen) |

---

## 🏗️ Arquitetura do código

### Metodologia CSS — **BEM**

Todos os componentes usam a convenção BEM (`Block__Element--Modifier`):

```html
<article class="product-card">
  <div class="product-card__image-wrapper">
    <span class="product-card__badge product-card__badge--rose">Últimas peças</span>
  </div>
</article>
```

### Organização do CSS

O `<style>` está dividido em seções comentadas:

1. **Design System** (`:root` com custom properties)
2. **Reset/Base** (universal, tipografia global, foco)
3. **Layout utilitário** (`.container`, `.section`, `.btn`, `.link-animado`)
4. **Seções numeradas 1 a 12** (header, hero, marquee, manifesto, coleções, lookbook, produtos, loja, depoimentos, instagram, newsletter, footer)
5. **Carrinho** (drawer, itens, opções de entrega, CEP)
6. **Toast** (notificações)
7. **Media queries** (640px, 1024px, `prefers-reduced-motion`)

### Organização do JavaScript

O `<script>` é um **IIFE** (Immediately Invoked Function Expression) único, com módulos internos comentados:

```js
(function () {
  'use strict';

  // 1. HEADER — transparente → sólido
  // 2. DRAWER MOBILE — menu hambúrguer
  // 3. PAINEL DE BUSCA
  // 4. MODAL LOOKBOOK
  // 5. SCROLL REVEAL
  // 6. NAVEGAÇÃO ATIVA
  // 7. NEWSLETTER
  // 8. CARRINHO DE COMPRAS  ← módulo principal
  // 9. TECLA ESC (fecha tudo)
})();
```

O **carrinho é encapsulado em uma factory function** `Cart()` que expõe apenas o necessário:

```js
const Cart = (function () {
  // ... variáveis e funções privadas ...

  return {
    adicionar: adicionar,
    abrir: abrir,
    fechar: fechar
  };
})();
```

---

## 🛒 Carrinho de compras

### Fluxo do usuário

```
[Card de produto]
      │
      ▼  clique em "Adicionar à sacola"
[Toast de confirmação] + [Badge atualiza] + [Drawer abre]
      │
      ▼  usuário pode:
      ├─ ajustar quantidade (+/−)
      ├─ remover item (×)
      ├─ escolher retirada OU entrega
      └─ informar CEP (se entrega)
      │
      ▼  clique em "Finalizar pelo WhatsApp"
[Mensagem formatada → WhatsApp da loja]
```

### Persistência

- Chave: `aura_cart_v1` no `localStorage`
- Estrutura: array de objetos `{ id, nome, preco, imagem, qtd }`
- Sobrevive a recarregamentos e reaberturas do navegador

### Estrutura da mensagem WhatsApp

```
*Olá, Aura!* Gostaria de finalizar meu pedido 🌿

*— ITENS —*
• 1x Vestido Midi Linho — R$ 289,00
• 2x Camisa Seda Off-White — R$ 518,00

Subtotal: R$ 807,00
Entrega: *Retirada na loja* — Rua Harmonia, 512 (Vila Madalena)
Frete: Grátis

*Total: R$ 807,00*

Meu nome: Marina

Aguardo o retorno para combinar o pagamento. Obrigada! 💛
```

### Distribuição de altura do drawer

O drawer foi estruturado em três blocos:

| Bloco | `flex` | Comportamento |
|---|---|---|
| **Header** (título + fechar) | `flex: 0 0 auto` | Altura fixa |
| **Corpo** (itens) | `flex: 1 1 auto` + `min-height: 0` | Ocupa espaço restante, rola internamente |
| **Footer** (resumo + checkout) | `flex: 0 0 auto` | Altura natural, sem `max-height` |

Em telas com menos de **620px de altura**, um `@media (max-height: 620px)` libera scroll dentro do próprio rodapé como rede de segurança.

---

## 📱 Integração com WhatsApp

### Número da loja

Definido como constante no módulo do carrinho:

```js
const LOJA_WHATSAPP = '5511998765432'; // formato: DDI + DDD + número
```

### Onde a integração é usada

1. **Botão "Comprar"** em cada produto → mensagem individual
2. **Botão "Finalizar pelo WhatsApp"** no carrinho → resumo completo
3. **Botão "Quero esse look"** no modal do lookbook → pergunta sobre o look
4. **Ícone de sacola no header** → abre o carrinho (não envia msg direta)
5. **Links no footer e drawer** → contato direto

### Como funciona

A URL é montada com `encodeURIComponent()` para garantir que acentos, emojis e caracteres especiais cheguem corretos:

```js
const url = 'https://wa.me/' + LOJA_WHATSAPP + '?text=' + encodeURIComponent(msg);
window.open(url, '_blank', 'noopener');
```

---

## 📦 Cálculo de frete

### Regras implementadas

| Regra | Valor |
|---|---|
| **Retirada na loja** | Sempre grátis |
| **Frete grátis (entrega)** | Pedidos acima de **R$ 399** |
| **Cálculo por CEP** | Mock baseado no 1º dígito do CEP |

### Tabela simulada

```js
const tabela = {
  0: 19.90, 1: 22.90, 2: 24.90, 3: 27.90,
  4: 29.90, 5: 32.90, 6: 34.90, 7: 36.90,
  8: 38.90, 9: 42.90
};
```

> ⚠️ **Importante:** este cálculo é **mockado** para demonstração. Para produção, substitua por uma API real:
> - **Correios** — [WS Correios](https://www.correios.com.br/atendimento/ferramentas/sistemas)
> - **Melhor Envio** — [melhorenvio.com.br](https://melhorenvio.com.br/)
> - **Frenet** — [frenet.com.br](https://frenet.com.br/)
> - **Kangu** — [kangu.com.br](https://kangu.com.br/)

### Onde substituir

Procure a função `calcularFrete()` dentro do módulo `Cart` e troque o retorno síncrono por uma chamada `fetch()`.

---

## ♿ Acessibilidade

O projeto segue as diretrizes **WCAG 2.1 nível AA**:

### Contraste
- Todos os pares texto/fundo respeitam o contraste mínimo de **4.5:1** para texto normal e **3:1** para texto grande.

### Navegação por teclado
- Foco visível customizado (`:focus-visible` com outline rosé);
- Trap de foco no drawer mobile, modal e carrinho;
- Tecla `ESC` fecha qualquer overlay aberto;
- Botão `Pular para o conteúdo` no início da página.

### ARIA e semântica
- `role="dialog"` + `aria-modal="true"` em modais e drawers;
- `aria-live="polite"` em feedbacks (newsletter, CEP, toast);
- `aria-label` em todos os botões com ícone;
- `aria-current="true"` na seção ativa da navegação;
- `inert` no conteúdo de fundo quando um overlay está aberto.

### Imagens
- `alt` descritivo em todas as imagens (não decorativas);
- `alt=""` em imagens puramente decorativas.

### Movimento
- Respeita `prefers-reduced-motion: reduce` — desativa animações, marquee e scroll reveal.

---

## ⚡ Performance

| Técnica | Onde |
|---|---|
| **Lazy loading** | `loading="lazy"` em todas as imagens exceto hero |
| **Prioridade de carregamento** | `fetchpriority="high"` no hero |
| **Width/height explícitos** | Em todas as imagens (evita CLS) |
| **Animações com GPU** | Apenas `transform` e `opacity` |
| **Delegação de eventos** | Listeners únicos por container |
| **Debounce implícito** | `{ passive: true }` no scroll do header |
| **Unobserve pós-animação** | `IntersectionObserver` desconecta após revelar |
| **Font display swap** | `&display=swap` no Google Fonts |

---

## 🔍 SEO

### Meta tags implementadas

```html
<title>Aura — Moda feminina com alma de bairro | Vila Madalena, SP</title>
<meta name="description" content="...">
<link rel="canonical" href="https://www.aura.com.br/">

<!-- Open Graph -->
<meta property="og:type" content="website">
<meta property="og:locale" content="pt_BR">
<meta property="og:title" content="...">
<meta property="og:description" content="...">
<meta property="og:image" content="...">
<meta property="og:url" content="...">

<!-- Twitter -->
<meta name="twitter:card" content="summary_large_image">
```

### Hierarquia semântica
- Um único `<h1>` por página (título do hero);
- `<h2>` para títulos de seção;
- `<h3>` para nomes de produtos, cards de coleção, etc.;
- `<header>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<nav>`, `<aside>` usados corretamente.

---

## 📐 Responsividade

Abordagem **mobile-first** com três breakpoints principais:

| Breakpoint | Comportamento |
|---|---|
| **< 640px** | 1 coluna, menu hambúrguer, hero centralizado, grids 1 col |
| **640px – 1024px** | 2 colunas nos grids, hero alinhado à esquerda |
| **> 1024px** | Layout completo, nav horizontal, grids 3–4 colunas, container 1280px |

### Tipografia fluida
Todos os tamanhos grandes usam `clamp()`:

```css
h1 { font-size: clamp(2.5rem, 6vw, 5rem); }
h2 { font-size: clamp(2rem, 4vw, 3rem); }
```

### Breakpoint extra de altura
```css
@media (max-height: 620px) { /* ajustes no carrinho */ }
```

---

## 🔧 Personalização

### Trocar a marca
Substitua todas as ocorrências de **"Aura"** por outro nome. Pontos principais:

| Onde | O que trocar |
|---|---|
| `<title>` e meta tags | Nome da marca e descrição |
| `.header__logo`, `.footer__marca` | Nome |
| `<h1>` do hero | Título principal |
| URL de Instagram | `https://instagram.com/suamarca` |
| E-mail | `oi@suamarca.com.br` |

### Trocar o número do WhatsApp
No módulo `Cart`, altere:

```js
const LOJA_WHATSAPP = '5511998765432'; // ← seu número aqui
```

E também nos links estáticos `<a href="https://wa.me/...">` no HTML.

### Trocar imagens
Todas as imagens usam **Unsplash** com parâmetros de tamanho. Para trocar:

1. Escolha uma nova foto em [unsplash.com](https://unsplash.com);
2. Copie a URL base (ex: `https://images.unsplash.com/photo-XXXXX`);
3. Substitua mantendo os parâmetros `?auto=format&fit=crop&w=800&q=80`;
4. Ajuste o `alt` descritivo.

### Trocar as cores
Altere as custom properties em `:root`:

```css
--cor-primaria: #B76E79;   /* cor de destaque da marca */
--cor-destaque: #C9A227;   /* dourado */
```

### Trocar o frete grátis
No módulo `Cart`:

```js
const FRETE_GRATIS_MIN = 399; // ← valor mínimo para frete grátis
```

### Trocar a tabela de frete
Substitua o objeto `tabela` em `calcularFrete()` por chamada real de API.

### Trocar o endereço da loja
Procure por **"Rua Harmonia, 512"** no HTML e substitua em:
- `.loja__dados` (endereço + horário);
- Drawer mobile (rodapé);
- Footer (Atendimento);
- `iframe` do mapa (atualize a query `q=`);
- Link "Como chegar" (atualize a query do Google Maps).

---

## 🗺️ Roadmap

Melhorias futuras sugeridas:

- [ ] **Página de produto individual** com galeria, tamanhos e descrição longa
- [ ] **Filtros de coleção** por tamanho, cor e preço
- [ ] **Wishlist** persistente em `localStorage`
- [ ] **Integração real de frete** (Correios / Melhor Envio)
- [ ] **Checkout com PIX** (QR code gerado a partir do total)
- [ ] **Cupons de desconto** (código aplicado no carrinho)
- [ ] **Backend headless** (Strapi, Sanity ou Contentful) para o catálogo
- [ ] **PWA** com service worker e manifest
- [ ] **Analytics** (GA4 ou Plausible)
- [ ] **Testes automatizados** (Playwright para E2E, Vitest para unit)

---

## 📄 Licença

Este projeto é entregue como **demonstração de portfólio**. Sinta-se livre para estudar, adaptar e usar como base para projetos próprios.

As imagens do **Unsplash** seguem a [Unsplash License](https://unsplash.com/license) — uso livre, inclusive comercial, sem atribuição obrigatória.

As fontes **Playfair Display** e **Inter** são distribuídas sob a [SIL Open Font License](https://openfontlicense.org/) via Google Fonts.

---

## 🤝 Contribuindo

Sugestões, correções e melhorias são bem-vindas. Abra uma issue ou envie um PR com:

1. Descrição clara do problema/melhoria;
2. Screenshots (se for visual);
3. Teste em pelo menos **mobile (375px)** e **desktop (1440px)**.

---

## 📬 Contato

**Aura** — Moda feminina com alma de bairro
📍 Rua Harmonia, 512 — Vila Madalena, São Paulo/SP
📱 [WhatsApp (11) 99876-5432](https://wa.me/5511998765432)
📷 [@aura](https://instagram.com/aura)
✉️ [oi@aura.com.br](mailto:oi@aura.com.br)

---

<p align="center">
  <em>Feito com amor no bairro. 🌿</em>
</p>
