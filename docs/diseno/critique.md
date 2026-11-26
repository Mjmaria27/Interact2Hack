# Impeccable Critique: Dirección B «Control operativo»

> **Procedencia de este documento.** Es la transcripción del informe que generó Claude con la skill Impeccable (v4.11.0, comando `critique`) el 25 de noviembre de 2026, en la sesión de trabajo del Avance 2. El texto del informe no se reformuló.
>
> Solo se añadieron tres cosas, identificadas como tales:
> - este encabezado;
> - el apéndice con las respuestas del equipo a las preguntas de cierre;
> - una nota posterior en CR-10.
>
> Las decisiones del equipo sobre cada recomendación están en [`decisiones-impeccable.md`](decisiones-impeccable.md).
>
> **Alcance:** los resultados corresponden a una **exploración visual estática** (`style-tiles.html`), no a una aplicación funcional. Son recomendaciones de IA; no son validaciones del cliente.

⚠️ DEGRADED: single-context (no autorizaste subagentes, así que las evaluaciones A y B se hicieron en este mismo contexto, una tras otra: primero A completa y después el detector)

**Objetivo:** `docs/diseno/style-tiles.html`, solo la Dirección B; las direcciones A y C se usan como comparación.
**Base de la evaluación:** la apariencia real. Rendericé la página a 1440 × 900 y a 390 × 844 con `impeccable shot`, sobre una copia en la carpeta temporal, y además revisé el código fuente.
**Modo:** Operate (herramienta de trabajo).
**Contexto leído:** `brief.md`, `direccion-visual.md`, PRD v0.3, `sistema-de-diseno.md` y el brand board «Señal Neón». No hay `PRODUCT.md` ni `DESIGN.md`, y no ejecuté `init`.

## 1. Design Health Score

Un style tile es una exploración estática, sin interacción. Por eso marco como `n/a` las heurísticas que no se pueden evaluar sobre una imagen, en lugar de penalizar funciones que todavía no corresponde mostrar.

| # | Heurística | Puntuación | Problema principal |
|---|---|---|---|
| 1 | Visibilidad del estado del sistema | 2 | Solo aparece «Por vencer». El marcador «02 Pasos completados» no dice de qué es el total. No se ven las tareas vencidas, que según P-34 van primero. |
| 2 | Coincidencia con el mundo real | 3 | El lenguaje es claro y del dominio (aula, proyectores, responsable). «TAREA #001» introduce un número de tarea que el PRD no define. |
| 3 | Control y libertad del usuario | n/a | Es una maqueta estática: no hay flujos que deshacer. |
| 4 | Consistencia y estándares | 2 | El chip de estado se estira a la mitad del ancho en B, pero no en A ni en C. Hay casillas que parecen marcables en la vista del administrador, y los términos cambian entre direcciones («Ubicación», «Lugar», «Vence», «Vencimiento», «Avance», «Progreso»). |
| 5 | Prevención de errores | n/a | Sin interacción representada. |
| 6 | Reconocer antes que recordar | 3 | Cada dato tiene su etiqueta, y hay barra de progreso y contador. |
| 7 | Flexibilidad y eficiencia | n/a | Sin interacción representada. |
| 8 | Diseño estético y minimalista | 2 | La tarjeta del tablero incluye el checklist completo. El morado domina el texto, los marcadores, las casillas, la barra y el botón. |
| 9 | Recuperación de errores | n/a | Sin interacción representada. |
| 10 | Ayuda y documentación | n/a | No aplica a un style tile. |
| **Total** | | **12/20** | **Aceptable (60 %)** |

Con cinco heurísticas no aplicables, el máximo es 20. Según la escala de Impeccable, el 60 % corresponde a «Aceptable»: hacen falta mejoras importantes antes de que los usuarios queden satisfechos.

**Carga cognitiva:** fallan 2 de los 8 puntos de la lista de comprobación: la jerarquía visual (el título de la pantalla, el título de la tarea y los números morados compiten) y la revelación progresiva (el checklist completo en la tarjeta del tablero). Carga **moderada**. En ninguna decisión hay más de 4 opciones visibles.

## 2. Design Specificity Verdict

