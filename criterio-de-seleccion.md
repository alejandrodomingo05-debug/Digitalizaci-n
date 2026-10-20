# Criterio de selección de referentes

**Fase 01 · v0.2.0 · Fecha de consulta:** 2026-10-14

Este documento explica **qué referentes se usarán en la métrica (Fase 03)**, cuáles se descartan y
**por qué**. Es el puente entre el inventario ([`README.md`](README.md)) y la métrica.

## Frontera de alcance (la decisión más importante)

`auditor-ux` evalúa **experiencia de usuario**. Dos áreas vecinas **no** le corresponden:

| Área excluida | Auditor responsable | Motivo |
|---|---|---|
| Diseño visual y consistencia (color, tipografía, componentes) | `auditor-ui` | No es usabilidad; es calidad visual |
| Cumplimiento técnico de accesibilidad WCAG | `auditor-wcag` | Requiere criterios de conformidad WCAG y pruebas técnicas |

Por eso, los referentes de accesibilidad (WCAG 2.2, WCAG-EM, EN 301 549, EAA, Section 508) y los
puramente visuales (principios de Gestalt como estética, guías de estilo de plataforma) se marcan
como **`FRONTERA`**: se citan como contexto, pero **no puntúan en este auditor**.

## Criterios de inclusión (USAR)

Un referente entra en la métrica de `auditor-ux` si cumple **todos** estos criterios:

1. **Pertenece al área de UX:** usabilidad, arquitectura de información, flujos y tareas,
   errores/retroalimentación, carga cognitiva o lenguaje de la interfaz.
2. **Tiene fuente primaria** verificable (organismo emisor) con versión y fecha.
3. **Aporta criterios evaluables** (permite un *check* con resultado comprobable).
4. **No se solapa** con el alcance de `auditor-ui` ni de `auditor-wcag`.

## Criterios de exclusión (FRONTERA / DESCARTAR)

- **FRONTERA:** es relevante como contexto o pertenece a otro auditor. Se cita, no puntúa.
- **DESCARTAR:** queda fuera del alcance de UX o no es un criterio de usabilidad.

## Tabla de decisión

| Referente | Decisión | Justificación |
|---|---|---|
| ISO 9241-11 | USAR | Define usabilidad (efectividad, eficiencia, satisfacción); base de la métrica |
| ISO 9241-110 | USAR | 7 principios de interacción; generan *checks* directos |
| ISO 9241-210 | USAR | Marco del proceso centrado en el humano; guía el "cómo" auditar |
| ISO/IEC 25010 | USAR | Modelo de calidad en uso; ancla categorías de evaluación |
| ISO/IEC 25040 | USAR | Proceso de evaluación reproducible; sustenta la reproducibilidad |
| 10 heurísticas de Nielsen | USAR | Núcleo del método heurístico; categorías principales |
| Severidad (Nielsen) | USAR | Sistema de priorización/puntuación defendible |
| Tognazzini | USAR | Complementa a Nielsen en interacción y eficiencia |
| Laws of UX | USAR | Heurísticas cognitivas aplicables y medibles |
| Baymard | USAR | Evidencia de referencia en flujos y conversión |
| Information Architecture | USAR | Fundamenta los *checks* de IA y navegación |
| Plain Language / UX Writing | USAR | Criterios de contenido y microcopy |
| Cognitive Walkthrough | USAR | Método de inspección para flujos y aprendizaje |
| GOMS / KLM | USAR | Predicción de eficiencia; criterios cuantificables |
| Card sorting / Tree testing | USAR | Evalúan findability y arquitectura |
| Test de usabilidad (N=5) | USAR | Validación empírica; base de la evidencia |
| SUS, SUPR-Q, UMUX-Lite, UEQ, PSSUQ | USAR | Instrumentos validados de percepción |
| OECD / Deceptive Patterns / DSA | USAR | Detección de patrones oscuros; riesgo y ética |
| WCAG 2.2 / WCAG-EM / EN 301 549 / EAA / Section 508 | FRONTERA | Accesibilidad técnica → `auditor-wcag` |
| Principios de Gestalt (estética) / guías de plataforma visuales | FRONTERA | Diseño visual → `auditor-ui` |
| NPS | DESCARTAR | Métrica de negocio (lealtad), no de usabilidad |

## Trazabilidad hacia la Fase 03

Cada categoría, *check*, peso y umbral de la métrica (Fase 03) deberá **citar** el referente de esta
fase (o un hallazgo de la Fase 02) que lo justifica. Sin esa cita, el *check* no entra en la métrica
(principio de trazabilidad de [`AGENTS.md`](../../AGENTS.md)).

## Referentes y huecos

El inventario cubre las cinco subáreas de UX (usabilidad, IA, flujos/tareas, errores/retroalimentación,
contenido/carga cognitiva). Posibles huecos a vigilar en la Fase 02: guías específicas de **UX para
IA/conversacional** y de **internacionalización**; si la investigación reciente aporta referentes
primarios, se añadirán al inventario con su fuente y fecha.
