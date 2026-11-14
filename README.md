# DAM1M04 · Exercici004 · Strata

Reproducció acadèmica de la pàgina principal de [Strata](https://www.strata.ai/#), feta amb HTML i CSS.

**Alumnes:** _Nom Cognom 1_ · _Nom Cognom 2_

> Aquest projecte és una **reproducció acadèmica** per practicar maquetació responsive. Els logotips, les imatges, els textos i el disseny de referència són de Strata.

## Com obrir la pàgina

1. Obre la carpeta del projecte amb VS Code.
2. Clica amb el botó dret `index.html` → **Open with Live Server**.
3. Revisa-la a 1440 px, 768 px, 390 px i 360 px (eines de desenvolupador → mode dispositiu).

Cal un servidor local perquè l'animació 3D del hero carregui bé. Si s'obre l'arxiu directament, la pàgina es veu igual però potser sense el gràfic.

## Estructura

```text
DAM1M04-Exercici004/
├── index.html        → una sola pàgina, de la capçalera al peu
├── estils.css        → tots els estils, en l'ordre de la pàgina
├── assets/
│   ├── img/          → logotips i captures de producte
│   ├── fonts/        → Plus Jakarta Sans i JetBrains Mono (locals)
│   └── js/           → scripts de l'animació del hero (sense modificar)
└── README.md
```

## Decisions de maquetació

- **HTML semàntic:** `header`, `nav`, `main`, `section`, `article`, `footer`, un únic `h1` i `h2`/`h3` per a cada secció. Les dades de «From the field» són una llista de definicions (`dl`), i els passos i els serveis són llistes (`ol`/`ul`).
- **Només Flexbox**, sense Grid. Les files de targetes fan servir `flex-wrap: wrap` i `flex: 1 1 260px`, així salten de línia soles quan no hi ha espai.
- **Contenidor centrat** (`.container`): `max-width: 1200px`, `margin: 0 auto` i marges laterals.
- **Variables CSS** a `:root` per als colors, els degradats i les fonts. Els colors s'han agafat amb el comptagotes de les captures de `referencies`.
- **Capçalera fixa** amb `position: sticky; top: 0`. A diferència de `fixed`, no tapa el contingut i no cal afegir `margin-top` al `main`.
- **Text en degradat** («done», «writing off») amb `background-clip: text`.
- **Detalls decoratius** (barres de color, punts, línies dels passos) amb `::before` i `::after`, sense imatges.
- **Colors de les targetes de Governance** amb `:nth-child()` i una variable `--color`, per no repetir classes.
- **Estats** `:hover` i `:focus-visible` als enllaços (navegació amb teclat).
- **Contingut estàtic:** les xifres i la consulta d'Atlas són text fix. S'han animat només amb CSS: el cursor parpelleja, el punt de la capçalera fa pulsacions, els degradats es mouen i, en navegadors compatibles, les xifres apareixen quan entren a la pantalla (`animation-timeline: view()`). Amb `prefers-reduced-motion` s'atura tot.
- **«Book a Demo»** porta a la pàgina de demo original: <https://www.strata.ai/book-a-demo>.

## Adaptació a mòbil

- **≤ 1024 px:** les seccions de dues columnes passen a una, s'amaga la pastilla «ILTACON» i es redueixen els títols grans.
- **≤ 767 px:**
  - S'amaga la navegació de la capçalera, com a l'original; els enllaços continuen al peu.
  - S'amaga el gràfic 3D i queda el degradat.
  - Les mètriques, els serveis, els passos d'Atlas i els nodes es posen en columna.
  - Els passos de Governance es mostren en vertical amb una línia de color a l'esquerra.
- S'ha comprovat que no hi ha desplaçament horitzontal a 1440, 768, 390 i 360 px.

## Procedència dels recursos

- Disseny, textos, logotips i captures: [Strata](https://www.strata.ai/#), consultat el 19/10/2026 (material facilitat pel professor).
- Fonts: Plus Jakarta Sans i JetBrains Mono, llicència SIL OFL (`assets/fonts/*-OFL.txt`).
- Animació del hero: script original de Strata, <https://www.strata.ai/hero-graph.js>, sense modificacions.
- Biblioteques: Three.js r149 i 3d-force-graph 1.73.4, llicència MIT (`assets/js/vendor/*-LICENSE.txt`).
