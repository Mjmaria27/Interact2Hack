# PRD · Plataforma de coordinación del staff de Interact2Hack

**Estado:** Borrador v0.2 (Avance 2, corregido según docs/prd/revision.md)
**Fecha:** 24 de noviembre de 2026
**Equipo:** María Paula Baca y Carlos Aluisa
**Fuentes únicas:**
- `docs/fuentes/descripcion-proyecto.md` — descripción del proyecto final (citada como **[DESC]**).
- `docs/cliente/preguntas.md` — preguntas del Avance 1 y respuestas del cliente del 11 de noviembre de 2026 (citadas como **P-xx**).

Todo lo que no proviene de estas fuentes está marcado como **[SUPUESTO]** y se detalla en la sección 8 con un identificador **S-xx**. Las preguntas que el cliente no respondió y que siguen sin una decisión aparecen en la misma sección como puntos abiertos **A-xx**.

---

## 1. Problema y contexto

Interact2Hack es un hackathon en el que el staff, formado por estudiantes, tiene que hacer muchas tareas operativas en distintos lugares y aulas, con horas límite definidas. Hoy no existe una herramienta común para repartir ese trabajo, explicar paso a paso lo que hay que hacer, confirmar que se hizo y ver de un vistazo qué está atrasado o a punto de vencer **[DESC]**.

Esta plataforma lo resuelve así:

- Los administradores crean tareas en forma de checklist, con fecha y hora de vencimiento, lugar, descripción y uno o varios responsables **[DESC]**, **P-10**.
- Los estudiantes ven sus tareas, completan cada paso del checklist y confirman la finalización **[DESC]**, **P-25**.
- Los administradores siguen el cumplimiento en un tablero que muestra primero lo vencido y lo que está por vencer **[DESC]**, **P-23**, **P-31**, **P-33**.

El uso será sobre todo en celular, durante el evento y en movimiento entre espacios **P-39**.

**Calendario académico [DESC]:** Avance 1 (preguntas), 11 de noviembre · Avance 2 (PRD, brandboard y sistema de diseño), 23 de noviembre · Avance 3 (avance funcional para el cliente), 2 de diciembre · Presentación final, 16 y 17 de diciembre.

---

## 2. Usuarios y perfiles

| Perfil | Quién es | Qué hace | Fuente |
|---|---|---|---|
| **Super admin** | Responsable general de la coordinación del staff. | Tiene todo lo que tiene un administrador, con más permisos y acceso. Qué permisos adicionales tiene exactamente está pendiente: ver S-01. | P-01 |
| **Administrador** | Coordinador de un área del evento (por ejemplo aulas o escenarios). Puede haber varios y, «en teoría», todos tienen los mismos privilegios (ver S-21). | Gestiona usuarios, crea, edita, elimina y asigna tareas, gestiona la disponibilidad del staff y supervisa el tablero de cumplimiento. | [DESC], P-01, P-02, P-04 |
| **Estudiante (staff)** | Miembro del staff que ejecuta tareas en el evento. | Ve las tareas que tiene asignadas y su estado, abre el detalle, marca los pasos del checklist, añade observaciones y confirma la finalización. Puede cambiar su contraseña. | [DESC], P-06, P-25 |

**Datos de la cuenta:** nombre y correo **P-05**. No hay registro público: las cuentas las crea un administrador **[DESC]**.

---

## 3. Objetivos y éxito

### Objetivos

| # | Objetivo | Fuente |
|---|---|---|
| O1 | Repartir el trabajo del staff con tareas claras, paso a paso, y con responsables definidos. | [DESC] |
| O2 | Dejar constancia confiable de qué se hizo, quién lo hizo y cuándo se terminó. | P-03, P-18, P-32 |
| O3 | Detectar a tiempo las tareas vencidas o próximas a vencer para que los administradores puedan actuar. | P-23, P-33, P-34, P-37 |
| O4 | Que los estudiantes puedan usar la herramienta con comodidad desde el celular durante el evento. | P-39 |

### Criterios de éxito

