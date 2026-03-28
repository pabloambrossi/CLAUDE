[plan-v4-addendum-kb.md](https://github.com/user-attachments/files/26326771/plan-v4-addendum-kb.md)
# Plan Operativo: Addendum KB — Knowledge Base G&I v2.0

**Versión**: 4.3 · Marzo 2026 · *Pipeline KB mejorado: 5 capas, 9 categorías accionables, estructura espejo, track paralelo al skill alkemy-presentations*  
**Complementa**: `plan-skill-alkemy-v4.md` (plan principal)  
**Carpeta KB**: `C:\Users\PabloAmbrossiLarios\Ontwice\ES_ALK_GTM-Growth and Innovation - Documentos\00-claude\alkemy-knowledge-base\`

---

## Por qué este addendum

El plan v4 cubre el skill de presentaciones. La Knowledge Base (KB) es el **sistema nervioso** que alimenta al skill y a toda la actividad estratégica de G&I. La KB actual (v1) tiene 66 MDs, 10 masters y un knowledge graph con ~200 aristas. Pero tiene problemas:

1. **Extracciones crudas**: los MDs son volcados de pymupdf, no redacciones profesionales
2. **Categorías poco accionables**: B1 "Macro Tendencias" es un cajón de sastre de 12 archivos
3. **Estructura plana**: todos los MDs sueltos en una carpeta, sin reflejo en las fuentes originales
4. **Sin visión global**: falta el documento ejecutivo que conecte todo

Este addendum reconstruye la KB con un **circuito virtuoso**: categorías accionables → subcarpetas en MDs → subcarpetas espejo en fuentes originales → cualquier persona o agente navega toda la KB por su estructura de carpetas.

---

## Relación con el plan principal

```
PLAN v4 (skill)                    ADDENDUM KB (este documento)
═══════════════                    ════════════════════════════

Pre-Fase (DONE) ──────────────┐
                               │
Fase 0 (assets, iconos,       │    Fase KB.0 — Reestructurar carpetas (5 capas, 9 categorías)
  docs/ pre-extraídos)  ──────┤    Fase KB.1 — Redacción inteligente
                               │    Fase KB.2 — Validación MECE → 02-categories/
Fase 1 (SKILL.md) ◄───────────┤    Fase KB.3 — Regenerar masters → 03-masters/
  └─ company-context.md ◄─────┤    Fase KB.4 — Visión global → 03-masters/
                               │    Fase KB.5 — Knowledge Graph → 04-graph/
Fase 2 (test + piloto)        │
                               │
Fase 5 (mantenimiento) ◄──────┘    Fase KB.6 — Mantenimiento continuo
                                     └─ Tarea programada: kb-sync
                                     └─ Reglas de propagación
```

### Dependencias concretas

| Del plan v4 | Depende de KB | Naturaleza |
|-------------|--------------|------------|
| `references/company-context.md` del skill | Masters posicionamiento + credenciales | El company-context.md se genera DESDE los masters |
| Slides con datos de mercado | Masters tendencias-ia-tech + tendencias-marketing-media + servicios-ofertas | Los [DATA] son la "munición" de las presentaciones |
| Narrativa SCQA en propuestas | Master frameworks-comunicacion + Visión Global | La estructura argumental viene de la KB |
| Modo express (datos por defecto) | company-context.md derivado de KB | Necesita datos fiables para los defaults |

### Cuándo ejecutar cada track

| Semana | Track Skill (plan v4) | Track KB (este addendum) |
|--------|----------------------|-------------------------|
| 1 | Fase 0: assets, iconos, docs/ | **KB.0**: Reestructurar carpetas (5 capas, 9 categorías) |
| 1 | Fase 0: assets, iconos, docs/ | **KB.1**: Redacción inteligente (primeras 5 categorías) |
| 2 | Fase 0: READMEs, inventario | **KB.1**: Redacción inteligente (últimas 4 categorías) |
| 2 | — | **KB.2**: Validación MECE → 02-categories/ |
| 3 | Fase 1: SKILL.md (YA HECHO) | **KB.3**: Regenerar masters → 03-masters/ |
| 3 | Fase 1: references restantes | **KB.4**: Visión global → 03-masters/ |
| 4 | Fase 2: montar + test | **KB.5**: Knowledge Graph → 04-graph/ |
| 4 | Fase 2: piloto early adopters | **KB.5b** → genera company-context.md v2.0 para el skill |
| 5+ | Fase 5: mantenimiento | **KB.6**: kb-sync como tarea programada |

**La KB no bloquea el skill**, pero lo mejora. El skill puede arrancar con el company-context.md v1.0 (ya creado) y actualizarse cuando la KB v2.0 esté lista.

---

## Leyenda de herramientas (misma que plan v4)

| Icono | Herramienta | Cuándo usarla |
|-------|-------------|---------------|
| 🟦 CHAT | Claude Chat + Proyecto | Pensar, diseñar, validar tesis |
| 🟩 COWORK | Claude Cowork (Desktop) | Ejecutar sobre archivos locales |
| 🟥 CODE | Claude Code (terminal) | Git, scripts, validación técnica |
| ⬜ MANUAL | Tú manualmente | Decisiones, revisión humana |

---

## Las 9 categorías accionables

El criterio de diseño: **"¿cuándo necesito esta información y para qué la acciono?"** — no "¿de qué tema habla el documento?".

| # | Carpeta | Pregunta que responde | Cuándo la abro | Archivos est. |
|---|---------|----------------------|----------------|---------------|
| 1 | `tendencias-ia-tech/` | "¿Qué está pasando en IA y tecnología que crea urgencia?" | Argumentar el "por qué ahora" en cualquier propuesta | ~10 |
| 2 | `tendencias-marketing-media/` | "¿Qué demanda el mercado de agencias y CMOs?" | Propuestas de Agency, media, martech | ~8 |
| 3 | `regulacion/` | "¿Qué obliga la regulación y qué oportunidad crea?" | Propuestas compliance, FSI, AI Act/DORA | ~3 |
| 4 | `servicios-ofertas/` | "¿Qué podemos vender que sea nuevo o diferencial?" | Diseñar máquinas de venta: GEO, CRO, Martech, AI agents, CODEXA | ~10 |
| 5 | `posicionamiento/` | "¿Quién es Alkemy y por qué elegirnos?" | Slide "about us", propuesta de valor, competitive positioning | ~6 |
| 6 | `credenciales/` | "¿Qué hemos entregado y con qué resultados?" | Proof points en propuestas, credenciales por vertical | ~8 |
| 7 | `benchmark-competitivo/` | "¿Cómo comparamos contra el mercado?" | Posicionarnos vs competidores, justificar pricing, sizing | ~5 |
| 8 | `operaciones-internas/` | "¿Qué estamos construyendo y cómo nos organizamos?" | Plan G&I para Duccio, business review, org chart, herramientas | ~10 |
| 9 | `frameworks-comunicacion/` | "¿Cómo estructuro la narrativa?" | Antes de armar cualquier presentación: Minto, Knaflic, guías | ~4 |

### Migración desde los bloques B1-B9

| Antes (B1-B9) | Ahora | Por qué cambia |
|---------------|-------|----------------|
| B1 "Macro Tendencias" (12 archivos) | Se divide: docs tech → `tendencias-ia-tech/`, docs internos → `operaciones-internas/` | B1 era demasiado grande y mezclaba mercado externo con análisis internos |
| B2 "Tech Industry" (4 archivos) | Se absorbe en `tendencias-ia-tech/` | Demasiado pequeño; Thoughtworks y Capgemini son tendencias tech |
| B3 "Agency & Marketing" (9 archivos) | → `tendencias-marketing-media/` | Mismo concepto, nombre más accionable |
| B4 "Regulación" (3 archivos) | → `regulacion/` | Directo, sin cambio de concepto |
| B5 "Nuevas Capacidades" (8 archivos) | → `servicios-ofertas/` | El foco pasa de "capacidades que tenemos" a "ofertas que vendemos" |
| B6 "Posicionamiento" (6 archivos) | → `posicionamiento/` | Directo |
| B7 "Credenciales + Benchmark" (11 archivos) | Se divide: casos → `credenciales/`, benchmark → `benchmark-competitivo/` | Son dos acciones distintas: probar vs. comparar |
| B8 "Ejecución Interna" (7 archivos) | → `operaciones-internas/` (+ archivos internos de B1) | Consolidar todo lo internal-facing |
| B9 "Frameworks" (4 archivos) | → `frameworks-comunicacion/` | Nombre más claro |
| Especial "Nuevas Prácticas" (2 archivos) | → `servicios-ofertas/` | Son ofertas vendibles, no una categoría separada |

---

## Arquitectura de carpetas KB — 5 capas

```
00-claude/
├── alkemy-corporate-slides/              ← Assets del skill (plan v4)
│   └── docs/company-context.md           ← DERIVADO de masters posicionamiento + credenciales
│
└── alkemy-knowledge-base/                ← Knowledge Base G&I
    │
    ├── 00-fuentes/                       ← CAPA 0: Originales (solo lectura)
    │   ├── tendencias-ia-tech/           ← PDFs, PPTXs agrupados por categoría
    │   ├── tendencias-marketing-media/
    │   ├── regulacion/
    │   ├── servicios-ofertas/
    │   ├── posicionamiento/
    │   ├── credenciales/
    │   ├── benchmark-competitivo/
    │   ├── operaciones-internas/
    │   └── frameworks-comunicacion/
    │
    ├── 01-fuentes-md/                    ← CAPA 1: Redacciones (espejo de 00-fuentes/)
    │   ├── tendencias-ia-tech/
    │   │   ├── gartner-cio-survey-spain-2026.md
    │   │   ├── mckinsey-tech-agenda-2026.md
    │   │   ├── bcg-ai-radar-2026.md
    │   │   └── ...
    │   ├── tendencias-marketing-media/
    │   │   ├── iab-agentic-future-es.md
    │   │   ├── kantar-marketing-trends-2026.md
    │   │   └── ...
    │   ├── regulacion/
    │   │   ├── law-ai-act.md
    │   │   ├── law-dora.md
    │   │   └── ...
    │   ├── servicios-ofertas/
    │   ├── posicionamiento/
    │   ├── credenciales/
    │   ├── benchmark-competitivo/
    │   ├── operaciones-internas/
    │   └── frameworks-comunicacion/
    │
    ├── 02-categories/                    ← CAPA 2: Metadatos de clasificación
    │   ├── INDEX.md                      ← Índice maestro: archivo → categoría
    │   ├── block-definitions.md          ← Definición formal de cada categoría
    │   └── VALIDACION-MECE.md            ← Último informe de validación
    │
    ├── 03-masters/                       ← CAPA 3: Síntesis cruzada
    │   ├── master-tendencias-ia-tech.md
    │   ├── master-tendencias-marketing-media.md
    │   ├── master-regulacion.md
    │   ├── master-servicios-ofertas.md
    │   ├── master-posicionamiento.md
    │   ├── master-credenciales.md
    │   ├── master-benchmark-competitivo.md
    │   ├── master-operaciones-internas.md
    │   ├── master-frameworks-comunicacion.md
    │   └── VISION-GLOBAL.md
    │
    └── 04-graph/                         ← CAPA 4: Grafo + reglas
        ├── KNOWLEDGE_GRAPH.md
        ├── PROPAGATION-RULES.md
        └── CHANGELOG.md
```

### El circuito virtuoso

```
1. Cowork lee todos los MDs planos en 01-fuentes-md/
         │
         ▼
2. Clasifica en 9 categorías → 02-categories/INDEX.md
         │
         ▼
3. Tú validas → OK
         │
         ▼
4. Cowork crea subcarpetas en 01-fuentes-md/ y mueve los MDs
         │
         ▼
5. Cowork replica la MISMA estructura en 00-fuentes/ y mueve los originales
         │
         ▼
6. Ahora ambas carpetas son un espejo:
   00-fuentes/regulacion/Ley-AI-Act.pdf ↔ 01-fuentes-md/regulacion/law-ai-act.md
         │
         ▼
7. Llega un documento nuevo → ¿en qué carpeta va?
   → Mira block-definitions.md → lo pones en la carpeta correcta
   → Cowork lo redacta → actualiza el master → propaga por el grafo
```

---

## Fase KB.0 — Reestructurar carpetas

> *Crear las 5 capas con subcarpetas por categoría y mover todos los archivos.*

**🟩 COWORK** · Apuntar a `...\00-claude\alkemy-knowledge-base\`

### Prompt KB.0 (copiar literal en Cowork)

```
Necesito reestructurar completamente la Knowledge Base. Hay 3 carpetas actuales 
(00-fuentes/, 01-fuentes-md/, 02-knowledge-base/) y necesito migrar a una 
estructura de 5 capas con subcarpetas por categoría.

PASO 1 — CREAR ESTRUCTURA DE CARPETAS NUEVAS:

En 01-fuentes-md/, crear estas 9 subcarpetas:
- tendencias-ia-tech/
- tendencias-marketing-media/
- regulacion/
- servicios-ofertas/
- posicionamiento/
- credenciales/
- benchmark-competitivo/
- operaciones-internas/
- frameworks-comunicacion/

Crear las mismas 9 subcarpetas en 00-fuentes/.

Crear las carpetas nuevas:
- 02-categories/
- 03-masters/
- 04-graph/

PASO 2 — CLASIFICAR Y MOVER LOS MDs:

Lee TODOS los archivos .md en 01-fuentes-md/ (están sueltos, sin subcarpetas).
Para cada uno, decide en qué categoría va según estas reglas:

| Categoría | Qué va aquí | Qué NO va aquí |
|-----------|------------|----------------|
| tendencias-ia-tech/ | Informes de consultoras sobre IA, tech, cloud, agentic AI, sovereign AI, modernización legacy. Gartner, McKinsey, BCG, Deloitte Tech, Thoughtworks, Capgemini. | Nada de marketing, agency, ni documentos internos de Alkemy |
| tendencias-marketing-media/ | Informes sobre marketing, media, advertising, CMO trends, agency evolution. IAB, Kantar, Deloitte Marketing, DataReportal. | Nada de tech puro ni de servicios específicos de Alkemy |
| regulacion/ | Legislación EU: AI Act, DORA. Análisis de compliance como oportunidad. | No meter propuestas comerciales de compliance (esas van a servicios-ofertas/) |
| servicios-ofertas/ | Propuestas de nuevas prácticas, análisis GEO, propuestas martech, CRO partnerships, análisis de servicios vendibles. | No meter estudios de mercado genéricos (esos van a tendencias) |
| posicionamiento/ | Propuesta de valor de Alkemy, replanteamiento estratégico, plan G&I, welcome/first steps, descripción de BUs y servicios. | No meter credenciales de proyectos específicos |
| credenciales/ | Decks de credenciales por vertical (FSI, Energy, Data), casos de éxito con resultados medibles. | No meter benchmark competitivo |
| benchmark-competitivo/ | Análisis de competidores, benchmark data (xlsx), comparativas de mercado, positioning maps. | No meter credenciales propias |
| operaciones-internas/ | Business review, plan de iniciativas IA, organigrama, plan UX, herramientas (agency tools), SDLC integration, información operativa interna. | Nada client-facing |
| frameworks-comunicacion/ | Minto Pyramid, Storytelling with Data (Knaflic), guía de presentaciones de alto impacto, frameworks narrativos. | No meter contenido real — solo metodología |

Para cada archivo, muéstrame tu clasificación ANTES de mover:
| Archivo | Categoría propuesta | Razón breve |

Espera mi OK antes de mover los archivos a las subcarpetas.

PASO 3 — MOVER FUENTES ORIGINALES (espejo):

Después de mover los MDs, replica los movimientos en 00-fuentes/.
Para cada MD movido, busca su archivo original correspondiente en 00-fuentes/ 
(el campo "source:" del frontmatter indica el nombre del original) y muévelo 
a la misma subcarpeta.

Si un original no tiene MD correspondiente, déjalo suelto en 00-fuentes/ y 
repórtalo como "huérfano".

PASO 4 — MOVER MASTERS Y GRAFO:

- Todos los master-b*.md y master-especial-*.md de 02-knowledge-base/ → 03-masters/
- KNOWLEDGE_GRAPH.md de 02-knowledge-base/ → 04-graph/
- Si existe VISION-GLOBAL.md → 03-masters/

PASO 5 — CREAR ARCHIVOS INICIALES:

a) 02-categories/INDEX.md:
   # Knowledge Base — Índice por Categorías
   **Updated:** 2026-03-29 | **Total archivos:** [contar]
   
   ## tendencias-ia-tech/
   | Archivo | Contenido (1 línea) |
   [listar los MDs que moviste a esta subcarpeta]
   
   [repetir para cada categoría]

