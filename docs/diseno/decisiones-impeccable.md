# Decisiones del equipo sobre Impeccable Critique y Audit

**Proyecto:** Interact2Hack Staff, Avance 2
**Fecha:** 25 de noviembre de 2026
**Dirección visual:** B «Control operativo» se mantiene como dirección principal, con elementos de la Dirección C para la experiencia del estudiante (ver [`direccion-visual.md`](direccion-visual.md)).
**Informes de origen:**

| Informe | Modo de ejecución | Puntuación |
|---|---|---|
| [`critique.md`](critique.md) | Degradado, single-context | 12/20 (Aceptable) |
| [`audit.md`](audit.md) | Completo | 11/20 (Aceptable) |

## Alcance y procedencia

- **Qué se evaluó.** Ambos informes evalúan una **exploración visual estática** (`style-tiles.html`), no una aplicación funcional. Sus mediciones describen ese documento, no el comportamiento de la futura plataforma.
- **Quién hizo qué.** Cada fila de este registro distingue tres cosas:

| Elemento | Origen |
|---|---|
| **Recomendación** | IA: Claude, con la skill Impeccable 4.11.0. |
| **Decisión** | Equipo (María Paula Baca y Carlos Aluisa): aceptar, aceptar con ajustes o rechazar. |
| **Validación del cliente** | **Ninguna** de estas decisiones ha sido validada por el cliente. Las adaptaciones de marca siguen pendientes de A-10 y SD-02, y los archivos del logotipo, de A-12. |

- **Nada está implementado.** Ninguna recomendación aceptada se ha aplicado todavía. Se aplicarán al redactar el futuro `DESIGN.md`, cuando el equipo lo autorice.
- **El PRD no cambia.** Este registro no cierra ningún punto abierto del PRD v0.3 (A-01 a A-24) ni modifica sus reglas.

**Sobre la columna «Justificación»:**
- En las decisiones **aceptadas**, el equipo no aportó un texto propio. La columna resume la evidencia de los informes que respalda la recomendación.
- En las **aceptadas con ajustes** y las **rechazadas**, se transcribe el criterio que dio el equipo.

## Resumen

| Informe | Aceptadas | Aceptadas con ajustes | Rechazadas | Total |
|---|---|---|---|---|
| Critique (CR) | 8 | 4 | 0 | 12 |
| Audit (AU) | 8 | 3 | 0 | 11 |
| Falsos positivos del detector (FP) | 0 | 0 | 2 (4 apariciones) | 2 |
| **Total** | **16** | **7** | **2** | **25** |

## Registro de decisiones

### Recomendaciones de Critique

