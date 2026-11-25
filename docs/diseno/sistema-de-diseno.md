# Sistema de Diseño · Interact2Hack Staff

**Estado:** Borrador v0.1 (Avance 2)
**Fecha:** 25 de noviembre de 2026
**Equipo:** María Paula Baca y Carlos Aluisa
**Producto:** Plataforma de coordinación del staff de Interact2Hack (ver `docs/prd/PRD.md`, v0.2)
**Referencia visual:** `docs/diseno/Interact2Hack-Brandboard.html` («Señal Neón» v1.0)

---

## 0. Cómo leer este documento

### Origen de cada decisión

Cada decisión lleva una marca que indica de dónde viene:

| Marca | Significado |
|---|---|
| **[BB]** | Viene del Brandboard «Señal Neón» v1.0. Se aplica sin cambios. |
| **[PRD]** | Viene de un requisito, regla o supuesto del PRD (M-xx, R-xx, S-xx, P-xx). **[DESC]** indica que el PRD lo toma de la descripción del proyecto. |
| **[EQUIPO]** | Propuesta del equipo para cubrir algo que el Brandboard no define. El cliente no la ha validado. |

### Estatus del Brandboard

- **Es una referencia visual, no una aprobación del cliente.** El Brandboard dice que se extrajo de la presentación para auspiciantes 2027 de Interact2Hack (USFQ Medios Interactivos y NESTLab). En el PRD sigue abierto el punto A-12, porque falta recibir la carpeta oficial de identidad visual. Tampoco hay respuesta sobre si la plataforma debe seguir la estética tecnológica del hackathon o ser más sobria (A-10, P-45). Mientras ambos puntos sigan abiertos, este sistema trata el Brandboard como referencia visual.
- **Lo que se mantiene sin cambios [BB]:**
  - Tipografías: Big Shoulders Display y Sora.
  - Los cinco colores de marca.
  - Esquinas rectas (radio 0).
  - Modo oscuro único.
  - Iconografía de línea.
  - Escala de espaciado.

### Qué no cubre el Brandboard

El Brandboard se hizo para una landing, una app de participantes, redes sociales y slides. No define nada de lo que necesita una herramienta operativa de tareas. Por eso este documento añade, marcado como [EQUIPO]:

| Lo que falta en el Brandboard | Dónde se resuelve |
|---|---|
| Colores semánticos (error, advertencia) y colores de estado | §1 y §7 |
| Campos de formulario, casillas de verificación y validaciones | §5 y §8 |
| Estados deshabilitado, foco y pulsado | §4 |
| Diálogos de confirmación | §8 |
| Ajustes de contraste en bordes de componentes interactivos | §1 y §11 |

Hay además dos reglas del Brandboard que chocan con un tablero de muchas tareas: **«una sola señal morada por vista»** y **«la lima es escasa»**. Cómo se adaptan está explicado en §7 y §9.

---

## 1. Colores y variables de diseño

### 1.1 Colores de marca [BB]

Son los cinco colores oficiales del Brandboard, con sus mismos roles.

| Token | HEX | Rol en el Brandboard | Uso en la plataforma |
|---|---|---|---|
| `--i2h-black` | `#050307` | Fondo de todo; base del sistema | Fondo de todas las pantallas |
| `--i2h-ink` | `#0B0612` | Texto sobre morado y lima; menús | Superficie de tarjetas, campos, diálogos y menús; texto sobre morado y lima |
| `--i2h-purple` | `#A46CFB` | Color de marca: señal, kicker, acción | Botón primario, alerta de tareas por vencer, kickers, casillas marcadas |
| `--i2h-purple-deep` | `#5B2BB5` | Grado de foto, fases, avatares | Avatares de responsables. **Nunca como texto.** |
| `--i2h-lime` | `#5CF000` | Un solo dato clave o estado activo | Pestaña activa, estado «en ejecución», foco de teclado, hover del primario |

**Derivados del Brandboard [BB]:**

| Token | Valor | Uso |
|---|---|---|
| `--i2h-white` | `#FFFFFF` | Texto principal |
| `--i2h-muted` | `rgba(255,255,255,0.64)` | Texto secundario y metadatos |
| `--i2h-faint` | `rgba(255,255,255,0.14)` | Bordes de chips y tarjetas |
| `--i2h-hair` | `rgba(255,255,255,0.09)` | Separadores finos |
| `--i2h-progress` | `linear-gradient(90deg, #A46CFB, #5CF000)` | Barras de progreso |

**Proporción por pantalla [BB]:** negro 70 %, texto 16 %, morado 9 %, morado profundo 3 % y lima 2 %.

### 1.2 Colores semánticos propuestos [EQUIPO]

El Brandboard no tiene colores de error ni de advertencia. En su propia documentación usa `#FF6B6B` y `#FFC857` para marcar «No» y «Solo texto grande», pero no les asigna token ni rol. Los proponemos como colores semánticos, **separados de la paleta oficial** con el prefijo `--i2h-st-` (estado) y `--i2h-fb-` (retroalimentación).

| Token | Valor | Uso | Origen |
|---|---|---|---|
| `--i2h-st-vencida` | `#FF6B6B` | Estado «vencida» | [EQUIPO], con un tono que ya aparece en el Brandboard |
| `--i2h-st-por-vencer` | `#FFC857` | Estado «por vencer» | [EQUIPO], con un tono que ya aparece en el Brandboard |
| `--i2h-st-en-ejecucion` | `#5CF000` (lima) | Estado «en ejecución» | [BB]: «lima = ahora», chip «En curso» |
| `--i2h-st-sin-asignar` | `rgba(255,255,255,0.64)` | Estado «sin asignar» | [BB]: color atenuado |
| `--i2h-st-terminada` | `#A46CFB` (morado) | Estado «terminada» | [EQUIPO], con un color de marca |
| `--i2h-fb-error` | `#FF6B6B` | Errores de formulario y acciones destructivas | [EQUIPO] |
| `--i2h-fb-exito` | `#5CF000` | Aviso de acción completada | [BB]: el aviso breve del Brandboard es lima |
| `--i2h-border-control` | `rgba(255,255,255,0.38)` | Borde de campos y casillas | [EQUIPO], para cumplir 3:1 (ver 1.3) |

### 1.3 Contraste verificado

Los ratios se **calcularon con la fórmula de luminancia relativa de WCAG 2.x**. No están estimados. Los colores con transparencia se calcularon ya mezclados con el fondo.

**Texto** (AA pide 4,5:1 en texto normal y 3:1 en texto grande, es decir 24 px o más, o 18,66 px en negrita):