b) 02-categories/block-definitions.md:
   # Definición de Categorías
   
   ## tendencias-ia-tech/
   - **Pregunta que responde:** ¿Qué está pasando en IA y tecnología que crea urgencia?
   - **Cuándo se usa:** Argumentar "por qué ahora" en propuestas
   - **Criterio de inclusión:** Informes de consultoras sobre IA, tech, cloud, agentic AI
   - **Criterio de exclusión:** Nada de marketing, agency, ni documentos internos
   - **Archivos actuales:** [N]
   
   [repetir para cada categoría con los criterios de la tabla del Paso 2]

c) 04-graph/PROPAGATION-RULES.md:
   Extraer las secciones de "Reglas de Propagación" del KNOWLEDGE_GRAPH.md 
   y copiarlas aquí como archivo independiente.

d) 04-graph/CHANGELOG.md:
   # Changelog del Knowledge Graph
   | Fecha | Versión | Cambios |
   |-------|---------|---------|
   | 2026-03-29 | pre-2.0 | Reestructuración: 5 capas, 9 categorías accionables |

PASO 6 — LIMPIEZA:

- Eliminar 02-knowledge-base/ SOLO si está completamente vacía
- Si quedaron archivos sueltos en 01-fuentes-md/ (no clasificados), listarlos
- Si quedaron archivos sueltos en 00-fuentes/ (huérfanos), listarlos

