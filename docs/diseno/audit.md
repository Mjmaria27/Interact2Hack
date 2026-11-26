# Impeccable Audit: Dirección B «Control operativo»

> **Procedencia de este documento.** Es la transcripción del informe que generó Claude con la skill Impeccable (v4.11.0, comando `audit`) el 25 de noviembre de 2026, en la sesión de trabajo del Avance 2. El texto del informe no se reformuló. Solo se añadió este encabezado.
>
> Las decisiones del equipo sobre cada hallazgo están en [`decisiones-impeccable.md`](decisiones-impeccable.md).
>
> **Alcance:** los resultados corresponden a una **exploración visual estática** (`style-tiles.html`), no a una auditoría de la aplicación funcional. Son hallazgos y recomendaciones de IA; no son validaciones del cliente.

**Objetivo:** `docs/diseno/style-tiles.html`, con foco en la Dirección B. El archivo no cambió desde la crítica: su hash SHA-256 sigue empezando por `379e196a…`.
**Modo de ejecución:** completo, no degradado. La auditoría de Impeccable no exige subagentes y todas sus comprobaciones se hicieron en este contexto.
**Dónde se trabajó:** todos los archivos auxiliares (copias, capturas, mediciones y JSON del detector) se crearon en la carpeta temporal de la sesión, fuera del repositorio.
**Cómo leer este informe:** el documento es una **exploración estática**. Los hallazgos separan lo que se comprueba en el documento actual de lo que será un requisito de la futura aplicación.

## Audit Health Score

| # | Dimensión | Puntuación | Hallazgo principal |
|---|---|---|---|
| 1 | Accesibilidad | 2 | El contraste de texto cumple AA en las 14 combinaciones, pero hay texto de 9 a 11 px, la pista de progreso tiene 1,33:1 y no hay estilos de foco. |
| 2 | Rendimiento | 3 | 17.975 bytes, sin imágenes ni JavaScript propio. Se pide el peso 600 de Sora, que no se usa. |
| 3 | Theming | 2 | 8 variables definidas, pero 14 colores escritos directamente y 16 estilos en línea. El lima está definido y no se usa nunca. |
| 4 | Diseño adaptable | 2 | Sin desbordamiento horizontal de 320 a 1440 px, pero el botón mide 40 px de alto, la casilla 17 px y el chip se deforma. |
| 5 | Integridad de la implementación | 2 | 27 hallazgos del detector (11 en B; 23 reales y 4 falsos positivos), además de deriva de tokens y espaciado. |
| **Total** | | **11/20** | **Aceptable** (10 a 13: hace falta trabajo importante) |

## Implementation Integrity Verdict

**Aprobado con reservas.** El documento expresa un sistema reconocible y propio de Interact2Hack:
- usa la paleta oficial como variables (`--negro`, `--tinta`, `--morado`, `--morado-oscuro` y `--lima`);
- usa Big Shoulders Display y Sora, oficiales del brand board;
- tiene esquinas rectas y una anatomía de tarjeta coherente.

Las reservas son tres, todas verificadas:
1. **Deriva de tokens:** 14 colores escritos directamente y 30 valores de espaciado distintos, varios fuera de la escala de 4 px del brand board.
2. **Lima sin uso:** el token `--lima` existe pero no se usa en ninguna regla.
3. **Detector:** de los 27 hallazgos, 23 son tamaños de texto reales y 4 son falsos positivos. `ai-color-palette` (×3) marca la paleta oficial del cliente (AC-01), y `hero-eyebrow-chip` (×1) marca el patrón de kicker del propio brand board, en la portada del documento.

## Executive Summary

- **Audit Health Score: 11/20 (Aceptable).**
- **11 hallazgos:** 0 de P0, 2 de P1, 5 de P2 y 4 de P3.
- **Los más importantes:**
  - AU-01: texto funcional de 9 a 11 px, incluidas las etiquetas de datos de 9,17 px, que la crítica no había detectado.
  - AU-02: objetivos táctiles de 40 px de alto (botón) y 17 px (casilla).
  - AU-03: pista de la barra de progreso a 1,33:1.
  - AU-07: deriva de tokens, con el lima sin uso.
  - AU-09: chip de estado deformado en todos los anchos.