| Texto / fondo | Ratio | Resultado | Origen del color |
|---|---|---|---|
| Blanco / negro `#050307` | 20,54:1 | AA y AAA | [BB] |
| Blanco / tinta `#0B0612` | 20,02:1 | AA y AAA | [BB] |
| Blanco 64 % / negro | 8,27:1 | AA y AAA | [BB] |
| Blanco 64 % / tinta | 8,20:1 | AA y AAA | [BB] |
| Lima / negro | 13,61:1 | AA y AAA | [BB] |
| Tinta / lima | 13,27:1 | AA y AAA | [BB] |
| Morado / negro | 5,98:1 | AA | [BB] |
| Morado / tinta | 5,83:1 | AA | [BB] |
| Tinta / morado | 5,83:1 | AA | [BB] |
| Blanco / morado profundo | 8,54:1 | AA y AAA | [BB] |
| `#FF6B6B` / negro | 7,40:1 | AA y AAA | [EQUIPO] |
| `#FF6B6B` / tinta | 7,21:1 | AA y AAA | [EQUIPO] |
| `#FFC857` / negro | 13,35:1 | AA y AAA | [EQUIPO] |
| `#FFC857` / tinta | 13,01:1 | AA y AAA | [EQUIPO] |

**Combinaciones restringidas:**

| Texto / fondo | Ratio | Regla |
|---|---|---|
| Blanco / morado | 3,43:1 | Solo texto de 24 px o más. En lo demás, usar tinta [BB]. |
| Blanco 45 % / negro | 4,43:1 | Solo texto grande, decorativo o de controles deshabilitados. |
| Tinta al 72 % / morado | ≈4,0:1 | **No cumple AA en texto pequeño.** El Brandboard usa esta opacidad en la etiqueta de la tarjeta señal; aquí la etiqueta va en tinta al 100 % [EQUIPO]. |
| Morado profundo / negro | 2,40:1 | Nunca para texto [BB]. |

**Elementos que no son texto** (WCAG 1.4.11 pide 3:1 en los bordes de componentes interactivos y en indicadores):

| Elemento | Ratio | Resultado |
|---|---|---|
| Borde blanco 14 % / negro (borde del Brandboard) | 1,37:1 | **No cumple.** Se mantiene solo en chips y tarjetas, porque su contenido ya los identifica. |
| Borde blanco 38 % / negro (`--i2h-border-control`) | 3,44:1 | Cumple. Es obligatorio en campos y casillas [EQUIPO]. |
| Morado 38 % / negro | 1,72:1 | No cumple. No se usa como indicador de hover [EQUIPO]. |
| Lima sobre morado | 2,28:1 | No cumple. El foco lima no se usa dentro de la tarjeta señal [EQUIPO]. |
| Puntos de estado sobre tinta | 5,83 a 13,27:1 | Cumplen. |

Solo se declara conformidad AA en las combinaciones verificadas de esta tabla. Una combinación nueva tiene que calcularse antes de usarla.

### 1.4 Variables de diseño

```css
:root {
  /* Marca [BB], valores idénticos al Brandboard */
  --i2h-black: #050307;
  --i2h-ink: #0B0612;
  --i2h-purple: #A46CFB;
  --i2h-purple-deep: #5B2BB5;
  --i2h-lime: #5CF000;
  --i2h-white: #FFFFFF;
  --i2h-muted: rgba(255,255,255,0.64);
  --i2h-faint: rgba(255,255,255,0.14);
  --i2h-hair: rgba(255,255,255,0.09);
  --i2h-progress: linear-gradient(90deg, #A46CFB, #5CF000);

  /* Semánticos [EQUIPO], fuera de la paleta oficial */
  --i2h-st-vencida: #FF6B6B;
  --i2h-st-por-vencer: #FFC857;
  --i2h-st-en-ejecucion: var(--i2h-lime);
  --i2h-st-sin-asignar: var(--i2h-muted);
  --i2h-st-terminada: var(--i2h-purple);
  --i2h-fb-error: #FF6B6B;
  --i2h-fb-exito: var(--i2h-lime);
  --i2h-border-control: rgba(255,255,255,0.38);
  --i2h-disabled-text: rgba(255,255,255,0.45);

  /* Tipografía [BB] */
  --i2h-display: 'Big Shoulders Display', 'Arial Narrow', sans-serif; /* 700, 900 */
  --i2h-body: 'Sora', 'Segoe UI', sans-serif;                         /* 400, 600 */

  /* Espacio, base 4 [BB] */
  --i2h-space-1: 4px;  --i2h-space-2: 8px;  --i2h-space-3: 12px;
  --i2h-space-4: 16px; --i2h-space-5: 24px; --i2h-space-6: 32px;
  --i2h-space-7: 48px; --i2h-space-8: 64px; --i2h-space-9: 96px;
  --i2h-space-10: 120px;

  /* Forma [BB] */
  --i2h-radius: 0;
  --i2h-border: 2px solid var(--i2h-faint);
  --i2h-shadow-float: 0 18px 60px rgba(0,0,0,0.6);

  /* Interacción [EQUIPO] */
  --i2h-touch-min: 48px;
  --i2h-focus-ring: 3px solid var(--i2h-lime);
  --i2h-focus-offset: 2px;

  /* Movimiento [BB] */
  --i2h-ease: cubic-bezier(0.16, 1, 0.3, 1);
  --i2h-dur-ui: 200ms;
}
```

---

## 2. Tipografías y jerarquía de textos

### 2.1 Familias [BB]

| Familia | Pesos | Uso | Reglas |
|---|---|---|---|
| **Big Shoulders Display** | 900 (principal), 700 | Títulos de pantalla, cifras y hora de vencimiento | Siempre en mayúsculas. Interlineado de 0,88 a 0,95. **Nunca por debajo de 24 px ni en párrafos.** |
| **Sora** | 400 (lectura), 600 (énfasis, etiquetas, botones) | Toda la interfaz: checklist, formularios, metadatos, navegación | Interlineado de 1,4 a 1,6 en párrafos. |

Las dos son de Google Fonts y tienen licencia SIL Open Font License 1.1 [BB].

### 2.2 Escala de la interfaz

La escala base es la de «Web móvil» y «Web escritorio» del Brandboard. Los ajustes del equipo están marcados.