| # | Criterio | Objetivo | Fuente |
|---|---|---|---|
| C1 | Un administrador puede crear una tarea completa (fecha y hora, lugar, descripción, checklist y responsables) y asignarla a uno o varios estudiantes. | O1 | [DESC], P-10 |
| C2 | Un estudiante no puede confirmar una tarea mientras quede algún paso sin marcar. | O1, O2 | P-12, P-25 |
| C3 | En cada tarea terminada se ve quién marcó cada paso, y la tarea no se puede borrar. | O2 | P-03, P-18, P-32 |
| C4 | Al entrar, el administrador ve en su página de inicio una cuadrícula de tarjetas ordenada por estado, con las tareas próximas a vencer destacadas arriba. | O3 | P-23, P-31, P-33 |
| C5 | Una tarea que llega a su hora límite sin terminarse aparece sola como vencida y en primer lugar. | O3 | P-34, P-37 |
| C6 | Un estudiante completa una tarea desde un celular sin tener que hacer zoom ni desplazarse horizontalmente. | O4 | P-39 |
| C7 | La plataforma se usa durante el hackathon para coordinar al staff. Cómo se mide la adopción está pendiente: ver S-15. | O1 a O4 | [SUPUESTO] |

---

## 4. Alcance (MoSCoW)

La clasificación MoSCoW es una propuesta del equipo, porque el cliente no respondió qué es indispensable ni qué puede esperar (P-46, P-48; A-09). **[SUPUESTO]** S-22. Como subconjunto provisional para el Avance 3 (2 de diciembre) proponemos M1, M2, M5 a M9, M11 y M12; tampoco está confirmado por el cliente. **[SUPUESTO]** S-22.

### Must have (indispensable para la primera versión)

- **M1.** Inicio de sesión con usuario y contraseña, sin registro público **[DESC]**.
- **M2.** Tres perfiles: super admin, administrador y estudiante **P-01**, **[DESC]**.
- **M3.** Gestión de usuarios (ver, crear, editar y eliminar) por parte de los administradores **[DESC]**. Restricción provisional: solo el super admin gestiona las cuentas de administrador (ver R8). **[SUPUESTO]** S-01.
- **M4.** Cambio de contraseña por parte del propio usuario **P-06**.
- **M5.** Gestión de tareas (ver, crear, editar y eliminar) con fecha y hora de vencimiento, lugar o aula, descripción y checklist **[DESC]**, **P-10**.
- **M6.** Asignación de cada tarea a uno o varios estudiantes, sin responsable principal **[DESC]**, **P-22**.
- **M7.** Lista de tareas asignadas al estudiante, con su estado **[DESC]**.
- **M8.** Detalle de la tarea con toda su información, el formulario del checklist, un campo de observaciones y un botón de guardar **[DESC]**.
- **M9.** Confirmación de la finalización por parte del estudiante, posible solo si todos los pasos están marcados **P-12**, **P-25**.
- **M10.** Registro de quién marcó cada paso **P-18**, **P-32**.
- **M11.** Cinco estados (vencida, por vencer, en ejecución, sin asignar y terminada) que se calculan solos **P-23**, **P-34**. Los criterios de «en ejecución» y «por vencer» son **[SUPUESTO]** S-08 y S-09.
- **M12.** Tablero de cumplimiento en la página de inicio del administrador: cuadrícula de tarjetas en el orden definido y alerta visual arriba para lo próximo a vencer **P-23**, **P-31**, **P-33**.
- **M13.** Archivo de las tareas terminadas, que no se pueden borrar, y conservación del historial aunque se elimine al estudiante **P-03**, **P-32**.
- **M14.** Protecciones al editar: una tarea en ejecución no se puede borrar y dos administradores no pueden editar la misma tarea a la vez **P-13**. La forma de impedir la edición simultánea es **[SUPUESTO]** S-17.
- **M15.** Diseño pensado primero para celular **P-39**.
- **M16.** Uso de la identidad visual del hackathon que entregará el cliente **P-43**, **P-44**. Depende de recibir la carpeta de identidad visual (A-12).

### Should have (importante, pero no bloquea la primera versión)

