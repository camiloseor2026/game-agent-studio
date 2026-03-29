---
name: asset-pipeline-checklist
description: Checklists for DCC export, file formats, import settings, collisions, LODs, and material assignment for Unreal game assets. Use when setting up or auditing the art pipeline for a slice or before bulk import.
---

# Asset pipeline checklist

## Objetivo

Asegurar que cada tipo de asset **entra a UE una vez** con reglas claras, sin sorpresas de escala, pivotes o materiales rotos.

## Por tipo (marcar OK / riesgo / N/A)

### Estática (SM_)
- Escala: 1 UE unit = 1 cm (confirmar convención del proyecto).
- Pivot en suelo o centro según uso; documentar excepciones.
- Collision: UCX_ simple o generada; complejidad acotada al slice.
- LOD0 obligatorio; LOD1+ si el charter lo pide.
- Lightmap UVs si hay bake estático en el slice.

### Esquelética (SK_ / SKM_)
- Bind pose acordada; escala consistente con personaje de referencia.
- Joint orientations y jerarquía documentada (PDF o tabla corta).
- No transforms congelados no comunicados en el FBX.

### Animación
- Misma esqueleto que referencia; sin retargeting no acordado.
- Frame rate y rango de frames explícitos; root motion sí/no.

### Texturas / materiales
- Potencias de 2; compresión alineada a plataforma objetivo (nota en brief).
- Naming `T_`, `M_`, `MI_` según `docs/naming_conventions.md` y unreal-asset-naming-validation.

### Audio / VFX (si aplica fase)
- Solo si el brief lo incluye; rutas `Content/` y prefijos acordados.

## Salida

Tabla **asset (lista) → tipo → ruta Content sugerida → riesgo → dueño**. Preguntas abiertas van a Camilo si bloquean import.
