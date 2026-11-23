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