| Rol | Celular | Escritorio | Familia y peso | Origen | Uso en la plataforma |
|---|---|---|---|---|---|
| Título de pantalla (H1) | 44 / 0,92 | 72 / 0,92 | Big Shoulders 900 | [BB] | «Tablero», «Mis tareas» |
| Sección (H2) | 32 / 0,95 | 48 / 0,95 | Big Shoulders 900 | [BB] | Grupos del tablero: «Vencidas», «Por vencer»… |
| Subtítulo (H3) | 24 / 1 | 32 / 1 | Big Shoulders 900 | [BB] | Título del diálogo y título de la tarea en el detalle |
| Hora de vencimiento | 24 / 1 | 24 / 1 | Big Shoulders 900 | [BB], patrón de la agenda de la app | «14:30» en la tarjeta |
| Kicker | 12 · +0,2 em | 14 · +0,2 em | Sora 600, mayúsculas | [BB] | Etiqueta sobre títulos; tiempo relativo |
| Título de tarea en tarjeta | 17 / 1,3 | 17 / 1,3 | Sora 600 | [BB], el «Headline» de la app | Nombre de la tarea |
| Cuerpo | 16 / 1,6 | 17 / 1,6 | Sora 400 | [BB] | Descripción y pasos del checklist |
| Botón y etiqueta de campo | 15 / 1 (botón) · 14 (etiqueta) | igual | Sora 600 | [BB] botón · [EQUIPO] etiqueta | |
| Texto de campos | **16** | 16 | Sora 400 | [EQUIPO] | Evita el zoom automático en iOS |
| Metadatos | **14** / 1,5 | 14 / 1,5 | Sora 400, blanco 64 % | [EQUIPO]. El Brandboard usa 12–13. | Lugar, responsables, «marcado por…» |
| Pequeño | 13 / 1,5 | 13 / 1,5 | Sora 400, blanco 64 % | [BB] | Ayudas de campo, notas |
| Barra inferior | **11** | — | Sora 600 | [EQUIPO]. El Brandboard usa 10. | Etiquetas de pestañas |

**Por qué los ajustes:** el staff usa la plataforma de pie, en movimiento y durante jornadas largas (P-39). Los tamaños de 10 y 12 px del Brandboard están pensados para una app de consulta ocasional.

### 2.3 Patrón de encabezado [BB]

El kicker en Sora 600 morado va sobre el título en Big Shoulders 900, con 14 a 20 px de separación. Puede haber como máximo una palabra o cifra en lima dentro del título.

> Ejemplo: kicker «JUEVES 19 · 3 PENDIENTES» y título «MIS TAREAS».

### 2.4 Voz y tono [BB]

- Se trata de **«tú»** al usuario. Las frases son cortas y directas, y van primero el dato y luego lo que significa.
- Las fechas se escriben completas. Junto a la hora se pone el tiempo relativo: «14:30 · vence en 12 min».
- Ejemplos para la interfaz [EQUIPO]:
  - Error: «Escribe el lugar o aula de la tarea.»
  - Estado vacío: «No tienes tareas asignadas por ahora.»
  - Botón deshabilitado: «Faltan 2 pasos para confirmar.»

---

## 3. Espaciados, bordes y esquinas

### 3.1 Escala de espaciado [BB]

Todo se mide en múltiplos de 4 px.

| Token | Valor | Uso típico en la plataforma |
|---|---|---|
| `space-1` | 4 px | Separación entre icono y texto en chips |
| `space-2` | 8 px | Separación mínima entre elementos tocables |
| `space-3` | 12 px | Espacio interno de chips; separación entre etiqueta y campo |
| `space-4` | 16 px | Margen lateral en celular; espacio interno de tarjetas en celular; medianil |
| `space-5` | 24 px | Espacio interno de tarjetas en escritorio; separación entre campos |
| `space-6` | 32 px | Separación entre secciones de una pantalla |
| `space-7` | 48 px | Altura mínima de controles; separación entre bloques grandes |
| `space-8` a `space-10` | 64 / 96 / 120 px | Márgenes de pantalla en escritorio; uso poco frecuente |

### 3.2 Retícula [BB]

| Dispositivo | Columnas | Margen | Medianil | Ancho máximo |
|---|---|---|---|---|
| Celular (menos de 720 px) | 4 | 16 a 20 px | 16 px | — |
| Tablet (720 a 1.099 px) | 8 | 32 px | 24 px | — |
| Escritorio (1.100 px o más) | 12 | automático | 24 px | 1.200 px |

### 3.3 Bordes [BB, con un ajuste del EQUIPO]

| Tipo | Valor | Uso | Origen |
|---|---|---|---|
| Línea fina | 1 px blanco 9–14 % | Separadores de lista y de secciones | [BB] |
| Borde de componente | 2 px blanco 14 % | Chips, tarjetas y paneles | [BB] |
| Borde de control | 2 px blanco 38 % | Campos de formulario y casillas | [EQUIPO], porque el 14 % no llega a 3:1 (§1.3) |
| Acento de estado | 4 px a la izquierda | Tarjetas vencidas y por vencer (§6) | [EQUIPO], variante del borde lima de 6 px de la tarjeta de contacto [BB] |
| Acento de lista | 3–4 px morado arriba | Listas numeradas | [BB] |

### 3.4 Esquinas y profundidad [BB]

- **Radio 0 en todo:** botones, tarjetas, chips, campos, casillas, diálogos y alertas.
- Las únicas formas curvas son los **puntos indicadores** (estado, pestaña activa) y los **avatares** circulares.
- **Sin sombras** en superficies. Solo los menús desplegables y los diálogos llevan `0 18px 60px rgba(0,0,0,.6)`.
- La profundidad se logra con el brillo radial morado, que se usa **solo** en la pantalla de inicio de sesión.

---

## 4. Botones

**Función:** iniciar las acciones del usuario. Hay como máximo **un botón primario por vista** [BB: «una sola señal morada»].

### 4.1 Variantes

| Variante | Normal | Hover y pulsado | Origen | Uso en la plataforma |
|---|---|---|---|---|
| **Primario** | Fondo morado, texto tinta, borde morado de 2 px | Fondo y borde lima, texto tinta (13,27:1) | [BB] | «Confirmar tarea», «Guardar tarea», «Iniciar sesión» |
| **Secundario** | Fondo transparente, borde morado de 2 px, texto blanco | Fondo morado, texto tinta | [BB] | «Cancelar», «Volver», «Editar» |
| **Destructivo** | Fondo transparente, borde `#FF6B6B` de 2 px, texto `#FF6B6B` (7,40:1) | Fondo `#FF6B6B`, texto tinta | [EQUIPO] | «Eliminar tarea», «Eliminar usuario» |
| **Enlace** | Big Shoulders 900 en mayúsculas, subrayado lima de 4 px | Subrayado más grueso | [BB] | Enlaces destacados, por ejemplo «Ver todas las vencidas» |

### 4.2 Medidas

