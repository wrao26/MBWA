# Mbwa Ent — Website

Site institucional/plataforma de eventos da Mbwa Ent (Luanda, Angola). Estático — HTML5 + Tailwind CSS + GSAP + Three.js, sem build step.

## Estrutura

```
index.html                  Home (hero 3D "Event Energy Core", countdown, destaques)
sobre.html                  Sobre a Mbwa Ent
eventos.html                Listagem de eventos (com filtros Próximos/Realizados/Todos)
evento-kambwa-show.html     ⚠️ PLACEHOLDER — ver nota abaixo
galeria.html                Galeria masonry com filtros + lightbox fullscreen
patrocinadores.html         Marcas atuais, 3 níveis de parceria, formulário
servicos.html                6 serviços + processo em 4 fases
contactos.html               Formulário, telefones/email/Instagram, mapa

css/style.css                Design tokens + todos os componentes partilhados
js/energy-core.js            Cena Three.js do "Event Energy Core" (só na Home)
js/main.js                   Nav, menu mobile, countdown, GSAP ScrollTrigger reveals
partials/nav.html            Referência do markup do nav (colado manualmente em cada página)
partials/footer.html         Referência do markup do footer (idem)
```

## ⚠️ Sobre o `evento-kambwa-show.html`

Este ficheiro é um **placeholder meu**, construído como o template-tipo para páginas de evento (hero, countdown, programação, mapa, galeria, patrocinadores, FAQ, bilhetes). Vais substituí-lo pela tua própria versão da página do Kambwa Show.

Para integrar sem partir o resto do site, a tua versão só precisa de manter:
- O mesmo `<nav>` e `<footer>` (copia de qualquer outra página, ex. `sobre.html`) — para a navegação ficar consistente.
- Os `<link>`/`<script>` no `<head>` e antes do `</body>` (Tailwind CDN + config, `css/style.css`, GSAP, `js/main.js`) — para herdar o design system.
- O nome do ficheiro `evento-kambwa-show.html` — todos os outros ficheiros já apontam para este nome (nav, footer, home, listagem de eventos).

Se a tua versão tiver uma estrutura de design completamente diferente, também está bem — envia-a e eu ajusto a integração (incluindo adaptar nav/footer/tokens ao que já trouxeres, em vez de forçar o meu template).

## Antes de publicar

1. **Tailwind**: está a usar o Play CDN (`cdn.tailwindcss.com`), ótimo para pré-visualizar mas não para produção — o aviso na consola é esperado. Antes de publicar, compila com o [Tailwind CLI](https://tailwindcss.com/docs/installation) ou integra num bundler (Vite/Next), gerando um `styles.css` estático.
2. **Imagens**: todas as imagens são placeholders do `picsum.photos` — substitui pelos ficheiros reais da Mbwa Ent (fotos de eventos, vídeos, logótipos de patrocinadores).
3. **Formulários**: os 3 formulários (newsletter, patrocínio, contacto) estão só no front-end — liga a um serviço como Formspree/EmailJS, ou a um endpoint próprio, para receberes os envios de facto.
4. **Countdown**: a data está fixa em `2026-08-02T18:00:00` (hora de Luanda/WAT, sem conversão de fuso explícita) — confirma a hora exata do evento.
5. **Mapas**: os embeds do Google Maps usam pesquisa por nome de local — substitui por coordenadas exatas do recinto quando as tiveres.

## Stack (decisões tomadas)

O brief original pedia Framer Motion, que é uma biblioteca exclusiva de React — como o site é HTML/JS puro (sem bundler/React), usei **GSAP + Three.js** para todo o motion em vez disso. Tudo o resto do brief (Three.js, GSAP, TailwindCSS, SwiperJS quando necessário) foi seguido como pedido.
