# 07 — Catálogo de acciones, variantes y resultados

## 1. Propósito

Este documento define el catálogo inicial de acciones estadísticas de volleyball que podrá registrar la plataforma, tomando como referencia la planilla de estadísticas utilizada en el archivo Excel `PERUANOS EN SEVILLA ESTADISTICA`.

El catálogo será la base para:

- Registrar acciones individuales o agrupadas.
- Clasificar acciones por tipo, zona, variante y resultado.
- Calcular estadísticas acumuladas y por partido.
- Calcular métricas de efectividad y eficiencia.
- Generar comparaciones entre jugadoras, equipos y partidos.
- Alimentar los indicadores y la carta visual del jugador.

El Excel se utiliza como referencia funcional, pero la aplicación no debe copiar literalmente su distribución visual ni depender de fórmulas basadas en coordenadas de celdas.

---

## 2. Principios del catálogo

1. Cada acción debe pertenecer a un tipo de acción.
2. Cada tipo de acción puede tener variantes propias.
3. Las variantes deben representar conceptos deportivos, no posiciones de columnas.
4. Los resultados válidos dependen del tipo de acción.
5. Los datos registrados son la fuente de verdad.
6. Los totales, porcentajes, efectividad y eficiencia deben calcularse a partir de los registros.
7. La interfaz puede permitir registrar cantidades agrupadas, pero debe conservar la misma estructura lógica que una acción individual.
8. El catálogo debe poder ampliarse sin modificar toda la estructura de la aplicación.
9. Las etiquetas visibles pueden estar en español, mientras que los identificadores internos deben ser estables.
10. Las categorías que actualmente presentan nombres inconsistentes deben normalizarse.

---

## 3. Tipos de acción iniciales

La primera versión debe soportar los siguientes tipos de acción:

- Colocación.
- Ataque.
- Toque.
- Pase/recepción.
- Defensa.
- Saque.
- Bloqueo.
- Apoyo al bloqueo.
- Asistencia, cuando corresponda al modelo estadístico definitivo.

La acción de asistencia debe mantenerse como categoría prevista, aunque su definición exacta debe validarse con el responsable deportivo antes de activarla definitivamente.

---

## 4. Estructura lógica de una acción

Cada registro de acción debe contener, como mínimo:

- `action_id`: identificador único del registro.
- `match_id`: partido al que pertenece.
- `set_id`: set en el que ocurrió la acción, cuando se registre por set.
- `player_id`: jugador o jugadora que ejecutó la acción.
- `team_id`: equipo al que pertenecía el jugador durante el partido.
- `action_type`: tipo principal de acción.
- `variant`: variante específica de la acción.
- `zone`: zona de origen, destino o clasificación, cuando aplique.
- `result`: resultado de la acción.
- `quantity`: cantidad de acciones representadas por el registro.
- `registered_by`: usuario que registró la acción.
- `created_at`: fecha y hora de creación.
- `updated_at`: fecha y hora de última modificación.

Los campos `variant`, `zone` y `result` no deben ser obligatorios para todas las acciones. Su obligatoriedad dependerá del tipo de acción.

### 4.1 Registro individual y agrupado

La plataforma debe permitir dos modalidades:

- **Registro individual:** una fila representa una acción.
- **Registro agrupado:** una fila representa varias acciones iguales mediante el campo `quantity`.

Ejemplo de registro agrupado:

```text
Jugador: Kattya
Partido: Partido 1
Set: 2
Tipo: Ataque
Variante: Diagonal 4
Resultado: Efectivo
Cantidad: 3
```

Este registro equivale a tres acciones del mismo tipo, variante y resultado.

---

## 5. Catálogo de colocación

### 5.1 Variantes de colocación

El catálogo inicial debe contemplar las variantes observadas en el Excel:

- T3 a 4.
- T2 a 4.
- T3 a 3.
- T2 a 3.
- T1 a 3.
- T2 a 2.
- T3 a 2.
- T3 a 6.
- T2 a 6.

