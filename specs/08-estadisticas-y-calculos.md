# Estadísticas y cálculos

## Propósito

Definir cómo se obtienen las estadísticas individuales, de equipo y de club a partir de las acciones registradas.

## Fuente de verdad

El flujo será:

```text
Acciones registradas → clasificación → conteos → métricas → dashboards y overall
```

Los totales no deben depender de números introducidos manualmente como valores definitivos.

## Niveles de consulta

Las métricas deberán consultarse:

- Por acción.
- Por jugador y set.
- Por jugador y partido.
- Por jugador y periodo.
- Por equipo y partido.
- Por equipo y periodo.
- Por club y periodo.
- Por temporada, si se implementa.

Filtros mínimos: partido, fecha, club, equipo, jugador, set, tipo de acción, variante, resultado y tipo de partido.

## Conteos básicos

- **Acciones ocurridas:** suma de las cantidades de registros válidos.
- **Acciones positivas:** acciones clasificadas como positivas.
- **Acciones negativas:** acciones clasificadas como negativas.
- **Acciones neutrales:** acciones que no son positivas ni negativas.
- **Acciones efectivas:** acciones que cumplen la definición técnica de efectividad.

## Efectividad

Fórmula preliminar:

```text
Efectividad (%) = acciones efectivas / acciones ocurridas × 100
```

Si no existen acciones ocurridas, no debe producirse una división inválida. La interfaz mostrará `N/D`, `0` o un valor configurable.

## Eficiencia

Fórmula preliminar:

```text
Eficiencia (%) = (acciones positivas - acciones negativas) / acciones ocurridas × 100
```

La fórmula debe validarse por tipo de acción. Puede producir valores negativos.

## Métricas por acción

### Ataque

- Ataques ocurridos.
- Ataques efectivos.
- Ataques positivos.
- Ataques fallidos.
- Block out.
- Puntos generados.
- Efectividad y eficiencia.
- Distribución por zona y variante.
- Promedios por set y partido.

### Colocación

- Colocaciones ocurridas.
- Colocaciones efectivas, positivas y fallidas.
- Distribución por destino.
- Efectividad y eficiencia.

### Toque y recepción

- Acciones ocurridas.
- Acciones positivas y negativas.
- Fallos.
- Distribución por zona.
- Efectividad y eficiencia del recibo.

### Pase

- Pases ocurridos.
- Pases A, B, C y D.
- Fallos.
- Distribución por calidad.
- Efectividad y eficiencia.

### Defensa

- Defensas ocurridas.
- Defensas A, B, C y D, si se confirma la clasificación.
- Defensas efectivas y fallidas.
- Distribución por zona.
- Efectividad y eficiencia defensiva.

### Saque

- Saques ocurridos.
- Saques efectivos y fallidos.
- Puntos directos, si se registran.
- Distribución por zona y distancia.
- Efectividad y eficiencia.

### Bloqueo

- Bloqueos ocurridos.
- Bloqueos efectivos y fallidos.
- Block out.
- Puntos directos, si se registran.
- Distribución por zona.
- Efectividad y eficiencia.

### Apoyo al bloqueo

Si se conserva como acción independiente, tendrá conteos, distribución y métricas propias.

## Métricas de equipo

- Partidos jugados, ganados y perdidos.
- Sets ganados y perdidos.
- Puntos a favor y en contra.
- Diferencia de puntos y sets.
- Promedio de puntos por set.
- Estadísticas colectivas por acción.
- Evolución de resultados.
- Comparación entre partidos oficiales y de entrenamiento.

Las acciones del rival nunca deben incluirse en las métricas propias.

## Métricas de club

- Equipos y jugadores activos.
- Partidos disputados.
- Victorias y derrotas.
- Sets y puntos a favor/en contra.
- Evolución por equipo.
- Comparaciones por categoría o rama.
- Participación de jugadores.

## Muestras pequeñas

Cada métrica debe mostrar, cuando sea posible:

- Cantidad de acciones.
- Cantidad de sets.
- Cantidad de partidos.
- Periodo analizado.

Una muestra pequeña debe identificarse como poco representativa. El overall podrá exigir mínimos de partidos o acciones.

## Datos incompletos

- No se inventarán acciones ni resultados.
- Los partidos incompletos se distinguirán de los partidos sin participación.
- Las métricas insuficientes mostrarán una advertencia.
- Los datos desconocidos no se contarán automáticamente como fallos.

## Actualización

Las métricas podrán actualizarse al guardar una acción, al cerrar un partido o al consultar. Si se almacenan, deberán reconstruirse desde las acciones fuente.

## Overall

El overall deberá:

- Basarse en métricas reales.
- Considerar la posición.
- Considerar volumen y rendimiento.
- Considerar partidos y sets.
- Aplicar un factor de confiabilidad si se decide necesario.
- Mostrar los atributos que contribuyeron al resultado.

La fórmula definitiva queda pendiente.

## Criterios de aceptación

- Registrar una acción actualiza los conteos correspondientes.
- Corregir o eliminar una acción actualiza las métricas.
- Las métricas de un jugador no incluyen acciones ajenas.
- Las métricas de un equipo no incluyen acciones del rival.
- Los filtros funcionan individualmente y combinados.
- Las divisiones entre cero se manejan correctamente.
- Los acumulados coinciden con los registros válidos.
- El historial permanece al cambiar de equipo.
- El overall respeta los requisitos mínimos definidos.
