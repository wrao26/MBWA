<!doctype html>
<html lang="pt">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Galeria — Mbwa Ent</title>
<meta name="description" content="Imagens e vídeos dos eventos organizados pela Mbwa Ent em Angola." />
<link rel="preconnect" href="https://fonts.googleapis.com" />
<style>
/* ==========================================================================
   MBWA ENT — Design System
   Modo: Soft/Ethereal Glass (adaptado à paleta da marca)
   Display: Clash Display · Body: General Sans · Telemetria: Space Mono
   ========================================================================== */

@import url('https://api.fontshare.com/v2/css?f[]=clash-display@600,700&f[]=general-sans@400,500,600&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&display=swap');

:root {
  /* Cor — paleta da marca, tons "profundos" em vez de puro preto/branco */
  --black-deep: #0a0a0c;
  --black-soft: #111114;
  --graphite: #1c1d21;
  --graphite-light: #2a2b30;
  --white: #f7f7f8;
  --white-dim: rgba(247, 247, 248, 0.64);
  --white-faint: rgba(247, 247, 248, 0.12);
  --orange: #ff5a1f;
  --orange-dim: rgba(255, 90, 31, 0.14);
  --blue-electric: #00b4ff;
  --red-performance: #e4002b;

  /* Motion */
  --ease-out: cubic-bezier(0.23, 1, 0.32, 1);
  --ease-in-out: cubic-bezier(0.77, 0, 0.175, 1);

  /* Layout */
  --container-max: 1440px;
  --radius-lg: 1.75rem;
  --radius-md: 1rem;
}

* { box-sizing: border-box; }
html { scroll-behavior: smooth; }

body {
  background: var(--black-deep);
  color: var(--white);
  font-family: 'General Sans', system-ui, sans-serif;
  -webkit-font-smoothing: antialiased;
  overflow-x: hidden;
}

.font-display {
  font-family: 'Clash Display', 'General Sans', sans-serif;
  letter-spacing: -0.02em;
}

.font-mono {
  font-family: 'Space Mono', monospace;
}

::selection { background: var(--orange); color: var(--black-deep); }

/* Foco visível — obrigatório */
a:focus-visible, button:focus-visible, input:focus-visible, textarea:focus-visible {
  outline: 2px solid var(--orange);
  outline-offset: 3px;
  border-radius: 4px;
}

/* Reduced motion — mantém opacidade, remove movimento */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.001ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.001ms !important;
    scroll-behavior: auto !important;
  }
}

/* ==========================================================================
   Nav — pill flutuante, morph em mobile
   ========================================================================== */

.site-nav {
  position: fixed;
  top: 1.25rem;
  left: 50%;
  transform: translateX(-50%);
  z-index: 100;
  width: min(94%, 1180px);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0.65rem 0.75rem 0.65rem 1.5rem;
  border-radius: 999px;
  background: rgba(17, 17, 20, 0.55);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border: 1px solid var(--white-faint);
  transition: background 0.4s var(--ease-out), border-color 0.4s var(--ease-out);
}

.site-nav.is-scrolled {
  background: rgba(17, 17, 20, 0.82);
  border-color: rgba(255, 90, 31, 0.25);
}

.site-nav__logo {
  font-family: 'Clash Display', sans-serif;
  font-weight: 700;
  font-size: 1.05rem;
  letter-spacing: -0.01em;
  color: var(--white);
  text-decoration: none;
}

.site-nav__logo span { color: var(--orange); }

.site-nav__links {
  display: none;
  gap: 2rem;
  font-size: 0.9rem;
  color: var(--white-dim);
}

@media (min-width: 900px) {
  .site-nav__links { display: flex; }
}

.site-nav__links a {
  position: relative;
  text-decoration: none;
  color: inherit;
  transition: color 0.25s var(--ease-out);
}

.site-nav__links a:hover,
.site-nav__links a.is-active { color: var(--white); }

.site-nav__links a.is-active::after {
  content: '';
  position: absolute;
  left: 0; right: 0; bottom: -0.4rem;
  height: 2px;
  background: var(--orange);
  border-radius: 2px;
}

