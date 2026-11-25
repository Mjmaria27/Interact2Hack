# PRD · Plataforma de coordinación del staff de Interact2Hack

**Estado:** Borrador v0.3 (Avance 2). Actualizado con la consolidación de respuestas y supuestos de `docs/cliente/preguntas.md` y con las decisiones del equipo sobre la revisión del PRD v0.2.
**Fecha:** 25 de noviembre de 2026
**Equipo:** María Paula Baca y Carlos Aluisa
**Fuentes únicas:**
- `docs/fuentes/descripcion-proyecto.md`: descripción del proyecto final. Se cita como **[DESC]**.
- `docs/cliente/preguntas.md`, que contiene:
  - las preguntas del Avance 1 y las respuestas del cliente del 11 de noviembre de 2026, citadas como **P-xx**;
  - la sección «Consolidación de respuestas y supuestos», con los temas adicionales **T-x**;
  - las aclaraciones posteriores a la reunión, citadas como **AC-xx**.

**Supuestos y puntos abiertos.** Todo lo que no proviene de estas fuentes está marcado como **[SUPUESTO]** y se detalla en la sección 8 con un identificador **S-xx**. Una restricción que solo se deduce del reparto de funciones de [DESC], sin que ninguna fuente la diga de forma explícita, también se registra como supuesto. Las preguntas que el cliente no respondió aparecen en la sección 8 como puntos abiertos **A-xx**. Un supuesto es una decisión provisional del equipo: **no es una aprobación del cliente**.

**Identificadores que no deben confundirse:**

| Identificador | Qué es |
|---|---|
| **S-01** a **S-35** (con guion) | Supuestos |
| **S1** a **S4** (sin guion) | Requisitos Should |
| **CE1** a **CE8** | Criterios de éxito |
| **C1** a **C5** | Requisitos Could |

---

## 1. Problema y contexto

Interact2Hack es un hackathon en el que el staff, formado por estudiantes, tiene que hacer muchas tareas operativas en distintos lugares y aulas, con horas límite definidas. Hoy no existe una herramienta común para repartir ese trabajo, explicar paso a paso lo que hay que hacer, confirmar que se hizo y ver de un vistazo qué está atrasado o a punto de vencer **[DESC]**.

Esta plataforma lo resuelve así:

- Los administradores crean tareas en forma de checklist, con fecha y hora de vencimiento, lugar, descripción y uno o varios responsables **[DESC]**, **P-10**.
- Los estudiantes ven sus tareas, completan cada paso del checklist y confirman la finalización **[DESC]**, **P-25**.
- Los administradores siguen el cumplimiento en un tablero que muestra primero lo vencido y lo que está por vencer **[DESC]**, **P-23**, **P-31**, **P-33**.

**La confirmación es manual (P-25).** [DESC] dice que «una vez que todos los checks han sido confirmados, se confirma la ejecución de la tarea». P-25, que es más específica y posterior, aclara que esa confirmación la hace el estudiante, y que solo puede hacerla si todos los pasos están marcados.

El uso será sobre todo en celular, durante el evento y en movimiento entre espacios **P-39**. La interfaz sigue la identidad visual «Señal Neón» del hackathon, cuyo brand board proporcionó el cliente a través del profesor **AC-01**.

**Calendario académico [DESC]:**

| Entrega | Contenido | Fecha |
|---|---|---|
| Avance 1 | Preguntas | 11 de noviembre |
| Avance 2 | PRD, brandboard y sistema de diseño | 23 de noviembre |
| Avance 3 | Avance funcional para el cliente | 2 de diciembre |
| Presentación final | — | 16 y 17 de diciembre |

---

## 2. Usuarios y perfiles

| Perfil | Quién es | Qué hace | Fuente |
|---|---|---|---|
| **Super admin** | Responsable general de la coordinación del staff. | Tiene permisos mayores y más acceso que un administrador (P-01). Que herede todos los permisos del administrador, y cuáles son sus permisos adicionales, es **[SUPUESTO]** S-01, pendiente de A-01. | P-01; S-01 |
| **Administrador** | Coordinador de un área del evento (por ejemplo aulas o escenarios). Puede haber varios y, «en teoría», todos tienen los mismos privilegios (ver S-21). | Gestiona usuarios; crea, edita, elimina y asigna tareas; gestiona la disponibilidad del staff y supervisa el tablero de cumplimiento. | [DESC], P-01, P-02, P-04 |
| **Estudiante (staff)** | Miembro del staff que ejecuta tareas en el evento. | Ve las tareas que tiene asignadas y su estado; abre el detalle; marca los pasos del checklist y desmarca los suyos antes de confirmar (S-29); añade observaciones y confirma la finalización. Puede cambiar su contraseña. | [DESC], P-06, P-25 |

**Datos de la cuenta:** nombre y correo **P-05**. No hay registro público: las cuentas las crea un administrador **[DESC]**.

### Qué no puede hacer cada perfil

Valores de la columna **Tipo**:

| Tipo | Significado |
|---|---|
| **Confirmada** | Hay respaldo explícito del cliente. |
| **Confirmada en parte** | El cliente dijo una parte, y la forma de aplicarla es un supuesto. |
| **Supuesto** | Derivada del reparto de funciones de [DESC] o decidida por el equipo. Pendiente de validación. |

| Perfil | Restricción | Tipo | Fuente | Regla |
|---|---|---|---|---|
| Estudiante | No puede confirmar una tarea mientras quede algún paso sin marcar. | Confirmada | P-12, P-25 | R25 |
| Estudiante | No puede borrar una tarea terminada. | Confirmada | P-03 | R19 |
| Estudiante | No ve las tareas que no tiene asignadas. | Supuesto (derivada de [DESC]) | S-33 | R9 |
| Estudiante | No crea, edita, elimina ni asigna tareas, ni gestiona usuarios. | Supuesto (derivada de [DESC]) | S-33 | R9 |
| Estudiante | No desmarca los pasos que marcó otra persona. | Supuesto | S-29 | R46 |
| Estudiante | No modifica una tarea después de confirmarla. | Supuesto | S-11 | R29 |
| Estudiante | No modifica una tarea de la que ya no es responsable, aunque antes haya marcado pasos en ella. Los pasos que marcó conservan su autoría. | Supuesto (derivada de S-07, S-29 y S-33) | S-07, S-29, S-33 | R43, R46 |
| Administrador | No puede borrar una tarea terminada. | Confirmada | P-03 | R19 |
| Administrador | No puede editar una tarea que otro administrador está editando. | Confirmada. El mecanismo es S-17. | P-13 | R18 |
| Administrador | No puede borrar una tarea con responsables asignados ni una tarea con actividad de ejecución registrada. | Confirmada en parte | P-13 («una tarea en ejecución no se puede borrar»); S-28 | R17 |
| Administrador | No marca pasos ni confirma tareas en nombre de un estudiante. | Supuesto | S-27 | R47 |
| Administrador | No crea, edita ni elimina cuentas de administrador. | Supuesto | S-01 | R8 |
| Super admin | Tiene las mismas restricciones que el administrador sobre las tareas: no borra tareas terminadas, con responsables o con actividad registrada, y no marca pasos ni confirma tareas. | Como en las filas del administrador | P-03, P-13; S-27, S-28 | R17, R19, R47 |
| Super admin | No puede eliminar la última cuenta de super admin. | Supuesto | S-26 | R44 |

---

## 3. Objetivos y éxito

### Objetivos

| # | Objetivo | Fuente |
|---|---|---|
| O1 | Repartir el trabajo del staff con tareas claras, paso a paso, y con responsables definidos. | [DESC] |
| O2 | Dejar constancia confiable de qué se hizo, quién lo hizo y cuándo se terminó. | P-03, P-18, P-32 |
| O3 | Detectar a tiempo las tareas vencidas o próximas a vencer para que los administradores puedan actuar. | P-23, P-33, P-34, P-37 |
| O4 | Que los estudiantes puedan usar la herramienta con comodidad desde el celular durante el evento. | P-39 |
| O5 | Que la plataforma se use durante el hackathon real para coordinar al staff. Se evalúa fuera de la entrega académica, porque depende de la fecha del evento (A-13), y no hay métricas acordadas con el cliente. | [SUPUESTO] S-15 |

