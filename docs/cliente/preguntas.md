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

Los identificadores son los del PRD (S-xx para supuestos; R-xx, M-xx, W-xx, etc. para reglas y requisitos). **SD-xx** identifica decisiones del sistema de diseño relacionadas con la identidad visual. **AC-xx** remite a las aclaraciones posteriores a la reunión.

| ID | Supuesto o decisión | Pregunta de origen | Estado | Justificación |
|---|---|---|---|---|
| R6 / M2 | Hay tres perfiles: super admin, administrador y estudiante. | P-01, [DESC] | Confirmado | P-01: «Habrá varios administradores» y «debe existir un super admin». [DESC] define los perfiles de administrador y estudiante. |
| R7a | Puede haber varios administradores y cada uno se encarga de un área (aulas, escenarios). | P-01 | Confirmado | Lo dice la respuesta a P-01. |
| R7b | Todos los administradores tienen los mismos privilegios. | P-01 | Pendiente | El cliente dijo que los tienen «en teoría». Es una respuesta condicional y no se toma como definitiva. |
| S-21 | Todos los administradores ven y gestionan todas las tareas, sin distinguir por área. | P-01, P-17 | Pendiente | Lo deduce el equipo. P-01 asigna un área a cada administrador, y P-17 solo dice que no es relevante clasificar las tareas por área. Ninguna respuesta dice si el acceso se limita por área. Punto abierto A-18. |
| S-01 / R8 | El permiso adicional del super admin es gestionar las cuentas de los administradores. Por eso M3 restringe esa gestión al super admin. | P-01 | Pendiente | P-01 confirma que el super admin tiene «permisos mayores y más acceso», pero no dice cuáles. Punto abierto A-01. |
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
| R13 / M5 | Toda tarea tiene fecha y hora de vencimiento, lugar o aula, descripción y un checklist. | P-10, [DESC] | Confirmado | P-10 confirma la fecha, la hora y la descripción. [DESC] incluye el lugar o aula y el checklist. Exigir «al menos un paso» es una consecuencia lógica que no se validó por separado. |
| R15 / W3 | Las tareas no dependen unas de otras: el estudiante las hace en el orden que quiera. | P-11 | Confirmado | P-11: «una tarea no abre otra; cada estudiante puede avanzar en el orden que prefiera». |
| R23 | Todos los pasos del checklist son obligatorios. | P-12 | Confirmado | P-12: «Todos los pasos son obligatorios». |
| R17 | Una tarea en ejecución no se puede borrar. | P-13 | Confirmado | El cliente lo dijo como comentario relacionado con P-13. La pregunta P-13 en sí (modificar los pasos de una tarea ya empezada) sigue pendiente: A-02. |
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
| S-07 / R22 / S2 | El administrador puede cambiar los responsables de una tarea no terminada, también cuando ya venció. Otro estudiante accede a una tarea vencida solo si un administrador se la asigna (R9). | P-20, P-35 | Pendiente | P-20 no se abordó. P-35 dice que otra persona «podría realizarla», pero no cómo llega a ella. Punto abierto A-20. |
| S-14b / W6 | El estado «bloqueada» y las solicitudes de reasignación hechas por el estudiante quedan fuera de esta versión. | P-21, P-28 | Pendiente | P-21 y P-28 no se abordaron. Es una propuesta del equipo. |
| R14a | El responsable forma parte de los datos de creación de una tarea, y existe el estado «sin asignar». | [DESC], P-23 | Confirmado | [DESC] incluye el responsable entre los datos de creación. P-23 incluye el estado «sin asignar». |
| S-23 / R14b | Una tarea se puede guardar sin responsables y asignarse después. | [DESC], P-23 | Pendiente | Lo deduce el equipo de que exista el estado «sin asignar». [DESC] incluye el responsable como dato de creación. Punto abierto A-22. |
| R31 / M11a | Una tarea siempre está en uno de cinco estados: vencida, por vencer, en ejecución, sin asignar o terminada. | P-23 | Confirmado | Lo dice la respuesta a P-23. |
| R37 | El tablero se ordena así: vencidas, por vencer (por fecha de vencimiento), en ejecución, sin asignar y terminadas. | P-23, P-17 | Confirmado | Lo dicen las respuestas a P-23 y P-17. |
| R35 | Si una tarea cumple las condiciones de varios estados, el estado se calcula con esta precedencia: terminada, vencida, por vencer, en ejecución, sin asignar. | P-23 | Pendiente | P-23 define el orden del tablero, no cómo se calcula el estado. Punto abierto A-15. |
| S-08 / R32 | Una tarea pasa a «en ejecución» cuando se marca su primer paso. | P-24 | Pendiente | P-24 no se abordó. Punto abierto A-16. |
| R25 / M9 | El estudiante confirma la finalización, y solo puede hacerlo si todos los pasos están marcados. La tarea no se termina sola. | P-25, P-12 | Confirmado | P-25: «La confirmación la hace el estudiante […] y solo puede finalizar si todos los checks están marcados». |
| R27 | Al completar una tarea, el estudiante puede escribir observaciones adicionales. | [DESC] | Confirmado | [DESC]: «un campo para colocar observaciones adicionales». |
| R19 | Una tarea terminada queda archivada y nadie puede borrarla. | P-03, P-32 | Confirmado | Lo dicen las respuestas a P-03 y P-32. |
| S-11 / R29 | Una tarea terminada no se puede reabrir ni editar. | P-26 | Pendiente | P-26 no se abordó. El cliente solo confirmó que no se puede **borrar** (R19). No dijo nada sobre editarla. |
| R28a | La confirmación del estudiante es la que da la tarea por terminada. | P-27 | Confirmado | P-27: «La confirmación la hace el estudiante». |
| R28b / W4 | El administrador no aprueba las tareas terminadas. Ese flujo queda fuera de la versión. | P-27 | Pendiente | Según la respuesta, el cliente «no mencionó una aprobación adicional del admin». No mencionarla no equivale a confirmar que no se necesita ni a descartarla, así que queda pendiente de validación. El PRD marca R28 como decisión del cliente; conviene corregirlo. |
| S-13b / C3 | Los filtros del tablero por responsable y por lugar o aula son deseables, pero no indispensables (Could). | P-29, P-30 | Pendiente | P-29 y P-30 no se abordaron. Que se vea el responsable de cada tarea sí está confirmado (R39). |
| R39 | En cada tarea se ve quién es el responsable y, en el historial, quién marcó cada paso. | P-18, P-29, P-32 | Confirmado | Lo dicen las respuestas a P-18, P-29 y P-32. |
| R36 / M12 | El tablero de cumplimiento es la página de inicio del administrador y muestra una cuadrícula de tarjetas con el estado de cada tarea. | P-31 | Confirmado | P-31: «Al ingresar como admin debe verse una cuadrícula de tarjetas […] el panel de seguimiento debe estar ya en el homepage». |
| S-10 / S3 | El tablero refleja los cambios en un máximo de 60 segundos, sin recargar la página. | P-31 | Pendiente | El cliente «no precisó la actualización automática». La cifra es una propuesta del equipo. Punto abierto A-23. |
| R24b | La tarea guarda la hora en que se terminó. | P-32 | Confirmado | La pregunta P-32 incluye la hora de forma explícita: «¿Necesitan consultar un historial de tareas completadas para revisar quién las realizó y a qué hora?». La respuesta empieza con un «Sí» sin condiciones, que responde a la pregunta completa: «Sí. Las tareas completadas se archivan sin poder borrarse y debe verse quién fue el responsable de cada check.» La segunda frase agrega detalle sobre el responsable, pero no limita el «Sí». La hora de cada paso es otro tema (S-20). |
| S-20 | Además de quién marcó cada paso, se guarda la hora en que se marcó. | P-18, P-32 | Pendiente | Ninguna respuesta pide la hora de cada paso. Punto abierto A-24. |
| R38 | Las tareas próximas a vencer se destacan con una alerta visual en la parte superior de la página. | P-33, P-49 | Confirmado | P-33: «Alerta visual: en la misma página, en la parte superior». |
| W8 | No hay notificaciones fuera de la plataforma (correo o push). | P-33 | Confirmado | P-33 ofrecía tres opciones: «una alerta visual en el tablero, una notificación o ambas». El cliente eligió la alerta visual: «Alerta visual: en la misma página, en la parte superior, debe aparecer la tarea próxima a vencer.» Esta respuesta no aprueba alertas sonoras ni otros tipos de aviso, porque no se preguntó por ellos. |
| R34 / M11b | Si llega la hora límite y la tarea no está terminada, pasa sola a «vencida» y aparece en primer lugar. | P-34, P-37 | Confirmado | P-34: «Debe aparecer como vencida (no ejecutada) y en primer lugar del tablero». P-37 lo repite. |
| R30a | Una tarea vencida sigue visible. | P-35 | Confirmado | P-35: «la tarea vencida sigue visible». |
| S-19 / R30b | Una tarea vencida todavía se puede completar, por el responsable original o por otra persona a la que un administrador se la asigne. | P-35 | Pendiente | La respuesta es parcial: solo dice que «otra persona podría realizarla». No aclara si el responsable original puede seguir ni cómo se asigna a otra persona. Puntos abiertos A-14 y A-20. |
| S-14c / W7 | Los reportes descargables y la medición del tiempo de retraso quedan fuera de esta versión. | P-38, P-47 | Pendiente | P-38 y P-47 no se abordaron. Es una propuesta del equipo. Punto abierto A-21. |
| S-09 / R33 | Una tarea está «por vencer» cuando faltan 30 minutos o menos para su hora límite. | P-49 | Pendiente | El cliente «no definió un intervalo exacto». Los 30 minutos son una propuesta del equipo. Punto abierto A-05. |
| M15 / R40 | El diseño se piensa primero para celular, y toda función del estudiante se puede usar con comodidad en el celular. | P-39 | Confirmado | P-39: «El diseño debe pensarse más para celular». |
| S-12 / C2 / W9 | No habrá trabajo sin conexión. Como mucho, se avisará al estudiante de que perdió la conexión. | P-40, P-41 | Pendiente | P-40 y P-41 no se abordaron. El cliente comentó que JavaScript puede detectar la falta de conexión, lo que indica que el aviso es viable, pero no decide el alcance. Punto abierto A-08. |
| M16 / R41 / E9a | La interfaz usa la identidad visual del hackathon. | P-43, P-44; AC-01 | Confirmado | P-43 y P-44 confirman que existe una identidad visual. Según la aclaración posterior AC-01, el brand board «Señal Neón» fue proporcionado por el cliente como guía para diseñar la herramienta. |
| E9b / A-12 | Se dispone de archivos independientes del logotipo (SVG o PNG) para usarlos en la plataforma. | P-44; AC-01 | Pendiente | El brand board oficial ya está disponible en HTML y permite avanzar con el diseño (AC-01). Sin embargo, el logotipo solo aparece dentro de ese HTML; no se han recibido archivos del logotipo por separado. |
| SD-01 | El brand board es solo una referencia visual, sin respaldo del cliente, y falta recibir la identidad oficial (sistema de diseño §0; PRD M16 y A-12). | P-43, P-44; AC-01 | Descartado | AC-01 establece que el cliente proporcionó el brand board a través del profesor y que el profesor indicó usarlo como guía. Deja de ser una referencia sin respaldo. |
| SD-02 | Las decisiones de interfaz que agregan elementos a la marca o cambian sus reglas son aceptables para el cliente:<br>• colores de estado fuera de la paleta oficial (`#FF6B6B` para «vencida» y `#FFC857` para «por vencer»);<br>• uso del morado de marca para el estado «terminada»;<br>• adaptación de la regla «la lima es escasa», que permite varios puntos lima a la vez en el tablero;<br>• adaptación de la regla «una sola señal morada por vista», que reserva la tarjeta señal para la alerta de tareas por vencer. | P-45; AC-01 | Pendiente | Estas decisiones cambian cómo se aplica la identidad del cliente, no solo cómo se construye un componente. AC-01 indica que el brand board es la guía, pero no implica que el cliente apruebe estas adaptaciones. P-45 no se abordó. Punto abierto A-10. Las decisiones de interfaz que corresponden al equipo de diseño están en la sección siguiente (SD-03) y no se incluyen en esta fila. |
| S-22 | La clasificación MoSCoW del PRD y el subconjunto para el Avance 3 (M1, M2, M5 a M9, M11 y M12) son una propuesta del equipo. | P-46, P-48 | Pendiente | P-46 y P-48 no se abordaron. Punto abierto A-09. |
| S-15 / C7 | El éxito se mide por el uso real durante el hackathon, sin métricas numéricas. | P-46 | Pendiente | P-46 no se abordó y no hay métricas acordadas con el cliente. |
| S-16a | La plataforma es solo para el staff: no gestiona participantes, equipos, jurado ni inscripciones. | [DESC] | Confirmado | [DESC] la describe como «herramienta de organización de staff». |
| S-16b | No hay mensajería ni chat interno entre administradores y estudiantes. | — | Pendiente | No se preguntó al cliente. Es una exclusión propuesta por el equipo. |