| ID | Informe | Recomendación original (IA) | Decisión (equipo) | Justificación | Relación | Implicación para el futuro DESIGN.md | Estado |
|---|---|---|---|---|---|---|---|
| CR-01 | Critique | Tarjeta resumida en una cuadrícula agrupada por estado, con lo vencido primero; el checklist pasa al detalle de la tarea. | Aceptada | B muestra una sola tarea con su checklist completo (líneas 532 a 585), lo que no permite la supervisión que justificó elegir B. | Brief (ClickUp, supervisar); dirección visual; PRD R36, R37 y M12 | Definir la anatomía de la tarjeta resumida y la cuadrícula del tablero ordenada por estado. | No implementada. La estructura del tablero se apoya en requisitos confirmados por el cliente (P-23, P-31); el diseño visual no está validado por el cliente. |
| CR-02 | Critique | Marcadores «Vencidas» y «Por vencer · menos de 30 min», sin ceros a la izquierda; cambiar «Pasos completados» por un dato con un alcance definido. | **Aceptada con ajustes** | *Ajuste del equipo:* priorizar los indicadores de tareas vencidas y por vencer. Conservar la idea de mostrar los pasos completados con un alcance claramente definido y **sin introducir requisitos funcionales nuevos**. Respetar S-09 y R33, **incluido exactamente el minuto 30**. El umbral sigue pendiente de A-05. | Dirección visual (marcadores); PRD R33, R38, S-09 y P-34; A-05 | Especificar los marcadores del tablero (vencidas y por vencer), el texto del umbral según S-09 y el alcance del indicador de pasos. | No implementada. Pendiente de A-05 (umbral). |
| CR-03 | Critique | Escala mínima: 14 px para metadatos, 13 px para chips, 16 px para cuerpo y pasos, y 15 px para botones. | Aceptada | Texto funcional de 9 a 11 px, confirmado por el detector y ampliado por AU-01. | PRD P-39, R40 y CE6; sistema de diseño §2.2 | Fijar la escala tipográfica mínima con Big Shoulders y Sora. | No implementada. Decisión de interfaz del equipo (SD-03). |
| CR-04 | Critique | Chip ajustado a su contenido con punto, icono y texto; franja de 4 px para vencida y por vencer; sistema para los cinco estados. | Aceptada | Solo existe el chip ámbar, estirado (línea 536); confirmado con medidas por AU-09. | Brief («tareas urgentes fáciles de reconocer»); PRD R31 y R37; sistema de diseño §7 | Definir el componente de chip de estado y la franja de urgencia para los cinco estados. | No implementada. Los colores de estado fuera de la paleta siguen pendientes de SD-02 y A-10. |
| CR-05 | Critique | Avance de solo lectura para el administrador; vista del estudiante basada en la Dirección C. | Aceptada | La vista del administrador muestra casillas que parecen marcables (S-27) y B no tiene vista de estudiante. | PRD S-27, R9 y §2; dirección visual (incorporar C) | Diferenciar los componentes por perfil: avance de solo lectura y checklist ejecutable. | No implementada. S-27 sigue pendiente de validación (A-01). |
| CR-06 | Critique | Área táctil mínima de 48 px y filas de paso de 56 px que se puedan pulsar enteras. | Aceptada | Casillas de 17 px y botón de 40 px; confirmado con medidas por AU-02. | PRD P-39 y R40; sistema de diseño §11.4 | Fijar las áreas táctiles mínimas y la fila de paso del checklist. | No implementada. Decisión de interfaz del equipo (SD-03). |
| CR-07 | Critique | Reservar el morado sólido para la acción o la señal; lima para el estado activo; barra en degradado de morado a lima. | **Aceptada con ajustes** | *Ajuste del equipo:* recuperar el lima de forma controlada para la actividad actual y el foco, valorar el degradado oficial de progreso y evitar la saturación visual. Las adaptaciones de marca relacionadas siguen pendientes de A-10 y SD-02. | Brand board («la lima es escasa», degradado de progreso, «una sola señal morada por vista»); A-10, SD-02; AU-05 y AU-07 | Definir el rol del lima (actividad actual y foco) y del morado (acción y señal), y valorar el degradado de progreso. | No implementada. Pendiente de A-10 y SD-02. |
| CR-08 | Critique | Usar el logotipo del brand board, o al menos el «2» en lima, mientras llegan los archivos. | **Aceptada con ajustes** | *Ajuste del equipo:* respetar el logotipo oficial del brand board. **No inventar ni presentar una reconstrucción como recurso oficial.** Los archivos gráficos independientes siguen pendientes de A-12. | Brand board §02 Logo; AC-01; E9b, A-12 | Indicar que el logotipo debe ser el oficial y registrar que faltan los archivos independientes. | No implementada. Pendiente de A-12. |
| CR-09 | Critique | Convertir los colores sueltos en pocas variables (texto atenuado, superficie y borde) y documentar las excepciones. | Aceptada | Se usan `--gris`, `#11091C` y unos 8 tonos de borde fuera de la paleta; cuantificado por AU-07 y AU-08. | Sistema de diseño §1; SD-03 | Consolidar los tokens de color de la interfaz. | No implementada. Decisión de interfaz del equipo (SD-03). |
| CR-10 | Critique | Bordes de 2 px y borde de control con contraste de al menos 3:1. | **Aceptada con ajustes** | *Ajuste del equipo:* se acepta mejorar el grosor y la coherencia de los bordes, pero se corrige la afirmación sobre el contraste de la casilla según AU-04: **el borde actual alcanza 5,83:1**. | Brand board (2 px); sistema de diseño §1.3 y §3.3; AU-04 | Bordes de 2 px coherentes con el brand board. El requisito de 3:1 se aplica a los elementos que identifican controles y estados (ver AU-04). | No implementada. Decisión de interfaz del equipo (SD-03). |
| CR-11 | Critique | Unificar los términos en «Lugar», «Vence» y «Avance». | Aceptada | Hay términos distintos para el mismo dato entre direcciones. | PRD R13 («lugar o aula») | Fijar la terminología de las etiquetas de datos. | No implementada. |
| CR-12 | Critique | Incorporar de C las filas de paso, el paso actual destacado, el progreso grande y el encabezado del estudiante, con «Guardar avance» y «Confirmar tarea». | Aceptada | C resuelve la ejecución en el celular; sus pasos de 53 a 54 px cumplen el objetivo táctil (AU-02). | Dirección visual (incorporar C); PRD R25, R42 y M15 | Definir la vista del estudiante y el detalle de la tarea, con guardar y confirmar diferenciados. | No implementada. R42 (S-30) sigue pendiente de validación (A-19). |