- **Forma y texto [BB]:** Sora 600 de 15 px, radio 0, espacio interno de 14 × 22 px y transición de 0,2 s.
- **Altura mínima [EQUIPO]:** 48 px. El Brandboard pide un área táctil de 44 × 44 px como mínimo; subimos a 48 para un uso intensivo en celular.
- **Celular [BB]:** la acción principal ocupa todo el ancho, como en la app del Brandboard.
- **Iconos [BB]:** 18 px, de línea, con trazo de 2,4 y 10 px de separación con el texto.

### 4.3 Estados

| Estado | Apariencia | Comportamiento | Origen |
|---|---|---|---|
| Normal | Según la variante | — | [BB] |
| Hover | Según la variante | Transición de 0,2 s; solo con puntero | [BB] |
| Pulsado | Igual que hover | Se ve al tocar en pantallas táctiles | [EQUIPO] |
| Foco de teclado | Contorno lima de 3 px con 2 px de separación (13,61:1 sobre negro) | Visible solo con navegación por teclado (`:focus-visible`) | [EQUIPO] |
| Foco dentro de la tarjeta señal | Contorno tinta de 3 px (5,83:1 sobre morado) | El lima sobre morado se queda en 2,28:1 | [EQUIPO] |
| Deshabilitado | Fondo transparente, borde blanco 14 %, texto blanco 45 % | Sin hover y con `cursor: not-allowed`. Siempre va acompañado de un texto que explique por qué (§8) | [EQUIPO] |
| Cargando | Texto «Guardando…» y botón inactivo | Evita envíos dobles | [EQUIPO] |

**Nota sobre el deshabilitado:** WCAG no exige contraste en controles deshabilitados. Aun así, el motivo se explica con texto en blanco 64 % (8,27:1), para que la información no dependa del estilo.

---

## 5. Campos de formulario y validaciones

El Brandboard no define formularios. Todo este apartado es **[EQUIPO]** y respeta las reglas visuales del Brandboard: radio 0, Sora, fondo oscuro y sin sombras.

**Dónde se usan [PRD]:**
- Inicio de sesión (R1, M1).
- Cambio de contraseña (R3, M4).
- Gestión de usuarios: nombre, correo y perfil (R2, M3).
- Creación y edición de tareas (R13, M5).
- Asignación de responsables (R20, M6).
- Observaciones al completar una tarea (R27).

### 5.1 Anatomía

| Parte | Apariencia |
|---|---|
| Etiqueta | Sora 600 de 14 px, blanco, **siempre visible encima del campo** (nunca solo como texto de ejemplo). Los campos obligatorios llevan «(obligatorio)» en texto, no solo un asterisco. |
| Campo | Fondo tinta `#0B0612`, borde de 2 px blanco 38 % (3,44:1), radio 0, altura de 48 px, espacio interno de 12 × 16 px, Sora 400 de 16 px blanco. |
| Texto de ejemplo | Blanco 45 %. Es solo orientativo y nunca sustituye a la etiqueta. |
| Ayuda | Sora 400 de 13 px, blanco 64 %, debajo del campo. |
| Mensaje de error | Sora 400 de 13 px, `#FF6B6B` (7,21:1 sobre tinta), con icono de alerta. Sustituye a la ayuda. |

### 5.2 Tipos de campo

| Tipo | Uso | Particularidades |
|---|---|---|
| Texto | Nombre, lugar o aula, título | — |
| Correo | Correo del usuario (R2) | Teclado de correo en celular |
| Contraseña | Inicio de sesión y cambio de contraseña (R3) | Botón «Mostrar» de 48 × 48 px dentro del campo |
| Fecha y hora | Vencimiento de la tarea (R13) | Selector nativo del sistema; hora local de Ecuador (S-18) |
| Área de texto | Descripción (R13) y observaciones (R27) | Mínimo 4 líneas; crece con el contenido |
| Lista editable | Pasos del checklist (R13) | Cada paso es un campo de texto, con botones «Añadir paso» (secundario) y «Quitar» (icono de 48 × 48 px). Mínimo 1 paso. |
| Selección múltiple | Responsables (R20) | Lista con buscador. Los elegidos se muestran como chips [BB] que se pueden quitar. El campo es opcional mientras siga vigente el supuesto **S-23** (A-22). |
| Selección única | Perfil del usuario (R6) | Super admin, administrador o estudiante. Las opciones dependen de los permisos de quien edita (R8, S-01). |

### 5.3 Estados del campo

| Estado | Apariencia |
|---|---|
| Normal | Borde blanco 38 % |
| Hover | Borde blanco 64 % |
| Foco | Borde morado de 2 px y contorno lima de 3 px con 2 px de separación |
| Con error | Borde `#FF6B6B` y mensaje de error debajo |
| Deshabilitado | Borde blanco 14 % y texto blanco 45 % |
| Solo lectura | Sin borde y texto blanco; se usa para mostrar datos en el detalle |

### 5.4 Validaciones

**Cuándo se valida:**
- **Al salir del campo:** solo los campos que el usuario ya tocó.
- **Al enviar:** se validan todos. Si hay errores, aparece arriba del formulario un **resumen** con un enlace a cada error, y el foco pasa al resumen.
- **No se valida mientras se escribe.**

**Cómo se comunica el error:**
- Siempre con texto, icono y color: nunca solo con color.
- El mensaje queda asociado al campo para los lectores de pantalla (`aria-describedby` y `aria-invalid="true"`).

**Reglas de validación del PRD:**

| Formulario | Campo | Regla | Mensaje | Origen |
|---|---|---|---|---|
| Tarea | Fecha y hora de vencimiento | Obligatoria | «Indica la fecha y la hora de vencimiento.» | [PRD] R13 |
| Tarea | Lugar o aula | Obligatorio | «Escribe el lugar o aula de la tarea.» | [PRD] R13 |
| Tarea | Descripción | Obligatoria | «Describe qué hay que hacer.» | [PRD] R13 |
| Tarea | Checklist | Al menos 1 paso con texto | «Añade al menos un paso.» | [PRD] R13 |
| Tarea | Responsables | Opcional; sin ellos la tarea queda «sin asignar» | — | [PRD] R14, S-23 |
| Usuario | Nombre | Obligatorio | «Escribe el nombre.» | [PRD] R2 |
| Usuario | Correo | Obligatorio y con formato de correo | «Escribe un correo válido, por ejemplo nombre@usfq.edu.ec.» | [PRD] R2 |
| Inicio de sesión | Credenciales | Error genérico, sin revelar qué dato falló | «Correo o contraseña incorrectos.» | [EQUIPO] |

