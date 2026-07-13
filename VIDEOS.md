# RECURSOS COMPLEMENTARIOS DE PROGRAMACIÓN DINÁMICA

---

## TABLA FINAL — RECURSOS COMPLEMENTARIOS DE DP

### Subtema 1: Concepto Fundamental

| # | Recurso | Tipo | Plataforma/URL | Idioma | Duración | Subtítulos | Subtema(s) | Por qué ayuda |
|---|---|---|---|---|---|---|---|---|
| 1 | Abdul Bari - Dynamic Programming (playlist) | Video playlist | `youtube.com/playlist?list=PLJULIlvhz0rE83NKhnq7acXYIeA0o1dXb` | Inglés (Hindi) | ~20 videos, 10-25 min | Sí, disponibles | 1, 2 | Pizarra con principio de optimalidad; subestructura óptima y solapamiento de subproblemas dibujados paso a paso |
| 3 | Errichto - Dynamic Programming lectures | Video playlist | `youtube.com/playlist?list=PLl0KD3g-oDOGJUdmhFk19LaPgrfmAGQfo` | Inglés | 4-6 videos, 15-20 min | Sí, disponibles | 1, 2, 3 | Lecture #1: Fibonacci iteration vs recursion. Explica por qué la recursión naive es exponencial y cómo DP lo reduce a O(n) |
| 6 | Pedro Antonio Teppa Garran - Nociones de base de la PD | Video | `youtube.com/watch?v=B0S3Ip5MuKk` | Español | ~25 min | N/A (audio en español) | 1 | Único recurso en español. Subestructura óptima, solapamiento, etapas, estados, variables de decisión, función de recurrencia |
| 7 | VisuAlgo - Recursion Tree / DAG | Visualizador interactivo | `visualgo.net/en/recursion` | Inglés | Interactivo | N/A (sin audio) | 1, 2, 3 | Anima árbol de recursión mostrando subproblemas repetidos en azul; compara naive vs DP. Incluye Fibonacci, Coin Change, Knapsack, LCS, TSP |
| 13 | Sundeep Saradhi - DP vs Greedy Method (Key Differences) | Video | `youtube.com/watch?v=vczcQLRf8Ys` | Inglés | 10 min | Sí, disponibles | 1 | Comparación directa lado a lado: optimización, subproblemas, memorización vs backtracking. Ejemplos: 0/1 Knapsack (DP) vs Fractional Knapsack (Greedy). Garantía de optimalidad |
| 14 | The DSA Handbook - Greedy vs DP (artículo interactivo) | Artículo interactivo | `dsa.handbook.academy/patterns/greedy-vs-dp/` | Inglés | ~15 min lectura | N/A (texto) | 1 | Flowchart de decisión, tabla side-by-side, 3 problemas signature (Jump Game=greedy, Coin Change=DP, 0/1 Knapsack=DP), counterexamples clásicos, framework paso a paso |

### Subtema 2: Paradigmas de Implementación

| # | Recurso | Tipo | Plataforma/URL | Idioma | Duración | Subtítulos | Subtema(s) | Por qué ayuda |
|---|---|---|---|---|---|---|---|---|
| 2 | freeCodeCamp - Dynamic Programming (curso completo) | Video curso | `youtube.com/watch?v=oBt53YbR9Kk` | Inglés | 5 horas | Sí, disponibles | 1, 2, 3 | Cubre memoization (top-down) y tabulación (bottom-up) con código en vivo para cada enfoque; permite comparar ambos lado a lado |
| 9 | dpvis - Python DP Animation Library | Visualizador (librería) | `github.com/itsdawei/dpvis` | Inglés | Interactivo | N/A (sin audio) | 1, 2, 3, 4 | Librería académica (USC, paper arXiv). Anima frame-by-frame cualquier implementación DP con 2 líneas de cambio. Modo quiz interactivo |

### Subtema 3: Problemas Clásicos 1D

| # | Recurso | Tipo | Plataforma/URL | Idioma | Duración | Subtítulos | Subtema(s) | Por qué ayuda |
|---|---|---|---|---|---|---|---|---|
| 4 | William Fiset - Dynamic Programming (playlist) | Video playlist | `youtube.com/@WilliamFiset-videos/playlists` | Inglés | 12 videos, 10-20 min | Sí, disponibles | 1, 2, 3, 4 | Cubre Fibonacci, Coin Change, Climbing Stairs, Tiling. Animaciones de tablas DP construyéndose celda por celda |
| 10 | AlgoExplorer - DP Lab | Playground interactivo | `github.com/Ashilman25/AlgoExplorer` | Inglés | Interactivo | N/A (sin audio) | 3, 4 | Plataforma fullstack con timeline de pasos, playback, explicaciones en lenguaje natural. Incluye Fibonacci, Coin Change con traceback |
| 12 | DP Visualizer (easyhard) | Playground (JavaScript) | `easyhard.github.io/dpv/` | Inglés | Interactivo | N/A (sin audio) | 3, 4 | Implementas tu solución DP en JS con `memofunction` y ves la animación automática de la tabla; ideal para experimentar |

### Subtema 4: Problemas 2D

| # | Recurso | Tipo | Plataforma/URL | Idioma | Duración | Subtítulos | Subtema(s) | Por qué ayuda |
|---|---|---|---|---|---|---|---|---|
| 5 | Back to Back SWE - The 0/1 Knapsack Problem | Video | `youtube.com/watch?v=xCbYmUPvc2Q` | Inglés | 20 min | Sí, disponibles | 3, 4 | "Cada celda SIGNIFICA ALGO, no es magia". Anima tabla de Knapsack celda por celda, explica recurrence y backtracking |
| 8 | DP Generator - Visualizer & Code Generator | Visualizador + Playground | `dpgenerator.com` | Inglés | Interactivo | N/A (sin audio) | 3, 4 | Ingresa tu problema DP y genera visualización paso a paso + código en Python/Java/C++/JS; ver la tabla llenarse celda por celda |
| 11 | Knapsack Visualizer (alltools.dev) | Visualizador | `alltools.dev/tools/visualizations/knapsack-visualizer/` | Inglés | Interactivo | N/A (sin audio) | 4 | Tres modos: tabla DP completa, rolling 1D, DP vs Greedy. Backtracking para recover items. Sonificación. Ideal para defender Space Optimization |

### Subtema 5: Optimización y Aplicación Profesional

*(Cubierto por tu biblioteca existente: Martin Kleppmann + AWS Builders Library)*

---

## RESUMEN POR SUBTEMA

| Subtema | Videos | Interactivos | Total |
|---|---|---|---|
| 1. Concepto Fundamental | 4 (#1, #3, #6, #13) | 2 (#7, #14) | **6** |
| 2. Paradigmas de Implementación | 1 (#2) | 1 (#9) | **2** |
| 3. Problemas Clásicos 1D | 1 (#4) | 2 (#10, #12) | **3** |
| 4. Problemas 2D | 1 (#5) | 2 (#8, #11) | **3** |
| 5. Optimización y Aplicación | — | — | *(biblioteca existente)* |
| **TOTAL** | **7** | **7** | **14** |

**Subtítulos resumen:** 6 videos en inglés con subtítulos disponibles (auto-generados u oficiales) + 1 video en español (N/A) + 6 recursos interactivos sin audio (N/A) + 1 artículo interactivo (texto, N/A).