### Criterios de éxito

Los criterios CE1 a CE8 son criterios de verificación del equipo para la entrega académica. No son requisitos aprobados por el cliente. Cada uno se puede comprobar en una demostración.

| # | Criterio | Objetivo | Fuente |
|---|---|---|---|
| CE1 | Un administrador puede crear una tarea completa (fecha y hora, lugar, descripción, checklist y responsables) y asignarla a uno o varios estudiantes. | O1 | [DESC], P-10 |
| CE2 | Un estudiante no puede confirmar una tarea mientras quede algún paso sin marcar. | O1, O2 | P-12, P-25 |
| CE3 | En cada tarea terminada se ve quién marcó cada paso y la hora en que se terminó, y la tarea no se puede borrar. | O2 | P-03, P-18, P-32 |
| CE4 | Al entrar, el administrador ve en su página de inicio una cuadrícula de tarjetas ordenada por estado, con las tareas próximas a vencer destacadas arriba. | O3 | P-23, P-31, P-33 |
| CE5 | Tiene dos partes, que se verifican por separado:<br>• **Parte indispensable (M11, M12):** al consultar o actualizar el tablero, una tarea que llegó a su hora límite sin terminarse aparece como vencida y en primer lugar, y cada tarea muestra el estado que le corresponde según R35.<br>• **Parte de S3 (Should):** el tablero refleja los cambios sin que el administrador recargue la página, en un máximo provisional de 60 segundos. Solo se exige si S3 se implementa; no convierte S3 en Must. | O3 | P-34, P-37; [SUPUESTO] S-10 (parte de S3), A-23 |
| CE6 | Un estudiante completa una tarea desde un celular sin hacer zoom ni desplazarse horizontalmente.<br>• **Ancho de prueba:** se prueba al menos con 360 px. Es una referencia de prueba, no un límite de compatibilidad.<br>• **Objetivo mínimo de diseño:** 320 px sin desplazamiento horizontal.<br>• **Verificación de ambos tamaños:** se documentará en DESIGN.md. | O4 | P-39 |
| CE7 | En la demostración del avance funcional (Avance 3) y en la presentación final, con un administrador y al menos dos estudiantes, se completa el ciclo crear → asignar → ejecutar → confirmar → consultar en el tablero.<br>• Los estudiantes ejecutan y confirman sus tareas desde el celular.<br>• El administrador puede usar celular o computadora; usar el celular no es una exigencia del cliente para su perfil.<br>• En el Avance 3 se pueden usar cuentas creadas previamente, porque M3 (gestión de usuarios) no forma parte del subconjunto provisional (S-22). | O1 a O4 | Equipo (criterio académico) |
| CE8 | Un estudiante no ve tareas que no tiene asignadas. Además, la plataforma impide eliminar:<br>• una tarea con responsables, en cualquier estado;<br>• una tarea terminada;<br>• una tarea con actividad de ejecución registrada, es decir, con algún paso marcado que se guardó correctamente, aunque después sus pasos hayan vuelto a cero o se hayan retirado sus responsables.<br>En cambio, permite eliminar una tarea sin responsables, sin actividad registrada y no terminada, también si está vencida o por vencer. | O1, O2 | P-03, P-13; [SUPUESTO] S-28, S-33 |

---

## 4. Alcance (MoSCoW)

La clasificación MoSCoW es una propuesta del equipo, porque el cliente no respondió qué es indispensable ni qué puede esperar (P-46, P-48; A-09). **[SUPUESTO]** S-22.

**Subconjunto provisional para el Avance 3 (2 de diciembre):** M1, M2, M5 a M12 y M15.

- En v0.3 se añadieron M10 y M15:
  - **M10**, porque P-18 pide de forma expresa ver quién marcó cada paso.
  - **M15**, porque el diseño para celular es la forma de construir la interfaz desde el inicio.
- Es una propuesta del equipo. No está confirmada por el cliente ni es un requisito académico confirmado por el profesor. **[SUPUESTO]** S-22.

Los identificadores S1 a S4 (Should) y C1 a C5 (Could) son distintos de los supuestos S-xx y de los criterios de éxito CE1 a CE8.

### Must have (indispensable para la primera versión)

- **M1.** Inicio de sesión con usuario y contraseña, sin registro público **[DESC]**.
- **M2.** Tres perfiles: super admin, administrador y estudiante **P-01**, **[DESC]**.
- **M3.** Gestión de usuarios (ver, crear, editar y eliminar) por parte de los administradores **[DESC]**. Restricciones provisionales **[SUPUESTO]**:
  - solo el super admin gestiona las cuentas de administrador (R8, S-01);
  - no se puede eliminar al último super admin (R44, S-26);
  - al eliminar a un estudiante se aplica R45 (S-32).
- **M4.** Cambio de contraseña por parte del propio usuario **P-06**.
- **M5.** Gestión de tareas (ver, crear, editar y eliminar) con fecha y hora de vencimiento, lugar o aula, descripción y checklist **[DESC]**, **P-10**. La eliminación tiene las restricciones de M14.
- **M6.** Asignación de cada tarea a uno o varios estudiantes, sin responsable principal **[DESC]**, **P-22**.
- **M7.** Lista de tareas asignadas al estudiante, con su estado **[DESC]**.
- **M8.** Detalle de la tarea con toda su información, el formulario del checklist, un campo de observaciones y un botón de guardar **[DESC]**.
  - La diferencia entre guardar y confirmar sigue R42 (**[SUPUESTO]** S-30).
  - Si una operación falla, se aplica R43 (**[SUPUESTO]** S-31).
- **M9.** Confirmación de la finalización por parte del estudiante, posible solo si todos los pasos están marcados **P-12**, **P-25**.
- **M10.** Registro de quién marcó cada paso **P-18**, **P-32**. Cada estudiante solo desmarca sus propios pasos, y la autoría se conserva aunque su autor sea reasignado o eliminado. **[SUPUESTO]** S-29 (R46).
- **M11.** Cinco estados (vencida, por vencer, en ejecución, sin asignar y terminada) que se calculan solos **P-23**, **P-34**. Los criterios de «en ejecución» y de «por vencer», y la precedencia entre estados, son **[SUPUESTO]** S-08, S-09 y S-25.
- **M12.** Tablero de cumplimiento en la página de inicio del administrador: cuadrícula de tarjetas en el orden definido y alerta visual arriba para lo próximo a vencer **P-23**, **P-31**, **P-33**.
- **M13.** Archivo de las tareas terminadas, que no se pueden borrar, y conservación del historial aunque se elimine al estudiante **P-03**, **P-32**.
- **M14.** Protecciones al editar y eliminar:
  - dos administradores no pueden editar la misma tarea a la vez **P-13**; la forma de impedirlo es **[SUPUESTO]** S-17;
  - una tarea terminada no se puede borrar **P-03**;
  - una tarea en ejecución no se puede borrar **P-13**. El equipo lo aplica así: no se puede borrar una tarea con responsables ni una tarea con actividad de ejecución registrada. **[SUPUESTO]** S-28 (R17).
- **M15.** Diseño pensado primero para celular **P-39**.
- **M16.** Uso de la identidad visual del hackathon, «Señal Neón», según el brand board `docs/diseno/Interact2Hack-Brandboard.html`. El cliente lo proporcionó a través del profesor como guía para diseñar la herramienta **AC-01**, **P-43**, **P-44**. AC-01 no aprueba las decisiones de interfaz del equipo. Siguen pendientes:
  - las adaptaciones que agregan elementos a la marca o cambian sus reglas (A-10);
  - los archivos independientes del logotipo (A-12).

### Should have (importante, pero no bloquea la primera versión)

- **S1.** Gestión del estado o la disponibilidad del staff por parte del administrador, para casos como una calamidad que impide asistir **P-02**, **P-04**.
- **S2.** Cambio de los responsables de una tarea ya asignada, para que otra persona pueda hacer una tarea vencida **P-35**. **[SUPUESTO]** S-07. Retirar responsables no quita la protección de una tarea con actividad registrada (R17).
- **S3.** Actualización del tablero sin que el administrador tenga que recargar la página **P-31**. **[SUPUESTO]** S-10.
- **S4.** Consulta del historial de tareas terminadas con quién marcó cada paso y la hora de finalización **P-32**. La hora de cada paso es **[SUPUESTO]** S-20.