### Resumen de la clasificación

| Estado | Filas |
|---|---|
| Confirmado | 33 |
| Descartado | 1 |
| Pendiente | 33 |
| **Total** | **67** |

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
| **Efecto sobre los puntos abiertos del PRD** | **A-12** deja de ser «falta recibir la carpeta» y pasa a ser «confirmar si hay archivos independientes del logotipo». **A-10** sigue abierto, limitado a las adaptaciones de SD-02. |

## Puntos pendientes de validación con el cliente

### Con punto abierto en el PRD

Se mantienen las prioridades de `docs/prd/revision.md`. A-12 y A-10 se reformulan por la aclaración AC-01.

| Prioridad | Punto | Qué hay que validar | Preguntas | Filas de la tabla |
|---|---|---|---|---|
| Alta | A-19 | Si los responsables comparten un mismo checklist y si basta con que uno confirme la finalización. | P-18, P-19 | S-05, S-06 |
| Alta | A-16 | En qué momento pasa una tarea a «en ejecución». | P-24 | S-08 |
| Alta | A-05 | Cuántos minutos antes de la hora límite una tarea está «por vencer». | P-49 | S-09 |
| Alta | A-15 | Cómo se ve una tarea que cumple las condiciones de varios estados. | P-23 | R35 |
| Alta | A-14 | Quién puede completar una tarea vencida. | P-35 | S-19 |
| Alta | A-20 | Si un administrador puede cambiar los responsables, y cómo llega otro estudiante a una tarea vencida. | P-20, P-35 | S-07 |
| Alta | A-22 | Si el responsable es obligatorio al crear una tarea. | [DESC], P-23 | S-23 |
| Alta | A-18 | Si cada administrador gestiona todas las tareas o solo las de su área, y si los privilegios son realmente iguales («en teoría»). | P-01, P-17 | S-21, R7b |
| Alta | A-01 | Qué permisos concretos tiene el super admin, quién crea su cuenta y si un administrador puede eliminar a otro. | P-01 | S-01 |
| Alta | A-09 | Cuáles son las funciones indispensables y cuáles pueden esperar a una segunda versión. | P-46, P-48 | S-22, S-15 |
| Media | A-12 (reformulado) | Si hay archivos independientes del logotipo (SVG o PNG). El brand board oficial ya está disponible en HTML, así que este punto no bloquea el diseño. | P-44 | E9b |
| Media | A-02 | Si el administrador puede cambiar los pasos de una tarea que un estudiante ya empezó. | P-13 | — |
| Media | A-06 | Si el administrador puede ampliar la hora límite y si la tarea deja de estar vencida. | P-36 | — |
| Media | A-17 | Qué pasa cuando un segundo administrador intenta editar una tarea que ya se está editando. | P-13 | S-17 |
| Media | A-23 | Cuánto retraso es aceptable para que el tablero refleje los cambios. | P-31 | S-10 |
| Media | A-24 | Si hay que registrar la hora de cada paso del checklist. | P-18, P-32 | S-20 |
| Media | A-08 | Si hay conexión estable en todos los espacios y qué debe pasar sin conexión. | P-40, P-41 | S-12 |
| Media | A-03 | Cuánto dura la sesión antes de pedir de nuevo el inicio de sesión. | P-08 | — |
| Media | A-13 | En qué fechas se celebra el hackathon. | — | — |
| Baja | A-11 | Si se incluye el adjunto de fotografías como evidencia. | P-16 | C1 |
| Baja | A-21 | Si hay que medir el tiempo de retraso o descargar reportes. | P-38, P-47 | S-14c |
| Baja | A-10 (reformulado) | Si son aceptables las adaptaciones que agregan elementos a la marca o cambian sus reglas: colores de estado fuera de la paleta, morado para «terminada» y uso del lima y de la señal morada en el tablero. No incluye las decisiones que corresponden al equipo (SD-03). | P-45 | SD-02 |
| Baja | A-07 | Cuántos estudiantes y administradores usarán la plataforma. | P-42 | — |
| Baja | A-04 | Si la plataforma estará disponible solo durante el evento o también antes y después. | P-09 | — |

