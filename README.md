<!doctype html>
<html lang="pt">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Galeria — Mbwa Ent</title>
<meta name="description" content="Imagens e vídeos dos eventos organizados pela Mbwa Ent em Angola." />
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="stylesheet" href="css/style.css" />
<script src="https://cdn.tailwindcss.com"></script>
<script>
  tailwind.config = { theme: { extend: {
    colors: { black: { deep: '#0a0a0c', soft: '#111114' }, graphite: { DEFAULT: '#1c1d21', light: '#2a2b30' }, orange: '#ff5a1f', blue: { electric: '#00b4ff' }, red: { performance: '#e4002b' } },
    fontFamily: { display: ['Clash Display','General Sans','sans-serif'], body: ['General Sans','system-ui','sans-serif'], mono: ['Space Mono','monospace'] },
  } } };
</script>
</head>
<body>

<div class="site-loader" id="siteLoader"><div class="site-loader__mark">MBWA<span>ENT</span></div><div class="site-loader__bar"></div></div>
<div class="grain-overlay"></div>

<nav class="site-nav" id="siteNav">
  <a href="index.html" class="site-nav__logo">MBWA<span>ENT</span></a>
  <div class="site-nav__links">
    <a href="index.html">Início</a><a href="sobre.html">Sobre</a><a href="eventos.html">Eventos</a>
    <a href="galeria.html" class="is-active">Galeria</a><a href="patrocinadores.html">Patrocinadores</a><a href="servicos.html">Serviços</a><a href="contactos.html">Contactos</a>
  </div>
  <div style="display:flex; align-items:center; gap:0.5rem;">
    <a href="evento-kambwa-show.html" class="site-nav__cta">Kambwa Show 2026</a>
    <button class="site-nav__burger" id="navBurger" aria-label="Abrir menu" aria-expanded="false">
      <svg width="18" height="18" viewBox="0 0 18 18" fill="none"><path d="M2 5h14M2 13h14" stroke="white" stroke-width="1.6" stroke-linecap="round"/></svg>
    </button>
  </div>
</nav>

<div class="mobile-menu" id="mobileMenu">
  <div class="mobile-menu__links">
    <a href="index.html">Início</a><a href="sobre.html">Sobre</a><a href="eventos.html">Eventos</a>
    <a href="galeria.html">Galeria</a><a href="patrocinadores.html">Patrocinadores</a><a href="servicos.html">Serviços</a><a href="contactos.html">Contactos</a>
  </div>
  <a href="evento-kambwa-show.html" class="btn btn--primary" style="margin-top:2rem;">Kambwa Show 2026</a>
</div>

<header class="pt-40 pb-10">
  <div class="container">
    <span class="eyebrow reveal">Momentos</span>
    <h1 class="font-display font-700 mt-5 reveal" style="font-size:clamp(2.4rem, 6vw, 4.2rem); max-width: 16ch; line-height:1.02;">A Energia Capturada.</h1>
  </div>
</header>

<!-- ============ FILTROS ============ -->
<section class="container pb-8">
  <div class="reveal flex flex-wrap gap-3 font-mono text-xs uppercase tracking-widest" id="galleryFilters">
    <button class="gallery-filter is-active" data-filter="todos">Todos</button>
    <button class="gallery-filter" data-filter="kambwa">Kambwa Show</button>
    <button class="gallery-filter" data-filter="corporativo">Corporativo</button>
    <button class="gallery-filter" data-filter="cultural">Cultural</button>
    <button class="gallery-filter" data-filter="video">Vídeos</button>
  </div>
</section>