.site-nav__cta {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: var(--white);
  color: var(--black-deep);
  font-size: 0.85rem;
  font-weight: 600;
  padding: 0.55rem 1.1rem;
  border-radius: 999px;
  text-decoration: none;
  transition: transform 0.25s var(--ease-out), background 0.25s var(--ease-out);
}

.site-nav__cta:hover { background: var(--orange); transform: translateY(-1px); }

.site-nav__burger {
  display: flex;
  width: 40px; height: 40px;
  border-radius: 999px;
  background: var(--white-faint);
  align-items: center;
  justify-content: center;
  border: none;
  cursor: pointer;
}

@media (min-width: 900px) { .site-nav__burger { display: none; } }

/* ==========================================================================
   Double-Bezel — componente assinatura (cards, tiles)
   ========================================================================== */

.bezel {
  padding: 0.375rem;
  border-radius: var(--radius-lg);
  background: var(--graphite);
  box-shadow: inset 0 0 0 1px rgba(255,255,255,0.05);
}

.bezel__inner {
  border-radius: calc(var(--radius-lg) - 0.375rem);
  background: var(--black-soft);
  height: 100%;
}

/* ==========================================================================
   Botões
   ========================================================================== */

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.6rem;
  padding: 0.9rem 1.6rem;
  border-radius: 999px;
  font-size: 0.95rem;
  font-weight: 600;
  text-decoration: none;
  transition: transform 0.2s var(--ease-out), background 0.25s var(--ease-out), box-shadow 0.25s var(--ease-out);
  cursor: pointer;
  border: none;
}

.btn:active { transform: scale(0.97); }

.btn--primary {
  background: var(--orange);
  color: var(--black-deep);
  box-shadow: 0 8px 30px -8px rgba(255, 90, 31, 0.55);
}

.btn--primary:hover { transform: translateY(-2px); box-shadow: 0 12px 34px -6px rgba(255, 90, 31, 0.7); }

.btn--ghost {
  background: transparent;
  color: var(--white);
  border: 1px solid var(--white-faint);
}

.btn--ghost:hover { border-color: var(--white-dim); background: rgba(255,255,255,0.04); }

.btn__icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 26px; height: 26px;
  border-radius: 999px;
  background: rgba(0,0,0,0.15);
  transition: transform 0.25s var(--ease-out);
}

.btn:hover .btn__icon { transform: translate(2px, -2px); }

/* ==========================================================================
   Utilitários de secção
   ========================================================================== */

.section { padding: clamp(4rem, 8vw, 7rem) 0; position: relative; }
.container { width: min(92%, var(--container-max)); margin-inline: auto; }

.eyebrow {
  font-family: 'Space Mono', monospace;
  font-size: 0.72rem;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: var(--orange);
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
}

.eyebrow::before {
  content: '';
  width: 6px; height: 6px;
  border-radius: 999px;
  background: var(--orange);
  box-shadow: 0 0 12px 2px var(--orange);
}

/* Grão subtil — apenas em camada fixed, nunca em containers com scroll */
.grain-overlay {
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: 2;
  opacity: 0.035;
  mix-blend-mode: overlay;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='120'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
}

/* ==========================================================================
   Menu mobile — overlay full-screen, blur pesado
   ========================================================================== */

.mobile-menu {
  position: fixed;
  inset: 0;
  z-index: 90;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: rgba(10, 10, 12, 0.9);
  backdrop-filter: blur(28px);
  -webkit-backdrop-filter: blur(28px);
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.4s var(--ease-out);
}

.mobile-menu.is-open { opacity: 1; pointer-events: auto; }

.mobile-menu__links {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.4rem;
}

.mobile-menu__links a {
  font-family: 'Clash Display', sans-serif;
  font-size: 2rem;
  color: var(--white);
  text-decoration: none;
  opacity: 0;
  transform: translateY(14px);
  transition: opacity 0.4s var(--ease-out), transform 0.4s var(--ease-out);
}

.mobile-menu.is-open .mobile-menu__links a { opacity: 1; transform: translateY(0); }

/* ==========================================================================
   WhatsApp flutuante
   ========================================================================== */