### Hallazgos de Audit

| ID | Informe | Recomendación original (IA) | Decisión (equipo) | Justificación | Relación | Implicación para el futuro DESIGN.md | Estado |
|---|---|---|---|---|---|---|---|
| AU-01 | Audit | Escala de 16, 14, 13 y 15 px; quitar `<small>` como mecanismo de tamaño. | Aceptada | Tamaños calculados de 9, 9,17, 10 y 11 px en B; el detector lo marca 9 veces. | CR-03; PRD P-39, R40 y CE6 | Igual que CR-03, más la regla de no usar `<small>` para fijar tamaños. | No implementada. |
| AU-02 | Audit | Botones de 48 px o más; casilla visual de 24 px dentro de una fila táctil de 56 px. | Aceptada | Botón de 40 px de alto y fila de checklist de 17 px, medidos en cinco anchos. | CR-06, CR-12; sistema de diseño §11.4 | Distinguir el tamaño visual de la casilla de su área táctil. | No implementada. |
| AU-03 | Audit | Pista de progreso con 3:1 o más frente a la tarjeta; contador en texto siempre visible; valorar el degradado oficial. | Aceptada | La pista mide 1,33:1 (WCAG 1.4.11). | CR-07, CR-10; brand board (degradado) | Especificar el componente de barra de progreso con su contador en texto. | No implementada. El degradado depende de la decisión sobre el lima (A-10, SD-02). |
| AU-04 | Audit | Borde de 3:1 o más en los elementos que se puedan pulsar. | **Aceptada con ajustes** | *Ajuste del equipo:* exigir 3:1 en los elementos **necesarios para identificar controles y estados**, **no indiscriminadamente en separadores decorativos**. | WCAG 1.4.11; CR-10; sistema de diseño §6.2 | Regla de contraste de bordes por tipo de elemento: control o estado frente a decorativo. | No implementada. |
| AU-05 | Audit | Contorno de foco lima de 3 px con 2 px de separación; tinta dentro de la tarjeta señal. | Aceptada | El CSS no tiene ninguna regla `:focus` ni `:focus-visible` (WCAG 2.4.7). | CR-07; sistema de diseño §4.3 | Definir el indicador de foco. | No implementada. Requisito para la implementación futura. |
| AU-06 | Audit | `<input type="checkbox">` nativo con su etiqueta; avance de solo lectura para el administrador. | Aceptada | Las casillas son `<span>` con «✓»: es una limitación esperable de la exploración y un requisito de la futura implementación. | CR-05; PRD S-27; sistema de diseño §8.2 | Requisito semántico de la casilla del checklist. | No implementada. Requisito para la implementación futura. |
| AU-07 | Audit | Convertir en variables el texto atenuado, la superficie, el borde y los estados; separar la marca de la interfaz. | **Aceptada con ajustes** | *Ajuste del equipo:* consolidar los tokens, **diferenciando las decisiones de interfaz del equipo (SD-03) de las adaptaciones de marca pendientes de validación (SD-02 y A-10)**. | CR-07, CR-09; SD-02, SD-03, A-10 | Sistema de tokens en dos niveles: marca oficial y equipo, con las adaptaciones de marca marcadas como pendientes. | No implementada. Las adaptaciones de marca siguen pendientes de A-10 y SD-02. |
| AU-08 | Audit | Usar los tokens `space-1` a `space-10` (base 4). | Aceptada | 30 valores de espaciado distintos, varios fuera de la base 4. | CR-09; brand board (escala base 4); sistema de diseño §3.1 | Adoptar la escala de espaciado de base 4. | No implementada. |
| AU-09 | Audit | Chip ajustado a su contenido, sin saltos de línea; cabecera de la tarjeta con su propio diseño. | Aceptada | Chip de 162, 291 y 114 px de ancho, y en dos líneas a 320 px. | CR-04 | Componente de chip independiente de la cuadrícula de datos. | No implementada. |
| AU-10 | Audit | Mostrar la vista de celular (360 a 390 px) por separado de la de escritorio. | Aceptada | La «pantalla» simulada mide 238 px a 320 px; la exploración no tiene una variante móvil propia. | CR-05, CR-12; PRD CE6 | Documentar las vistas de celular y escritorio, y verificar 320 y 360 px (CE6). | No implementada. |
| AU-11 | Audit | Pedir solo los pesos tipográficos que se usen. | **Aceptada con ajustes** | *Ajuste del equipo:* cargar únicamente los pesos que use el sistema definitivo. **No eliminar automáticamente Sora 600**, porque está contemplado en el sistema de diseño. | Sistema de diseño §2.1 (Sora 400 y 600) | Lista final de pesos tipográficos, incluido Sora 600. | No implementada. |