---

## 6. Tarjetas de tareas

**Función:** resumir una tarea y llevar a su detalle. Se usan en:
- **Tablero de cumplimiento** del administrador: cuadrícula de tarjetas (R36, R37, M12, P-31).
- **Lista de tareas** del estudiante (M7, R9).

### 6.1 Anatomía

```
┌─────────────────────────────────────┐
▌ ● VENCIDA ⚠                         │  ← chip de estado (§7)
▌                                     │
▌ 14:30   VENCIÓ HACE 5 MIN           │  ← hora (Big Shoulders 24) + kicker relativo
▌ Preparar el aula de mentoría        │  ← título (Sora 600, 17 px)
▌ 📍 Aula 205 · Edificio Galileo      │  ← lugar (Sora 14, blanco 64 %)
▌ 👤 Ana R., Mateo V.                 │  ← responsables (Sora 14, blanco 64 %)
▌ ▬▬▬▬▬▬▬▬▬▬░░░░░░  3/5 pasos         │  ← barra de progreso [BB] + contador
└─────────────────────────────────────┘
 ▌ = franja de estado de 4 px (solo en vencida y por vencer)
```

| Parte | Apariencia | Origen |
|---|---|---|
| Contenedor | Fondo tinta `#0B0612`, borde de 2 px blanco 14 %, radio 0, sin sombra. Espacio interno de 16 px en celular y 24 px en escritorio. | [BB] |
| Franja de estado | 4 px a la izquierda, solo en **vencida** (`#FF6B6B`) y **por vencer** (`#FFC857`) | [EQUIPO] |
| Chip de estado | Ver §7 | [BB], adaptado |
| Hora de vencimiento | Big Shoulders 900 de 24 px, blanco. Es el dato que más se consulta. | [BB], patrón de agenda |
| Tiempo relativo | Kicker en Sora 600, mayúsculas, +0,2 em, blanco 64 %: «VENCE EN 12 MIN» o «VENCIÓ HACE 5 MIN» | [EQUIPO] |
| Título | Sora 600 de 17 px, blanco, 2 líneas como máximo y elipsis | [BB] |
| Lugar o aula | Icono de 20 px y Sora 400 de 14 px, blanco 64 % | [PRD] M5 · [EQUIPO] estilo |
| Responsables | Icono y nombres, o «Sin responsables» | [PRD] R39 |
| Avance | Barra de 4 px con el degradado morado → lima, fondo blanco 14 % y contador «3/5 pasos» | [BB] barra de progreso |

### 6.2 Comportamiento

- **Toda la tarjeta se puede tocar** y abre el detalle de la tarea. Se marca como un único enlace para los lectores de pantalla, con un nombre accesible del tipo «Preparar el aula de mentoría, vencida, 14:30».
- **Hover:** el borde pasa a morado sólido de 2 px (5,98:1). Se descartó el morado al 38 % porque solo llega a 1,72:1 [EQUIPO].
- **Foco:** contorno lima de 3 px (§4.3).
- **Las tarjetas no van rellenas de morado.** El relleno morado queda reservado a la alerta de tareas por vencer (§9), por la regla de una sola señal por vista [BB].
- **Tareas terminadas:** misma tarjeta, sin franja, con el chip «Terminada» y sin barra de avance. No se reduce la opacidad, para no perder contraste.
- **Ordenación del tablero [PRD R37]:** vencidas, por vencer (de la más cercana a la más lejana), en ejecución, sin asignar y terminadas. Cada grupo lleva un título H2 con el número de tareas.

### 6.3 Variantes por perfil

| Perfil | Diferencias |
|---|---|
| Administrador | Muestra siempre los responsables, porque necesita ver quién tiene cada tarea (R39). |
| Estudiante | Solo ve sus tareas (R9). En los responsables muestra «Tú» y, si hay más, «Tú y 2 más». |

---

## 7. Los cinco estados de tarea

**Origen funcional [PRD]:** R31 define los cinco estados y R37 su orden en el tablero (P-23). Los criterios para calcularlos (R32 a R35) dependen de los supuestos **S-08** («en ejecución» al marcar el primer paso) y **S-09** («por vencer» 30 min antes). Este sistema solo define cómo se ven los estados, no cuándo se aplican.

### 7.1 Componente: chip de estado

- **Base [BB]:** chip con borde de 2 px blanco 14 %, Sora 600 de 13 px, sin relleno y radio 0.
- **Tres señales a la vez [EQUIPO]**, para que el estado nunca dependa solo del color:
  1. **Punto** circular de 8 px con el color del estado. El Brandboard permite formas curvas en los indicadores.
  2. **Icono** de línea de 20 px, en blanco, como pide el Brandboard: los iconos son blancos y el lima solo marca el estado activo.
  3. **Texto** del estado en blanco (20,02:1 sobre tinta).

| Estado | Punto | Contraste del punto sobre tinta | Icono | Franja en tarjeta | Orden (R37) | Origen del color |
|---|---|---|---|---|---|---|
| **Vencida** | `#FF6B6B` | 7,21:1 | Triángulo de alerta | Sí, `#FF6B6B` | 1 | [EQUIPO] |
| **Por vencer** | `#FFC857` | 13,01:1 | Reloj | Sí, `#FFC857` | 2 | [EQUIPO] |
| **En ejecución** | Lima `#5CF000` | 13,27:1 | Círculo de progreso | No | 3 | [BB]: «lima = ahora», chip «En curso» |
| **Sin asignar** | Blanco 64 %, borde del chip **punteado** | 8,20:1 | Usuario vacío | No | 4 | [BB] color atenuado · [EQUIPO] borde punteado |
| **Terminada** | Morado `#A46CFB` | 5,83:1 | Check | No | 5 | [EQUIPO], con un color de marca |

### 7.2 Adaptación de la regla «la lima es escasa» [EQUIPO]

**El conflicto:** el Brandboard limita el lima a «un solo dato clave por vista», pero en el tablero puede haber varias tareas en ejecución a la vez.

**Cómo lo resolvemos:**
- En los estados, el lima se usa **solo en el punto de 8 px** del chip «En ejecución». Nunca se usa en el texto, en el fondo ni en la franja.
- **Lima permitido en la plataforma:**
  - Punto de «en ejecución».
  - Punto de la pestaña activa [BB].
  - Contorno de foco.
  - Hover del botón primario [BB].
  - Aviso breve de acción completada [BB].
- **Lima prohibido:** fondos grandes [BB], texto largo y franjas de tarjeta.

Esta adaptación es una decisión del equipo y conviene validarla con el cliente cuando entregue la identidad oficial (A-12).