- **Sobre el contraste de color:** cumple con holgura en todo el texto. Los problemas de accesibilidad son de tamaño, área táctil y elementos que no son texto, no de los colores de texto.

## 1. Accesibilidad y contraste

**Método:** fórmula de luminancia relativa de WCAG 2.x, calculada con un script. Los colores con transparencia se mezclaron primero con su fondo real.

**Texto**

Requisito: 4,5:1 para texto normal; 3:1 para texto grande, es decir, 24 px o más, o 18,66 px o más en negrita.

| ID | Elemento (B) | Primer plano | Fondo | Ratio | Requisito | Resultado |
|---|---|---|---|---|---|---|
| T1 | Títulos y texto principal | #FFFFFF | #050307 | 20,54:1 | 4,5 | Cumple |
| T2 | Datos y pasos del checklist (11 px) | #FFFFFF | #0B0612 | 20,02:1 | 4,5 | Cumple |
| T3 | Sección «Panel de seguimiento» (10 px) | #B3AABF | #050307 | 9,21:1 | 4,5 | Cumple |
| T4 | Etiquetas «UBICACIÓN» y similares (9,17 px) | #B3AABF | #0B0612 | 8,98:1 | 4,5 | Cumple |
| T5 | Etiqueta del marcador (9 px) | #B3AABF | #11091C | 8,72:1 | 4,5 | Cumple |
| T6 | Número del marcador (25 px, Big Shoulders 700) | #A46CFB | #11091C | 5,67:1 | 3 (grande) | Cumple |
| T7 | Chip «POR VENCER» (10 px, 700) | #FFC857 | #FFC85715 sobre #0B0612 | 11,51:1 | 4,5 | Cumple |
| T8 | Texto del botón «VER TAREA» (11 px, 700) | #050307 | #A46CFB | 5,98:1 | 4,5 | Cumple |
| T9 | «✓» dentro de la casilla | #050307 | #A46CFB | 5,98:1 | 4,5 | Cumple |
| T10 | «2» del logotipo (24 px, 900) | #A46CFB | #050307 | 5,98:1 | 3 (grande) | Cumple |
| T11 | Etiqueta «ADMIN» (10 px) | #FFFFFF | #050307 | 20,54:1 | 4,5 | Cumple |
| T12 | Kicker «DIRECCIÓN 02» (11 px, 700) | #A46CFB | #0B0612 | 5,83:1 | 4,5 | Cumple |
| T13 | Descripción y anotaciones (11 y 12 px) | #B3AABF | #0B0612 | 8,98:1 | 4,5 | Cumple |
| T14 | Paso actual de C (comparación) | #FFFFFF | #A46CFB10 sobre #050307 | 19,56:1 | 4,5 | Cumple |

**Elementos que no son texto**

Requisito: 3:1 cuando el elemento es necesario para identificar un control o un estado (WCAG 1.4.11).

| ID | Elemento | Primer plano | Fondo | Ratio | ¿Aplica 1.4.11? | Resultado |
|---|---|---|---|---|---|---|
| N1 | Borde de casilla sin marcar (1 px) | #A46CFB | #0B0612 | 5,83:1 | Sí | Cumple |
| N2 | Casilla marcada (relleno) | #A46CFB | #0B0612 | 5,83:1 | Sí | Cumple |
| N3 | **Pista de la barra de progreso** | #30203D | #0B0612 | **1,33:1** | Sí (indica cuánto falta) | **No cumple** |
| N4 | Relleno de progreso frente a la pista | #A46CFB | #30203D | 4,37:1 | Sí | Cumple |
| N5 | Borde del chip (ámbar al 50 %) | #FFC85780 | #0B0612 | 3,82:1 | Sí | Cumple |
| N6 | Fondo del botón frente a la tarjeta | #A46CFB | #0B0612 | 5,83:1 | Sí | Cumple |
| N7 | Borde de la etiqueta «ADMIN» | #A46CFB | #050307 | 5,98:1 | Solo si fuera un control | Cumple |
| N8 | Borde de la tarjeta de tarea | #674B7A | #050307 | **2,80:1** | Hoy no; sí cuando la tarjeta se pueda pulsar (sistema de diseño §6.2) | No cumple si pasa a ser un control |
| N9 | Borde de la tarjeta de marcador | #4D3562 | #050307 | **1,96:1** | Hoy no; sí si se vuelve un filtro | No cumple si pasa a ser un control |
| N10 | Separador | #3B294B | #0B0612 | 1,53:1 | No (decorativo) | — |
| N11 | Borde del tile del documento | #463452 | #050307 | 1,83:1 | No (decorativo) | — |
| R1 | Referencia: lima sobre negro (no se usa en B) | #5CF000 | #050307 | 13,61:1 | — | Disponible |