### Falsos positivos del detector

| ID | Informe | Recomendación original (detector de Impeccable) | Decisión (equipo) | Justificación | Relación | Implicación para el futuro DESIGN.md | Estado |
|---|---|---|---|---|---|---|---|
| FP-01 | Critique y Audit | `ai-color-palette` (3 apariciones: líneas 523, 527 y 663): evitar el morado y los tonos neón sobre fondo oscuro. | **Rechazada como defecto** | La combinación de morado y negro procede de la **identidad oficial** «Señal Neón», proporcionada por el cliente (AC-01). | Brand board; AC-01 | Mantener la paleta oficial. **Esto no implica rechazar** las mejoras de jerarquía visual ni la reducción del uso excesivo del morado (CR-07, AU-07). | Sin cambio. |
| FP-02 | Critique y Audit | `hero-eyebrow-chip` (1 aparición: línea 366): quitar la etiqueta pequeña sobre el título. | **Rechazada como defecto** | Corresponde al **patrón de encabezado del brand board** (kicker sobre el título), y aparece en la portada del documento de exploración. | Brand board (patrón de encabezado) | Mantener el patrón de kicker del brand board. | Sin cambio. |

## Limitaciones que siguen pendientes

- **Exploración estática.** No se verificaron la navegación con teclado, el lector de pantalla, el foco real, el comportamiento táctil ni los estados interactivos.
- **Critique se ejecutó en modo degradado.** Las evaluaciones A (diseño) y B (detector) se hicieron en el mismo contexto, porque no se autorizaron subagentes.
- **No se generaron capas visuales del detector** en ninguno de los dos informes.
- **Contraste.** Se calculó a partir de los colores del CSS, no con lecturas de píxeles.
- **Rendimiento.** No se midieron tiempos de carga ni métricas de experiencia (LCP, CLS).
- **El diseño adaptable medido es el del documento** de presentación, no el de la futura aplicación.
- **Los informes no se guardaron en `.impeccable/`**, por indicación del equipo, así que no hay historial de puntuaciones de Impeccable.
- **Validaciones del cliente pendientes** que afectan a estas decisiones:

| Punto | Tema | Decisiones afectadas |
|---|---|---|
| A-05 | Umbral de «por vencer» | CR-02 |
| A-10 y SD-02 | Adaptaciones de marca | CR-04, CR-07, AU-03 y AU-07 |
| A-12 | Archivos independientes del logotipo | CR-08 |
| A-19 | Checklist compartido, S-30 | CR-12 |
| A-01 | Permisos, S-27 | CR-05 |
