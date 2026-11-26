# DESIGN.md · Sistema de Diseño de Interact2Hack Staff

**Versión:** 1.0 (Avance 2)  
**Fecha:** 25 de noviembre de 2026  
**Equipo:** María Paula Baca y Carlos Aluisa  
**Producto:** Plataforma de coordinación del staff de Interact2Hack  
**PRD:** `docs/prd/PRD.md` v0.3  
**Propósito:** Referencia visual definitiva para el Avance 2. Define los tokens, los componentes, las reglas de accesibilidad y los criterios verificables que guían el desarrollo de la interfaz.

---

## Cómo leer este documento

Cada decisión lleva una marca de origen:

| Marca | Significado |
|---|---|
| **[BB]** | Viene del brand board «Señal Neón» v1.0 (`docs/diseno/Interact2Hack-Brandboard.html`). Se aplica sin cambios. |
| **[PRD]** | Viene de un requisito, regla o supuesto del PRD v0.3 (citado como R-xx, S-xx, CE-xx, etc.). |
| **[EQUIPO]** | Propuesta del equipo de diseño. El cliente no la ha validado. |
| **[SD-02]** | Adaptación de marca pendiente de validación del cliente (A-10). |
| **[SD-03]** | Decisión de interfaz del equipo que no altera la identidad oficial. |

Los elementos marcados **[SD-02]** no son adaptaciones aprobadas: se documentan como propuestas del equipo para cuando el cliente responda (A-10). Los archivos independientes del logotipo siguen pendientes de A-12.

---

## 1. Brief del equipo

> *Texto original del equipo, conservado sin reformulación.*

**Palabras de personalidad:** Intuitivo, Llamativo y Eficaz.

**Referente visual:** ClickUp

Elegimos ClickUp como referente porque es una plataforma que permite organizar y supervisar tareas de manera clara y visual, algo fundamental para nuestro proyecto. Nos interesa especialmente la forma en que presenta las actividades, los responsables, las fechas de vencimiento y los estados de progreso.

También nos parece útil su organización mediante checklists, ya que los estudiantes deberán completar diferentes pasos antes de confirmar una tarea. Queremos tomar como inspiración su estructura y facilidad de navegación para diseñar una plataforma que permita a los administradores supervisar el trabajo y a los estudiantes identificar rápidamente sus responsabilidades.

**Contexto de uso:** Interact2Hack Staff es una plataforma web destinada a organizar el trabajo del personal estudiantil durante el hackathon. Los administradores necesitan crear, asignar y monitorear tareas, mientras que los estudiantes deben consultar sus responsabilidades, completar checklists y confirmar las actividades realizadas. Como los estudiantes estarán movilizándose entre diferentes espacios del evento, la interfaz debe priorizar el uso desde celulares sin descuidar su funcionamiento en computadoras.

**Objetivo visual:** Diseñar una experiencia moderna y coherente con la identidad de Interact2Hack, donde las tareas urgentes sean fáciles de reconocer y cada usuario pueda realizar sus actividades sin confusión.

---

## 2. Dirección visual

> *Texto original del equipo, conservado sin reformulación.*

### 2.1 Justificación — Dirección B: Control operativo

Después de comparar las tres propuestas de diseño, elegimos la **Dirección B — Control operativo**, porque consideramos que es la que mejor responde a las necesidades de Interact2Hack Staff y a las tres palabras de personalidad que definimos: intuitivo, llamativo y eficaz.

Esta propuesta está inspirada en la organización de ClickUp y permite visualizar de manera clara las tareas, los responsables, las fechas de vencimiento, los estados y el progreso de las actividades. Consideramos que esto es fundamental para nuestro proyecto, ya que los administradores necesitan supervisar varias tareas al mismo tiempo y reconocer rápidamente cuáles requieren mayor atención.

Uno de los aspectos que más nos gustó de esta alternativa fue la incorporación de **marcadores visuales que muestran la cantidad de tareas por vencer y los pasos completados**. Consideramos que estos indicadores son especialmente útiles porque permiten conocer rápidamente el estado de las actividades sin necesidad de revisar cada tarea individualmente. Además, facilitan el seguimiento del trabajo y ayudan a identificar las prioridades durante el desarrollo del evento.

En comparación con la Dirección A, que prioriza el impacto visual, y la Dirección C, que se enfoca principalmente en los checklists de los estudiantes, la Dirección B ofrece un mejor equilibrio entre organización, funcionalidad y claridad. También mantiene los colores y las tipografías establecidos en la identidad visual de Interact2Hack, logrando una apariencia tecnológica y llamativa sin comprometer la facilidad de uso.

Aunque seleccionamos la Dirección B como nuestra propuesta principal, reconocemos que **todavía existen aspectos que pueden mejorarse a lo largo del desarrollo del proyecto**. Por ejemplo, podemos perfeccionar la distribución de la información, adaptar mejor los componentes a dispositivos móviles e incorporar elementos de la Dirección C que faciliten la visualización y realización de los checklists por parte de los estudiantes. Consideramos que el diseño debe evolucionar conforme avancemos en la implementación y realicemos pruebas de funcionamiento y usabilidad.

En conclusión, elegimos la Dirección B porque representa una base sólida para desarrollar una plataforma organizada, visualmente atractiva y eficiente. Sin embargo, no la consideramos una propuesta definitiva e inmodificable, sino un punto de partida que podremos ajustar y mejorar para ofrecer una mejor experiencia tanto a los administradores como a los estudiantes de Interact2Hack Staff.

### 2.2 Integración de elementos de la Dirección C

La Dirección C aporta la experiencia del estudiante en el celular: filas de paso de al menos 56 px, el paso siguiente destacado, una barra de progreso grande y un encabezado específico con «Guardar avance» y «Confirmar tarea» como acciones diferenciadas (CR-12, decisión aceptada). Estos elementos se incorporan a la vista de detalle de tarea del estudiante dentro de la Dirección B.

### 2.3 Relación con Critique y Audit

Los informes Critique (12/20) y Audit (11/20) se generaron sobre la exploración estática `docs/diseno/style-tiles.html`. Sus recomendaciones fueron revisadas por el equipo y registradas en `docs/diseno/decisiones-impeccable.md`. Las 16 aceptadas y las 7 con ajustes informan este documento; las 2 rechazadas (falsos positivos del detector) no cambian la identidad visual oficial.

**Cambios más importantes respecto a las style tiles:**
- La vista principal del tablero pasa a una cuadrícula de tarjetas resumidas agrupadas por estado, en lugar de mostrar el detalle de una sola tarea (CR-01).
- Se añade el sistema de chips de estado con punto, icono y texto para los cinco estados (CR-04).
- El lima se recupera de forma controlada, solo en la lista cerrada de usos de §4.1 (CR-07, con ajuste).
- La tipografía adopta la escala mínima: 16 px para cuerpo, pasos y campos, 15 px para botones, 14 px para metadatos y 13 px para chips, ayudas y kickers (CR-03, AU-01).
- Las áreas táctiles pasan a 48 px mínimo y las filas de paso a 56 px (CR-06, AU-02).
- Los tokens de color se consolidan y separan en dos niveles: identidad oficial [BB] y extensiones del equipo [EQUIPO] (CR-09, AU-07).

**Decisiones que siguen pendientes de validación del cliente:**
- Adaptaciones de la regla «la lima es escasa» del brand board para el tablero con múltiples tareas en ejecución (SD-02, A-10).
- Umbral exacto del estado «por vencer»: 30 minutos, incluido el instante, según S-09 (A-05).
- Archivos independientes del logotipo: SVG o PNG (A-12).

---

## 3. Identidad visual

### 3.1 Estatus del brand board

El brand board «Señal Neón» fue proporcionado por el cliente a través del profesor (AC-01). Es la referencia visual oficial: fija tipografías, colores de marca, esquemas cromáticos y el estilo iconográfico. **No es una aprobación del cliente para las decisiones de interfaz**, que siguen siendo propuestas del equipo (SD-03) o adaptaciones pendientes de validación (SD-02).

**Lo que no cubre el brand board:** el brand board se creó para una landing, una app de participantes, redes sociales y slides. No define formularios, estados de tarea, colores de error ni componentes operativos. Este documento los cubre con [EQUIPO].

### 3.2 Logotipo

Usar únicamente el logotipo oficial del brand board (`docs/diseno/Interact2Hack-Brandboard.html`). **No se debe inventar ni presentar como oficial ninguna reconstrucción del logotipo.** Los archivos independientes (SVG o PNG) siguen pendientes de A-12 (CR-08, con ajuste).

Mientras A-12 esté abierto, el logotipo se referencia desde el brand board y se usa con un ancho mínimo de 96 px sobre fondo negro [BB].

