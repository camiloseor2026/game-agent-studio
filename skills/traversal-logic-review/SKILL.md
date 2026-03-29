---
name: traversal-logic-review
description: Reviews how the player traverses the space: valid paths, gates, skill-gates, one-way flows, and consistency with movement mechanics. Use after greybox or when navigation feels broken or unclear in design docs.
---

# Traversal logic review

## Objetivo

Auditar la **lógica transversal** del juego en el mapa: qué caminos son válidos, qué cierra o abre progreso y si es coherente con las capacidades del personaje **definidas por Gameplay**.

## Checklist de revisión

1. **Grafo de navegación conceptual**: nodos = zonas o POIs; aristas = “puede ir”; marcar unidireccionales.
2. **Gates**: puertas, elevaciones, llaves, habilidades — quién las abre y cuándo (aunque sea placeholder).
3. **Skill-gates**: saltos, agacharse, interacción — alineados a mecánicas existentes o marcados como TBD + riesgo.
4. **Backtracking**: obligatorio u opcional; si rompe pacing, señalar.
5. **Fricción ilegítima**: callejones sin salida no intencionales, saltos ambiguos, escaleras que no leen como escaleras.
6. **Loop de progreso**: desde spawn hasta objetivo y retorno si aplica; detectar soft-locks de diseño.

## Salida

- Tabla **issue / severidad / sugerencia** (máx. una pantalla).
- Lista de **preguntas para Gameplay** si falta definición de movimiento o interacción.

## No incluye

- Pathfinding técnico de UE ni NavMesh bake; solo **diseño** y coherencia con el brief.