<!-- ============ GALERIA MASONRY ============ -->
<section class="section pt-4">
  <div class="container">
    <div class="masonry" id="masonryGrid">

      <div class="masonry__item reveal" data-cat="kambwa" style="grid-row: span 2;">
        <button class="gallery-tile" data-full="https://picsum.photos/seed/gal-1/1400/1800" aria-label="Ampliar imagem — palco Kambwa Show">
          <img src="https://picsum.photos/seed/gal-1/700/900" alt="Palco do Kambwa Show com luzes intensas" loading="lazy" />
        </button>
      </div>

      <div class="masonry__item reveal" data-cat="corporativo">
        <button class="gallery-tile" data-full="https://picsum.photos/seed/gal-2/1200/900" aria-label="Ampliar imagem — evento corporativo">
          <img src="https://picsum.photos/seed/gal-2/700/560" alt="Convidados num evento corporativo Mbwa Ent" loading="lazy" />
        </button>
      </div>

      <div class="masonry__item reveal" data-cat="video">
        <button class="gallery-tile gallery-tile--video" data-full="https://picsum.photos/seed/gal-3/1200/900" aria-label="Reproduzir vídeo — resumo do evento">
          <img src="https://picsum.photos/seed/gal-3/700/560" alt="Fotograma de vídeo do evento" loading="lazy" />
          <span class="play-badge">▶</span>
        </button>
      </div>

      <div class="masonry__item reveal" data-cat="cultural" style="grid-row: span 2;">
        <button class="gallery-tile" data-full="https://picsum.photos/seed/gal-4/1400/1800" aria-label="Ampliar imagem — evento cultural">
          <img src="https://picsum.photos/seed/gal-4/700/900" alt="Artista em performance num evento cultural" loading="lazy" />
        </button>
      </div>

      <div class="masonry__item reveal" data-cat="kambwa">
        <button class="gallery-tile" data-full="https://picsum.photos/seed/gal-5/1200/900" aria-label="Ampliar imagem — multidão Kambwa Show">
          <img src="https://picsum.photos/seed/gal-5/700/560" alt="Multidão a celebrar no Kambwa Show" loading="lazy" />
        </button>
      </div>

      <div class="masonry__item reveal" data-cat="kambwa">
        <button class="gallery-tile" data-full="https://picsum.photos/seed/gal-6/1200/900" aria-label="Ampliar imagem — DJ set">
          <img src="https://picsum.photos/seed/gal-6/700/560" alt="DJ em performance ao vivo" loading="lazy" />
        </button>
      </div>

      <div class="masonry__item reveal" data-cat="corporativo" style="grid-row: span 2;">
        <button class="gallery-tile" data-full="https://picsum.photos/seed/gal-7/1400/1800" aria-label="Ampliar imagem — gala corporativa">
          <img src="https://picsum.photos/seed/gal-7/700/900" alt="Gala corporativa com mesas decoradas" loading="lazy" />
        </button>
      </div>

      <div class="masonry__item reveal" data-cat="cultural">
        <button class="gallery-tile" data-full="https://picsum.photos/seed/gal-8/1200/900" aria-label="Ampliar imagem — dança tradicional">
          <img src="https://picsum.photos/seed/gal-8/700/560" alt="Grupo de dança num festival cultural" loading="lazy" />
        </button>
      </div>

      <div class="masonry__item reveal" data-cat="video">
        <button class="gallery-tile gallery-tile--video" data-full="https://picsum.photos/seed/gal-9/1200/900" aria-label="Reproduzir vídeo — bastidores">
          <img src="https://picsum.photos/seed/gal-9/700/560" alt="Fotograma de vídeo dos bastidores" loading="lazy" />
          <span class="play-badge">▶</span>
        </button>
      </div>

      <div class="masonry__item reveal" data-cat="kambwa" style="grid-row: span 2;">
        <button class="gallery-tile" data-full="https://picsum.photos/seed/gal-10/1400/1800" aria-label="Ampliar imagem — vista aérea do público">
          <img src="https://picsum.photos/seed/gal-10/700/900" alt="Vista aérea do público no Kambwa Show" loading="lazy" />
        </button>
      </div>

    </div>
    <p id="galleryEmpty" class="hidden text-center py-16" style="color:var(--white-dim);">Sem conteúdo nesta categoria por agora.</p>
  </div>
</section>

