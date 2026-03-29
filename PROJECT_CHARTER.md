# Project Charter — Game Agent Studio

## Resumen ejecutivo

Construir una **fábrica experimental** capaz de producir **slices estilo AAA-like con evidencia técnica**, mediante un agente orquestador, subagentes especializados, Cursor como ejecutor en repo, y Unreal como motor de integración. **No** es el objetivo entregar un AAA completo en la primera fase.

## Principio rector

> No vamos a construir un AAA. Vamos a construir una plataforma experimental de producción con una primera prueba controlada, medible y honesta.

## Hipótesis central

Un ecosistema bien orquestado (agentes, skills, MCPs, repo, validaciones, workflows UE) puede asumir una parte significativa de preproducción, prototipado, integración, QA, research y live ops, **medible** en:

- velocidad de producción  
- calidad del output  
- retrabajo  
- autonomía útil  
- cuellos de botella humanos inevitables  

## Alcance de la Fase 1 (Vertical Slice Shooter)

**Incluye**

- Mapa pequeño, loop principal claro  
- Un arma funcional, enemigo o bot funcional  
- Navegación básica, daño y muerte mínimos  
- Assets temporales o estilizados  
- Métricas de rendimiento básicas  
- Pruebas automáticas + checklist QA  
- Pipeline documentado para repetir el proceso  

**Excluye (inicio)**

- Mundo abierto, multiplayer real en fase 1  
- Realismo visual full AAA desde el inicio  
- Monetización compleja al principio  
- Física/simulación avanzada como dependencia crítica temprana  
- Cambios sin validaciones por parte de los agentes  

## Equipo base

| Rol | Responsabilidad |
|-----|-----------------|
| Product Owner / Creative Director (Camilo) | Visión, prioridades, aceptación final |
| Orquestador y subagentes | Flujo de trabajo documentado: descomposición, briefs, artefactos en `agents/` y `docs/` |
| Cursor | Ejecución local en el repositorio (archivos, scripts) según brief aprobado |

## KPIs orientativos

- Tiempo de brief → primer output jugable  
- Iteración por feature  
- Tareas completadas sin retrabajo mayor  
- Bugs por feature, regresiones, estabilidad del build  
- Delegación exitosa, handoffs rotos, intervención humana obligatoria  

## Género

Shooter como **punto de partida razonable**; el género final no se cierra sin la línea de research de mercado.

## Revisión

Este charter se revisa al cerrar el primer slice y al final de cada sprint significativo.
