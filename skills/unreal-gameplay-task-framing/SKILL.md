---
name: unreal-gameplay-task-framing
description: Frames gameplay work for Unreal Engine development: BP vs C++ boundaries, maps, modules, placeholders, and integration hooks appropriate to a small team slice. Use when writing Cursor briefs or specs that will become UE assets and code.
---

# Unreal gameplay task framing

## Objetivo

Que cada tarea sea **accionable en UE** sin asumir un estudio AAA: rutas conceptuales, tipo de implementación y puntos de integración claros.

## Checklist por tarea

- **Capa**: Blueprint-only, C++ module, o mixto (justificar en una línea).
- **Dónde vive**: mapa de prueba sugerido, `Content/…` lógico, `Source/…` si aplica (sin inventar nombre de proyecto si no existe en `unreal/`).
- **Actores / componentes** a crear o extender (nombres tentativos alineados a `docs/naming_conventions.md`).
- **Input**: Enhanced Input / legacy — elegir una para el slice y **no mezclar** sin decisión en `TECH_DECISIONS_LOG.md`.
- **Datos**: DataTable vs defaults en BP vs C++ struct (elegir lo más simple que cumpla el brief).
- **Placeholder**: mesh/cube, anim stub, audio null — qué es suficiente para probar la mecánica.
- **Prueba en editor**: pasos mínimos (PIE, mapa X, acción Y, resultado Z).
- **Riesgos UE**: hot reload, dependencias circulares BP↔C++ — mencionar si la tarea los toca.

## Alcance slice

- Priorizar **vertical slice** sobre generalización (un arma, un enemigo, un nivel greybox).
- Multiplayer, física avanzada, GAS completo: solo si el charter lo incluye; si no, **explícitamente fuera**.