### Could have (deseable si hay tiempo)

- **C1.** Fotografías como evidencia al completar una tarea. El cliente dijo «se podría» **P-16**.
- **C2.** Aviso continuo al estudiante cuando pierde la conexión mientras completa un checklist **P-41**. **[SUPUESTO]** S-12. No incluye trabajo sin conexión ni sincronización posterior (W9).
- **C3.** Filtros del tablero por estudiante responsable y por lugar o aula **P-29**, **P-30**. **[SUPUESTO]** S-13.
- **C4.** Archivos o imágenes de referencia dentro de la tarea **P-15**. **[SUPUESTO]** S-13.
- **C5.** Recuperación de la contraseña por cuenta propia **P-07**. **[SUPUESTO]** S-04.

### Won't have (fuera de esta versión)

- **W1.** Categorías o áreas temáticas de tareas: el cliente dijo que no son relevantes **P-17**.
- **W2.** Responsable principal o líder de tarea: el cliente dijo que por ahora no es necesario **P-22**.
- **W3.** Dependencias entre tareas o desbloqueo en secuencia **P-11**.
- **W4.** Aprobación de las tareas terminadas por parte de un administrador **P-27**. **[SUPUESTO]** S-24: el cliente no mencionó una aprobación adicional, lo que no equivale a descartarla (A-19).
- **W5.** Tareas recurrentes generadas automáticamente **P-14**. **[SUPUESTO]** S-14.
- **W6.** Estado «bloqueada» y solicitudes de reasignación hechas por el estudiante **P-21**, **P-28**. **[SUPUESTO]** S-14.
- **W7.** Reportes descargables y medición del tiempo de retraso **P-38**, **P-47**. **[SUPUESTO]** S-14: dejarlos fuera es una propuesta del equipo, no una decisión del cliente (A-21).
- **W8.** Notificaciones fuera de la plataforma (correo o push): el cliente pidió una alerta visual en la página **P-33**.
- **W9.** Trabajo completo sin conexión con sincronización posterior **P-41**. **[SUPUESTO]** S-12. Qué pasa cuando falla un guardado está en R43.

---

## 5. No-alcance

Esta versión no incluye:

- Registro abierto de usuarios ni invitaciones con enlace propio: las cuentas las crea un administrador **[DESC]**.
- La gestión del hackathon en sí (participantes, equipos, jurado, inscripciones o calificaciones). La herramienta es solo para el staff **[DESC]** (S-16a).
- La planificación de turnos o la asistencia del staff, más allá de marcar su estado o disponibilidad **P-02**, **P-04**.
- Mensajería o chat entre administradores y estudiantes. **[SUPUESTO]** S-16b.
- Clasificar tareas por categoría o área del evento **P-17**.
- Flujos de aprobación o revisión de tareas terminadas **P-27**. **[SUPUESTO]** S-24.
- Trabajo sin conexión con sincronización posterior. **[SUPUESTO]** S-12.
- Medir el tiempo de retraso de las tareas. Solo se pueden consultar la hora límite y la hora de finalización (R24). **[SUPUESTO]** S-14.
- Las funciones de la lista *Won't have* (sección 4).

---

## 6. Reglas de negocio

Las reglas R42 a R47 se añadieron en v0.3 y se ubican en el grupo temático que les corresponde. R28 se dividió en R28a y R28b.

**Acceso y cuentas**

- **R1.** Solo se entra a la plataforma iniciando sesión. No hay registro público: las cuentas las crea un administrador.
- **R2.** Una cuenta tiene nombre y correo.
- **R3.** Cada usuario puede cambiar su propia contraseña.
- **R4.** El administrador entrega las credenciales iniciales directamente al estudiante. **[SUPUESTO]** S-03.
- **R5.** Si un estudiante olvida su contraseña, un administrador se la restablece. **[SUPUESTO]** S-04.

**Perfiles y permisos**

- **R6.** Hay tres perfiles: super admin, administrador y estudiante.
- **R7.** Cada administrador se encarga de un área (por ejemplo aulas o escenarios) y, «en teoría», todos tienen los mismos privilegios. Que todos vean y gestionen todas las tareas, sin distinguir por área, es **[SUPUESTO]** (S-21).
- **R8.** El super admin puede hacer todo lo que hace un administrador y, además, es el único que puede crear, editar o eliminar cuentas de administrador. **[SUPUESTO]** S-01.
- **R9.** Un estudiante ve la lista de las tareas que tiene asignadas y su estado **[DESC]**. Que no pueda ver las tareas de otros ni gestionar tareas o usuarios es una restricción derivada de [DESC], no una respuesta del cliente: **[SUPUESTO]** S-33. Para que otro estudiante haga una tarea vencida, un administrador tiene que asignársela (ver R22 y R30): **[SUPUESTO]** S-07.
- **R44.** Siempre existe al menos una cuenta de super admin, y no se puede eliminar la última. **[SUPUESTO]** S-26.
- **R47.** Ni los administradores ni el super admin marcan pasos ni confirman tareas en nombre de un estudiante. [DESC] asigna la ejecución y la confirmación a los estudiantes, pero no prohíbe esto de forma explícita. **[SUPUESTO]** S-27.

**Usuarios y disponibilidad**

- **R10.** Si se elimina a un estudiante, se conserva el historial de las tareas que completó.
- **R11.** El administrador puede cambiar el estado o la disponibilidad de un miembro del staff, por ejemplo si no puede asistir por una calamidad.
- **R12.** Si un estudiante deja de estar disponible, sus tareas pendientes siguen existiendo y el administrador decide si las reasigna. **[SUPUESTO]** S-02.
- **R45.** Si se elimina a un estudiante, sus tareas no terminadas siguen existiendo y quedan disponibles para reasignar. **[SUPUESTO]** S-32.
  - Se conservan los demás responsables. Si no queda ninguno, la tarea se queda sin responsables. Su estado se recalcula según R35 (puede ser «sin asignar», «por vencer» o «vencida») y su tarjeta indica «Sin responsables» (R39).
  - Los pasos que marcó ese estudiante conservan su autoría.
  - Si la tarea tuvo actividad, sigue protegida contra eliminación (R17).

**Tareas**

- **R13.** Datos de una tarea.
  - Toda tarea tiene fecha y hora de vencimiento y descripción (P-10), y un checklist ([DESC]).
  - El lugar o aula forma parte de los datos de la tarea según [DESC]. Que sea obligatorio es **[SUPUESTO]** S-35.
  - Que el checklist tenga al menos un paso es **[SUPUESTO]** S-34.
- **R14.** El responsable forma parte de los datos de creación de una tarea, y existe el estado «sin asignar».
  - Que se pueda guardar una tarea sin responsables para asignarla después es **[SUPUESTO]** (S-23).
  - No tener responsables no determina por sí solo el estado: este se calcula según R35. Una tarea sin responsables está «sin asignar» si no está terminada, vencida ni por vencer. Si está vencida o por vencer, conserva ese estado, y su tarjeta indica «Sin responsables» (R39).
- **R15.** Las tareas no dependen unas de otras: el estudiante puede hacerlas en el orden que quiera.
- **R16.** Las tareas no se clasifican por categoría ni por área.
- **R17.** Una tarea no se puede eliminar en ninguno de estos casos:
  - tiene responsables asignados;
  - tiene actividad de ejecución registrada;
  - está terminada (R19).

  **Actividad registrada:** existe desde que se guarda correctamente, por primera vez, un paso marcado (R42). Un cambio que nunca se llegó a guardar no cuenta como actividad. Una vez registrada, la actividad no desaparece aunque después se desmarquen los pasos, se retiren los responsables o se reasigne la tarea.

  **Qué se puede eliminar:** solo una tarea sin responsables, que nunca tuvo actividad registrada y que no está terminada, sea cual sea su estado («sin asignar», «por vencer» o «vencida»). Para eliminar una tarea asignada que nadie empezó, el administrador primero retira sus responsables.

  **Origen:** el cliente pidió que «una tarea en ejecución no se puede borrar» (P-13). Esta forma de aplicarlo es **[SUPUESTO]** S-28. Es coherente con R32, porque toda tarea «en ejecución» tiene responsables.