Estas variantes representan la relación entre la zona o posición de origen y la zona o posición de destino.

### 5.2 Resultados de colocación

Resultados iniciales:

- Colocación efectiva.
- Colocación con error o fallo.
- Colocación de calidad A.
- Colocación de calidad B.
- Colocación de calidad C.
- Colocación de calidad D.

Las categorías A, B, C y D deben validarse con el criterio técnico utilizado por el equipo. No deben interpretarse automáticamente como puntos a favor o en contra.

### 5.3 Reglas

- Una colocación debe identificar al colocador responsable.
- La zona de destino puede ser obligatoria cuando se registra una colocación táctica.
- Un fallo de colocación debe registrarse como resultado negativo, no como una variante.
- La aplicación debe permitir consultar colocaciones por zona de destino y por resultado.

---

## 6. Catálogo de ataque

### 6.1 Variantes de ataque

El catálogo inicial debe contemplar:

- Diagonal 4.
- Línea 4.
- Diagonal 3.
- Línea 3.
- Diagonal 2.
- Línea 2.
- Diagonal 6.
- Línea 6.
- Block out.

### 6.2 Resultados de ataque

Resultados iniciales:

- Punto directo.
- Ataque efectivo.
- Ataque defendido.
- Ataque bloqueado.
- Block out.
- Error o fallo.

Debe definirse si `block out` se considera una categoría de resultado, una variante táctica o ambas. Para evitar duplicidad, la implementación debe tratarlo inicialmente como resultado del ataque.

### 6.3 Reglas

- Un ataque debe asociarse al jugador que lo ejecutó.
- La variante debe identificar la dirección o zona del ataque cuando se conozca.
- Un ataque puede generar punto directo, error, bloqueo, defensa rival o block out.
- Los ataques efectivos no deben contarse únicamente por la existencia de una variante; deben depender del resultado.
- Los ataques fallidos deben distinguirse de los ataques defendidos por el rival.

---

## 7. Catálogo de toque

### 7.1 Variantes de toque

El catálogo inicial debe contemplar:

- Zona 4.
- Zona 3.
- Zona 2.
- Zona 8.
- 6 largo.
- Corto 1.
- Largo 1.
- Corto 5.
- Largo 5.

### 7.2 Resultados de toque

Resultados iniciales:

- Toque efectivo.
- Toque controlado.
- Toque defectuoso.
- Fallo.

Las definiciones exactas de `efectivo`, `controlado` y `defectuoso` deben validarse con el criterio del equipo.

### 7.3 Reglas

- El toque debe poder clasificarse por zona de procedencia o zona de destino.
- Debe poder consultarse el volumen total de toques y su distribución por zona.
- Un fallo debe registrarse como resultado y no como una zona.

---

## 8. Catálogo de pase o recepción

### 8.1 Variantes de pase

- Pase A.
- Pase B.
- Pase C.
- Pase D.

### 8.2 Resultados de pase

Resultados iniciales:

- Pase positivo.
- Pase controlable.
- Pase deficiente.
- Fallo.

La correspondencia entre las letras A, B, C y D y las categorías deportivas debe configurarse según el criterio técnico del club.

### 8.3 Reglas

- La plataforma debe permitir registrar la calidad del pase mediante una escala configurable.
- La escala no debe estar codificada únicamente en la interfaz.
- Debe poder consultarse el porcentaje de pases de cada categoría.
- Un fallo de recepción debe diferenciarse de un pase simplemente deficiente.

---

## 9. Catálogo de defensa

### 9.1 Variantes de defensa

- Defensa A.
- Defensa B.
- Defensa C.
- Defensa D.

### 9.2 Resultados de defensa

Resultados iniciales:

- Defensa efectiva.
- Defensa controlable.
- Defensa deficiente.
- Fallo.