---

## 4. Tokens de diseño

### 4.1 Colores de marca [BB]

Valores idénticos al brand board. No modificar.

| Token | HEX | Rol en el brand board | Uso en la plataforma |
|---|---|---|---|
| `--i2h-black` | `#050307` | Fondo base | Fondo de todas las pantallas |
| `--i2h-ink` | `#0B0612` | Texto sobre morado y lima; menús | Superficie de tarjetas, campos, diálogos y menús; texto sobre morado y lima |
| `--i2h-purple` | `#A46CFB` | Señal, kicker, acción | Botón primario, señal de «por vencer», kickers, casillas marcadas, estado «terminada» |
| `--i2h-purple-deep` | `#5B2BB5` | Degradado de foto, fases, avatares | Avatares de responsables. **Nunca como texto.** |
| `--i2h-lime` | `#5CF000` | Un solo dato clave o estado activo | Solo los usos de la lista cerrada de esta sección |
| `--i2h-white` | `#FFFFFF` | Texto principal | Texto principal |
| `--i2h-muted` | `rgba(255,255,255,0.64)` | Texto secundario | Metadatos, tiempo relativo, ayudas de campo, estado «sin asignar» |
| `--i2h-faint` | `rgba(255,255,255,0.14)` | Bordes de chips y tarjetas | Bordes de chips, tarjetas y paneles (no interactivos o identificados por texto) |
| `--i2h-hair` | `rgba(255,255,255,0.09)` | Separadores | Separadores finos de lista y de secciones |
| `--i2h-progress` | `linear-gradient(90deg, #A46CFB, #5CF000)` | Progreso | Relleno de la barra de progreso [BB]; uso repetido **provisional** (SD-02, A-10). |

**Reglas de uso del lima [BB, con ajuste SD-02].** El brand board lo limita a «un solo dato clave por vista». La plataforma lo permite **solo** en estos usos:

| # | Uso del lima | Estatus |
|---|---|---|
| 1 | Punto de 8 px del estado «En ejecución» (puede repetirse en el tablero) | **Provisional** (SD-02, A-10) |
| 2 | Punto de la pestaña o sección activa | [BB] |
| 3 | Anillo de foco sobre fondos oscuros | **Provisional** (SD-02, A-10) |
| 4 | Fondo y borde del botón primario en hover o pulsado | [BB] |
| 5 | Fondo del aviso breve de éxito | [BB] |
| 6 | Subrayado de 4 px del botón enlace | [BB] |
| 7 | Extremo final del degradado de progreso | Degradado [BB]; su repetición en varias tarjetas es **provisional** (SD-02, A-10) |

Nunca en fondos grandes, texto, franjas de tarjeta ni filas de checklist. Mientras A-10 siga abierto, los usos provisionales se aplican como propuesta del equipo; si el cliente los rechaza, el progreso pasa a morado sólido.

**Reglas de uso del morado [BB y EQUIPO].**

- **Superficie señal:** como máximo una superficie grande rellena de morado por vista: la tarjeta señal **o** un botón primario, nunca ambos. En el tablero del administrador, las acciones usan la variante secundaria, haya o no tarjeta señal. Un diálogo abierto cuenta como vista propia.
- **Elementos pequeños permitidos** (no cuentan como superficie señal): casilla marcada, punto «Terminada», kickers, bordes del botón secundario, del campo enfocado, de la tarjeta en hover y del paso siguiente, relleno inicial del progreso y relleno de hover del botón secundario.
- El morado profundo se usa solo en avatares.

### 4.2 Colores semánticos [EQUIPO/SD-03]

Los colores a continuación no forman parte de la paleta oficial del brand board. Se proponen como extensiones de interfaz [SD-03]. Los tonos `#FF6B6B` y `#FFC857` ya aparecen en la documentación interna del brand board (marcas «No» y «Solo texto grande»), aunque sin token ni rol asignado.

| Token | Valor | Uso | Origen |
|---|---|---|---|
| `--i2h-st-vencida` | `#FF6B6B` | Estado «vencida»; color de error | [EQUIPO] |
| `--i2h-st-por-vencer` | `#FFC857` | Estado «por vencer» | [EQUIPO] |
| `--i2h-st-en-ejecucion` | `var(--i2h-lime)` | Estado «en ejecución» | [BB]: «lima = ahora» |
| `--i2h-st-sin-asignar` | `var(--i2h-muted)` | Estado «sin asignar» | [BB]: color atenuado |
| `--i2h-st-terminada` | `var(--i2h-purple)` | Estado «terminada» | [EQUIPO] |
| `--i2h-fb-error` | `#FF6B6B` | Errores de formulario; acciones destructivas | [EQUIPO] |
| `--i2h-fb-exito` | `var(--i2h-lime)` | Aviso de acción completada | [BB]: aviso breve lima |
| `--i2h-border-control` | `rgba(255,255,255,0.38)` | Borde de campos, casillas y contorno de la barra de progreso | [EQUIPO] |
| `--i2h-disabled-text` | `rgba(255,255,255,0.45)` | Solo texto de controles deshabilitados | [EQUIPO] |

### 4.3 Contraste calculado

Calculado con un único script que aplica la fórmula de luminancia relativa de WCAG 2.x y compone las transparencias en sRGB sobre el fondo indicado. Los valores se truncan a dos decimales. El «peor caso» de la barra inferior (negro al 96 %) supone contenido blanco por debajo. WCAG AA pide 4,5:1 en texto normal y 3:1 en texto grande (24 px, o 18,66 px en negrita) y en elementos no textuales necesarios para identificar controles y estados. El cálculo parte de los valores CSS: no sustituye la revisión de la interfaz renderizada.

**Texto:**

| Combinación | Ratio | Mínimo | Resultado |
|---|---|---|---|
| Blanco sobre negro (texto principal) | 20,53:1 | 4,5:1 | Cumple |
| Blanco sobre tinta (tarjetas, campos, diálogos, aviso sin conexión) | 20,01:1 | 4,5:1 | Cumple |
| Blanco 64 % sobre negro (metadatos) | 8,29:1 | 4,5:1 | Cumple |
| Blanco 64 % sobre tinta (metadatos, ayudas, texto de ejemplo) | 8,22:1 | 4,5:1 | Cumple |
| Blanco sobre barra inferior, peor caso | 19,33:1 | 4,5:1 | Cumple |
| Blanco 64 % sobre barra inferior, peor caso | 8,14:1 | 4,5:1 | Cumple |
| Morado sobre negro (kicker) | 5,98:1 | 4,5:1 | Cumple |
| Morado sobre tinta (kicker en tarjetas) | 5,83:1 | 4,5:1 | Cumple |
| Tinta sobre morado (botón primario, tarjeta señal) | 5,83:1 | 4,5:1 | Cumple |
| Tinta sobre lima (hover primario, aviso de éxito) | 13,26:1 | 4,5:1 | Cumple |
| Blanco sobre morado profundo (avatares) | 8,54:1 | 4,5:1 | Cumple |
| Error `#FF6B6B` sobre negro | 7,40:1 | 4,5:1 | Cumple |
| Error `#FF6B6B` sobre tinta (error, destructivo) | 7,21:1 | 4,5:1 | Cumple |
| Tinta sobre `#FF6B6B` (hover destructivo) | 7,21:1 | 4,5:1 | Cumple |

**Controles, foco y estados:**

| Combinación | Ratio | Mínimo | Resultado |
|---|---|---|---|
| Borde de control blanco 38 % / negro (campo, casilla, contorno de progreso) | 3,42:1 | 3:1 | Cumple |
| Borde de control blanco 38 % / tinta | 3,47:1 | 3:1 | Cumple |
| Borde de campo en hover, blanco 64 % / tinta | 8,22:1 | 3:1 | Cumple |
| Borde morado / negro (botón secundario, hover de tarjeta, paso siguiente) | 5,98:1 | 3:1 | Cumple |
| Borde morado / tinta (campo enfocado, casilla marcada) | 5,83:1 | 3:1 | Cumple |
| Check tinta sobre casilla morada | 5,83:1 | 3:1 | Cumple |
| Foco lima / negro | 13,61:1 | 3:1 | Cumple |
| Foco lima / tinta | 13,26:1 | 3:1 | Cumple |
| Foco tinta sobre tarjeta señal morada | 5,83:1 | 3:1 | Cumple |
| Borde de error y destructivo `#FF6B6B` / tinta | 7,21:1 | 3:1 | Cumple |
| Punto y franja «vencida» / tinta | 7,21:1 | 3:1 | Cumple |
| Franja «vencida» / negro | 7,40:1 | 3:1 | Cumple |
| Punto «por vencer» / tinta | 13,01:1 | 3:1 | Cumple |
| Franja «por vencer» / negro | 13,35:1 | 3:1 | Cumple |
| Punto «en ejecución» (lima) / tinta | 13,26:1 | 3:1 | Cumple |
| Punto «sin asignar» (blanco 64 %) / tinta | 8,22:1 | 3:1 | Cumple |
| Punto «terminada» (morado) / tinta | 5,83:1 | 3:1 | Cumple |
| Punto de pestaña activa (lima) / barra inferior, peor caso | 12,81:1 | 3:1 | Cumple |
| Subrayado lima del botón enlace / negro | 13,61:1 | 3:1 | Cumple |