PASO 7 — VERIFICACIÓN:

Muéstrame:
1. Árbol de carpetas final con conteo de archivos por subcarpeta
2. Lista de archivos que no pudiste clasificar (si hay)
3. Lista de originales huérfanos en 00-fuentes/ (si hay)
```

### Output esperado

```
alkemy-knowledge-base/
├── 00-fuentes/          (63 archivos en 9 subcarpetas)
├── 01-fuentes-md/       (66 archivos en 9 subcarpetas)
├── 02-categories/       (3 archivos)
├── 03-masters/          (10-11 archivos)
└── 04-graph/            (3 archivos)
```

**⬜ MANUAL** · Antes de que Cowork mueva los archivos:

1. Revisa la tabla de clasificación que propone
2. Corrige si algún archivo está mal clasificado
3. Da OK para que ejecute los movimientos
4. Después verifica en el explorador de archivos que todo está correcto

---

## Fase KB.1 — Redacción inteligente de fuentes

> *Reemplaza las transcripciones crudas con redacciones profesionales.*

**🟩 COWORK** · Apuntar a `...\00-claude\alkemy-knowledge-base\`

**Proceso**: categoría por categoría. Cowork lee los MDs actuales (ya movidos a subcarpetas), los reescribe, y espera OK antes de pasar a la siguiente categoría.

### Prompt KB.1 (copiar literal en Cowork)

```
CONTEXTO: Estoy reconstruyendo la Knowledge Base del equipo de Growth & Innovation 
de Alkemy España. En 01-fuentes-md/ hay 66 archivos markdown organizados en 9 
subcarpetas por categoría. Son transcripciones crudas de los originales. Necesito 
que los reescribas como redacciones inteligentes.