**Evaluación del diseño.** B pertenece claramente a Interact2Hack por la identidad: Big Shoulders en mayúsculas, Sora, el fondo #050307, esquinas rectas y contenido real del evento. Pero su **composición es la de cualquier panel de control**: dos tarjetas de métricas encima de una tarjeta de detalle. No se ve lo que la propia Dirección B promete y lo que el equipo valoró de ClickUp: **supervisar muchas tareas a la vez**, con responsables, vencimientos y estados en una vista de lista o tablero. Al mostrar una sola tarea, B y A se parecen más de lo que dicen sus descripciones. Además, se pierden dos rasgos propios de la marca:
- **el lima, que no aparece:** en el brand board «lima = ahora», que encaja con el estado «en ejecución»;
- **la barra de progreso en degradado de morado a lima** del brand board, que aquí es un morado plano.

**Escaneo automático** (`impeccable detect`, sobre la copia temporal): **27 hallazgos en el archivo, 11 de ellos en la Dirección B.**

| Regla | En el archivo | En B | Lectura |
|---|---|---|---|
| `undersized-ui-text` (texto funcional por debajo de 11 px) | 11 | 5 (líneas 513, 518, 524, 528 y 536) | **Coincide** con la revisión: etiquetas de los marcadores de 9 px, y chip de estado, etiqueta de rol y sección de 10 px. |
| `tiny-text` (texto de cuerpo por debajo de 12 px) | 12 | 4 (563, 568, 573 y 597) | **Coincide**: los pasos del checklist miden 11 px. La línea 597 es una anotación de la exploración, no parte de la interfaz. |
| `ai-color-palette` | 3 | 2 (523 y 527) | **Falso positivo como defecto.** El morado sobre negro es la identidad oficial «Señal Neón», proporcionada por el cliente (AC-01). Sí indica algo real: el morado está sobreutilizado (CR-07). |
| `hero-eyebrow-chip` | 1 | 0 (línea 366, portada de la exploración) | **Restricción oficial.** El kicker sobre el título es el patrón de encabezado del brand board, y aparece en la portada de la exploración, no en la interfaz. |

El detector no evalúa la composición; lo que encontró sobre tamaños y legibilidad coincide con la revisión manual.

**Capas visuales:** no están disponibles. En esta sesión no hay una herramienta de navegador capaz de inyectar el script del detector, así que no hubo servidor en vivo ni pestaña «[Human]».

## 3. Overall Impression

B es la base más honesta para el administrador: tiene datos con etiqueta, un estado visible, avance doble (barra y contador) y una sola acción principal. Su mayor oportunidad está en **mostrar el tablero de verdad**: varias tarjetas resumidas, agrupadas por estado, con lo vencido primero y la alerta arriba, tal como piden R36 a R38. Además, el checklist debería pasar al detalle de la tarea, donde la Dirección C ya resuelve bien la experiencia del estudiante.

## 4. What's Working (aspectos para conservar de la Dirección B)

1. **Fidelidad a la identidad oficial.** Usa Big Shoulders en mayúsculas para los títulos, Sora para la lectura, el negro y la tinta del brand board, las esquinas rectas y el morado en la acción principal. Se reconoce como Interact2Hack sin inventar nada ajeno a la marca.
2. **Una anatomía de tarjeta que se puede escanear.** La cuadrícula de datos con etiqueta (Ubicación, Responsable, Vencimiento, Avance) permite leer de un vistazo. El avance se codifica dos veces, con «2/3 pasos» y la barra, y no depende solo del color.
3. **Los marcadores del tablero y la etiqueta de rol.** La idea que el equipo destacó, contar las tareas por vencer, coincide con la alerta de R38. La etiqueta «ADMIN» en la barra superior es una forma simple de diferenciar los perfiles.

## 5. Priority Issues

| Prioridad | Problema | Recomendación | Comando sugerido |
|---|---|---|---|
| **P1** | El tablero no muestra supervisión de varias tareas | CR-01 | `/impeccable layout` |
| **P1** | Marcadores ambiguos y sin el de vencidas | CR-02 | `/impeccable clarify` |
| **P1** | Texto funcional de 9 a 11 px | CR-03 | `/impeccable typeset` |
| **P2** | Las tareas urgentes no se distinguen lo suficiente | CR-04 | `/impeccable colorize` |
| **P2** | Sin diferencia entre perfiles y con objetivos táctiles pequeños | CR-05, CR-06 y CR-12 | `/impeccable adapt` |

El detalle de cada una está en la sección 10.

## 6. Persona Red Flags

**Alex (usuario avanzado, el administrador durante el evento).** Para saber qué atender tiene que leer una tarjeta completa con su checklist, porque no hay una lista compacta de tareas. Los marcadores no dicen qué es urgente y no ve las tareas vencidas.