- **S1.** Gestión del estado o la disponibilidad del staff por parte del administrador, para casos como una calamidad que impide asistir **P-02**, **P-04**.
- **S2.** Cambio de los responsables de una tarea ya asignada, para que otra persona pueda hacer una tarea vencida **P-35**. **[SUPUESTO]** S-07.
- **S3.** Actualización del tablero sin que el administrador tenga que recargar la página **P-31**. **[SUPUESTO]** S-10.
- **S4.** Consulta del historial de tareas terminadas con quién marcó cada paso y la hora de finalización **P-32**. La hora de cada paso es **[SUPUESTO]** S-20.

### Could have (deseable si hay tiempo)

- **C1.** Fotografías como evidencia al completar una tarea. El cliente dijo «se podría» **P-16**.
- **C2.** Aviso al estudiante cuando pierde la conexión mientras completa un checklist **P-41**. **[SUPUESTO]** S-12.
- **C3.** Filtros del tablero por estudiante responsable y por lugar o aula **P-29**, **P-30**. **[SUPUESTO]** S-13.
- **C4.** Archivos o imágenes de referencia dentro de la tarea **P-15**. **[SUPUESTO]** S-13.
- **C5.** Recuperación de la contraseña por cuenta propia **P-07**. **[SUPUESTO]** S-04.

### Won't have (fuera de esta versión)

- **W1.** Categorías o áreas temáticas de tareas: el cliente dijo que no son relevantes **P-17**.
- **W2.** Responsable principal o líder de tarea: el cliente dijo que por ahora no es necesario **P-22**.
- **W3.** Dependencias entre tareas o desbloqueo en secuencia **P-11**.
- **W4.** Aprobación de las tareas terminadas por parte de un administrador **P-27**.
- **W5.** Tareas recurrentes generadas automáticamente **P-14**. **[SUPUESTO]** S-14.
- **W6.** Estado «bloqueada» y solicitudes de reasignación hechas por el estudiante **P-21**, **P-28**. **[SUPUESTO]** S-14.
- **W7.** Reportes descargables y medición del tiempo de retraso **P-38**, **P-47**. **[SUPUESTO]** S-14: dejarlos fuera es una propuesta del equipo, no una decisión del cliente (A-21).
- **W8.** Notificaciones fuera de la plataforma (correo o push): el cliente pidió una alerta visual en la página **P-33**.
- **W9.** Trabajo completo sin conexión con sincronización posterior **P-41**. **[SUPUESTO]** S-12.

---

## 5. No-alcance

Esta versión no incluye:

- Registro abierto de usuarios ni invitaciones con enlace propio: las cuentas las crea un administrador **[DESC]**.
- La gestión del hackathon en sí (participantes, equipos, jurado, inscripciones o calificaciones). La herramienta es solo para el staff **[DESC]**. **[SUPUESTO]** S-16.
- La planificación de turnos o la asistencia del staff, más allá de marcar su estado o disponibilidad **P-02**, **P-04**.
- Mensajería o chat entre administradores y estudiantes. **[SUPUESTO]** S-16.
- Clasificar tareas por categoría o área del evento **P-17**.
- Flujos de aprobación o revisión de tareas terminadas **P-27**.
- Las funciones de la lista *Won't have* (sección 4).

---

## 6. Reglas de negocio

**Acceso y cuentas**

- **R1.** Solo se entra a la plataforma iniciando sesión. No hay registro público: las cuentas las crea un administrador.
- **R2.** Una cuenta tiene, como mínimo, nombre y correo.
- **R3.** Cada usuario puede cambiar su propia contraseña.
- **R4.** El administrador entrega las credenciales iniciales directamente al estudiante. **[SUPUESTO]**
- **R5.** Si un estudiante olvida su contraseña, un administrador se la restablece. **[SUPUESTO]**

**Perfiles y permisos**