**Barra de progreso (§5.10):**

| Combinación | Ratio | Mínimo | Resultado |
|---|---|---|---|
| Contorno de pista (blanco 38 %) / tinta | 3,47:1 | 3:1 | Cumple |
| Relleno morado / tinta | 5,83:1 | 3:1 | Cumple |
| Relleno lima / tinta | 13,26:1 | 3:1 | Cumple |
| Degradado, peor punto de 101 muestras / tinta | 5,83:1 | 3:1 | Cumple |
| Contorno de pista (blanco 38 %) / negro | 3,42:1 | 3:1 | Cumple |
| Relleno morado / negro | 5,98:1 | 3:1 | Cumple |
| Relleno lima / negro | 13,61:1 | 3:1 | Cumple |
| Degradado, peor punto de 101 muestras / negro | 5,98:1 | 3:1 | Cumple |

**Combinaciones restringidas o descartadas:**

| Combinación | Ratio | Regla |
|---|---|---|
| Blanco sobre morado | 3,43:1 | Solo texto de 24 px o más; en texto pequeño usar tinta. |
| Blanco 45 % sobre negro | 4,44:1 | Solo controles deshabilitados (exentos en WCAG). Nunca texto de ejemplo ni informativo. |
| Blanco 45 % sobre tinta | 4,47:1 | Igual que la anterior. |
| Morado profundo sobre negro | 2,40:1 | Nunca para texto. |
| Borde blanco 14 % / negro | 1,37:1 | Solo decorativo: no identifica controles ni estados. |
| Borde blanco 14 % / tinta | 1,40:1 | Igual que la anterior. |
| Foco lima sobre morado | 2,27:1 | No usar; dentro de superficies moradas el foco va en tinta. |
| Relleno morado / pista blanco 14 % sobre tinta | 4,14:1 | Pista anterior, sustituida por la pista con contorno. |
| Relleno lima / pista blanco 14 % sobre tinta | 9,43:1 | La pista rellena no se usa. |
| Pista blanco 14 % / tinta | 1,40:1 | La pista rellena no se usa. |

Una combinación nueva debe calcularse antes de usarse. Solo se declara contraste suficiente en las combinaciones aprobadas de estas tablas.

### 4.4 Tipografías [BB]

| Familia | Pesos | Uso | Reglas |
|---|---|---|---|
| **Big Shoulders Display** | 900 (principal), 700 | Títulos de pantalla, cifras de vencimiento, kickers de sección | **Siempre en mayúsculas.** Interlineado 0,88 a 0,95. **Nunca por debajo de 24 px ni en párrafos.** |
| **Sora** | 400 (lectura), 600 (énfasis, etiquetas, botones) | Toda la interfaz: checklist, formularios, metadatos, navegación | Interlineado 1,4 a 1,6 en párrafos. |

Cargar únicamente los pesos que se usen: Big Shoulders Display 900 y 700, Sora 400 y 600 (AU-11, con ajuste). No se elimina Sora 600 porque está contemplado en el sistema.

**Escala de la interfaz.** Mínimos acordados (CR-03, AU-01): 16 px cuerpo, pasos y campos; 15 px botones; 14 px metadatos y etiquetas; 13 px chips, ayudas, kickers y navegación inferior. Ningún texto baja de 13 px.

| Rol | Celular | Escritorio | Familia y peso | Origen |
|---|---|---|---|---|
| Título de pantalla (H1) | 44 px / 0,92 | 72 px / 0,92 | Big Shoulders 900 | [BB] |
| Sección (H2) | 32 px / 0,95 | 48 px / 0,95 | Big Shoulders 900 | [BB] |
| Subtítulo (H3) y contador de progreso del detalle | 24 px / 0,95 | 32 px / 0,95 | Big Shoulders 900 | [BB] |
| Cifra de la tarjeta señal y de los indicadores | 40 px / 0,9 | 56 px / 0,9 | Big Shoulders 900 | [BB] |
| Hora de vencimiento en tarjeta | 24 px / 0,95 | 24 px / 0,95 | Big Shoulders 900 | [BB] |
| Título de tarea en tarjeta | 17 px / 1,3 | 17 px / 1,3 | Sora 600 | [BB] |
| Cuerpo y pasos de checklist | 16 px / 1,6 | 17 px / 1,6 | Sora 400 | [BB] |
| Texto en campos | 16 px | 16 px | Sora 400 | [EQUIPO]: evita zoom automático en iOS |
| Botón y enlaces de la tarjeta señal | 15 px | 15 px | Sora 600 | [BB] |
| Etiqueta de campo, apoyo de la tarjeta señal y aviso | 14 px | 14 px | Sora 600 | [EQUIPO] |
| Metadatos | 14 px / 1,5 | 14 px / 1,5 | Sora 400, blanco 64 % | [EQUIPO] |
| Kicker, tiempo relativo y etiqueta de la tarjeta señal | 13 px · +0,2 em | 14 px · +0,2 em | Sora 600, mayúsculas | [BB] ajustado [EQUIPO] |
| Chip de estado | 13 px | 13 px | Sora 600 | [BB] |
| Ayudas, errores y notas | 13 px / 1,5 | 13 px / 1,5 | Sora 400 | [BB] |
| Etiquetas de barra inferior | 13 px | — | Sora 600 | [EQUIPO] |
| Enlaces de barra superior | — | 14 px | Sora 600 | [EQUIPO] |
| Botón enlace | 24 px | 24 px | Big Shoulders 900 | [BB] ajustado [EQUIPO] |

### 4.5 Espaciado (base 4) [BB]

| Token | Valor | Uso típico |
|---|---|---|
| `space-1` | 4 px | Separación entre icono y texto en chips |
| `space-2` | 8 px | Separación mínima entre elementos tocables |
| `space-3` | 12 px | Espacio interno de chips; separación entre etiqueta y campo |
| `space-4` | 16 px | Margen lateral en celular; espacio interno de tarjetas en celular; medianil |
| `space-5` | 24 px | Espacio interno de tarjetas en escritorio; separación entre campos |
| `space-6` | 32 px | Separación entre secciones |
| `space-7` | 48 px | Altura mínima de controles; separación entre bloques grandes |
| `space-8` | 64 px | Márgenes de pantalla en escritorio |
| `space-9` | 96 px | Uso poco frecuente |
| `space-10` | 120 px | Uso poco frecuente |

Todo `margin`, `padding` y `gap` usa estos tokens o `0` (múltiplos de 4 px, AU-08). Los grosores de borde, el anillo de foco y su separación no son espaciado.

### 4.6 Forma, bordes y superficies

| Tipo | Valor | Uso | Origen |
|---|---|---|---|
| **Radio** | 0 en todo | Botones, tarjetas, chips, campos, casillas, diálogos | [BB] |
| Formas curvas | Círculo | Solo en puntos indicadores de estado y avatares | [BB] |
| Línea fina | 1 px blanco 9–14 % | Separadores de lista y de secciones | [BB] |
| Borde de componente | 2 px blanco 14 % | Chips, tarjetas y paneles | [BB] |
| Borde de control | 2 px blanco 38 % | Campos de formulario y casillas | [EQUIPO] |
| Acento de estado | 4 px izquierda | Tarjetas vencidas y por vencer | [EQUIPO] |
| Sombra flotante | `0 18px 60px rgba(0,0,0,0.6)` | Solo en menús desplegables y diálogos | [BB] |

### 4.7 Variables CSS completas