**Control cruzado:** las cifras compartidas (20,54, 20,02, 5,98, 5,83, 13,61 y 2,40 para el morado profundo) coinciden con la tabla §1.3 del sistema de diseño.

**Información que depende solo del color:** no se encontró en B. El estado lleva texto («POR VENCER»), el avance lleva el contador «2/3 pasos» y la casilla marcada lleva el «✓».

**Foco:** el CSS no tiene ninguna regla `:focus` ni `:focus-visible`. El botón depende del contorno por defecto del navegador, cuya visibilidad sobre el morado **no se pudo verificar** (ver Limitaciones).

## 2. Tipografía

| Tamaño calculado (B) | Elementos | Lectura |
|---|---|---|
| 9 px | 2 (etiquetas de los marcadores) | Muy por debajo del mínimo del sistema de diseño |
| **9,17 px** | **4 (etiquetas «UBICACIÓN», «RESPONSABLE», «VENCIMIENTO» y «AVANCE»)** | Hallazgo nuevo: la etiqueta `<small>` dentro de `.datos` de 11 px reduce el texto a 9,17 px |
| 10 px | 3 (sección, «ADMIN» y chip) | Por debajo del mínimo |
| 11 px | 13 (datos, pasos y botón) | Por debajo de los 14 y 16 px del sistema de diseño |
| 12 px | 4 | Anotaciones del documento |
| 24 a 35 px | 7 | Títulos en Big Shoulders: correctos y por encima de los 24 px que exige el brand board |

- **Jerarquía:** el título de la pantalla (33 px), el de la tarea (29 px) y los números de los marcadores (25 px) son tres tamaños grandes muy próximos. El salto de los títulos (24 px o más) al cuerpo (11 px) es abrupto, sin un nivel intermedio.
- **Fuentes oficiales:** se respetan. Big Shoulders va en mayúsculas y solo en títulos, nunca por debajo de 24 px, como pide el brand board. Sora se usa para el resto. Las dos fuentes se cargaron correctamente en la medición.
- **Mayúsculas:** las etiquetas de 9 a 10 px en mayúsculas con espaciado ancho (2 a 3 px) reducen todavía más la legibilidad a esos tamaños.
- **Interlineado:** el de los datos y los pasos es el normal del navegador; los pasos están separados 11 px. La fila del checklist mide 17 px de alto.

## 3. Diseño adaptable

**Método:**
- **768 y 1440 px:** Chrome sin interfaz, con mediciones del DOM (anchos reales de 744 y 1416 px) y capturas de `impeccable shot`.
- **320, 360 y 390 px:** iframes del ancho exacto, porque la ventana de Chrome sin interfaz no baja de unos 518 px. Más capturas a 320 y 390 px.

| Ancho | Desborda en horizontal | Columnas del documento | Ancho de la «pantalla» simulada de B | Chip de estado | Marcador |
|---|---|---|---|---|---|
| 320 | No | 1 | 238 px | 79 × **38** (dos líneas) | 98 × **96** (la etiqueta pasa a varias líneas) |
| 360 | No | 1 | 278 px | 99 × 25 | 118 × 96 |
| 390 | No | 1 | 308 px | 114 × 25 | 133 × 75 |
| 768 | No | 1 | 662 px | **291 × 25** (estirado) | 310 × 75 |
| 1440 | No | 3 | 405 px | **162 × 25** (estirado) | 181 × 75 |

