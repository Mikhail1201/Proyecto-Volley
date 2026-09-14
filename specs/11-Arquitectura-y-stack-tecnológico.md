# 11. Arquitectura y stack tecnológico

## 11.1. Propósito

Esta especificación define las tecnologías, lenguajes, componentes y decisiones arquitectónicas que se utilizarán para desarrollar la plataforma de estadísticas de volleyball.

El objetivo es establecer una base tecnológica clara, mantenible y preparada para el crecimiento del sistema, incluyendo futuras capacidades de análisis estadístico avanzado e inteligencia artificial.

---

## 11.2. Stack tecnológico oficial

La primera versión de la plataforma utilizará el siguiente stack:

| Capa | Tecnología | Responsabilidad principal |
|---|---|---|
| Frontend | Next.js | Construcción de la interfaz web, navegación, páginas y consumo de la API |
| Estilos | Tailwind CSS | Diseño visual, responsive design y estilos reutilizables |
| Lenguaje del frontend | TypeScript | Desarrollo tipado y mantenible de la interfaz |
| Backend | Flask | API REST, reglas de negocio, validaciones, cálculos e integraciones |
| Lenguaje del backend | Python | Desarrollo de Flask, procesamiento estadístico y futuras funciones de inteligencia artificial |
| Base de datos | Neon PostgreSQL | Persistencia de usuarios, clubes, equipos, jugadores, partidos, acciones y estadísticas |
| Comunicación | HTTP/HTTPS mediante API REST | Intercambio de información entre Next.js y Flask |
| Control de versiones | Git | Seguimiento de cambios y colaboración sobre el código |

---

## 11.3. Arquitectura general

La aplicación seguirá una arquitectura cliente-servidor separada en tres capas principales:

```text
Usuario
   │
   ▼
Next.js + Tailwind CSS
   │
   │ Solicitudes HTTP/HTTPS mediante API REST
   ▼
Flask API
   ├── Autenticación y autorización
   ├── Gestión de usuarios
   ├── Gestión de clubes
   ├── Gestión de equipos
   ├── Gestión de jugadores
   ├── Gestión de partidos
   ├── Registro de acciones estadísticas
   ├── Cálculos y métricas
   ├── Dashboards y reportes
   └── Futuro módulo de análisis e inteligencia artificial
   │
   ▼
Neon PostgreSQL
```

La separación de responsabilidades permitirá modificar o ampliar una capa sin acoplarla innecesariamente a las demás.

---

## 11.4. Responsabilidades del frontend

Next.js será responsable de:

- Mostrar las páginas y componentes de la plataforma.
- Gestionar la navegación entre las diferentes secciones.
- Proporcionar formularios para registrar y editar información.
- Mostrar partidos, jugadores, equipos, clubes y estadísticas.
- Presentar dashboards, gráficos y cartas visuales de jugadores.
- Gestionar el estado visual de la aplicación.
- Validar de forma preliminar los datos introducidos por el usuario.
- Consumir la API de Flask mediante solicitudes HTTP/HTTPS.
- Mostrar mensajes de éxito, advertencia y error.
- Adaptar la interfaz a computadoras, tabletas y dispositivos móviles.

El frontend no deberá conectarse directamente a Neon PostgreSQL ni contener reglas de negocio críticas que deban ser compartidas por otros clientes.

---

## 11.5. Responsabilidades de Tailwind CSS

Tailwind CSS será utilizado para:

- Definir el sistema visual de la aplicación.
- Construir interfaces responsive.
- Mantener consistencia en colores, espaciados, tipografías y componentes.
- Implementar estados visuales como carga, error, éxito, selección y desactivación.
- Facilitar la creación de una interfaz clara para el registro de estadísticas durante un partido.

Los estilos deberán organizarse de forma reutilizable y evitar duplicaciones innecesarias.

---

## 11.6. Responsabilidades del backend Flask

Flask será responsable de:

- Exponer la API REST de la plataforma.
- Recibir y validar solicitudes del frontend.
- Aplicar las reglas de negocio definidas en las especificaciones.
- Gestionar autenticación y autorización.
- Controlar los permisos por rol, club, equipo y partido.
- Crear, consultar, actualizar y desactivar entidades.
- Registrar partidos, sets y acciones estadísticas.
- Garantizar que cada equipo solo pueda modificar sus propios registros cuando corresponda.
- Ejecutar los cálculos estadísticos oficiales.
- Preparar los datos utilizados por los dashboards.
- Gestionar errores y respuestas consistentes.
- Integrarse posteriormente con módulos de análisis de datos e inteligencia artificial.

Las operaciones críticas deberán validarse en el backend, aunque también exista validación en el frontend.

---

## 11.7. Justificación de Flask y Python

Se utilizará Flask en lugar de construir el backend principal con Node.js debido a la proyección futura del proyecto hacia el análisis avanzado de datos y la inteligencia artificial.

Python cuenta con un ecosistema amplio y consolidado para:

- Análisis y manipulación de datos.
- Procesamiento estadístico.
- Aprendizaje automático.
- Entrenamiento y evaluación de modelos.
- Procesamiento de grandes volúmenes de información.
- Visualización y exploración de datos.

Entre las bibliotecas que podrían utilizarse en futuras etapas se encuentran:

- `NumPy` para operaciones numéricas.
- `pandas` para análisis y transformación de datos.
- `scikit-learn` para modelos de aprendizaje automático.
- `PyTorch` o `TensorFlow` para modelos de inteligencia artificial más avanzados.
- Bibliotecas adicionales de visualización y procesamiento según las necesidades del proyecto.

Esta decisión no significa que Node.js sea incapaz de integrarse con inteligencia artificial. Sin embargo, Python permite trabajar de forma más directa con el ecosistema de análisis de datos y machine learning, reduciendo la complejidad de futuras integraciones.

La elección de Flask permitirá mantener el backend en Python desde el inicio y facilitar la incorporación posterior de módulos de análisis sin tener que migrar la lógica principal del sistema.

---

## 11.8. Preparación para inteligencia artificial

La arquitectura deberá permitir incorporar funcionalidades de inteligencia artificial sin alterar la fuente de verdad del sistema.

En futuras versiones podrían desarrollarse funcionalidades como:

- Detección de patrones de rendimiento.
- Identificación de fortalezas y debilidades de jugadores.
- Recomendaciones de entrenamiento.
- Predicción de tendencias de rendimiento.
- Comparación avanzada entre jugadores, equipos y clubes.
- Clasificación o agrupación de perfiles deportivos.
- Generación de informes automáticos.
- Análisis de evolución a lo largo de varias temporadas.

La inteligencia artificial deberá utilizar los datos históricos de partidos y acciones como entrada. No deberá reemplazar los registros originales ni modificar automáticamente los datos oficiales sin autorización y trazabilidad.

La arquitectura futura podrá organizarse de la siguiente manera:

```text
Flask API
   ├── Módulo de usuarios y permisos
   ├── Módulo de clubes, equipos y jugadores
   ├── Módulo de partidos
   ├── Módulo de acciones estadísticas
   ├── Módulo de cálculos
   ├── Módulo de reportes
   └── Módulo de análisis e inteligencia artificial
          ├── Preparación de datos
          ├── Modelos estadísticos
          ├── Modelos de machine learning
          ├── Evaluación de resultados
          └── Generación de recomendaciones
```

---

## 11.9. Responsabilidades de Neon PostgreSQL

Neon PostgreSQL será la base de datos principal del sistema y almacenará de forma permanente:

- Usuarios y roles.
- Clubes.
- Equipos.
- Jugadores.
- Posiciones.
- Historiales de pertenencia a clubes y equipos.
- Relación entre técnicos y equipos.
- Partidos.
- Participantes de los partidos.
- Invitaciones.
- Sets.
- Participaciones de jugadores.
- Acciones estadísticas.
- Catálogos de acciones, variantes y resultados.
- Métricas o datos derivados cuando sea necesario.
- Registros de auditoría.