```css
:root {
  /* Marca [BB] */
  --i2h-black:         #050307;
  --i2h-ink:           #0B0612;
  --i2h-purple:        #A46CFB;
  --i2h-purple-deep:   #5B2BB5;
  --i2h-lime:          #5CF000;
  --i2h-white:         #FFFFFF;
  --i2h-muted:         rgba(255,255,255,0.64);
  --i2h-faint:         rgba(255,255,255,0.14);
  --i2h-hair:          rgba(255,255,255,0.09);
  --i2h-progress:      linear-gradient(90deg, #A46CFB, #5CF000);

  /* Semánticos [EQUIPO] */
  --i2h-st-vencida:        #FF6B6B;
  --i2h-st-por-vencer:     #FFC857;
  --i2h-st-en-ejecucion:   var(--i2h-lime);
  --i2h-st-sin-asignar:    var(--i2h-muted);
  --i2h-st-terminada:      var(--i2h-purple);
  --i2h-fb-error:          #FF6B6B;
  --i2h-fb-exito:          var(--i2h-lime);
  --i2h-border-control:    rgba(255,255,255,0.38);
  --i2h-disabled-text:     rgba(255,255,255,0.45);

  /* Tipografía [BB] */
  --i2h-display: 'Big Shoulders Display', 'Arial Narrow', sans-serif;
  --i2h-body:    'Sora', 'Segoe UI', sans-serif;

  /* Espacio [BB] */
  --i2h-space-1: 4px;   --i2h-space-2: 8px;   --i2h-space-3: 12px;
  --i2h-space-4: 16px;  --i2h-space-5: 24px;  --i2h-space-6: 32px;
  --i2h-space-7: 48px;  --i2h-space-8: 64px;  --i2h-space-9: 96px;
  --i2h-space-10: 120px;

  /* Forma [BB] */
  --i2h-radius: 0;
  --i2h-border: 2px solid var(--i2h-faint);
  --i2h-shadow-float: 0 18px 60px rgba(0,0,0,0.6);

  /* Interacción [EQUIPO] */
  --i2h-touch-min:   48px;
  --i2h-row-min:     56px;
  --i2h-focus-ring:  3px solid var(--i2h-lime);
  --i2h-focus-offset: 2px;

  /* Movimiento [BB] */
  --i2h-ease:    cubic-bezier(0.16, 1, 0.3, 1);
  --i2h-dur-ui:  200ms;
}
```

### 4.8 Estados de interacción

| Estado | Apariencia | Comportamiento | Origen |
|---|---|---|---|
| Normal | Según el componente | — | — |
| Hover | Cambio de color o borde; transición 0,2 s | Solo con puntero | [BB] |
| Pulsado | Igual que hover | Visible al tocar en pantallas táctiles | [EQUIPO] |
| Foco | Contorno 3 px · 2 px de separación: lima sobre fondos oscuros (13,61:1 sobre negro); tinta sobre superficies moradas (5,83:1) | `:focus-visible`; nunca se elimina | [EQUIPO]; el lima es provisional (A-10) |
| Deshabilitado | Fondo transparente, borde blanco 14 %, texto blanco 45 %, `cursor: not-allowed` | Siempre acompañado de texto que explica el motivo | [EQUIPO] |
| Cargando | Texto «Guardando…» o «Confirmando…», botón inactivo | Evita envíos dobles; el éxito se muestra solo cuando la operación termina correctamente | [EQUIPO] |

---

## 5. Componentes

### 5.1 Tarjeta resumida de tarea

**Propósito:** resumir una tarea y llevar al detalle. Se usa en el tablero del administrador (R36, R37, M12) y en la lista de tareas del estudiante (M7, R9). CR-01, aceptada.

**Anatomía:**

```
┌─────────────────────────────────────┐
▌ ● VENCIDA ⚠                         │  chip de estado (§5.3)
▌                                     │
▌ 14:30   VENCIÓ HACE 5 MIN           │  hora (Big Shoulders 24) + kicker relativo
▌ Preparar el aula de mentoría        │  título (Sora 600, 17 px), 2 líneas máx.
▌ 📍 Aula 205 · Edificio Galileo      │  lugar (Sora 14, blanco 64 %)
▌ 👤 Ana R., Mateo V.                 │  responsables (Sora 14, blanco 64 %)
▌ ▬▬▬▬▬▬░░░░  3/5 pasos               │  barra (no en terminadas) + contador
└─────────────────────────────────────┘
 ▌ = franja de acento de 4 px (solo en vencida y por vencer)
```

| Parte | Valor | Origen |
|---|---|---|
| Contenedor | Fondo tinta, borde 2 px blanco 14 %, radio 0, sin sombra. Espacio interno 16 px (celular) / 24 px (escritorio). | [BB] |
| Franja de acento | 4 px a la izquierda: `--i2h-st-vencida` o `--i2h-st-por-vencer`. Solo en esos dos estados. | [EQUIPO] |
| Hora | Big Shoulders 900 · 24 px · blanco | [BB] |
| Tiempo relativo | Sora 600 · mayúsculas · 13 px · blanco 64 %: «VENCE EN 12 MIN» / «VENCIÓ HACE 5 MIN» | [EQUIPO] |
| Título | Sora 600 · 17 px · blanco · 2 líneas con elipsis | [BB] |
| Lugar | Icono 20 px + Sora 400 · 14 px · blanco 64 % | [PRD] M5 |
| Responsables | Icono + nombres, o «Sin responsables» en blanco 64 % | [PRD] R39 |
| Avance, tarea no terminada | Barra compacta (§5.10) + contador «3/5 pasos». Igual en los dos perfiles. | [BB] · [EQUIPO] |
| Avance, tarea terminada | Solo el contador «5/5 pasos»; sin barra. Igual en los dos perfiles. | [EQUIPO] |

**Variantes por perfil:**

| Perfil | Diferencias |
|---|---|
| Administrador | Muestra siempre los responsables o «Sin responsables» (R39). |
| Estudiante | Solo ve sus tareas asignadas (R9, S-33). En responsables muestra «Tú» o «Tú y N más». |

**Comportamiento:**
- Toda la tarjeta es tocable y abre el detalle. Nombre accesible compuesto: «{título}, {estado}, {hora}».
- Hover: borde pasa a morado sólido 2 px (5,98:1).
- Foco: contorno lima de 3 px (provisional, A-10).
- Tareas terminadas: sin franja, con chip «Terminada», sin barra y con contador. No se reduce la opacidad.
- Ordenación del tablero [PRD R37]: vencidas → por vencer (de la hora límite más cercana a la más lejana, S-25) → en ejecución → sin asignar → terminadas. Cada grupo lleva un H2 con el número de tareas.

**Restricciones:**
- Las tarjetas no van rellenas de morado; ese relleno queda para la tarjeta señal (§5.7) [BB].

---

### 5.2 Checklist

**Propósito:** que el estudiante marque los pasos de su tarea y que el administrador los consulte. Se usa en el detalle de la tarea (M8, M10).

**Anatomía de la fila de paso [EQUIPO]:**

| Parte | Valor |
|---|---|
| Fila | Todo el ancho · **56 px de alto mínimo** en los dos perfiles. Separador 1 px blanco 9 %. |
| Texto del paso | Sora 400 · 16 px · blanco. No se tacha al marcarse. |
| Autoría | Sora 400 · 14 px · blanco 64 %: «Marcado por Ana R.» (R24, R39, R46). La hora («· 14:12») solo se muestra si se confirma S-20 (A-24). |

**Variante estudiante (interactiva):**

- `<input type="checkbox">` nativo dentro de su `<label>`; toda la fila es tocable (AU-06).
- Casilla visual 24 × 24 px, radio 0. Sin marcar: borde 2 px blanco 38 % (3,47:1 sobre tinta). Marcada: fondo morado y check tinta de trazo 2,4 (5,83:1).
- Foco: contorno lima de 3 px alrededor de la fila.
- Solo puede desmarcar los pasos que marcó él mismo, mientras sea responsable y antes de que se confirme la tarea (R46, S-29). Un paso marcado por otro responsable queda bloqueado y muestra «Marcado por {nombre}».
- **Paso siguiente destacado** (CR-12, de la Dirección C): el primer paso sin marcar lleva borde morado de 2 px y el texto «Siguiente». Es una ayuda visual: no impone orden y cualquier paso se puede marcar.
- Los cambios en pantalla no están guardados hasta que «Guardar avance» o «Confirmar tarea» terminen correctamente (R42, R43, S-30, S-31). Mientras tanto, el contador va acompañado de «Cambios sin guardar» [EQUIPO].
- Acciones, siempre separadas (R42): «Guardar avance» (secundario) registra pasos y observaciones sin terminar la tarea; «Confirmar tarea» (primario) guarda el progreso final y la termina, solo con todos los pasos marcados (R25).

**Variante administrador (solo lectura, no interactiva):**

- Lista semántica (`<ul>` / `<li>`). **No contiene checkboxes, botones ni elementos enfocables.**
- Cada elemento muestra un icono decorativo (`aria-hidden="true"`): check para los pasos marcados y guion para los demás, sin caja que parezca una casilla; sin hover ni cursor de acción.
- El estado se dice en texto: «Marcado por Ana R.» o «Sin marcar».
- El administrador y el super admin no marcan pasos ni confirman tareas (R47, S-27, A-01).