- **R18.** Dos administradores no pueden editar la misma tarea a la vez.
- **R19.** Una tarea terminada queda archivada y nadie puede borrarla, en ningún caso.

**Asignación**

- **R20.** Una tarea se puede asignar a uno o varios estudiantes, y ninguno es responsable principal.
- **R21.** Si una tarea tiene varios responsables, todos trabajan sobre un mismo checklist compartido. **[SUPUESTO]** S-05.
- **R22.** El administrador puede cambiar los responsables de una tarea que todavía no esté terminada, también cuando ya venció. Retirar o cambiar responsables no quita la protección de R17, y el estado de la tarea se recalcula según R35. **[SUPUESTO]** S-07.

**Ejecución**

- **R23.** Todos los pasos del checklist son obligatorios.
- **R24.** Cada paso marcado guarda quién lo marcó, y la tarea guarda la hora en que se terminó.
  - Con la hora de finalización y la hora límite (R13) se puede consultar si una tarea terminó después de vencer.
  - No se calcula ni se mide el retraso (W7).
  - Que también se guarde la hora de cada paso es **[SUPUESTO]** (S-20).
- **R25.** Una tarea no se termina sola: el estudiante tiene que confirmarla, y solo puede hacerlo si todos los pasos están marcados. Si hay varios responsables, ver R26.
- **R26.** En una tarea con varios responsables, basta con que uno de ellos confirme la finalización. **[SUPUESTO]** S-06.
- **R27.** Al completar una tarea, el estudiante puede escribir observaciones adicionales.
- **R28a.** La confirmación del estudiante es la que da la tarea por terminada.
- **R28b.** El administrador no aprueba las tareas terminadas. **[SUPUESTO]** S-24: el cliente no mencionó una aprobación adicional (P-27), lo que no equivale a descartarla.
- **R29.** Una vez confirmada, la tarea ya no se puede editar, ni por el estudiante ni por el administrador. **[SUPUESTO]** S-11.
- **R30.** Una tarea vencida sigue visible. Que todavía se pueda completar después de su hora límite, por el responsable original o por otra persona a la que un administrador se la asigne, es **[SUPUESTO]** (S-19, S-07).
- **R42.** Guardar y confirmar son acciones distintas.
  - **De las fuentes:** el detalle de la tarea tiene un botón de guardar y un campo de observaciones **[DESC]**. La confirmación la hace el estudiante, y solo con todos los pasos marcados (P-25, P-12).
  - **Del equipo, [SUPUESTO] S-30:**
    - «Guardar» registra los pasos marcados o desmarcados y las observaciones, sin terminar la tarea.
    - «Confirmar» guarda el progreso final y termina la tarea.
    - Cuando un responsable guarda, no se pierden los cambios que otro responsable hizo en pasos diferentes.
- **R43.** Si guardar o confirmar falla, el usuario ve un mensaje de error y puede reintentar. **[SUPUESTO]** S-31.
  - Una operación nunca se muestra como completada si no se completó.
  - Los cambios sin guardar se conservan mientras el usuario siga en la misma pantalla. No se garantiza que se conserven si cierra o recarga la aplicación.
  - No hay trabajo sin conexión ni sincronización posterior (W9).
  - Solo los responsables actuales de una tarea no terminada pueden guardar o confirmar cambios en ella. Si un estudiante intenta guardar o confirmar después de dejar de ser responsable, o después de que la tarea se confirmó, la operación falla y no se muestra como completada. Los pasos que marcó y guardó antes conservan su autoría (R46). Esto se deriva de R9, R22, R29 y R46 (S-33, S-07, S-11 y S-29); no es una regla independiente.
- **R46.** Mientras sea responsable de la tarea, cada estudiante solo puede desmarcar los pasos que marcó él mismo, y solo antes de que se confirme la tarea. **[SUPUESTO]** S-29.
  - Los pasos marcados y su autoría se conservan aunque su autor sea reasignado o eliminado.
  - Quién puede corregir un paso marcado por error cuando su autor ya no está disponible es un punto abierto (A-19).

**Estados y vencimientos**

- **R31.** Una tarea siempre está en uno de estos cinco estados: vencida, por vencer, en ejecución, sin asignar o terminada.
- **R32.** Una tarea con responsables que no está terminada, vencida ni por vencer está «en ejecución», aunque todavía no tenga pasos marcados. **[SUPUESTO]** S-08.
- **R33.** Una tarea no terminada está «por vencer» desde 30 minutos antes de su hora límite, incluido ese instante, hasta justo antes de la hora límite. El umbral es único para todas las tareas. **[SUPUESTO]** S-09.
- **R34.** Si llega la hora límite y la tarea no está terminada, pasa sola a «vencida». Desde el instante exacto de la hora límite la tarea está vencida, no por vencer (S-09).
- **R35.** Para calcular el estado de una tarea se aplica esta precedencia (no se usa para ordenar el tablero, que sigue R37):
  1. terminada;
  2. si no, vencida;
  3. si no, por vencer;
  4. si no y tiene responsables, en ejecución;
  5. si no, sin asignar.

  Así, cada tarea está siempre en un solo estado de los cinco. Agregar, retirar o eliminar responsables no fija el estado: se recalcula siempre con esta precedencia. Por ejemplo, una tarea vencida o por vencer sin responsables sigue «vencida» o «por vencer», y su tarjeta indica «Sin responsables» (R39). **[SUPUESTO]** S-25.

**Tablero de cumplimiento**

- **R36.** El tablero de cumplimiento es la página de inicio del administrador y muestra una tarjeta por tarea.
- **R37.** El tablero se ordena por estado: vencidas, por vencer, en ejecución, sin asignar y terminadas. Dentro del grupo «por vencer», las tareas se ordenan por fecha de vencimiento (P-23). Que vayan de la hora límite más cercana a la más lejana es una interpretación del equipo: **[SUPUESTO]** S-25.
- **R38.** Las tareas próximas a vencer se destacan con una alerta visual en la parte superior de la página.
- **R39.** En cada tarea se ve quién es el responsable y, en el historial, quién marcó cada paso. Si una tarea no tiene responsables, su tarjeta lo indica en cualquier estado, también cuando está vencida o por vencer. **[SUPUESTO]** S-25.

**Experiencia**

- **R40.** Toda funcionalidad del estudiante tiene que poder usarse con comodidad en un celular.
- **R41.** La interfaz sigue la identidad visual «Señal Neón» del brand board que el cliente proporcionó a través del profesor como guía (AC-01). Esto no aprueba las decisiones de interfaz del equipo: las adaptaciones que agregan elementos a la marca o cambian sus reglas están pendientes de validación (A-10).

---

## 7. Épicas

**E1 · Acceso y cuenta propia — Must**
Permite entrar a la plataforma con las credenciales que da un administrador, sin registro público, y cambiar la contraseña propia. Fija qué ve cada perfil al entrar: el administrador llega al tablero de cumplimiento y el estudiante a su lista de tareas asignadas. Que el estudiante no vea las tareas de otros es **[SUPUESTO]** S-33. Cubre R1 a R5 y R9.

**E2 · Gestión de usuarios y perfiles — Must**
Los administradores ven, crean, editan y eliminan cuentas con nombre, correo y perfil.
- El super admin tiene permisos mayores que los administradores (P-01); cuáles son es **[SUPUESTO]** S-01.
- Siempre existe al menos un super admin (**[SUPUESTO]** S-26).
- Ningún administrador marca pasos ni confirma tareas (**[SUPUESTO]** S-27).
- Al eliminar a un estudiante se conserva todo lo que completó (P-03), y sus tareas no terminadas quedan para reasignar (**[SUPUESTO]** S-32).

Cubre R2, R6 a R8, R10, R44, R45 y R47.

**E3 · Gestión de tareas — Must**
Los administradores ven, crean, editan y eliminan tareas con fecha y hora de vencimiento, lugar, descripción y checklist. La épica incluye las protecciones:
- no se borra una tarea terminada (P-03);
- no se borra una tarea con responsables ni una con actividad registrada (P-13, interpretado en **[SUPUESTO]** S-28);
- dos administradores no pueden editar la misma tarea a la vez (P-13).