.wa-float {
  position: fixed;
  bottom: 1.75rem;
  right: 1.75rem;
  z-index: 95;
  width: 58px; height: 58px;
  border-radius: 999px;
  background: #25d366;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 10px 30px -6px rgba(37, 211, 102, 0.55);
  transition: transform 0.25s var(--ease-out);
  text-decoration: none;
}

.wa-float:hover { transform: scale(1.08) translateY(-2px); }
.wa-float:active { transform: scale(0.96); }

/* ==========================================================================
   HUD / Telemetria — countdown, badges de estado
   ========================================================================== */

.hud-card {
  font-family: 'Space Mono', monospace;
  border: 1px solid var(--white-faint);
  background: rgba(17, 17, 20, 0.6);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border-radius: var(--radius-md);
  padding: 1.1rem 1.3rem;
}

.hud-label {
  font-size: 0.68rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--white-dim);
}

.countdown {
  display: flex;
  gap: 1.1rem;
}

.countdown__unit { text-align: center; }

.countdown__value {
  font-size: clamp(1.4rem, 3vw, 2rem);
  font-weight: 700;
  color: var(--white);
  font-variant-numeric: tabular-nums;
}

.countdown__label {
  font-size: 0.62rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--orange);
}

.status-pill {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  font-family: 'Space Mono', monospace;
  font-size: 0.7rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  padding: 0.3rem 0.7rem;
  border-radius: 999px;
}

.status-pill--upcoming { background: rgba(255,90,31,0.14); color: var(--orange); }
.status-pill--done { background: rgba(255,255,255,0.08); color: var(--white-dim); }

/* ==========================================================================
   Loading screen cinematográfica
   ========================================================================== */

.site-loader {
  position: fixed;
  inset: 0;
  z-index: 999;
  background: var(--black-deep);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1.2rem;
  transition: opacity 0.6s var(--ease-out);
  /* Seguro: nunca bloqueia cliques, mesmo que o JS que o remove falhe por alguma razão */
  pointer-events: none;
  /* Seguro extra: desaparece sozinho ao fim de 2.5s mesmo sem nenhum JS a correr */
  animation: siteLoaderFailSafe 0.6s ease 2.5s forwards;
}

@keyframes siteLoaderFailSafe {
  to { opacity: 0; visibility: hidden; }
}

.site-loader__mark {
  font-family: 'Clash Display', sans-serif;
  font-size: 1.4rem;
  font-weight: 700;
  letter-spacing: 0.02em;
}

.site-loader__mark span { color: var(--orange); }

.site-loader__bar {
  width: 220px;
  height: 2px;
  background: var(--white-faint);
  border-radius: 999px;
  overflow: hidden;
}

.site-loader__bar::after {
  content: '';
  display: block;
  height: 100%;
  width: 40%;
  background: var(--orange);
  animation: loaderSweep 1.1s ease-in-out infinite;
}

@keyframes loaderSweep {
  0% { transform: translateX(-120%); }
  100% { transform: translateX(340%); }
}

/* Reveal genérico — usado pelo GSAP (main.js adiciona a classe .is-visible) */
.reveal {
  opacity: 0;
  transform: translateY(28px);
  transition: opacity 0.8s var(--ease-out), transform 0.8s var(--ease-out);
}

.reveal.is-visible { opacity: 1; transform: translateY(0); }


/* ============================================================
   Tailwind FALLBACK — utilidades essenciais em CSS puro.
   Garante que o layout funciona mesmo se cdn.tailwindcss.com
   falhar a carregar (bloqueado por rede/firewall/adblock).
   Gerado a partir das classes realmente usadas no site.
   ============================================================ */

