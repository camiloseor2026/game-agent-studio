---
name: art-integration-notes
description: Writes integration notes for how art assets connect to blueprints, levels, materials, and Niagara in Unreal for small-team slices. Use when handing assets to Gameplay, World, or Cursor implementers.
---

# Art integration notes

## Objetivo

Que **Gameplay/World** sepan qué asset usar, dónde, y qué **no tocar** sin avisar a Art.

## Plantilla corta

- **Asset(s)**: nombre UE + ruta `Content/…`
- **Consumidor**: BP_ / nivel / componente sugerido
- **Materiales**: `M_` base vs `MI_` por variante; parámetros expuestos (lista)
- **Animación**: AnimBP sugerida o “estática hasta…”
- **Sockets / attach**: nombre exacto y orientación esperada
- **Collision**: tipo (simple / per-poly / none) y por qué
- **LOD / culldistance**: si hay regla provisional
- **Fallback**: placeholder si falta asset final
- **Known issues**: escalado, clipping, UV, etc.

## Reglas

- Una nota por **feature o entrega**; enlazar a rigging-handoff si aplica.
- Si la integración requiere código C++, marcar **brief para Cursor** con rutas `Source/` tentativas.

## Salida

Markdown listo para pegar en PR, `agents/art_rigging/`, o sección de `templates/agent_output.md`.