Cubre R13 a R19.

**E4 · Asignación de tareas — Must**
Permite asignar una tarea a uno o varios estudiantes, sin responsable principal, y dejarla sin responsables si todavía no hay quién la haga (**[SUPUESTO]** S-23). Una tarea sin responsables está «sin asignar», «por vencer» o «vencida», según R35.
- Que el administrador pueda cambiar los responsables de una tarea pendiente o vencida para que otra persona pueda hacerla es **[SUPUESTO]** S-07.
- Las tareas no terminadas de un estudiante eliminado quedan disponibles para reasignar (**[SUPUESTO]** S-32).

Cubre R14, R20 a R22 y R45.

**E5 · Ejecución de tareas por el estudiante — Must**
El estudiante:
- ve sus tareas asignadas con su estado y abre el detalle completo;
- marca los pasos del checklist y solo desmarca los suyos (**[SUPUESTO]** S-29);
- escribe observaciones y guarda su avance;
- confirma la finalización solo cuando todos los pasos están marcados (R42).

Cada paso guarda quién lo marcó; la hora de cada paso es **[SUPUESTO]** S-20. Si guardar o confirmar falla, se muestra un error y se puede reintentar (**[SUPUESTO]** S-31). Está pensada para celular.

Cubre R23 a R30 (incluidas R28a y R28b), R40, R42, R43, R46 y R47.

**E6 · Tablero de cumplimiento y alertas — Must**
Es la página de inicio del administrador: una cuadrícula de tarjetas ordenada por estado, con lo vencido primero y una alerta visual arriba para lo próximo a vencer. Los estados se calculan solos según la hora límite, los responsables y la confirmación; los criterios son **[SUPUESTO]** S-08, S-09 y S-25. Una tarea sin responsables lo indica en su tarjeta en cualquier estado. Cubre R31 a R39.

**E7 · Historial y archivo — Must**
Las tareas terminadas quedan archivadas y no se pueden borrar (P-03); que tampoco se puedan editar es **[SUPUESTO]** S-11.
- Se pueden consultar como constancia de quién hizo cada paso y a qué hora se terminó la tarea (P-32), junto con su hora límite.
- La hora de cada paso es **[SUPUESTO]** S-20.

Cubre R10, R19, R24, R29 y R39.

**E8 · Disponibilidad del staff — Should**
El administrador marca el estado o la disponibilidad de cada miembro del staff, por ejemplo si alguien no puede asistir por una calamidad, para decidir si reasigna sus tareas. Cubre R11 y R12.

**E9 · Identidad visual — Must**
La interfaz aplica el logotipo, los colores y las tipografías del brand board «Señal Neón», que el cliente proporcionó a través del profesor como guía (AC-01). Se documenta en el sistema de diseño del Avance 2.

Esta épica distingue:
- **Lo confirmado:** seguir el brand board (AC-01, P-43, P-44).
- **Lo pendiente de validación con el cliente:** las adaptaciones que agregan elementos a la marca o cambian sus reglas (A-10).
- **Lo que decide el equipo de diseño:** el resto de las decisiones de interfaz, que no se consultan una por una.
- **Lo pendiente sobre el logotipo:** los archivos independientes en SVG o PNG (A-12).

AC-01 **no** aprueba las decisiones de interfaz del equipo. Cubre R41.

**E10 · Evidencias y continuidad — Could**
Agrupa las mejoras opcionales:
- adjuntar fotografías como evidencia;
- adjuntar material de referencia en la tarea;
- avisar de forma continua al estudiante cuando pierde la conexión;
- filtrar el tablero por responsable o por lugar.

Se trabajará solo si las épicas Must están terminadas.

---

## 8. Supuestos y puntos abiertos

### Supuestos

Son decisiones provisionales del equipo. El cliente debe validarlas y **ninguna equivale a una aprobación del cliente**.

**Excepción: S-16a.** Conserva su identificador histórico solo por trazabilidad. Ya está confirmado por [DESC], así que no es un supuesto ni una decisión pendiente.

La columna «Estado» resume la clasificación de `docs/cliente/preguntas.md` (sección «Consolidación de respuestas y supuestos»), donde están las justificaciones completas. S-08 y S-09 se modificaron en v0.3; S-16 se dividió en S-16a y S-16b; S-24 a S-35 son nuevos.