### Sin punto abierto en el PRD

Estos supuestos o preguntas siguen sin respuesta del cliente, pero el PRD v0.2 no los incluye en la lista A-01 a A-24. Hay que validarlos igual. La última columna los compara con los 24 puntos abiertos existentes.

| # | Qué hay que validar | Preguntas | Filas de la tabla | Relación con los puntos abiertos A-01 a A-24 |
|---|---|---|---|---|
| T-1 | Qué pasa con las tareas de un estudiante que deja el staff o deja de estar disponible. | P-02 | S-02 | **Relacionado con A-20.** Si el administrador puede cambiar los responsables, esa misma respuesta indica cómo se reasignan las tareas de quien no está disponible. No es un duplicado: A-20 no habla de la disponibilidad. |
| T-2 | Si un estudiante no disponible queda desactivado (sin acceso) o solo marcado. | P-04 | R11b | **Relacionado con T-1** (mismo caso: miembro del staff no disponible) y, de forma lejana, con A-01 (quién gestiona las cuentas). |
| T-3 | Cómo reciben los estudiantes sus credenciales iniciales. | P-05 | S-03 | **Sin punto abierto equivalente.** Comparte tema con T-4 y A-03 (acceso a la cuenta). |
| T-4 | Cómo se recupera una contraseña olvidada durante el evento. | P-07 | S-04 | **Sin punto abierto equivalente.** Comparte tema con T-3 y A-03. |
| T-5 | Si una tarea terminada se puede reabrir o editar. | P-26 | S-11 | **Relacionado con A-02** (editar una tarea ya empezada) y con A-19 (cómo se confirma la finalización). Afecta al texto del diálogo de confirmación del sistema de diseño (§8.4). |
| T-6 | Si el administrador debe aprobar las tareas terminadas. | P-27 | R28b | **Relacionado con A-19** (quién confirma la finalización) y con T-5. Los tres tratan del cierre de una tarea. |
| T-7 | Si se necesitan tareas recurrentes, el estado «bloqueada» o solicitudes de reasignación. | P-14, P-21, P-28 | S-14a, S-14b | **Se solapa en parte con A-09** (qué es indispensable y qué puede esperar) y es de la misma naturaleza que A-21 (funciones que el equipo propone dejar fuera). Además, P-21 se relaciona con A-20 (reasignación), y un estado «bloqueada» cambiaría el modelo de cinco estados (A-15). |
| T-8 | Si se necesitan adjuntos de referencia en las tareas y filtros del tablero por responsable o por lugar. | P-15, P-29, P-30 | S-13a, S-13b | **Se solapa en parte con A-09.** Los adjuntos de referencia (P-15) están **relacionados con A-11** (fotografías como evidencia): las dos funciones dependen de poder guardar archivos, y el cliente dijo que eso «depende de la base de datos» (P-16). |
| T-9 | Si se usa la hora local de Ecuador. | — | S-18 | **Relacionado con A-13** (fechas del hackathon) y con los cálculos de tiempo de A-05 y A-06. |
| T-10 | Si se descarta la mensajería interna. | — | S-16b | **Se solapa en parte con A-09** (alcance de la versión). |

**Duplicidades:** ninguno de los 10 temas está ya cubierto por un punto abierto. Las relaciones son parciales: la respuesta a un punto abierto puede ayudar a resolver un tema, pero no lo cierra por sí sola.

**Agrupaciones posibles** para la próxima revisión del PRD. Son solo una propuesta: todavía no se crean identificadores A-xx nuevos.

| Grupo | Temas adicionales | Puntos abiertos existentes |
|---|---|---|
| Acceso y credenciales | T-3, T-4 | A-03 |
| Staff no disponible y reasignación | T-1, T-2 | A-20 |
| Cierre y edición de una tarea | T-5, T-6 | A-19, A-02 |
| Archivos adjuntos | T-8 (P-15) | A-11 |
| Alcance de funciones opcionales | T-7, T-8 (P-29, P-30), T-10 | A-09, A-21 |
| Hora y calendario | T-9 | A-13 |