- **R6.** Hay tres perfiles: super admin, administrador y estudiante.
- **R7.** Cada administrador se encarga de un área (por ejemplo aulas o escenarios) y, «en teoría», todos tienen los mismos privilegios. Que todos vean y gestionen todas las tareas, sin distinguir por área, es **[SUPUESTO]** (S-21).
- **R8.** El super admin puede hacer todo lo que hace un administrador y, además, es el único que puede crear, editar o eliminar cuentas de administrador. **[SUPUESTO]**
- **R9.** Un estudiante solo ve las tareas que tiene asignadas. Para que otro estudiante haga una tarea vencida, un administrador tiene que asignársela (ver R22 y R30); esto es **[SUPUESTO]** (S-07).

**Usuarios y disponibilidad**

- **R10.** Si se elimina a un estudiante, se conserva el historial de las tareas que completó.
- **R11.** El administrador puede cambiar el estado o la disponibilidad de un miembro del staff, por ejemplo si no puede asistir por una calamidad.
- **R12.** Si un estudiante deja de estar disponible, sus tareas pendientes siguen existiendo y el administrador decide si las reasigna. **[SUPUESTO]**

**Tareas**

- **R13.** Toda tarea tiene fecha y hora de vencimiento, lugar o aula, descripción y un checklist con al menos un paso.
- **R14.** El responsable forma parte de los datos de creación de una tarea, y una tarea sin responsables tiene el estado «sin asignar». Que se pueda guardar una tarea sin responsables para asignarla después es **[SUPUESTO]** (S-23).
- **R15.** Las tareas no dependen unas de otras: el estudiante puede hacerlas en el orden que quiera.
- **R16.** Las tareas no se clasifican por categoría ni por área.
- **R17.** Una tarea en ejecución no se puede borrar.
- **R18.** Dos administradores no pueden editar la misma tarea a la vez.
- **R19.** Una tarea terminada queda archivada y nadie puede borrarla.

**Asignación**

- **R20.** Una tarea se puede asignar a uno o varios estudiantes, y ninguno es responsable principal.
- **R21.** Si una tarea tiene varios responsables, todos trabajan sobre un mismo checklist compartido. **[SUPUESTO]**
- **R22.** El administrador puede cambiar los responsables de una tarea que todavía no esté terminada, también cuando ya venció. **[SUPUESTO]**

**Ejecución**

- **R23.** Todos los pasos del checklist son obligatorios.
- **R24.** Cada paso marcado guarda quién lo marcó, y la tarea guarda la hora en que se terminó. Que también se guarde la hora de cada paso es **[SUPUESTO]** (S-20).
- **R25.** Una tarea no se termina sola: el estudiante tiene que confirmarla, y solo puede hacerlo si todos los pasos están marcados.
- **R26.** En una tarea con varios responsables, basta con que uno de ellos confirme la finalización. **[SUPUESTO]**
- **R27.** Al completar una tarea, el estudiante puede escribir observaciones adicionales.
- **R28.** La confirmación del estudiante es suficiente: el administrador no tiene que aprobarla.
- **R29.** Una vez confirmada, la tarea ya no se puede editar, ni por el estudiante ni por el administrador. **[SUPUESTO]**
- **R30.** Una tarea vencida sigue visible. Que todavía se pueda completar después de su hora límite, por el responsable original o por otra persona a la que un administrador se la asigne, es **[SUPUESTO]** (S-19, S-07).

**Estados y vencimientos**

- **R31.** Una tarea siempre está en uno de estos cinco estados: vencida, por vencer, en ejecución, sin asignar o terminada.
- **R32.** Una tarea pasa a «en ejecución» cuando se marca el primero de sus pasos. **[SUPUESTO]**
- **R33.** Una tarea está «por vencer» cuando faltan 30 minutos o menos para su hora límite y no está terminada. **[SUPUESTO]**
- **R34.** Si llega la hora límite y la tarea no está terminada, pasa sola a «vencida».
- **R35.** Para calcular el estado de una tarea (no para ordenar el tablero, que sigue R37), si cumple las condiciones de varios estados se aplica esta precedencia: terminada, vencida, por vencer, en ejecución, sin asignar. **[SUPUESTO]**

**Tablero de cumplimiento**

