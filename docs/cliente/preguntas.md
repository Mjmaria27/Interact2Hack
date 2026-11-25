# Avance 1 · Interact2Hack — Preguntas y respuestas del cliente

**Proyecto:** Plataforma de coordinación del staff de Interact2Hack  
**Materia:** Desarrollo Web | **Fecha:** 11 de noviembre de 2026  
**Integrantes:** María Paula Baca y Carlos Aluisa


## 2.1. Usuarios y perfiles

**P-01** — ¿Existirá un único administrador general o varios administradores podrán gestionar las tareas y los usuarios del evento?

> **Respuesta del cliente:** Habrá varios administradores; cada uno se encarga de un área (aulas, escenarios) y, en teoría, todos tienen los mismos privilegios. Además, debe existir un super admin con permisos mayores y más acceso.

**P-02** — Si un estudiante deja de formar parte del staff durante el evento, ¿qué debería pasar con las tareas que tenía asignadas?

> **Respuesta del cliente:** No abordado en la reunión. Relacionado: el admin puede gestionar la disponibilidad del staff si alguien no puede asistir por una calamidad.

**P-03** — Si se elimina a un estudiante de la plataforma, ¿se debe conservar el historial de tareas que completó?

> **Respuesta del cliente:** Sí. Las tareas completadas se archivan y no se pueden borrar, como constancia de que se hicieron.

**P-04** — ¿Un administrador podrá desactivar temporalmente a un estudiante sin eliminar su cuenta?

> **Respuesta del cliente:** No abordado en la reunión. Relacionado: se puede manejar un estado del staff u hora de disponibilidad, que controla el admin.


## 2.2. Acceso

**P-05** — ¿Cómo prefieren que los estudiantes reciban sus credenciales de acceso: por correo electrónico o directamente del administrador?

> **Respuesta del cliente:** No abordado en la reunión. Solo indicó que los datos de la cuenta son nombre y correo.

**P-06** — ¿Los estudiantes podrán cambiar la contraseña que les haya asignado el administrador?

> **Respuesta del cliente:** Sí, el usuario debe poder cambiar su contraseña.

**P-07** — Si un estudiante olvida su contraseña durante el hackathon, ¿debería poder recuperarla por su cuenta o solicitar ayuda al administrador?

> **Respuesta del cliente:** No abordado en la reunión.

**P-08** — ¿Necesitan que los usuarios permanezcan conectados durante toda su jornada o que vuelvan a iniciar sesión después de un período de inactividad?

> **Respuesta del cliente:** No abordado en la reunión.

**P-09** — ¿El acceso a la plataforma estará disponible únicamente durante los días del evento o también antes y después?

> **Respuesta del cliente:** No abordado en la reunión.


## 2.3. Tareas y checklist

**P-10** — ¿Cada tarea deberá tener un título y una descripción detallada, o bastará con un nombre y su checklist?

> **Respuesta del cliente:** La tarea debe tener fecha y hora e información/descripción (en descripción.txt).

**P-11** — ¿Los estudiantes podrán ejecutar todas sus tareas desde el inicio o algunas permanecerán bloqueadas hasta completar una tarea anterior, aunque sean visibles?

> **Respuesta del cliente:** No. Técnicamente una tarea no abre otra; cada estudiante puede avanzar en el orden que prefiera.

**P-12** — ¿Una tarea puede incluir pasos opcionales o todos deben ser obligatorios para considerarla completada?

> **Respuesta del cliente:** Todos los pasos son obligatorios: no se debe poder finalizar la tarea si no están todos marcados.

**P-13** — ¿El administrador podrá modificar los pasos de una tarea cuando un estudiante ya haya comenzado a completarla?

> **Respuesta del cliente:** No abordado en la reunión. Relacionado: una tarea en ejecución no se puede borrar y dos admins no pueden editarla a la vez.

**P-14** — ¿Necesitan que las tareas se generen automáticamente de forma recurrente, por ejemplo cada día, o basta con que el administrador las programe anticipadamente?

> **Respuesta del cliente:** No abordado en la reunión.

**P-15** — ¿Una tarea podrá incluir archivos o imágenes de referencia para explicar mejor lo que debe hacer el estudiante?

> **Respuesta del cliente:** No abordado en la reunión.

**P-16** — ¿Los estudiantes podrán adjuntar fotografías como evidencia de que realizaron una tarea o bastará con marcar el checklist y escribir observaciones?

> **Respuesta del cliente:** Sí, se podría; depende de la base de datos.

**P-17** — ¿Necesitan clasificar las tareas en categorías específicas, por ejemplo logística, soporte técnico o preparación de espacios?

> **Respuesta del cliente:** No es relevante clasificar por áreas o categorías del hackathon. Las tareas se ordenan por estado (vencidas, por vencer, en ejecución, sin asignar, terminadas).


## 2.4. Asignación

**P-18** — Si una tarea se asigna a varios estudiantes, ¿todos trabajarán sobre un mismo checklist o cada uno tendrá una copia individual?

> **Respuesta del cliente:** No abordado en la reunión. Sí pidió que en cada check se vea quién fue el responsable.

**P-19** — Cuando una tarea tiene varios responsables, ¿basta con que uno confirme su ejecución o deben hacerlo todos?

> **Respuesta del cliente:** No abordado en la reunión.

**P-20** — ¿Un administrador podrá cambiar a los responsables de una tarea después de haberla asignado?

> **Respuesta del cliente:** No abordado en la reunión.

**P-21** — Si un estudiante no puede realizar una tarea asignada, ¿podrá solicitar una reasignación desde la plataforma?

> **Respuesta del cliente:** No abordado en la reunión.

**P-22** — ¿Necesitan identificar a un responsable principal cuando una tarea esté asignada a varios estudiantes?

> **Respuesta del cliente:** Por el momento no es necesario asignar un líder o responsable principal.


## 2.5. Ejecución y estados

**P-23** — ¿Qué estados necesitan manejar para las tareas: pendiente, en progreso, completada, atrasada u otros?

> **Respuesta del cliente:** Se manejan: vencida, por vencer, en ejecución, sin asignar y terminada. Orden en el tablero: vencidas, por vencer (por fecha de vencimiento), en ejecución, sin asignar y terminadas.

**P-24** — ¿Una tarea debería cambiar automáticamente a «En progreso» cuando un estudiante marca su primer paso?

> **Respuesta del cliente:** No abordado en la reunión.

**P-25** — Cuando se completan todos los pasos del checklist, ¿la tarea debe marcarse como terminada automáticamente o requerir una confirmación final del estudiante?

> **Respuesta del cliente:** La confirmación la hace el estudiante, marcando la tarea como completada, y solo puede finalizar si todos los checks están marcados.

**P-26** — Después de confirmar una tarea como completada, ¿el estudiante podrá volver a editar el checklist?

> **Respuesta del cliente:** No abordado en la reunión. Relacionado: las tareas completadas quedan archivadas y no se pueden borrar.

**P-27** — ¿El administrador debe revisar y aprobar una tarea completada o la confirmación del estudiante será suficiente?

> **Respuesta del cliente:** La confirmación la hace el estudiante; no mencionó una aprobación adicional del admin.

**P-28** — Si un estudiante encuentra un problema que le impide completar una tarea, ¿debería poder marcarla como bloqueada y explicar el motivo?

> **Respuesta del cliente:** No abordado en la reunión.


## 2.6. Tablero de cumplimiento

**P-29** — ¿El administrador debería poder filtrar las tareas por estudiante responsable?

> **Respuesta del cliente:** No abordado en la reunión. Sí indicó que debe verse quién fue el responsable de cada tarea.