**Reglas comunes:**

- Checklist compartido entre los responsables (R21, S-05, A-19); basta con que uno confirme (R26, S-06).
- Al menos un paso por tarea (R13, S-34); todos son obligatorios (R23).
- El orden de la lista no es obligatorio [EQUIPO], coherente con la ausencia de desbloqueo en secuencia (W3).
- Tarea vencida: la puede completar un responsable actual (R30, S-19, S-07; A-14, A-20).
- Tarea terminada: ambos perfiles la ven con la variante de solo lectura; no se puede editar (R29, S-11, A-19).

---

### 5.3 Badge de estado

**Propósito:** mostrar el estado de la tarea con tres señales simultáneas (punto, icono y texto) para que el estado nunca dependa solo del color. CR-04, aceptada; AU-09, aceptada.

**Base [BB]:** chip con borde 2 px blanco 14 %, Sora 600 · 13 px · blanco, sin relleno, radio 0. Ajustado al contenido; sin saltos de línea.

**Los cinco estados [PRD R31, R35]:**

| Estado | Punto | Contraste del punto / tinta | Icono | Franja | Orden R37 | Color |
|---|---|---|---|---|---|---|
| **Vencida** | `#FF6B6B` · 8 px | 7,21:1 | Triángulo de alerta | Sí, `#FF6B6B` | 1 | [EQUIPO] |
| **Por vencer** | `#FFC857` · 8 px | 13,01:1 | Reloj | Sí, `#FFC857` | 2 | [EQUIPO] |
| **En ejecución** | Lima `#5CF000` · 8 px | 13,26:1 | Círculo de progreso | No | 3 | [BB] |
| **Sin asignar** | Blanco 64 % · 8 px · borde del chip **punteado** | 8,22:1 | Usuario vacío | No | 4 | [BB] atenuado |
| **Terminada** | Morado `#A46CFB` · 8 px | 5,83:1 | Check | No | 5 | [EQUIPO] |

**Precedencia de cálculo [PRD R35, S-25]:** 1) terminada; 2) si no, vencida; 3) si no, por vencer; 4) si no y tiene responsables, en ejecución; 5) si no, sin asignar. Cada tarea está siempre en un solo estado. Es distinta del orden del tablero (R37).

**Criterios provisionales:** «Por vencer» va desde 30 minutos antes de la hora límite, **incluido ese instante**, hasta justo antes de la hora límite; desde la hora límite exacta la tarea está «Vencida» (R33, R34, S-09; A-05). «En ejecución» incluye tareas con responsables aunque no tengan pasos marcados (R32, S-08; A-16).

«Sin responsables» se muestra siempre en la tarjeta, independientemente del estado [PRD R39, S-25].

**Comportamiento:**
- El chip cambia con una transición de color de 0,2 s.
- En el tablero del administrador hay una leyenda de estados plegable, con punto, icono y texto de cada uno.

**Restricciones:**
- Exactamente cinco estados. No agregar «pendiente», «por aprobar» ni «bloqueada» [PRD R31].
- En el chip, el lima aparece solo en el punto circular de «En ejecución».

---

### 5.4 Formulario

**Propósito:** crear y editar tareas, gestionar usuarios e iniciar sesión. Todo este componente es [EQUIPO/SD-03]; respeta las reglas visuales del brand board.

**Dónde se usa [PRD]:** inicio de sesión (R1, M1); cambio de contraseña (R3, M4); gestión de usuarios: nombre, correo y perfil (R2, M3); creación y edición de tareas (R13, M5); asignación de responsables (R20, M6); observaciones al completar (R27).

**Anatomía:**

| Parte | Valor |
|---|---|
| Etiqueta | Sora 600 · 14 px · blanco · **siempre visible encima del campo**. Obligatorio: texto «(obligatorio)», no solo asterisco. |
| Campo | Fondo tinta · borde 2 px blanco 38 % (3,47:1 sobre tinta) · radio 0 · 48 px de alto · espacio interno 12 × 16 px · Sora 400 · 16 px · blanco. |
| Texto de ejemplo | Blanco 64 % (8,22:1 sobre tinta). Solo orientativo; nunca sustituye a la etiqueta. |
| Ayuda | Sora 400 · 13 px · blanco 64 % · debajo del campo. |
| Error | Sora 400 · 13 px · `#FF6B6B` (7,21:1 sobre tinta) · icono de alerta · sustituye a la ayuda. |

**Tipos de campo:**

| Tipo | Uso | Notas |
|---|---|---|
| Texto | Nombre, lugar, título | — |
| Correo | Correo del usuario (R2) | Teclado de correo en celular |
| Contraseña | Inicio de sesión y cambio (R3) | Botón «Mostrar» de 48 × 48 px dentro del campo |
| Fecha y hora | Vencimiento (R13) | Selector nativo; hora local de Ecuador (S-18) |
| Área de texto | Descripción (R13) y observaciones (R27) | Mínimo 4 líneas; crece con el contenido |
| Lista editable | Pasos del checklist (R13) | Mínimo 1 paso; botones «Añadir paso» y «Quitar» de 48 × 48 px |
| Selección múltiple | Responsables (R20) | Lista con buscador; elegidos como chips; opcional según S-23 (A-22) |
| Selección única | Perfil del usuario (R6) | Solo el super admin gestiona cuentas de administrador (R8, S-01) |

**Datos obligatorios:** nombre y correo de la cuenta (R2); en la tarea, fecha y hora y descripción (R13), lugar (provisional, S-35) y al menos un paso (provisional, S-34). Los responsables son opcionales (provisional, S-23, A-22). Las observaciones son opcionales (R27).

**Estados del campo:**

| Estado | Apariencia |
|---|---|
| Normal | Borde blanco 38 % |
| Hover | Borde blanco 64 % |
| Foco | Borde morado 2 px + contorno lima 3 px · separación 2 px |
| Error | Borde `#FF6B6B` + mensaje de error |
| Deshabilitado | Borde blanco 14 % + texto blanco 45 % |
| Solo lectura | Sin borde; texto blanco |

**Validaciones:**
- Al salir del campo: solo los campos ya tocados.
- Al enviar: todos. Si hay errores, resumen enlazado al inicio del formulario; foco al resumen.
- No se valida mientras se escribe.
- El error siempre incluye texto, icono y color; nunca solo color.
- Mensaje de error de inicio de sesión genérico: «Correo o contraseña incorrectos» (sin revelar qué dato falló).

**Error al guardar o confirmar [PRD R43, S-31]:** se muestra un mensaje de error con «Reintentar». Los cambios sin guardar se conservan solo mientras el usuario siga en la misma pantalla; no se garantiza si cierra o recarga. Una operación nunca se muestra como completada si no se completó. También falla si el estudiante dejó de ser responsable o la tarea ya se confirmó.

---

### 5.5 Botones

**Propósito:** iniciar acciones del usuario. Máximo un botón primario por vista [BB]; ninguno en el tablero del administrador (§4.1).

**Variantes:**

| Variante | Normal | Hover / Pulsado | Uso |
|---|---|---|---|
| **Primario** | Fondo morado · texto tinta · borde morado 2 px | Fondo y borde lima · texto tinta (13,26:1) | «Confirmar tarea», «Guardar tarea», «Iniciar sesión» |
| **Secundario** | Fondo transparente · borde morado 2 px · texto blanco | Fondo morado · texto tinta | «Cancelar», «Volver», «Editar» |
| **Destructivo** | Fondo transparente · borde `#FF6B6B` 2 px · texto `#FF6B6B` (7,40:1) | Fondo `#FF6B6B` · texto tinta | «Eliminar tarea», «Eliminar usuario» |
| **Enlace** | Big Shoulders 900 24 px mayúsculas · subrayado lima 4 px · alto mínimo 48 px | Subrayado de 8 px | «Ver todas las vencidas» |

**Medidas:** Sora 600 · 15 px · radio 0 · espacio interno 12 × 24 px (el brand board usa 14 × 22; se ajusta a base 4, AU-08) · separación icono–texto 8 px · altura mínima **48 px** · transición 0,2 s. En celular, la acción principal ocupa todo el ancho. La variante primaria sigue la regla de superficie señal (§4.1).

**Estados:**

| Estado | Apariencia |
|---|---|
| Foco | Contorno 3 px · 2 px: lima sobre fondo oscuro; tinta sobre superficies moradas |
| Deshabilitado | Fondo transparente · borde blanco 14 % · texto blanco 45 % · `cursor: not-allowed` · **texto visible que explica el motivo**. «Confirmar tarea» usa `aria-disabled="true"` y sigue siendo enfocable |
| Cargando | «Guardando…» o «Confirmando…» · botón inactivo |

---

