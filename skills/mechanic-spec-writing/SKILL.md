---
name: mechanic-spec-writing
description: Writes developer-readable mechanic specifications: rules, states, edge cases, and contracts from gameplay understanding. Use after system breakdown or when a single mechanic needs a buildable definition before Unreal work.
---

# Mechanic spec writing

## Objetivo

Documentar una mecánica de forma que **implementación y QA** compartan la misma verdad, sin ambigüedad de diseño.

## Plantilla mínima por mecánica

- **Nombre / ID** (ej. `MEC-weapon-primary-fire`)
- **Propósito** (una frase)
- **Actores involucrados** y quién es autoridad de estado
- **Disparadores** (input, evento de mundo, timer)
- **Reglas normales** (paso a paso o bullet)
- **Estados** (si aplica): transiciones válidas
- **Edge cases**: sin munición, muerte mid-action, stun, colisión fallida, etc.
- **Datos expuestos** (damage, cadence, range…) y rangos razonables o “TBD + default”
- **Criterios de aceptación** testeables (3–7 bullets)
- **Fuera de alcance** de esta mecánica en el slice actual

## Calidad

- Evitar narrativa marketing; usar **condiciones** y **resultados observables**.
- Si algo depende de UE (tick, replication), marcar **single-player / local** salvo que el charter diga lo contrario.
- Referenciar otras mecánicas por ID cuando haya acoplamiento.