- **R36.** El tablero de cumplimiento es la página de inicio del administrador y muestra una tarjeta por tarea.
- **R37.** El tablero se ordena así: vencidas, por vencer (de la más cercana a la más lejana), en ejecución, sin asignar y terminadas.
- **R38.** Las tareas próximas a vencer se destacan con una alerta visual en la parte superior de la página.
- **R39.** En cada tarea se ve quién es el responsable y, en el historial, quién marcó cada paso.

**Experiencia**

- **R40.** Toda funcionalidad del estudiante tiene que poder usarse con comodidad en un celular.
- **R41.** La interfaz usa la identidad visual oficial del hackathon que entregará el cliente.

---

## 7. Épicas

**E1 · Acceso y cuenta propia — Must**
Permite entrar a la plataforma con las credenciales que da un administrador, sin registro público, y cambiar la contraseña propia. Fija qué ve cada perfil al entrar: el administrador llega al tablero de cumplimiento y el estudiante a su lista de tareas. Cubre R1 a R5 y R9.

**E2 · Gestión de usuarios y perfiles — Must**
Los administradores ven, crean, editan y eliminan cuentas con nombre, correo y perfil. El super admin tiene permisos mayores que los administradores (P-01); cuáles son es **[SUPUESTO]** S-01. Al eliminar a un estudiante se conserva todo lo que completó. Cubre R6 a R8 y R10.

**E3 · Gestión de tareas — Must**
Los administradores ven, crean, editan y eliminan tareas con fecha y hora de vencimiento, lugar, descripción y checklist. La épica incluye las protecciones que pidió el cliente: no se borra una tarea en ejecución ni una terminada, y dos administradores no pueden editar la misma tarea a la vez. Cubre R13 a R19.

**E4 · Asignación de tareas — Must**
Permite asignar una tarea a uno o varios estudiantes, sin responsable principal, y dejarla sin asignar si todavía no hay quién la haga (**[SUPUESTO]** S-23). Que el administrador pueda cambiar los responsables de una tarea pendiente o vencida para que otra persona pueda hacerla es **[SUPUESTO]** S-07. Cubre R14 y R20 a R22.

**E5 · Ejecución de tareas por el estudiante — Must**
El estudiante ve sus tareas asignadas con su estado, abre el detalle completo, marca los pasos del checklist, escribe observaciones y confirma la finalización solo cuando todos los pasos están marcados. Cada paso guarda quién lo marcó; la hora de cada paso es **[SUPUESTO]** S-20. Está pensada para celular. Cubre R23 a R30 y R40.

**E6 · Tablero de cumplimiento y alertas — Must**
Es la página de inicio del administrador: una cuadrícula de tarjetas ordenada por estado, con lo vencido primero y una alerta visual arriba para lo próximo a vencer. Los estados se calculan solos según la hora límite y el avance del checklist. Cubre R31 a R39.

**E7 · Historial y archivo — Must**
Las tareas terminadas quedan archivadas y no se pueden borrar (P-03); que tampoco se puedan editar es **[SUPUESTO]** S-11. Se pueden consultar como constancia de quién hizo cada paso y a qué hora se terminó la tarea (P-32); la hora de cada paso es **[SUPUESTO]** S-20. Cubre R10, R19, R24, R29 y R39.

**E8 · Disponibilidad del staff — Should**
El administrador marca el estado o la disponibilidad de cada miembro del staff, por ejemplo si alguien no puede asistir por una calamidad, para decidir si reasigna sus tareas. Cubre R11 y R12.

**E9 · Identidad visual — Must**
La interfaz aplica el logotipo, los colores y las tipografías del hackathon que entregará el cliente, y se documenta en el brandboard y el sistema de diseño del Avance 2. Cubre R41.

**E10 · Evidencias y continuidad — Could**
Agrupa las mejoras opcionales: adjuntar fotografías como evidencia, adjuntar material de referencia en la tarea, avisar al estudiante cuando pierde la conexión y filtrar el tablero por responsable o por lugar. Se trabajará solo si las épicas Must están terminadas.

---

## 8. Supuestos y puntos abiertos

