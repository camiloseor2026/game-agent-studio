---
name: gameplay-system-breakdown
description: Decomposes a game or vertical slice into playable systems, actors, inputs, states, and cross-system dependencies. Use when starting a feature, aligning on the core loop, or mapping what should trigger what before writing specs or Unreal tasks.
---

# Gameplay system breakdown

## Objetivo

Pasar de idea o loop deseado a un **mapa de sistemas**: qué existe, quién lo posee, qué eventos fluyen y qué depende de qué.

## Salida esperada

1. **Core loop** en 1–3 frases + pasos numerados del jugador (y del enemigo si aplica).
2. **Lista de sistemas** (tabla): nombre | responsabilidad | entradas | salidas | depende de.
3. **Actores / roles** lógicos (jugador, arma, proyectil, salud, spawner, UI mínima) sin nombres de asset finales si aún no existen.
4. **Reglas globales**: qué está en scope del slice vs explícitamente fuera (charter).
5. **Orden de implementación sugerido** (solo gameplay): qué bloquea qué (ej. input + pawn antes que arma compleja).

## Reglas

- Separar **datos** (valores tunables) de **reglas** (cuándo aplican).
- Marcar **incertidumbres** con `¿?` y una opción por defecto para prototipo.
- No diseñar nivel ni arte; solo **requisitos funcionales** que World/Art puedan consumir después.
