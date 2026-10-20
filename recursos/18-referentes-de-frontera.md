# Ficha — Referentes de frontera (fuera del alcance de UX)

| Campo | Valor |
|---|---|
| Tipo | Estándares / normas / leyes / guías de áreas vecinas |
| Organismo | W3C, ETSI/CEN, UE, EE.UU.; guías de plataforma |
| Versión vigente | WCAG 2.2 (2023) · WCAG-EM 2.0 (2026) · EN 301 549 V4.1.1 (2026) · EAA 2019/882 · Section 508 |
| Fuente primaria | https://www.w3.org/TR/WCAG22/ · https://www.w3.org/WAI/test-evaluate/conformance/wcag-em/ · https://eur-lex.europa.eu/eli/dir/2019/882/oj · https://www.section508.gov/ |
| Fecha de consulta | 2026-10-14 |
| Decisión | **FRONTERA** (contexto; no puntúan aquí) |

## Qué incluye y por qué queda fuera

- **Accesibilidad (→ `auditor-wcag`):** WCAG 2.2 (4 principios POUR; nivel AA de mercado; 86
  criterios), WCAG-EM (metodología de evaluación en 5 pasos), EN 301 549, European Accessibility Act
  (Directiva UE 2019/882, aplicable desde 2025) y Section 508 (EE.UU.).
- **Diseño visual (→ `auditor-ui`):** principios de **Gestalt** entendidos como estética, guías de
  plataforma visuales (Material Design, Human Interface Guidelines de Apple, Fluent de Microsoft) y
  sistemas de diseño en su dimensión visual.

## A quién aplica

A los auditores vecinos. `auditor-ux` los **cita como contexto** (una barrera de accesibilidad o un
problema visual pueden afectar a la usabilidad) pero **no los evalúa ni los puntúa**.

## Qué parte es medible (en su área, no en esta)

- Accesibilidad: conformidad por criterio WCAG (técnica → `auditor-wcag`).
- Diseño visual: contraste, tipografía, consistencia de componentes (→ `auditor-ui`).

## Relación con la métrica (Fase 03)

**No genera *checks* propios.** Su función es evitar el solape: si un hallazgo pertenece a UI o a
WCAG, se **deriva** al auditor correspondiente (regla de alcance de [`AGENTS.md`](../../../AGENTS.md)).