**Documento frente a interfaz simulada.**
- **El documento:** se adapta bien, con 3 columnas que pasan a 1 por debajo de 1050 px y sin desbordamiento en ningún ancho. Esto **solo prueba que la página de presentación se adapta**.
- **La interfaz simulada:** es una caja dentro de cada tile. A 320 px de documento, la «pantalla» de B mide solo 238 px, más estrecha que cualquier celular real, porque hereda los márgenes del documento y del tile. Ninguna exploración tiene una variante móvil propia; lo que se ve es la misma composición reducida.
- **Conclusión:** estas mediciones **no son evidencia de que la futura aplicación vaya a adaptarse bien a cada pantalla**.

## 4. Uso táctil

| Elemento (B) | Tamaño medido | Objetivo del equipo (48 px) | WCAG 2.5.8 (24 px, AA) | Observación |
|---|---|---|---|---|
| Botón «VER TAREA» | 170 a 595 × **40** px | No cumple (alto) | Cumple | Es un `<button>` real: el área visual es su área interactiva. |
| Casilla | **17 × 17** px (visual) | — | — | Es un `<span>`, no un control. Su futura área interactiva puede ser toda la fila. |
| Fila del checklist | Ancho completo × **17** px | No cumple si la fila es el área táctil | No cumple | La fila no tiene relleno vertical. |
| Etiqueta «ADMIN» | 54 × 25 px | — | — | No es un control. |
| **Referencia: paso de la Dirección C** | Ancho completo × **53 a 54** px | **Cumple** | Cumple | Es el patrón que ya alcanza el objetivo. |

## 5. Consistencia visual

| Aspecto | Medición | Clasificación |
|---|---|---|
| Variables de color | 8 en `:root`; 30 usos de `var()`. `--lima`: 0 usos; `--morado`: 11; `--morado-oscuro`: 1 | Uso del lima: adaptación de marca pendiente (A-10, SD-02) |
| Colores escritos directamente | 14 valores distintos en 16 usos (`#60447B`, `#463452`, `#3B294B`, `#392B45`, `#674B7A`, `#30203D`, `#4D3562`, `#4B3561`, `#4F3860`, `#11091C`, `#FFFFFF30`, `#FFC85715`, `#FFC85780` y `#A46CFB10`) | Decisión de interfaz del equipo; convertirlos en variables (SD-03) |
| Colores fuera de la paleta oficial | `--gris #B3AABF` y `--amarillo #FFC857` | El gris es una decisión del equipo (el brand board usa blanco al 64 %). El ámbar como color de estado es una adaptación de marca pendiente (SD-02). |
| Estilos en línea | 16 (paletas de muestra y un `font-size:12px` en A) | Del documento de presentación |
| Bordes | Todos de 1 px, en 9 colores distintos | El brand board usa 2 px al 14 %; el sistema de diseño pide 2 px al 38 % en los controles |
| Espaciado | 30 valores distintos de padding, margin y gap; varios fuera de la base de 4 px (5, 7, 9, 11, 13, 15, 17 y 35 px) | El brand board fija una escala de base 4 (sistema de diseño §3.1) |
| Tamaños de fuente | 14 valores declarados | No hay una escala definida |
| Superficies | negro, tinta y #11091C (marcador) | #11091C es una tercera superficie que no está en la paleta oficial |
| Barra de progreso | Morado plano | El brand board define un degradado de morado a lima (`--i2h-progress`) |

## 6. Semántica y comportamiento

| Tipo | Hallazgo |
|---|---|
| **Comprobable en el documento** | Están `lang="es"`, `<main>`, `<header>`, `<section>` y `<article>`. Los encabezados van de H1 a H2 y H3 sin saltos. No hay estilos de foco. Los 3 `<button>` no tienen `type`, algo inocuo porque no están dentro de un formulario. Hay una línea en blanco antes de `<!DOCTYPE>`, que es inocua: no activa el modo de compatibilidad. |
| **Limitación esperable de una exploración estática** | Las casillas son `<span>` con «✓» y no `<input type="checkbox">`. Los botones no hacen nada. El logotipo es texto, no una imagen con texto alternativo. No hay estados de carga, error ni deshabilitado. |
| **Requisitos para la implementación futura** | Casillas nativas con su etiqueta, la fila entera como área táctil (sistema de diseño §8.2), foco visible (lima 3 px, 13,61:1; tinta dentro de la tarjeta señal), «Confirmar» con `aria-disabled` y el motivo en texto (R25, R42), error con reintento (R43), la tarjeta entera como un solo enlace con nombre accesible (sistema de diseño §6.2) y la alerta con `role="status"` (R38). |
| **No verificable todavía** | Navegación con teclado, anuncios de lector de pantalla, comportamiento al ampliar al 200 %, preferencia de reducir movimiento (hoy no hay animaciones), interacción táctil real y si los indicadores se actualizan en 60 s (S-10). |

