# 03. Requisitos funcionales

## 1. Propósito

Este documento define las funciones que debe ofrecer la plataforma de estadísticas de voleibol. Los requisitos se expresan mediante identificadores únicos y prioridades:

- **MUST:** requisito obligatorio para la primera versión.
- **SHOULD:** requisito importante, pero puede implementarse después del núcleo inicial.
- **COULD:** requisito opcional o de evolución futura.

## 2. Gestión de cuentas y acceso

### RF-001 — Registro de usuario
**Prioridad:** MUST  
El sistema debe permitir que una persona cree una cuenta mediante los datos requeridos por la plataforma.

### RF-002 — Inicio de sesión
**Prioridad:** MUST  
El sistema debe permitir iniciar sesión y acceder únicamente a las funciones autorizadas para el usuario.

### RF-003 — Cierre de sesión
**Prioridad:** MUST  
El sistema debe permitir cerrar la sesión activa.

### RF-004 — Gestión del perfil
**Prioridad:** MUST  
El usuario debe poder consultar y modificar la información editable de su perfil.

### RF-005 — Recuperación de acceso
**Prioridad:** SHOULD  
El sistema debería permitir recuperar el acceso a una cuenta mediante un mecanismo seguro.

### RF-006 — Gestión de roles
**Prioridad:** MUST  
El sistema debe distinguir, como mínimo, entre jugadores, técnicos, presidentes o administradores de club y administradores generales.

### RF-007 — Control de permisos
**Prioridad:** MUST  
El sistema debe autorizar las operaciones según el rol del usuario, su club, sus equipos y su relación con los partidos.

## 3. Gestión de clubes

### RF-008 — Crear club
**Prioridad:** MUST  
Un usuario autorizado debe poder crear un club indicando sus datos básicos.

### RF-009 — Consultar club
**Prioridad:** MUST  
El sistema debe permitir consultar la información general de un club y sus equipos asociados.

### RF-010 — Editar club
**Prioridad:** MUST  
Un usuario con permisos de administración del club debe poder modificar sus datos.

### RF-011 — Desactivar club
**Prioridad:** SHOULD  
El sistema debería permitir desactivar un club sin eliminar su historial deportivo.

### RF-012 — Gestionar administradores del club
**Prioridad:** MUST  
El sistema debe permitir asignar y retirar usuarios con permisos de administración dentro del club.

## 4. Gestión de equipos

### RF-013 — Crear equipo
**Prioridad:** MUST  
Un usuario autorizado debe poder crear equipos pertenecientes a un club.

### RF-014 — Clasificar equipo
**Prioridad:** MUST  
El equipo debe poder registrar información como categoría, rama, edad, nivel o temporada cuando corresponda.

### RF-015 — Consultar equipo
**Prioridad:** MUST  
El sistema debe permitir consultar los datos del equipo, sus jugadores, técnicos, partidos y estadísticas.

### RF-016 — Editar equipo
**Prioridad:** MUST  
Un usuario autorizado debe poder modificar los datos básicos del equipo.

### RF-017 — Desactivar equipo
**Prioridad:** SHOULD  
El sistema debería permitir desactivar un equipo conservando sus partidos, jugadores e históricos.

### RF-018 — Asignar técnicos
**Prioridad:** MUST  
El sistema debe permitir asociar uno o varios técnicos a un equipo.

### RF-019 — Gestionar pertenencia de técnicos
**Prioridad:** MUST  
El sistema debe permitir registrar el inicio y final de la relación de un técnico con un equipo o club.

## 5. Gestión de jugadores

### RF-020 — Registrar jugador
**Prioridad:** MUST  
El sistema debe permitir registrar un jugador con sus datos personales y deportivos básicos.

### RF-021 — Editar información del jugador
**Prioridad:** MUST  
Un usuario autorizado debe poder actualizar los datos editables del jugador.