### 5.6 Alertas

**Propósito:** comunicar errores, avisos y resultados sin perder el contexto.

| Tipo | Apariencia | Texto y comportamiento |
|---|---|---|
| Error de formulario | Icono + `#FF6B6B` sobre tinta | Mensaje junto al campo (§5.4) |
| Tarea vencida | Borde izquierdo de 4 px e icono `#FF6B6B`; texto blanco | «Esta tarea venció a las 14:30» |
| Error al guardar o confirmar | Tinta · borde 2 px `#FF6B6B` · icono y título `#FF6B6B` · `role="alert"` | «No se pudo guardar. Tus cambios siguen en esta pantalla.» o «No se pudo confirmar la tarea.» con «Reintentar» (secundario). Permanece hasta que se reintente o se salga (R43, S-31). Si la causa es que ya no es responsable o que la tarea ya se confirmó, se indica. |
| Sin conexión (solo si se implementa C2) | Fijo arriba · tinta · borde 2 px blanco 38 % · icono · Sora 600 14 px blanco | «Sin conexión. Tus cambios no se han guardado; no cierres ni recargues esta pantalla.» con «Reintentar». **No promete guardado ni sincronización posterior** (S-12, W9, R43). Texto provisional (A-08). |
| Edición ocupada | Tinta · borde 2 px blanco 38 % · icono | «Otro administrador está editando esta tarea. No puedes guardar hasta que termine.» (R18; mecanismo provisional S-17, A-17) |
| Aviso de éxito | Fondo lima · texto tinta (13,26:1) · abajo centrado · 4 s · `role="status"` | «Avance guardado» o «Tarea confirmada». **Solo aparece cuando la operación se completó correctamente.** |

Toda alerta combina texto, icono y color; nunca solo color.

---

### 5.7 Indicadores del dashboard

**Propósito:** dar al administrador una visión de conjunto del estado del staff al entrar (CE4).

**Tarjeta señal [BB]:** el brand board reserva una tarjeta señal morada por vista para «la acción o el aviso más importante». En el tablero del administrador, ese aviso son las tareas por vencer.

| Parte | Valor | Origen |
|---|---|---|
| Contenedor | Fondo morado `#A46CFB` · radio 0 · sin sombra · espacio interno 24 px · ancho completo | [BB] |
| Etiqueta | Sora 600 · 13 px · mayúsculas · +0,2 em · **tinta al 100 %**: «POR VENCER» | [BB] ajustado; tinta al 100 % para mantener 5,83:1 [EQUIPO] |
| Dato principal | Big Shoulders 900 · 40 px (celular) / 56 px (escritorio) · tinta: «1 TAREA» / «2 TAREAS» | [BB] |
| Apoyo | Sora 600 · 14 px · tinta: «Vencen en 30 minutos o menos.» (en singular, «Vence…»). Provisional (R33, S-09, A-05); incluye el instante exacto de 30 minutos. | [BB] · [PRD] |
| Lista | Hasta 3 tareas como enlaces tinta subrayados, Sora 600 15 px, fila de 48 px: «14:30 · Preparar aula 205». Si hay más: «Ver las 5». | [EQUIPO] |
| Foco | Contorno **tinta** 3 px (5,83:1). El lima sobre morado queda en 2,27:1. | [EQUIPO] |

**Comportamiento:**
- Solo aparece si hay al menos una tarea por vencer.
- No se puede cerrar mientras haya tareas por vencer.
- Se actualiza junto con el tablero, con el retraso máximo provisional de 60 s (S-10, A-23).
- `role="status"`, anuncio «polite» cuando cambia el número de tareas.

**Marcadores del tablero** (CR-02): dos indicadores en la parte superior, «Vencidas» y «Por vencer · 30 min o menos», con cifra sin ceros a la izquierda, punto, icono y texto. **Alcance explícito:** «En todas las tareas del tablero» (R7, S-21, A-18). Las vencidas no usan la tarjeta señal: aparecen primero en la cuadrícula con franja y chip. El avance de pasos se muestra **solo por tarea** (§5.10); no hay métricas globales nuevas.

**Leyenda de estados:** plegable, en el tablero del administrador, con punto, icono y texto de cada estado.

**Indicadores por estado del tablero:**

| Grupo | Indicador visual |
|---|---|
| Vencidas | H2 «VENCIDAS» · franja roja en tarjetas · punto rojo en el chip |
| Por vencer | Tarjeta señal morada · H2 «POR VENCER» · franja ámbar |
| En ejecución | H2 «EN EJECUCIÓN» · punto lima en el chip |
| Sin asignar | H2 «SIN ASIGNAR» · punto atenuado y borde punteado en el chip |
| Terminadas | H2 «TERMINADAS» · punto morado en el chip |

---

### 5.8 Navegación

**Propósito:** orientar al usuario y moverse entre pantallas sin perder contexto.

| Dispositivo | Patrón | Valor |
|---|---|---|
| Celular | **Barra inferior de pestañas** · 64 px de alto · fondo negro 96 % · línea superior 1 px. Icono 20 px + etiqueta 13 px. Pestaña activa: blanco + punto lima arriba; inactiva: blanco 64 %. | [BB] app móvil · [EQUIPO] etiqueta 13 px |
| Tablet y escritorio | **Barra superior** · logo oficial 96 px mínimo sobre negro · enlaces Sora 600 14 px blanco 64 % (activo: blanco + punto lima) · menú de cuenta a la derecha. | [BB] web |

**Pestañas por perfil [PRD]:**
- **Administrador:** Tablero (M12), Tareas (M5), Usuarios (M3), Cuenta (M4).
- **Estudiante:** Mis tareas (M7), Cuenta (M4).
- El super admin usa la navegación del administrador; solo él gestiona cuentas de administrador (R8, S-01).

**Comportamiento:**
- El primer elemento enfocable de cada página es «Saltar al contenido».
- El orden de tabulación sigue el orden visual.
- En el tablero: alerta señal → grupos en el orden de R37 → tarjetas dentro de cada grupo.

---

### 5.9 Diálogos de confirmación

**Propósito:** confirmar acciones irreversibles o de alta consecuencia (completar una tarea, eliminar una tarea o usuario).

**Apariencia:** panel tinta · borde 2 px blanco 14 % · radio 0 · `--i2h-shadow-float` · velo negro 70 %.

**Diálogo de confirmación de tarea:**

| Parte | Valor |
|---|---|
| Título (H3) | Big Shoulders 900 · 24 px · mayúsculas: «¿CONFIRMAR TAREA?» |
| Resumen | Sora 400 · 16 px: título de la tarea + «5 de 5 pasos marcados» + observaciones si las hay |
| Texto de archivo | «La tarea quedará archivada como constancia.» (respaldado por P-03 y P-32, R19) |
| Texto de edición posterior | «Después de confirmarla no podrás editarla.» **Provisional** (R29, S-11, A-19). Si S-11 no se confirma, la frase se elimina o cambia. |
| Acciones | «Volver» (secundario, recibe el foco al abrirse) + «Confirmar» (primario). Solo lo abre un estudiante responsable con todos los pasos marcados (R25, R47). |

**Diálogo de eliminación:**
- Título: «¿ELIMINAR {NOMBRE DE LA TAREA / USUARIO}?»
- Texto de advertencia en `#FF6B6B`. Al eliminar un estudiante: «Se conserva el historial de lo que completó. Sus tareas no terminadas quedarán disponibles para reasignar.» (R10, R45, S-32).
- Acciones: «Cancelar» (secundario, recibe el foco) + «Eliminar» (destructivo).

**Comportamiento:**
- El diálogo atrapa el foco.
- Se cierra con Esc o con la acción secundaria.
- Al cerrarse, el foco regresa al elemento que lo abrió.
- Al aceptar, el botón muestra «Confirmando…» o «Eliminando…». El aviso de éxito aparece **solo cuando la operación se completa**; si falla, se muestra el error con «Reintentar» (R43).

**Restricciones:**
- Ni administradores ni super admin eliminan una tarea terminada (R19), con responsables o con actividad de ejecución registrada (R17, S-28). La actividad existe desde el primer guardado correcto con un paso marcado. En esos casos no aparece «Eliminar» y se explica el motivo en texto.
- No se puede eliminar la última cuenta de super admin (R44, S-26).
- El estudiante no elimina tareas ni usuarios (R9, S-33).

---

### 5.10 Barra y contador de progreso

**Propósito:** mostrar el avance de los pasos de una tarea.

**Solución accesible [EQUIPO, sobre la barra del brand board]:** la pista no es un relleno tenue, sino un **contorno** de 2 px blanco 38 % sobre la propia superficie, con 4 px de separación interior. El relleno nunca toca el contorno: contrasta con la superficie interior, y el contorno contrasta con la superficie. El brand board usa una pista rellena blanco 14 % (1,40:1 sobre tinta), que no alcanza 3:1.

