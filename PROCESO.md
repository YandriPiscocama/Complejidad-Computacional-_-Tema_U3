# PROCESO DE CURADURÍA DE RECURSOS — Programación Dinámica

Documento que describe el proceso seguido para crear la colección de recursos
bibliográficos y complementarios sobre Programación Dinámica, utilizando
**opencode** como asistente de desarrollo.

---

## Fase 1 — Búsqueda de 10 recursos bibliográficos (PDFs/HTMLs)

### Prompt utilizado

> "Busca y descarga 10 recursos bibliográficos académicos (PDFs o artículos
> HTML) sobre Programación Dinámica, distribuidos en 5 subtemas:
> (1) Concepto fundamental, (2) Paradigmas de implementación,
> (3) Problemas 1D, (4) Problemas 2D, (5) Optimización y aplicación.
> Solo fuentes verificadas: arXiv, MIT OCW, Stanford CS161, CMU 15-451,
> CSES/ICPC, Jeff Erickson (UIUC). Sin URLs inventadas."

### Acciones ejecutadas por opencode

1. **Búsqueda web** (`websearch`): Se ejecutaron múltiples búsquedas en
   paralelo para localizar PDFs académicos reales por subtema.
2. **Verificación de URLs** (`webfetch`): Cada URL fue verificada para
   confirmar que apuntaba a un PDF descargable, no a una landing page.
3. **Descarga de archivos** (`Invoke-WebRequest`): Cada PDF/HTML fue
   descargado a la carpeta correspondiente dentro de `recursos/`.
4. **Validación de texto** (`pymupdf`/`fitz`): Se verificó que cada PDF
   tuviera texto extraíble (no fueran imágenes escaneadas).

### Comandos ejecutados

```powershell
# Descarga de cada recurso bibliográfico
Invoke-WebRequest -Uri <url_verificada> -OutFile <ruta_local>

# Verificación de que el PDF tiene texto extraíble (no escaneado)
python -c "import fitz; doc=fitz.open('<ruta>'); print(doc[0].get_text()[:200])"
```

### Resultado

10 archivos distribuidos en 5 subcarpetas:

| Subcarpeta | Archivo | Fuente |
|------------|---------|--------|
| `01-concepto-fundamental` | `mit6006_fall2011_lec19_dp_intro.pdf` | MIT 6.006 Fall 2011 |
| `01-concepto-fundamental` | `mit6006_spring2020_lec16_dp.pdf` | MIT 6.006 Spring 2020 |
| `01-concepto-fundamental` | `cmu15451_fall2017_dp1.pdf` | CMU 15-451 Fall 2017 |
| `02-paradigmas-implementacion` | `uiuc_cs374_memoization.pdf` | UIUC CS374 Fall 2017 |
| `03-problemas-1d` | `stanford_cs161_lec13_dp.pdf` | Stanford CS161 |
| `03-problemas-1d` | `cses_handbook_full.pdf` | CSES / ICPC |
| `04-problemas-2d` | `cmu15451_fall2023_dp2.pdf` | CMU 15-451 Fall 2023 |
| `04-problemas-2d` | `erickson_advanced_dp.pdf` | Jeff Erickson (UIUC) |
| `05-optimizacion-aplicacion` | `kleppmann_rethinking_caching.html` | Martin Kleppmann |
| `05-optimizacion-aplicacion` | `aws_builders_caching_strategies.html` | AWS Builders Library |

---

## Fase 2 — Búsqueda de 14 recursos complementarios (videos/interactivos)

### Prompt utilizado

> "Busca 14 recursos complementarios para reforzar el estudio de Programación
> Dinámica: videos de YouTube, visualizadores interactivos, playgrounds de
> código. Prioriza canales reconocidos: Abdul Bari, Errichto, William Fiset,
> freeCodeCamp, Back to Back SWE. Incluye VisuAlgo y herramientas
> interactivas. Verifica que los videos tengan subtítulos disponibles.
> Sin URLs inventadas."

### Acciones ejecutadas por opencode

1. **Búsqueda web** (`websearch`): Se buscaron canales y videos específicos
   por nombre y topic.
