# 04. Requisitos no funcionales

## 1. Propósito

Este documento define las características de calidad, restricciones técnicas y condiciones operativas que debe cumplir la plataforma de estadísticas de voleibol.

Las prioridades utilizadas son:

- **MUST:** requisito obligatorio para la primera versión.
- **SHOULD:** requisito importante, pero puede planificarse para una iteración posterior.
- **COULD:** mejora opcional.

## 2. Usabilidad

### RNF-001 — Interfaz clara
**Prioridad:** MUST  
La interfaz debe presentar las funciones, formularios, métricas y estados de forma comprensible para jugadores, técnicos y administradores.

### RNF-002 — Registro rápido de acciones
**Prioridad:** MUST  
El registro de estadísticas debe requerir la menor cantidad de pasos posible, especialmente durante un partido en vivo.

### RNF-003 — Uso en tiempo real
**Prioridad:** MUST  
La interfaz debe permitir registrar acciones y consultar el marcador sin obligar al usuario a abandonar constantemente la pantalla principal del partido.

### RNF-004 — Diseño responsive
**Prioridad:** MUST  
La aplicación debe adaptarse a computadores, tabletas y teléfonos móviles.

### RNF-005 — Consistencia visual
**Prioridad:** MUST  
Los botones, formularios, mensajes, tablas, tarjetas y estados deben mantener patrones visuales consistentes.

### RNF-006 — Prevención de errores
**Prioridad:** MUST  
La interfaz debe prevenir combinaciones inválidas y advertir antes de operaciones destructivas o sensibles.

### RNF-007 — Confirmación de operaciones importantes
**Prioridad:** MUST  
El sistema debe solicitar confirmación antes de eliminar, invalidar, cerrar o modificar información crítica.

### RNF-008 — Accesibilidad básica
**Prioridad:** SHOULD  
La aplicación debería utilizar etiquetas claras, contraste suficiente, navegación mediante teclado, estados visibles y controles accesibles.

### RNF-009 — Idioma
**Prioridad:** MUST  
La primera versión debe estar disponible en español y utilizar terminología deportiva coherente.

## 3. Rendimiento

### RNF-010 — Tiempo de carga inicial
**Prioridad:** SHOULD  
En condiciones normales de red y hardware, las pantallas principales deberían comenzar a mostrarse en un tiempo objetivo inferior a tres segundos.

### RNF-011 — Respuesta de operaciones
**Prioridad:** MUST  
Las operaciones habituales, como guardar una acción, actualizar un marcador o consultar una ficha, deben responder sin retrasos que dificulten el uso durante un partido.

### RNF-012 — Registro sin recargas innecesarias
**Prioridad:** MUST  
Registrar una acción o actualizar una cantidad no debe requerir recargar manualmente toda la página.

### RNF-013 — Consultas eficientes
**Prioridad:** MUST  
Las consultas de estadísticas deben utilizar filtros, índices y agregaciones apropiadas para evitar cargar datos innecesarios.

### RNF-014 — Cálculos escalables
**Prioridad:** SHOULD  
Los cálculos acumulados y dashboards deben diseñarse para funcionar con un crecimiento progresivo de partidos, jugadores, equipos y clubes.

### RNF-015 — Actualización de métricas
**Prioridad:** MUST  
Las métricas deben actualizarse después de registrar o modificar datos relevantes, sin mostrar resultados obsoletos de forma indefinida.

## 4. Seguridad y autorización

### RNF-016 — Autenticación
**Prioridad:** MUST  
Las funciones privadas deben requerir autenticación válida.

### RNF-017 — Autorización por rol
**Prioridad:** MUST  
El sistema debe comprobar los permisos del usuario antes de ejecutar cualquier operación protegida.

### RNF-018 — Aislamiento entre equipos
**Prioridad:** MUST  
En partidos compartidos, los usuarios no deben poder editar las estadísticas pertenecientes al equipo rival.

