[informe-estudio-brand-alkemy-2026.md](https://github.com/user-attachments/files/26332614/informe-estudio-brand-alkemy-2026.md)
# INFORME DE ESTUDIO — Brand Visual Identity Alkemy 2026

**Fuentes estudiadas:**
- `source/guide-brand--visual-identity-2026.pdf` (40 pp.)
- 45 PNGs en `ref/layout/` (layouts vacíos del master PPTX)
- 62 PNGs en `ref/example/` (slides con contenido real)
- 12 fotos en `asset/photo/` + README
- 38 logos en `asset/logos/` + README
- `slide-catalog.md`, `brand-system.md`, `design-tokens.md`, `master-layouts.md`

---

## 1. REGLAS OBSERVADAS EN ref/layout/ (OBSERVADAS, NO INVENTADAS)

### 1.1 Estructura Header/Footer constante en slides de contenido

Observado en TODOS los layouts de contenido (12–44): existe una **barra de navegación superior** (header) con 5 zonas:

| Posición | Contenido | Tipografía observada |
|----------|-----------|---------------------|
| Extremo izquierdo | `[Alkemy]` (logo texto) | ~12px, bold, negro |
| Centro-izquierda | "Presentation Title" (placeholder dashed) | ~10px, regular |
| Centro | "Section Title" (placeholder dashed) | ~10px, regular |
| Centro-derecha | "© Alkemy. All rights reserved." | ~10px, regular |
| Extremo derecho | "Page XX" | ~10px, regular |

**Footer**: No se observa footer separado en los layouts; el header concentra la navegación. Esto contradice la estructura de 3 elementos (logo izq / copyright centro / logo der) definida en slide-catalog.md para el HTML.

**Fondo de los layouts**: Gris claro #E8E8E8 ("Light Grey") es el fondo por defecto de TODOS los slides de contenido. No blanco puro.

### 1.2 Covers (layouts 01–08)

**01-cover--white-header**: Fondo Light Grey. Solo la barra header (5 placeholders). Sin contenido visual. Es la "cáscara vacía" corporativa.

**02-cover--dark-header**: Idéntico a 01 pero con fondo negro (#000000). Header con placeholders en blanco.

**03-cover--title-light**: Fondo Light Grey. Título enorme (~120px bold) posicionado en zona inferior izquierda (~65% vertical). Subtítulo arriba izquierda. Placeholder "Data" arriba derecha. Símbolo `[A]` gigante (~200px) en esquina inferior derecha. **Esta es la portada corporativa principal.**

**04-cover--title-gray**: Variante de 03 con fondo gris medio. Misma composición.

**05–08 covers gradiente BU**: Gradiente del color de BU hacia Light Grey (de izquierda a derecha). Título en zona inferior izquierda. Logo de BU en esquina inferior derecha (ej: `[Alkemy] Data.Tech.AI.`). Colores observados:
- 05: Blue #404AFF → Light Grey (Data Tech AI)
- 06: Cyan #3ED6FF → Light Grey (Retail Tech)
- 07: Red #FF2821 → Light Grey ([Alkemy]+)
- 08: Green #00DA7F → Light Grey (Nova)

### 1.3 Sections/Chapters (layouts 09–11, 15)

**10-section--chapter-title**: Fondo Light Grey. Título GIGANTE (~150px, bold, black) en zona superior izquierda, ocupando ~50% del ancho. Subtítulo de capítulo abajo izquierda (~24px bold). Mitad derecha completamente vacía. **Mucho espacio en blanco — densidad ~20%.**

**11-section--chapter-gray**: Similar pero con barra lateral gris oscuro a la derecha (~15% del ancho). Título con más área vertical disponible.

**15-section--chapter-dark**: Fondo negro. Header en blanco. Misma composición que 10 pero invertida.

### 1.4 Contenido (layouts 12–14, 16–19)

**12-content--title-body**: El workhorse. Fondo blanco. Título (~60px bold) en zona superior izquierda, ocupando ~50% del ancho. Todo el resto es espacio libre. **Densidad observada: ~10% ocupada por placeholders.**

**16-content--split-text-image**: División 50/50. Mitad izquierda: título + subtítulo + body text. Mitad derecha completa: placeholder de imagen (borde a borde en vertical). **La imagen toca el borde derecho del slide.**

**25-metrics--three-kpi**: Título arriba izquierda. 3 columnas de métricas equidistantes en zona central. Cada métrica: número grande (~80px) + label debajo (~14px). 4 placeholders de imagen en grid 2×2 en mitad derecha.

### 1.5 Quote (layout 36)

**36-quote--large-attributed**: Fondo NEGRO. Texto "Creative" centrado (~150px bold blanco) en zona central dentro de un recuadro con borde blanco fino. Atribución debajo centrada (~14px). **Estética de máximo impacto, mínima densidad.**

### 1.6 Reglas de composición transversales observadas

- **Alineación siempre a la izquierda** para títulos de contenido (nunca centrado, excepto quotes)
- **Títulos en zona superior izquierda**, nunca centrados verticalmente en slides de contenido
- **Grid implícito**: el contenido se organiza en una cuadrícula donde el título ocupa ~50% del ancho y el contenido restante el 50% derecho (o se extiende debajo)
- **Espacio negativo abundante**: la mayoría de layouts vacíos tienen <30% de superficie ocupada
- **Sin bordes decorativos**: los layouts no usan líneas, sombras ni bordes (excepto el recuadro del quote)
- **Sin iconos ni ornamentos**: cero elementos decorativos en los layouts base

---

## 2. REGLAS DE VISUAL IMAGERY DEL PDF DE GUIDELINES

### 2.1 Dualidad "Designed by humans / Powered by AI" (pp.33–40)

El sistema visual de Alkemy se basa en dos mundos de imagen complementarios:

**"Designed by humans" (fotografía real)**:
- Personas reales en situaciones candid/natural
- Tonos cálidos: naranja, rojo, coral, dorado
- Luz natural, nunca flash directo
- Imperfección aceptada (movimiento, grano)
- Estilos: close-up de rostros, actividades grupales, paisajes botánicos naturales
- **5 categorías observadas en p.35**: retrato cálido, underwater/artístico, ballet/movimiento, naturaleza/flores, paisaje nocturno

**"Powered by AI" (ilustración generativa)**:
- Arte digital, formas orgánicas abstractas
- Saturación ALTA: neón, holográfico, bioluminiscente
- Gradientes multicolor fluidos (cyan-magenta-naranja)
- Temáticas: flores generativas, esculturas holográficas, gradientes fluidos, burbujas/esferas 3D
- **5 categorías observadas en p.36**: flores neón sobre fondo caliente, gradientes fluid, escultura chrome, burbujas translúcidas 3D, textura noise abstracta

### 2.2 Reglas de uso de fotografía/ilustración

- Las fotos "humanas" aparecen siempre en la **mitad izquierda** de slides con panel lateral (como se ve en pp.4–10 del PDF)
- Las ilustraciones IA se usan como **fondos decorativos** en secciones de capítulo (pp.3, 11, 20, 24, 33)
- Las fotos NUNCA cubren toda la slide en layouts de contenido — siempre dejan espacio para texto
- En los covers por BU (pp.20–22), el gradiente reemplaza la fotografía
- **Nunca overlay oscuro sobre foto** en el master template PPTX; las fotos se muestran sin filtro
- Las fotos con texto encima usan el tagline literalmente: "Designed by humans." o "Powered by AI." como caption (p.34)

### 2.3 Pilares de diseño (p.37)

| Pilar | Descripción visual |
|-------|-------------------|
| **Maxi Typography** | Tipografía enorme como elemento visual principal. El texto ES el diseño. Fondo oscuro, tipo blanco gigante. |
| **Full White** | Foto humana tratada en duotono rojo/cyan. Fondo blanco/gris. Texto negro. Tagline visible. |
| **Brackets** | Los corchetes `[ ]` como marco visual. Se usan como overlay sobre imagen (gris translúcido sobre caballo holográfico). Marcos que enmarcan contenido. |
| **AI Interface** | Estética de interfaz digital. Grid de palabras dispersas tipo word-cloud. Foto humana en background con palabras flotando. |

---

## 3. REGLAS DE LOGO DEL PDF DE GUIDELINES

### 3.1 Variantes del logo (p.12)

| Variante | Uso |
|----------|-----|
| Primary Logo: `[Alkemy]` | El logo principal. Headers, footers, slides interiores |
| Primary Logo + Payoff: `[Alkemy]` + "Designed by humans. Powered by AI." | Portadas, slides de cierre, documentos externos |
| Business Unit Logo: `[Alkemy] Data.Tech.AI.` / `Retail Tech.` / `+` | Slides de contexto de BU |
| Sub-brand Logo: `Retex [Alkemy]` etc. | Grids de empresas, credenciales |
| Symbol: `[A]` | Favicon, watermarks, espacios reducidos |

### 3.2 Color Ways del logo (p.13)

- **Negro sobre Light Grey** — estándar para slides claras
- **Blanco sobre negro** — slides oscuras
- **Negro sobre Blue sólido** — slides de BU Data Tech
- **Logo blanco sobre foto vibrante** — cuando la foto cubre el fondo entero

### 3.3 Clear Space (p.14)

- Margen mínimo = **X1** (altura del bracket `[` del logo) alrededor de todos los lados
- Se aplica tanto al Primary Logo como al Symbol `[A]`
- **Tamaño mínimo**: Primary Logo = 140px ancho, Symbol = 45px ancho, Logo + Payoff = 390px ancho

### 3.4 Positioning del logo (p.18)

5 posiciones válidas observadas (mostradas con rectángulos verdes):
1. **Top-left + bottom-left** (composición diagonal izquierda)
2. **Top-left + top-right** (barra superior bilateral)
3. **Top-right + bottom-left** (diagonal cruzada)
4. **Center** (centrado vertical)
5. **Top-right + bottom-right** (extremo derecho, bleeding)

Para el Symbol `[A]` (p.19): mismas 5 posiciones pero en cyan (`#3ED6FF`).

### 3.5 Don'ts del logo (p.17)

PROHIBIDO:
- Outline (solo relleno sólido)
- All-caps (`[ALKEMY]`)
- Gradiente en el logo
- Sombra (drop shadow)
- Dos colores distintos en el logo
- Separar los brackets del texto
- Estirar/distorsionar
- Rotar

---

## 4. REGLAS DE TIPOGRAFÍA (pp.20–23)

### 4.1 Fuentes del sistema

| Rol | Fuente | Peso | Estilo especial |
|-----|--------|------|----------------|
| **Headline** | Alkemy Sans (propietaria) | Lowercase (minúscula con mayúscula inicial) | Kerning **-10pt** tight. Tamaño enorme (~80-150px en covers) |
| **Subline** | Aeonik Medium | 500 | Tamaño medio (~24-32px). Mismo estilo que headline pero más pequeño |
| **Body copy** | Aeonik Medium | 500 | Mixed case regular (~14-18px) |
| **Sub-headline** | Aeonik SemiBold | 600 | UPPERCASE. Labels de categoría (~11-14px) |
| **Annotation** | Aeonik Mono | Regular | UPPERCASE. URLs, footnotes (~10-11px) |
| **Button** | Aeonik Mono | Regular | UPPERCASE. CTAs (~12px, fondo negro) |

### 4.2 Reglas tipográficas críticas (pp.12-13 del ejemplo ref/)

1. **Bold Only** — Solo negritas como peso tipográfico. Jerarquía por TAMAÑO y COLOR, nunca por variación de peso (light/regular/bold)
2. **Tight Kerning** — Siempre `letter-spacing: -10pt` (≈ -1px en web) en headlines grandes
3. **Color, Not Italic** — Resaltar con color de acento, NUNCA cursiva ni subrayado
4. **Edit Not Invent** — Adaptar contenido a los templates, no crear layouts nuevos
5. **Paste & Match** — Al pegar texto, siempre "Match Destination" para mantener estilos
6. **Check Navigation Bar** — Verificar que la barra de navegación superior sea correcta

### 4.3 Fallback web (de brand-system.md)

```
Headline: 'Inter' weight 900, letter-spacing tight
Body: 'Inter' weight 400-500
Mono: 'JetBrains Mono'
```

---

## 5. REGLAS DE COLOR (pp.24–32)

### 5.1 Paleta primaria

| # | Nombre | HEX | Uso |
|---|--------|-----|-----|
| 01 | White | `#FFFFFF` | Fondos claros, texto sobre oscuro |
| 02 | Light Grey | `#E8E8E8` | **Fondo dominante** del master PPTX. Bordes, soporte |
| 03 | Dark Grey | `#BDB8B8` | Texto secundario, muted |
| 04 | Black | `#000000` | Fondos oscuros, texto principal |

### 5.2 Paleta secundaria (BU colors)

| # | Nombre | HEX | BU |
|---|--------|-----|-----|
| 05 | Green | `#00DA7F` | Master Brand, Nova |
| 06 | Blue | `#404AFF` | Data. Tech. AI. |
| 07 | Red | `#FF2821` | [Alkemy]+ Agency |
| 08 | Cyan | `#3ED6FF` | Retail Tech |

### 5.3 Paleta de acento (gradientes/decoración)

| # | Nombre | HEX | Uso |
|---|--------|-----|-----|
| 13 | Magenta | `#FF78F3` | Puntos decorativos, gradientes |
| 14 | Yellow/Lime | `#CCFD54` | Puntos decorativos, gradientes |
| 15 | Violet | `#9D5FFF` | Puntos decorativos, gradientes |
| 16 | Orange | `#FF6C18` | Puntos decorativos, gradientes |

### 5.4 Combinaciones permitidas (p.27)

**BASIC COMBINATIONS** (las 3 seguras para cada color secundario):
1. Color sólido de fondo + texto blanco
2. Fondo Light Grey + texto en color
3. Fondo negro + texto en color

**HIGHLIGHTED TEXT** (3 variantes):
4. Color de fondo + texto en color más claro (subtle)
5. Fondo Light Grey + texto en color + texto negro (mixto)
6. Fondo negro + texto en color + texto blanco (mixto)

**GRADIENTS & ACCENTS** (3 variantes):
7. Gradiente del color hacia negro + texto blanco
8. Fondo Light Grey + texto en color + puntos de acento (magenta, yellow, violet, orange)
9. Fondo negro + texto en color + puntos de acento

### 5.5 Gradientes del template (observados en ref/example/)

Los gradientes van SIEMPRE del color de BU hacia Light Grey `#E8E8E8` (de izquierda a derecha o de arriba a abajo). NUNCA color-a-color.

### 5.6 DON'TS de color (p.32)

Observados con línea roja diagonal (prohibidos):
- Texto púrpura sobre fondo cyan
- Texto naranja sobre fondo Light Grey (baja legibilidad)
- Highlight amarillo sobre fondo negro con texto negro
- Gradiente diagonal con colores no permitidos
- Texto claro sobre fondo claro (contraste insuficiente)
- Puntos de acento sobre fondo de color secundario (solo sobre primario)

---

## 6. CATÁLOGO DE ASSETS DISPONIBLES

### 6.1 Fotos (12 archivos WebP)

| Archivo | Orientación | Categoría | Uso recomendado |
|---------|-------------|-----------|-----------------|
| `photo--portrait-sunglasses-warm.webp` | Portrait 1062×1368 | Designed by humans | Hero shot, About Us, cultura |
| `photo--flowers-daisies-sky.webp` | Portrait 1060×1368 | Designed by humans | Crecimiento, frescura, apertura |
| `photo--peonies-coral-sky.webp` | Portrait 1570×2112 | Designed by humans | Premium, elegante, portada alta gama |
| `photo--team-casual-group.webp` | **Landscape** 1632×912 | Designed by humans | Equipo, cultura, "Quiénes somos" |
| `photo--abstract-gradient-layers.webp` | Portrait 1062×1362 | Powered by AI | Background cover, textura, divider |
| `photo--clouds-abstract-blue.webp` | Portrait 1026×1538 | Powered by AI | Background sutil, calma visual |
| `photo--flowers-rainbow-abstract.webp` | Portrait 1032×1370 | Powered by AI | Creatividad, diversidad, [Alkemy]+ |
| `photo--cosmos-blue-turquoise.webp` | Portrait 916×1178 | Powered by AI | Estética moderna, BU Data Tech |
| `photo--waves-gradient-fluid.webp` | Portrait 1406×1884 | Powered by AI | Tech/innovación, overview corporativo |
| `photo--cosmos-green-luminescent.webp` | Portrait 818×1228 | Powered by AI | BU Nova (verde), sostenibilidad tech |
| `photo--horse-holographic-neon.webp` | **Landscape** 1400×1114 | Powered by AI | IA, innovación radical, covers impacto |
| `photo--flowers-multicolor-vibrant.webp` | Portrait 1382×1858 | Powered by AI | Diversidad, celebración, portfolio |

### 6.2 Logos (38 PNGs transparentes)

**Master Brand (6)**:
- `logo-master--alkemy-tagline-{black|white}.png` (682×285) → Portadas, cierre
- `logo-master--alkemy-{black|white}.png` (682×249) → Headers, footers
- `logo-master--alkemy-isotype-{black|white}.png` (256×247) → Watermarks, favicon

**Business Units (8)**:
- `logo-bu--data-tech-ai-{black|white}.png` (730×214) → BU Data Tech AI
- `logo-bu--retail-tech-{black|white}.png` (730×212) → BU Retail Tech
- `logo-bu--alkemy-plus-{black|white}.png` (670×215) → BU Agency
- `logo-bu--nova-{black|white}.png` (364×216) → BU Nova

**Sub-brands (24, 12 empresas × 2 colores)**:
Connexia, Cosmic, Design Group Italia, Witailer, Retex, Venistar, LEM ICT, Mercurio Sistemi, Konvergence, Tier1, Innocv, XCC — cada una en `-black` y `-white`.

---

## 7. DISCREPANCIAS DETECTADAS

### 7.1 Fondo por defecto: Light Grey vs. White

**PDF guidelines + ref/layout/**: El fondo por defecto de TODAS las slides (incluidas las de contenido) es **Light Grey `#E8E8E8`**, no blanco. Esto se observa claramente en todos los 45 PNGs de layout.

**slide-catalog.md**: Describe `.slide-content` con "Fondo blanco". Los backgrounds del skill (`.bg1` a `.bg5`) son todos dark gradients o white/light. No hay una clase explícita para Light Grey como fondo de contenido.

**brand-system.md**: Define `.bg3` como "white/light" con gradiente `#fff → #f8f8ff → #ededff → #e4e6ff → #dde0ff` que es ligeramente azulado, NO el Light Grey neutro #E8E8E8 del master.

→ **DISCREPANCIA CRÍTICA**: El HTML debería usar `background: #E8E8E8` como fondo default de slides de contenido para replicar el master, pero el skill no tiene esta clase.

### 7.2 Header/Footer: 5 campos vs. 3 campos

**ref/layout/ (PPTX master)**: El header tiene **5 zonas**: [Alkemy] | Presentation Title | Section Title | © Alkemy. All rights reserved. | Page XX — todo en una SOLA barra superior.

**slide-catalog.md (HTML)**: Define header con **3 spans** y footer SEPARADO con otros 3 spans. La estructura es:
- Header: `<span>Credenciales 2026</span><span>Capacidades</span><span></span>`
- Footer: `<span>[A]</span><span>©Alkemy 2026</span><span>[Alkemy]</span>`

→ **DISCREPANCIA**: El PPTX real pone TODO en el header (incluyendo copyright y page number). No tiene footer visible como elemento separado. El HTML separa en header + footer.

### 7.3 Fuente: Alkemy Sans / Aeonik vs. Arial vs. Inter

**PDF guidelines (pp.21-22)**: Define **Alkemy Sans** (propietaria, lowercase) como headline y **Aeonik Medium** como subline/body.

**ref/example/ (ejemplo 11)**: Muestra que dentro del PPTX el fallback real es **Arial** (no Montserrat, no Inter).

**brand-system.md + design-tokens.md**: Define **Inter weight 900** como fallback web para headlines y **JetBrains Mono** para mono.

→ **No es discrepancia per se** (son cascadas de fallback), pero debe quedar claro: el ideal es Alkemy Sans → fallback web Inter 900 → fallback PPTX Arial Bold.

### 7.4 Logo en header: texto `[Alkemy]` vs. imagen PNG

**ref/layout/**: El header muestra `[Alkemy]` como TEXTO renderizado en la fuente del master (no una imagen PNG).

**slide-catalog.md**: Define `.alkemy-logo` como un span con CSS que genera un glifo de 20×19px — presuntamente un SVG inline o background-image.

→ **Considerar**: Para pixel-perfect HTML, el logo en header debe ser el texto `[Alkemy]` en Inter weight 900, no una imagen, para replicar la estética del PPTX.

### 7.5 Gradientes de section: BU color → Light Grey vs. dark gradients

**ref/example/ (27-31)**: Los chapter dividers usan gradiente del color de BU → Light Grey `#E8E8E8`, yendo de izquierda a derecha. Son CLAROS.

**brand-system.md**: Define `.bg-section-blue` etc. como variante "corporativa" pero los gradientes `.bg-fade-*` son del color BU → charcoal oscuro `#1A1A1A` — son OSCUROS.

→ **DISCREPANCIA**: El master PPTX usa gradientes claros (BU color → Light Grey) para chapters. El skill define gradientes oscuros (BU color → charcoal). Para replicar el master, los chapters deberían ir de `#404AFF` → `#E8E8E8`, no de `#404AFF` → `#1A1A1A`.

### 7.6 Densidad del contenido

**ref/layout/**: Los layouts del master tienen densidad MUY BAJA (~10-25% de superficie con contenido). El espacio vacío es el protagonista.

**slide-catalog.md**: Los patrones avanzados (Staircase, Compare Table, Value Grid, Ask) sugieren composiciones más densas con cards, grids, y elementos apilados que son más propias de una estética "boutique/modern" que de la estética corporativa del master.

→ **OBSERVACIÓN**: Para replicar el master PPTX fielmente, reducir la densidad de contenido por slide y priorizar espacio vacío sobre información.

### 7.7 Colores de BU en logos README vs. PDF

**PDF guidelines (p.26)** y **brand-system.md**: Retail Tech = Cyan `#3ED6FF`, [Alkemy]+ = Red `#FF2821`.

**logos/README.md**: Lista Retail Tech con color Red `#FF2820` y [Alkemy]+ con color Cyan `#3ED6FF` — **los colores están invertidos** en el README de logos respecto a las guidelines.

→ **DISCREPANCIA EN DOCUMENTACIÓN**: El README de logos tiene los colores de BU intercambiados para Retail Tech y [Alkemy]+. Según el PDF oficial (p.26 Colors Hierarchy), la asignación correcta es:
- Data Tech AI → Blue `#404AFF`
- Retail Tech → Cyan `#3ED6FF`
- [Alkemy]+ Agency → Red `#FF2821`
- Nova → Green `#00DA7F`

---

*Informe generado el 2026-03-29. Solo fase de estudio — no se ha generado ninguna slide.*
