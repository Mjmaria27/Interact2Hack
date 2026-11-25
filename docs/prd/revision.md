# Revisión del PRD

**Equipo:** Carlos Aluisa, Maria Paula Baca
**Fecha:** 23 de noviembre de 2026
**Fuentes:** docs/fuentes/descripcion-proyecto.md y docs/cliente/preguntas.md

> **Nota añadida el 25 de noviembre de 2026.** Las secciones «Huecos», «Para presentar» y «Preguntas para el cliente» son el **registro histórico** de la revisión del borrador v0.1 del PRD, generado con IA (commit `12ef135`). De esa revisión salió el PRD v0.2 (commits `fa64fed` y `4739ba0`).
>
> Se conservan tal como se escribieron: sus frases, prioridades y conclusiones reflejan lo que se sabía en ese momento.
>
> La revisión vigente es la sección «[Revisión del PRD v0.3 — Avance 2](#revisión-del-prd-v03--avance-2)», al final de este documento.

## Huecos

| # | Sección | Frase exacta del PRD | Tipo (1–8) | Gravedad | Origen | Qué dicen las fuentes | Corrección |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | 6. Reglas de negocio — R30 | Una tarea vencida sigue visible y todavía se puede completar, también por otra persona. | 1 — Supuesto escrito como hecho | Alta | Equipo | P-35 confirma que una tarea vencida sigue visible y menciona que otra persona podría realizarla, pero no aclara si el responsable original puede continuar. La descripción oficial tampoco lo especifica. | Corregir R30: mantener como hecho que «una tarea vencida sigue visible» (P-35). La posibilidad de seguir ejecutándola después del vencimiento, por el responsable original o por otra persona, se documenta como supuesto propuesto S-19 [SUPUESTO]. P-35 solo dice que otra persona «podría realizarla»; no se presenta como confirmado que otro estudiante pueda hacerla sin que un administrador se la asigne (ver S-07). Punto abierto propuesto A-14: quién puede completar una tarea vencida. |
| 2 | 6. Reglas de negocio — R24 | Cada paso marcado guarda quién lo marcó y a qué hora. | 1 — Supuesto escrito como hecho | Media | Equipo | P-18 y P-32 indican que debe verse quién fue responsable de cada check. P-32 respalda además la hora de finalización de la tarea, porque el cliente respondió «Sí» a una pregunta que incluía «quién las realizó y a qué hora», pero no confirma expresamente que deba registrarse la hora de cada paso. | Corregir R24: mantener que cada paso guarda quién lo marcó (P-18, P-32). La hora en que se termina la tarea queda respaldada por P-32, porque el cliente respondió «Sí» a una pregunta que incluía «a qué hora». La hora de cada paso pasa a ser el supuesto propuesto S-20 [SUPUESTO]. Ajustar O2 y E7 en el mismo sentido. |
| 3 | 6. Reglas de negocio — R35 | Si una tarea cumple las condiciones de varios estados, se aplica esta precedencia: terminada, vencida, por vencer, en ejecución, sin asignar. **[SUPUESTO]** | 4 — Contradicción potencial | Alta | Equipo | P-23 establece el orden del tablero: vencidas, por vencer, en ejecución, sin asignar y terminadas. No define la precedencia para calcular estados. La regla podría causar confusión entre prioridad de visualización y prioridad de clasificación. | Aclarar R35 sin cambiar su contenido: la precedencia sirve solo para calcular el estado de cada tarea y sigue marcada como [SUPUESTO]. El orden en que el tablero muestra las tareas es el de R37 (P-23). Punto abierto propuesto A-15: cómo debe verse una tarea que cumple las condiciones de varios estados. |
| 4 | 4. Alcance — M11 | Cinco estados (vencida, por vencer, en ejecución, sin asignar y terminada) que se calculan solos **P-23**, **P-34**. | 2 — Regla vaga o incompleta | Alta | Equipo | P-23 confirma los cinco estados y P-34 que una tarea pasa a vencida al llegar su hora límite. P-24 no define cuándo comienza en ejecución y P-49 no define el intervalo para por vencer. | Aclarar M11: mantener los cinco estados (P-23) y el paso automático a vencida (P-34). Indicar que el criterio de «en ejecución» es el supuesto S-08 [SUPUESTO] y el de «por vencer» es S-09 [SUPUESTO]. Punto abierto propuesto A-16 para P-24; P-49 ya está cubierta por A-05. |
| 5 | 4. Alcance — M14 | Protecciones al editar: una tarea en ejecución no se puede borrar y dos administradores no pueden editar la misma tarea a la vez **P-13**. | 2 — Regla incompleta | Media | Equipo | P-13 menciona ambas restricciones, pero no especifica cómo se resuelve el conflicto entre administradores. El PRD propone un comportamiento en S-17, que sigue pendiente de validación. | Aclarar M14: mantener las dos restricciones de P-13 y añadir que la forma de impedir la edición simultánea es el mecanismo supuesto S-17 [SUPUESTO]. Punto abierto propuesto A-17: qué debe pasar cuando un segundo administrador intenta editar una tarea que ya se está editando. |
| 6 | 6. Reglas de negocio — R7 y R16 | Todos los administradores tienen los mismos privilegios, aunque cada uno se ocupe de un área distinta. / Las tareas no se clasifican por categoría ni por área. | 6 — Perfil o permiso incompleto | Alta | IA | P-01 dice que hay varios administradores, que cada uno «se encarga de un área (aulas, escenarios)» y que «en teoría» todos tienen los mismos privilegios. P-17 dice que no es relevante clasificar las tareas por áreas del hackathon. El PRD quita el «en teoría» y no aclara si un administrador gestiona todas las tareas o solo las de su área. | Corregir R7 para respetar P-01: cada administrador se encarga de un área (aulas, escenarios) y, «en teoría», todos tienen los mismos privilegios. Que todos los administradores vean y gestionen todas las tareas pasa a ser el supuesto propuesto S-21 [SUPUESTO]. R16 se mantiene (P-17) y no se agrega un campo de área. Punto abierto propuesto A-18: si cada administrador gestiona todas las tareas o solo las de su área. |
| 7 | 4. Alcance — Must have | Must have (indispensable para la primera versión) / Uso de la identidad visual del hackathon que entregará el cliente **P-43**, **P-44**. | 3 — Alcance inflado | Alta | IA | descripcion-proyecto.md fija el avance funcional para el 2 de diciembre. P-46 y P-48, que preguntaban qué es indispensable y qué puede esperar, no se respondieron, así que el equipo decidió los 16 ítems Must sin validarlos con el cliente. M16 depende de la carpeta de identidad visual que el cliente aún no ha enviado (P-43, P-44). | Aclarar en la sección 4 que la clasificación MoSCoW es una propuesta del equipo, supuesto propuesto S-22 [SUPUESTO], porque P-46 y P-48 no se respondieron. No se elimina ningún requisito. Como parte de S-22, proponer un subconjunto provisional para el 2 de diciembre (M1, M2, M5 a M9, M11 y M12), no confirmado por el cliente y pendiente de A-09. Indicar que M16 depende de recibir la carpeta de identidad visual (A-12). |
| 8 | 7. Épicas — E7, E4 y E2 | Las tareas terminadas quedan archivadas, no se pueden borrar ni editar, y se pueden consultar como constancia de quién hizo cada paso y a qué hora. / También permite cambiar los responsables de una tarea pendiente o vencida para que otra persona pueda hacerla. / El super admin tiene permisos adicionales sobre los administradores. | 1 — Supuesto escrito como hecho | Alta | IA | P-26 y P-20 no se abordaron en la reunión. P-03 solo confirma que las tareas terminadas no se pueden borrar. P-01 menciona «permisos mayores» del super admin sin decir cuáles son. En la sección 6 estas ideas están marcadas como supuestos (R29, R22 y R8), pero las épicas las repiten sin la marca [SUPUESTO]. | Corregir las épicas para identificar los supuestos. E7: las tareas terminadas no se pueden borrar (P-03); que tampoco se puedan editar es S-11 [SUPUESTO]; la hora de cada paso se ajusta según el hueco 2. E4: cambiar los responsables de una tarea pendiente o vencida es S-07 [SUPUESTO]. E2: el super admin tiene permisos mayores (P-01); cuáles son es S-01 [SUPUESTO]. |
| 9 | 6. Reglas de negocio — R26 | En una tarea con varios responsables, basta con que uno de ellos confirme la finalización. **[SUPUESTO]** | 5 — Pregunta abierta desaparecida | Alta | IA | P-18, P-19, P-20, P-38 y P-47 no se abordaron en la reunión. El PRD las convierte en los supuestos S-05, S-06, S-07 y S-14 o en el Won't W7, pero ninguna aparece en la lista de puntos abiertos A-01 a A-13 que hay que cerrar antes del Avance 3. | Mantener R21, R22 y R26 como supuestos (S-05, S-06 y S-07). Agregar los puntos abiertos propuestos A-19 (P-18 y P-19: checklist compartido y quién confirma la finalización), A-20 (P-20: cambio de responsables) y A-21 (P-38 y P-47: medición del retraso y reportes descargables). Aclarar en W7 que dejar esas funciones fuera es una propuesta del equipo (S-14), no una decisión del cliente. |
| 10 | 4. Alcance — M3 | Gestión de usuarios (ver, crear, editar y eliminar) por parte de los administradores **[DESC]**. | 6 — Perfil o permiso incompleto | Media | IA | descripcion-proyecto.md asigna la gestión de usuarios al administrador, y P-01 añade un super admin «con permisos mayores». M3 no es coherente con R8, donde solo el super admin gestiona a los administradores. Tampoco dice quién crea al super admin ni si un administrador puede eliminar a otro administrador. | Aclarar M3: los administradores gestionan usuarios (descripcion-proyecto.md), con la restricción provisional de que solo el super admin gestiona las cuentas de administrador (R8, S-01 [SUPUESTO]). Ampliar A-01 para preguntar también quién crea la cuenta del super admin y si un administrador puede eliminar a otro administrador. |
| 11 | 6. Reglas de negocio — R14 | Una tarea puede existir sin responsables; mientras no tenga ninguno, su estado es «sin asignar». | 4 — Contradicción resuelta en silencio | Media | IA | descripcion-proyecto.md, en «Como crear las tareas», incluye el responsable como dato de creación. P-23 incluye el estado «sin asignar». El PRD elige P-23 sin explicarlo y sin decir si el responsable es obligatorio al crear la tarea. | Aclarar R14: mantener el responsable como dato de creación de la tarea (descripcion-proyecto.md) y el estado «sin asignar» (P-23). Que se pueda guardar una tarea sin responsables pasa a ser el supuesto propuesto S-23 [SUPUESTO], deducido de que existe ese estado. Punto abierto propuesto A-22: si el responsable es obligatorio al crear la tarea. |
| 12 | 6. Reglas de negocio — R9 | Un estudiante solo ve las tareas que tiene asignadas. | 6 — Perfil o permiso incompleto | Media | IA | descripcion-proyecto.md dice que el estudiante ve su «lista de tareas asignadas». P-35 dice que la tarea vencida sigue visible y que «otra persona podría realizarla». El PRD no define cómo llega otro estudiante a una tarea vencida: si la toma por su cuenta o si un administrador se la reasigna. | Mantener R9 (descripcion-proyecto.md). Señalar que otro estudiante accede a una tarea vencida solo si un administrador se la reasigna, lo cual es el supuesto S-07 [SUPUESTO], pendiente de confirmar. Relacionar R9 con R22 y R30. No se agrega una lista de tareas libres. La pregunta queda cubierta por el punto abierto propuesto A-20. |
| 13 | 8. Supuestos — S-10 (relacionado con el Should S3) | El tablero se actualiza solo cada cierto tiempo, sin que el administrador recargue la página. | 2 — Regla vaga o incompleta | Media | IA | P-31: el cliente pidió la cuadrícula de tarjetas en la página de inicio, pero no precisó si se actualiza sola. La frecuencia está marcada como supuesto, pero «cada cierto tiempo» no tiene cifra y no se puede comprobar. De esa frecuencia depende que la alerta de por vencer (R38) y el paso a vencida (R34) se vean a tiempo. | Reescribir S-10 con una cifra comprobable: «[SUPUESTO] El tablero refleja los cambios en un máximo de 60 segundos, sin que el administrador recargue la página.» La cifra es una propuesta del equipo, no del cliente (P-31). Relacionar S-10 con R34 y R38. S3 se mantiene como Should. Punto abierto propuesto A-23: qué retraso es aceptable para el cliente. |

## Para presentar

Elegimos los tres huecos que más afectan a las funcionalidades principales de Interact2Hack: ejecutar una tarea, calcular su estado y atender las tareas vencidas.

### Hueco 9 — Tareas con varios responsables

- **Qué encontramos:** la descripción del proyecto dice que una tarea puede asignarse a uno o varios estudiantes, pero el cliente no respondió cómo trabajan juntos (P-18 y P-19) ni si un administrador puede cambiar los responsables (P-20). El primer borrador del PRD convirtió estas preguntas en supuestos (S-05, S-06 y S-07) y no las incluyó en la lista de puntos abiertos.
- **Por qué es importante:** define cómo funciona el checklist, que es el centro de la herramienta. Si cada estudiante tiene su propio checklist, o si todos deben confirmar la finalización, cambian la ejecución, el cálculo del estado y el historial.
- **Qué debe decidir el cliente:** si los responsables comparten un mismo checklist, si basta con que uno confirme la finalización y si un administrador puede cambiar los responsables de una tarea ya asignada.
- **Cómo quedó en el PRD revisado:** R21, R22 y R26 siguen marcadas como [SUPUESTO] (S-05, S-06 y S-07). Agregamos los puntos abiertos A-19 (P-18, P-19), A-20 (P-20) y A-21 (P-38, P-47). En W7 aclaramos que dejar fuera los reportes es una propuesta del equipo, no una decisión del cliente.

### Hueco 4 — Cómo se calculan los estados de una tarea

- **Qué encontramos:** M11 decía que los cinco estados «se calculan solos», pero el cliente no definió cuándo una tarea pasa a «en ejecución» (P-24) ni con cuánta anticipación está «por vencer» (P-49). Solo están confirmados los cinco estados (P-23) y el paso automático a vencida (P-34).
- **Por qué es importante:** el tablero de cumplimiento es la página de inicio del administrador y ordena las tareas por estado. Sin estos criterios no se puede construir ni probar el tablero ni la alerta de tareas próximas a vencer.
- **Qué debe decidir el cliente:** en qué momento una tarea pasa a «en ejecución» y cuántos minutos antes de su hora límite debe considerarse «por vencer».
- **Cómo quedó en el PRD revisado:** M11 conserva los cinco estados y el paso a vencida, y marca los criterios de «en ejecución» y «por vencer» como [SUPUESTO] S-08 y S-09 (30 minutos, cifra propuesta por el equipo). Agregamos el punto abierto A-16; el intervalo de «por vencer» ya estaba en A-05. La precedencia entre estados (hueco 3) queda en A-15.

### Hueco 1 — Qué pasa con una tarea vencida

- **Qué encontramos:** R30 afirmaba que una tarea vencida «todavía se puede completar, también por otra persona». P-35 solo confirma que la tarea vencida sigue visible y que otra persona «podría realizarla»; no dice quién puede completarla ni cómo. El mismo problema aparece en R9 (hueco 12): si un estudiante solo ve sus tareas, otro estudiante no tiene forma de encontrar la tarea vencida.
- **Por qué es importante:** durante el evento las tareas vencidas son las que más necesitan atención, y aparecen en primer lugar del tablero (P-34, P-37). Si no está claro quién puede terminarlas, el administrador ve el problema pero no sabe cómo resolverlo.
- **Qué debe decidir el cliente:** si el responsable original puede seguir completando una tarea vencida, y si otro estudiante la toma por su cuenta o debe asignársela un administrador.
- **Cómo quedó en el PRD revisado:** R30 conserva como hecho que la tarea vencida sigue visible (P-35). Que se pueda completar después del vencimiento queda como [SUPUESTO] S-19, y el acceso de otro estudiante mediante reasignación del administrador como [SUPUESTO] S-07 (R9, R22). Agregamos los puntos abiertos A-14 y A-20.

## Preguntas para el cliente

> **Lista histórica** (revisión del PRD v0.1, 23 y 24 de noviembre de 2026). La lista vigente, basada en el PRD v0.3, está en la sección «Preguntas pendientes para el cliente (vigente)» de la revisión del PRD v0.3.

Preguntas para cerrar antes del Avance 3 (2 de diciembre), tomadas de los puntos abiertos A-01 a A-24 del PRD revisado. Ninguna tiene respuesta todavía.

### Prioridad alta: necesarias para implementar los flujos principales

| # | Punto | Pregunta | Fuente |
| --- | --- | --- | --- |
| 1 | A-19 | Si una tarea tiene varios responsables, ¿comparten un mismo checklist? ¿Basta con que uno confirme la finalización? | P-18, P-19 |
| 2 | A-16 | ¿En qué momento pasa una tarea a «en ejecución»? | P-24 |
| 3 | A-05 | ¿Cuál es el intervalo exacto para considerar una tarea «por vencer»? | P-49 |
| 4 | A-15 | Si una tarea cumple las condiciones de varios estados (por ejemplo, vencida con pasos marcados o sin responsables), ¿cómo debe verse? | P-23 |
| 5 | A-14 | ¿Quién puede completar una tarea vencida: el responsable original, otra persona asignada por un administrador o ambos? | P-35 |
| 6 | A-20 | ¿Un administrador puede cambiar los responsables de una tarea ya asignada? Cuando una tarea vence, ¿otro estudiante la toma por su cuenta o se la asigna un administrador? | P-20, P-35 |
| 7 | A-22 | ¿El responsable es obligatorio al crear una tarea, o se puede guardar sin responsable y asignarla después? | [DESC], P-23 |
| 8 | A-18 | ¿Cada administrador gestiona todas las tareas o solo las de su área? | P-01, P-17 |
| 9 | A-01 | ¿Qué permisos concretos tiene el super admin que no tenga un administrador? ¿Quién crea la cuenta del super admin? ¿Un administrador puede eliminar a otro administrador? | P-01 |
| 10 | A-09 | ¿Cuáles son las tres funcionalidades indispensables y cuáles pueden esperar a una segunda versión? | P-46, P-48 |

### Prioridad media: importantes, pero pueden resolverse después

| # | Punto | Pregunta | Fuente |
| --- | --- | --- | --- |
| 11 | A-12 | ¿Cuándo nos envían la carpeta con la identidad visual del hackathon? | P-43, P-44 |
| 12 | A-02 | ¿Puede el administrador cambiar los pasos de una tarea que un estudiante ya empezó? | P-13 |
| 13 | A-06 | ¿Puede el administrador ampliar la hora límite de una tarea vencida y, si lo hace, la tarea deja de estar vencida? | P-36 |
| 14 | A-17 | ¿Qué debe pasar cuando un segundo administrador intenta editar una tarea que otro administrador ya está editando? | P-13 |
| 15 | A-23 | ¿Cuánto retraso es aceptable entre que un estudiante termina una tarea y el administrador lo ve en el tablero? | P-31 |
| 16 | A-24 | ¿Es necesario registrar la hora exacta de cada paso del checklist o basta con registrar quién lo marcó y la hora de finalización de la tarea? | P-18, P-32 |
| 17 | A-08 | ¿Hay conexión estable a internet en todos los espacios del evento? | P-40 |
| 18 | A-03 | ¿Cuánto debe durar la sesión antes de pedir de nuevo el inicio de sesión? | P-08 |
| 19 | A-13 | ¿En qué fechas se celebra el hackathon? | — |

### Prioridad baja: mejoras o detalles secundarios

| # | Punto | Pregunta | Fuente |
| --- | --- | --- | --- |
| 20 | A-11 | ¿Se confirma el adjunto de fotografías como evidencia? | P-16 |
| 21 | A-21 | ¿Necesitan medir el tiempo de retraso de las tareas o descargar reportes de cumplimiento? | P-38, P-47 |
| 22 | A-10 | ¿La interfaz debe seguir la estética tecnológica del hackathon o ser más sobria? | P-45 |
| 23 | A-07 | ¿Cuántos estudiantes y administradores usarán la plataforma? | P-42 |
| 24 | A-04 | ¿La plataforma estará disponible solo durante el evento o también antes y después? | P-09 |

---

## Revisión del PRD v0.3 — Avance 2

**Equipo:** Carlos Aluisa, Maria Paula Baca
**Fecha:** 25 de noviembre de 2026
**Documento revisado:** `docs/prd/PRD.md`, de la v0.2 a la v0.3.
**Fuentes:**
- `docs/fuentes/descripcion-proyecto.md` ([DESC]).
- `docs/cliente/preguntas.md`, con las respuestas P-xx, la sección «Consolidación de respuestas y supuestos» (commit `8b0bf91`) y la aclaración AC-01.
- `docs/diseno/sistema-de-diseno.md` v0.1.
- El plan de revisión elaborado con IA, que es un archivo de trabajo fuera del repositorio.

### Proceso seguido

1. **Consolidación del Avance 1** (`preguntas.md`). Cada supuesto quedó clasificado como confirmado, descartado o pendiente, y se registró la aclaración AC-01 sobre el brand board.
2. **Revisión del PRD v0.2 con IA.** La IA elaboró un plan con:
   - la comprobación de las nueve secciones académicas;
   - el estado de los 13 hallazgos históricos;
   - las correcciones documentales C-1 a C-11;
   - las contradicciones funcionales D-1 a D-12;
   - la reorganización de los puntos abiertos.
3. **Decisiones del equipo sobre ese plan.** C-1 a C-11 se aceptaron con precisiones, y D-1 a D-12 se aceptaron con o sin ajustes. Se rechazaron dos propuestas del plan: cerrar puntos abiertos y dejar R44 como opcional.
4. **Segunda versión del plan.** La IA incorporó esas decisiones y señaló seis contradicciones nuevas, H-1 a H-6, que el equipo resolvió.
5. **Implementación del PRD v0.3** con todo lo aprobado.
6. **Revisión externa del equipo (Prompt 02.3).** El equipo comparó el PRD v0.3 con las fuentes y detectó seis problemas (RX-1 a RX-6), que se corrigieron.
7. **Precisiones finales (Prompt 02.4).** Cuatro afirmaciones que la IA había señalado como insuficientemente respaldadas se convirtieron en supuestos o se corrigieron (PF-1 a PF-4).
8. **Sincronización de la consolidación (Prompt 02.5).** `preguntas.md` se actualizó según el PRD v0.3. Las 49 preguntas originales no cambiaron.

**Quién decide.** La IA propuso cambios y detectó problemas; las decisiones son del equipo. **Ninguna decisión de esta sección es una respuesta ni una aprobación del cliente.** Lo único nuevo que viene del cliente es AC-01, recibida a través del profesor.

### Estado de los 13 hallazgos históricos en el PRD v0.3

Las correcciones de los 13 hallazgos se aplicaron al pasar a la v0.2 y siguen vigentes en la v0.3. Esta revisión no las volvió a proponer.

| # | Estado | Observación sobre la v0.3 |
|---|---|---|
| 1 | Resuelto | R30 conserva la separación entre lo confirmado (P-35) y S-19. |
| 2 | Resuelto | R24 sin cambios de fondo. La hora de finalización está confirmada en la consolidación (R24b). |
| 3 | Resuelto en el texto | El problema de fondo (una tarea sin responsables que vence) se trató como D-2 y RX-1. |
| 4 | Resuelto en el texto | El problema de fondo (una tarea sin estado) se trató como D-1. |
| 5 | Resuelto | S-17 y A-17 se mantienen. |
| 6 | Resuelto | S-21 y A-18 se mantienen. |
| 7 | Resuelto | La dependencia de M16 respecto de A-12 quedó superada por AC-01 (C-1). |
| 8 | Resuelto | Las épicas siguen marcando los supuestos. |
| 9 | Resuelto en su alcance | El mismo tipo de problema en otras preguntas se trató con T-1 a T-10. |
| 10 | Resuelto | M3 se amplió con R44 y R45. |
| 11 | Resuelto | S-23 se precisó en RX-1. |
| 12 | Resuelto | R9 se precisó con S-33 (H-4). |
| 13 | Resuelto | S-10 se precisó en RX-3. |

### Registro de decisiones del equipo

**Valores de la columna «Origen»:**

| Origen | Significado |
|---|---|
| **IA** | La propuesta la hizo la IA. |
| **Equipo** | El problema lo detectó el equipo. |
| **IA y equipo** | La IA detectó el problema y el equipo eligió la solución. |

**Valores de la columna «Decisión»:**

| Decisión | Significado |
|---|---|
| **Aceptada** | Se aplicó tal como se propuso. |
| **Aceptada con ajustes** | Se aplicó con cambios del equipo. |
| **Rechazada** | No se aplicó. |

Los identificadores C-x (con guion) son correcciones del plan. No deben confundirse con los requisitos Could C1 a C5 del PRD.

#### Consolidación del Avance 1 (`preguntas.md`)

| ID | Hallazgo o problema | Propuesta original | Origen | Decisión | Justificación | Cambio aplicado en el PRD | Referencias | Validación con el cliente |
|---|---|---|---|---|---|---|---|---|
| CN-1 | El sistema de diseño (§0) trataba el brand board como referencia visual sin respaldo del cliente, y el PRD v0.2 decía que faltaba recibir la identidad visual. | Mantener la premisa del sistema de diseño v0.1. | Sistema de diseño v0.1 (autoría no registrada en esta revisión) | Rechazada | Según AC-01, el cliente proporcionó el brand board a través del profesor como guía. La premisa quedó descartada (SD-01). | M16, R41 y E9 citan AC-01; A-12 reformulado. | AC-01, SD-01, P-43, P-44 | AC-01 no aprueba las decisiones de interfaz del equipo. |
| CN-2 | Clasificación de R24b (hora de finalización). | Confirmado por el «Sí» de P-32. | IA | Aceptada con ajustes | Se confirmó solo tras comprobar que P-32 incluye la hora de forma explícita y que el «Sí» responde a la pregunta completa. Se citó la evidencia literal. | Ninguno: R24 ya lo recogía. | P-32, R24, S-20 | Confirmado (P-32). |
| CN-3 | Clasificación de W8 (sin notificaciones externas). | Confirmado, porque el cliente eligió la alerta visual en P-33. | IA | Aceptada con ajustes | Se añadió que la respuesta no aprueba alertas sonoras. | Ninguno: W8 y R38 ya decían «alerta visual». | P-33, W8, R38 | Confirmado (P-33). |
| CN-4 | Material de identidad visual pendiente (E9b). | Pendiente: saber si el brand board es toda la «carpeta» prometida. | IA | Aceptada con ajustes | El pendiente se limitó a los archivos independientes del logotipo; el brand board en HTML permite avanzar con el diseño. | A-12 reformulado; M16 y E9. | E9b, A-12, AC-01 | Pendiente (A-12). |
| CN-5 | Aprobación de las tareas por el administrador (R28b). | Pendiente, porque el cliente solo «no mencionó» la aprobación (P-27). | IA | Aceptada | No mencionar algo no equivale a confirmarlo ni a descartarlo. | R28 dividido en R28a y R28b; S-24 (ver C-2). | P-27, S-24 | Pendiente (A-19). |
| CN-6 | Adaptaciones visuales del equipo (SD-02). | Todas las decisiones [EQUIPO] del sistema de diseño quedan pendientes de validación. | IA | Aceptada con ajustes | No todas requieren aprobación individual. Se separó SD-02, que cambia la marca y necesita validación, de SD-03, que decide el equipo de diseño. | A-10 limitado a SD-02; E9. | SD-02, SD-03, A-10 | Solo SD-02 pendiente (A-10). |
| CN-7 | Fecha de la aclaración AC-01. | Dejarla «por completar». | IA | Aceptada con ajustes | No se inventa una fecha: se registró «Fecha exacta no registrada». | Ninguno. | AC-01 | No aplica. |

#### Correcciones documentales del plan (C-1 a C-11)

| ID | Hallazgo o problema | Propuesta original | Origen | Decisión | Justificación | Cambio aplicado en el PRD | Referencias | Validación con el cliente |
|---|---|---|---|---|---|---|---|---|
| C-1 | M16, R41 y E9 decían «que entregará el cliente». | Citar AC-01 y separar lo confirmado de lo pendiente. | IA | Aceptada | Aplica AC-01 sin presentarla como aprobación de la interfaz. | M16, R41, E9. | AC-01 | Pendiente: A-10 y A-12. |
| C-2 | R28 se presentaba como decisión del cliente. | Dividirlo en R28a (confirmado) y R28b (S-24). | IA | Aceptada con ajustes | Precisión del equipo: no presentar la ausencia de aprobación como requisito confirmado. | R28a, R28b, W4 y §5. | P-27, S-24 | Pendiente (A-19). |
| C-3 | A-10 y A-12 estaban desactualizados. | Reformularlos según AC-01 y SD-02. | IA | Aceptada | Reflejan la información recibida. | A-10 y A-12, con su texto original citado. | AC-01, SD-02 | Pendiente. |
| C-4 | El encabezado no citaba las aclaraciones AC-xx. | Pasar a v0.3 y ampliar las fuentes. | IA | Aceptada | Trazabilidad de las fuentes. | Encabezado. | AC-01 | No aplica. |
| C-5 | La precedencia de R35 no tenía identificador de supuesto. | Crear S-25. | IA | Aceptada con ajustes | Precisión del equipo: S-25 queda pendiente de validación. | R35, §8 y §9. | S-25, A-15 | Pendiente (A-15). |
| C-6 | Revisar W8 y R38. | Dejarlos sin cambios. | IA | Aceptada | Ya decían «alerta visual» y no mencionaban sonido. | Ninguno. | P-33 | Confirmado (P-33). |
| C-7 | Los criterios C1–C7 se confundían con los Could C1–C5. | Renombrar los criterios como CE. | IA | Aceptada con ajustes | Precisión del equipo: actualizar todas las referencias sin tocar los Could. | §3, S-15. En `preguntas.md` queda «S-15 / C7» por corregir. | CE1–CE8 | No aplica. |
| C-8 | §2 no indicaba qué no puede hacer cada perfil. | Añadir una columna «Qué no puede hacer». | IA | Aceptada con ajustes | Precisión del equipo: separar las restricciones confirmadas de las deducidas. | §2: tabla de restricciones por perfil con su tipo. | S-01, S-27, S-28, S-33 | Las restricciones supuestas quedan pendientes. |
| C-9 | S-16 mezclaba algo confirmado por [DESC] con un supuesto. | Dividirlo en S-16a y S-16b. | IA | Aceptada con ajustes | Precisión del equipo: conservar la trazabilidad histórica del identificador. | §5 y §8. | [DESC] | S-16a confirmado por [DESC]; S-16b pendiente. |
| C-10 | §8 no mostraba el estado de cada supuesto. | Añadir una columna «Estado». | IA | Aceptada con ajustes | Precisión del equipo: no duplicar el contenido de `preguntas.md`. | §8, columna breve. | `preguntas.md` | No aplica. |
| C-11 | [DESC] puede leerse como un cierre automático de la tarea; P-25 lo hace manual. | Añadir una nota sobre cuál prevalece. | IA | Aceptada con ajustes | Precisión del equipo: P-25 es la evidencia principal. | §1 y R25. | P-25, [DESC] | Confirmado (P-25). |

#### Decisiones funcionales del plan (D-1 a D-12)

| ID | Hallazgo o problema | Propuesta original | Origen | Decisión | Justificación | Cambio aplicado en el PRD | Referencias | Validación con el cliente |
|---|---|---|---|---|---|---|---|---|
| D-1 | Una tarea asignada, sin pasos marcados y lejos de vencer no encajaba en ningún estado. | Alternativa (a): «en ejecución» = tiene responsables y no está terminada, vencida ni por vencer. | IA | Aceptada | Conserva los cinco estados de P-23, sin un sexto estado. | S-08, R32. | P-23, P-24 | Pendiente (A-16, reformulado). |
| D-2 | Una tarea sin responsables que vence no mostraba que le faltan responsables. | Mantener la precedencia, mostrar «Sin responsables» en cualquier estado y cerrar A-15. | IA | Aceptada con ajustes | A-15 no se cierra: la precedencia queda como supuesto provisional. | S-25, R35, R39. | P-34, A-15 | Pendiente (A-15). |
| D-3 | R17 protegía por estado: una tarea empezada que pasaba a por vencer o vencida quedaba eliminable. | Proteger por actividad registrada (al menos un paso marcado). | IA | Aceptada con ajustes | Ajustes del equipo:<br>• la protección se mantiene aunque los pasos se desmarquen;<br>• no basta con contar los pasos marcados en ese momento;<br>• no se crea un registro de auditoría.<br>Después se ajustó otra vez con H-1 y RX-2. | R17, S-28, CE8. | P-13, P-03 | Pendiente (A-02). |
| D-4 | El umbral de «por vencer» no tenía límites precisos. | 30 minutos, igual para todas las tareas; a la hora límite exacta, «vencida». | IA | Aceptada | Elimina la ambigüedad entre los dos estados. | S-09, R33, R34. | P-49 | Pendiente (A-05). |
| D-5 | Permisos sin definir: si el administrador marca pasos, si se puede eliminar al último super admin y qué pasa con las tareas de un estudiante eliminado. | (i) Que el administrador no marque pasos, como algo confirmado por [DESC]; (ii) S-26; (iii) reasignar las tareas. | IA | Aceptada con ajustes | (i) pasa a supuesto (S-27), porque [DESC] no lo prohíbe de forma expresa (ver RJ-3). Se conservan los demás responsables de la tarea. | S-26 y R44, S-27 y R47, S-32 y R45. | P-01, P-03 | Pendiente (A-01, A-20). |
| D-6 | No estaba definido si un responsable puede desmarcar los pasos de otro. | Mantener S-05 y S-06, y que cualquier responsable pueda desmarcar. | IA | Aceptada con ajustes | Cada estudiante solo desmarca sus propios pasos y se conserva la autoría (ver RJ-4). | S-29, R46. | P-18 | Pendiente (A-19). |
| D-7 | Guardar y confirmar no estaban diferenciados. | Nueva regla R42. | IA | Aceptada | Se separa lo que viene de las fuentes de lo que decide el equipo. | R42, S-30. | [DESC], P-25 | S-30 pendiente (A-19). |
| D-8 | Aprobación de las tareas por el administrador. | Supuesto S-24, sin flujo de aprobación. | IA | Aceptada | Sin flujo de aprobación ni sexto estado. | S-24, W4. | P-27 | Pendiente (A-19). |
| D-9 | Completar tareas vencidas. | Mantener S-19 y S-07, y mostrar la hora límite y la hora de finalización. | IA | Aceptada | Sin métricas de retraso (W7). | R24, R30. | P-35 | Pendiente (A-14, A-20). |
| D-10 | El sistema de diseño prometía sincronizar sin conexión y ningún requisito cubría un guardado fallido. | Nueva regla R43; aviso de conexión como Could (C2); trabajo sin conexión fuera de alcance (W9). | IA | Aceptada con ajustes | Los cambios sin guardar se conservan solo mientras se siga en la pantalla, sin prometer persistencia. | R43, S-31. | P-40, P-41 | Pendiente (A-08). |
| D-11 | Criterios de éxito que no se podían comprobar. | CE5 con 60 s, CE6 con 360 px, CE7 como demostración y un CE8 nuevo. | IA | Aceptada con ajustes | Ajustes del equipo:<br>• 60 s es una cifra provisional;<br>• 360 px es una referencia de prueba;<br>• la adopción real pasa a ser el objetivo O5;<br>• CE8 se alinea con D-3.<br>Después se ajustó con RX-3 y RX-4. | §3. | S-10, S-15 | No aplica (criterios del equipo). |
| D-12 | El subconjunto del Avance 3 no incluía M10 ni M15. | Añadirlos. | IA | Aceptada | Es una propuesta provisional, no confirmada por el cliente ni por el profesor. | S-22, §4. | P-18, P-39 | Pendiente (A-09). |

#### Contradicciones al combinar las decisiones (H-1 a H-6)

| ID | Hallazgo o problema | Propuesta original | Origen | Decisión | Justificación | Cambio aplicado en el PRD | Referencias | Validación con el cliente |
|---|---|---|---|---|---|---|---|---|
| H-1 | Con D-1 y D-3, una tarea «en ejecución» sin actividad quedaba eliminable, en contra de la frase literal de P-13. | (a) Proteger la tarea si está en ejecución o si tiene actividad. | IA | Aceptada con ajustes | El equipo fijó la regla: no se elimina si tiene responsables, si tiene actividad registrada o si está terminada. Retirar responsables, reasignar o desmarcar no quita la protección. | R17, R19, R32, S-28, CE8, §2. | P-13 | Pendiente (A-02). |
| H-2 | Los pasos de un autor reasignado o eliminado no se podían desmarcar. | Aceptarlo y registrarlo en A-19. | IA | Aceptada | No se añaden permisos ni funciones de corrección sin validación. | R46, S-29, A-19. | P-18 | Pendiente (A-19). |
| H-3 | Dos responsables pueden guardar el mismo checklist casi a la vez. | El guardado de uno no deshace los cambios del otro. | IA | Aceptada | Se describe el comportamiento, sin fijar un mecanismo técnico. | R42, S-30. | P-18 | Pendiente (A-19). |
| H-4 | R9 («el estudiante solo ve sus tareas») solo se deduce de [DESC]. | (a) Marcarlo como deducido sin crear un supuesto. | IA | Aceptada con ajustes | Se revisaron las fuentes y ninguna lo respalda de forma explícita. Por eso el equipo pidió registrarlo como supuesto con identificador propio. | R9, S-33, §2. | [DESC] | Pendiente (A-20). |
| H-5 | Con la nueva definición de «en ejecución» habrá más puntos lima en el tablero. | Registrarlo en A-10 sin cambiar la identidad visual. | IA | Aceptada | La solución visual se definirá en las exploraciones de diseño. | A-10. | SD-02 | Pendiente (A-10). |
| H-6 | CE6 prueba con 360 px y el sistema de diseño exige 320 px. | CE6: «se prueba al menos con 360 px». | IA | Aceptada | 320 px queda como objetivo mínimo de diseño. La verificación de ambos tamaños se documentará en DESIGN.md. | CE6. | P-39 | No aplica. |

#### Propuestas de la IA rechazadas por el equipo

| ID | Hallazgo o problema | Propuesta original | Origen | Decisión | Justificación | Cambio aplicado en el PRD | Referencias | Validación con el cliente |
|---|---|---|---|---|---|---|---|---|
| RJ-1 | Puntos abiertos que ya tenían una solución provisional. | Plan v1: cerrar A-15 y tratar A-17, A-22, A-23, A-24 y parte de A-03 como «lo decide el equipo». | IA | Rechazada | Una solución provisional del equipo no cierra un punto sin evidencia del cliente. | Los 24 puntos siguen abiertos; los que tienen solución provisional figuran como «Provisional». | A-01 a A-24 | Pendientes. |
| RJ-2 | Protección de la última cuenta de super admin. | Plan v1: incluir R44 como regla «opcional». | IA | Rechazada | Una regla no puede quedar sin decidir. R44 se incorporó como regla en todas las tablas. | R44, S-26. | P-01 | Pendiente (A-01). |
| RJ-3 | Que el administrador no marque pasos ni confirme tareas. | D-5(i): tratarlo como algo confirmado por la fuente. | IA | Rechazada | [DESC] reparte las responsabilidades, pero no prohíbe esto de forma expresa. | S-27, como supuesto. | [DESC] | Pendiente (A-01). |
| RJ-4 | Desmarcar los pasos que marcó otro responsable. | D-6: cualquier responsable puede desmarcar cualquier paso. | IA | Rechazada | Pondría en riesgo la autoría que pide P-18. | S-29 y R46: cada uno desmarca solo los suyos. | P-18 | Pendiente (A-19). |
| RJ-5 | Eliminar una tarea asignada que no tiene actividad. | Consecuencia de D-3 tal como se propuso (proteger solo por actividad) y alternativa H-1(b). | IA | Rechazada | Contradecía la frase literal de P-13. Se adoptó la protección de R17 por responsables, actividad o tarea terminada. | R17. | P-13 | Pendiente (A-02). |

#### Revisión externa del equipo (Prompt 02.3)

| ID | Hallazgo o problema | Propuesta original | Origen | Decisión | Justificación | Cambio aplicado en el PRD | Referencias | Validación con el cliente |
|---|---|---|---|---|---|---|---|---|
| RX-1 | R14, R45, S-23 y S-32 decían que una tarea sin responsables pasa a «sin asignar», lo que contradice la precedencia de R35. | Recalcular siempre el estado con R35 y mostrar «Sin responsables» en cualquier estado. | Equipo | Aceptada | Era un error de interpretación (ver la tabla siguiente). No se crea un sexto estado. | R14, R22, R35, R45, S-23, S-32, E4. | S-25, R39 | Pendiente (A-15). |
| RX-2 | El PRD no decía cuándo empieza la actividad registrada. Además, el informe de la IA afirmó por error que las tareas vencidas y por vencer siempre tienen responsables. | La actividad empieza cuando se guarda correctamente, por primera vez, un paso marcado. Una tarea vencida o por vencer sin responsables ni actividad se puede eliminar. | Equipo | Aceptada | Un cambio que no se guardó no deja constancia. Se mantiene como supuesto. | R17, S-28, CE8. | P-13 | Pendiente (A-02). |
| RX-3 | CE5 exigía actualizar el tablero en 60 s, lo que convertía indirectamente S3 (Should) en indispensable. | Separar en CE5 la parte indispensable de la parte de S3. | Equipo | Aceptada | Se respeta la clasificación MoSCoW; S3 sigue siendo Should. | CE5, S-10. | S3, S-10 | Pendiente (A-23). |
| RX-4 | CE7 exigía hacer toda la demostración desde el celular, también para el administrador, y M3 no está en el subconjunto del Avance 3. | Permitir cuentas creadas previamente; los estudiantes, en celular; sin exigir el celular al administrador. | Equipo | Aceptada | Usar el celular no es una exigencia del cliente para el perfil de administrador. CE7 sigue siendo un criterio académico del equipo. | CE7. | P-39, S-22 | No aplica. |
| RX-5 | S-16a podía leerse como pendiente, y R13 presentaba como confirmado el mínimo de un paso. | Aclarar S-16a y crear S-34. | Equipo | Aceptada | El mínimo de un paso no fue validado por el cliente. | Introducción de §8, R13, S-34, A-22. | [DESC], P-10 | S-34 pendiente (A-22). |
| RX-6 | No estaba definido qué pasa si un estudiante guarda después de perder la asignación o después de que la tarea se confirmó. | La operación falla y no se muestra como completada; los pasos que marcó conservan su autoría. | Equipo | Aceptada | Es una consecuencia de supuestos que ya existían; no añade perfiles, estados ni funciones. | R43, R46, §2. | S-07, S-11, S-29, S-33 | Pendiente. |

#### Precisiones finales (Prompt 02.4)

| ID | Hallazgo o problema | Propuesta original | Origen | Decisión | Justificación | Cambio aplicado en el PRD | Referencias | Validación con el cliente |
|---|---|---|---|---|---|---|---|---|
| PF-1 | R13 presentaba como confirmado que el lugar o aula es obligatorio. | La IA lo señaló sin recomendar una solución. El equipo decidió mantenerlo obligatorio como supuesto. | IA y equipo | Aceptada | Es importante para la coordinación logística. [DESC] lo incluye como dato de la tarea, pero no como obligatorio. | R13, S-35, A-22, §9. | [DESC], P-10 | Pendiente (A-22). |
| PF-2 | §2 presentaba como confirmado que el super admin hereda todos los permisos del administrador. | Integrar esa interpretación en S-01. | IA y equipo | Aceptada | P-01 solo dice «permisos mayores y más acceso». | §2, S-01, A-01. | P-01 | Pendiente (A-01). |
| PF-3 | R37 presentaba como confirmado el orden de la más cercana a la más lejana. | Separar el orden confirmado de la interpretación del equipo. | IA y equipo | Aceptada | P-23 solo dice «por fecha de vencimiento». | R37, S-25, A-15, §9. | P-23 | Pendiente (A-15). |
| PF-4 | R2 decía «como mínimo», sin fuente. | Quitar la expresión. | IA y equipo | Aceptada | P-05 indica nombre y correo; no se añaden campos personales. | R2. | P-05 | Confirmado (P-05). |

#### Resumen

| Decisión | Cantidad | Detalle |
|---|---|---|
| Aceptada | 25 | CN-5; C-1, C-3, C-4 y C-6; D-1, D-4, D-7, D-8, D-9 y D-12; H-2, H-3, H-5 y H-6; RX-1 a RX-6; PF-1 a PF-4 |
| Aceptada con ajustes | 20 | CN-2, CN-3, CN-4, CN-6 y CN-7; C-2, C-5, C-7, C-8, C-9, C-10 y C-11; D-2, D-3, D-5, D-6, D-10 y D-11; H-1 y H-4 |
| Rechazada | 6 | CN-1 y RJ-1 a RJ-5 |
| **Total** | **51** | |

**Alternativas que no se cuentan como decisiones.** Durante el análisis, la propia IA descartó algunas alternativas al recomendar otra. Son: D-1(b) sexto estado, D-1(c), D-2(b), D-3(b), D-3(c), D-4(c) umbral configurable, D-6(b) checklist individual, D-8(b) flujo de aprobación, D-9(b), D-9(c) y H-2(b). El equipo aceptó la alternativa recomendada o una variante de ella, y no hubo una decisión aparte sobre las descartadas.

### Propuestas rechazadas o modificadas y errores de interpretación

Esta tabla distingue cuatro tipos de casos:

| Tipo | Significado |
|---|---|
| **Propuesta rechazada** | La IA la planteó y el equipo no la aplicó. |
| **Propuesta modificada** | Se aplicó con cambios. |
| **Error de interpretación** | Una afirmación del PRD o de un informe que no estaba respaldada. |
| **Premisa descartada** | Una información nueva dejó sin efecto la premisa. |

| Propuesta o afirmación | Tipo | Qué problema generaba | Por qué se cambió | Registro |
|---|---|---|---|---|
| Cerrar puntos abiertos por decisión del equipo | Propuesta rechazada (IA, plan v1) | Haría pasar decisiones provisionales del equipo por respuestas del cliente y quitaría preguntas de la lista. | Ningún punto se cierra sin evidencia del cliente. | RJ-1 |
| Dejar como opcional la protección de la última cuenta de super admin | Propuesta rechazada (IA, plan v1) | Dejaba una regla de negocio sin decidir y fuera de las verificaciones. | Se incorporó como R44 (S-26). | RJ-2 |
| Permitir eliminar una tarea asignada sin actividad | Propuesta rechazada (consecuencia de D-3 y de H-1(b)) | Permitía borrar una tarea «en ejecución», en contra de la frase literal de P-13. | Se adoptó la protección de R17. | RJ-5 |
| Considerar que una tarea sin responsables siempre está «sin asignar» | Error de interpretación | Contradecía la precedencia de R35: una tarea vencida o por vencer perdería ese estado al quedarse sin responsables. | El estado se recalcula siempre con R35. El error venía de la v0.2 (R14, S-23) y la IA lo extendió a R45 y S-32 en la v0.3. | RX-1 |
| Exigir la actualización automática en 60 s como condición indispensable | Propuesta modificada (IA, D-11) | Convertía indirectamente S3 (Should) en Must. | CE5 se separó en una parte indispensable y una parte de S3. | RX-3 |
| Exigir que el administrador haga toda la demostración desde el celular | Propuesta modificada (IA, D-11) | Atribuía al perfil de administrador una exigencia que el cliente no planteó, y no tenía en cuenta que M3 está fuera del subconjunto. | Los estudiantes usan el celular; el administrador, celular o computadora; se permiten cuentas creadas previamente. | RX-4 |
| Presentar como confirmada la ausencia de aprobación del administrador | Error de interpretación (PRD v0.2, R28 con tipo «Cliente») | Convertía en decisión del cliente algo que el cliente solo no mencionó. | Se corrigió y se registró como supuesto S-24 (R28b). | CN-5, C-2 |
| Considerar el brand board solo como una referencia visual sin respaldo del cliente | Premisa descartada (sistema de diseño v0.1) | Ignoraba que el cliente proporcionó el brand board como guía. | Se descartó mediante AC-01, que no aprueba las decisiones de interfaz del equipo. | CN-1 |
| Tratar como confirmada la restricción de que el administrador no marca pasos | Propuesta rechazada (IA, D-5(i)) | Presentaba una deducción como si estuviera respaldada por la fuente. | Se registró como supuesto S-27. | RJ-3 |
| Permitir que cualquier responsable desmarque los pasos de otro | Propuesta rechazada (IA, D-6) | Ponía en riesgo la autoría que pide P-18. | Cada estudiante solo desmarca sus propios pasos (S-29). | RJ-4 |
| «Las tareas vencidas y por vencer siempre tienen responsables» | Error de interpretación (informe de la IA en la implementación de la v0.3) | Daba por cierta una justificación falsa de la coherencia de R17. | Se corrigió y se comprobó con el modelo lógico (ver «Evidencia de verificación»). | RX-2 |
| El lugar obligatorio, la herencia de permisos del super admin, el orden de la más cercana a la más lejana y «como mínimo» | Errores de interpretación (afirmaciones sin respaldo suficiente) | Presentaban decisiones del equipo como si fueran confirmadas. | Se convirtieron en supuestos (S-35, S-01, S-25) o se eliminaron. | PF-1 a PF-4 |

Ninguna de estas decisiones se atribuye al cliente.

### Preguntas pendientes para el cliente (vigente)

Esta lista sustituye a la lista histórica de la sección «Preguntas para el cliente». Usa las formulaciones y prioridades del PRD v0.3 (§8).

- **Todas las preguntas siguen sin respuesta del cliente.**
- La columna «Solución provisional del equipo» indica qué supuesto se aplica mientras tanto. Un supuesto no cierra la pregunta.
- Los temas T-1 a T-10 de la consolidación están dentro de sus puntos abiertos.

#### Prioridad alta

| # | Punto | Pregunta vigente | Fuente | Solución provisional del equipo |
|---|---|---|---|---|
| 1 | A-01 | ¿Qué permisos concretos tiene el super admin que no tenga un administrador? ¿Tiene todos los permisos del administrador? ¿Quién crea su cuenta? ¿Un administrador puede eliminar a otro? ¿Puede un administrador o el super admin marcar pasos o confirmar tareas en nombre de un estudiante? ¿Se acepta que siempre exista al menos un super admin? | P-01 | S-01, S-26, S-27 |
| 2 | A-05 | ¿Cuál es el intervalo exacto para considerar una tarea «por vencer»? | P-49 | S-09 (30 min) |
| 3 | A-09 | ¿Cuáles son las tres funcionalidades indispensables y cuáles pueden esperar a una segunda versión? **(T-7)** ¿Se necesitan tareas recurrentes, el estado «bloqueada» o solicitudes de reasignación? **(T-8)** ¿Se necesitan filtros por responsable o por lugar? **(T-10)** ¿Se descarta la mensajería interna? | P-46, P-48, P-14, P-21, P-28, P-29, P-30 | S-22, S-13, S-14, S-16b |
| 4 | A-14 | ¿Quién puede completar una tarea vencida: el responsable original, otra persona asignada por un administrador o ambos? | P-35 | S-19 |
| 5 | A-16 | ¿«En ejecución» significa que la tarea tiene responsables y no está terminada, vencida ni por vencer, aunque no tenga pasos marcados, o solo que ya tiene pasos marcados? | P-24 | S-08 |
| 6 | A-18 | ¿Cada administrador gestiona todas las tareas o solo las de su área? | P-01, P-17 | S-21 |
| 7 | A-19 | Si una tarea tiene varios responsables, ¿comparten un mismo checklist? ¿Basta con que uno confirme? ¿Cada estudiante solo desmarca sus propios pasos? Si un paso se marcó por error y su autor ya no está disponible, ¿quién puede corregirlo? ¿Cuando un responsable guarda, se conservan los cambios que otro hizo en pasos diferentes? **(T-5)** ¿Se puede reabrir o editar una tarea terminada? **(T-6)** ¿El administrador debe aprobar las tareas terminadas? | P-18, P-19, P-26, P-27 | S-05, S-06, S-29, S-30, S-11, S-24 |
| 8 | A-20 | ¿Un administrador puede cambiar los responsables de una tarea ya asignada? Cuando una tarea vence, ¿otro estudiante la toma por su cuenta o se la asigna un administrador? **(T-1)** ¿Qué pasa con las tareas de un estudiante que deja de estar disponible? **(T-2)** ¿Un estudiante no disponible queda desactivado o solo marcado? ¿Qué pasa con las tareas no terminadas de un estudiante eliminado? ¿El estudiante solo ve sus tareas asignadas? | P-20, P-35, P-02, P-04 | S-07, S-02, S-32, S-33 |

#### Prioridad media

| # | Punto | Pregunta vigente | Fuente | Solución provisional del equipo |
|---|---|---|---|---|
| 9 | A-02 | ¿Puede el administrador cambiar los pasos de una tarea que un estudiante ya empezó? ¿Se aplica «una tarea en ejecución no se puede borrar» como propone el equipo, es decir, sin poder borrar tareas con responsables ni tareas con actividad registrada? | P-13 | S-28 |
| 10 | A-06 | ¿Puede el administrador ampliar la hora límite de una tarea vencida y, si lo hace, la tarea deja de estar vencida? ¿Se puede crear una tarea con una hora límite ya pasada? | P-36 | Ninguna |
| 11 | A-08 | ¿Hay conexión estable a internet en todos los espacios del evento? | P-40, P-41 | S-12, S-31 |
| 12 | A-12 | El brand board oficial «Señal Neón» **ya se recibió** (AC-01) y permite avanzar con el diseño. Solo quedan pendientes los archivos independientes del logotipo: ¿pueden enviarlos en SVG o PNG? | P-43, P-44 | Ninguna (se usa el logotipo incluido en el brand board) |
| 13 | A-13 | ¿En qué fechas se celebra el hackathon? **(T-9)** ¿Se usa la hora local de Ecuador? | — | S-18 |
| 14 | A-15 | Si una tarea cumple las condiciones de varios estados, ¿cómo debe verse? ¿Las tareas por vencer se ordenan de la hora límite más cercana a la más lejana? | P-23 | S-25 |
| 15 | A-22 | ¿El responsable es obligatorio al crear una tarea, o se puede guardar sin responsable y asignarla después? ¿El checklist debe tener al menos un paso? ¿El lugar o aula es obligatorio? | [DESC], P-23, P-10 | S-23, S-34, S-35 |

#### Prioridad baja

| # | Punto | Pregunta vigente | Fuente | Solución provisional del equipo |
|---|---|---|---|---|
| 16 | A-03 | ¿Cuánto debe durar la sesión antes de pedir de nuevo el inicio de sesión? **(T-3)** ¿Cómo reciben los estudiantes sus credenciales iniciales? **(T-4)** ¿Cómo se recupera una contraseña olvidada durante el evento? | P-08, P-05, P-07 | S-03 y S-04; ninguna para la duración de la sesión |
| 17 | A-04 | ¿La plataforma estará disponible solo durante el evento o también antes y después? | P-09 | Ninguna |
| 18 | A-07 | ¿Cuántos estudiantes y administradores usarán la plataforma? | P-42 | Ninguna |
| 19 | A-10 | ¿Son aceptables las adaptaciones de interfaz que agregan elementos a la marca o cambian sus reglas (colores de estado fuera de la paleta, morado para «terminada», uso del lima y de la señal morada en el tablero), incluida la posible tensión por el uso del lima en las tareas «en ejecución»? | P-45 | Ninguna; la solución visual se definirá en las exploraciones de diseño |
| 20 | A-11 | ¿Se confirma el adjunto de fotografías como evidencia? **(T-8)** ¿Se necesitan archivos o imágenes de referencia dentro de la tarea? | P-16, P-15 | S-13 |
| 21 | A-17 | ¿Qué debe pasar cuando un segundo administrador intenta editar una tarea que otro ya está editando? | P-13 | S-17 |
| 22 | A-21 | ¿Necesitan medir el tiempo de retraso de las tareas o descargar reportes de cumplimiento? | P-38, P-47 | S-14 |
| 23 | A-23 | ¿Cuánto retraso es aceptable entre que un estudiante termina una tarea y el administrador lo ve en el tablero? | P-31 | S-10 (60 s, parte de S3) |
| 24 | A-24 | ¿Es necesario registrar la hora exacta de cada paso del checklist? | P-18, P-32 | S-20 |

**Resumen:**
- **Por prioridad:** 8 de prioridad alta, 7 de prioridad media y 9 de prioridad baja, 24 en total.
- **Por solución provisional:**
  - 19 tienen una solución provisional del equipo.
  - 4 no tienen ninguna: A-04, A-06, A-07 y A-10.
  - A-12 tampoco tiene un supuesto: mientras tanto se usa el logotipo incluido en el brand board.
- **Ninguna pregunta está cerrada.**

### Evidencia de verificación

**Qué se verificó y qué no.** Las comprobaciones se hicieron sobre el texto de `docs/prd/PRD.md` y sobre un modelo de sus reglas de negocio de estado (R35) y eliminación (R17).

- **No** prueban una aplicación implementada, porque todavía no existe.
- **No** son una validación del cliente.
- Se ejecutaron con dos scripts de comprobación (`verificar_prd.mjs` y `verificar_logica.mjs`). Son archivos de trabajo fuera del repositorio, ejecutados con Node.js.

**Qué cubre cada verificación:**

- **Estructural:**
  - las nueve secciones del PRD;
  - cada regla con su fila de trazabilidad, su épica y su requisito;
  - identificadores sin duplicar y sin referencias rotas;
  - A-01 a A-24 y T-1 a T-10;
  - criterios CE1 a CE8 y la referencia a AC-01;
  - cinco estados y ninguna promesa de sincronización sin conexión.
- **Lógica:**
  - comprobaciones del texto sobre asignación y estados, eliminación, CE5 y MoSCoW, CE7, supuestos, y permisos y guardado;
  - 17 escenarios del modelo de estado y eliminación;
  - un recorrido de 72 combinaciones de estas variables: terminada, tiempo relativo a la hora límite, número de responsables y actividad registrada.

**Resultados:**

| Momento | Estructurales | Lógicas | Escenarios | Combinaciones |
|---|---|---|---|---|
| Prompt 02.3 (después de RX-1 a RX-6) | 29 de 29 | 48 de 48 | 17 de 17 | 72, sin fallos |
| Prompt 02.4 (después de PF-1 a PF-4) | 29 de 29 | 53 de 53 | 17 de 17 | 72, sin fallos |

Las 5 comprobaciones lógicas añadidas en el Prompt 02.4 verifican las precisiones PF-1 a PF-4: R2 sin «como mínimo», S-35 en R13 y A-22, la herencia de permisos como parte de S-01 y el orden de R37 como S-25.

**Prompt 02.5: verificación de `preguntas.md`** (comprobación del documento): **41 de 41** comprobaciones. Incluye:
- la conservación de las 49 preguntas, comparadas por contenido con los commits `3549219` y `8b0bf91`;
- la coincidencia de los 36 supuestos con el PRD v0.3.

**Prompt 02.6: auditoría cruzada de los tres documentos** (comprobaciones del documento y del modelo lógico).
- **Resultados de los scripts:** 29 de 29 estructurales, 53 de 53 lógicas y 41 de 41 de `preguntas.md`.
- **Coherencia entre documentos:**
  - Las prioridades de los 24 puntos abiertos coinciden entre el PRD y la lista vigente de esta revisión.
  - El historial de esta revisión es idéntico, por contenido, al del commit `4739ba0`, descontando las dos notas añadidas.
  - Las diferencias detectadas son justificadas: A-10 cita S-08 solo como contexto, y 11 vínculos entre supuestos y puntos abiertos están en la trazabilidad del PRD.
- **Hallazgos:** ninguno bloqueante y tres menores (M-1 a M-3), corregidos en el Prompt 02.6.1:
  - M-1: estas referencias pendientes;
  - M-2: la relación entre S-30 y A-19;
  - M-3: esta evidencia.

Ninguna de estas verificaciones prueba una aplicación funcional ni es una validación del cliente.

### Registros que no se pudieron recuperar

Quedan **pendientes de confirmación por el equipo**:

- **Quién escribió la premisa de CN-1.** No consta en esta revisión quién redactó la premisa del sistema de diseño v0.1 según la cual el brand board era solo una referencia visual.
- **Qué significa «ajuste aprobado».** No consta quién aprobó el ajuste marcado así en el sistema de diseño (§10).
- **La fecha exacta de AC-01.** Se mantiene como «Fecha exacta no registrada».
- **Las deliberaciones del equipo sobre los 13 hallazgos históricos.** Esta revisión solo comprueba que sus correcciones están aplicadas en el PRD.

### Referencias pendientes en otros documentos

Se corregirán en un paso posterior, con autorización del equipo:

- **`docs/cliente/preguntas.md`: completado en el Prompt 02.5 (25 de noviembre de 2026).**
  - *Pendiente al cerrar el Prompt 02.4 (registro histórico):* «S-15 / C7» debía pasar a «S-15 / CE7»; la fila «S-08 / R32» describía la definición anterior de «en ejecución»; faltaban los supuestos S-33 a S-35.
  - *Resuelto en el Prompt 02.5:*
    - La fila S-15 se identifica ahora con el objetivo O5, y una nota explica que el antiguo criterio es CE7.
    - S-08, S-01, S-09, S-10, S-22 y S-23 se actualizaron.
    - Se añadió el «Índice de supuestos del PRD v0.3», con S-01 a S-35.
- **`docs/diseno/sistema-de-diseno.md`:**
  - el texto sobre la conexión (§10.4) contradice R43 y W9;
  - la definición de «en ejecución» debe pasar a S-08;
  - falta mostrar «Sin responsables» en cualquier estado;
  - faltan guardar y confirmar (R42), el error y reintento (R43) y el botón de eliminar deshabilitado según R17;
  - faltan S-34 y S-35 en las validaciones (§5.4);
  - el Anexo B no incluye los supuestos nuevos;
  - el encabezado todavía cita «PRD v0.2».