# Modelo de datos

## Propósito

Definir las entidades y relaciones necesarias para conservar el historial de clubes, equipos, jugadores, partidos, sets y estadísticas.

## Principios

- Cada entidad tendrá un identificador único.
- Los nombres no serán identificadores permanentes.
- Las acciones registradas serán la fuente de verdad estadística.
- Los totales, porcentajes y overalls se calcularán desde las acciones.
- Los cambios de equipo o club no eliminarán el historial del jugador.
- Se preferirá la eliminación lógica para entidades con historial.
- Cada modificación importante deberá conservar quién la realizó.

## Entidades principales

### Usuario

Cuenta de acceso a la plataforma.

Campos mínimos:

- `id`
- `nombre`
- `apellidos`
- `correo`
- `estado`
- `fecha_creacion`
- `fecha_actualizacion`

### Rol

Roles iniciales:

- Jugador.
- Técnico.
- Administrador de club.
- Administrador de plataforma.

Los roles no deben confundirse con las posiciones deportivas.

### Club

Campos mínimos:

- `id`
- `nombre`
- `nombre_corto`
- `ciudad`
- `pais`
- `logo`
- `estado`
- `fecha_creacion`
- `fecha_actualizacion`

Un club puede tener múltiples equipos.

### Equipo

Campos mínimos:

- `id`
- `club_id`
- `nombre`
- `categoria`
- `rama`
- `temporada_id`, opcional
- `estado`
- `fecha_creacion`
- `fecha_actualizacion`

### Jugador

Representa a una persona independientemente de sus equipos.

Campos mínimos:

- `id`
- `usuario_id`, opcional
- `nombre`
- `apellidos`
- `fecha_nacimiento`, opcional
- `foto`, opcional
- `estado`

### Posición deportiva

Catálogo inicial:

- Líbero.
- Colocador.
- Banda.
- Central.
- Opuesto.

Se deben normalizar variantes como `OPUESTA` y `OPUESTO`.

### Pertenencia de jugador a equipo

Permite conservar el historial deportivo.

Campos mínimos:

- `id`
- `jugador_id`
- `equipo_id`
- `numero_camiseta`
- `posicion_principal_id`
- `fecha_inicio`
- `fecha_fin`, opcional
- `estado`
- `observaciones`

Un jugador puede pertenecer a varios equipos y cambiar de camiseta o posición.

### Pertenencia de técnico a equipo

Campos mínimos:

- `id`
- `usuario_id`
- `equipo_id`
- `tipo_responsabilidad`
- `fecha_inicio`
- `fecha_fin`
- `estado`

### Partido

Campos mínimos:

- `id`
- `tipo_partido`
- `fecha_hora`
- `ubicacion`
- `estado`
- `creado_por`
- `observaciones`
- `fecha_creacion`
- `fecha_actualizacion`

Estados iniciales: borrador, pendiente, confirmado, en registro, finalizado, cancelado y archivado.

### Participante de partido

Relaciona cada partido con sus equipos.

Campos mínimos:

- `id`
- `partido_id`
- `equipo_id`
- `rol`
- `es_equipo_creador`
- `estado_invitacion`
- `marcador_confirmado`
- `usuario_responsable`

Cada equipo solo puede editar sus propios registros estadísticos.

### Invitación a partido

Campos mínimos:

- `id`
- `partido_id`
- `equipo_invitado_id`
- `enviada_por`
- `estado`
- `fecha_envio`
- `fecha_respuesta`
- `mensaje`

### Set

Campos mínimos:

- `id`
- `partido_id`
- `numero`
- `puntos_equipo_a`
- `puntos_equipo_b`
- `ganador_equipo_id`
- `estado`

El número de set será único dentro del partido.

### Participación de jugador en partido

Campos mínimos:

- `id`
- `partido_id`
- `equipo_id`
- `jugador_id`
- `numero_camiseta_en_partido`
- `posicion_en_partido`
- `participo`
- `observaciones`

### Acción estadística

Campos mínimos:

- `id`
- `partido_id`
- `set_id`, opcional hasta tomar una decisión definitiva
- `equipo_id`
- `jugador_id`
- `tipo_accion_id`
- `variante_accion_id`
- `resultado_accion_id`
- `cantidad`
- `registrada_por`
- `fecha_registro`
- `fecha_actualizacion`
- `observaciones`

`cantidad` será un entero positivo. El sistema permitirá registrar una acción individual o varias acciones agrupadas.

### Catálogos estadísticos

- Tipo de acción.
- Variante de acción.
- Resultado de acción.
- Posición deportiva.
- Tipo de partido.
- Estado de partido.

### Métrica calculada

Las métricas podrán calcularse bajo demanda o almacenarse como caché reconstruible. Nunca serán la única fuente de verdad.

## Relaciones principales

```text
Club 1:N Equipo
Equipo N:N Jugador mediante PertenenciaEquipo
Usuario N:N Equipo mediante PertenenciaTecnico
Partido 1:N ParticipantePartido
Partido 1:N Set
Partido 1:N Acción
Set 1:N Acción
Jugador 1:N Acción
Equipo 1:N Acción
TipoAcción 1:N VarianteAcción
TipoAcción 1:N ResultadoAcción
Partido 1:N Invitación
Partido 1:N ParticipaciónJugador
```

## Reglas de integridad

- Una acción solo puede pertenecer a un partido válido.
- El equipo de la acción debe participar en el partido.
- El jugador debe estar asociado al equipo o autorizado para ese partido.
- No se eliminarán físicamente jugadores, equipos o partidos con historial.
- Los catálogos tendrán identificadores estables.
- Cambiar el nombre de un club o equipo no alterará el historial.
- Se conservarán auditorías de cambios relevantes.

## Pendientes

- Definir si el set será obligatorio.
- Definir si apoyo al bloqueo será acción independiente.
- Definir si habrá temporadas en la primera versión.
- Definir si el jugador necesitará cuenta obligatoria.
- Definir si se conservarán versiones anteriores de estadísticas editadas.