### 9.3 Reglas

- La defensa debe asociarse al jugador que realizó el contacto defensivo.
- Debe poder clasificarse por calidad.
- La defensa debe distinguirse del toque y de la recepción, aunque algunas categorías puedan compartir zonas.
- Las métricas defensivas deben poder calcularse por partido, set, jugador y equipo.

---

## 10. Catálogo de saque

### 10.1 Variantes de saque

El catálogo inicial debe contemplar:

- Corto zona 1.
- Largo zona 1.
- Corto zona 6.
- Largo zona 6.
- Corto zona 5.
- Largo zona 5.

### 10.2 Resultados de saque

Resultados iniciales:

- Punto directo o ace.
- Saque efectivo.
- Saque recibido por el rival.
- Saque con presión.
- Error o fallo.

La categoría `saque efectivo` debe definirse con precisión para evitar que se confunda con un ace.

### 10.3 Reglas

- El saque debe asociarse al jugador que lo ejecutó.
- Debe poder clasificarse por zona de destino y longitud.
- Un saque fallido debe contabilizarse como error.
- Un ace debe diferenciarse de un saque que dificulta la recepción pero no genera punto directo.

---

## 11. Catálogo de bloqueo

### 11.1 Variantes de bloqueo

- Bloqueo zona 4.
- Bloqueo zona 3.
- Bloqueo zona 2.
- Maya.

### 11.2 Resultados de bloqueo

Resultados iniciales:

- Punto directo de bloqueo.
- Bloqueo efectivo.
- Block out provocado.
- Bloqueo tocado o desviado.
- Bloqueo fallido.
- Falta de bloqueo.

### 11.3 Reglas

- Debe distinguirse el bloqueo que genera punto directo del bloqueo que desvía el balón.
- `Block out` debe poder identificarse como resultado favorable del bloqueo cuando corresponda.
- El bloqueo fallido no debe confundirse con una acción en la que el balón simplemente supera el bloqueo.
- La plataforma debe permitir registrar bloqueos individuales y bloqueos colectivos si el criterio estadístico lo requiere.

---

## 12. Catálogo de apoyo al bloqueo

El Excel contempla una sección separada para acciones de apoyo al bloqueo.

### 12.1 Variantes iniciales

- Apoyo en zona 4.
- Apoyo en zona 3.
- Apoyo en zona 2.
- Maya.

### 12.2 Resultados iniciales

- Apoyo efectivo.
- Apoyo controlable.
- Apoyo fallido.
- Fallo.

Antes de implementar esta categoría debe confirmarse si representa:

- Una acción defensiva independiente.
- Una participación secundaria en un bloqueo.
- Una clasificación de cobertura.

Si no existe una diferencia deportiva clara, puede modelarse como una variante de defensa o cobertura en lugar de una acción independiente.

---

## 13. Normalización de nombres

La aplicación debe normalizar los nombres del Excel para evitar duplicidades.

Ejemplos:

| Nombre observado | Nombre normalizado sugerido |
|---|---|
| OPUESTA | Opuesta |
| OPUESTO | Opuesta |
| COLOCACION | Colocación |
| TOQUE | Toque |
| DEFENCIBA | Defensiva |
| FALLO | Fallo |
| BLOCK OUT | Block out |
| LINE | Línea |
| DIAGO | Diagonal |

La normalización debe aplicarse en el catálogo y no únicamente mediante texto libre en la interfaz.

---

## 14. Modelo de resultados

Los resultados deben clasificarse mediante atributos que permitan calcular métricas sin depender de nombres textuales.

Cada resultado debería tener, como mínimo:

- `result_id`.
- `name`.
- `action_type`.
- `is_positive`.
- `is_negative`.
- `counts_as_success`.
- `counts_as_error`.
- `counts_as_point_for`.
- `counts_as_point_against`.
- `quality_level`, cuando aplique.
- `active`.