### RF-022 — Asociar jugador a equipo
**Prioridad:** MUST  
El sistema debe permitir asociar un jugador a uno o varios equipos del mismo club, según las reglas de la plataforma.

### RF-023 — Registrar historial de pertenencias
**Prioridad:** MUST  
El sistema debe conservar el historial de equipos, clubes, categorías, posiciones y dorsales utilizados por un jugador.

### RF-024 — Finalizar pertenencia
**Prioridad:** MUST  
El sistema debe permitir registrar la fecha o condición de finalización de la pertenencia de un jugador a un equipo.

### RF-025 — Transferir jugador
**Prioridad:** SHOULD  
El sistema debería permitir registrar el cambio de un jugador entre equipos o clubes sin perder sus estadísticas históricas.

### RF-026 — Registrar posiciones
**Prioridad:** MUST  
El sistema debe permitir asociar una o varias posiciones a un jugador y conservar su historial de posiciones.

### RF-027 — Registrar dorsal
**Prioridad:** MUST  
El sistema debe permitir registrar el dorsal utilizado por el jugador en cada equipo o periodo.

### RF-028 — Consultar ficha deportiva
**Prioridad:** MUST  
El sistema debe permitir consultar la ficha deportiva, pertenencias, partidos y estadísticas de un jugador.

## 6. Gestión de partidos

### RF-029 — Crear partido
**Prioridad:** MUST  
Un técnico autorizado debe poder crear un partido entre su equipo y un equipo rival.

### RF-030 — Definir tipo de partido
**Prioridad:** MUST  
El sistema debe permitir clasificar el partido como oficial, amistoso, de entrenamiento u otro tipo configurado.

### RF-031 — Invitar equipo rival
**Prioridad:** MUST  
El creador del partido debe poder invitar al equipo rival mediante un mecanismo identificable dentro de la plataforma.

### RF-032 — Responder invitación
**Prioridad:** MUST  
El equipo invitado debe poder aceptar, rechazar o dejar pendiente la invitación.

### RF-033 — Gestionar estado del partido
**Prioridad:** MUST  
El sistema debe manejar estados como borrador, pendiente de aceptación, programado, en curso, finalizado, cancelado y archivado.

### RF-034 — Registrar datos generales del partido
**Prioridad:** MUST  
El sistema debe permitir registrar fecha, lugar, equipos participantes, temporada, tipo de partido y observaciones.

### RF-035 — Registrar sets
**Prioridad:** MUST  
El sistema debe permitir registrar los sets disputados y los puntos obtenidos por cada equipo en cada set.

### RF-036 — Calcular marcador final
**Prioridad:** MUST  
El sistema debe calcular el resultado final a partir de los sets y puntos registrados.

### RF-037 — Registrar marcador por equipo
**Prioridad:** MUST  
Cada equipo debe poder registrar su propia versión del marcador del partido.

### RF-038 — Comparar marcadores
**Prioridad:** MUST  
El sistema debe permitir comparar los marcadores registrados por ambos equipos.

### RF-039 — Resolver discrepancias
**Prioridad:** MUST  
El sistema debe permitir identificar y resolver discrepancias entre los marcadores registrados por los equipos.

### RF-040 — Cerrar partido
**Prioridad:** MUST  
Un partido debe poder marcarse como finalizado cuando se cumplan las condiciones definidas por la plataforma.

### RF-041 — Reabrir partido
**Prioridad:** SHOULD  
Un usuario con permisos suficientes debería poder reabrir un partido cerrado, dejando registro de la modificación.

## 7. Registro de estadísticas

### RF-042 — Registrar acción estadística
**Prioridad:** MUST  
El sistema debe permitir registrar una acción realizada por un jugador durante un partido.

### RF-043 — Registrar acción individual
**Prioridad:** MUST  
El usuario debe poder registrar acciones una por una cuando necesite precisión temporal o contextual.