TAREA: Para CADA archivo .md en 01-fuentes-md/, léelo completo y genera una versión 
mejorada que REEMPLACE al archivo actual (mismo nombre, misma subcarpeta). 
NO es una transcripción — es una redacción profesional.

REGLAS DE REDACCIÓN:

1. HEADER ESTÁNDAR (obligatorio en cada archivo):
   ---
   source: [nombre-archivo-original en 00-fuentes/]
   category: [nombre de la subcarpeta, e.g. tendencias-ia-tech]
   extracted: 2026-03-29
   version: 2.0
   ---

2. CONTENIDO: Redacta como un analista senior que lee el documento original y 
   escribe un briefing ejecutivo COMPLETO para su equipo. No resumas en exceso — 
   captura TODA la sustancia, pero redactada con lógica argumentativa:
   - ¿Cuál es la tesis principal del documento?
   - ¿Qué argumentos la soportan?
   - ¿Qué datos cuantitativos presenta?
   - ¿Qué implicaciones tiene para Alkemy?

3. ELIMINAR RUIDO: Quitar headers repetidos de página, paginación ("--- PAGE N ---"), 
   texto de navegación, disclaimers genéricos, biografías de autores, índices, notas 
   al pie irrelevantes, texto de slides sin contexto ("An Alkemy Deck.", "ALKEMY | 2026").

4. PRESERVAR DATOS: Todo dato cuantitativo (%, €, fechas, rankings, nombres propios, 
   citas directas de fuentes) debe mantenerse con tag [DATA] al inicio de línea.

