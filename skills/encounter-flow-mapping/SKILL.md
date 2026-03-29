---
name: encounter-flow-mapping
description: Maps encounter order, triggers, intensity curve, and spatial anchors for a level or slice. Use when pacing combat or challenges in greybox or production maps, or when aligning World with Gameplay spawn rules.
---

# Encounter flow mapping

## Objetivo

Describir **cuándo y dónde** ocurren los encuentros y cómo sube/baja la intensidad, sin implementar lógica (eso va en briefs para Cursor/Gameplay).

## Salida

1. **Lista ordenada de encuentros** (E1, E2…) con: zona/layout anchor, tipo (combat / ambiente / tutorial micro), objetivo de diseño (una línea).
2. **Gatillos** conceptuales: volumen, línea, uso de puerta, timer — según lo que el slice permita.
3. **Curva de intensidad** esquemática (baja/media/alta) o tabla por encuentro.
4. **Recursos del jugador** asumidos al entrar a cada encuentro (salud/munición si aplica; “default slice” si no está definido).
5. **Fallos y recovery**: si el jugador huye o muere, cómo se reintenta el flujo (re-spawn, backtrack).
6. **Dependencias Gameplay**: IDs de enemigos/armas necesarios; bloqueos si no existen aún.

## Límites

- No diseñar stats finos de IA; solo **placing y ritmo** espacial.
- Si el charter excluye sistemas (ej. oleadas complejas), **no** introducirlos aquí.