Un resultado no necesariamente debe ser positivo o negativo de manera absoluta. Por ejemplo, un ataque defendido puede no ser un error del atacante, pero tampoco ser un punto directo.

---

## 15. Reglas de cálculo preliminares

Las fórmulas definitivas deben validarse con el responsable técnico. Como base inicial:

### 15.1 Acciones ocurridas

```text
Acciones ocurridas = suma de la cantidad de todos los registros del tipo de acción
```

### 15.2 Acciones efectivas

```text
Acciones efectivas = suma de cantidades cuyo resultado esté marcado como éxito
```

### 15.3 Acciones fallidas

```text
Acciones fallidas = suma de cantidades cuyo resultado esté marcado como error
```

### 15.4 Efectividad

```text
Efectividad = acciones efectivas / acciones ocurridas × 100
```

### 15.5 Eficiencia

```text
Eficiencia = (acciones positivas - acciones negativas) / acciones ocurridas × 100
```

Estas fórmulas son preliminares. Cada acción debe definir qué resultados cuentan como positivos, negativos, neutros o de calidad intermedia.

### 15.6 División entre cero

Si no existen acciones ocurridas, la métrica debe mostrar `N/D` o `0`, según la decisión de diseño, pero nunca producir un error de división entre cero.

---

## 16. Reglas para el overall

El overall no debe calcularse directamente desde una sola estadística ni desde un promedio simple de todas las acciones.

El cálculo futuro debe considerar, como mínimo:

- Posición del jugador.
- Volumen de participación.
- Efectividad.
- Eficiencia.
- Calidad de las acciones.
- Evolución histórica.
- Número mínimo de partidos registrados.
- Peso específico de cada acción según la posición.

La carta visual debe ser una representación del resultado calculado y nunca la fuente original de los datos.

---

## 17. Reglas de validación

La plataforma debe impedir o advertir cuando:

- Se registre una acción sin jugador.
- Se registre una acción sin partido.
- Se seleccione una variante incompatible con el tipo de acción.
- Se utilice un resultado que no pertenece al tipo de acción.
- Se registre una cantidad menor o igual que cero.
- Se registre una acción para un jugador que no pertenecía al equipo en ese partido.
- Se intente modificar estadísticas del equipo contrario sin autorización.
- Se duplique accidentalmente un registro individual.

---

## 18. Pendientes de validación deportiva

Antes de cerrar el catálogo deben confirmarse los siguientes puntos:

1. Definición exacta de efectividad y eficiencia para cada acción.
2. Significado preciso de las escalas A, B, C y D.
3. Diferencia entre toque, recepción, pase y defensa.
4. Si `block out` pertenece al ataque, al bloqueo o a ambos mediante resultados relacionados.
5. Si el apoyo al bloqueo será una acción independiente.
6. Si las zonas representan origen, destino o ubicación del jugador.
7. Si las acciones se registrarán siempre por set.
8. Si se permitirán acciones colectivas, especialmente en bloqueo.
9. Qué resultados cuentan como punto a favor o punto en contra.
10. Qué acciones tendrán peso en el overall según la posición.

---

## 19. Criterios de aceptación

- La plataforma permite seleccionar un tipo de acción válido.
- La plataforma muestra únicamente variantes compatibles con el tipo seleccionado.
- La plataforma muestra únicamente resultados compatibles con el tipo seleccionado.
- Se puede registrar una acción individual.
- Se puede registrar una cantidad agrupada de acciones.
- Cada registro queda asociado a jugador, equipo, partido y, cuando corresponda, set.
- Los totales se calculan a partir de los registros y no se almacenan como valores manuales independientes.
- Las acciones efectivas y fallidas se calculan según las reglas del resultado.
- Las métricas no generan divisiones inválidas.
- Los nombres y categorías del Excel quedan normalizados.
- El catálogo puede ampliarse sin rediseñar las entidades principales del sistema.