**Sam (usuario que depende de la accesibilidad).** El texto de 9 y 10 px falla al ampliar en pantallas pequeñas. Las casillas de 17 px tienen un borde morado de 1 px, por debajo del borde de control de 2 px al 38 % que fija el sistema de diseño. El estado «Por vencer» solo se comunica con color y texto, sin icono. Las casillas de la vista del administrador parecen interactivas sin serlo.

**Casey (usuario móvil distraído, el estudiante entre aulas).** B no tiene vista de estudiante. Al pasar la vista del administrador al celular, la acción queda al final de una tarjeta larga, y las casillas son demasiado pequeñas para el pulgar. La Dirección C sí resuelve este caso: filas grandes, paso actual destacado y «2/3» bien visible.

*Sin personas específicas del proyecto: no existe `PRODUCT.md` con una sección de usuarios.*

## 7. Minor Observations

- **Botón del administrador:** dice «Ver tarea», es morado y ocupa todo el ancho dentro de la tarjeta del tablero. En una cuadrícula con varias tarjetas, la tarjeta entera debería poder pulsarse (sistema de diseño §6.2), y el morado sólido quedaría reservado a la señal.
- **«TAREA #001»:** es un número de tarea que no existe en el PRD. Decidan si se queda.
- **Etiqueta de rol «ADMIN»:** en 10 px y con borde morado, compite con el logotipo.
- **Recorrido emocional:** el momento de mayor carga para el estudiante, confirmar una tarea, no aparece en ninguna dirección. Es esperable en una exploración, pero es el pico que conviene diseñar.

## 8. Questions to Consider

- ¿Cómo se vería B con seis tarjetas resumidas en lugar de una tarjeta completa?
- Si el administrador solo pudiera ver un número al entrar, ¿cuál sería: las vencidas o las por vencer?
- ¿Qué gana la plataforma si el lima marca solo «ahora» (en ejecución, el foco y la confirmación) y el morado queda para la acción?
- ¿B y C pueden ser dos vistas del mismo sistema, el tablero del administrador y el detalle del estudiante, en lugar de dos direcciones?

## 9. Lo que no cuento como defecto

La falta de los estados vencida, en ejecución, sin asignar y terminada; de «Sin responsables»; de guardar y confirmar; del aviso de error; y del estado de eliminación. La exploración no tenía por qué mostrarlos. Los registro como trabajo pendiente para el sistema definitivo, no como fallos de B.

## 10. Las 12 recomendaciones (CR-01 a CR-12)

Cada recomendación indica de qué **tipo** es:

| Tipo | Significado |
|---|---|
| **Restricción oficial** | Viene del brand board. |
| **Decisión del equipo** | Decisión visual propia de la exploración. |
| **Problema de diseño** | Problema en lo que sí está representado. |
| **No representado** | Ausencia esperable en una exploración. |
| **Mejora para el sistema definitivo** | Mejora para el sistema de diseño final. |

Las prioridades usan la escala de Impeccable:

| Prioridad | Nombre | Significado |
|---|---|---|
| **P1** | Importante | Causa dificultades o confusión importantes. |
| **P2** | Menor | Molesta, pero hay una forma de resolverlo. |
| **P3** | Pulido | Sin impacto real en el usuario. |

Ninguna llega a P0 (bloqueante): es una exploración, no una aplicación.

### CR-01 · El tablero no muestra supervisión de varias tareas
- **Tipo:** Problema de diseño.
- **Problema:** el tablero del administrador muestra una sola tarea con su checklist completo.
- **Evidencia:** líneas 532 a 585. Con 1440 px, la tarjeta ocupa toda la pantalla simulada; con 390 px, ocupa toda la altura útil.
- **Impacto:** el administrador no puede comparar tareas ni ver cuáles atender primero, que es la promesa de B.
- **Recomendación:** tarjeta resumida (chip de estado, hora, título, lugar, responsables y barra con contador) en una cuadrícula agrupada por estado, con lo vencido primero. El checklist pasa al detalle de la tarea.
- **Prioridad:** P1.
- **Justificación:** afecta a la función central del perfil de administrador y a la razón por la que se eligió B.
- **Relación:** brief (ClickUp, supervisar tareas); dirección visual («supervisar varias tareas al mismo tiempo»); PRD R36, R37 y M12.
- **Comando sugerido:** `/impeccable layout`.