### 7.3 Comportamiento

- El estado se recalcula solo (M11). El chip y la franja cambian sin animación llamativa: una transición de color de 0,2 s [BB].
- Cuando una tarea cambia de grupo en el tablero, la tarjeta se mueve sin animación de desplazamiento, para no distraer ni marear (§11).
- **Leyenda:** en el tablero del administrador hay una leyenda de estados que se puede plegar, con punto, icono y texto de cada uno.

---

## 8. Checklist y confirmación de tareas

**Origen funcional [PRD]:**
- **Pantalla de detalle [DESC]:** muestra toda la información de la tarea, el formulario del checklist, las observaciones y el botón de guardar.
- **Pasos:** todos son obligatorios (R23, P-12).
- **Registro:** cada paso guarda quién lo marcó (R24, P-18).
- **Finalización:** el estudiante confirma la tarea y solo puede hacerlo con todos los pasos marcados (R25, P-25).
- **Observaciones:** el estudiante puede añadirlas (R27).

### 8.1 Estructura de la pantalla de detalle

1. **Encabezado:** chip de estado, hora de vencimiento (Big Shoulders de 24 px), título (H3), lugar y responsables.
2. **Descripción:** Sora 400 de 16 px.
3. **Avance:** barra de progreso [BB] y el texto «3 de 5 pasos».
4. **Checklist:** lista de pasos (§8.2).
5. **Observaciones:** área de texto (§5.2), opcional.
6. **Acciones:**
   - «Guardar avance» (secundario).
   - «Confirmar tarea» (primario). En celular queda fijo abajo; en escritorio, al final del formulario (§10).

### 8.2 Fila de paso [EQUIPO]

| Parte | Apariencia |
|---|---|
| Fila | Todo el ancho, 56 px de alto como mínimo. **Se puede tocar en cualquier parte.** Separador de 1 px blanco 9 % [BB]. |
| Casilla | Cuadrada de 24 × 24 px, radio 0 [BB]. Sin marcar: borde de 2 px blanco 38 % (3,44:1). Marcada: fondo morado y check tinta de 2,4 px de trazo (5,83:1). |
| Texto del paso | Sora 400 de 16 px, blanco. **No se tacha al marcarse**, para que siga leyéndose. |
| Quién lo marcó | Debajo del texto, en Sora de 14 px y blanco 64 %: «Marcado por Ana R.» [PRD R24]. La hora de cada paso solo se muestra si se confirma el supuesto **S-20** (punto abierto A-24). Mientras tanto, el diseño deja sitio para «· 14:12» sin depender de ello. |
| Foco | Contorno lima de 3 px alrededor de toda la fila |

**Comportamiento:**
- Al tocar la fila se marca o desmarca el paso, con un cambio inmediato y una transición de 0,2 s.
- La barra de avance y el contador se actualizan al momento.
- **Teclado:** Tab pasa de un paso a otro y Espacio marca o desmarca. Cada paso es una casilla de verificación nativa con su etiqueta, para que los lectores de pantalla lo anuncien bien.
- **Tareas con varios responsables:** según el supuesto **S-05**, el checklist es compartido. Cada paso muestra quién lo marcó, así que el diseño funciona tanto con un checklist compartido como con uno individual (A-19).

### 8.3 Botón «Confirmar tarea»

| Situación | Apariencia y comportamiento |
|---|---|
| Faltan pasos | Botón **deshabilitado** (§4.3), acompañado del texto «Faltan 2 pasos para confirmar» en blanco 64 %. Se marca con `aria-disabled="true"` en lugar de quitarlo del orden de tabulación, para que quien navega con teclado o con lector de pantalla pueda llegar a él y oír el motivo [EQUIPO]. Cumple R25. |
| Todos los pasos marcados | Botón **primario** activo (morado con texto tinta). Al pulsarlo se abre el diálogo de confirmación. |

### 8.4 Diálogo de confirmación [EQUIPO]

**Apariencia:**
- Panel tinta con borde de 2 px blanco 14 %, radio 0 y la sombra flotante del Brandboard, sobre un velo negro al 70 %.
- Título H3 en Big Shoulders: «¿CONFIRMAR TAREA?».
- Resumen en Sora 16: título de la tarea, «5 de 5 pasos marcados» y si se añadieron observaciones.

**Texto sobre lo que ocurre después de confirmar:**

| Parte del mensaje | Texto | Estatus |
|---|---|---|
| Archivo | «La tarea quedará archivada como constancia.» | **Respaldado** por P-03 y P-32 (R19) |
| Edición posterior | «Después de confirmarla no podrás editarla.» | **Pendiente.** Depende del **supuesto S-11** (P-26 sin respuesta). No es una decisión del cliente. Si S-11 no se confirma, esta frase se elimina o se cambia. |

**Acciones:**
- «Confirmar» (primario).
- «Volver» (secundario, recibe el foco al abrirse el diálogo).

**Comportamiento:**
- El diálogo atrapa el foco y se cierra con Esc o con «Volver».
- Al confirmar, aparece un **aviso breve** [BB `.toast`] abajo y centrado, con fondo lima y texto tinta (13,27:1): «Tarea confirmada». Desaparece a los 4 s y se anuncia a los lectores de pantalla con `role="status"`.

### 8.5 Variante pendiente: tarea vencida

La tarea vencida sigue visible (R30, P-35). Si se puede seguir completando y quién puede hacerlo depende de los supuestos **S-19** y **S-07** (puntos abiertos A-14 y A-20).

- **Mientras siga abierto:** el detalle muestra un aviso en texto: «Esta tarea venció a las 14:30». Lleva el icono de alerta y el color `#FF6B6B` en el icono y en el borde izquierdo.
- **El checklist se diseña habilitado** y podrá deshabilitarse si el cliente decide lo contrario.

---

## 9. Alertas de tareas próximas a vencer

**Origen funcional [PRD]:**
- Las tareas próximas a vencer se destacan con una alerta visual en la parte superior de la página de inicio del administrador (R38, P-33).
- La alerta es visual dentro de la plataforma, no por correo ni notificación (W8).
- El umbral de «por vencer» es el supuesto **S-09** (30 min, punto abierto A-05).

### 9.1 Componente: tarjeta señal [BB]

El Brandboard ya reserva la **tarjeta señal morada**, una por vista, para «la acción o el aviso más importante». En el tablero del administrador ese aviso son las tareas por vencer, así que se usa este componente sin inventar uno nuevo.

