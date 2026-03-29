---
name: greybox-planning
description: Plans Unreal greybox blockouts: primitive shapes, scale references, iteration order, and placeholder semantics before final art. Use before building geometry in engine or when rescoping a slice map.
---

# Greybox planning

## Objetivo

Definir **qué** se blockoutea, **en qué orden** y **con qué semántica** (color/material por tipo de superficie opcional) sin comprometer arte final.

## Pasos

1. Fijar **escala de referencia** (módulo de pasillo, altura de cobertura, step height máximo del personaje según Gameplay).
2. Lista de **volúmenes** por zona: propósito, forma aproximada (caja, L, patio), dimensiones guía.
3. **Orden de construcción** en UE: jugador spawn → ruta crítica → encuentros → rutas opcionales.
4. **Placeholders**: enemigos = cilindros/cápsulas; interactuables = prisma marcado; triggers = volumen invisible documentado.
5. **Iteración**: qué medir en primera pasada (tiempos de recorrido, líneas de vista rotas) vs segunda (detalle de cobertura).
6. **Criterio de “listo para encuentros”**: cuándo Gameplay puede colocar spawners sin rehacer geometría mayor.

## Reglas

- Greybox **valida** pacing y lectura; no sustituye encounter-flow detallado (skill aparte).
- Documentar **supuestos** de movimiento del pawn (velocidad, doble salto si aplica) como dependencia.