La base de datos deberá conservar los registros históricos y evitar que un cambio de equipo, club o posición destruya la información de partidos anteriores.

El acceso a Neon deberá realizarse desde el backend Flask. El frontend no tendrá acceso directo a las credenciales ni a la conexión de la base de datos.

---

## 11.10. Comunicación entre frontend y backend

Next.js y Flask se comunicarán mediante una API REST sobre HTTP o HTTPS.

Las solicitudes deberán:

- Utilizar rutas claras y consistentes.
- Utilizar métodos HTTP apropiados, como `GET`, `POST`, `PUT`, `PATCH` y `DELETE` cuando corresponda.
- Intercambiar información en formato JSON, salvo operaciones específicas que requieran otro formato.
- Devolver códigos de estado HTTP coherentes.
- Incluir respuestas de error estructuradas.
- Validar los datos recibidos antes de procesarlos.
- Aplicar autenticación y autorización en los endpoints protegidos.

Ejemplo conceptual:

```text
Next.js
   │
   └── POST /api/partidos
            │
            ▼
        Flask API
            │
            ▼
      Neon PostgreSQL
            │
            ▼
     Respuesta JSON
            │
            ▼
        Next.js
```

---

## 11.11. Separación de responsabilidades

Se deberán respetar las siguientes reglas:

1. Next.js manejará la presentación y la interacción del usuario.
2. Flask manejará las reglas de negocio y las operaciones oficiales.
3. Neon PostgreSQL almacenará la información persistente.
4. Los cálculos estadísticos oficiales deberán ejecutarse en el backend o en servicios controlados por este.
5. La inteligencia artificial futura deberá integrarse mediante módulos claramente separados.
6. Las credenciales de la base de datos nunca deberán exponerse en el frontend.
7. Las validaciones del frontend no reemplazarán las validaciones del backend.
8. Los componentes visuales no deberán contener consultas directas a la base de datos.
9. Las entidades y relaciones deberán mantenerse coherentes con el modelo de datos aprobado.
10. Las tecnologías elegidas deberán poder sustituirse o ampliarse sin reescribir toda la aplicación.

---

## 11.12. Restricciones técnicas

- El frontend principal deberá desarrollarse con Next.js.
- Los estilos deberán implementarse principalmente con Tailwind CSS.
- El backend principal deberá desarrollarse con Flask y Python.
- La base de datos principal deberá ser PostgreSQL alojada en Neon.
- El frontend no deberá conectarse directamente a la base de datos.
- Las reglas de negocio críticas deberán centralizarse en el backend.
- Los datos originales de partidos y acciones serán la fuente de verdad.
- Los dashboards deberán calcularse a partir de los datos registrados y no de valores introducidos manualmente sin trazabilidad.
- La arquitectura deberá permitir incorporar análisis estadístico e inteligencia artificial en el futuro.
- La elección de bibliotecas adicionales deberá justificarse según una necesidad concreta del sistema.

---

## 11.13. Criterios de aceptación

La especificación se considerará cumplida cuando:

- El proyecto frontend esté configurado con Next.js y TypeScript.
- Tailwind CSS esté integrado y sea utilizado para la interfaz.
- Exista un backend Flask independiente del frontend.
- Flask pueda recibir y responder solicitudes mediante una API REST.
- Flask pueda conectarse de forma segura a Neon PostgreSQL.
- El frontend consuma la API de Flask y no acceda directamente a Neon.
- Las reglas de negocio y cálculos oficiales se ejecuten en el backend.
- La estructura del backend permita agregar posteriormente un módulo de análisis e inteligencia artificial.
- La documentación del proyecto explique la razón de utilizar Python y Flask.
- Las tecnologías utilizadas coincidan con las definidas en esta especificación.
