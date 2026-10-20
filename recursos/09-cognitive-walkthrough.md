# Ficha — Cognitive Walkthrough

| Campo | Valor |
|---|---|
| Tipo | Método de inspección (evaluación sin usuarios) |
| Organismo | Academia (Lewis, Polson, Wharton & Rieman, CHI '90) |
| Versión vigente | Método establecido (1990; variantes posteriores) |
| Fuente primaria | https://doi.org/10.1145/97243.97279 |
| Fecha de consulta | 2026-10-14 |
| Decisión | **USAR** |

## Qué exige o propone

Método para evaluar interfaces **paso a paso**, simulando el razonamiento de un usuario **novel** que
aprende por exploración. Por cada acción de la tarea se plantean cuatro preguntas:

1. ¿El usuario intentará lograr el efecto correcto?
2. ¿Verá que la acción está disponible?
3. ¿Asociará la acción con el efecto deseado?
4. ¿Verá que el progreso avanza hacia su meta?

## A quién aplica

Especialmente a **flujos nuevos** y a usuarios que se enfrentan a la interfaz por primera vez;
útil para evaluar *learnability* y autodescriptividad.

## Qué parte es medible

- Cada una de las cuatro preguntas por paso da un resultado **sí/no** con evidencia.
- Se cuenta el número de **pasos con problemas** y su severidad.
- No mide tiempos ni satisfacción (para eso, GOMS/KLM o test con usuarios).

## Relación con la métrica (Fase 03)

Alimenta los *checks* de **flujos y tareas clave** (pasos, fricción) y de **autodescriptividad**
(ISO 9241-110). Permite localizar el punto exacto donde el usuario se pierde.
