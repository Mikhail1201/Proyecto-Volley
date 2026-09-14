# Registro de partidos

## 1. Objetivo

Definir cómo se crean, registran, editan y conservan los partidos de volleyball dentro de la plataforma.

## 2. Creación de un partido

El técnico de un equipo podrá crear un partido indicando:

- Equipo al que representa.
- Equipo contrario.
- Fecha.
- Tipo de partido.
- Información adicional que se defina posteriormente.

El técnico podrá invitar al equipo contrario para que participe en el registro compartido del partido.

## 3. Partidos compartidos

Un partido podrá ser compartido entre dos equipos.

Cada equipo podrá registrar sus propias estadísticas y datos del partido.

La aplicación deberá garantizar que:

- El equipo A solo pueda editar sus propios registros.
- El equipo B solo pueda editar sus propios registros.
- Ningún equipo pueda modificar las estadísticas del otro.
- Ambos equipos puedan consultar la información compartida que corresponda a sus permisos.

## 4. Registro del marcador

El sistema deberá permitir registrar:

- Sets disputados.
- Puntos por set.
- Resultado de cada set.
- Resultado final del partido.

El marcador podrá ser registrado por ambos equipos y el sistema deberá contemplar mecanismos para comparar o acordar la información registrada.

## 5. Registro de estadísticas

Cada equipo podrá registrar las acciones deportivas de sus propios jugadores.

El sistema deberá permitir:

- Registrar acciones individualmente.
- Registrar cantidades agrupadas cuando sea necesario.
- Asociar cada acción a un jugador.
- Asociar cada acción al partido.
- Asociar cada acción al set correspondiente, si aplica.
- Registrar los atributos específicos de la acción.
- Editar los registros propios antes o después de guardar el partido, según los permisos definidos.

## 6. Guardado del partido

Al guardar el partido, el sistema deberá conservar:

- La información general.
- Los equipos participantes.
- El marcador.
- Los sets y puntos.
- Las estadísticas de cada equipo.
- Las estadísticas individuales.
- La información necesaria para los cálculos históricos.

## 7. Historial

Los partidos guardados deberán poder consultarse posteriormente.

Los datos históricos no deberán perderse como consecuencia de una edición ordinaria de la información del partido.

La política de correcciones, versiones y anulación de partidos deberá definirse antes de la implementación.