### Supuestos

Decisiones que tomamos para poder escribir el borrador. El cliente debe validarlas.

| ID | Supuesto | Pregunta relacionada |
|---|---|---|
| S-01 | **[SUPUESTO]** El permiso adicional del super admin es gestionar las cuentas de los administradores (crearlas, editarlas y eliminarlas). | P-01 |
| S-02 | **[SUPUESTO]** Si un estudiante deja de estar disponible, sus tareas pendientes no cambian solas y el administrador decide si las reasigna. | P-02, P-04 |
| S-03 | **[SUPUESTO]** El administrador entrega las credenciales iniciales directamente al estudiante; la plataforma no las envía por correo. | P-05 |
| S-04 | **[SUPUESTO]** La recuperación de la contraseña la hace un administrador restableciéndola. La recuperación por cuenta propia queda como Could. | P-07 |
| S-05 | **[SUPUESTO]** Varios responsables de una tarea comparten un mismo checklist, y por eso cada paso registra quién lo marcó. | P-18 |
| S-06 | **[SUPUESTO]** En una tarea con varios responsables basta con que uno confirme la finalización. | P-19 |
| S-07 | **[SUPUESTO]** El administrador puede cambiar los responsables de una tarea mientras no esté terminada, también cuando ya venció. | P-20, P-35 |
| S-08 | **[SUPUESTO]** Una tarea pasa a «en ejecución» cuando se marca su primer paso. | P-24 |
| S-09 | **[SUPUESTO]** Una tarea está «por vencer» cuando faltan 30 minutos o menos para su hora límite. | P-49 |
| S-10 | **[SUPUESTO]** El tablero refleja los cambios en un máximo de 60 segundos, sin que el administrador recargue la página. La cifra es una propuesta del equipo; de ella depende que R34 y R38 se vean a tiempo. | P-31 |
| S-11 | **[SUPUESTO]** Una tarea terminada no se puede reabrir ni editar. | P-26 |
| S-12 | **[SUPUESTO]** No habrá trabajo sin conexión; como mucho, se avisará al estudiante que perdió la conexión. | P-40, P-41 |
| S-13 | **[SUPUESTO]** Los filtros del tablero y los adjuntos de referencia en las tareas son deseables pero no indispensables (Could). | P-15, P-29, P-30 |
| S-14 | **[SUPUESTO]** Las tareas recurrentes, el estado «bloqueada», las solicitudes de reasignación, los reportes descargables y la medición del retraso quedan fuera de esta versión. | P-14, P-21, P-28, P-38, P-47, P-48 |
| S-15 | **[SUPUESTO]** El éxito se medirá por el uso real durante el hackathon. No hay métricas numéricas acordadas con el cliente. | P-46 |
| S-16 | **[SUPUESTO]** La plataforma es solo para el staff: no incluye la gestión de participantes del hackathon ni un chat interno. | — |
| S-17 | **[SUPUESTO]** Cuando dos administradores quieren editar la misma tarea, el segundo recibe un aviso y no puede guardar hasta que el primero termine. | P-13 |
| S-18 | **[SUPUESTO]** Las fechas y horas de la plataforma usan la hora local de Ecuador. | — |
| S-19 | **[SUPUESTO]** Una tarea vencida que no está terminada todavía se puede completar después de su hora límite, por el responsable original o por otra persona a la que un administrador se la asigne (S-07). | P-35 |
| S-20 | **[SUPUESTO]** Además de quién marcó cada paso, se guarda la hora en que se marcó. La hora de finalización de la tarea sí está respaldada por P-32. | P-18, P-32 |
| S-21 | **[SUPUESTO]** Todos los administradores ven y gestionan todas las tareas, sin distinguir por área. | P-01, P-17 |
| S-22 | **[SUPUESTO]** La clasificación MoSCoW de la sección 4 es una propuesta del equipo. El subconjunto para el Avance 3 (M1, M2, M5 a M9, M11 y M12) también es provisional. | P-46, P-48 |
| S-23 | **[SUPUESTO]** Una tarea se puede guardar sin responsables y asignarse después; mientras tanto queda «sin asignar». | [DESC], P-23 |