## 7. Rendimiento (solo lo medible)

- **Tamaño y recursos:** 17.975 bytes, 0 imágenes, 0 scripts propios y 2 hojas de estilo (la de Google Fonts y la incrustada).
- **Fuentes:** se usa `preconnect` hacia `fonts.googleapis.com` y `fonts.gstatic.com`, y `display=swap`.
- **Pesos que no se usan:** se piden Big Shoulders 700 y 900, que sí se usan, y Sora 400, 600 y 700. **El peso 600 de Sora no aparece en ninguna regla.**
- **Sin animaciones ni transiciones.**
- **No medido:** tiempos de carga, LCP ni CLS. No hay un entorno de medición controlado y no presento estimaciones como resultados.

## Detailed Findings by Severity

### P1

**AU-01 [P1] Texto funcional de 9 a 11 px**
- **Problema:** el texto funcional de B está entre 9 y 11 px; las etiquetas de datos miden 9,17 px por el `<small>` heredado.
- **Evidencia:** tamaños calculados en B: 9 px ×2, 9,17 px ×4, 10 px ×3 y 11 px ×13. El detector lo marca 9 veces en B (`undersized-ui-text` en las líneas 513, 518, 524, 528 y 536; `tiny-text` en las 563, 568 y 573; y la anotación de la 597).
- **Método:** `getComputedStyle` en Chrome sin interfaz y `impeccable detect`.
- **Categoría:** Accesibilidad / Integridad.
- **Impacto:** lectura difícil en el celular y en movimiento (P-39); el usuario tiene que ampliar.
- **Norma:** WCAG no fija un tamaño mínimo en píxeles. El criterio que se incumple es el sistema de diseño §2.2 (14 px para metadatos y 16 px para cuerpo), coherente con R40 y CE6.
- **Recomendación:** escala de 16 px para cuerpo y pasos, 14 px para metadatos y etiquetas, 13 px para chips y 15 px para botones. Quitar `<small>` como mecanismo de tamaño.
- **Relación:** **confirma y amplía CR-03.** Las etiquetas de 9,17 px son un hallazgo nuevo.
- **Comando sugerido:** `/impeccable typeset`.

**AU-02 [P1] Objetivos táctiles por debajo de 48 px**
- **Problema:** el área táctil del botón y de las filas del checklist no llega al objetivo del equipo.
- **Evidencia:** botón de 40 px de alto en los cinco anchos; casilla de 17 × 17 px; fila del checklist de 17 px de alto. El paso de C mide entre 53 y 54 px.
- **Método:** medición del DOM a 320, 360, 390, 768 y 1440 px.
- **Categoría:** Diseño adaptable.
- **Impacto:** toques fallidos con el pulgar mientras se camina entre espacios.
- **Norma:** objetivo del equipo de 48 px (sistema de diseño §11.4). El botón cumple WCAG 2.5.8 (24 px) pero no la recomendación de 44 px (2.5.5, AAA).
- **Recomendación:** botones de 48 px de alto o más. Para el checklist, una casilla visual de 24 px dentro de una fila táctil de 56 px, como el paso de C.
- **Relación:** **confirma CR-06 con medidas** y distingue el tamaño visual del área táctil. Respalda CR-12.
- **Comando sugerido:** `/impeccable adapt`.

### P2

**AU-03 [P2] Pista de la barra de progreso a 1,33:1**
- **Problema:** la parte que falta de la barra de progreso casi no se distingue de la tarjeta.
- **Evidencia:** `#30203D` sobre `#0B0612` da 1,33:1; el relleno sobre la pista da 4,37:1, que sí cumple.
- **Método:** fórmula de WCAG.
- **Categoría:** Accesibilidad.
- **Impacto:** no se percibe cuánto falta. Lo compensa el texto «2/3 pasos», por eso es P2 y no P1.
- **Norma:** WCAG 1.4.11.
- **Recomendación:** pista con 3:1 o más frente a la tarjeta (por ejemplo, un borde de pista) y mantener siempre el contador en texto. Valorar el degradado de progreso del brand board.
- **Relación:** **amplía CR-10 y CR-07** (degradado).
- **Comando sugerido:** `/impeccable polish`.

