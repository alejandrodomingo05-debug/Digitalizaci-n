# Ficha — GOMS / Keystroke-Level Model (KLM)

| Campo | Valor |
|---|---|
| Tipo | Modelo predictivo / método analítico |
| Organismo | Academia (Card, Moran & Newell) |
| Versión vigente | GOMS (1983); KLM como su variante más simple |
| Fuente primaria | https://www.textbookofusability.com/chapter/goms-and-keystroke-level-model.html |
| Fecha de consulta | 2026-10-14 |
| Decisión | **USAR** |

## Qué exige o propone

Modelos para **predecir el tiempo** que tarda un usuario **experto y sin errores** en completar una
tarea, sin necesidad de usuarios reales. GOMS = *Goals, Operators, Methods, Selection rules*.

El **KLM** estima el tiempo sumando operadores primitivos (**6** en el modelo original):
**K** (pulsación de tecla), **P** (apuntar), **B** (pulsar botón), **H** (cambiar de dispositivo),
**M** (preparación mental) y **R** (espera del sistema). *(D — dibujar — es una extensión posterior.)*

## A quién aplica

A la comparación de **variantes de un mismo flujo** y a la detección de ineficiencias de interacción
(pasos o clics innecesarios).

## Qué parte es medible

- Predice **tiempo de ejecución** (segundos) y **número de pasos/operadores**: totalmente
  cuantificable.
- Permite comparar dos diseños alternativos de forma objetiva.
- Limitación: asume usuario experto y sin errores; no modela novatos ni satisfacción.

## Relación con la métrica (Fase 03)

Sustenta el *check* de **eficiencia** (pasos, clics, tiempo) con un método analítico defendible y
reproducible, sin depender de medir con usuarios.
