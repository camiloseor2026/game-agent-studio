---
name: rigging-handoff-brief
description: Produces rigging and skeleton handoff briefs for animators and Unreal integration: joints, constraints, sockets, facial/body scope, and export rules. Use when a character or creature needs rig before animation or engine hookup.
---

# Rigging handoff brief

## Objetivo

Documentar **qué rig existe**, **qué puede animarse** y **cómo se engancha en UE**, sin asumir pipeline de estudio AAA completo.

## Contenido mínimo

1. **Asset ID** y mesh de referencia (ruta o nombre tentativo).
2. **Esqueleto**: número de huesos principales; extremidades; cadena de spine; dedos (nivel de detalle).
3. **Sockets / attach points**: arma, VFX, casco, etc. (nombres UE sugeridos).
4. **Constraints / IK**: qué está en DCC vs qué se hará en Control Rig/AnimBP (si aplica).
5. **Rango de movimiento esperado**: humanoide estándar vs criatura; notas de “no soportado en slice”.
6. **Export**: FBX versión, bake de animación, escala, eje forward/up alineado al proyecto.
7. **Dependencias Gameplay**: qué blueprint espera qué socket (referencia brief de gameplay si existe).
8. **Fuera de alcance** en esta iteración (facial full, cloth sim, etc.).

## Salida

Brief corto listo para copiar a `templates/task_brief.md` o anexo en `agents/art_rigging/`. Issues de bloqueo → Orquestador / Camilo.