### CR-02 · Marcadores ambiguos y sin el de vencidas
- **Tipo:** Problema de diseño.
- **Problema:** «02 Pasos completados» no dice si es un total del evento o de una tarea. «01 Por vencer» no indica el plazo. Los ceros a la izquierda sugieren un identificador. No hay marcador de tareas vencidas.
- **Evidencia:** líneas 521 a 530.
- **Impacto:** lectura ambigua del estado del evento, y lo más urgente (las vencidas) queda oculto.
- **Recomendación:** marcadores que correspondan a los estados del PRD: «Vencidas» y «Por vencer · menos de 30 min». Números sin ceros a la izquierda. El de «por vencer» puede ser la tarjeta señal de R38. Cambiar «Pasos completados» por un dato con un alcance definido.
- **Prioridad:** P1.
- **Justificación:** los marcadores son lo que el equipo más valoró de B. Si son ambiguos, se pierde la ventaja principal de esta dirección.
- **Relación:** dirección visual («marcadores visuales»); PRD R38, S-09 y P-34.
- **Comando sugerido:** `/impeccable clarify`.

### CR-03 · Texto funcional de 9 a 11 px
- **Tipo:** Problema de diseño.
- **Problema:** las etiquetas de los marcadores miden 9 px; el chip de estado, la etiqueta de rol y la sección, 10 px; los pasos, los datos y el botón, 11 px.
- **Evidencia:** el detector lo marca en 9 puntos de B (líneas 513, 518, 524, 528, 536, 563, 568 y 573, más la anotación de la 597).
- **Impacto:** lectura difícil en el celular, de pie y en movimiento.
- **Recomendación:** aplicar la escala del sistema de diseño (§2.2): 14 px para metadatos, 13 px para chips, 16 px para cuerpo y pasos, y 15 px para botones.
- **Prioridad:** P1.
- **Justificación:** afecta a la legibilidad de toda la vista y contradice el uso principal en celular.
- **Relación:** PRD P-39, R40 y CE6; sistema de diseño §2.2.
- **Comando sugerido:** `/impeccable typeset`.

### CR-04 · Las tareas urgentes no se distinguen lo suficiente
- **Tipo:** Problema de diseño.
- **Problema:** solo existe el chip ámbar de «Por vencer». En B se estira hasta la mitad del ancho porque está dentro de la cuadrícula de datos. No hay franja lateral ni un color para «vencida».
- **Evidencia:** línea 536.
- **Impacto:** la urgencia no destaca y la cabecera de la tarjeta se lee desordenada.
- **Recomendación:** chip ajustado a su contenido, con punto, icono y texto; franja de 4 px para vencida y por vencer; un sistema para los cinco estados.
- **Prioridad:** P2.
- **Justificación:** la urgencia es visible, pero débil. No impide entender la tarea.
- **Relación:** brief («tareas urgentes fáciles de reconocer»); PRD R31 y R37; sistema de diseño §7.
- **Comando sugerido:** `/impeccable colorize`.

### CR-05 · Sin diferencia real entre perfiles
- **Tipo:** No representado / problema de diseño.
- **Problema:** la vista del administrador muestra casillas que parecen marcables, y B no tiene vista de estudiante.
- **Evidencia:** líneas 562 a 577.
- **Impacto:** parece que el administrador puede marcar pasos (no puede, según S-27), y el estudiante no tiene una experiencia diseñada.
- **Recomendación:** avance de solo lectura para el administrador; vista del estudiante basada en la Dirección C (ver CR-12).
- **Prioridad:** P2.
- **Justificación:** genera una expectativa falsa en el administrador, aunque la ausencia de la vista del estudiante es esperable en una exploración.
- **Relación:** PRD S-27, R9 y §2; dirección visual (incorporar C).
- **Comando sugerido:** `/impeccable adapt`.

### CR-06 · Objetivos táctiles pequeños
- **Tipo:** Problema de diseño.
- **Problema:** las casillas miden 17 px y el botón unos 40 px de alto, con texto de 11 px.
- **Evidencia:** CSS de `.casilla` y `.boton`.
- **Impacto:** toques fallidos con el pulgar mientras se camina entre espacios.
- **Recomendación:** área táctil mínima de 48 px y filas de paso de 56 px que se puedan pulsar enteras.
- **Prioridad:** P2.
- **Justificación:** se puede usar, pero con errores frecuentes en el celular.
- **Relación:** PRD P-39 y R40; sistema de diseño §11.4.
- **Comando sugerido:** `/impeccable adapt`.