**AU-04 [P2] Bordes de tarjetas y marcadores por debajo de 3:1**
- **Problema:** los bordes de las tarjetas no alcanzan 3:1, lo que importará cuando sean controles.
- **Evidencia:** tarjeta de tarea a 2,80:1; marcador a 1,96:1.
- **Método:** fórmula de WCAG.
- **Categoría:** Accesibilidad.
- **Impacto:** hoy no es un fallo, porque no son controles. Cuando la tarjeta entera se pueda pulsar (sistema de diseño §6.2) o el marcador funcione como filtro, su límite no será identificable.
- **Norma:** WCAG 1.4.11, en el futuro.
- **Recomendación:** borde de 3:1 o más en los elementos que se puedan pulsar, o un indicador equivalente.
- **Relación:** **contradice en parte CR-10.** El borde de 1 px de la casilla **sí cumple** (5,83:1): ahí el problema es de grosor y de coherencia con el brand board, no de contraste. Los bordes que no llegan son los de las tarjetas y los marcadores.
- **Comando sugerido:** `/impeccable polish`.

**AU-05 [P2] Sin estilos de foco**
- **Problema:** el CSS no define ningún estilo de foco.
- **Evidencia:** cero reglas `:focus` y `:focus-visible`.
- **Método:** análisis del CSS.
- **Categoría:** Accesibilidad.
- **Impacto:** quien navega con teclado depende del contorno por defecto del navegador, cuya visibilidad sobre el morado no está garantizada.
- **Norma:** WCAG 2.4.7.
- **Recomendación:** contorno lima de 3 px con 2 px de separación, y contorno tinta dentro de la tarjeta señal (sistema de diseño §4.3).
- **Relación:** requisito futuro. **Amplía CR-07**: el foco es un uso legítimo del lima.
- **Comando sugerido:** `/impeccable harden`.

**AU-07 [P2] Deriva de tokens y lima sin uso**
- **Problema:** muchos colores se escriben directamente en lugar de usar variables, y el token del lima no se usa.
- **Evidencia:** 14 colores escritos directamente en 16 usos; 16 estilos en línea; `var(--lima)` con 0 usos frente a 11 de `var(--morado)`; 3 superficies, una de ellas fuera de la paleta (`#11091C`).
- **Método:** análisis del CSS.
- **Categoría:** Theming.
- **Impacto:** dificulta mantener el sistema, y el morado queda sin contrapeso, porque el lima no aparece.
- **Recomendación:** convertir en variables el texto atenuado, la superficie, el borde y los colores de estado. Separar lo que es adaptación de marca (ámbar y uso del lima: SD-02, A-10) de lo que decide el equipo (gris, bordes y superficies: SD-03).
- **Relación:** **confirma CR-09 y cuantifica CR-07.**
- **Comando sugerido:** `/impeccable colorize`, solo para el uso del lima, cuando se decida A-10.

**AU-09 [P2] Chip de estado deformado**
- **Problema:** el chip de estado se estira o se parte según el ancho.
- **Evidencia:** 162, 291 y 114 px de ancho a 1440, 768 y 390 px, porque hereda la cuadrícula `.datos` (líneas 534 a 537). A 320 px pasa a dos líneas (79 × 38 px).
- **Método:** medición del DOM y capturas.
- **Categoría:** Diseño adaptable / Integridad.
- **Impacto:** la señal de urgencia cambia de forma según la pantalla y se lee como un bloque, no como una etiqueta.
- **Recomendación:** chip ajustado a su contenido (`width: max-content`), sin saltos de línea, y cabecera de la tarjeta con su propio diseño.
- **Relación:** **confirma CR-04 con medidas.**
- **Comando sugerido:** `/impeccable layout`.

### P3