| ID | Supuesto | Pregunta relacionada | Estado |
|---|---|---|---|
| S-01 | **[SUPUESTO]** El super admin hereda todos los permisos del administrador. Su permiso adicional es gestionar las cuentas de los administradores (crearlas, editarlas y eliminarlas). P-01 solo dice que tiene «permisos mayores y más acceso», sin confirmar de forma expresa que herede todos los permisos del administrador. | P-01 | Pendiente. P-01 solo confirma que existe un super admin con permisos mayores. |
| S-02 | **[SUPUESTO]** Si un estudiante deja de estar disponible, sus tareas pendientes no cambian solas y el administrador decide si las reasigna. | P-02, P-04 | Pendiente |
| S-03 | **[SUPUESTO]** El administrador entrega las credenciales iniciales directamente al estudiante; la plataforma no las envía por correo. | P-05 | Pendiente |
| S-04 | **[SUPUESTO]** La recuperación de la contraseña la hace un administrador restableciéndola. La recuperación por cuenta propia queda como Could. | P-07 | Pendiente |
| S-05 | **[SUPUESTO]** Varios responsables de una tarea comparten un mismo checklist, y por eso cada paso registra quién lo marcó. | P-18 | Pendiente. P-18 solo confirma que se ve quién marcó cada paso. |
| S-06 | **[SUPUESTO]** En una tarea con varios responsables basta con que uno confirme la finalización. | P-19 | Pendiente |
| S-07 | **[SUPUESTO]** El administrador puede cambiar los responsables de una tarea mientras no esté terminada, también cuando ya venció. | P-20, P-35 | Pendiente. P-35 solo dice que otra persona «podría realizarla». |
| S-08 | **[SUPUESTO]** Una tarea con responsables que no está terminada, vencida ni por vencer está «en ejecución», aunque no tenga pasos marcados.<br>En v0.2 decía: «pasa a "en ejecución" cuando se marca su primer paso». Se cambió porque con esa definición una tarea asignada y sin pasos marcados no tenía ninguno de los cinco estados. | P-24, P-23 | Pendiente (modificado en v0.3) |
| S-09 | **[SUPUESTO]** Una tarea está «por vencer» desde 30 minutos antes de su hora límite, incluido ese instante, hasta justo antes de la hora límite. Desde la hora límite exacta está «vencida». El umbral es único para todas las tareas. | P-49, P-34 | Pendiente (precisado en v0.3) |
| S-10 | **[SUPUESTO]** El tablero refleja los cambios en un máximo de 60 segundos, sin que el administrador recargue la página. La cifra es una propuesta del equipo y corresponde a S3 (Should). De ella depende solo la parte de S3 de CE5; el cálculo de los estados (R34, R35) y la alerta (R38) no dependen de ella. | P-31 | Pendiente |
| S-11 | **[SUPUESTO]** Una tarea terminada no se puede reabrir ni editar. | P-26 | Pendiente. P-03 solo confirma que no se puede borrar. |
| S-12 | **[SUPUESTO]** No habrá trabajo sin conexión; como mucho, se avisará al estudiante de que perdió la conexión. Qué pasa si falla un guardado se define en S-31. | P-40, P-41 | Pendiente |
| S-13 | **[SUPUESTO]** Los filtros del tablero y los adjuntos de referencia en las tareas son deseables, pero no indispensables (Could). | P-15, P-29, P-30 | Pendiente |
| S-14 | **[SUPUESTO]** Las tareas recurrentes, el estado «bloqueada», las solicitudes de reasignación, los reportes descargables y la medición del retraso quedan fuera de esta versión. | P-14, P-21, P-28, P-38, P-47, P-48 | Pendiente |
| S-15 | **[SUPUESTO]** La adopción real durante el hackathon (O5) no tiene métricas acordadas con el cliente. Los criterios CE1 a CE8 son de verificación académica. | P-46 | Pendiente |
| S-16a | La plataforma es solo para el staff: no incluye la gestión de participantes del hackathon. | — ([DESC]) | Confirmado por [DESC]. Era supuesto en v0.2; se conserva el identificador por trazabilidad. |
| S-16b | **[SUPUESTO]** La plataforma no incluye un chat interno. | — | Pendiente |
| S-17 | **[SUPUESTO]** Cuando dos administradores quieren editar la misma tarea, el segundo recibe un aviso y no puede guardar hasta que el primero termine. | P-13 | Pendiente. P-13 confirma la restricción, no el mecanismo. |
| S-18 | **[SUPUESTO]** Las fechas y horas de la plataforma usan la hora local de Ecuador. | — | Pendiente |
| S-19 | **[SUPUESTO]** Una tarea vencida que no está terminada todavía se puede completar después de su hora límite, por el responsable original o por otra persona a la que un administrador se la asigne (S-07). | P-35 | Pendiente. P-35 solo confirma que sigue visible. |
| S-20 | **[SUPUESTO]** Además de quién marcó cada paso, se guarda la hora en que se marcó. La hora de finalización de la tarea sí está respaldada por P-32. | P-18, P-32 | Pendiente |
| S-21 | **[SUPUESTO]** Todos los administradores ven y gestionan todas las tareas, sin distinguir por área. | P-01, P-17 | Pendiente. P-01 solo confirma que cada administrador se encarga de un área. |
| S-22 | **[SUPUESTO]** La clasificación MoSCoW de la sección 4 es una propuesta del equipo. El subconjunto para el Avance 3 (M1, M2, M5 a M12 y M15) también es provisional. | P-46, P-48 | Pendiente |
| S-23 | **[SUPUESTO]** Una tarea se puede guardar sin responsables y asignarse después. Mientras no tenga responsables, su estado se calcula según R35: «sin asignar», o bien «por vencer» o «vencida» si corresponde. Su tarjeta indica «Sin responsables». | [DESC], P-23 | Pendiente |
| S-24 | **[SUPUESTO]** El administrador no aprueba las tareas terminadas: basta con la confirmación del estudiante. | P-27 | Pendiente (nuevo en v0.3) |
| S-25 | **[SUPUESTO]** Para calcular el estado se usa esta precedencia: terminada, vencida, por vencer, en ejecución y sin asignar. Si una tarea no tiene responsables, su tarjeta lo indica en cualquier estado. Dentro del grupo «por vencer» del tablero, las tareas van de la hora límite más cercana a la más lejana; P-23 solo dice «por fecha de vencimiento». | P-23, P-34 | Pendiente (nuevo en v0.3) |
| S-26 | **[SUPUESTO]** Siempre existe al menos una cuenta de super admin, y no se puede eliminar la última. | P-01 | Pendiente (nuevo en v0.3) |
| S-27 | **[SUPUESTO]** Ni los administradores ni el super admin marcan pasos ni confirman tareas en nombre de un estudiante. Se deduce de [DESC], que asigna la ejecución y la confirmación a los estudiantes, pero no lo prohíbe de forma explícita. | [DESC], P-25 | Pendiente (nuevo en v0.3) |
| S-28 | **[SUPUESTO]** La petición «una tarea en ejecución no se puede borrar» (P-13) se aplica así:<br>• No se puede eliminar una tarea con responsables asignados ni una con actividad de ejecución registrada, aunque después se desmarquen los pasos, se retiren los responsables o se reasigne la tarea.<br>• La actividad registrada empieza cuando se guarda correctamente, por primera vez, un paso marcado. Un cambio que nunca se guardó no cuenta.<br>• Solo se puede eliminar una tarea sin responsables, sin actividad registrada y no terminada, sea cual sea su estado. | P-13, P-03 | Pendiente (nuevo en v0.3) |
| S-29 | **[SUPUESTO]** Cada estudiante solo desmarca los pasos que marcó él mismo, y solo antes de la confirmación. Los pasos marcados y su autoría se conservan aunque su autor sea reasignado o eliminado. | P-18 | Pendiente (nuevo en v0.3) |
| S-30 | **[SUPUESTO]** «Guardar» registra los pasos y las observaciones sin terminar la tarea. «Confirmar» guarda el progreso final y la termina. Cuando un responsable guarda, no se pierden los cambios que otro responsable hizo en pasos diferentes. | [DESC], P-25 | Pendiente (nuevo en v0.3; se valida en A-19) |
| S-31 | **[SUPUESTO]** Si guardar o confirmar falla, se ve un error y se puede reintentar. Nada se muestra como completado si no lo está, tampoco cuando un estudiante intenta guardar o confirmar después de dejar de ser responsable o después de que la tarea se confirmó. Los cambios sin guardar se conservan solo mientras el usuario siga en la pantalla. | P-40, P-41 | Pendiente (nuevo en v0.3) |
| S-32 | **[SUPUESTO]** Al eliminar a un estudiante, sus tareas no terminadas quedan para reasignar.<br>• Se conservan los demás responsables y la autoría de los pasos que marcó.<br>• Si no queda ningún responsable, su estado se recalcula según R35 y su tarjeta indica «Sin responsables». | P-02, P-03 | Pendiente (nuevo en v0.3) |
| S-33 | **[SUPUESTO]** El estudiante solo ve las tareas que tiene asignadas, y no gestiona tareas ni usuarios. [DESC] describe la lista de tareas asignadas del estudiante y reparte la gestión entre los administradores, pero no prohíbe de forma explícita que el estudiante vea otras tareas. Ninguna respuesta del cliente lo trata. | — ([DESC]) | Pendiente (nuevo en v0.3) |
| S-34 | **[SUPUESTO]** El checklist de una tarea tiene al menos un paso. [DESC] y P-10 describen la tarea y su checklist, pero el cliente no validó un número mínimo de pasos. | [DESC], P-10 | Pendiente (nuevo en v0.3) |
| S-35 | **[SUPUESTO]** El lugar o aula es obligatorio al crear una tarea, por el contexto de coordinación logística del hackathon. [DESC] lo incluye entre los datos de la tarea, pero no dice que sea obligatorio, y el cliente no lo validó. | [DESC], P-10 | Pendiente (nuevo en v0.3) |

### Puntos abiertos

Preguntas que el cliente no respondió y que conviene cerrar antes del Avance 3 (2 de diciembre).

**Cómo está organizada esta lista:**

- Se conservan los identificadores A-01 a A-24 con su texto original. Cuando un punto se reformuló, se cita su texto anterior.
- Los grupos son solo etiquetas: no fusionan ni eliminan preguntas.
- **Ningún punto se cierra** porque el equipo haya adoptado una solución provisional.
- Los temas T-1 a T-10 de la consolidación de `preguntas.md` se añaden como preguntas explícitas:

| Temas | Punto abierto donde se añaden |
|---|---|
| T-1 y T-2 | A-20 |
| T-3 y T-4 | A-03 |
| T-5 y T-6 | A-19 |
| T-7 y T-10 | A-09 |
| T-8 | A-09 y A-11 |
| T-9 | A-13 |

**Valores de la columna «Categoría»:**

| Categoría | Significado |
|---|---|
| **Cliente** | Necesita la decisión del cliente. |
| **Provisional** | El equipo ya adoptó un supuesto, pero el punto sigue pendiente de validación. |
| **Posterior** | Pertenece a una etapa posterior o a una función opcional. |

