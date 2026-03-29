---
name: regression-review
description: Determines what to re-test after code, level, or asset changes to prevent silent rework in Unreal and repo workflows. Use after merges, refactors, or when a fix touches shared systems.
---

# Regression review

## Objetivo

Responder: **cambió X → qué volver a validar** sin ejecutar toda la suite.

## Entrada

- Descripción del cambio (diff mental, lista de archivos, o TASK ID).
- Superficies conocidas: BP compartido, mapa, input, daño, NavMesh, materiales globales, etc.

## Salida

1. **Áreas en riesgo** (tabla): superficie | por qué | tests sugeridos (smoke / focused).
2. **Smoke mínimo ampliado**: 3–7 pasos extra si el riesgo es alto.
3. **Exclusiones explícitas**: qué **no** hace falta retestear y por qué.
4. **Señal de alarma**: si el cambio toca contrato entre Gameplay ↔ World ↔ Art, marcar **regresión cruzada**.

## Heurísticas Unreal

- Cambio en **GameMode / Default Pawn / PlayerController** → retest input + spawn + cámara.
- Cambio en **collision / mesh** de nivel → retest navegación y líneas de fuego clave.
- Cambio en **skeleton / socket** → retest attach de arma y animaciones básicas.
- Cambio solo en **doc** → regression-review puede ser N/A con justificación.