**AU-06 [P3, requisito futuro] Casillas sin semántica de control**
- **Problema:** las casillas no son controles.
- **Evidencia:** son `<span class="casilla">` con «✓» de texto (líneas 563 a 575).
- **Método:** análisis del HTML.
- **Categoría:** Accesibilidad.
- **Impacto:** en la exploración no hay impacto, porque es una limitación esperable. En la aplicación, un lector de pantalla no anunciaría el estado.
- **Recomendación:** `<input type="checkbox">` nativo con su etiqueta (sistema de diseño §8.2). En la vista del administrador, avance de solo lectura (S-27).
- **Relación:** CR-05.
- **Comando sugerido:** `/impeccable harden`.

**AU-08 [P3] Espaciado fuera de la escala de base 4**
- **Problema:** el espaciado no sigue la escala de 4 px del brand board.
- **Evidencia:** 30 valores distintos, entre ellos 5, 7, 9, 11, 13, 15, 17 y 35 px.
- **Método:** análisis del CSS.
- **Categoría:** Integridad.
- **Impacto:** ritmo irregular y difícil de mantener.
- **Recomendación:** usar los tokens `space-1` a `space-10` del sistema de diseño §3.1.
- **Relación:** **amplía CR-09**; es un hallazgo nuevo.
- **Comando sugerido:** `/impeccable layout`.

**AU-10 [P3] La interfaz simulada no tiene variante móvil propia**
- **Problema:** la composición simulada solo se encoge con el documento.
- **Evidencia:** la «pantalla» de B mide 238 px a 320 px de documento; a 320 px las etiquetas de los marcadores pasan a varias líneas (marcador de 96 px de alto).
- **Método:** medición en iframes y capturas.
- **Categoría:** Diseño adaptable.
- **Impacto:** no permite evaluar la experiencia móvil real de B.
- **Recomendación:** que el sistema definitivo muestre la vista de celular (360 a 390 px) por separado de la de escritorio.
- **Relación:** CR-05 y CR-12; la verificación de 320 y 360 px queda para DESIGN.md (CE6).
- **Comando sugerido:** `/impeccable adapt`.

**AU-11 [P3] Peso de fuente que no se usa**
- **Problema:** se descarga un peso de Sora que ninguna regla usa.
- **Evidencia:** la URL de Google Fonts pide Sora 600; ninguna regla usa `font-weight: 600`.
- **Método:** análisis de la URL y del CSS.
- **Categoría:** Rendimiento.
- **Impacto:** una descarga de más. El tamaño no se midió.
- **Recomendación:** pedir solo los pesos que se usen. Si el sistema definitivo adopta Sora 600 para etiquetas y botones, como dice el sistema de diseño, retirar en su lugar el 700.
- **Comando sugerido:** `/impeccable optimize`.

## Patterns & Systemic Issues

- **El problema de accesibilidad es de tamaño, no de color.** Los 14 contrastes de texto cumplen AA, la mayoría con mucha holgura. Lo que falla de forma sistemática es el tamaño: 22 elementos de texto de B miden 11 px o menos, y ningún control llega a 48 px.
- **Componentes que dependen de la estructura que les rodea:** el chip hereda la cuadrícula de datos y las etiquetas heredan `<small>`. Son componentes que todavía no son independientes.
- **Valores sueltos en lugar de una escala:** 14 colores, 30 espaciados y 14 tamaños de fuente sin un sistema común.

## Positive Findings

- **Contraste de texto de nivel AA en todas las combinaciones**, con valores coherentes con el sistema de diseño (por ejemplo, negro sobre morado a 5,98:1 en el botón).
- **No depende solo del color:** cada estado y cada avance llevan su texto.
- **Base semántica correcta:** `lang`, regiones de página, encabezados en orden y `<button>` real.
- **Fuentes oficiales bien cargadas** (con `preconnect` y `display=swap`) y Big Shoulders usada solo por encima de 24 px, como pide el brand board.
- **Un documento ligero y sin desbordamiento** en ningún ancho, de 320 a 1440 px.
- **El paso de la Dirección C** (53 a 54 px de alto) ya cumple el objetivo táctil: es una pieza reutilizable.

## Relación con la crítica