| Parte | Valor | Contraste sobre tinta |
|---|---|---|
| Contorno (pista) | 2 px blanco 38 % · radio 0 · espacio interno 4 px | 3,47:1 (3,42:1 sobre negro) |
| Relleno | `--i2h-progress`, degradado extendido sobre el ancho relleno; alternativa si A-10 lo rechaza: morado sólido | 5,83:1 en el peor punto |
| Tarjeta resumida | Relleno de 4 px (alto total 16 px) | — |
| Detalle | Relleno de 8 px (alto total 20 px) | — |
| Contador | Siempre visible. Tarjeta: «3/5 pasos», Sora 600 14 px. Detalle: «3 de 5 pasos», Big Shoulders 24 / 32 px | Blanco, 20,01:1 |

**Por estado de la tarea:**

| Vista | No terminada | Terminada |
|---|---|---|
| Tarjeta resumida (ambos perfiles) | Barra + contador | Solo contador |
| Detalle (ambos perfiles) | Barra + contador, antes del checklist | Barra completa + contador, solo lectura |

El contador es el dato principal; la barra lo acompaña (`aria-hidden="true"`, porque el texto ya comunica el valor). En el detalle del estudiante, el contador refleja lo marcado en pantalla y muestra «Cambios sin guardar» hasta que se guarde correctamente.

---

## 6. Accesibilidad

**Objetivo:** WCAG 2.2, nivel AA. Esta sección define **requisitos**, no resultados: lo único calculado son los ratios de contraste de la sección 4.3. La conformidad de la interfaz no está comprobada, porque la aplicación todavía no existe; no se ha probado con teclado manual, lector de pantalla, zoom ni dispositivos reales.

### 6.1 Contraste

- Texto normal: combinaciones de §4.3 con 4,5:1 o más.
- Texto de 24 px o más: mínimo 3:1. De las combinaciones restringidas, solo blanco sobre morado se permite como texto informativo, y a ese tamaño.
- Los controles deshabilitados están exentos de contraste en WCAG; no se declara conformidad para ellos y su motivo se explica en texto legible.
- Bordes de controles y estados: mínimo 3:1 según WCAG 1.4.11 (AU-04, con ajuste). Esto aplica a elementos **necesarios para identificar controles** (campo, casilla, control de estado), no a separadores decorativos.
- Los bordes decorativos de chips y tarjetas (blanco 14 %, 1,40:1 sobre tinta) se permiten solo cuando el elemento se identifica por su contenido textual.
- Una combinación nueva debe calcularse antes de usarse.

### 6.2 Color nunca es el único indicador [EQUIPO]

- Estados de tarea: punto + icono + texto (§5.3).
- Errores: icono + mensaje de texto (§5.4).
- Botón deshabilitado: texto que explica el motivo (§5.5).
- Los estados «vencida» y «por vencer» tienen además la franja de acento (§5.1).

### 6.3 Navegación por teclado [EQUIPO]

- Todo debe poder usarse con teclado: tarjetas, checklist, formularios, diálogos y navegación.
- Foco visible: contorno 3 px · 2 px con `:focus-visible`, lima sobre fondos oscuros y tinta sobre superficies moradas. Nunca se elimina.
- Orden de tabulación: sigue el orden visual.
- Primer elemento: enlace de «Saltar al contenido» en cada página.
- Diálogos: deben atrapar el foco, cerrarse con Esc y devolver el foco al origen.
- Checklist del estudiante: Tab y Mayús+Tab entre pasos, Espacio para marcar. El del administrador no es enfocable.
- Estructura semántica: encabezados en orden (H1 → H2 → H3), regiones de página, etiquetas asociadas a cada campo.
- Tarjeta de tarea: un único enlace con nombre accesible compuesto.

### 6.4 Áreas táctiles [BB y EQUIPO]

| Regla | Valor | Origen |
|---|---|---|
| Área táctil mínima del brand board | 44 × 44 px | [BB] |
| Área táctil mínima en la plataforma | **48 × 48 px** | [EQUIPO] |
| Separación mínima entre elementos tocables | 8 px | [EQUIPO] |
| Fila de paso del checklist | **56 px mínimo** en ambos perfiles; tocable entera en la del estudiante | [EQUIPO] |
| Barra inferior | 64 px | [BB] |

### 6.5 Texto y zoom [EQUIPO]

- Texto mínimo: 13 px; ver la escala de §4.4.
- Debe admitir zoom al 200 % sin pérdida de contenido.
- Sin desplazamiento horizontal desde **320 px** (objetivo de diseño). La verificación académica CE6 se realiza también con **360 px** como referencia.
- Sora debe escalar con el tamaño de texto del sistema; Big Shoulders crece como máximo 1,3 veces [BB].
- **Verificación de 320 y 360 px en el Avance 2 (CE6):** solo se comprobó la maqueta `docs/diseno/brand-board.html` en Chrome headless a 320, 360 y 1440 px, sin desbordamiento horizontal detectado. D-18 y D-19 siguen pendientes sobre la aplicación.

### 6.6 Movimiento [BB]

- Transiciones de interfaz: 0,2 s.
- Animaciones de entrada (0,8 s) y barrido (0,9 s): solo en el inicio de sesión y en la primera aparición de la tarjeta señal. **No en el tablero.**
- Sin rebote ni movimiento continuo.
- Con `prefers-reduced-motion: reduce`, todo debe aparecer sin animación.

### 6.7 Contenido no textual

- Logo: `alt="Interact2Hack"`.
- Iconos que acompañan texto: decorativos (`aria-hidden="true"`).
- Iconos solos («Quitar paso», «Mostrar contraseña»): nombre accesible.
- Avatares: iniciales visibles + nombre completo como nombre accesible.
- Aviso de éxito: `role="status"`. Error al guardar o confirmar: `role="alert"`.
- Tarjeta señal: `role="status"`, anuncio «polite».

---

## 7. Reglas para agentes de IA

Los agentes que implementen la interfaz de Interact2Hack Staff deben:

1. **Usar únicamente los tokens definidos en §4.** No inventar colores, tipografías, espaciados ni sombras fuera del sistema.
2. **Reutilizar los componentes documentados en §5.** No crear variantes no documentadas sin justificación explícita.
3. **No inventar estados de tarea.** Los únicos estados válidos son los cinco del PRD (R31): vencida, por vencer, en ejecución, sin asignar, terminada. No agregar «pendiente», «por aprobar», «bloqueada» ni ningún otro.
4. **No inventar permisos ni funcionalidades.** Las acciones de cada perfil están definidas en el PRD §2. Los supuestos (S-xx) son provisionales; no presentarlos como requisitos confirmados.
5. **Respetar la identidad oficial.** No modificar los valores de los tokens [BB]. No inventar ni presentar como oficial ninguna reconstrucción del logotipo (A-12).
6. **No modificar el PRD para resolver decisiones visuales.** Las contradicciones entre el diseño y el PRD se documentan como puntos abiertos.
7. **Mantener accesibilidad.** Toda combinación nueva de texto/fondo debe calcularse antes de usarse. El contraste mínimo para texto normal es 4,5:1; para texto grande y bordes de control, 3:1.
8. **Mantener coherencia entre perfiles.** El administrador ve el checklist como lista no interactiva (S-27, A-01). El estudiante tiene «Guardar avance» y «Confirmar tarea» como acciones separadas.
9. **No prometer sincronización offline** ni guardado diferido (S-12, W9). El éxito se muestra solo cuando la operación se completó (R43).
10. **Documentar cualquier excepción.** Si es necesario salirse del sistema por una limitación técnica, dejar un comentario con el token que debería usarse y el motivo del desvío.
11. **Verificar los anchos 320 y 360 px** antes de dar por completada cualquier pantalla (CE6, D-18, D-19).
12. **Mantener los puntos abiertos.** Las adaptaciones pendientes de A-10, SD-02 y A-12 no se dan por resueltas sin respuesta del cliente.

---

## 8. Criterios verificables de diseño

Los criterios D-01 a D-23 son verificables en una demo o inspección. Los criterios subjetivos o de estimación no se incluyen aquí.