| ID | Punto abierto | Pregunta | Grupo | Categoría | Prioridad |
|---|---|---|---|---|---|
| A-01 | ¿Qué permisos concretos tiene el super admin que no tenga un administrador? ¿Quién crea la cuenta del super admin? ¿Un administrador puede eliminar a otro administrador?<br>**Añadido en v0.3:** ¿El super admin tiene todos los permisos del administrador (S-01)? ¿Puede un administrador o el super admin marcar pasos o confirmar tareas en nombre de un estudiante (S-27)? ¿Se acepta que siempre exista al menos un super admin y que no se pueda eliminar el último (S-26)? | P-01 | Perfiles y permisos | Cliente | Alta |
| A-02 | ¿Puede el administrador cambiar los pasos de una tarea que un estudiante ya empezó?<br>**Añadido en v0.3:** ¿Se aplica «una tarea en ejecución no se puede borrar» como propone S-28, es decir, sin poder borrar tareas con responsables ni tareas con actividad registrada? | P-13 | Edición y eliminación de tareas | Cliente | Media |
| A-03 | ¿Cuánto debe durar la sesión antes de pedir de nuevo el inicio de sesión?<br>**(T-3)** ¿Cómo reciben los estudiantes sus credenciales iniciales (S-03)?<br>**(T-4)** ¿Cómo se recupera una contraseña olvidada durante el evento (S-04)? | P-08, P-05, P-07 | Acceso | Cliente (sesión). Provisional (S-03, S-04) | Baja |
| A-04 | ¿La plataforma estará disponible solo durante el evento o también antes y después? | P-09 | Contexto operativo | Posterior | Baja |
| A-05 | ¿Cuál es el intervalo exacto para considerar una tarea «por vencer»? | P-49 | Modelo de estados | Cliente | Alta |
| A-06 | ¿Puede el administrador ampliar la hora límite de una tarea vencida y, si lo hace, la tarea deja de estar vencida?<br>**Añadido en v0.3:** como los estados se calculan solos (R35), una tarea cuya hora límite se amplía se recalcula sola, pero falta confirmar que el administrador pueda ampliarla. Tampoco está definido si se puede crear una tarea con una hora límite ya pasada. | P-36 | Edición y eliminación de tareas | Cliente | Media |
| A-07 | ¿Cuántos estudiantes y administradores usarán la plataforma? | P-42 | Contexto operativo | Posterior | Baja |
| A-08 | ¿Hay conexión estable a internet en todos los espacios del evento?<br>**Añadido en v0.3:** mientras tanto, R43 (S-31) define qué pasa si falla un guardado. | P-40, P-41 | Tiempo real y conexión | Cliente | Media |
| A-09 | ¿Cuáles son las tres funcionalidades indispensables y cuáles pueden esperar a una segunda versión?<br>**(T-7)** ¿Se necesitan tareas recurrentes, el estado «bloqueada» o solicitudes de reasignación (S-14)?<br>**(T-8)** ¿Se necesitan filtros del tablero por responsable o por lugar (S-13)?<br>**(T-10)** ¿Se descarta la mensajería interna (S-16b)? | P-46, P-48, P-14, P-21, P-28, P-29, P-30 | Alcance | Cliente | Alta |
| A-10 | **Reformulado en v0.3 (AC-01):** ¿Son aceptables las adaptaciones de interfaz que agregan elementos a la marca o cambian sus reglas? Son los colores de estado fuera de la paleta, el morado para «terminada» y el uso del lima y de la señal morada en el tablero.<br>Hay una posible tensión entre el lima de las tareas «en ejecución», que con S-08 serán más, y la regla de uso limitado del lima del brand board. La solución visual se definirá en las exploraciones de diseño. Las decisiones que corresponden al equipo de diseño no se consultan una por una.<br>*Texto original:* «¿La interfaz debe seguir la estética tecnológica del hackathon o ser más sobria?» | P-45 | Identidad visual | Cliente | Baja |
| A-11 | ¿Se confirma el adjunto de fotografías como evidencia? El cliente dijo «se podría; depende de la base de datos».<br>**(T-8)** ¿Se necesitan archivos o imágenes de referencia dentro de la tarea (S-13)? | P-16, P-15 | Adjuntos | Posterior | Baja |
| A-12 | **Reformulado en v0.3 (AC-01):** ¿Hay archivos independientes del logotipo (SVG o PNG)? El brand board oficial ya está disponible en HTML y permite avanzar con el diseño.<br>*Texto original:* «Falta recibir la carpeta con la identidad visual del hackathon.» | P-43, P-44 | Identidad visual | Cliente (no bloquea) | Media |
| A-13 | ¿En qué fechas se celebra el hackathon? Sin ellas no se puede saber cuánto margen hay entre la presentación final y el evento.<br>**(T-9)** ¿Se usa la hora local de Ecuador (S-18)? | — | Hora y calendario | Cliente | Media |
| A-14 | ¿Quién puede completar una tarea vencida: el responsable original, otra persona asignada por un administrador o ambos? | P-35 | Vencidas, reasignación y disponibilidad | Cliente | Alta |
| A-15 | Si una tarea cumple las condiciones de varios estados (por ejemplo, vencida con pasos marcados o sin responsables), ¿cómo debe verse?<br>**Añadido en v0.3:** propuesta provisional en S-25. ¿Las tareas por vencer se ordenan de la hora límite más cercana a la más lejana (S-25)? | P-23 | Modelo de estados | Provisional | Media |
| A-16 | **Reformulado en v0.3:** ¿«En ejecución» significa que la tarea tiene responsables y no está terminada, vencida ni por vencer, aunque no tenga pasos marcados (S-08), o solo que ya tiene pasos marcados?<br>*Texto original:* «¿En qué momento pasa una tarea a "en ejecución"?» | P-24 | Modelo de estados | Cliente | Alta |
| A-17 | ¿Qué debe pasar cuando un segundo administrador intenta editar una tarea que otro administrador ya está editando? Propuesta provisional en S-17. | P-13 | Edición y eliminación de tareas | Provisional | Baja |
| A-18 | ¿Cada administrador gestiona todas las tareas o solo las de su área? | P-01, P-17 | Perfiles y permisos | Cliente | Alta |
| A-19 | Si una tarea tiene varios responsables, ¿comparten un mismo checklist? ¿Basta con que uno confirme la finalización?<br>**Añadido en v0.3:** ¿Cada estudiante solo desmarca sus propios pasos (S-29)? Si un paso se marcó por error y su autor ya no está disponible porque fue reasignado o eliminado, ¿quién puede corregirlo? Cuando un responsable guarda, ¿se conservan los cambios que otro responsable hizo en pasos diferentes (S-30)?<br>**(T-5)** ¿Se puede reabrir o editar una tarea terminada (S-11)?<br>**(T-6)** ¿El administrador debe aprobar las tareas terminadas (S-24)? | P-18, P-19, P-26, P-27 | Varios responsables y cierre | Cliente | Alta |
| A-20 | ¿Un administrador puede cambiar los responsables de una tarea ya asignada? Cuando una tarea vence, ¿otro estudiante la toma por su cuenta o se la asigna un administrador?<br>**(T-1)** ¿Qué pasa con las tareas de un estudiante que deja el staff o deja de estar disponible (S-02)?<br>**(T-2)** ¿Un estudiante no disponible queda desactivado o solo marcado (P-04)?<br>**Añadido en v0.3:** ¿Qué pasa con las tareas no terminadas de un estudiante eliminado (S-32)? ¿El estudiante solo ve sus tareas asignadas (S-33)? | P-20, P-35, P-02, P-04 | Vencidas, reasignación y disponibilidad | Cliente | Alta |
| A-21 | ¿Necesitan medir el tiempo de retraso de las tareas o descargar reportes de cumplimiento? | P-38, P-47 | Alcance | Posterior | Baja |
| A-22 | ¿El responsable es obligatorio al crear una tarea, o se puede guardar sin responsable y asignarla después? Propuesta provisional en S-23.<br>**Añadido en v0.3:** ¿El checklist debe tener al menos un paso? Propuesta provisional en S-34. ¿El lugar o aula es obligatorio? Propuesta provisional en S-35. | [DESC], P-23, P-10 | Asignación | Provisional | Media |
| A-23 | ¿Cuánto retraso es aceptable entre que un estudiante termina una tarea y el administrador lo ve en el tablero? Propuesta provisional en S-10. | P-31 | Tiempo real y conexión | Provisional | Baja |
| A-24 | ¿Es necesario registrar la hora exacta de cada paso del checklist o basta con registrar quién lo marcó y la hora de finalización de la tarea? Propuesta provisional en S-20. | P-18, P-32; S-20 | Historial | Provisional | Baja |

---

## 9. Trazabilidad

