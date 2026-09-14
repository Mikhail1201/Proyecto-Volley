# Decisiones pendientes

## Propósito

Registrar las decisiones deportivas, funcionales y técnicas que deben confirmarse antes de cerrar el diseño de la base de datos y comenzar la implementación.

## Catálogo de acciones

- [ ] Confirmar si toque y recepción son acciones diferentes.
- [ ] Confirmar si apoyo al bloqueo será independiente o una variante de bloqueo.
- [ ] Confirmar el catálogo definitivo de acciones de la primera versión.
- [ ] Confirmar si las variantes podrán administrarse desde la plataforma.
- [ ] Confirmar si se conservarán exactamente los nombres del Excel o se normalizarán.
- [ ] Confirmar si las zonas serán generales o específicas por acción.

## Resultados

- [ ] Definir exactamente qué significa efectivo.
- [ ] Definir qué significa positivo, negativo y neutral.
- [ ] Confirmar si todo fallo es negativo.
- [ ] Definir el tratamiento de block out.
- [ ] Definir si block out genera punto directo.
- [ ] Definir Pase A, B, C y D.
- [ ] Definir Defensa A, B, C y D.
- [ ] Confirmar si los niveles A/B/C/D son mutuamente excluyentes.
- [ ] Definir si una acción puede tener más de un resultado.
- [ ] Definir si se permiten resultados desconocidos.

## Registro por set

- [ ] Decidir si cada acción debe asociarse obligatoriamente a un set.
- [ ] Decidir si se permitirán registros sin separación por set.
- [ ] Definir qué ocurre al registrar después de cerrar un set.
- [ ] Definir si se pueden editar acciones de un set cerrado.
- [ ] Definir si se registrarán acciones de calentamiento.

## Registro individual y agrupado

- [ ] Confirmar el modelo híbrido.
- [ ] Definir cuándo usar registro individual.
- [ ] Definir cuándo usar cantidades agrupadas.
- [ ] Definir si los registros agrupados podrán dividirse.
- [ ] Conservar quién registró cada cantidad.

## Partidos compartidos

- [ ] Definir qué ocurre si el rival rechaza o no responde.
- [ ] Definir si el partido puede comenzar antes de aceptar.
- [ ] Definir quién puede modificar fecha, ubicación y tipo.
- [ ] Definir quién puede modificar el marcador.
- [ ] Definir qué ocurre si los marcadores de ambos equipos difieren.
- [ ] Definir cómo se confirma el marcador oficial.
- [ ] Definir quién resuelve discrepancias.
- [ ] Definir si se puede cerrar un partido incompleto.
- [ ] Definir si un partido cerrado puede reabrirse.

## Jugadores

- [ ] Definir si el jugador necesita cuenta.
- [ ] Confirmar si puede pertenecer a varios equipos simultáneamente.
- [ ] Definir cambios de camiseta.
- [ ] Definir si el número es obligatorio.
- [ ] Definir si puede repetirse un número dentro del mismo partido.
- [ ] Definir si se permiten posiciones secundarias.
- [ ] Definir cómo se registra una posición distinta durante un partido.
- [ ] Decidir si se almacena edad o fecha de nacimiento.
- [ ] Definir el tratamiento de jugadores inactivos.

## Permisos

- [ ] Confirmar si el técnico puede registrar por cualquier jugador de su equipo.
- [ ] Confirmar si el jugador puede registrar sus propias estadísticas.
- [ ] Definir permisos de edición después del cierre.
- [ ] Definir capacidades del administrador de club.
- [ ] Definir qué estadísticas puede ver el equipo rival.
- [ ] Definir qué información será pública.

## Métricas

- [ ] Confirmar fórmula de efectividad por acción.
- [ ] Confirmar fórmula de eficiencia por acción.
- [ ] Definir numerador y denominador de cada métrica.
- [ ] Definir tratamiento de acciones neutrales.
- [ ] Definir tratamiento de resultados desconocidos.
- [ ] Definir redondeo de porcentajes.
- [ ] Definir si se mostrarán eficiencias negativas.
- [ ] Definir mínimos de acciones, sets o partidos.

## Overall y carta

- [ ] Definir atributos por posición.
- [ ] Definir métricas que alimentan cada atributo.
- [ ] Definir fórmula de cada atributo.
- [ ] Definir fórmula del overall.
- [ ] Decidir si será distinto por posición.
- [ ] Decidir si será ponderado.
- [ ] Definir factor de confiabilidad.
- [ ] Definir mínimo de partidos para crear una carta.
- [ ] Definir cartas por temporada.
- [ ] Definir periodo mostrado en la carta.
- [ ] Definir comparación entre cartas.

## Históricos e importación

- [ ] Decidir si se importarán datos antiguos desde Excel.
- [ ] Definir columnas importables.
- [ ] Definir identificación de jugadores durante la importación.
- [ ] Definir tratamiento de nombres duplicados.
- [ ] Conservar el Excel original como respaldo.
- [ ] Definir si los partidos importados serán editables.
- [ ] Marcar los datos importados como históricos.

## Temporadas y competiciones

- [ ] Decidir si habrá temporadas en la primera versión.
- [ ] Decidir si habrá torneos o competiciones.
- [ ] Definir si un partido puede pertenecer a una competición.
- [ ] Definir si las estadísticas se reinician por temporada.
- [ ] Definir consultas históricas por temporada.

## Auditoría

- [ ] Definir historial de cambios de estadísticas.
- [ ] Definir quién puede corregir registros.
- [ ] Exigir una razón para correcciones importantes.
- [ ] Conservar el valor anterior de una acción modificada.
- [ ] Definir reglas para reabrir partidos finalizados.
- [ ] Definir eliminaciones lógicas.

## Orden recomendado para resolver

1. Catálogo definitivo de acciones.
2. Resultados y niveles A/B/C/D.
3. Tratamiento de block out.
4. Fórmulas de efectividad y eficiencia.
5. Registro obligatorio o no por set.
6. Permisos entre equipos.
7. Cierre y modificación de partidos.
8. Requisitos mínimos del overall.