### RF-044 — Registrar cantidades agrupadas
**Prioridad:** MUST  
El usuario debe poder registrar cantidades agrupadas de una acción cuando no sea necesario introducir cada evento individualmente.

### RF-045 — Asociar acción a jugador
**Prioridad:** MUST  
Cada registro estadístico debe poder asociarse al jugador responsable de la acción.

### RF-046 — Asociar acción a partido
**Prioridad:** MUST  
Cada registro estadístico debe estar asociado a un partido.

### RF-047 — Asociar acción a set
**Prioridad:** SHOULD  
El sistema debería permitir asociar una acción a un set específico.

### RF-048 — Seleccionar tipo de acción
**Prioridad:** MUST  
El sistema debe permitir seleccionar el tipo de acción, incluyendo ataques, defensas, saques, bloqueos, recepciones, colocaciones y asistencias.

### RF-049 — Seleccionar variante de acción
**Prioridad:** MUST  
El sistema debe permitir registrar variantes deportivas, como zona, dirección, tipo de saque, tipo de pase o tipo de colocación, cuando apliquen.

### RF-050 — Registrar resultado de acción
**Prioridad:** MUST  
El sistema debe permitir registrar el resultado de la acción, por ejemplo, efectiva, positiva, negativa, fallida, bloqueada, defendida o neutra, según el catálogo aprobado.

### RF-051 — Validar combinación de datos
**Prioridad:** MUST  
El sistema debe validar que el tipo de acción, la variante y el resultado sean compatibles.

### RF-052 — Editar estadística
**Prioridad:** MUST  
Un usuario autorizado debe poder modificar un registro estadístico propio o de su equipo.

### RF-053 — Eliminar lógicamente estadística
**Prioridad:** MUST  
El sistema debe permitir invalidar o eliminar lógicamente un registro sin destruir el historial de auditoría.

### RF-054 — Restringir edición por equipo
**Prioridad:** MUST  
En un partido compartido, cada técnico solo debe poder crear, editar o eliminar estadísticas de su propio equipo.

### RF-055 — Registrar autor y fecha
**Prioridad:** MUST  
El sistema debe conservar quién creó o modificó una estadística y cuándo lo hizo.

## 8. Cálculos y métricas

### RF-056 — Calcular conteos
**Prioridad:** MUST  
El sistema debe calcular los intentos, éxitos, fallos y demás conteos definidos para cada acción.

### RF-057 — Calcular efectividad
**Prioridad:** MUST  
El sistema debe calcular la efectividad de una acción según la fórmula y las categorías aprobadas para dicha acción.

### RF-058 — Calcular eficiencia
**Prioridad:** MUST  
El sistema debe calcular la eficiencia cuando el tipo de acción disponga de una fórmula válida.

### RF-059 — Calcular estadísticas por partido
**Prioridad:** MUST  
El sistema debe mostrar las estadísticas de jugadores y equipos dentro de un partido específico.

### RF-060 — Calcular estadísticas por set
**Prioridad:** SHOULD  
El sistema debería mostrar estadísticas desglosadas por set cuando existan registros asociados a sets.

### RF-061 — Calcular estadísticas acumuladas
**Prioridad:** MUST  
El sistema debe calcular estadísticas acumuladas a partir de los partidos y acciones válidos registrados.

### RF-062 — Filtrar estadísticas
**Prioridad:** MUST  
El usuario debe poder filtrar estadísticas por jugador, equipo, club, partido, temporada, fecha, tipo de acción, posición y tipo de partido cuando corresponda.

### RF-063 — Calcular métricas de equipo
**Prioridad:** MUST  
El sistema debe calcular indicadores colectivos a partir de las estadísticas de los jugadores del equipo.

### RF-064 — Calcular métricas de club
**Prioridad:** SHOULD  
El sistema debería calcular indicadores agregados del club a partir de sus equipos y partidos.

### RF-065 — Informar muestras insuficientes
**Prioridad:** MUST  
El sistema debe indicar cuando una métrica no tenga suficientes datos para interpretarse de forma confiable.