5. SECCIONES OBLIGATORIAS para cada archivo:

   ## Tesis principal
   [1-2 párrafos: qué dice este documento y por qué importa]
   
   ## Argumentos y hallazgos clave
   [Cuerpo principal redactado con subsecciones lógicas — headers ###]
   
   ## Key Data
   [DATA] [cada dato cuantitativo en línea separada]
   
   ## Relevancia para Alkemy
   [2-3 bullets: qué puede hacer Alkemy con esta información]

6. LONGITUD según densidad del original:
   - PDF denso de consultora (Gartner, McKinsey, BCG): 1500-2000 palabras
   - Credencial interna o presentación de 10-15 slides: 500-800 palabras
   - Análisis o propuesta generada por G&I: 800-1200 palabras
   - Legislación (AI Act, DORA): 1500-2000 palabras (preservar estructura legal)

7. NO INVENTAR: Si el documento original no dice algo, no lo añadas. Los datos 
   [DATA] deben ser exactamente los del original.

PROCESO:
- Empieza por la categoría tendencias-ia-tech/ (~10 archivos)
- Cuando termines esta categoría, muéstrame:
  · Cuántos archivos procesaste
  · El título de "Tesis principal" de cada uno (1 línea)
  · Cualquier problema (archivo corrupto, contenido vacío, etc.)
- Espera mi OK antes de continuar con la siguiente categoría
- Orden de categorías:
  1. tendencias-ia-tech/
  2. tendencias-marketing-media/
  3. regulacion/
  4. servicios-ofertas/
  5. posicionamiento/
  6. credenciales/
  7. benchmark-competitivo/
  8. operaciones-internas/
  9. frameworks-comunicacion/

IMPORTANTE: Guarda cada archivo con el MISMO nombre en la MISMA subcarpeta 
(sobreescribe). El campo "version: 2.0" lo distingue de la versión anterior.
```

### Output esperado

66 MDs reescritos con calidad profesional. Validación intermedia por categoría.

### Estimación de tiempo

~2-3 sesiones de Cowork. Las categorías más pesadas son tendencias-ia-tech/ (~10 archivos densos) y operaciones-internas/ (~10 archivos variados). Regulacion/ y frameworks-comunicacion/ son rápidas (3-4 archivos).

### Posibles problemas y solución

| Problema | Solución |
|----------|----------|
| Cowork pierde contexto en categoría grande | Dividir en sub-lotes: "procesa solo los primeros 5 de tendencias-ia-tech/" |
| Archivo fuente no legible (PDF escaneado) | Marcar como "[REQUIRES_OCR]" y procesar aparte con Claude Code multimodal |
| MD actual tiene contenido que no está en el original | Marcar como "[GENERATED_CONTENT]" para investigar |
| Cowork intenta resumir demasiado | Recordar: "entre 500-2000 palabras según densidad" |

---

## Fase KB.2 — Validación de categorización MECE

> *Verificar que la clasificación en 9 categorías es correcta con el contenido ahora bien redactado.*

**🟩 COWORK** · Misma carpeta, después de completar KB.1

### Prompt KB.2 (copiar literal)

```
CONTEXTO: Acabo de reescribir todos los archivos de 01-fuentes-md/ con redacción 
inteligente (version 2.0). Están organizados en 9 subcarpetas por categoría. 
Necesito validar que la clasificación es correcta.

TAREA: 
1. Lee TODOS los archivos de TODAS las subcarpetas de 01-fuentes-md/
2. Para cada archivo, verifica:
   - ¿La categoría asignada (subcarpeta donde está) es la más apropiada?
   - ¿Hay algún archivo que encajaría mejor en otra categoría?
   - ¿Hay contenido que cruza 2 categorías y debería señalarse como cross-category?
   - ¿Hay archivos redundantes que dicen esencialmente lo mismo?

3. Genera un INFORME DE VALIDACIÓN MECE:

   # Informe de Validación MECE — 2026-03-29
   
   ## Resumen
   - Total archivos evaluados: [N]
   - Bien clasificados: [N]
   - Reclasificaciones propuestas: [N]
   - Archivos redundantes detectados: [N]
   
   ## Archivos bien clasificados
   [Lista agrupada por categoría — solo nombres]
   
   ## Reclasificaciones propuestas
   | Archivo | Categoría actual | Categoría propuesta | Razón |
   
   ## Archivos con contenido cross-category significativo
   | Archivo | Categoría principal | Categorías secundarias | Contenido que cruza |
   
   ## Archivos potencialmente redundantes
   | Archivo A | Archivo B | % solapamiento estimado | Acción propuesta |
   (Opciones: fusionar, mantener ambos con nota, eliminar uno)
   
   ## Categorías a revisar
   [Solo si alguna categoría tiene demasiados o muy pocos archivos, 
   o si la definición no funciona bien]

4. Actualiza 02-categories/block-definitions.md con las definiciones finales 
   de cada categoría (incluyendo conteo de archivos actualizado)

5. Actualiza 02-categories/INDEX.md con el índice completo

6. NO muevas ningún archivo. Solo presenta el informe. Yo decido.

Guarda el informe como: 02-categories/VALIDACION-MECE.md
```

### Tu intervención

**⬜ MANUAL** · Revisar el informe y decidir:

1. Para cada reclasificación propuesta: ¿acepto? → Cowork mueve el archivo y actualiza frontmatters
2. Para cada redundancia: ¿fusiono, mantengo, o elimino?

Después de decidir:

```
Ejecuta los siguientes cambios de la validación MECE:
[pegar decisiones]
Mueve los archivos en 01-fuentes-md/ Y en 00-fuentes/ (espejo).
Actualiza 02-categories/INDEX.md con la estructura final.
Actualiza los frontmatters de los archivos reclasificados.
```

---

## Fase KB.3 — Regenerar masters

> *Síntesis cruzada profesional desde las fuentes v2.0 validadas.*

**🟩 COWORK** · Misma carpeta, después de KB.2

### Prompt KB.3 (copiar literal)

```
CONTEXTO: Los archivos de 01-fuentes-md/ están reescritos (v2.0) y la categorización 
MECE está validada. Necesito generar 9 masters en 03-masters/, uno por categoría.

TAREA: Para CADA categoría, lee TODOS los archivos de su subcarpeta en 01-fuentes-md/ 
y genera un master en 03-masters/.

NOMENCLATURA: master-[nombre-categoria].md
Ejemplo: master-tendencias-ia-tech.md, master-regulacion.md

ESTRUCTURA OBLIGATORIA de cada master:

# Master — [Nombre legible de la categoría]
## Síntesis de conocimiento para Growth & Innovation Alkemy España

---
category: [nombre-carpeta]
source_files: [lista completa de archivos de la categoría]
total_sources: [N]
updated: 2026-03-29
version: 2.0
---

## Tesis de la categoría
[1 párrafo denso: la conclusión principal que emerge de cruzar TODAS las fuentes 
de esta categoría. No es un resumen archivo por archivo — es el argumento que 
construyen juntas. Debe poder usarse como "elevator pitch".]

## Narrativa de síntesis
[3-5 párrafos que cuentan la HISTORIA. Estructura argumentativa:
- Párrafo 1: El contexto/situación
- Párrafo 2: El cambio/complicación que crea urgencia
- Párrafo 3: Las evidencias que convergen
- Párrafo 4: Lo que esto significa en concreto
- Párrafo 5 (si aplica): Lo que aún no sabemos

Cruza datos de diferentes fuentes. Cita fuentes entre paréntesis (fuente: 
nombre-archivo.md). Debe poder leerse de forma independiente.]

## Key Data — Consolidado
[TODOS los [DATA] de los archivos fuente, deduplicados y organizados por subtema. 
Si dos fuentes dan cifras diferentes, incluir ambas y marcar la discrepancia.]

[DATA] dato 1 — (fuente: archivo.md)
[DATA] dato 2 — (fuente: archivo.md)

## Tensiones y contradicciones
[OBLIGATORIO: mínimo 2 tensiones por master. Formato:

**Tensión 1: [título descriptivo]**
[Fuente A dice X]. Sin embargo, [Fuente B dice Y]. La reconciliación más probable 
es [Z], lo que implica [implicación para Alkemy].

Si no encuentras tensiones, busca mejor — las hay siempre.]

## Implicaciones para Alkemy
[Bullets concretos y accionables. Cada uno con:
- **Qué hacer**: acción específica
- **Quién**: owner potencial (G&I, DTC, Agency, Dirección, Ventas)
- **Urgencia**: ahora / Q2 2026 / segundo semestre / exploratorio
- **Dependencia**: qué necesita para ejecutarse]

## Conexiones con otras categorías
[Lista: qué otros masters están relacionados y por qué.

→ master-[X].md — [razón de la conexión]
→ master-[Y].md — [razón de la conexión]]

---

PROCESO:
- Empieza por tendencias-ia-tech/
- ANTES de escribir el master completo, muéstrame solo la "Tesis de la categoría" 
  (1 párrafo). Espera mi OK.
- Con mi OK, genera el master completo
- Orden:
  1. master-tendencias-ia-tech.md
  2. master-tendencias-marketing-media.md
  3. master-regulacion.md
  4. master-servicios-ofertas.md
  5. master-posicionamiento.md
  6. master-credenciales.md
  7. master-benchmark-competitivo.md
  8. master-operaciones-internas.md
  9. master-frameworks-comunicacion.md

REGLA CRÍTICA: Síntesis, NUNCA concatenación. Si suena como "el archivo A dice X, 
el archivo B dice Y", está MAL. Debe sonar como "el mercado muestra una convergencia 
entre X e Y que crea una oportunidad Z".

REGLA DE DATOS: Los [DATA] nunca se inventan. Si no aparece en ninguna fuente, no existe.

Guarda cada master en: 03-masters/master-[nombre-categoria].md
```

### Output esperado

9 masters v2.0, cada uno validado por tesis antes de generarse completo.

### Tu intervención

Para cada categoría:

1. Cowork te muestra la tesis (1 párrafo)
2. Evalúas: ¿captura la esencia? ¿falta un ángulo?
3. OK → Cowork genera el master completo
4. Revisa "Tensiones" e "Implicaciones" — son las secciones de más valor

---

## Fase KB.4 — Visión global

> *Documento ejecutivo que sintetiza toda la KB.*

**🟩 COWORK** · Misma carpeta, después de KB.3

### Prompt KB.4 (copiar literal)

```
CONTEXTO: Los 9 masters (v2.0) están completos en 03-masters/. Necesito un 
documento de VISIÓN GLOBAL que sintetice toda la Knowledge Base.

TAREA: Lee los 9 masters y genera:

# Visión Global — Knowledge Base G&I Alkemy España
## Marzo 2026

---
sources: 9 masters, ~66 archivos fuente
updated: 2026-03-29
version: 1.0
---

## El argumento en 30 segundos
[3 frases que capturan la esencia de TODA la KB. Si Duccio solo lee esto, 
debe entender el mensaje. Sin jerga.]

## Las 5 grandes tesis
[5 conclusiones que emergen de CRUZAR categorías — no resúmenes individuales. 
Son insights que solo aparecen al conectar tendencias-ia-tech con regulacion, 
o servicios-ofertas con benchmark-competitivo.

Cada tesis en 1 párrafo con el insight + datos de soporte + implicación.]

## Mapa de oportunidades
| Oportunidad | Evidencia (categoría) | Tamaño estimado | Urgencia | Owner |
|-------------|----------------------|-----------------|----------|-------|
[8-12 oportunidades concretas, ordenadas por impacto × urgencia]

## Riesgos y puntos ciegos
[Qué NO sabemos. Qué asumimos sin datos. Dónde podríamos estar equivocados. 
Mínimo 5.]

## Las 3 tensiones más importantes
[De todas las tensiones de los 9 masters, las 3 que más impactan la estrategia.
Cada una: la tensión + por qué importa + cómo navegarla.]

## Agenda de acción — Top 10
| # | Acción | Qué | Quién | Cuándo | Depende de |
|---|--------|-----|-------|--------|------------|
[Acciones VENDIBLES o CONSTRUÍBLES, no reflexiones teóricas.]

Guarda como: 03-masters/VISION-GLOBAL.md
```

---

## Fase KB.5 — Knowledge Graph v2.0

> *Regenerar el grafo completo desde los masters v2.0.*

**🟩 COWORK** · Misma carpeta, después de KB.4

### Prompt KB.5 (copiar literal)

```
CONTEXTO: Toda la KB está reconstruida: ~66 MDs redactados (v2.0) en 9 categorías, 
9 masters regenerados, visión global creada. Necesito regenerar el Knowledge Graph.

TAREA: Lee TODOS los archivos (01-fuentes-md/ completo + 03-masters/ completo) 
y genera un Knowledge Graph v2.0.

IMPORTANTE: NO copiar el grafo v1.2 y editar. Regenerar DESDE CERO.

ESTRUCTURA (12 secciones):

## 1. Tipos de nodos
| Tipo | Descripción | Cantidad |
SOURCE, MASTER, CONCEPT, ENTITY, VISION

## 2. Tipos de aristas
8 tipos: SYNTHESIZES, CONTAINS, RELATED_TO, REINFORCES, CONTRADICTS, 
DEPENDS_ON, TRIGGERS_UPDATE, CROSS_CATEGORY (renombrado de CROSS_BLOCK)

## 3. Registro de Nodos Concepto
| ID | Concepto (PascalCase) | Categorías donde aparece | Archivos clave |
Un concepto es transversal si aparece en 2+ categorías.

## 4. Registro de Entidades
| ID | Entidad | Tipo | Categorías | Archivos clave |

## 5. Aristas Cross-Category
Desde la sección "Conexiones con otras categorías" de cada master.

## 6. Aristas Reinforces / Contradicts
Desde las secciones "Tensiones" de cada master.

## 7. Matriz de Impacto
| Si el nuevo doc es de... | Actualizar master | Revisar también | ¿Actualizar company-context.md? |

## 8. Mapa de Conceptos por Categoría
Diagrama ASCII.

## 9. Reglas de Propagación (6 reglas)
Mantener las 5 existentes adaptadas a categorías + añadir:

### Regla 6: Actualización de la KB → actualizar el skill
Si se actualiza master-posicionamiento.md o master-credenciales.md:
→ Regenerar 00-claude/alkemy-corporate-slides/docs/company-context.md
→ Verificar consistencia de cifras, clientes y servicios
→ Si hay cambio sustancial → re-testear skill

Guardar reglas TAMBIÉN como: 04-graph/PROPAGATION-RULES.md

## 10. Estadísticas del Grafo

## 11. Versioning
| 2.0 | 2026-03-29 | Reconstrucción completa: 9 categorías accionables, 
~66 MDs v2.0, 9 masters, visión global, grafo regenerado desde cero |

## 12. Changelog desde v1.2
| Tipo cambio | Detalle |
Guardar changelog TAMBIÉN como: 04-graph/CHANGELOG.md

Guarda el grafo como: 04-graph/KNOWLEDGE_GRAPH.md
```

---

## Fase KB.5b — Regenerar company-context.md del skill

> *Puente entre la KB y el skill de presentaciones.*

**🟩 COWORK** · Después de KB.5

### Prompt KB.5b (copiar literal)

```
CONTEXTO: La Knowledge Base v2.0 está completa. Necesito actualizar el archivo 
company-context.md del skill alkemy-presentations.

TAREA: 
1. Lee 03-masters/master-posicionamiento.md
2. Lee 03-masters/master-credenciales.md
3. Lee 03-masters/VISION-GLOBAL.md
4. Genera un company-context.md actualizado con:
   - Cifras reales del grupo
   - Clientes referenciables actualizados
   - Posición competitiva actual
   - Servicios por BU
   - Tono de comunicación
   - Frases prohibidas y recomendadas

Guarda en: 00-claude/alkemy-corporate-slides/docs/company-context.md

Formato: mantener la estructura actual pero con datos actualizados.
No superar ~400 tokens (se lee en cada invocación del skill).
```

---

## Fase KB.6 — Mantenimiento continuo

> *Integrar la KB en el ciclo de mantenimiento del plan v4.*

### Nueva tarea programada: "KB Sync" (quincenal, miércoles 11:00)

**🟩 COWORK** · Añadir al proyecto "Alkemy Skill Maintenance" del plan v4

```
Nombre: kb-sync-biweekly
Frecuencia: Cada 2 semanas, miércoles 11:00
Carpeta: 00-claude\alkemy-knowledge-base

Prompt:

Revisa si hay cambios en la Knowledge Base que requieran propagación.

1. FUENTES NUEVAS: ¿Hay archivos en alguna subcarpeta de 00-fuentes/ que no 
   tienen un .md correspondiente en la misma subcarpeta de 01-fuentes-md/?
   - Lista los archivos nuevos con su categoría
   - NO los proceses — solo reporta

2. ARCHIVOS SIN CATEGORÍA: ¿Hay archivos sueltos (no en subcarpeta) en 
   00-fuentes/ o 01-fuentes-md/?
   - Propón a qué categoría pertenecen

3. FUENTES MODIFICADAS: Para cada archivo en 01-fuentes-md/, compara la fecha 
   "extracted:" con la fecha de modificación del original en 00-fuentes/.
   Si el original es más reciente:
   - Lista los desactualizados
   - Indica qué master se vería afectado

4. CONSISTENCIA:
   - 02-categories/INDEX.md coincide con la realidad de las subcarpetas
   - Cada MD tiene frontmatter completo (source, category, extracted, version)
   - Los masters en 03-masters/ referencian archivos que existen
   - 04-graph/KNOWLEDGE_GRAPH.md es consistente con los masters

5. COMPANY-CONTEXT: Compara cifras de 
   00-claude/alkemy-corporate-slides/docs/company-context.md con 
   master-posicionamiento.md y master-credenciales.md. Reportar discrepancias.

Genera reporte en: 00-claude/outputs/kb-sync-[fecha].md

Formato:
- Estado: ✅ KB sincronizada / ⚠️ Cambios pendientes / 🔴 Inconsistencias
- Fuentes nuevas: [lista o "ninguna"]
- Archivos sin categoría: [lista o "ninguno"]
- Fuentes desactualizadas: [lista o "ninguna"]
- Consistencia: [OK o problemas]
- Company-context: [OK o discrepancias]
```

### Flujo cuando kb-sync detecta cambios

```
kb-sync reporta ⚠️ "2 fuentes nuevas + 1 desactualizada"
    │
    ▼
⬜ MANUAL: Tú decides qué procesar
    │
    ▼
🟩 COWORK: "Procesa estos archivos siguiendo las reglas de KB.1"
    │
    ▼
🟩 COWORK: "Actualiza el master de la categoría afectada (KB.3)"
    │
    ▼
🟩 COWORK: "Actualiza el Knowledge Graph (secciones afectadas)"
    │
    ▼
🟩 COWORK: "¿Afecta a company-context.md? Si sí, regenera"
    │
    ▼
🟥 CODE: Commit + push si el skill cambió
```

### Reglas de propagación (adaptadas a categorías)

| # | Trigger | Acción |
|---|---------|--------|
| 1 | Nuevo doc de tendencias | → Clasificar categoría → redactar MD v2.0 → actualizar master → verificar tensiones |
| 2 | Nuevo doc regulatorio | → Actualizar master-regulacion → SIEMPRE verificar master-credenciales (FSI) y master-posicionamiento |
| 3 | Nueva credencial / caso | → Actualizar master-credenciales → ¿valida oferta de servicios-ofertas? → ¿refuerza posicionamiento? → actualizar company-context.md |
| 4 | Nueva propuesta de servicio | → Actualizar master-servicios-ofertas → cross-reference con tendencias |
| 5 | Actualización de archivo existente | → Actualizar MD existente → marcar [UPDATED] en master → verificar cross-category |
| 6 | **Cambio en master-posicionamiento o master-credenciales** | **→ Regenerar company-context.md del skill → re-testear skill** |

---

## Actualización a la Fase 5 del plan v4

Añadir la tarea `kb-sync-biweekly` al diagrama visual:

```
┌─────────────────────────────────────────────────────────────────┐
│                    CICLO AUTOMÁTICO                              │
│                                                                  │
│  Viernes 9:00        Lunes 9:00         Cada 2 sem              │
│  ┌──────────┐       ┌──────────────┐    ┌────────────────┐      │
│  │ Asset    │       │ Health       │    │ Feedback       │      │
│  │ Sync     │──────▶│ Check        │───▶│ Digest         │      │
│  │ (Cowork) │       │ (Cowork)     │    │ (Cowork)       │      │
│  └──────────┘       └──────────────┘    └────────────────┘      │
│                                                                  │
│  Cada 2 sem (miércoles)                                         │
│  ┌──────────────┐                                               │
│  │ KB Sync      │──▶ ¿Fuentes nuevas? ¿Desactualizadas?        │
│  │ (Cowork)     │    ¿Archivos sin categoría? ¿company-context? │
│  └──────────────┘                                               │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Resumen ejecutivo del addendum

| Antes (KB v1) | Después (KB v2) |
|---------------|----------------|
| Todo mezclado en 02-knowledge-base/ | 5 capas: fuentes → MDs → categorías → masters → grafo |
| Bloques B1-B9 (por tema académico) | 9 categorías accionables (por cuándo y para qué se usan) |
| Archivos planos sin subcarpetas | Subcarpetas por categoría, espejo entre fuentes y MDs |
| Transcripciones crudas de pymupdf | Redacciones profesionales con tesis, argumentos, datos y relevancia |
| Categorización implícita (README) | Validación MECE formal + block-definitions.md |
| Masters numerados (master-b1, b2...) | Masters por nombre: master-tendencias-ia-tech.md |
| Masters = concatenación variable | Masters = síntesis cruzada con tensiones e implicaciones accionables |
| Sin visión global | VISION-GLOBAL.md: el argumento completo en 5 min |
| Knowledge Graph estático | Grafo con changelog + propagation rules separados |
| company-context.md escrito a mano | Derivado de masters (trazabilidad) |
| Sin mantenimiento | kb-sync quincenal con propagación automática |

**Input total**: ~63 documentos originales + 66 MDs crudos existentes  
**Output total**: estructura 5 capas × 9 categorías + 66 MDs v2.0 + 3 archivos de categorización + 9 masters v2.0 + 1 visión global + grafo v2.0 + reglas + changelog + company-context.md  
**Tiempo estimado**: 2-3 semanas en paralelo con el track del skill

---

## Quick reference: qué prompt para qué paso

| Paso | Prompt | Qué produce | Tu checkpoint |
|------|--------|-------------|---------------|
| KB.0 | Reestructurar carpetas | 5 capas + 9 subcarpetas + archivos movidos | Validar tabla de clasificación antes de mover |
| KB.1 | Redacción inteligente | 66 MDs v2.0 | OK por categoría |
| KB.2 | Validación MECE | INDEX.md + block-definitions.md + VALIDACION-MECE.md | Decidir reclasificaciones |
| KB.3 | Regenerar masters | 9 masters v2.0 | OK por tesis |
| KB.4 | Visión global | VISION-GLOBAL.md | Revisión final |
| KB.5 | Knowledge Graph | KNOWLEDGE_GRAPH.md + PROPAGATION-RULES.md + CHANGELOG.md | Verificar stats |
| KB.5b | Company context | company-context.md actualizado | — |
| KB.6 | Tarea kb-sync | Reportes quincenales | Decidir qué procesar |