### CR-07 · El morado lo ocupa todo y el lima no aparece
- **Tipo:** Decisión del equipo.
- **Problema:** el morado se usa en los marcadores, las casillas, la barra, el botón, la sección y el «2» del logotipo. El lima no aparece.
- **Evidencia:** en el CSS de B, `var(--morado)` aparece en 7 componentes; `--lima` no se usa en ninguno.
- **Impacto:** todo tiene el mismo peso, sin una señal dominante, y se pierde «lima = ahora».
- **Recomendación:** reservar el morado sólido para la acción o la señal; usar el lima en el estado activo (el punto de «en ejecución» o el foco); barra en degradado de morado a lima.
- **Prioridad:** P2.
- **Justificación:** afecta a la jerarquía y a la fidelidad con la marca, pero no impide usar la interfaz.
- **Relación:** brand board («una sola señal morada por vista», «la lima es escasa», degradado de progreso); A-10 y SD-02.
- **Comando sugerido:** `/impeccable colorize`.
- **Estado:** pendiente de su decisión, después de Audit y considerando A-10 y SD-02, según su respuesta.

### CR-08 · Logotipo como texto
- **Tipo:** Restricción oficial.
- **Problema:** el logotipo es texto con el «2» en morado. El logotipo oficial es una pieza gráfica con el «2» en lima.
- **Evidencia:** líneas 510 a 512; brand board, sección 02 Logo.
- **Impacto:** se aleja de la marca en el elemento más visible de la pantalla.
- **Recomendación:** usar el logotipo del brand board, o al menos el «2» en lima, mientras llegan los archivos independientes.
- **Prioridad:** P3.
- **Justificación:** no afecta a la tarea, pero sí a la identidad.
- **Relación:** brand board; AC-01; E9b y A-12.
- **Comando sugerido:** `/impeccable polish`.

### CR-09 · Colores fuera de la paleta oficial
- **Tipo:** Mejora para el sistema definitivo.
- **Problema:** se usan `--gris #B3AABF`, `#11091C` y unos 8 tonos de borde morado (`#463452`, `#674B7A`, `#4D3562` y otros).
- **Evidencia:** CSS, líneas 21 a 337.
- **Impacto:** inconsistencia y dificultad para mantener el sistema.
- **Recomendación:** convertirlos en pocas variables (texto atenuado, superficie y borde), usar el blanco al 64 % y los bordes del brand board, y documentar las excepciones.
- **Prioridad:** P3.
- **Justificación:** no afecta al usuario directamente; afecta a la coherencia del sistema.
- **Relación:** sistema de diseño §1; SD-03.
- **Comando sugerido:** `/impeccable polish`.

### CR-10 · Bordes de 1 px
- **Tipo:** Problema de diseño.
- **Problema:** controles y tarjetas usan bordes de 1 px. El brand board usa 2 px, y el sistema de diseño pide 2 px al 38 % en los controles.
- **Evidencia:** CSS de `.tile`, `.tarea`, `.casilla` y `.metrica`.
- **Impacto:** casillas poco visibles para personas con baja visión.
- **Recomendación:** bordes de 2 px y borde de control con contraste de al menos 3:1.
- **Prioridad:** P3.
- **Justificación:** se corrige fácilmente; el impacto se concentra en la accesibilidad.
- **Relación:** brand board; sistema de diseño §1.3 y §3.3.
- **Comando sugerido:** `/impeccable polish`.

> **Nota posterior, no forma parte del informe original.** La auditoría (AU-04 en [`audit.md`](audit.md)) midió que el borde actual de 1 px de la casilla alcanza **5,83:1** frente a la tarjeta, por encima del 3:1 de WCAG 1.4.11. El equipo aceptó CR-10 con ajustes: se acepta mejorar el grosor y la coherencia de los bordes, y se corrige la idea de que la casilla tenga un problema de contraste. Ver [`decisiones-impeccable.md`](decisiones-impeccable.md).

### CR-11 · Términos distintos para el mismo dato
- **Tipo:** Problema de diseño.
- **Problema:** Ubicación y Lugar; Vencimiento y Vence; Avance y Progreso.
- **Evidencia:** líneas 420, 543, 647, 551, 655, 432 y 555.
- **Impacto:** una pequeña carga de traducción entre pantallas.
- **Recomendación:** unificar en «Lugar», «Vence» y «Avance», alineado con el PRD («lugar o aula»).
- **Prioridad:** P3.
- **Justificación:** es una molestia leve.
- **Relación:** PRD R13.
- **Comando sugerido:** `/impeccable clarify`.