### RNF-019 — Aislamiento entre clubes
**Prioridad:** MUST  
Los datos de un club deben ser visibles y modificables únicamente por usuarios con permisos suficientes, salvo información explícitamente pública.

### RNF-020 — Protección de datos personales
**Prioridad:** MUST  
La aplicación debe limitar la exposición de datos personales a la información necesaria para cada función.

### RNF-021 — Protección de credenciales
**Prioridad:** MUST  
Las contraseñas y credenciales no deben almacenarse en texto plano ni exponerse en registros o respuestas públicas.

### RNF-022 — Validación de entradas
**Prioridad:** MUST  
Los datos recibidos desde formularios, archivos, API o cualquier cliente deben validarse antes de almacenarse o procesarse.

### RNF-023 — Gestión segura de sesiones
**Prioridad:** MUST  
Las sesiones deben expirar, invalidarse y protegerse mediante mecanismos adecuados al sistema de autenticación utilizado.

### RNF-024 — Auditoría de operaciones sensibles
**Prioridad:** MUST  
El sistema debe registrar quién realizó cambios importantes, qué cambió y cuándo ocurrió.

## 5. Integridad y confiabilidad

### RNF-025 — Integridad referencial
**Prioridad:** MUST  
Las relaciones entre clubes, equipos, jugadores, partidos, sets y acciones deben mantener consistencia.

### RNF-026 — Fuente única de verdad
**Prioridad:** MUST  
Los datos de partidos y acciones deben ser la fuente de verdad para generar estadísticas, históricos, métricas y dashboards.

### RNF-027 — Operaciones atómicas
**Prioridad:** MUST  
Las operaciones que afecten varias entidades relacionadas deben completarse completamente o revertirse para evitar estados parciales.

### RNF-028 — Manejo de errores
**Prioridad:** MUST  
Los errores deben comunicarse mediante mensajes comprensibles sin revelar información sensible o detalles internos innecesarios.

### RNF-029 — Recuperación ante fallos
**Prioridad:** SHOULD  
El sistema debería contar con mecanismos de recuperación ante fallos de aplicación, base de datos o infraestructura.

### RNF-030 — Copias de seguridad
**Prioridad:** SHOULD  
La información histórica debería contar con copias de seguridad periódicas y procedimientos de restauración comprobables.

### RNF-031 — No pérdida de historial
**Prioridad:** MUST  
Desactivar un club, equipo, jugador o partido no debe eliminar automáticamente las estadísticas históricas asociadas.

## 6. Escalabilidad y mantenibilidad

### RNF-032 — Arquitectura modular
**Prioridad:** MUST  
La aplicación debe separar, como mínimo, autenticación, clubes, equipos, jugadores, partidos, estadísticas, cálculos y reportes.

### RNF-033 — Catálogos extensibles
**Prioridad:** MUST  
El diseño debe permitir agregar nuevos tipos de acciones, variantes, resultados, posiciones y categorías sin reescribir toda la aplicación.

### RNF-034 — Separación de responsabilidades
**Prioridad:** MUST  
La interfaz, la lógica de negocio, el acceso a datos y los cálculos estadísticos deben mantenerse separados.

### RNF-035 — Código mantenible
**Prioridad:** MUST  
El código debe utilizar nombres claros, estructuras consistentes, componentes reutilizables y documentación suficiente.

### RNF-036 — Pruebas automatizadas
**Prioridad:** SHOULD  
Las funciones críticas, especialmente permisos, cálculos, marcador e importación, deberían contar con pruebas automatizadas.

### RNF-037 — Migraciones controladas
**Prioridad:** MUST  
Los cambios en la estructura de la base de datos deben realizarse mediante migraciones versionadas y reproducibles.

### RNF-038 — Crecimiento geográfico
**Prioridad:** SHOULD  
El sistema debería permitir incorporar clubes y competiciones de otras ciudades, regiones y países sin depender de reglas exclusivas de Sevilla.