.\-top-3 { top:-0.75rem; }
.absolute { position:absolute; }
.bg-black { background:#000; }
.bg-transparent { background:transparent; }
.block { display:block; }
.border { border-width:1px;border-style:solid; }
.border-y { border-top-width:1px;border-bottom-width:1px;border-style:solid; }
.break-all { word-break:break-all; }
.cursor-pointer { cursor:pointer; }
.flex { display:flex; }
.flex-1 { flex:1 1 0%; }
.flex-col { flex-direction:column; }
.flex-wrap { flex-wrap:wrap; }
.font-600 { font-weight:600; }
.font-700 { font-weight:700; }
.font-bold { font-weight:700; }
.font-display { font-family:'Clash Display','General Sans',sans-serif; }
.font-mono { font-family:'Space Mono',monospace; }
.gap-10 { gap:2.5rem; }
.gap-12 { gap:3rem; }
.gap-14 { gap:3.5rem; }
.gap-16 { gap:4rem; }
.gap-2 { gap:0.5rem; }
.gap-3 { gap:0.75rem; }
.gap-4 { gap:1rem; }
.gap-5 { gap:1.25rem; }
.gap-6 { gap:1.5rem; }
.gap-8 { gap:2rem; }
.gap-x-12 { column-gap:3rem; }
.gap-x-8 { column-gap:2rem; }
.gap-y-3 { row-gap:0.75rem; }
.gap-y-6 { row-gap:1.5rem; }
.grid { display:grid; }
.grid-cols-1 { grid-template-columns:repeat(1,minmax(0,1fr)); }
.grid-cols-2 { grid-template-columns:repeat(2,minmax(0,1fr)); }
.grid-cols-3 { grid-template-columns:repeat(3,minmax(0,1fr)); }
.h-28 { height:7.0rem; }
.h-fit { height:fit-content; }
.h-full { height:100%; }
.hidden { display:none; }
.inset-0 { top:0;right:0;bottom:0;left:0; }
.items-center { align-items:center; }
.items-end { align-items:flex-end; }
.items-start { align-items:flex-start; }
.justify-between { justify-content:space-between; }
.justify-center { justify-content:center; }
.justify-end { justify-content:flex-end; }
.leading-\[0\.95\] { line-height: 0.95; }
.list-none { list-style:none; }
.max-w-3xl { max-width:48rem; }
.max-w-md { max-width:28rem; }
.mb-10 { margin-bottom:2.5rem; }
.mb-2 { margin-bottom:0.5rem; }
.mb-3 { margin-bottom:0.75rem; }
.mb-4 { margin-bottom:1rem; }
.mb-5 { margin-bottom:1.25rem; }
.mb-6 { margin-bottom:1.5rem; }
.mb-8 { margin-bottom:2rem; }
.min-h-\[100dvh\] { min-height: 100dvh; }
.min-h-\[86dvh\] { min-height: 86dvh; }
.mt-1 { margin-top:0.25rem; }
.mt-10 { margin-top:2.5rem; }
.mt-12 { margin-top:3rem; }
.mt-2 { margin-top:0.5rem; }
.mt-3 { margin-top:0.75rem; }
.mt-4 { margin-top:1rem; }
.mt-5 { margin-top:1.25rem; }
.mt-6 { margin-top:1.5rem; }
.mt-7 { margin-top:1.75rem; }
.mt-8 { margin-top:2rem; }
.mt-9 { margin-top:2.25rem; }
.mx-auto { margin-left:auto;margin-right:auto; }
.object-cover { object-fit:cover; }
.opacity-60 { opacity:0.6; }
.opacity-70 { opacity:0.7; }
.opacity-90 { opacity:0.9; }
.overflow-hidden { overflow:hidden; }
.p-10 { padding:2.5rem; }
.p-5 { padding:1.25rem; }
.p-6 { padding:1.5rem; }
.p-7 { padding:1.75rem; }
.p-8 { padding:2rem; }
.pb-10 { padding-bottom:2.5rem; }
.pb-14 { padding-bottom:3.5rem; }
.pb-16 { padding-bottom:4rem; }
.pb-20 { padding-bottom:5rem; }
.pb-5 { padding-bottom:1.25rem; }
.pb-8 { padding-bottom:2rem; }
.pt-0 { padding-top:0; }
.pt-32 { padding-top:8.0rem; }
.pt-4 { padding-top:1rem; }
.pt-40 { padding-top:10.0rem; }
.px-4 { padding-left:1rem;padding-right:1rem; }
.px-5 { padding-left:1.25rem;padding-right:1.25rem; }
.py-10 { padding-top:2.5rem;padding-bottom:2.5rem; }
.py-16 { padding-top:4rem;padding-bottom:4rem; }
.py-3 { padding-top:0.75rem;padding-bottom:0.75rem; }
.py-5 { padding-top:1.25rem;padding-bottom:1.25rem; }
.relative { position:relative; }
.rounded-full { border-radius:9999px; }
.rounded-xl { border-radius:0.75rem; }
.shrink-0 { flex-shrink:0; }
.space-y-0 > * + * { margin-top: 0; }
.space-y-2 > * + * { margin-top: 0.5rem; }
.space-y-3 > * + * { margin-top: 0.75rem; }
.space-y-4 > * + * { margin-top: 1rem; }
.space-y-6 > * + * { margin-top: 1.5rem; }
.text-2xl { font-size:1.5rem; }
.text-\[0\.65rem\] { font-size: 0.65rem; }
.text-\[0\.75rem\] { font-size: 0.75rem; }
.text-\[1\.05rem\] { font-size: 1.05rem; }
.text-center { text-align:center; }
.text-lg { font-size:1.125rem; }
.text-sm { font-size:0.875rem; }
.text-xl { font-size:1.25rem; }
.text-xs { font-size:0.75rem; }
.tracking-widest { letter-spacing:0.1em; }
.uppercase { text-transform:uppercase; }
.w-20 { width:5.0rem; }
.w-fit { width:fit-content; }
.w-full { width:100%; }
.z-10 { z-index:10; }
@media (min-width: 640px) {
  .flex-row { flex-direction:row; }
  .grid-cols-2 { grid-template-columns:repeat(2,minmax(0,1fr)); }
}
@media (min-width: 768px) {
  .col-span-2 { grid-column:span 2 / span 2; }
  .flex-row { flex-direction:row; }
  .grid-cols-2 { grid-template-columns:repeat(2,minmax(0,1fr)); }
  .grid-cols-3 { grid-template-columns:repeat(3,minmax(0,1fr)); }
  .grid-cols-4 { grid-template-columns:repeat(4,minmax(0,1fr)); }
  .grid-cols-\[auto 1fr auto\] { grid-template-columns:auto_1fr_auto; }
  .items-center { align-items:center; }
  .p-10 { padding:2.5rem; }
  .p-12 { padding:3rem; }
  .p-14 { padding:3.5rem; }
  .text-3xl { font-size:1.875rem; }
  .text-left { text-align:left; }
  .w-64 { width:16.0rem; }
}
@media (min-width: 1024px) {
  .grid-cols-1 { grid-template-columns:repeat(1,minmax(0,1fr)); }
  .grid-cols-2 { grid-template-columns:repeat(2,minmax(0,1fr)); }
  .grid-cols-3 { grid-template-columns:repeat(3,minmax(0,1fr)); }
  .grid-cols-\[0\.9fr 1\.1fr\] { grid-template-columns:0.9fr_1.1fr; }
  .grid-cols-\[1\.15fr 0\.85fr\] { grid-template-columns:1.15fr_0.85fr; }
  .grid-cols-\[1\.1fr 0\.9fr\] { grid-template-columns:1.1fr_0.9fr; }
  .grid-cols-\[1fr 0\.7fr\] { grid-template-columns:1fr_0.7fr; }
  .grid-cols-\[1fr 0\.85fr\] { grid-template-columns:1fr_0.85fr; }
  .grid-cols-\[1fr 0\.8fr\] { grid-template-columns:1fr_0.8fr; }
}

</style>
<script src="https://cdn.tailwindcss.com"></script>
<script>
  if (window.tailwind) { tailwind.config = { theme: { extend: {
    colors: { black: { deep: '#0a0a0c', soft: '#111114' }, graphite: { DEFAULT: '#1c1d21', light: '#2a2b30' }, orange: '#ff5a1f', blue: { electric: '#00b4ff' }, red: { performance: '#e4002b' } },
    fontFamily: { display: ['Clash Display','General Sans','sans-serif'], body: ['General Sans','system-ui','sans-serif'], mono: ['Space Mono','monospace'] },
  } } }; }
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
<script>
/* ==========================================================================
   MBWA ENT — main.js
   Nav state, menu mobile, countdown, GSAP ScrollTrigger reveals.
   ========================================================================== */

document.addEventListener('DOMContentLoaded', () => {
  /* ---------------- Nav: estado ao fazer scroll ---------------- */
  const nav = document.getElementById('siteNav');
  if (nav) {
    const onScroll = () => nav.classList.toggle('is-scrolled', window.scrollY > 40);
    onScroll();
    window.addEventListener('scroll', onScroll, { passive: true });
  }

  /* ---------------- Menu mobile ---------------- */
  const burger = document.getElementById('navBurger');
  const mobileMenu = document.getElementById('mobileMenu');
  if (burger && mobileMenu) {
    burger.addEventListener('click', () => {
      const isOpen = mobileMenu.classList.toggle('is-open');
      burger.setAttribute('aria-expanded', String(isOpen));
      document.body.style.overflow = isOpen ? 'hidden' : '';
    });
    mobileMenu.querySelectorAll('a').forEach((a) =>
      a.addEventListener('click', () => {
        mobileMenu.classList.remove('is-open');
        document.body.style.overflow = '';
      })
    );
  }

  /* ---------------- Countdown genérico ----------------
     Uso: <div data-countdown="2026-08-02T18:00:00" ...> com filhos
     [data-cd="days|hours|minutes|seconds"]
  */
  document.querySelectorAll('[data-countdown]').forEach((el) => {
    const target = new Date(el.getAttribute('data-countdown')).getTime();
    const dEl = el.querySelector('[data-cd="days"]');
    const hEl = el.querySelector('[data-cd="hours"]');
    const mEl = el.querySelector('[data-cd="minutes"]');
    const sEl = el.querySelector('[data-cd="seconds"]');

    function tick() {
      const diff = Math.max(0, target - Date.now());
      const days = Math.floor(diff / 86400000);
      const hours = Math.floor((diff % 86400000) / 3600000);
      const minutes = Math.floor((diff % 3600000) / 60000);
      const seconds = Math.floor((diff % 60000) / 1000);
      if (dEl) dEl.textContent = String(days).padStart(2, '0');
      if (hEl) hEl.textContent = String(hours).padStart(2, '0');
      if (mEl) mEl.textContent = String(minutes).padStart(2, '0');
      if (sEl) sEl.textContent = String(seconds).padStart(2, '0');
    }
    tick();
    setInterval(tick, 1000);
  });

  /* ---------------- GSAP: reveals + Energy Core intensity ---------------- */
  if (window.gsap && window.ScrollTrigger) {
    gsap.registerPlugin(ScrollTrigger);

    gsap.utils.toArray('.reveal').forEach((el, i) => {
      ScrollTrigger.create({
        trigger: el,
        start: 'top 85%',
        onEnter: () => el.classList.add('is-visible'),
        once: true,
      });
    });

    gsap.utils.toArray('.reveal-stagger').forEach((group) => {
      const items = group.querySelectorAll(':scope > *');
      gsap.set(items, { opacity: 0, y: 24 });
      ScrollTrigger.create({
        trigger: group,
        start: 'top 82%',
        once: true,
        onEnter: () =>
          gsap.to(items, { opacity: 1, y: 0, duration: 0.7, ease: 'power3.out', stagger: 0.08 }),
      });
    });

    // Energy Core reage à secção em vista — cresce/intensifica gradualmente
    if (window.EnergyCore) {
      gsap.utils.toArray('[data-core-intensity]').forEach((section) => {
        const intensity = parseFloat(section.getAttribute('data-core-intensity'));
        const scale = parseFloat(section.getAttribute('data-core-scale') || '1');
        ScrollTrigger.create({
          trigger: section,
          start: 'top center',
          end: 'bottom center',
          onEnter: () => { EnergyCore.setIntensity(intensity); EnergyCore.setScale(scale); },
          onEnterBack: () => { EnergyCore.setIntensity(intensity); EnergyCore.setScale(scale); },
        });
      });
    }
  } else {
    // Sem GSAP disponível — mostra tudo imediatamente (degradação graciosa)
    document.querySelectorAll('.reveal').forEach((el) => el.classList.add('is-visible'));
  }

  /* ---------------- Loading screen cinematográfica ---------------- */
  const loader = document.getElementById('siteLoader');
  if (loader) {
    window.addEventListener('load', () => {
      setTimeout(() => {
        loader.style.opacity = '0';
        setTimeout(() => loader.remove(), 600);
      }, 400);
    });
  }
});

</script>
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