**P-30** — ¿Necesitan filtrar las tareas por lugar o aula para supervisar las actividades de cada espacio?

> **Respuesta del cliente:** No abordado en la reunión.

**P-31** — ¿El tablero debe actualizarse automáticamente cuando un estudiante complete una tarea o es suficiente actualizar la información manualmente?

> **Respuesta del cliente:** Al ingresar como admin debe verse una cuadrícula de tarjetas con el estado de cada tarea; el panel de seguimiento debe estar ya en el homepage. No precisó la actualización automática.

**P-32** — ¿Necesitan consultar un historial de tareas completadas para revisar quién las realizó y a qué hora?

> **Respuesta del cliente:** Sí. Las tareas completadas se archivan sin poder borrarse y debe verse quién fue el responsable de cada check.

**P-33** — Cuando una tarea esté próxima a vencer, ¿qué tipo de aviso necesita recibir el administrador: una alerta visual en el tablero, una notificación o ambas?

> **Respuesta del cliente:** Alerta visual: en la misma página, en la parte superior, debe aparecer la tarea próxima a vencer.


## 2.7. Vencimientos

**P-34** — Si llega la hora límite de una tarea y no está completada, ¿debería marcarse automáticamente como atrasada?

> **Respuesta del cliente:** Debe aparecer como vencida (no ejecutada) y en primer lugar del tablero.

**P-35** — ¿Un estudiante podrá seguir completando una tarea después de su hora de vencimiento?

> **Respuesta del cliente:** No abordado en la reunión. Indicó que la tarea vencida sigue visible y otra persona podría realizarla.

**P-36** — ¿El administrador podrá ampliar la fecha u hora límite de una tarea que está próxima a vencer o ya está atrasada?

> **Respuesta del cliente:** No abordado en la reunión.

**P-37** — Cuando una tarea se atrase, ¿el administrador debería recibir una alerta para tomar medidas?

> **Respuesta del cliente:** Se resalta en el tablero: las tareas vencidas aparecen en primer lugar.

**P-38** — ¿Necesitan registrar cuánto tiempo de retraso tuvo una tarea para evaluar el cumplimiento del staff?

> **Respuesta del cliente:** No abordado en la reunión.

**P-49** — ¿Con cuánta anticipación una tarea debe considerarse «próxima a vencer»: 15 minutos, 30 minutos, una hora u otro intervalo?

> **Respuesta del cliente:** No definió un intervalo exacto; solo pidió que la tarea próxima a vencer aparezca en la parte superior de la página.


## 2.8. Contexto de uso

**P-39** — Durante el hackathon, ¿los estudiantes utilizarán principalmente celulares, computadoras o ambos dispositivos?

> **Respuesta del cliente:** El diseño debe pensarse más para celular, para que la información se vea bien.

**P-40** — ¿Se espera que todos los espacios del evento tengan conexión estable a internet?

> **Respuesta del cliente:** No abordado en la reunión.

**P-41** — Si un estudiante pierde la conexión mientras completa un checklist, ¿necesitan que pueda continuar trabajando y sincronizar su avance cuando vuelva a conectarse?

> **Respuesta del cliente:** No abordado en la reunión. Indicó que en JavaScript existe una forma de detectar cuando no hay conexión.

**P-42** — ¿Cuántos estudiantes y administradores estiman que utilizarán la plataforma durante el evento?

> **Respuesta del cliente:** No abordado en la reunión.


## 2.9. Marca y diseño

**P-43** — ¿Interact2Hack cuenta con una identidad visual oficial que debamos respetar, como logotipo, colores y tipografías?

> **Respuesta del cliente:** Sí. El cliente enviará una carpeta con el diseño del hackathon.

**P-44** — Si existe una identidad visual, ¿podrían proporcionarnos los archivos y lineamientos de marca?

> **Respuesta del cliente:** Sí, enviarán una carpeta con el diseño del hackathon.

**P-45** — ¿Prefieren una interfaz visualmente relacionada con la estética tecnológica del hackathon o una apariencia más sencilla y enfocada en la organización de tareas?

> **Respuesta del cliente:** No abordado en la reunión.


## 2.10. Alcance del proyecto

**P-46** — ¿Cuáles son las tres funcionalidades que consideran indispensables para que la primera versión sea útil durante el hackathon?

> **Respuesta del cliente:** No abordado en la reunión.

**P-47** — ¿Necesitan que los administradores puedan descargar reportes del cumplimiento de tareas al finalizar el evento?

> **Respuesta del cliente:** No abordado en la reunión.

**P-48** — ¿Qué funcionalidades consideran deseables, pero podrían dejarse para una segunda versión si el tiempo de desarrollo es limitado?

> **Respuesta del cliente:** No abordado en la reunión.


---

# Consolidación de respuestas y supuestos

**Fecha de consolidación:** 25 de noviembre de 2026  
**Documentos revisados:** este documento (respuestas del 11 de noviembre de 2026), `docs/fuentes/descripcion-proyecto.md` (**[DESC]**), `docs/prd/PRD.md` v0.2, `docs/prd/revision.md` y `docs/diseno/sistema-de-diseno.md` v0.1.

Esta sección no modifica las preguntas P-01 a P-49 ni las respuestas registradas arriba. Relaciona cada supuesto o decisión del PRD con la pregunta de la que sale y clasifica su estado según la evidencia disponible.

**Sincronización con el PRD v0.3 (25 de noviembre de 2026).** La consolidación inicial se hizo sobre el PRD v0.2. Después se sincronizó con:
- el PRD v0.3;
- el registro de decisiones de `docs/prd/revision.md`, en la sección «Revisión del PRD v0.3 — Avance 2».

Las fuentes primarias siguen siendo las respuestas del cliente y [DESC]. Ninguna decisión del equipo tomada después de la reunión se presenta como respuesta del cliente. Las filas actualizadas llevan la marca «(v0.3)».

## Criterios de clasificación

| Estado | Cuándo se usa |
|---|---|
| **Confirmado** | Una respuesta del cliente lo dice de forma directa, o lo establece la descripción oficial del proyecto (**[DESC]**). Si la evidencia es una aclaración posterior (sección AC-xx), se indica en la justificación. |
| **Descartado** | La evidencia disponible lo contradice o lo deja sin efecto. |
| **Pendiente** | No hay respuesta del cliente, la respuesta es parcial, condicional («en teoría», «se podría», «por el momento») o ambigua, o se trata de una propuesta del equipo que el cliente no ha validado. |

Reglas aplicadas:

- Una decisión provisional del equipo (marcada **[SUPUESTO]** en el PRD o **[EQUIPO]** en el sistema de diseño) nunca se clasifica como confirmada solo porque el PRD la usa.
- Cuando una respuesta confirma una parte y deja otra sin resolver, la decisión se divide en dos filas (sufijos **a** y **b**): una con lo confirmado y otra con lo pendiente.
- Los comentarios que el cliente hizo «relacionados» con una pregunta no respondida confirman solo lo que dicen. No responden la pregunta original.
- La prioridad MoSCoW (Must, Should, Could, Won't) que el PRD asigna a cada función es siempre una propuesta del equipo (S-22), aunque la función en sí esté confirmada.

## Tabla de supuestos y decisiones

Los identificadores son los del PRD:

| Identificador | Qué es |
|---|---|
| S-xx | Supuestos |
| R-xx | Reglas |
| M, S1–S4, C1–C5, W | Requisitos Must, Should, Could y Won't |
| CE1–CE8 | Criterios de éxito |
| O1–O5 | Objetivos |
| **SD-xx** | Decisiones del sistema de diseño sobre la identidad visual |
| **AC-xx** | Aclaraciones posteriores a la reunión |

**C1 a C5** (sin «E») son requisitos Could. No deben confundirse con los criterios de éxito CE1 a CE8.

Los sufijos a, b y c de esta tabla (por ejemplo S-13a, S-14c o R17a) son divisiones propias de esta consolidación. En el PRD, el supuesto es uno solo (S-13, S-14).

Esta tabla clasifica las decisiones que tienen una parte respaldada por el cliente o por [DESC]. La lista completa de los supuestos del PRD v0.3 (S-01 a S-35), con su regla y su punto abierto, está en el «Índice de supuestos del PRD v0.3», después del resumen.

| ID | Supuesto o decisión | Pregunta de origen | Estado | Justificación |
|---|---|---|---|---|
| R6 / M2 | Hay tres perfiles: super admin, administrador y estudiante. | P-01, [DESC] | Confirmado | P-01: «Habrá varios administradores» y «debe existir un super admin». [DESC] define los perfiles de administrador y estudiante. |
| R7a | Puede haber varios administradores y cada uno se encarga de un área (aulas, escenarios). | P-01 | Confirmado | Lo dice la respuesta a P-01. |
| R7b | Todos los administradores tienen los mismos privilegios. | P-01 | Pendiente | El cliente dijo que los tienen «en teoría». Es una respuesta condicional y no se toma como definitiva. |
| S-21 | Todos los administradores ven y gestionan todas las tareas, sin distinguir por área. | P-01, P-17 | Pendiente | Lo deduce el equipo. P-01 asigna un área a cada administrador, y P-17 solo dice que no es relevante clasificar las tareas por área. Ninguna respuesta dice si el acceso se limita por área. Punto abierto A-18. |
| S-01 / R8 | (v0.3) El super admin hereda todos los permisos del administrador. Su permiso adicional es gestionar las cuentas de los administradores; por eso M3 restringe esa gestión al super admin. | P-01 | Pendiente | P-01 confirma que el super admin tiene «permisos mayores y más acceso», pero no dice cuáles ni confirma de forma expresa que herede todos los permisos del administrador. Punto abierto A-01. |
| R11 | El administrador gestiona el estado o la disponibilidad del staff, por ejemplo si alguien no puede asistir por una calamidad. | P-02, P-04 | Confirmado | El cliente lo mencionó como comentario relacionado con P-02 y P-04. Que sea Should (S1) es una propuesta del equipo (S-22). |
| R11b | Marcar el estado o la disponibilidad equivale a desactivar temporalmente al estudiante sin eliminar su cuenta. | P-04 | Pendiente | El PRD responde P-04 con R11, pero el cliente no dijo si un estudiante no disponible puede seguir iniciando sesión ni si su cuenta queda desactivada. |
| S-02 / R12 | Si un estudiante deja de estar disponible, sus tareas pendientes no cambian solas y el administrador decide si las reasigna. | P-02 | Pendiente | P-02 no se abordó. Solo se mencionó la gestión de la disponibilidad. |
| R10 / M13 | Si se elimina a un estudiante, se conserva el historial de las tareas que completó. | P-03 | Confirmado | P-03: «Sí. Las tareas completadas se archivan y no se pueden borrar». |
| R1 / M1 | Solo se entra iniciando sesión. No hay registro público: las cuentas las crea un administrador. | [DESC] | Confirmado | Lo establece la descripción del proyecto, no una respuesta de la reunión. |
| R2 | La cuenta tiene nombre y correo. | P-05 | Confirmado | En P-05 el cliente «indicó que los datos de la cuenta son nombre y correo». |
| S-03 / R4 | El administrador entrega las credenciales iniciales directamente al estudiante. La plataforma no las envía por correo. | P-05 | Pendiente | P-05 no se abordó en lo que respecta a cómo se entregan las credenciales. |
| R3 / M4 | Cada usuario puede cambiar su propia contraseña. | P-06 | Confirmado | P-06: «Sí, el usuario debe poder cambiar su contraseña». |
| S-04 / R5 / C5 | Si un estudiante olvida su contraseña, un administrador se la restablece. La recuperación por cuenta propia queda como Could. | P-07 | Pendiente | P-07 no se abordó. |
| S-18 | Las fechas y horas usan la hora local de Ecuador. | — | Pendiente | No se preguntó al cliente. |
| R13 / M5 | (v0.3) Toda tarea tiene fecha y hora de vencimiento y descripción, y un checklist. El lugar o aula es un dato de la tarea. | P-10, [DESC] | Confirmado | P-10 confirma la fecha, la hora y la descripción. [DESC] incluye el lugar o aula y el checklist entre los datos de la tarea. Dos condiciones quedan como supuestos pendientes (A-22): que el lugar sea **obligatorio** (S-35) y que el checklist tenga **al menos un paso** (S-34). |
| R15 / W3 | Las tareas no dependen unas de otras: el estudiante las hace en el orden que quiera. | P-11 | Confirmado | P-11: «una tarea no abre otra; cada estudiante puede avanzar en el orden que prefiera». |
| R23 | Todos los pasos del checklist son obligatorios. | P-12 | Confirmado | P-12: «Todos los pasos son obligatorios». |
| R17a | Una tarea en ejecución no se puede borrar. | P-13 | Confirmado | El cliente lo dijo como comentario relacionado con P-13. La pregunta P-13 en sí (modificar los pasos de una tarea ya empezada) sigue pendiente: A-02. |
| S-28 / R17b | (v0.3) Cómo se aplica la frase anterior: no se puede eliminar una tarea con responsables asignados, con actividad de ejecución registrada o terminada. La actividad registrada empieza cuando se guarda correctamente, por primera vez, un paso marcado, y no desaparece aunque después se desmarquen los pasos, se retiren los responsables o se reasigne la tarea. | P-13, P-03 | Pendiente | El cliente solo pidió que no se borre una tarea «en ejecución» (R17a) y una terminada (P-03). Proteger también las tareas con responsables o con actividad, y definir cuándo empieza la actividad, es una interpretación del equipo. Punto abierto A-02. |
| R18 / M14 | Dos administradores no pueden editar la misma tarea a la vez. | P-13 | Confirmado | Igual que R17: comentario relacionado con P-13. |
| S-17 | Cuando un segundo administrador intenta editar una tarea, recibe un aviso y no puede guardar hasta que el primero termine. | P-13 | Pendiente | El cliente pidió la restricción, pero no cómo debe aplicarse. Punto abierto A-17. |
| S-14a / W5 | Las tareas recurrentes generadas automáticamente quedan fuera de esta versión. | P-14 | Pendiente | P-14 no se abordó. Es una propuesta del equipo. |
| S-13a / C4 | Los archivos o imágenes de referencia dentro de la tarea son deseables, pero no indispensables (Could). | P-15 | Pendiente | P-15 no se abordó. |
| C1 | Se pueden adjuntar fotografías como evidencia, como función Could. | P-16 | Pendiente | La respuesta es condicional: «se podría; depende de la base de datos». No confirma que se deba hacer. Punto abierto A-11. |
| R16 / W1 | Las tareas no se clasifican por categoría ni por área. | P-17 | Confirmado | P-17: «No es relevante clasificar por áreas o categorías del hackathon». |
| R20 / M6 | Una tarea se asigna a uno o varios estudiantes. | [DESC] | Confirmado | Lo establece la descripción del proyecto. |
| W2 | No hay responsable principal o líder de tarea en esta versión. | P-22 | Confirmado | P-22: «Por el momento no es necesario». Queda confirmado solo para esta versión. La respuesta no excluye que se necesite más adelante. |
| M10 / R24a | Cada paso del checklist registra quién lo marcó. | P-18, P-32 | Confirmado | P-18: el cliente «pidió que en cada check se vea quién fue el responsable». P-32 lo repite. |
| S-05 / R21 | Si una tarea tiene varios responsables, todos trabajan sobre un mismo checklist compartido. | P-18 | Pendiente | P-18 no se abordó en este punto. Que se registre quién marcó cada paso es compatible con un checklist compartido, pero no lo confirma. Punto abierto A-19. |
| S-06 / R26 | En una tarea con varios responsables, basta con que uno confirme la finalización. | P-19 | Pendiente | P-19 no se abordó. Punto abierto A-19. |
| S-07 / R22 / S2 | El administrador puede cambiar los responsables de una tarea no terminada, también cuando ya venció. Otro estudiante accede a una tarea vencida solo si un administrador se la asigna (R9). | P-20, P-35 | Pendiente | P-20 no se abordó. P-35 dice que otra persona «podría realizarla», pero no cómo llega a ella. (v0.3) Retirar o cambiar responsables no quita la protección contra eliminación (S-28), y el estado se recalcula con R35. Punto abierto A-20. |
| S-14b / W6 | El estado «bloqueada» y las solicitudes de reasignación hechas por el estudiante quedan fuera de esta versión. | P-21, P-28 | Pendiente | P-21 y P-28 no se abordaron. Es una propuesta del equipo. |
| R14a | El responsable forma parte de los datos de creación de una tarea, y existe el estado «sin asignar». | [DESC], P-23 | Confirmado | [DESC] incluye el responsable entre los datos de creación. P-23 incluye el estado «sin asignar». |
| S-23 / R14b | (v0.3) Una tarea se puede guardar sin responsables y asignarse después. Mientras no tenga responsables, su estado se calcula según R35: «sin asignar», o bien «por vencer» o «vencida» si corresponde. Su tarjeta indica «Sin responsables». | [DESC], P-23 | Pendiente | Lo deduce el equipo de que exista el estado «sin asignar». [DESC] incluye el responsable como dato de creación. Una tarea sin responsables no queda automáticamente «sin asignar». Punto abierto A-22. |
| R31 / M11a | Una tarea siempre está en uno de cinco estados: vencida, por vencer, en ejecución, sin asignar o terminada. | P-23 | Confirmado | P-23 confirma los cinco estados. La precedencia que asegura que cada tarea tenga un solo estado es S-25, que está pendiente. |
| R37 | (v0.3) El tablero se ordena por estado: vencidas, por vencer, en ejecución, sin asignar y terminadas. Las tareas por vencer, por fecha de vencimiento. | P-23, P-17 | Confirmado | Lo dicen las respuestas a P-23 y P-17. Que las tareas por vencer vayan de la hora límite más cercana a la más lejana es una interpretación del equipo (S-25), pendiente en A-15. |
| S-25 / R35 | (v0.3) Para calcular el estado se usa esta precedencia: terminada, vencida, por vencer, en ejecución y sin asignar. Si una tarea no tiene responsables, su tarjeta lo indica en cualquier estado. Dentro del grupo «por vencer» del tablero, las tareas van de la hora límite más cercana a la más lejana. | P-23, P-34 | Pendiente | P-23 define el orden del tablero, no cómo se calcula el estado. Con esta precedencia, los estados de tiempo pesan más que la asignación: una tarea vencida o por vencer sin responsables conserva ese estado. Punto abierto A-15. |
| S-08 / R32 | (v0.3) Una tarea con responsables que no está terminada, vencida ni por vencer está «en ejecución», aunque no tenga pasos marcados. | P-24, P-23 | Pendiente | P-24 no se abordó. En el PRD v0.2 la definición era «pasa a "en ejecución" cuando se marca su primer paso». Se cambió porque con esa definición una tarea asignada y sin pasos marcados no tenía ninguno de los cinco estados. Punto abierto A-16. |
| R25 / M9 | El estudiante confirma la finalización, y solo puede hacerlo si todos los pasos están marcados. La tarea no se termina sola. | P-25, P-12 | Confirmado | P-25: «La confirmación la hace el estudiante […] y solo puede finalizar si todos los checks están marcados». |
| R27 | Al completar una tarea, el estudiante puede escribir observaciones adicionales. | [DESC] | Confirmado | [DESC]: «un campo para colocar observaciones adicionales». |
| R19 | Una tarea terminada queda archivada y nadie puede borrarla. | P-03, P-32 | Confirmado | Lo dicen las respuestas a P-03 y P-32. |
| S-11 / R29 | Una tarea terminada no se puede reabrir ni editar. | P-26 | Pendiente | P-26 no se abordó. El cliente solo confirmó que no se puede **borrar** (R19). No dijo nada sobre editarla. |
| R28a | La confirmación del estudiante es la que da la tarea por terminada. | P-27 | Confirmado | P-27: «La confirmación la hace el estudiante». |
| S-24 / R28b / W4 | El administrador no aprueba las tareas terminadas. Ese flujo queda fuera de la versión. | P-27 | Pendiente | Según la respuesta, el cliente «no mencionó una aprobación adicional del admin». No mencionarla no equivale a confirmar que no se necesita ni a descartarla, así que queda pendiente de validación. (v0.3) Ya está corregido en el PRD: R28 se dividió en R28a y R28b, y R28b se registró como supuesto S-24. Punto abierto A-19 (T-6). |
| S-13b / C3 | Los filtros del tablero por responsable y por lugar o aula son deseables, pero no indispensables (Could). | P-29, P-30 | Pendiente | P-29 y P-30 no se abordaron. Que se vea el responsable de cada tarea sí está confirmado (R39). |
| R39 | En cada tarea se ve quién es el responsable y, en el historial, quién marcó cada paso. | P-18, P-29, P-32 | Confirmado | Lo dicen las respuestas a P-18, P-29 y P-32. (v0.3) Que la tarjeta indique «Sin responsables» en cualquier estado forma parte de S-25, que está pendiente. |
| R36 / M12 | El tablero de cumplimiento es la página de inicio del administrador y muestra una cuadrícula de tarjetas con el estado de cada tarea. | P-31 | Confirmado | P-31: «Al ingresar como admin debe verse una cuadrícula de tarjetas […] el panel de seguimiento debe estar ya en el homepage». |
| S-10 / S3 | (v0.3) El tablero refleja los cambios en un máximo de 60 segundos, sin recargar la página. | P-31 | Pendiente | El cliente «no precisó la actualización automática». La cifra es una propuesta del equipo y corresponde a S3, que es Should. En CE5 se separan dos cosas: el cálculo correcto de los estados al consultar o actualizar el tablero, que es indispensable (M11, M12), y la actualización automática en 60 s, que es la parte de S3 y no la convierte en Must. Punto abierto A-23. |
| R24b | La tarea guarda la hora en que se terminó. | P-32 | Confirmado | La pregunta P-32 incluye la hora de forma explícita: «¿Necesitan consultar un historial de tareas completadas para revisar quién las realizó y a qué hora?». La respuesta empieza con un «Sí» sin condiciones, que responde a la pregunta completa: «Sí. Las tareas completadas se archivan sin poder borrarse y debe verse quién fue el responsable de cada check.» La segunda frase agrega detalle sobre el responsable, pero no limita el «Sí». La hora de cada paso es otro tema (S-20). |
| S-20 | Además de quién marcó cada paso, se guarda la hora en que se marcó. | P-18, P-32 | Pendiente | Ninguna respuesta pide la hora de cada paso. Punto abierto A-24. |
| R38 | Las tareas próximas a vencer se destacan con una alerta visual en la parte superior de la página. | P-33, P-49 | Confirmado | P-33: «Alerta visual: en la misma página, en la parte superior». |
| W8 | No hay notificaciones fuera de la plataforma (correo o push). | P-33 | Confirmado | P-33 ofrecía tres opciones: «una alerta visual en el tablero, una notificación o ambas». El cliente eligió la alerta visual: «Alerta visual: en la misma página, en la parte superior, debe aparecer la tarea próxima a vencer.» Esta respuesta no aprueba alertas sonoras ni otros tipos de aviso, porque no se preguntó por ellos. |
| R34 / M11b | Si llega la hora límite y la tarea no está terminada, pasa sola a «vencida» y aparece en primer lugar. | P-34, P-37 | Confirmado | P-34: «Debe aparecer como vencida (no ejecutada) y en primer lugar del tablero». P-37 lo repite. Que el instante exacto de la hora límite ya cuente como «vencida» se precisa en S-09. |
| R30a | Una tarea vencida sigue visible. | P-35 | Confirmado | P-35: «la tarea vencida sigue visible». |
| S-19 / R30b | Una tarea vencida todavía se puede completar, por el responsable original o por otra persona a la que un administrador se la asigne. | P-35 | Pendiente | La respuesta es parcial: solo dice que «otra persona podría realizarla». No aclara si el responsable original puede seguir ni cómo se asigna a otra persona. Puntos abiertos A-14 y A-20. |
| S-14c / W7 | Los reportes descargables y la medición del tiempo de retraso quedan fuera de esta versión. | P-38, P-47 | Pendiente | P-38 y P-47 no se abordaron. Es una propuesta del equipo. Punto abierto A-21. |
| S-09 / R33 | (v0.3) Una tarea está «por vencer» desde 30 minutos antes de su hora límite, incluido ese instante, hasta justo antes de la hora límite. Desde la hora límite exacta está «vencida». El umbral es único para todas las tareas. | P-49, P-34 | Pendiente | El cliente «no definió un intervalo exacto». Los 30 minutos son una propuesta del equipo. Punto abierto A-05. |
| M15 / R40 | El diseño se piensa primero para celular, y toda función del estudiante se puede usar con comodidad en el celular. | P-39 | Confirmado | P-39: «El diseño debe pensarse más para celular». |
| S-12 / C2 / W9 | No habrá trabajo sin conexión. Como mucho, se avisará al estudiante de que perdió la conexión. | P-40, P-41 | Pendiente | P-40 y P-41 no se abordaron. El cliente comentó que JavaScript puede detectar la falta de conexión, lo que indica que el aviso es viable, pero no decide el alcance. (v0.3) Qué pasa cuando falla un guardado se define en S-31 (R43), sin prometer sincronización. Punto abierto A-08. |
| M16 / R41 / E9a | La interfaz usa la identidad visual del hackathon. | P-43, P-44; AC-01 | Confirmado | P-43 y P-44 confirman que existe una identidad visual. Según la aclaración posterior AC-01, el brand board «Señal Neón» fue proporcionado por el cliente como guía para diseñar la herramienta. |
| E9b / A-12 | Se dispone de archivos independientes del logotipo (SVG o PNG) para usarlos en la plataforma. | P-44; AC-01 | Pendiente | El brand board oficial ya está disponible en HTML y permite avanzar con el diseño (AC-01). Sin embargo, el logotipo solo aparece dentro de ese HTML; no se han recibido archivos del logotipo por separado. |
| SD-01 | El brand board es solo una referencia visual, sin respaldo del cliente, y falta recibir la identidad oficial (sistema de diseño §0; PRD M16 y A-12). | P-43, P-44; AC-01 | Descartado | AC-01 establece que el cliente proporcionó el brand board a través del profesor y que el profesor indicó usarlo como guía. Deja de ser una referencia sin respaldo. |
| SD-02 | Las decisiones de interfaz que agregan elementos a la marca o cambian sus reglas son aceptables para el cliente:<br>• colores de estado fuera de la paleta oficial (`#FF6B6B` para «vencida» y `#FFC857` para «por vencer»);<br>• uso del morado de marca para el estado «terminada»;<br>• adaptación de la regla «la lima es escasa», que permite varios puntos lima a la vez en el tablero;<br>• adaptación de la regla «una sola señal morada por vista», que reserva la tarjeta señal para la alerta de tareas por vencer. | P-45; AC-01 | Pendiente | Estas decisiones cambian cómo se aplica la identidad del cliente, no solo cómo se construye un componente. AC-01 indica que el brand board es la guía, pero no implica que el cliente apruebe estas adaptaciones. P-45 no se abordó. Punto abierto A-10. Las decisiones de interfaz que corresponden al equipo de diseño están en la sección siguiente (SD-03) y no se incluyen en esta fila. (v0.3) Con la nueva definición de «en ejecución» (S-08) habrá más puntos lima en el tablero, lo que puede chocar con la regla de uso limitado del lima. Está registrado en A-10, y la solución visual se definirá en las exploraciones de diseño. |
| S-22 | (v0.3) La clasificación MoSCoW del PRD y el subconjunto para el Avance 3 (M1, M2, M5 a M12 y M15) son una propuesta del equipo. | P-46, P-48 | Pendiente | P-46 y P-48 no se abordaron. M10 y M15 se añadieron en la v0.3 como propuesta provisional. No está confirmado por el cliente ni es un requisito académico confirmado por el profesor. Punto abierto A-09. |
| S-15 / O5 | (v0.3) La adopción real durante el hackathon (objetivo O5) no tiene métricas acordadas con el cliente. | P-46 | Pendiente | P-46 no se abordó y no hay métricas acordadas con el cliente. Antes esta fila citaba el séptimo criterio de éxito del PRD v0.2, que ahora es **CE7**: un criterio académico del equipo (la demostración del ciclo completo) que no depende de S-15. Por eso la fila se identifica ahora con el objetivo O5. Se relaciona con A-13, porque la fecha del evento sigue sin conocerse. |
| S-16a | La plataforma es solo para el staff: no gestiona participantes, equipos, jurado ni inscripciones. | [DESC] | Confirmado | [DESC] la describe como «herramienta de organización de staff». Conserva su identificador histórico de supuesto, pero ya está confirmado por [DESC] y no es una decisión pendiente. |
| S-16b | No hay mensajería ni chat interno entre administradores y estudiantes. | — | Pendiente | No se preguntó al cliente. Es una exclusión propuesta por el equipo. |

### Resumen de la clasificación

| Estado | Filas |
|---|---|
| Confirmado | 33 |
| Descartado | 1 |
| Pendiente | 34 |
| **Total** | **68** |

En la sincronización con el PRD v0.3 se añadió la fila S-28 / R17b, que está pendiente. Las filas R35 y R28b pasaron a llamarse S-25 / R35 y S-24 / R28b / W4, sin cambiar su estado.

### Índice de supuestos del PRD v0.3

Contiene los supuestos de la sección 8 del PRD v0.3, con su significado vigente.

- **Estado:** ninguno está confirmado por el cliente, salvo S-16a, que está confirmado por [DESC] y conserva su identificador histórico.
- **Uso provisional:** que el equipo use un supuesto mientras tanto no lo confirma.
- **«Pendiente (con parte confirmada)»:** la pregunta relacionada confirma una parte, que figura como fila confirmada en la tabla anterior. El supuesto en sí sigue pendiente.

| ID | Descripción (PRD v0.3) | Fuente o evidencia | Estado | Regla o requisito | Punto abierto |
|---|---|---|---|---|---|
| S-01 | El super admin hereda todos los permisos del administrador. Su permiso adicional es gestionar las cuentas de los administradores (crearlas, editarlas y eliminarlas). | P-01: «permisos mayores y más acceso», sin detallar cuáles. | Pendiente (con parte confirmada: existe un super admin) | R8, M3 | A-01 |
| S-02 | Si un estudiante deja de estar disponible, sus tareas pendientes no cambian solas y el administrador decide si las reasigna. | P-02 no abordada; P-02 y P-04 solo mencionan la disponibilidad (R11). | Pendiente | R12, S1 | A-20 (T-1) |
| S-03 | El administrador entrega las credenciales iniciales directamente al estudiante; la plataforma no las envía por correo. | P-05 no abordada en cuanto al canal. | Pendiente | R4 | A-03 (T-3) |
| S-04 | La recuperación de la contraseña la hace un administrador restableciéndola. La recuperación por cuenta propia queda como Could. | P-07 no abordada. | Pendiente | R5, C5 | A-03 (T-4) |
| S-05 | Varios responsables de una tarea comparten un mismo checklist, y por eso cada paso registra quién lo marcó. | P-18: solo confirma que se ve quién marcó cada paso. | Pendiente (con parte confirmada) | R21 | A-19 |
| S-06 | En una tarea con varios responsables basta con que uno confirme la finalización. | P-19 no abordada. | Pendiente | R26 | A-19 |
| S-07 | El administrador puede cambiar los responsables de una tarea mientras no esté terminada, también cuando ya venció. | P-20 no abordada; P-35: otra persona «podría realizarla». | Pendiente (con parte confirmada) | R22, R9, R30, S2 | A-20, A-14 |
| S-08 | Una tarea con responsables que no está terminada, vencida ni por vencer está «en ejecución», aunque no tenga pasos marcados. | P-24 no abordada; P-23 confirma los cinco estados. | Pendiente | R32, M11 | A-16 |
| S-09 | Una tarea está «por vencer» desde 30 minutos antes de su hora límite, incluido ese instante, hasta justo antes de la hora límite. Desde la hora límite exacta está «vencida». El umbral es único para todas las tareas. | P-49: no definió un intervalo. | Pendiente | R33, R34, M11 | A-05 |
| S-10 | El tablero refleja los cambios en un máximo de 60 segundos, sin que el administrador recargue la página. Corresponde a S3 (Should): de él solo depende la parte de S3 de CE5, no el cálculo de los estados. | P-31: no precisó la actualización automática. | Pendiente | S3, CE5 (parte de S3) | A-23 |
| S-11 | Una tarea terminada no se puede reabrir ni editar. | P-26 no abordada; P-03 solo confirma que no se borra. | Pendiente (con parte confirmada) | R29 | A-19 (T-5) |
| S-12 | No habrá trabajo sin conexión; como mucho, se avisará al estudiante de que perdió la conexión. | P-40 y P-41 no abordadas. | Pendiente | C2, W9 | A-08 |
| S-13 | Los filtros del tablero y los adjuntos de referencia son deseables, pero no indispensables (Could). | P-15, P-29 y P-30 no abordadas. | Pendiente | C3, C4 | A-09 y A-11 (T-8) |
| S-14 | Las tareas recurrentes, el estado «bloqueada», las solicitudes de reasignación, los reportes descargables y la medición del retraso quedan fuera de esta versión. | P-14, P-21, P-28, P-38, P-47 y P-48 no abordadas. | Pendiente | W5, W6, W7 | A-09 (T-7), A-21 |
| S-15 | La adopción real durante el hackathon (O5) no tiene métricas acordadas con el cliente. Los criterios CE1 a CE8 son de verificación académica. | P-46 no abordada. | Pendiente | O5 | A-13 (fecha del evento) |
| S-16a | La plataforma es solo para el staff: no incluye la gestión de participantes del hackathon. | [DESC]: «herramienta de organización de staff». | Confirmado por [DESC] (identificador histórico) | §5 No-alcance | — |
| S-16b | La plataforma no incluye un chat interno. | No se preguntó al cliente. | Pendiente | §5 No-alcance | A-09 (T-10) |
| S-17 | Cuando dos administradores quieren editar la misma tarea, el segundo recibe un aviso y no puede guardar hasta que el primero termine. | P-13: confirma la restricción, no el mecanismo. | Pendiente (con parte confirmada) | R18, M14 | A-17 |
| S-18 | Las fechas y horas de la plataforma usan la hora local de Ecuador. | No se preguntó al cliente. | Pendiente | — | A-13 (T-9) |
| S-19 | Una tarea vencida que no está terminada todavía se puede completar después de su hora límite, por el responsable original o por otra persona a la que un administrador se la asigne. | P-35: solo confirma que sigue visible. | Pendiente (con parte confirmada) | R30 | A-14 |
| S-20 | Además de quién marcó cada paso, se guarda la hora en que se marcó. | P-18 y P-32: confirman quién marcó y la hora de finalización, no la de cada paso. | Pendiente (con parte confirmada) | R24, S4 | A-24 |
| S-21 | Todos los administradores ven y gestionan todas las tareas, sin distinguir por área. | P-01: cada administrador se encarga de un área; P-17. | Pendiente (con parte confirmada) | R7 | A-18 |
| S-22 | La clasificación MoSCoW es una propuesta del equipo. El subconjunto para el Avance 3 (M1, M2, M5 a M12 y M15) también es provisional. | P-46 y P-48 no abordadas. | Pendiente | §4 | A-09 |
| S-23 | Una tarea se puede guardar sin responsables y asignarse después. Mientras no tenga responsables, su estado se calcula según R35, y su tarjeta indica «Sin responsables». | [DESC] (responsable como dato de creación) y P-23 (existe «sin asignar»). | Pendiente | R14, E4 | A-22 |
| S-24 | El administrador no aprueba las tareas terminadas: basta con la confirmación del estudiante. | P-27: el cliente no mencionó una aprobación adicional. | Pendiente | R28b, W4 | A-19 (T-6) |
| S-25 | Precedencia para calcular el estado: terminada, vencida, por vencer, en ejecución y sin asignar. «Sin responsables» visible en cualquier estado. Las tareas por vencer, de la hora límite más cercana a la más lejana. | P-23 (orden del tablero y «por fecha de vencimiento»); P-34. | Pendiente | R35, R37, R39 | A-15 |
| S-26 | Siempre existe al menos una cuenta de super admin, y no se puede eliminar la última. | P-01 (existe un super admin). | Pendiente | R44, M3 | A-01 |
| S-27 | Ni los administradores ni el super admin marcan pasos ni confirman tareas en nombre de un estudiante. | Se deduce de [DESC], que asigna la ejecución y la confirmación a los estudiantes, pero no lo prohíbe de forma explícita; P-25. | Pendiente | R47 | A-01 |
| S-28 | No se puede eliminar una tarea con responsables asignados, con actividad de ejecución registrada o terminada. La actividad empieza cuando se guarda correctamente, por primera vez, un paso marcado, y no desaparece aunque se desmarquen los pasos, se retiren los responsables o se reasigne la tarea. | P-13: «una tarea en ejecución no se puede borrar» (R17a); P-03. | Pendiente (con parte confirmada) | R17, M14, CE8 | A-02 |
| S-29 | Cada estudiante solo desmarca los pasos que marcó él mismo, y solo antes de la confirmación. Los pasos marcados y su autoría se conservan aunque su autor sea reasignado o eliminado. | P-18: que se vea quién marcó cada paso. | Pendiente | R46, M10 | A-19 |
| S-30 | «Guardar» registra los pasos y las observaciones sin terminar la tarea. «Confirmar» guarda el progreso final y la termina. Cuando un responsable guarda, no se pierden los cambios que otro responsable hizo en pasos diferentes. | [DESC] (botón de guardar y observaciones); P-25 (la confirmación la hace el estudiante). | Pendiente (con parte confirmada) | R42, M8, M9 | A-19 |
| S-31 | Si guardar o confirmar falla, se ve un error y se puede reintentar. Nada se muestra como completado si no lo está, tampoco cuando el estudiante ya no es responsable o la tarea ya se confirmó. Los cambios sin guardar se conservan solo mientras el usuario siga en la pantalla. | P-40 y P-41 no abordadas. | Pendiente | R43 | A-08 |
| S-32 | Al eliminar a un estudiante, sus tareas no terminadas quedan para reasignar. Se conservan los demás responsables y la autoría de los pasos que marcó. Si no queda ningún responsable, el estado se recalcula según R35 y la tarjeta indica «Sin responsables». | P-03 (se conserva el historial); P-02 no abordada. | Pendiente (con parte confirmada) | R45 | A-20 |
| S-33 | El estudiante solo ve las tareas que tiene asignadas, y no gestiona tareas ni usuarios. | Se deduce de [DESC], que describe la lista de tareas asignadas; ninguna respuesta del cliente lo trata. | Pendiente | R9, §2 | A-20 |
| S-34 | El checklist de una tarea tiene al menos un paso. | [DESC] y P-10 describen el checklist, pero no un mínimo de pasos. | Pendiente | R13 | A-22 |
| S-35 | El lugar o aula es obligatorio al crear una tarea, por el contexto de coordinación logística del hackathon. | [DESC] lo incluye entre los datos de la tarea, pero no dice que sea obligatorio. | Pendiente | R13 | A-22 |

**Resumen del índice:** 36 entradas. 1 está confirmada por [DESC] (S-16a) y 35 están pendientes; 11 de las pendientes tienen una parte confirmada.

### Reglas principales del PRD v0.3 según su evidencia

| Tema | Parte confirmada | Parte supuesta (pendiente) |
|---|---|---|
| Estados de la tarea | Cinco estados (P-23); la tarea vencida aparece primero (P-34, P-37). | Precedencia: los estados de tiempo pesan más que la asignación (S-25). Definición de «en ejecución» (S-08). Límites de «por vencer» (S-09). |
| Tareas sin responsables | Existe el estado «sin asignar» (P-23). | Una tarea sin responsables puede estar «vencida» o «por vencer», y su tarjeta indica «Sin responsables» (S-23, S-25). |
| Eliminación de tareas | No se borra una tarea «en ejecución» (P-13) ni una terminada (P-03). | No se borra una tarea con responsables o con actividad registrada. La actividad empieza al guardar correctamente el primer paso marcado (S-28). |
| Guardar y confirmar | Botón de guardar y observaciones ([DESC]). El estudiante confirma y solo con todos los pasos marcados (P-25, P-12). | Guardar no termina la tarea ni pierde los cambios de otro responsable (S-30). |
| Autoría de los pasos | Se ve quién marcó cada paso (P-18, P-32). | Cada estudiante desmarca solo sus pasos, y la autoría se conserva si su autor es reasignado o eliminado (S-29, S-32). |
| Errores y conexión | — | Mensaje de error y reintento, sin prometer sincronización sin conexión (S-31, S-12, W9). |
| Restricciones de los perfiles | Tres perfiles (P-01, [DESC]); el administrador se encarga de un área (P-01). | Herencia de permisos del super admin (S-01); último super admin protegido (S-26); el administrador no marca pasos (S-27); restricciones del estudiante (S-33). |

### SD-03 · Decisiones de interfaz que corresponden al equipo de diseño

No todas las adaptaciones visuales necesitan la aprobación individual del cliente. Las siguientes decisiones del sistema de diseño (marcadas **[EQUIPO]**) aplican el brand board a componentes que no define o refuerzan la accesibilidad. No cambian la identidad visual: se mantienen la paleta oficial, las tipografías, las esquinas rectas, el modo oscuro y el estilo de los iconos. Por eso corresponden al equipo de diseño y **no se clasifican** en la tabla anterior. Se mostrarán al cliente como parte del sistema de diseño y del avance funcional, sin someterlas a aprobación una por una.

- **Accesibilidad y contraste:** borde de controles en blanco al 38 %, etiqueta de la tarjeta señal en tinta al 100 %, contorno de foco y objetivo WCAG 2.2 AA.
- **Uso en celular:** área táctil mínima de 48 px, texto de campos de 16 px, tamaños mínimos de 14 px para metadatos y de 11 px para la barra inferior, y reglas para el alcance del pulgar.
- **Componentes que el brand board no define:** anatomía y estados de los campos de formulario, validaciones y mensajes de error, estados deshabilitado, pulsado y cargando, botón destructivo, diálogo de confirmación y fila de paso del checklist.
- **Navegación y adaptación a cada dispositivo:** pestañas por perfil y distribución de las pantallas en celular, tablet y escritorio, siempre dentro de la retícula y los puntos de corte del brand board.
- **Iconos adicionales** dibujados con el estilo del brand board, y **partes del brand board que no se usan** en la herramienta (Anexo C del sistema de diseño).

Si alguna de estas decisiones termina cambiando un color de marca, una tipografía o una regla del brand board, deja de ser responsabilidad del equipo y pasa a SD-02.

## Aclaraciones posteriores a la reunión

Información recibida después de la reunión con el cliente del 11 de noviembre de 2026. **No son citas textuales del cliente** y no sustituyen las respuestas registradas en las preguntas P-01 a P-49.

### AC-01 · Brand board «Señal Neón» como guía de diseño

| Campo | Contenido |
|---|---|
| **Fecha de la aclaración** | Fecha exacta no registrada. Se registró en este documento el 25 de noviembre de 2026. |
| **Canal** | El profesor de la materia, como intermediario. No es una comunicación directa del cliente. |
| **Material** | `docs/diseno/Interact2Hack-Brandboard.html` («Brandboard extendido · Señal Neón v1.0»): logotipo, color, tipografía, retícula, fotografía, componentes, movimiento, voz y aplicaciones para web y app móvil. |
| **Qué se registra** | El cliente proporcionó este archivo a través del profesor. El profesor indicó que el equipo debe usarlo como guía para diseñar la herramienta del staff. |
| **Preguntas relacionadas** | **P-43** (existencia de una identidad visual oficial), **P-44** (entrega de archivos y lineamientos de marca) y **P-45** (estética tecnológica o apariencia más sencilla). |
| **Qué permite dar por confirmado** | Que la interfaz debe guiarse por la identidad «Señal Neón» (M16, R41, E9a), y que el brand board deja de ser una referencia sin respaldo (SD-01, descartado). |
| **Qué no permite dar por confirmado** | • Que el cliente haya aprobado las decisiones del equipo que agregan elementos a la marca o cambian sus reglas (SD-02). Las decisiones que corresponden al equipo de diseño (SD-03) no necesitan aprobación individual.<br>• Que existan archivos independientes del logotipo en SVG o PNG (E9b). El brand board oficial ya está disponible en HTML y permite avanzar con el diseño.<br>• Una respuesta completa a P-45. Seguir el brand board orienta la interfaz hacia la estética del hackathon, pero el cliente no dijo cuánto puede adaptarse para una herramienta operativa (A-10). |
| **Efecto sobre los puntos abiertos del PRD** | **A-12** deja de ser «falta recibir la carpeta» y pasa a ser «confirmar si hay archivos independientes del logotipo». **A-10** sigue abierto, limitado a las adaptaciones de SD-02. (v0.3) Aplicado en el PRD v0.3: M16, R41 y E9 citan AC-01, y A-10 y A-12 están reformulados citando su texto original. |
| **Resumen en cuatro niveles (v0.3)** | 1. **Identidad visual oficial recibida:** el brand board «Señal Neón» (AC-01). Es la guía de diseño.<br>2. **Adaptaciones de marca pendientes de validación:** SD-02, punto abierto A-10, que incluye la posible tensión por el uso del lima en las tareas «en ejecución».<br>3. **Decisiones de interfaz y accesibilidad del equipo:** SD-03. No requieren aprobación individual.<br>4. **Archivos independientes del logotipo pendientes:** E9b, punto abierto A-12. No bloquean el diseño.<br>AC-01 **no** es una aprobación del sistema de diseño de la plataforma. La premisa descartada sobre el brand board se conserva como registro histórico en SD-01. |

## Puntos pendientes de validación con el cliente

### Con punto abierto en el PRD

(v0.3) La lista vigente de preguntas para el cliente está en dos lugares, que no se duplican aquí:
- `docs/prd/PRD.md`, §8 «Puntos abiertos»: los 24 puntos A-01 a A-24, con su grupo, categoría y prioridad;
- `docs/prd/revision.md`, sección «Preguntas pendientes para el cliente (vigente)».

**Ningún punto está cerrado.** Un supuesto adoptado por el equipo no cierra la pregunta.

**Prioridades del PRD v0.3:**
- **Alta:** A-01, A-05, A-09, A-14, A-16, A-18, A-19 y A-20.
- **Media:** A-02, A-06, A-08, A-12, A-13, A-15 y A-22.
- **Baja:** A-03, A-04, A-07, A-10, A-11, A-17, A-21, A-23 y A-24.

**Formulaciones actualizadas en el PRD v0.3:**

| Punto | Cambio |
|---|---|
| A-10 | Limitado a las adaptaciones de SD-02, incluida la tensión por el uso del lima. |
| A-12 | El brand board ya se recibió; solo faltan los archivos independientes del logotipo. |
| A-16 | Qué significa «en ejecución» (S-08). |
| A-22 | Añade el mínimo de un paso (S-34) y la obligatoriedad del lugar (S-35). |

Además, A-01, A-02, A-06, A-08, A-15, A-19 y A-20 incorporan preguntas sobre los supuestos nuevos.

**Antes de la sincronización con la v0.3** había una tabla con las prioridades de la lista histórica de `revision.md`. Esa tabla se sustituyó por esta referencia cruzada para no duplicar el PRD, y sus prioridades ya no están vigentes. Se puede consultar en el historial de git (commit `8b0bf91`).

### Sin punto abierto en el PRD v0.2 (integrados en el PRD v0.3)

Estos temas no tenían punto abierto en el PRD v0.2. En el PRD v0.3 se integraron como preguntas explícitas dentro de los puntos indicados en la última columna, sin crear identificadores A-xx nuevos. Siguen sin respuesta del cliente.

| # | Qué hay que validar | Preguntas | Filas de la tabla | Relación con los puntos abiertos A-01 a A-24 | Integrado en el PRD v0.3 |
|---|---|---|---|---|---|
| T-1 | Qué pasa con las tareas de un estudiante que deja el staff o deja de estar disponible. | P-02 | S-02 | **Relacionado con A-20.** Si el administrador puede cambiar los responsables, esa misma respuesta indica cómo se reasignan las tareas de quien no está disponible. No es un duplicado: A-20 no habla de la disponibilidad. | A-20 (y S-32 para estudiantes eliminados) |
| T-2 | Si un estudiante no disponible queda desactivado (sin acceso) o solo marcado. | P-04 | R11b | **Relacionado con T-1** (mismo caso: miembro del staff no disponible) y, de forma lejana, con A-01 (quién gestiona las cuentas). | A-20 |
| T-3 | Cómo reciben los estudiantes sus credenciales iniciales. | P-05 | S-03 | **Sin punto abierto equivalente.** Comparte tema con T-4 y A-03 (acceso a la cuenta). | A-03 |
| T-4 | Cómo se recupera una contraseña olvidada durante el evento. | P-07 | S-04 | **Sin punto abierto equivalente.** Comparte tema con T-3 y A-03. | A-03 |
| T-5 | Si una tarea terminada se puede reabrir o editar. | P-26 | S-11 | **Relacionado con A-02** (editar una tarea ya empezada) y con A-19 (cómo se confirma la finalización). Afecta al texto del diálogo de confirmación del sistema de diseño (§8.4). | A-19 |
| T-6 | Si el administrador debe aprobar las tareas terminadas. | P-27 | S-24 / R28b | **Relacionado con A-19** (quién confirma la finalización) y con T-5. Los tres tratan del cierre de una tarea. | A-19 (S-24) |
| T-7 | Si se necesitan tareas recurrentes, el estado «bloqueada» o solicitudes de reasignación. | P-14, P-21, P-28 | S-14a, S-14b | **Se solapa en parte con A-09** (qué es indispensable y qué puede esperar) y es de la misma naturaleza que A-21 (funciones que el equipo propone dejar fuera). Además, P-21 se relaciona con A-20 (reasignación), y un estado «bloqueada» cambiaría el modelo de cinco estados (A-15). | A-09 |
| T-8 | Si se necesitan adjuntos de referencia en las tareas y filtros del tablero por responsable o por lugar. | P-15, P-29, P-30 | S-13a, S-13b | **Se solapa en parte con A-09.** Los adjuntos de referencia (P-15) están **relacionados con A-11** (fotografías como evidencia): las dos funciones dependen de poder guardar archivos, y el cliente dijo que eso «depende de la base de datos» (P-16). | A-09 (P-29, P-30) y A-11 (P-15) |
| T-9 | Si se usa la hora local de Ecuador. | — | S-18 | **Relacionado con A-13** (fechas del hackathon) y con los cálculos de tiempo de A-05 y A-06. | A-13 |
| T-10 | Si se descarta la mensajería interna. | — | S-16b | **Se solapa en parte con A-09** (alcance de la versión). | A-09 |

**Duplicidades:** ninguno de los 10 temas está ya cubierto por un punto abierto. Las relaciones son parciales: la respuesta a un punto abierto puede ayudar a resolver un tema, pero no lo cierra por sí sola.

**Agrupaciones propuestas** en esta consolidación. (v0.3) Se aplicaron en el PRD v0.3 sin crear identificadores A-xx nuevos: cada tema figura como pregunta explícita dentro de su punto abierto, y en el PRD los grupos son solo etiquetas.

| Grupo | Temas adicionales | Puntos abiertos existentes |
|---|---|---|
| Acceso y credenciales | T-3, T-4 | A-03 |
| Staff no disponible y reasignación | T-1, T-2 | A-20 |
| Cierre y edición de una tarea | T-5, T-6 | A-19, A-02 |
| Archivos adjuntos | T-8 (P-15) | A-11 |
| Alcance de funciones opcionales | T-7, T-8 (P-29, P-30), T-10 | A-09, A-21 |
| Hora y calendario | T-9 | A-13 |