### RNF-039 — Crecimiento deportivo
**Prioridad:** SHOULD  
El sistema debería permitir incorporar nuevas modalidades, categorías, niveles competitivos y métricas sin afectar los datos existentes.

## 7. Disponibilidad y operación

### RNF-040 — Disponibilidad
**Prioridad:** SHOULD  
La plataforma debería mantenerse disponible durante los horarios habituales de entrenamiento y competición.

### RNF-041 — Despliegue reproducible
**Prioridad:** MUST  
El proyecto debe poder desplegarse mediante instrucciones documentadas y configuración controlada.

### RNF-042 — Configuración por entorno
**Prioridad:** MUST  
Las variables sensibles y configuraciones específicas deben gestionarse por entorno y no estar codificadas directamente en el repositorio.

### RNF-043 — Registro de eventos técnicos
**Prioridad:** MUST  
La aplicación debe generar registros técnicos útiles para diagnosticar errores, fallos de conexión y operaciones importantes.

### RNF-044 — Monitoreo
**Prioridad:** SHOULD  
El sistema debería contar con mecanismos para detectar errores, caídas, lentitud y fallos de servicios externos.

### RNF-045 — Migraciones y despliegues seguros
**Prioridad:** MUST  
Las actualizaciones deben ejecutarse de manera que reduzcan el riesgo de pérdida de datos o interrupciones prolongadas.

## 8. Compatibilidad e interoperabilidad

### RNF-046 — Compatibilidad con navegadores
**Prioridad:** MUST  
La aplicación debe funcionar en las versiones recientes de los navegadores principales, como Chrome, Edge, Firefox y Safari.

### RNF-047 — Compatibilidad con dispositivos
**Prioridad:** MUST  
Las funciones principales deben ser utilizables tanto con mouse y teclado como mediante interacción táctil.

### RNF-048 — Importación de Excel
**Prioridad:** SHOULD  
El sistema debería aceptar planillas de estadísticas con una estructura documentada y mostrar errores cuando el archivo no cumpla el formato esperado.

### RNF-049 — Exportación de datos
**Prioridad:** SHOULD  
Los reportes exportados deben conservar nombres de columnas, unidades, filtros aplicados y suficiente información para interpretarse fuera de la plataforma.

### RNF-050 — API preparada para integración
**Prioridad:** SHOULD  
La arquitectura debería permitir integrar aplicaciones móviles, herramientas externas y servicios de terceros mediante una API documentada.

## 9. Privacidad y transparencia

### RNF-051 — Visibilidad controlada
**Prioridad:** MUST  
Cada dato debe tener una política de visibilidad definida: privado, visible para el equipo, visible para el club o público.

### RNF-052 — Transparencia de métricas
**Prioridad:** MUST  
El usuario debe poder conocer qué datos y fórmulas se utilizaron para calcular una métrica.

### RNF-053 — Distinción entre dato y estimación
**Prioridad:** MUST  
El sistema debe distinguir los registros reales de los valores estimados, importados, incompletos o calculados.

### RNF-054 — Historial de cambios
**Prioridad:** MUST  
Los cambios importantes deben conservar información suficiente para identificar el estado anterior y el nuevo estado cuando sea necesario.

### RNF-055 — Minimización de datos
**Prioridad:** MUST  
La plataforma debe almacenar únicamente los datos personales y deportivos necesarios para sus objetivos.

## 10. Criterios generales de aceptación

- Cada requisito no funcional MUST debe poder verificarse mediante una prueba, inspección, revisión técnica o criterio medible.
- Ningún usuario debe obtener permisos por confiar únicamente en controles visuales de la interfaz.
- Las estadísticas históricas deben permanecer disponibles después de cambios de equipo, club, posición o dorsal.
- Las métricas deben ser reproducibles a partir de los datos de origen.
- La aplicación debe conservar un comportamiento comprensible cuando falten datos o existan registros incompletos.
- Las operaciones críticas deben dejar trazabilidad suficiente para investigar errores o modificaciones no autorizadas.