<footer style="border-top:1px solid var(--white-faint); padding: 4.5rem 0 2rem;">
  <div class="container">
    <div class="footer-grid" style="display:grid; gap:3rem; grid-template-columns:1fr; margin-bottom:3.5rem;">
      <div>
        <div class="font-display" style="font-size:1.6rem; font-weight:700; margin-bottom:1rem;">MBWA<span style="color:var(--orange)">ENT</span></div>
        <p style="color:var(--white-dim); max-width:32ch; font-size:0.95rem; line-height:1.6;">Organização de eventos em Luanda. Experiências que ficam na memória.</p>
      </div>
      <div>
        <div class="eyebrow" style="margin-bottom:1rem;">Contactos</div>
        <ul style="list-style:none; padding:0; display:flex; flex-direction:column; gap:0.6rem; font-size:0.92rem; color:var(--white-dim);">
          <li><a href="tel:+244925577636" style="color:inherit; text-decoration:none;">+244 925 577 636</a></li>
          <li><a href="tel:+244923158516" style="color:inherit; text-decoration:none;">+244 923 158 516</a></li>
          <li><a href="mailto:mbwa.ent@outlook.pt" style="color:inherit; text-decoration:none;">mbwa.ent@outlook.pt</a></li>
          <li><a href="https://instagram.com/mbwa_ent" target="_blank" rel="noopener" style="color:inherit; text-decoration:none;">@mbwa_ent</a></li>
        </ul>
      </div>
      <div>
        <div class="eyebrow" style="margin-bottom:1rem;">Eventos</div>
        <ul style="list-style:none; padding:0; display:flex; flex-direction:column; gap:0.6rem; font-size:0.92rem; color:var(--white-dim);">
          <li><a href="evento-kambwa-show.html" style="color:inherit; text-decoration:none;">Kambwa Show 2026</a></li>
          <li><a href="eventos.html" style="color:inherit; text-decoration:none;">Próximos eventos</a></li>
          <li><a href="patrocinadores.html" style="color:inherit; text-decoration:none;">Torna-te patrocinador</a></li>
        </ul>
      </div>
      <div>
        <div class="eyebrow" style="margin-bottom:1rem;">Links rápidos</div>
        <ul style="list-style:none; padding:0; display:flex; flex-direction:column; gap:0.6rem; font-size:0.92rem; color:var(--white-dim);">
          <li><a href="sobre.html" style="color:inherit; text-decoration:none;">Sobre a Mbwa Ent</a></li>
          <li><a href="servicos.html" style="color:inherit; text-decoration:none;">Serviços</a></li>
          <li><a href="contactos.html" style="color:inherit; text-decoration:none;">Fala connosco</a></li>
        </ul>
      </div>
    </div>
    <div style="display:flex; flex-wrap:wrap; justify-content:space-between; gap:1rem; padding-top:2rem; border-top:1px solid var(--white-faint); font-size:0.8rem; color:var(--white-dim);">
      <span>© 2026 Mbwa Ent. Todos os direitos reservados.</span>
      <a href="https://instagram.com/websitesrapidos.ao" target="_blank" rel="noopener" style="color:var(--white-dim); text-decoration:none; opacity:0.6;">Made by WRAO</a>
    </div>
  </div>
</footer>

<style>
  @media (min-width: 700px) { .footer-grid { grid-template-columns: 1.4fr 1fr 1fr 1fr; } }

  .gallery-filter {
    padding: 0.4rem 0.9rem;
    border-radius: 999px;
    border: 1px solid var(--white-faint);
    color: var(--white-dim);
    background: transparent;
    cursor: pointer;
    transition: border-color 0.2s var(--ease-out), color 0.2s var(--ease-out);
  }
  .gallery-filter.is-active { border-color: var(--orange); color: var(--orange); }

  .masonry {
    columns: 1;
    column-gap: 0.9rem;
  }
  @media (min-width: 640px) { .masonry { columns: 2; } }
  @media (min-width: 1024px) { .masonry { columns: 3; } }

  .masonry__item { break-inside: avoid; margin-bottom: 0.9rem; }

  .gallery-tile {
    display: block;
    width: 100%;
    border: none;
    padding: 0;
    border-radius: var(--radius-md);
    overflow: hidden;
    position: relative;
    cursor: zoom-in;
    background: var(--graphite);
  }

  .gallery-tile img {
    width: 100%;
    display: block;
    transition: transform 0.6s var(--ease-out);
  }

  .gallery-tile:hover img { transform: scale(1.05); }

  .play-badge {
    position: absolute;
    inset: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.1rem;
    color: white;
    background: rgba(0,0,0,0.28);
  }

  /* Lightbox fullscreen */
  .lightbox {
    position: fixed;
    inset: 0;
    z-index: 200;
    background: rgba(6,6,7,0.96);
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.35s var(--ease-out);
    padding: 2rem;
  }
  .lightbox.is-open { opacity: 1; pointer-events: auto; }
  .lightbox img { max-width: 100%; max-height: 92vh; border-radius: 0.75rem; }
  .lightbox__close {
    position: absolute;
    top: 1.5rem; right: 1.5rem;
    width: 44px; height: 44px;
    border-radius: 999px;
    background: rgba(255,255,255,0.08);
    border: 1px solid var(--white-faint);
    color: white;
    font-size: 1.2rem;
    cursor: pointer;
  }
