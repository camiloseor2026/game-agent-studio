---
name: placeholder-asset-planning
description: Plans placeholder meshes, materials, and scale references for vertical slices before final art. Use when greybox must read clearly in engine or when deferring high-end assets without blocking Gameplay or World.
---

# Placeholder asset planning

## Objetivo

Definir **placeholders baratos y consistentes** que permitan probar loop, lectura espacial y animación sin comprometer el pipeline final.

## Pasos

1. **Lista mínima** por slice: jugador, arma, enemigo, props de nivel críticos, UI mesh si aplica.
2. **Por ítem**: forma primitive vs mesh simple; color/material semántico (enemigo = rojo suave, interactuable = verde, etc.) — convención única del proyecto.
3. **Escala**: misma referencia que World greybox (altura ojo, ancho pasillo).
4. **Naming**: prefijos UE placeholder (`SM_PH_…` o convención en `docs/naming_conventions.md`).
5. **Plan de reemplazo**: orden sugerido cuando llegue arte final (qué rompe blueprints si se renombra).
6. **Límite**: no crear biblioteca enorme de placeholders; solo lo del hito.

## Reglas

- Placeholders **no** sustituyen spec de rig si el personaje debe animar: usar **esqueleto mínimo** o maniquí UE documentado.
- Coordinar con **World** para no duplicar geometría de greybox y mesh final en el mismo lugar sin criterio.
