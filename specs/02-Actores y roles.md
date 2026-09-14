# Actores y roles

## 1. Actores principales

### 1.1 Jugador

Persona que participa en uno o más equipos de volleyball dentro de un club.

#### Responsabilidades

- Consultar su información personal y deportiva.
- Consultar sus estadísticas individuales.
- Consultar su evolución histórica.
- Consultar la información que el club permita visualizar.

#### Restricciones

- No podrá pertenecer simultáneamente a clubes diferentes dentro del mismo contexto de gestión, salvo que se defina explícitamente una excepción.
- Su historial deportivo deberá conservarse cuando cambie de equipo o club.

### 1.2 Técnico

Persona encargada de dirigir uno o más equipos dentro de un club.

#### Responsabilidades

- Consultar los equipos que dirige.
- Registrar partidos.
- Registrar acciones deportivas.
- Consultar estadísticas individuales.
- Consultar estadísticas de equipo.
- Consultar información histórica.
- Editar registros de partidos según los permisos establecidos.

#### Restricciones

- Su ámbito de gestión estará limitado a su club.
- No podrá gestionar equipos de otros clubes sin una autorización explícita.

### 1.3 Presidente o administrador del club

Persona encargada de gestionar la estructura general del club.

#### Responsabilidades

- Gestionar la información del club.
- Crear y administrar equipos.
- Gestionar jugadores.
- Consultar estadísticas de los equipos y del club.
- Gestionar usuarios y permisos dentro de su ámbito.

### 1.4 Administrador de la plataforma

Rol encargado de la administración global del sistema.

#### Responsabilidades

- Gestionar la plataforma.
- Administrar clubes y usuarios cuando sea necesario.
- Supervisar la operación general del sistema.
- Gestionar configuraciones globales.

## 2. Reglas de pertenencia

- Un usuario podrá pertenecer a un club.
- Un técnico podrá dirigir varios equipos dentro de su club.
- Un jugador podrá pertenecer a varios equipos dentro de su club.
- Un jugador podrá cambiar de equipo.
- Un jugador podrá cambiar de club.
- Los cambios de pertenencia no deberán eliminar su historial deportivo.

## 3. Reglas de permisos

- Los técnicos y rangos superiores podrán registrar estadísticas.
- Los técnicos y rangos superiores podrán editar partidos según las reglas de autorización.
- Los usuarios solo deberán acceder a la información que les corresponda según su club, equipo y rol.
- Los permisos específicos de cada rol deberán definirse antes de la implementación.