| ID | Criterio | Método de verificación | Relación PRD/diseño |
|---|---|---|---|
| D-01 | Los valores de los tokens [BB] (`--i2h-black`, `--i2h-ink`, `--i2h-purple`, `--i2h-purple-deep`, `--i2h-lime`) coinciden exactamente con los del brand board. | Comparar los valores CSS con `docs/diseno/Interact2Hack-Brandboard.html`. | §4.1; AC-01 |
| D-02 | El radio de borde es 0 en botones, tarjetas, chips, campos, casillas, diálogos y alertas. Las únicas formas curvas son los puntos indicadores de estado y los avatares. | Inspección del CSS (`border-radius`). | §4.6; [BB] |
| D-03 | El texto normal (menos de 24 px) tiene un contraste mínimo de 4,5:1 con su fondo. | Calcular con la fórmula WCAG sobre los valores CSS de cada combinación. Verificar con las tablas de §4.3. | §6.1; WCAG 1.4.3 |
| D-04 | Los elementos necesarios para identificar controles y estados (bordes de campo y casilla, foco, puntos de estado, contorno y relleno de la barra de progreso) tienen al menos 3:1 con su superficie adyacente. | Recalcular con la fórmula WCAG y comparar con §4.3. | §4.3; §5.10; §6.1; WCAG 1.4.11; AU-03, AU-04 |
| D-05 | Botones, campos e iconos tocables miden al menos 48 px de alto y de ancho. | Medir en DevTools a 320 y 360 px. | §5.5; §6.4; CR-06 |
| D-06 | Las filas del checklist miden al menos 56 px; en la vista del estudiante son tocables en toda su superficie. | Medir en DevTools a 360 px y tocar sobre el texto del paso. | §5.2; §6.4; CR-06 |
| D-07 | Todo elemento interactivo muestra foco (3 px, separación 2 px): lima sobre fondos oscuros y tinta sobre superficies moradas. | Recorrer las pantallas principales con Tab. | §4.8; §6.3; AU-05 |
| D-08 | Los chips de tarea usan exactamente cinco estados: vencida, por vencer, en ejecución, sin asignar y terminada. | Revisar todos los chips y su origen de datos. | §5.3; PRD R31 |
| D-09 | Cada chip de estado muestra simultáneamente punto, icono y texto del estado. El estado no depende solo del color. | Inspeccionar el DOM del chip; verificar presencia de los tres elementos y que el texto es visible. | §5.3; §6.2; CR-04 |
| D-10 | Cada vista tiene como máximo una superficie señal morada (tarjeta señal o botón primario, no ambos); en el tablero del administrador no hay botones primarios. Los demás usos del morado están en la lista de §4.1. | Revisar cada pantalla y buscar `--i2h-purple` en el CSS. | §4.1; [BB] |
| D-11 | El lima aparece solo en los siete usos de §4.1: punto «En ejecución», punto de navegación activa, foco sobre fondo oscuro, hover o pulsado del primario, aviso de éxito, subrayado del botón enlace y final del degradado de progreso. | Buscar `#5CF000` y `--i2h-lime` en el CSS y revisar cada uso. | §4.1; CR-07; A-10 |
| D-12 | «Guardar avance» y «Confirmar tarea» son acciones separadas; «Confirmar» está deshabilitado mientras falte un paso. | Probar con un paso sin marcar y luego con todos marcados. | §5.2; PRD R25, R42 |
| D-13 | El checklist del administrador es una lista no interactiva: sin checkboxes ni elementos enfocables, con el estado de cada paso en texto. | Inspeccionar el DOM y recorrer con Tab. | §5.2; PRD R47, S-27; AU-06 |
| D-14 | «Sin responsables» es visible en la tarjeta de cualquier tarea que no tenga responsables, independientemente de su estado. | Crear una tarea sin responsables y verificar que el texto aparece en la tarjeta. | §5.1; PRD R39 |
| D-15 | Los mensajes de error incluyen texto e icono; nunca solo color. | Provocar un error de formulario y verificar que hay texto descriptivo e icono junto al campo. | §5.6; §6.2; WCAG 1.4.1 |
| D-16 | El tablero del administrador ordena los grupos en este orden: vencidas → por vencer → en ejecución → sin asignar → terminadas. | Crear tareas en distintos estados y verificar el orden en el tablero. | §5.1; §5.3; PRD R37 |
| D-17 | El estudiante ve solo las tareas que tiene asignadas. | Iniciar sesión como estudiante y comparar con las asignaciones. | §5.1; PRD R9, S-33 |
| D-18 | No hay desplazamiento horizontal en ninguna pantalla con un ancho de viewport de 320 px. | Redimensionar el navegador a 320 px; verificar con DevTools (panel de dispositivos) que `overflow-x` no produce scroll. | §6.5; PRD CE6 |
| D-19 | A 360 px, un estudiante completa una tarea sin zoom ni desplazamiento horizontal. | Ejecutar y confirmar una tarea a 360 px. | §6.5; PRD CE6 |
| D-20 | El botón deshabilitado «Confirmar tarea» va acompañado de un texto visible que explica cuántos pasos faltan. | Verificar con un paso sin marcar: aparece el texto «Falta 1 paso para confirmar» o equivalente. | §5.5; PRD R25 |
| D-21 | Todos los valores de espaciado son múltiplos de 4 px (`space-1` a `space-10`). No hay valores de espaciado fuera de la escala. | Buscar valores de `margin`, `padding` y `gap` en el CSS; verificar que son múltiplos de 4. | §4.5; AU-08 |
| D-22 | Big Shoulders Display se usa siempre en mayúsculas. No aparece en párrafos ni en tamaños inferiores a 24 px. | Buscar todas las reglas `font-family` que usen Big Shoulders; verificar `text-transform: uppercase` y los tamaños. | §4.4 |
| D-23 | Si guardar o confirmar falla, hay mensaje de error y «Reintentar», sin aviso de éxito ni cambio de estado; el éxito aparece solo tras completarse la operación. | Simular un fallo de red y una operación correcta. | §5.6; PRD R43, S-31 |

---

## Anexo A. Puntos abiertos que afectan a este documento

| Punto | Tema | Qué puede cambiar |
|---|---|---|
| A-01 | Permisos del super admin y del administrador (S-01, S-26, S-27) | Gestión de cuentas y checklist de solo lectura. |
| A-05 | Umbral de «por vencer» (S-09) | Textos «30 min o menos». |
| A-08 | Conexión en el evento (S-12, S-31) | Texto del aviso sin conexión. |
| A-10 (SD-02) | Adaptaciones de marca | Usos provisionales del lima, degradado repetido y colores de estado. |
| A-12 | Archivos del logotipo | Uso del logotipo como recurso independiente. |
| A-14 y A-20 | Tareas vencidas y reasignación (S-19, S-07, S-32) | Checklist habilitado en vencidas y consecuencias de eliminar un estudiante. |
| A-15 y A-16 | Precedencia y «en ejecución» (S-25, S-08) | Estado mostrado y orden dentro de «por vencer». |
| A-17 | Edición simultánea (S-17) | Aviso de edición ocupada. |
| A-18 | Alcance de cada administrador (S-21) | Alcance de los marcadores. |
| A-19 | Checklist compartido, guardado y cierre (S-05, S-06, S-11, S-24, S-29, S-30) | Bloqueo de pasos, diálogo de confirmación y guardado. |
| A-22 | Responsables obligatorios (S-23) | Campo de responsables. |
| A-23 | Retraso del tablero (S-10) | Actualización de indicadores. |
| A-24 | Hora de cada paso (S-20) | Autoría con o sin hora. |

## Anexo B. Partes del brand board que no se usan

Fotografía y su degradado, fundidos, cita sobre foto, círculos de cifra, línea de fases, muro de auspiciantes, piezas para redes, retícula de slides, tarjeta de contacto (salvo como origen de la franja de estado) y video. Pertenecen a la comunicación del hackathon, no a la herramienta del staff (S-16).

## Anexo C. Documentos relacionados

| Documento | Contenido |
|---|---|
| `docs/diseno/sistema-de-diseno.md` | Borrador histórico v0.1. Conservado como referencia del proceso. Este documento lo reemplaza como referencia visual definitiva. |
| `docs/diseno/brief.md` | Texto original del brief del equipo. |
| `docs/diseno/direccion-visual.md` | Texto original de la justificación de la dirección visual. |
| `docs/diseno/style-tiles.html` | Exploración visual estática (Avance 2). No modificar. |
| `docs/diseno/Interact2Hack-Brandboard.html` | Brand board oficial «Señal Neón» v1.0. No modificar. |
| `docs/diseno/brand-board.html` | Brand board del sistema definido en este documento (maqueta autocontenida). |
| `docs/diseno/critique.md` | Informe Critique de Impeccable (12/20, degradado). |
| `docs/diseno/audit.md` | Informe Audit de Impeccable (11/20, completo). |
| `docs/diseno/decisiones-impeccable.md` | Decisiones del equipo sobre los 25 ítems de Critique y Audit. |
| `docs/prd/PRD.md` | PRD v0.3. Fuente de verdad funcional. |