### CR-12 · Elementos de la Dirección C para el estudiante
- **Tipo:** Mejora para el sistema definitivo.
- **Problema:** B no resuelve la ejecución del estudiante en el celular, pero la Dirección C sí.
- **Evidencia:** Dirección C, líneas 662 a 684: filas de paso grandes, paso actual destacado y «2/3» grande.
- **Impacto:** puede cubrir la debilidad declarada de B («demasiada información para un estudiante»).
- **Recomendación:** incorporar de C las filas de paso a todo el ancho, el paso actual destacado, el progreso grande y el encabezado del estudiante («Actividad asignada · Completa tus pasos»), con «Guardar avance» y «Confirmar tarea».
- **Prioridad:** P2.
- **Justificación:** resuelve el perfil de estudiante, que es el uso principal en celular.
- **Relación:** dirección visual (incorporar elementos de C); PRD R42, R25 y M15.
- **Comando sugerido:** `/impeccable adapt`.

### Resumen

| Prioridad | Recomendaciones |
|---|---|
| P1 | CR-01, CR-02 y CR-03 |
| P2 | CR-04, CR-05, CR-06, CR-07 y CR-12 |
| P3 | CR-08, CR-09, CR-10 y CR-11 |

**Puntuación de Impeccable:** 12/20 (Aceptable, 60 %).

## 11. Recomendaciones según sus respuestas

Pidieron evaluar las tres áreas antes de fijar un orden, y no implementar nada. Por eso los comandos que siguen son solo un mapa para cuando decidan; no ejecutaré ninguno sin su autorización.

1. **`/impeccable audit`** (siguiente paso que indicaron): revisión técnica de accesibilidad, contraste y diseño adaptable de la Dirección B, que completará la evidencia de CR-03, CR-06, CR-07 y CR-10.
2. **`/impeccable layout`**: CR-01.
3. **`/impeccable clarify`**: CR-02 y CR-11.
4. **`/impeccable typeset`**: CR-03.
5. **`/impeccable adapt`**: CR-05, CR-06 y CR-12.
6. **`/impeccable colorize`**: CR-04, y CR-07 solo si deciden introducir el lima.
7. **`/impeccable polish`**: CR-08, CR-09 y CR-10, como paso final.

Pueden pedirme que ejecute estos comandos de uno en uno, todos juntos o en el orden que prefieran. Cuando apliquen cambios, pueden volver a ejecutar `/impeccable critique` para ver cómo mejora la puntuación.

## 12. Notas de la ejecución

- **Snapshot no guardado.** La skill guarda cada crítica en `.impeccable/critique/` dentro del repositorio, y pediste no modificar archivos; por eso tampoco hay historial de puntuaciones.
- **Archivos temporales.** El detector y las capturas trabajaron sobre una copia en la carpeta temporal de la sesión.
- **Sin servidor en vivo.** No inicié ninguno, así que no queda nada que detener.
- **Estado del proyecto.** `git status` no muestra cambios. No ejecuté `audit`, `init` ni `document`, y no generé `DESIGN.md`.

---

## Apéndice: preguntas de cierre y respuestas del equipo

Al terminar el informe, Impeccable formuló tres preguntas. Estas son las respuestas del equipo, transcritas tal como las dieron:

| Pregunta | Respuesta del equipo |
|---|---|
| ¿Qué área quieren abordar primero (tablero e indicadores, legibilidad y uso táctil, o vista del estudiante con C)? | «Presenta primero el informe completo de Critique. Evaluaremos las tres áreas antes de establecer el orden de implementación. No realices modificaciones todavía.» |
| ¿Cómo quieren tratar el color (morado dominante, lima ausente; CR-07)? | «Consideraremos introducir el lima de manera controlada, respetando la identidad oficial. La decisión definitiva se tomará después de revisar Critique y Audit, considerando A-10 y SD-02. No implementar todavía.» |
| ¿Qué alcance quieren llevar al sistema de diseño definitivo? | «Presenta las 12 recomendaciones completas, CR-01 a CR-12, con su evidencia, prioridad, justificación y puntuación de Impeccable. El equipo decidirá cuáles aceptar, ajustar o rechazar después de realizar también Audit. No implementar cambios ni generar DESIGN.md todavía.» |