### Puntos abiertos

Preguntas que el cliente no respondió y que conviene cerrar antes del Avance 3 (2 de diciembre).

| ID | Punto abierto | Pregunta |
|---|---|---|
| A-01 | ¿Qué permisos concretos tiene el super admin que no tenga un administrador? ¿Quién crea la cuenta del super admin? ¿Un administrador puede eliminar a otro administrador? | P-01 |
| A-02 | ¿Puede el administrador cambiar los pasos de una tarea que un estudiante ya empezó? | P-13 |
| A-03 | ¿Cuánto debe durar la sesión antes de pedir de nuevo el inicio de sesión? | P-08 |
| A-04 | ¿La plataforma estará disponible solo durante el evento o también antes y después? | P-09 |
| A-05 | ¿Cuál es el intervalo exacto para considerar una tarea «por vencer»? | P-49 |
| A-06 | ¿Puede el administrador ampliar la hora límite de una tarea vencida y, si lo hace, la tarea deja de estar vencida? | P-36 |
| A-07 | ¿Cuántos estudiantes y administradores usarán la plataforma? | P-42 |
| A-08 | ¿Hay conexión estable a internet en todos los espacios del evento? | P-40 |
| A-09 | ¿Cuáles son las tres funcionalidades indispensables y cuáles pueden esperar a una segunda versión? | P-46, P-48 |
| A-10 | ¿La interfaz debe seguir la estética tecnológica del hackathon o ser más sobria? | P-45 |
| A-11 | ¿Se confirma el adjunto de fotografías como evidencia? El cliente dijo «se podría; depende de la base de datos». | P-16 |
| A-12 | Falta recibir la carpeta con la identidad visual del hackathon. | P-43, P-44 |
| A-13 | ¿En qué fechas se celebra el hackathon? Sin ellas no se puede saber cuánto margen hay entre la presentación final y el evento. | — |
| A-14 | ¿Quién puede completar una tarea vencida: el responsable original, otra persona asignada por un administrador o ambos? | P-35 |
| A-15 | Si una tarea cumple las condiciones de varios estados (por ejemplo, vencida con pasos marcados o sin responsables), ¿cómo debe verse? | P-23 |
| A-16 | ¿En qué momento pasa una tarea a «en ejecución»? | P-24 |
| A-17 | ¿Qué debe pasar cuando un segundo administrador intenta editar una tarea que otro administrador ya está editando? | P-13 |
| A-18 | ¿Cada administrador gestiona todas las tareas o solo las de su área? | P-01, P-17 |
| A-19 | Si una tarea tiene varios responsables, ¿comparten un mismo checklist? ¿Basta con que uno confirme la finalización? | P-18, P-19 |
| A-20 | ¿Un administrador puede cambiar los responsables de una tarea ya asignada? Cuando una tarea vence, ¿otro estudiante la toma por su cuenta o se la asigna un administrador? | P-20, P-35 |
| A-21 | ¿Necesitan medir el tiempo de retraso de las tareas o descargar reportes de cumplimiento? | P-38, P-47 |
| A-22 | ¿El responsable es obligatorio al crear una tarea, o se puede guardar sin responsable y asignarla después? | [DESC], P-23 |
| A-23 | ¿Cuánto retraso es aceptable entre que un estudiante termina una tarea y el administrador lo ve en el tablero? | P-31 |
| A-24 | ¿Es necesario registrar la hora exacta de cada paso del checklist o basta con registrar quién lo marcó y la hora de finalización de la tarea? | P-18, P-32; S-20 |

---

## 9. Trazabilidad

Relación de cada regla de negocio con la pregunta que la originó (P-xx), con la descripción del proyecto ([DESC]) o con el supuesto que la sostiene (S-xx).