</style>

<a href="https://wa.me/244925577636" target="_blank" rel="noopener" class="wa-float" aria-label="Fala connosco no WhatsApp">
  <svg width="28" height="28" viewBox="0 0 24 24" fill="white"><path d="M12.04 2C6.58 2 2.13 6.45 2.13 11.91c0 1.75.46 3.39 1.26 4.81L2.05 22l5.4-1.42a9.87 9.87 0 0 0 4.59 1.17h.01c5.46 0 9.9-4.45 9.9-9.91C21.96 6.45 17.5 2 12.04 2zm0 18.06h-.01a8.2 8.2 0 0 1-4.18-1.14l-.3-.18-3.11.82.83-3.03-.2-.31a8.18 8.18 0 0 1-1.26-4.31c0-4.53 3.69-8.22 8.23-8.22 2.2 0 4.26.86 5.82 2.42a8.16 8.16 0 0 1 2.41 5.81c0 4.53-3.69 8.14-8.23 8.14zm4.5-6.13c-.25-.12-1.46-.72-1.68-.8-.23-.08-.39-.12-.56.12-.17.25-.64.8-.78.96-.14.17-.29.19-.53.06-.25-.12-1.04-.38-1.98-1.22-.73-.65-1.23-1.46-1.37-1.7-.14-.25-.02-.38.11-.51.11-.11.25-.29.37-.43.12-.14.16-.25.25-.41.08-.17.04-.31-.02-.43-.06-.12-.56-1.35-.77-1.85-.2-.48-.41-.42-.56-.43h-.48c-.17 0-.43.06-.66.31-.23.25-.86.84-.86 2.05s.88 2.38 1 2.55c.12.17 1.73 2.64 4.19 3.7.59.25 1.05.4 1.4.51.59.19 1.13.16 1.55.1.47-.07 1.46-.6 1.67-1.18.2-.58.2-1.08.14-1.18-.06-.1-.23-.16-.48-.28z"/></svg>
</a>

<!-- Lightbox -->
<div class="lightbox" id="lightbox">
  <button class="lightbox__close" id="lightboxClose" aria-label="Fechar">✕</button>
  <img id="lightboxImg" src="" alt="" />
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js"></script>
<script src="js/main.js"></script>
<script>
  // Filtros
  const filters = document.querySelectorAll('.gallery-filter');
  const items = document.querySelectorAll('.masonry__item');
  const emptyMsg = document.getElementById('galleryEmpty');
  filters.forEach((btn) => {
    btn.addEventListener('click', () => {
      filters.forEach((b) => b.classList.remove('is-active'));
      btn.classList.add('is-active');
      const f = btn.getAttribute('data-filter');
      let visible = 0;
      items.forEach((item) => {
        const match = f === 'todos' || item.getAttribute('data-cat') === f;
        item.style.display = match ? '' : 'none';
        if (match) visible++;
      });
      emptyMsg.classList.toggle('hidden', visible > 0);
    });
  });

  // Lightbox
  const lightbox = document.getElementById('lightbox');
  const lightboxImg = document.getElementById('lightboxImg');
  document.querySelectorAll('.gallery-tile').forEach((tile) => {
    tile.addEventListener('click', () => {
      lightboxImg.src = tile.getAttribute('data-full');
      lightboxImg.alt = tile.querySelector('img').alt;
      lightbox.classList.add('is-open');
      document.body.style.overflow = 'hidden';
    });
  });
  function closeLightbox() {
    lightbox.classList.remove('is-open');
    document.body.style.overflow = '';
  }
  document.getElementById('lightboxClose').addEventListener('click', closeLightbox);
  lightbox.addEventListener('click', (e) => { if (e.target === lightbox) closeLightbox(); });
  document.addEventListener('keydown', (e) => { if (e.key === 'Escape') closeLightbox(); });
</script>
</body>
</html>
