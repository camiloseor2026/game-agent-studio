---
name: level-layout-brief
description: Produces precise level and world briefs: purpose, topology, zones, metrics, and readability goals for Unreal greybox or production. Use when kicking off a map, aligning World with Gameplay slice goals, or handing layout to Cursor or Art.
---

# Level layout brief

## Objetivo

Un documento **accionable** que describa el mundo/nivel sin confundirlo con lore largo ni mecánicas internas (eso referencia Gameplay por IDs).

## Contenido mínimo

1. **ID del nivel** + mapa UE sugerido (`L_…` si aplica `docs/naming_conventions.md`).
2. **Rol del nivel en el slice** (una frase): qué debe demostrar el playtest.
3. **Topología**: lista de **zonas** (nombre corto) y conexiones (A↔B, A→C unidireccional).
4. **Métricas orientativas**: tamaño aproximado, alturas clave, ancho mínimo de pasillo, distancia típica de engagement (rangos del arma si Gameplay los fijó).
5. **POIs**: objetivos, spawn jugador, salida, puntos de interés de lectura (silueta, landmark).
6. **Rutas**: principal + alternativa si el slice lo requiere; marcar riesgo de dead-end.
7. **Dependencias**: qué mecánica de Gameplay debe existir antes de cerrar layout (referencia `MEC-…` o brief).
8. **Fuera de alcance** del layout en esta iteración.

## Formato

Preferir tabla de zonas + bullets; evitar narrativa larga. Incluir **preguntas abiertas** para Camilo si bloquean el blockout.