| Parte | Apariencia | Origen |
|---|---|---|
| Contenedor | Fondo morado `#A46CFB`, radio 0, sin sombra, espacio interno de 20 a 28 px, ancho completo del contenido | [BB] |
| Etiqueta | Sora 600 de 11 a 12 px, mayúsculas, +0,2 em, **tinta al 100 %**: «POR VENCER» | [BB]. El Brandboard la pone al 72 %; aquí va al 100 % porque al 72 % queda en ≈4,0:1 [EQUIPO]. |
| Dato principal | Big Shoulders 900 de 40 px (celular) o 56 px (escritorio), tinta: «2 TAREAS» | [BB] |
| Apoyo | Sora 600 de 14 px, tinta: «Vencen en menos de 30 minutos.» | [BB] |
| Lista | Hasta 3 tareas como enlaces en Sora 600 de 15 px, tinta y subrayadas: «14:30 · Preparar aula 205». Si hay más, enlace «Ver las 5». | [EQUIPO] |
| Icono | Reloj de 24 px, tinta, con trazo de 2,4 | [BB] estilo de icono |
| Foco | Contorno **tinta** de 3 px (5,83:1). El lima sobre morado se queda en 2,28:1. | [EQUIPO] |

### 9.2 Comportamiento [EQUIPO]

- **Ubicación:** arriba del tablero, debajo del encabezado de la página y antes de la cuadrícula.
- **Visibilidad:** solo aparece si hay al menos una tarea por vencer. Si no hay ninguna, no se muestra.
- **No se puede cerrar** mientras haya tareas por vencer, porque su función es que no se pierdan.
- **Actualización:** se actualiza a la vez que el tablero, con un retraso de 60 s como máximo (**supuesto S-10**, punto abierto A-23).
- **Lectores de pantalla:** se anuncia con `role="status"` y prioridad «polite». Solo se anuncia cuando cambia el número de tareas, para no interrumpir constantemente.
- **Animación:** puede entrar con el barrido del Brandboard (0,9 s), solo la primera vez que aparece y nunca si el usuario activó «reducir movimiento».

### 9.3 Relación con las tareas vencidas

- **Las vencidas no usan la tarjeta señal.** Ya son el primer grupo de la cuadrícula (R37, P-34, P-37) y se distinguen por su franja y su chip `#FF6B6B`. Así se respeta que haya una sola señal morada por vista [BB].
- Si hay vencidas, el encabezado del tablero muestra un contador en texto: «3 vencidas · 2 por vencer».

### 9.4 Variante para el estudiante [EQUIPO]

- **Sin tarjeta señal:** el estudiante no tiene tablero (R9). Sus tareas por vencer se distinguen con la franja ámbar y el chip «Por vencer», y aparecen primero en su lista.
- **Botón primario:** como el estudiante no tiene tarjeta señal, el morado de su pantalla puede usarse en el botón primario.

---

## 10. Diseño adaptable para computadora y celular

**Origen [PRD]:** el diseño debe pensarse sobre todo para el celular (P-39, M15) y toda funcionalidad del estudiante tiene que poder usarse con comodidad en un celular (R40). **El administrador y el estudiante usan la plataforma en celular y en computadora. El celular tiene prioridad, pero ninguna función queda excluida en la computadora** [EQUIPO, ajuste aprobado].

### 10.1 Puntos de corte [BB]

| Rango | Nombre | Retícula |
|---|---|---|
| Menos de 720 px | Celular | 4 columnas |
| 720 a 1.099 px | Tablet | 8 columnas |
| 1.100 px o más | Escritorio | 12 columnas, 1.200 px como máximo |

Se diseña **primero para celular** y luego se amplía.

### 10.2 Navegación

| Dispositivo | Patrón | Origen |
|---|---|---|
| Celular | **Barra inferior de pestañas** de 64 px de alto, fondo negro al 96 % y línea superior fina. Lleva icono de 20 px y etiqueta de 11 px; la pestaña activa va en blanco con un punto lima arriba. | [BB] app móvil · [EQUIPO] etiqueta de 11 px |
| Tablet y escritorio | **Barra superior** con el logo (96 px de ancho como mínimo, sobre negro [BB]), los enlaces de sección (Sora 600 de 13 px, blanco 64 %; la activa en blanco con punto lima) y el menú de cuenta a la derecha. | [BB] navegación de la web |

**Pestañas por perfil [PRD]:**
- **Administrador:** Tablero (M12), Tareas (M5), Usuarios (M3) y Cuenta (M4).
- **Estudiante:** Mis tareas (M7) y Cuenta (M4).

### 10.3 Pantallas principales por dispositivo

| Pantalla | Celular | Tablet | Escritorio |
|---|---|---|---|
| Tablero (administrador) | Alerta señal arriba; tarjetas en 1 columna, agrupadas por estado | Tarjetas en 2 columnas | Tarjetas en 3 o 4 columnas, 1.200 px como máximo |
| Mis tareas (estudiante) | Tarjetas en 1 columna, ordenadas como R37 | 2 columnas | 2 o 3 columnas |
| Detalle y checklist | 1 columna; **«Confirmar tarea» fijo abajo**, a todo el ancho, por encima de la barra de pestañas | 1 columna centrada de 720 px como máximo | 1 columna centrada de 720 px como máximo; **«Confirmar tarea» al final del formulario**, sin fijar |
| Formulario de tarea y usuario | 1 columna; botones a todo el ancho | 1 columna de 720 px como máximo | 1 columna de 720 px como máximo; botones alineados a la derecha |
| Gestión de usuarios | Lista de filas tocables | Lista | Tabla del Brandboard: encabezado morado con texto tinta en mayúsculas y filas con línea fina [BB] |

### 10.4 Reglas para celular [EQUIPO]

- **Alcance del pulgar:** la acción principal de cada pantalla queda en el tercio inferior.
- **Sin hover:** ninguna información depende de pasar el cursor por encima.
- **Desplazamiento:** no hay desplazamiento horizontal con un ancho de 320 px.
- **Teclado del celular:** se usa el teclado que corresponde a cada campo (correo, fecha y hora, texto).
- **Pérdida de conexión** (Could C2, supuesto S-12): un aviso fijo arriba, en Sora 600 de 14 px, blanco sobre tinta y con el icono correspondiente: «Sin conexión. Tus cambios se guardarán cuando vuelvas a conectarte.» El texto definitivo depende de A-08.

---

## 11. Accesibilidad

**Objetivo:** WCAG 2.2, nivel AA. La conformidad solo se declara en las combinaciones verificadas (§1.3). Todo componente nuevo debe verificarse antes de usarse.

### 11.1 Contraste

