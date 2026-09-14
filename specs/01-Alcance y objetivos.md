# Alcance y objetivos

## 1. Objetivo general

Desarrollar una plataforma web que permita a clubes y equipos de volleyball registrar partidos, almacenar estadísticas individuales y colectivas, y consultar el rendimiento histórico de sus jugadores, equipos y clubes.

## 2. Objetivos específicos

- Permitir la creación y gestión de clubes.
- Permitir la creación y gestión de equipos dentro de un club.
- Permitir añadir jugadores a un club y vincularlos a sus equipos.
- Permitir gestionar la pertenencia histórica de los jugadores a equipos y clubes.
- Permitir registrar partidos oficiales y de entrenamiento.
- Permitir registrar sets y puntos de los partidos.
- Permitir registrar acciones deportivas individuales.
- Permitir registrar estadísticas a nivel de equipo.
- Permitir consultar y editar estadísticas según los permisos del usuario.
- Permitir calcular estadísticas históricas de jugadores.
- Permitir calcular estadísticas históricas de equipos.
- Permitir calcular estadísticas históricas de clubes.
- Permitir consultar dashboards de rendimiento.
- Permitir conservar permanentemente los registros históricos de los partidos.

## 3. Alcance geográfico

La primera versión estará orientada a clubes y equipos de volleyball de Sevilla.

La arquitectura deberá permitir una futura expansión a otras ciudades, regiones, países y competiciones.

## 4. Alcance deportivo

El sistema deberá contemplar diferentes tipos de equipos, incluyendo, entre otros:

- Equipos masculinos.
- Equipos femeninos.
- Categorías por edad.
- Equipos de diferentes niveles competitivos.
- Equipos de entrenamiento y competición.

## 5. Alcance funcional inicial

### Gestión de clubes

- Crear club.
- Editar información del club.
- Consultar equipos del club.
- Consultar jugadores vinculados al club.

### Gestión de equipos

- Crear equipo.
- Editar equipo.
- Asociar jugadores.
- Consultar partidos del equipo.
- Consultar estadísticas históricas del equipo.

### Gestión de jugadores

- Añadir jugadores.
- Editar información de jugadores.
- Vincular jugadores a equipos.
- Consultar estadísticas individuales.
- Consultar historial deportivo.

### Gestión de partidos

- Crear partidos.
- Registrar equipos participantes.
- Registrar tipo de partido.
- Registrar sets.
- Registrar puntos.
- Registrar acciones deportivas.
- Guardar y consultar partidos históricos.

### Análisis

- Consultar estadísticas individuales.
- Consultar estadísticas de equipo.
- Consultar estadísticas de club.
- Consultar evolución histórica.
- Visualizar información mediante dashboards.

## 6. Restricciones iniciales

- La primera versión será una aplicación web.
- El sistema deberá permitir registrar partidos sin depender de una aplicación móvil.
- Las estadísticas deberán poder ampliarse en futuras versiones.
- Los permisos de acceso deberán respetar la pertenencia de los usuarios a sus clubes.