### RF-066 — Manejar datos incompletos
**Prioridad:** MUST  
El sistema debe distinguir entre cero registrado, dato no registrado y dato no aplicable.

## 9. Dashboards y reportes

### RF-067 — Dashboard del jugador
**Prioridad:** MUST  
El sistema debe mostrar un resumen del rendimiento individual, estadísticas acumuladas, estadísticas por partido y evolución histórica.

### RF-068 — Dashboard del equipo
**Prioridad:** MUST  
El sistema debe mostrar resultados, rendimiento colectivo, estadísticas por partido, evolución y jugadores asociados.

### RF-069 — Dashboard del club
**Prioridad:** SHOULD  
El sistema debería mostrar una visión agregada del rendimiento de sus equipos y jugadores.

### RF-070 — Comparar jugadores
**Prioridad:** SHOULD  
El sistema debería permitir comparar jugadores bajo filtros y métricas equivalentes.

### RF-071 — Comparar equipos
**Prioridad:** SHOULD  
El sistema debería permitir comparar equipos dentro de los límites de visibilidad autorizados.

### RF-072 — Generar carta del jugador
**Prioridad:** SHOULD  
El sistema debería generar una carta visual del jugador inspirada en tarjetas deportivas, con sus datos, posición, atributos y overall.

### RF-073 — Calcular overall
**Prioridad:** SHOULD  
El sistema debería calcular un overall mediante una fórmula documentada, configurable y basada en estadísticas válidas.

### RF-074 — Exportar reportes
**Prioridad:** SHOULD  
El sistema debería permitir exportar estadísticas y reportes en formatos como PDF, CSV o Excel.

## 10. Históricos e importación

### RF-075 — Conservar historial permanente
**Prioridad:** MUST  
El sistema debe conservar los registros históricos de jugadores, equipos, clubes, partidos y acciones, incluso cuando cambien sus relaciones actuales.

### RF-076 — Consultar históricos
**Prioridad:** MUST  
El usuario autorizado debe poder consultar el rendimiento histórico según los filtros disponibles.

### RF-077 — Importar datos desde Excel
**Prioridad:** SHOULD  
El sistema debería permitir importar registros provenientes de planillas de estadísticas existentes.

### RF-078 — Validar importación
**Prioridad:** MUST  
Toda importación debe validar columnas, jugadores, acciones, resultados, duplicados y errores antes de confirmar los datos.

### RF-079 — Mostrar resumen de importación
**Prioridad:** SHOULD  
El sistema debería mostrar registros importados, rechazados, advertencias y errores corregibles.

## 11. Administración y auditoría

### RF-080 — Gestionar catálogos
**Prioridad:** SHOULD  
Los usuarios autorizados deberían poder administrar catálogos de acciones, posiciones, resultados, categorías y tipos de partido.

### RF-081 — Gestionar permisos especiales
**Prioridad:** MUST  
El sistema debe permitir asignar permisos especiales a técnicos de club y rangos superiores cuando corresponda.

### RF-082 — Consultar actividad
**Prioridad:** SHOULD  
El sistema debería permitir consultar acciones relevantes realizadas por los usuarios.

### RF-083 — Auditar cambios sensibles
**Prioridad:** MUST  
El sistema debe registrar cambios relacionados con partidos, estadísticas, permisos, pertenencias y resultados oficiales.

## 12. Criterios generales de aceptación

- Cada requisito MUST debe poder verificarse mediante una prueba funcional.
- Las estadísticas deben calcularse desde los registros de partidos y acciones, no desde valores manuales independientes.
- Los cambios de equipo o club no deben eliminar el historial del jugador.
- En partidos compartidos, un equipo no debe poder modificar las estadísticas del rival.
- Las métricas deben mostrar claramente su fórmula, unidad y alcance.
- Los permisos deben aplicarse tanto en la interfaz como en la lógica de negocio.