| Regla | Origen |
|---|---|
| El texto usa solo combinaciones de §1.3 con 4,5:1 o más. Las de 3:1 se limitan a texto de 24 px o más. | [BB] tabla de contraste · [EQUIPO] cálculo |
| No se usa blanco pequeño sobre morado (3,43:1). Sobre morado, el texto va en tinta (5,83:1). | [BB] |
| El morado profundo nunca se usa como texto (2,40:1). | [BB] |
| Los bordes de campos y casillas usan blanco 38 % (3,44:1). El 14 % del Brandboard (1,37:1) solo se usa en elementos no interactivos o identificados por su texto. | [EQUIPO] |
| Los colores de estado propuestos (`#FF6B6B` y `#FFC857`) superan 7:1 sobre negro y sobre tinta. | [EQUIPO], verificado |
| Los indicadores de hover y foco tienen 3:1 o más: morado sólido (5,98:1), lima (13,61:1) y tinta sobre morado (5,83:1). | [EQUIPO], verificado |

### 11.2 El color nunca es el único indicador [EQUIPO]

- Los estados de tarea llevan **punto, icono y texto** (§7).
- Los errores llevan **icono y mensaje de texto** (§5.4).
- El botón deshabilitado va con un **texto que explica el motivo** (§8.3).
- Los enlaces dentro de párrafos van subrayados [BB].

### 11.3 Navegación por teclado [EQUIPO]

- **Todo se puede usar con teclado:** tarjetas, checklist, formularios, diálogos y navegación.
- **Foco visible:** contorno lima de 3 px con 2 px de separación, o tinta dentro de la tarjeta señal. Se aplica con `:focus-visible` y nunca se elimina.
- **Orden de tabulación:** sigue el orden visual. En el tablero recorre la alerta señal, después los grupos en el orden de R37 y dentro de cada grupo las tarjetas.
- **Saltar al contenido:** es el primer elemento enfocable de cada página.
- **Diálogos:** atrapan el foco, se cierran con Esc y devuelven el foco al elemento que los abrió.
- **Checklist:** Tab y Mayús+Tab para moverse entre pasos y Espacio para marcar.
- **Estructura semántica:** encabezados en orden (H1 → H2 → H3), regiones de página (navegación, contenido principal) y etiquetas asociadas a cada campo.

### 11.4 Tamaños táctiles

| Regla | Valor | Origen |
|---|---|---|
| Área táctil mínima del Brandboard | 44 × 44 px | [BB] |
| Área táctil mínima en esta plataforma | **48 × 48 px** | [EQUIPO] |
| Separación mínima entre elementos tocables | 8 px (`space-2`) | [EQUIPO] |
| Fila de paso del checklist | 56 px de alto como mínimo, tocable en toda su superficie | [EQUIPO] |
| Barra inferior | 64 px de alto | [BB] |

### 11.5 Texto y zoom [EQUIPO]

- El texto de la interfaz es de 14 px como mínimo, salvo las ayudas y notas (13 px) y las etiquetas de la barra inferior (11 px, siempre acompañadas de icono).
- La interfaz admite **zoom del 200 %** sin perder contenido y se adapta a 320 px de ancho sin desplazamiento horizontal.
- Sora escala con el tamaño de texto del sistema; Big Shoulders crece como máximo 1,3 veces [BB].

### 11.6 Movimiento [BB]

- Las transiciones de interfaz duran 0,2 s.
- Las entradas escalonadas (0,8 s) y el barrido (0,9 s) se usan solo en el inicio de sesión y en la primera aparición de la alerta señal, **no en el tablero**.
- No hay animaciones con rebote ni movimiento continuo.
- Con la preferencia **«reducir movimiento»** activada, todo aparece sin animación.

### 11.7 Contenido no textual

- El logo lleva `alt="Interact2Hack"`.
- Los iconos que acompañan a un texto son decorativos (`aria-hidden="true"`). Los iconos que van solos, como «Quitar paso» o «Mostrar contraseña», tienen nombre accesible.
- Los avatares de responsables muestran iniciales y tienen el nombre completo como nombre accesible.

---

## Anexo A · Iconografía [BB]

- **Estilo:** iconos de línea en una retícula de 24 px, trazo de 2,4 px, uniones y puntas redondeadas, y el color se hereda del texto. **Nunca rellenos ni a dos colores.**
- **Tamaños:** 20 px en las barras de navegación, 24 px por defecto y 18 px dentro de botones.
- **Color:** blanco o blanco 64 % si está inactivo. El lima se reserva para el estado activo.
- **Iconos que necesita la plataforma [EQUIPO]:** tablero, tareas, usuarios, cuenta, lugar, responsable, reloj, alerta, check, progreso, usuario vacío, añadir, quitar, editar, eliminar, mostrar contraseña y sin conexión. Todos se dibujan con el estilo del Brandboard.

## Anexo B · Decisiones que dependen de supuestos o puntos abiertos del PRD

| Elemento del sistema | Depende de | Qué cambia si el cliente decide otra cosa |
|---|---|---|
| Texto del diálogo de confirmación sobre la edición posterior (§8.4) | S-11 | Se elimina o se cambia la frase. |
| Hora de cada paso en la fila del checklist (§8.2) | S-20, A-24 | Se muestra u oculta «· 14:12». |
| Checklist compartido entre varios responsables (§8.2) | S-05, A-19 | El diseño ya funciona en los dos casos. |
| Checklist de una tarea vencida (§8.5) | S-19, S-07, A-14, A-20 | Se deshabilita el checklist o se muestra un mensaje distinto. |
| Umbral del estado «por vencer» y de la alerta (§7, §9) | S-09, A-05 | Cambia el texto «menos de 30 minutos». |
| Momento en que una tarea pasa a «en ejecución» (§7) | S-08, A-16 | Ninguno visual. |
| Frecuencia de actualización de la alerta y el tablero (§9.2) | S-10, A-23 | Ninguno visual. |
| Responsables opcionales al crear una tarea (§5.2) | S-23, A-22 | El campo pasa a ser obligatorio. |
| Aviso de pérdida de conexión (§10.4) | S-12, A-08 | Cambia el texto del aviso. |
| Uso del Brandboard como identidad de la plataforma (todo) | A-12, A-10 | Se sustituyen los tokens de marca. Los semánticos y las reglas de accesibilidad se mantienen. |

## Anexo C · Partes del Brandboard que no se usan

Fotografía y su grado, fundidos, cita sobre foto, círculos de cifra, línea de fases, muro de auspiciantes, piezas para redes, retícula de slides, tarjeta de contacto (salvo como origen de la franja de estado) y video. Pertenecen a la comunicación del hackathon, no a la herramienta del staff (S-16).