| Regla | Resumen | Origen | Tipo |
|---|---|---|---|
| R1 | Acceso solo con inicio de sesión; cuentas creadas por un administrador | [DESC] | Fuente |
| R2 | La cuenta tiene nombre y correo | P-05 | Cliente |
| R3 | Cada usuario cambia su propia contraseña | P-06 | Cliente |
| R4 | El administrador entrega las credenciales | S-03 (P-05) | Supuesto |
| R5 | El administrador restablece la contraseña olvidada | S-04 (P-07) | Supuesto |
| R6 | Tres perfiles | P-01, [DESC] | Cliente |
| R7 | Administradores por área; «en teoría» mismos privilegios; acceso a todas las tareas supuesto | P-01; S-21 (P-01, P-17) | Cliente y supuesto |
| R8 | El super admin gestiona a los administradores | S-01 (P-01) | Supuesto |
| R9 | El estudiante solo ve sus tareas asignadas; acceso de otro estudiante a una tarea vencida por reasignación supuesto | [DESC]; S-07 (P-20, P-35) | Fuente y supuesto |
| R10 | Se conserva el historial del estudiante eliminado | P-03 | Cliente |
| R11 | El administrador gestiona la disponibilidad del staff | P-02, P-04 | Cliente |
| R12 | Las tareas de un estudiante no disponible se reasignan a criterio del administrador | S-02 (P-02) | Supuesto |
| R13 | Campos obligatorios de una tarea | [DESC], P-10 | Cliente |
| R14 | Responsable como dato de creación; estado «sin asignar»; guardar sin responsables supuesto | [DESC], P-23; S-23 | Cliente y supuesto |
| R15 | Sin dependencias entre tareas | P-11 | Cliente |
| R16 | Sin categorías de tareas | P-17 | Cliente |
| R17 | Una tarea en ejecución no se puede borrar | P-13 | Cliente |
| R18 | Dos administradores no editan la misma tarea a la vez | P-13 (forma de aplicarlo: S-17) | Cliente |
| R19 | Una tarea terminada se archiva y no se puede borrar | P-03, P-32 | Cliente |
| R20 | Uno o varios responsables, sin responsable principal | [DESC], P-22 | Cliente |
| R21 | Checklist compartido entre los responsables | S-05 (P-18) | Supuesto |
| R22 | El administrador cambia los responsables de una tarea no terminada | S-07 (P-20, P-35) | Supuesto |
| R23 | Todos los pasos son obligatorios | P-12 | Cliente |
| R24 | Quién marcó cada paso y hora de finalización de la tarea; hora de cada paso supuesta | P-18, P-32; S-20; A-24 | Cliente y supuesto |
| R25 | El estudiante confirma la finalización y solo con todos los pasos marcados | P-25, P-12 | Cliente |
| R26 | Basta con que confirme un responsable | S-06 (P-19) | Supuesto |
| R27 | Observaciones adicionales al completar | [DESC] | Fuente |
| R28 | No hay aprobación del administrador | P-27 | Cliente |
| R29 | Una tarea terminada no se puede editar | S-11 (P-26) | Supuesto |
| R30 | Una tarea vencida sigue visible; completarla después del vencimiento supuesto | P-35; S-19, S-07 | Cliente y supuesto |
| R31 | Cinco estados de tarea | P-23 | Cliente |
| R32 | Pasa a «en ejecución» al marcar el primer paso | S-08 (P-24) | Supuesto |
| R33 | «Por vencer» con 30 minutos o menos | S-09 (P-49) | Supuesto |
| R34 | Pasa sola a «vencida» al llegar la hora límite | P-34 | Cliente |
| R35 | Precedencia para calcular el estado (no el orden del tablero, que es R37) | S-08, S-09 (P-23); A-15 | Supuesto |
| R36 | El tablero es la página de inicio del administrador, con tarjetas | P-31 | Cliente |
| R37 | Orden del tablero | P-23, P-34, P-37 | Cliente |
| R38 | Alerta visual arriba para lo próximo a vencer | P-33, P-49 | Cliente |
| R39 | Se ve el responsable de cada tarea y de cada paso | P-18, P-29, P-32 | Cliente |
| R40 | Diseño pensado primero para celular | P-39 | Cliente |
| R41 | Identidad visual oficial del hackathon | P-43, P-44 | Cliente |