| Recomendación | Relación | Hallazgo |
|---|---|---|
| CR-03 (texto) | **Confirma y amplía** | AU-01 (las etiquetas de 9,17 px son nuevas) |
| CR-04 (urgencia) | **Confirma** | AU-09 (deformación del chip, medida) |
| CR-05 (perfiles) | Amplía | AU-06 (semántica futura) y AU-10 |
| CR-06 (área táctil) | **Confirma con medidas** | AU-02 |
| CR-07 (morado y lima) | **Cuantifica y amplía** | AU-07 (lima con 0 usos), AU-05 (foco lima) y AU-03 (degradado) |
| CR-09 (tokens) | **Confirma y amplía** | AU-07 y AU-08 (espaciado) |
| CR-10 (bordes) | **Contradice en parte** | AU-04: el borde de 1 px de la casilla **cumple 3:1** (5,83:1). Los que fallan son la pista (AU-03) y los bordes de tarjetas y marcadores. |
| CR-12 (Dirección C) | Respalda | AU-02 (el paso de C cumple el objetivo táctil) |
| CR-01, CR-02, CR-08 y CR-11 | Sin hallazgos técnicos nuevos | Son de composición, texto y marca, no medibles por la auditoría |

**Nota sobre CR-02.** Si el marcador «Por vencer» se mantiene, su etiqueta debe reflejar el umbral provisional de S-09: desde 30 minutos antes de la hora límite, **incluido el minuto 30**, hasta justo antes de la hora límite. Ese umbral está pendiente de A-05.

## Recommended Actions

Ordenadas por prioridad. No ejecutaré ninguna sin su autorización.

1. **[P1] `/impeccable typeset`**: escala mínima de 16, 14, 13 y 15 px, y quitar `<small>` como mecanismo de tamaño (AU-01, CR-03).
2. **[P1] `/impeccable adapt`**: botones de 48 px y filas de checklist de 56 px a partir del paso de C, más una vista de celular separada (AU-02, AU-10, CR-06 y CR-12).
3. **[P2] `/impeccable layout`**: chip ajustado a su contenido, cabecera de la tarjeta propia y espaciado en la escala de base 4 (AU-09, AU-08 y CR-04).
4. **[P2] `/impeccable harden`**: foco visible y semántica nativa de las casillas en la implementación (AU-05 y AU-06).
5. **[P2] `/impeccable polish`**: pista de progreso y bordes de controles a 3:1 o más, y variables de color (AU-03, AU-04, AU-07, CR-09 y CR-10).
6. **[P2] `/impeccable colorize`**: solo si deciden introducir el lima (AU-07 y CR-07), después de considerar A-10 y SD-02.
7. **[P3] `/impeccable optimize`**: ajustar los pesos de Sora (AU-11).
8. **`/impeccable polish`**: pasada final.

Pueden pedirme que ejecute estos comandos de uno en uno, todos juntos o en el orden que prefieran. Cuando apliquen cambios, pueden volver a ejecutar `/impeccable audit` para ver cómo mejora la puntuación.

## Limitaciones de la auditoría

- **Exploración estática.** No hay interacción, así que no se verificaron la navegación con teclado, el lector de pantalla, el foco real, el comportamiento táctil ni los estados.
- **Anchos estrechos.** Chrome sin interfaz no baja de unos 518 px de ventana. Los anchos de 320, 360 y 390 px se midieron en iframes del ancho exacto, y las capturas de `impeccable shot` confirman las mismas formas. Las primeras mediciones a 518 px se descartaron.
- **Documento frente a aplicación.** Que el documento se adapte bien no prueba nada sobre la futura aplicación.
- **Contraste.** Se calculó a partir de los colores del CSS y no con lecturas de píxeles. Los bordes de 1 px pueden verse más débiles de lo que indica el ratio por el suavizado del navegador.
- **Rendimiento.** No se midieron tiempos de carga ni métricas de experiencia (LCP, CLS); solo la composición de recursos.
- **Sin capas visuales del detector.** No hay una herramienta de navegador capaz de inyectarlas en esta sesión, y la auditoría no las exige.
- **Informe no guardado.** No se guardó en `.impeccable/` por tu restricción. Los resultados auxiliares están en la carpeta temporal de la sesión (`…\scratchpad\audit\` y `…\scratchpad\critique\`).

## Estado del repositorio

`git status --short` no muestra ningún cambio. No modifiqué ni creé archivos en el proyecto, no ejecuté `init`, `document` ni comandos de modificación, y no generé `DESIGN.md`.