2. **Verificación de URLs** (`webfetch`): Cada enlace de YouTube y recurso
   interactivo fue verificado como accesible.
3. **Verificación de subtítulos**: Se confirmó la disponibilidad de
   subtítulos (auto-generados u oficiales) en cada video.
4. **Organización por subtema**: Los recursos fueron clasificados según
   los 5 subtemas de la guía de estudio.

### Resultado

Archivo `VIDEOS.md` con 14 recursos organizados en tabla:

| # | Recurso | Tipo | Subtítulos |
|---|---------|------|------------|
| 1 | Abdul Bari — Dynamic Programming (playlist) | Video playlist | Sí |
| 2 | freeCodeCamp — Dynamic Programming (curso completo) | Video curso (5h) | Sí |
| 3 | Errichto — Dynamic Programming lectures | Video playlist | Sí |
| 4 | William Fiset — Dynamic Programming (playlist) | Video playlist | Sí |
| 5 | Back to Back SWE — The 0/1 Knapsack Problem | Video | Sí |
| 6 | Pedro Antonio Teppa Garran — Nociones de base de la PD | Video (español) | N/A |
| 7 | VisuAlgo — Recursion Tree / DAG | Visualizador interactivo | N/A |
| 8 | DP Generator — Visualizer & Code Generator | Visualizador + Playground | N/A |
| 9 | dpvis — Python DP Animation Library | Librería (GitHub) | N/A |
| 10 | AlgoExplorer — DP Lab | Playground interactivo | N/A |
| 11 | Knapsack Visualizer (alltools.dev) | Visualizador | N/A |
| 12 | DP Visualizer (easyhard) | Playground (JavaScript) | N/A |
| 13 | Sundeep Saradhi — DP vs Greedy Method | Video | Sí |
| 14 | The DSA Handbook — Greedy vs DP | Artículo interactivo | N/A |

---

## Fase 3 — Creación del índice de metadatos

### Prompt utilizado

> "Crea un archivo INDICE.md con metadata estructurada de cada uno de los
> 10 recursos bibliográficos. Para cada recurso incluir: título, autor/entidad,
> año de publicación, ruta local del archivo, URL original de descarga,
> subtemas que cubre, y una breve explicación de por qué es útil para
> el estudio de Programación Dinámica."

### Acciones ejecutadas por opencode

1. **Lectura de cada PDF** (`pymupdf`): Se extrajo la primera página de
   cada PDF para confirmar título, autor y contenido.
2. **Escritura de metadata**: Se compiló la información de cada recurso
   en formato estructurado Markdown con bloques `---INICIO---` / `---FIN---`.

### Comandos ejecutados

```powershell
# Extracción de metadata de cada PDF
python -c "
import fitz, sys
sys.stdout.reconfigure(encoding='utf-8')
doc = fitz.open('<ruta_pdf>')
print(doc[0].get_text()[:500])
"
```

### Resultado

Archivo `INDICE.md` con 10 entradas de metadata, una por recurso bibliográfico.

---

## Estructura final de la carpeta recursos/

```
recursos/
├── INDICE.md                              ← Metadata de los 10 PDFs/HTMLs
├── VIDEOS.md                              ← Tabla de 14 recursos complementarios
├── 01-concepto-fundamental/
│   ├── mit6006_fall2011_lec19_dp_intro.pdf
│   ├── mit6006_spring2020_lec16_dp.pdf
│   └── cmu15451_fall2017_dp1.pdf
├── 02-paradigmas-implementacion/
│   ├── uiuc_cs374_memoization.pdf
│   └── cmu15750_dp_space_optimization.pdf
├── 03-problemas-1d/
│   ├── stanford_cs161_lec13_dp.pdf
│   └── cses_handbook_full.pdf
├── 04-problemas-2d/
│   ├── cmu15451_fall2023_dp2.pdf
│   └── erickson_advanced_dp.pdf
└── 05-optimizacion-aplicacion/
    ├── kleppmann_rethinking_caching.html
    └── aws_builders_caching_strategies.html
```

**Total:** 12 archivos de recursos + 2 archivos de metadatos = **14 archivos**.