Relaciona cada regla de negocio con:
- su origen: la pregunta (P-xx), la descripción del proyecto ([DESC]), la aclaración (AC-xx) o el supuesto (S-xx) que la sostiene, y su punto abierto (A-xx) cuando lo tiene;
- la épica y el requisito MoSCoW que la cubren.

Valores de la columna **Tipo**:

| Tipo | Significado |
|---|---|
| **Cliente** | Respuesta del cliente. |
| **Fuente** | [DESC]. |
| **Aclaración** | AC-xx. |
| **Supuesto** | Pendiente de validación. |

Las combinaciones indican que la regla tiene una parte de cada tipo.

| Regla | Resumen | Origen | Tipo | Épica | Requisito |
|---|---|---|---|---|---|
| R1 | Acceso solo con inicio de sesión; cuentas creadas por un administrador | [DESC] | Fuente | E1 | M1 |
| R2 | La cuenta tiene nombre y correo | P-05 | Cliente | E1, E2 | M3 |
| R3 | Cada usuario cambia su propia contraseña | P-06 | Cliente | E1 | M4 |
| R4 | El administrador entrega las credenciales | S-03 (P-05); A-03 | Supuesto | E1 | M1, M3 |
| R5 | El administrador restablece la contraseña olvidada | S-04 (P-07); A-03 | Supuesto | E1 | C5 |
| R6 | Tres perfiles | P-01, [DESC] | Fuente y cliente | E2 | M2 |
| R7 | Administradores por área; «en teoría» los mismos privilegios; el acceso a todas las tareas es supuesto | P-01; S-21 (P-01, P-17); A-18 | Cliente y supuesto | E2 | M2 |
| R8 | El super admin gestiona a los administradores | S-01 (P-01); A-01 | Supuesto | E2 | M3 |
| R9 | El estudiante ve sus tareas asignadas; no ver las de otros ni gestionar tareas o usuarios es una restricción derivada; acceso a una tarea vencida por reasignación | [DESC]; S-33 ([DESC]); S-07 (P-20, P-35); A-20 | Fuente y supuesto | E1 | M7 |
| R10 | Se conserva el historial del estudiante eliminado | P-03 | Cliente | E2, E7 | M13 |
| R11 | El administrador gestiona la disponibilidad del staff | P-02, P-04 | Cliente | E8 | S1 |
| R12 | Las tareas de un estudiante no disponible se reasignan a criterio del administrador | S-02 (P-02); A-20 | Supuesto | E8 | S1, S2 |
| R13 | Datos de una tarea; la obligatoriedad del lugar y el mínimo de un paso son supuestos | [DESC], P-10; S-34, S-35; A-22 | Fuente, cliente y supuesto | E3 | M5 |
| R14 | Responsable como dato de creación; existe el estado «sin asignar»; guardar sin responsables es supuesto; el estado de una tarea sin responsables se calcula con R35 | [DESC], P-23; S-23, S-25; A-22 | Fuente, cliente y supuesto | E3, E4 | M5, M6 |
| R15 | Sin dependencias entre tareas | P-11 | Cliente | E3 | W3 |
| R16 | Sin categorías de tareas | P-17 | Cliente | E3 | W1 |
| R17 | No se elimina una tarea con responsables, con actividad registrada (desde el primer paso marcado que se guardó correctamente) o terminada | P-13 (literal: «una tarea en ejecución no se puede borrar»), P-03; S-28; A-02 | Cliente y supuesto | E3 | M14 |
| R18 | Dos administradores no editan la misma tarea a la vez | P-13 (el mecanismo es S-17; A-17) | Cliente | E3 | M14 |
| R19 | Una tarea terminada se archiva y nadie la borra | P-03, P-32 | Cliente | E3, E7 | M13, M14 |
| R20 | Uno o varios responsables, sin responsable principal | [DESC], P-22 | Fuente y cliente | E4 | M6, W2 |
| R21 | Checklist compartido entre los responsables | S-05 (P-18); A-19 | Supuesto | E4 | M6 |
| R22 | El administrador cambia los responsables de una tarea no terminada; la protección de R17 se mantiene y el estado se recalcula con R35 | S-07 (P-20, P-35), S-25; A-20 | Supuesto | E4 | S2 |
| R23 | Todos los pasos son obligatorios | P-12 | Cliente | E5 | M9 |
| R24 | Quién marcó cada paso y hora de finalización de la tarea; la hora de cada paso es supuesto | P-18, P-32; S-20; A-24 | Cliente y supuesto | E5, E7 | M10, S4 |
| R25 | El estudiante confirma la finalización, y solo con todos los pasos marcados | P-25, P-12 ([DESC] como contexto) | Cliente | E5 | M9 |
| R26 | Basta con que confirme un responsable | S-06 (P-19); A-19 | Supuesto | E5 | M9 |
| R27 | Observaciones adicionales al completar | [DESC] | Fuente | E5 | M8 |
| R28a | La confirmación del estudiante termina la tarea | P-27 | Cliente | E5 | M9 |
| R28b | No hay aprobación del administrador | S-24 (P-27); A-19 | Supuesto | E5 | W4 |
| R29 | Una tarea terminada no se puede editar | S-11 (P-26); A-19 | Supuesto | E7 | M13 |
| R30 | Una tarea vencida sigue visible; completarla después del vencimiento es supuesto | P-35; S-19, S-07; A-14, A-20 | Cliente y supuesto | E5 | S2 |
| R31 | Cinco estados de tarea | P-23 | Cliente | E6 | M11 |
| R32 | «En ejecución»: con responsables, no terminada, no vencida y no por vencer | S-08 (P-24, P-23); A-16 | Supuesto | E6 | M11 |
| R33 | «Por vencer»: desde 30 min antes hasta justo antes de la hora límite | S-09 (P-49); A-05 | Supuesto | E6 | M11 |
| R34 | Pasa sola a «vencida» al llegar la hora límite | P-34 (el instante exacto es S-09) | Cliente | E6 | M11 |
| R35 | Precedencia para calcular el estado (no es el orden del tablero, que es R37) | S-25 (P-23, P-34); A-15 | Supuesto | E6 | M11 |
| R36 | El tablero es la página de inicio del administrador, con tarjetas | P-31 | Cliente | E6 | M12 |
| R37 | Orden del tablero por estado; «por vencer» por fecha de vencimiento; de la más cercana a la más lejana es supuesto | P-23, P-34, P-37; S-25; A-15 | Cliente y supuesto | E6 | M12 |
| R38 | Alerta visual arriba para lo próximo a vencer | P-33 | Cliente | E6 | M12 |
| R39 | Se ve el responsable de cada tarea y quién marcó cada paso; «Sin responsables» visible en cualquier estado | P-18, P-29, P-32; S-25 | Cliente y supuesto | E6, E7 | M10, M12 |
| R40 | Diseño pensado primero para celular | P-39 | Cliente | E5 | M15 |
| R41 | Identidad visual «Señal Neón» como guía; las adaptaciones de interfaz están pendientes | P-43, P-44, AC-01; A-10, A-12 | Cliente y aclaración | E9 | M16 |
| R42 | Guardar y confirmar son acciones distintas; guardar no pierde los cambios de otro responsable | [DESC], P-25, P-12; S-30; A-19 | Fuente, cliente y supuesto | E5 | M8, M9 |
| R43 | Error y reintento si falla guardar o confirmar; sin sincronización sin conexión; falla si quien guarda ya no es responsable o la tarea ya está confirmada | S-31 (P-40, P-41); derivado de S-07, S-11, S-29 y S-33; A-08 | Supuesto | E5 | M8, M9 |
| R44 | Siempre existe al menos un super admin | P-01; S-26; A-01 | Cliente y supuesto | E2 | M2, M3 |
| R45 | Tareas no terminadas de un estudiante eliminado: reasignación, demás responsables y autoría conservados; el estado se recalcula con R35 | P-03; S-32 (P-02), S-25; A-20 | Cliente y supuesto | E2, E4 | M3, M6, M13 |
| R46 | Cada estudiante solo desmarca sus propios pasos; la autoría se conserva | P-18; S-29; A-19 | Cliente y supuesto | E5 | M8, M10 |
| R47 | Los administradores no marcan pasos ni confirman tareas | [DESC] (deducida); S-27; A-01 | Supuesto | E5, E2 | M9 |
