---
name: unreal-asset-naming-validation
description: Validates Unreal asset names and prefixes (SM_, SK_, SKM_, T_, M_, MI_, BP_, etc.) against project conventions. Use when renaming Content, before PR, or when onboarding new art paths.
---

# Unreal asset naming validation

## Objetivo

Detectar **inconsistencias de nombre** antes de que infecten referencias en blueprints y niveles.

## Fuente de verdad

1. `docs/naming_conventions.md` (sección Unreal si está rellena).
2. Si falta detalle: aplicar convención Epic común y **registrar decisión** en `TECH_DECISIONS_LOG.md` o brief.

## Prefijos típicos (ajustar al proyecto)

| Prefijo | Uso |
|---------|-----|
| `SM_` | Static mesh |
| `SK_` | Skeleton |
| `SKM_` | Skeletal mesh |
| `Anim_` / `A_` | Animación (elegir uno y unificar) |
| `T_` | Textura |
| `M_` | Material |
| `MI_` | Material instance |
| `BP_` | Blueprint actor |
| `PH_` | Placeholder (si se adopta) |

## Proceso

1. Muestra o lista paths bajo `Content/…` a validar.
2. Marcar: **válido**, **prefijo incorrecto**, **espacios o caracteres raros**, **duplicado semántico** (dos nombres para mismo rol).
3. Sugerir **rename target** solo si es mecánico; renombres masivos van en brief separado para Cursor.
4. Señalar **riesgo de redirectores** en UE si el proyecto ya tiene referencias.

## Salida

Tabla **path | problema | sugerencia | severidad**. Sin reescribir todo el Content en un solo paso salvo orden explícito.
