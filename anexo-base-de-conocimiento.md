# Base de Conocimiento — Asesor Profesional de Auditoría UX

> **Ubicación en el proyecto:** anexo de la Fase 01 (`docs/01-estandares-y-referentes/`) de `auditor-ux`.
> **Versión:** 2.1 · **Fecha:** 2026-10-14
> **Propósito:** Fuente de verdad para entrenar/prompt-ear una IA que actúe como asesora de UX
> fiable y profesional, con los estándares y referentes que usa el mercado.
> **Formato:** Diseñado para consumo por IA y por humanos. Secciones autocontenidas, con
> definiciones, criterios, reglas y checklists. Ver *Changelog* (sección 20) para cambios.
> **Aviso de vigencia:** las normas y leyes se actualizan. Antes de afirmar conformidad legal,
> verificar la edición vigente en la jurisdicción concreta.

---

## ÍNDICE

1. [Rol y alcance del asesor](#1-rol-y-alcance-del-asesor)
2. [Principios operativos y guardrails](#2-principios-operativos-y-guardrails)
3. [Cheat sheet de referencia rápida](#3-cheat-sheet-de-referencia-rápida)
4. [Mapa de estándares y referentes](#4-mapa-de-estándares-y-referentes)
5. [Heurísticas de Nielsen (núcleo)](#5-heurísticas-de-nielsen-núcleo)
6. [Otros marcos heurísticos](#6-otros-marcos-heurísticos)
7. [Normas ISO — base formal](#7-normas-iso--base-formal)
8. [Accesibilidad (WCAG, evaluación y legislación)](#8-accesibilidad-wcag-evaluación-y-legislación)
9. [Evidencia conductual y patrones de diseño](#9-evidencia-conductual-y-patrones-de-diseño)
10. [Dominios específicos de evaluación](#10-dominios-específicos-de-evaluación)
11. [Métricas estandarizadas y benchmarking](#11-métricas-estandarizadas-y-benchmarking)
12. [Métodos de inspección e investigación](#12-métodos-de-inspección-e-investigación)
13. [Sistema de severidad, priorización y ROI](#13-sistema-de-severidad-priorización-y-roi)
14. [Proceso estándar de auditoría](#14-proceso-estándar-de-auditoría)
15. [Estructura del informe profesional](#15-estructura-del-informe-profesional)
16. [Checklists operativas](#16-checklists-operativas)
17. [Ética, patrones oscuros, privacidad y consentimiento](#17-ética-patrones-oscuros-privacidad-y-consentimiento)
18. [Reglas de razonamiento y respuesta](#18-reglas-de-razonamiento-y-respuesta)
19. [Glosario](#19-glosario)
20. [Fuentes y changelog](#20-fuentes-y-changelog)

---

## 1. Rol y alcance del asesor

**Rol:** Asesor profesional de auditoría y evaluación de experiencia de usuario (UX), con dominio de
estándares internacionales, heurísticas, accesibilidad, contenido, investigación y medición.

**Qué debe poder hacer:**
- Evaluar productos digitales (web, app, software enterprise, e-commerce, SaaS) contra estándares.
- Diagnosticar problemas de usabilidad, accesibilidad, arquitectura de información, contenido,
  formularios, rendimiento percibido, confianza y conversión.
- Priorizar hallazgos por severidad, impacto y esfuerzo (ROI).
- Redactar hallazgos y recomendaciones accionables y defendibles ante negocio y ante legal.
- Recomendar el método de evaluación adecuado según contexto, riesgo y presupuesto.
- Citar el estándar correcto para cada tipo de hallazgo.

**Qué NO es su trabajo:**
- Inventar datos, métricas o resultados de investigación.
- Certificar cumplimiento legal (solo observar, documentar y recomendar).
- Sustituir la validación con usuarios reales cuando el riesgo lo exige.

**Tres ejes de toda evaluación:** Usabilidad · Accesibilidad · Impacto (usuario + negocio).

**Tipos de auditoría** (pueden combinarse):
| Tipo | Foco | Estándar principal |
|---|---|---|
| Usabilidad | Eficacia/eficiencia/satisfacción de tareas | Nielsen + ISO 9241-11 |
| Accesibilidad | Barreras para personas con discapacidad | WCAG 2.2 AA + WCAG-EM |
| Arquitectura de información | Organización, etiquetado, findability | Card sorting / tree testing |
| Contenido / UX Writing | Claridad, tono, microcopy | Plain language, guías de estilo |
| Conversión (CRO) | Fricción en el funnel | Baymard + analítica |
| Consistencia / Design System | Coherencia de componentes y patrones | Design system / plataforma |
| Ética | Manipulación, transparencia | DSA, UCPD, OECD |

---

## 2. Principios operativos y guardrails

Reglas que gobiernan CÓMO debe razonar y responder el asesor. Tienen prioridad sobre el estilo.

```
G1.  Citar la fuente. Todo hallazgo se ancla a un estándar/heurística/evidencia
     (p. ej. "viola H4 Nielsen", "incumple WCAG 2.2 SC 2.5.8", "ISO 9241-11", "Baymard").
G2.  Distinguir hecho de opinión: [Estándar] [Evidencia empírica] [Heurística/Buena práctica] [Recomendación].
G3.  No inventar. Nunca fabricar resultados de tests, tasas, cifras de usuarios ni referencias.
     Si faltan datos, decirlo y proponer cómo obtenerlos.
G4.  No prometer conformidad legal ni certificación. Usar "en riesgo de incumplir",
     "se observan incumplimientos de".
G5.  Contexto de uso primero. Usabilidad ≠ cualidad absoluta (ISO 9241-11).
G6.  Impacto de negocio. Traducir a abandono, conversión, soporte, riesgo legal, costo.
G7.  Separar observación de interpretación de recomendación.
G8.  Incertidumbre explícita: listar supuestos y proponer validación.
G9.  Priorizar sin ambigüedad: severidad + prioridad + esfuerzo (+ ROI si aplica).
G10. Neutralidad de herramienta: estándares abiertos antes que marcas comerciales.
G11. No usar "overlays"/widgets de accesibilidad como solución a problemas de accesibilidad
     (no garantizan conformidad y pueden interferir con tecnologías de asistencia).
G12. Verificar vigencia de normas y leyes antes de afirmarlas.
```

---

## 3. Cheat sheet de referencia rápida

Para respuestas rápidas y para verificar que se cubre lo esencial.

**5 pilares que todo auditor domina**
1. Heurísticas de Nielsen + evaluación heurística (NN/g)
2. Severidad y priorización (Nielsen / Lewis)
3. Definición normativa de usabilidad (ISO 9241-11)
4. Accesibilidad (WCAG 2.2 AA + WCAG-EM + EN 301 549)
5. Evidencia de conversión (Baymard)

**Códigos para citar**
- Heurísticas: `H1`–`H10` (Nielsen)
- WCAG: `SC <nivel><nº> <nombre>` (ej. `SC 2.5.8 Target Size`)
- ISO: `ISO 9241-11`, `ISO 9241-110`, `ISO 9241-210`, `ISO/IEC 25010`, `ISO/IEC 25040`
- Métodos: `Evaluación heurística`, `Cognitive walkthrough`, `Tree testing`, `WCAG-EM`
- Métricas: `SUS`, `SUPR-Q`, `UMUX-Lite`, `UEQ`, `PSSUQ`

**Umbrales numéricos clave**
- Contraste WCAG AA: 4.5:1 (texto normal) · 3:1 (texto grande/UI)
- Tamaño de objetivo táctil: ≥ 24×24 CSS px (WCAG 2.2 SC 2.5.8)
- SUS: media ≈ 68 · >80 excelente · <51 pobre
- N usuarios para detectar ~85% de problemas de usabilidad: **5** (Nielsen)
- 1 evaluador encuentra ~35% de problemas; 3–5 encuentran ~75% (Nielsen & Landauer)

---

## 4. Mapa de estándares y referentes

| Necesidad de la evaluación | Referente principal | Apoyo |
|---|---|---|
| Evaluación rápida de usabilidad | 10 Heurísticas de Nielsen | Tognazzini, ISO 9241-110 |
| Definición/contrato de usabilidad | ISO 9241-11 | ISO/IEC 25010 |
| Proceso de diseño centrado en el humano | ISO 9241-210 | — |
| Accesibilidad web/app | WCAG 2.2 (AA) | EN 301 549, Section 508, VPAT |
| **Metodología de evaluación de accesibilidad** | **WCAG-EM (W3C)** | Herramientas + pruebas manuales |
| Cumplimiento legal de accesibilidad | Legislación de la jurisdicción | EN 301 549/EAA, ADA, leyes LatAm |
| E-commerce / conversión | Baymard Institute | Heurísticas de checkout |
| Arquitectura de la información | Card sorting + Tree testing | Rosenfeld & Morville |
| Contenido / microcopy | Plain language + guía de estilo | Nielsen H2, H9 |
| Metrología subjetiva (satisfacción) | SUS, SUPR-Q, UMUX-Lite, UEQ | PSSUQ; NPS con cautela |
| Calidad de software completa | ISO/IEC 25010 | ISO/IEC 25040 |
| Análisis predictivo de tiempos | GOMS / KLM | Cognitive walkthrough |
| Ética / patrones oscuros | DSA, UCPD, Digital Fairness Act | OECD, Deceptive Patterns |

**Regla de oro:** toda auditoría cita **≥1 estándar formal** (ISO/WCAG) + **≥1 marco heurístico**
(Nielsen/Baymard) + **evidencia del producto** (captura, dato o paso a paso).

---

## 5. Heurísticas de Nielsen (núcleo)

Referente de facto del mercado desde 1994 (Nielsen Norman Group). Se aplican mediante
**evaluación heurística**: 3–5 evaluadores expertos inspeccionan de forma independiente y
consolidan hallazgos (Nielsen & Molich).

| # | Heurística | Pregunta de evaluación | Señales de violación típicas |
|---|-----------|------------------------|------------------------------|
| 1 | **Visibilidad del estado del sistema** | ¿El usuario sabe siempre qué ocurre? | Sin spinners, sin feedback al enviar, sin progreso |
| 2 | **Correspondencia sistema ↔ mundo real** | ¿El lenguaje coincide con el usuario? | Jerga técnica, íconos ambiguos, orden antinatural |
| 3 | **Control y libertad del usuario** | ¿Puede deshacer, salir, cancelar? | Sin "atrás", modales sin cierre, acciones irreversibles |
| 4 | **Consistencia y estándares** | ¿Mismo lenguaje y comportamiento? | Botones distintos para lo mismo, convenciones rotas |
| 5 | **Prevención de errores** | ¿El diseño evita que el error ocurra? | Sin validación en vivo, sin confirmación en destructivo |
| 6 | **Reconocer > recordar** | ¿Se minimiza la carga de memoria? | Opciones ocultas, sin historial, sin autocompletado |
| 7 | **Flexibilidad y eficiencia de uso** | ¿Hay atajos para expertos? | Sin atajos, sin personalización, flujo único forzado |
| 8 | **Diseño estético y minimalista** | ¿Solo lo relevante, sin ruido? | Exceso de texto/opciones, distractores |
| 9 | **Ayudar a diagnosticar y recuperar errores** | ¿Los errores se explican y ofrecen salida? | "Error 500", sin ubicación, mensajes culpabilizantes |
| 10 | **Ayuda y documentación** | ¿Hay soporte cuando se necesita? | Sin ayuda contextual, docs desactualizadas |

**Regla:** citar como `H<n>`. Un hallazgo puede violar varias heurísticas.

---

## 6. Otros marcos heurísticos

### 6.1 Primeros principios de Tognazzini (askTog)
Complementan a Nielsen con foco en interacción: **Anticipación, Autonomía, Color (y daltonismo),
Consistencia (niveles), Defaults, Descubribilidad (discoverability), Eficiencia del usuario,
Interfaces explorables, Ley de Fitts, Objetos de interfaz, Reducción de latencia, Aprendizaje,
Metáforas, Proteger el trabajo del usuario, Legibilidad, Simplicidad, Visibilidad del estado,
Navegación visible.**

### 6.2 ISO 9241-110:2020 — Principios de interacción (7)
1. Adecuación a la tarea del usuario
2. Autodescriptividad
3. Conformidad con las expectativas del usuario
4. Capacidad de aprendizaje (learnability)
5. Controlabilidad
6. Robustez frente a errores de uso
7. Compromiso del usuario (user engagement)

### 6.3 Cognitive Walkthrough
Inspección paso a paso que simula el proceso del usuario **novel** (aprendizaje por exploración).
Cuatro preguntas por acción:
1. ¿El usuario intentará lograr el efecto correcto?
2. ¿Verá que la acción está disponible?
3. ¿Asociará la acción con el efecto deseado?
4. ¿Verá que el progreso avanza hacia su meta?

### 6.4 GOMS / Keystroke-Level Model (KLM)
Modelos predictivos (Card, Moran & Newell, 1983) para estimar el tiempo de un usuario **experto,
sin errores**. **KLM tiene 6 operadores**: **K** (keystroke/tecla), **P** (apuntar/pointing),
**B** (pulsar botón), **H** (homing/cambio de dispositivo), **M** (preparación mental),
**R** (espera del sistema). *D (drawing) es una extensión posterior para gráficos, no parte del
modelo original de 6.* Útil para comparar variantes de flujo y detectar ineficiencias.

### 6.5 Principios de Gestalt
Proximidad, similitud, cierre, continuidad, **región común**, figura-fondo, conectividad uniforme.
Base perceptual para evaluar agrupación visual y jerarquía.

### 6.6 Heurísticas de contenido y otras aplicables
Plain language, "front-loading" (lo importante primero), escaneabilidad (F-pattern), consistencia
terminológica, y las guías de estilo editorial propia del producto.

---

## 7. Normas ISO — base formal

### 7.1 ISO 9241-11 — Definición de usabilidad
**Usabilidad:** grado en que un producto/servicio puede ser usado por **usuarios especificados**
para alcanzar **objetivos especificados** con **efectividad, eficiencia y satisfacción** en un
**contexto de uso especificado**.
- La revisión **2018** presenta la usabilidad como un **resultado del uso (outcome of use)** y
  refuerza que debe evaluarse en el contexto concreto (usuarios, tareas, equipos, entorno).
- **Efectividad:** precisión y completitud al lograr objetivos.
- **Eficiencia:** recursos (tiempo, esfuerzo) en relación con los resultados.
- **Satisfacción:** comodidad y actitud positiva hacia el uso.
> Nota: el criterio **"ausencia de riesgo" (freedom from risk)** pertenece al modelo de
> **calidad en uso** de ISO/IEC 25010, no a la definición de usabilidad de 9241-11.

### 7.2 ISO 9241-210 (2019) — Diseño centrado en el humano (HCD)
Proceso iterativo: (1) entender contexto de uso → (2) especificar requisitos de usuario →
(3) producir soluciones de diseño → (4) evaluar contra requisitos. Principios: basarse en
comprensión explícita de usuarios/tareas/entornos; participación de usuarios; iteración guiada
por evaluación; abordar la experiencia completa; equipo multidisciplinar.

### 7.3 ISO/IEC 25010 — Modelo de calidad de producto
Dos modelos: **calidad de producto** y **calidad en uso**.
- **Edición 2011 (8 características):** adecuación funcional, eficiencia de desempeño,
  compatibilidad, **usabilidad**, fiabilidad, seguridad, mantenibilidad, portabilidad.
- **Edición 2023 (9 características):** renombra "usabilidad" → **capacidad de interacción
  (interaction capability)** y "portabilidad" → **flexibilidad**; añade **seguridad funcional
  (safety)**. Nuevas subcaracterísticas: inclusividad, autodescriptividad, resistencia, escalabilidad.
- **Calidad en uso (2011, 5 características):** efectividad, eficiencia, satisfacción,
  **ausencia de riesgo (freedom from risk)**, cobertura de contexto.
- **Uso en auditoría:** ideal para marcos enterprise/gubernamentales y para contractualizar el
  alcance por característica.

### 7.4 ISO/IEC 25040 — Proceso de evaluación de calidad
Marco para planificar, ejecutar y reportar la evaluación de calidad de software de forma repetible
(útil para auditorías formales y comparables).

### 7.5 Distinción de términos: usabilidad vs UX vs CX
- **Usabilidad** (ISO 9241-11): constructo **orientado a metas** — efectividad, eficiencia y
  satisfacción en un contexto de uso especificado.
- **Experiencia de usuario (UX)** (ISO 9241-210): **percepciones y respuestas** del usuario que
  resultan del uso **y/o del uso anticipado** de un producto, sistema o servicio. Incluye
  emociones, creencias, preferencias, percepciones, comodidad y comportamientos; es **más amplia**
  que la usabilidad (abarca marca, estética y anticipación).
- **Customer Experience (CX):** experiencia en **todos los puntos de contacto** (no solo digital:
  atención, facturación, logística); más amplia todavía.
> **Regla para el asesor:** no usar "UX" como sinónimo de "usabilidad". Un hallazgo de usabilidad
> se evalúa contra ISO 9241-11; un juicio sobre la experiencia global considera además emoción,
> confianza y expectativas (ISO 9241-210).

**Regla:** usar el número de parte exacto (9241-**11/110/210**; 250**10/40**).

---

## 8. Accesibilidad (WCAG, evaluación y legislación)

### 8.1 WCAG 2.2 (W3C)
- **4 principios (POUR):** Perceptible, Operable, Comprensible, Robusto.
- **3 niveles:** A, **AA (estándar de mercado y legal)**, AAA.
- WCAG 2.2 (oct-2023): **86 criterios**. Añadió **9** y eliminó **4.1.1 Parsing**.
- **Criterios nuevos (y nivel):**
  - 2.4.11 Focus Not Obscured (Minimum) — **AA**
  - 2.4.12 Focus Not Obscured (Enhanced) — AAA
  - 2.4.13 Focus Appearance — AAA
  - 2.5.7 Dragging Movements — **AA**
  - 2.5.8 Target Size (Minimum) — **AA** (≥ 24×24 CSS px)
  - 3.2.6 Consistent Help — **A**
  - 3.3.7 Redundant Entry — **A**
  - 3.3.8 Accessible Authentication (Minimum) — **AA**
  - 3.3.9 Accessible Authentication (Enhanced) — AAA
- **WCAG 2.1 sigue vigente** (y es la referencia de algunas leyes); **WCAG 3.0** está en borrador
  y no es estándar de conformidad todavía.

### 8.2 WCAG-EM — Metodología de evaluación de conformidad
Método **oficial del W3C** para auditar accesibilidad de forma estructurada y reproducible
(evita el "muestreo arbitrario"). Cinco pasos:
1. **Definir el alcance** de la evaluación
2. **Explorar** el sitio/producto objetivo
3. **Seleccionar una muestra representativa** de páginas/vistas
4. **Auditar la muestra** (manual + herramientas + tecnologías de asistencia)
5. **Reportar los hallazgos** (conformidad por criterio y alcance)
> Existe una actualización **WCAG-EM 2.0** (2026) como nota del W3C. Verificar la versión vigente.
> WCAG-EM es lo que distingue una auditoría profesional de un simple escaneo automático.

### 8.3 Marcos legales y de conformidad
| Instrumento | Ámbito | Relación con WCAG |
|---|---|---|
| **EN 301 549** | UE | Norma armonizada; ed. 2026 usa WCAG 2.2 |
| **European Accessibility Act (EAA)** — Dir. (UE) 2019/882 | UE (aplicable desde 28-jun-2025) | Exige accesibilidad de productos/servicios digitales |
| **Section 508** | EE.UU. — sector público federal | Alineada a WCAG (2.0/2.1 AA) |
| **ADA — Title II** (regla final DOJ, abr-2024) | EE.UU. — gobiernos estatales/locales | Adopta **WCAG 2.1 AA** como estándar técnico |
| **ADA — Title III** | EE.UU. — sector privado | Sin estándar explícito; WCAG se usa en litigios/acuerdos |
| **VPAT / ACR 2.5** | Global | Documento de declaración de conformidad (ITI) |
| Leyes LatAm | Ver 8.4 | Varían; suelen exigir accesibilidad web pública |

### 8.4 Latinoamérica (contexto hispanohablante) — verificar vigencia
- **México:** Ley General para la Inclusión de las Personas con Discapacidad (LGIPD).
- **Colombia:** Ley 1618 de 2013 y normativa TIC de accesibilidad.
- **Chile:** Ley 20.422 (igualdad de oportunidades e inclusión).
- **Argentina:** Ley 26.653 (accesibilidad de la información en sitios del Estado).
- **Brasil:** Lei Brasileira de Inclusión (LBI) y modelo eMAG.
- **Panamá:** Ley 15 de 2016.
> **Regla:** la ley cambia; confirmar requisitos y plazos en la jurisdicción concreta.

### 8.5 Pruebas y herramientas
- **Herramientas de apoyo (no sustituyen la revisión manual):** axe DevTools, Lighthouse, WAVE,
  verificadores de contraste.
- **La conformidad AA requiere:** pruebas **manuales** + **navegación por teclado** + **lectores
  de pantalla** (NVDA, JAWS, VoiceOver) + ampliación/zoom + prueba con personas con discapacidad.
- **Perfiles a considerar:** visual (ciego, baja visión, daltonismo), auditivo (sordo,
  hipoacúsico), motor (teclado, switch, control por voz), cognitivo/neurológico y del habla.
- **Overlays/widgets de accesibilidad:** **no recomendados** como solución. No garantizan
  conformidad, pueden crear falsa seguridad e interferir con las tecnologías de asistencia.
  Corregir en el código fuente.

---

## 9. Evidencia conductual y patrones de diseño

### 9.1 Baymard Institute
Referente nº 1 en **e-commerce**. **700+ directrices UX respaldadas por investigación**
(>200.000 horas de estudios con usuarios) y benchmarking contra 330+ sitios líderes. Áreas:
checkout, página de producto, búsqueda, navegación, formularios, listados. Motor **UX-Ray**:
análisis con ~209 heurísticas validadas. **Regla:** citar "Baymard" en hallazgos de conversión/checkout.

### 9.2 Laws of UX (Jon Yablonski)
Fitts (tamaño/distancia), Hick (tiempo de decisión vs nº de opciones), Miller (memoria de trabajo),
Jakob (los usuarios esperan convenciones), Postel (robustez), Tesler (complejidad irreducible),
Aesthetic-Usability Effect, Peak-End, Von Restorff, Zeigarnik, Doherty Threshold (percepción de
respuesta < 400 ms), Goal-Gradient, Serial Position, Leves de Gestalt.

### 9.3 Heurísticas de plataforma
Material Design (Google), Human Interface Guidelines (Apple), Fluent (Microsoft). Evalúan
**conformidad con la convención de la plataforma**.

### 9.4 Patrones de referencia
Rosenfeld & Morville (*Information Architecture*) para navegación, etiquetado, búsqueda y
esquemas de organización. Patrones de formularios, tablas de datos, dashboards, etc.

---

## 10. Dominios específicos de evaluación

### 10.1 Contenido y UX Writing (microcopy)
- Lenguaje claro y **plain language**; sin jerga ni tecnicismos innecesarios.
- Mensajes de error que expliquen **qué pasó, por qué y cómo resolverlo** (sin culpar al usuario).
- Tono consistente con la marca; terminología unificada en todo el producto.
- CTAs con verbos de acción y resultado esperado ("Guardar cambios", no "Enviar").
- Escaneabilidad: encabezados jerárquicos, párrafos cortos, listas, front-loading.
- Ayuda contextual y textos legales comprensibles.

### 10.2 Formularios e introducción de datos
- Mínimo de campos; pedir solo lo necesario; no reingresar datos (WCAG 3.3.7).
- Etiquetas visibles y persistentes (no placeholder como etiqueta).
- Validación en vivo, tolerante a errores y con formato guiado (máscaras).
- Agrupación lógica, orden natural, valores por defecto sensatos.
- Manejo de errores a nivel de campo y de formulario; no perder datos introducidos.
- Autocompletado y atributos `autocomplete` correctos (accesibilidad y eficiencia).

### 10.3 Móvil y táctil
- Objetivos táctiles adecuados (≥ 24×24 CSS px por WCAG; idealmente ≥ 44×44 pt/píxeles de diseño).
- Gestos con alternativa accesible (WCAG 2.5.7); no depender de gestos ocultos.
- Espaciado entre elementos interactivos; evitación de errores por toque accidental.
- Respeto de patrones nativos (navegación, "atrás", permisos) de la plataforma.
- Diseño responsive/adaptativo; orientación y tamaños de pantalla variados.

### 10.4 Rendimiento percibido y latencia
- Feedback inmediato (< 100 ms) y umbral de respuesta (< 400 ms, Doherty).
- Skeletons/placeholders, carga progresiva, estados de "cargando".
- Evitar pantallas en blanco y bloqueos; evitar *layout shift*.
- La latencia se percibe como problema de usabilidad aunque sea técnica.

### 10.5 Confianza, seguridad y privacidad (UX)
- Transparencia de costos, condiciones y uso de datos (sin "hidden costs").
- Señales de seguridad y credibilidad (pagos, devoluciones, reseñas, certificados).
- Consentimiento informado y opciones de privacidad equilibradas (no *cookie walls* coercitivos).
- Autenticación accesible (sin barreras cognitivas — WCAG 3.3.8) y gestión de contraseñas/sesiones.

### 10.6 Internacionalización y localización (i18n / l10n)
- Textos expansibles/contraíbles sin romper el layout; evitar texto incrustado en imágenes.
- Formatos locales de fecha, hora, moneda, números y direcciones.
- Orden de lectura y soporte RTL/LTR; conjuntos de caracteres y pluralificación.
- Evitar chistes, metáforas o referencias culturales no universales.

### 10.7 Onboarding, estados vacíos y estados de error
- Primer uso guiado sin sobrecarga; valor antes que registro forzado.
- Estados vacíos útiles (explicar y ofrecer acción).
- Estados de error, carga y "sin conexión" diseñados, no improvisados.

### 10.8 Interfaces de IA y conversacionales
- **Transparencia:** dejar claro que es una IA y qué puede/no puede hacer; gestionar expectativas.
- **Control y corrección:** permitir editar, regenerar, deshacer y confirmar antes de acciones con impacto.
- **Confianza calibrada:** no presentar las salidas de IA como infalibles; mostrar incertidumbre y fuentes.
- **Recuperación de errores:** la IA se equivoca; ofrecer salida fácil y alternativa humana.
- **Eficiencia:** respuestas concisas, sin obligar a reformular; contexto y atajos persistentes.
- **Consistencia y latencia:** tono/formato estables y estados de "generando" (ver 10.4).
- **Privacidad:** qué datos se envían al modelo y cómo se usan (ver 17).

### 10.9 Consistencia y sistemas de diseño
- Coherencia de componentes, patrones y terminología entre pantallas y equipos.
- Estados completos de cada componente (normal, hover, foco, activo, error, carga, vacío).
- Adherencia al sistema de diseño o justificación de la desviación.
- Escalabilidad: soluciones reutilizables y consistentes, no parches ad-hoc por pantalla.

---

## 11. Métricas estandarizadas y benchmarking

Los auditores cuantifican tanto **comportamiento** como **percepción**:

- **Métricas de comportamiento (conductuales)** — lo que los usuarios *hacen*:
  *tasa de éxito en la tarea*, *tiempo en la tarea*, *tasa/densidad de errores*, *eficiencia* (pasos/clics).
- **Métricas actitudinales (de percepción)** — lo que los usuarios *sienten/opinan*: instrumentos
  validados (tabla inferior) y *Single Ease Question (SEQ)* al finalizar cada tarea.
> **Regla:** una conclusión sólida combina comportamiento + percepción y triangula con cualitativo.

**Instrumentos estandarizados de percepción:**

| Métrica | Qué mide | Formato | Notas de interpretación |
|---|---|---|---|
| **SUS** (System Usability Scale) | Usabilidad percibida global | 10 ítems Likert 1–5; puntaje 0–100 | No es %. Media ≈ 68 (Sauro & Lewis). ~>80 excelente, <51 pobre. La escala adjetival es de Bangor et al. |
| **SUPR-Q** | Calidad UX (usabilidad, confianza, apariencia, lealtad) | 8 ítems; percentil | Permite *percentile rank* vs benchmark |
| **UMUX-Lite** | Usabilidad y utilidad | 2 ítems | Alternativa ultracorta, correlaciona con SUS |
| **UEQ / UEQ+** | Experiencia de usuario (6 escalas) | 26 ítems (UEQ) | Atractivo, perspicuidad, eficiencia, fiabilidad, estimulación, novedad |
| **PSSUQ** | Satisfacción post-tarea | 16 ítems, 3 subescalas | Utilidad del sistema, calidad de la información, calidad de la interfaz |
| **NPS** | Lealtad (prob. de recomendación) | 1 ítem 0–10 | Métrica de negocio, **no** medida de usabilidad |

**Benchmarking:** comparar contra benchmarks publicados (MeasuringU, Baymard, NN/g).
**Regla:** una sola métrica no define la usabilidad; triangular con datos conductuales y cualitativos.

---

## 12. Métodos de inspección e investigación

| Método | Tipo | Cuándo usarlo | Salida |
|---|---|---|---|
| **Evaluación heurística** | Inspección experta | Siempre; rápido y económico | Violaciones por heurística |
| **Cognitive walkthrough** | Inspección cognitiva | Flujos nuevos, usuarios novel | Problemas de learnability paso a paso |
| **Recorrido pluralista** | Inspección en grupo | Alinear equipo/stakeholders | Hallazgos consensuados |
| **GOMS / KLM** | Predictivo | Comparar variantes de interacción | Estimación de tiempos expertos |
| **WCAG-EM** | Inspección de accesibilidad | Auditoría formal de conformidad | Conformidad WCAG por criterio |
| **Card sorting** | Investigación IA | Diseñar categorías de contenido | Modelos mentales de agrupación |
| **Tree testing** | Investigación IA | Validar navegación existente | Tasa de *findability* / éxito |
| **Test de usabilidad** | Validación empírica | Validar hallazgos y causa raíz | Evidencia conductual directa |
| **Analítica / funnel / heatmaps** | Cuantitativo | Cuantificar magnitud del problema | Fricción por paso, abandono |
| **A/B / test multivariante** | Experimental | Optimizar variantes medibles | Diferencia con significación |
| **Benchmarking competitivo** | Comparativo | Contextualizar el desempeño | Brechas vs competidores |
| **Personas / journey maps / service blueprint** | Artefactos de síntesis | Alinear el diseño con usuarios | Modelos compartidos de la experiencia |

**Reglas de método:**
- La inspección **identifica** problemas; los tests con usuarios **confirman** la causa raíz.
- **Efecto del evaluador único:** 1 evaluador detecta ~35% de los problemas; 3–5 detectan ~75%
  (Nielsen & Landauer). No emitir conclusiones con un solo evaluador y sin triangulación.
- **N para tests cualitativos:** ~5 usuarios descubren ~85% de los problemas (Nielsen).
- **Analítica:** describir comportamiento, no intención; complementar con cualitativo.
- **A/B testing:** requiere muestra suficiente y significación estadística; no extrapolar de muestras pequeñas.

---

## 13. Sistema de severidad, priorización y ROI

### 13.1 Escala de severidad de Nielsen (0–4)
| Nivel | Etiqueta | Significado |
|---|---|---|
| 0 | No es problema | No afecta la experiencia |
| 1 | Cosmético | Solo si hay tiempo sobrante |
| 2 | Menor | Bajo impacto; prioridad baja |
| 3 | Mayor | Impacto alto; importante arreglar |
| 4 | Catastrófico | Bloquea el objetivo; arreglar ya |

Determinada por: **Frecuencia** (¿cuántos lo encuentran?) · **Impacto** (¿qué tan grave?) ·
**Persistencia** (¿se supera con facilidad o es recurrente?).

### 13.2 Severidad combinada (Lewis / Rubin & Chisnell)
`Severidad = Magnitud × Frecuencia × Persistencia` → prioriza por producto de impacto.

### 13.3 Matriz de priorización (Impacto × Esfuerzo)
```
            ESFUERZO BAJO          ESFUERZO ALTO
IMPACTO ALTO   "Quick wins"          "Proyectos clave"
IMPACTO BAJO    "Rellenos"           "Evitar / descartar"
```
Ordenar por **severidad alta + esfuerzo bajo** primero.

**Mapeo por defecto severidad → prioridad** (ajustable según contexto/negocio):
| Severidad | Prioridad por defecto | Acción |
|---|---|---|
| 4 Catastrófico | P1 | Arreglar de inmediato |
| 3 Mayor | P1–P2 | Arreglar en el ciclo actual |
| 2 Menor | P3 | Planificar backlog |
| 1 Cosmético | P3 | Solo si hay tiempo |
| 0 No problema | — | Descartar |

### 13.4 Justificación de ROI
- El costo de corregir crece según cuándo se detecta (heurística "1-10-100": diseño < desarrollo
  < post-lanzamiento). Citar como estimación, no como dato exacto.
- Cuantificar impacto cuando haya datos: abandono de funnel, tickets de soporte, tasa de error,
  conversión, riesgo legal/multas.
- Sin datos: presentar ROI cualitativo (riesgo, alcance, esfuerzo) y proponer medición.

### 13.5 Plantilla de hallazgo (formato obligatorio)
```
ID:            [UX-###]
Título:        [Hallazgo en una frase]
Ubicación:     [Pantalla / flujo / componente]
Evidencia:     [Captura, dato, paso a paso]
Problema:      [Qué ocurre y por qué es un problema para el usuario]
Estándar:      [H# Nielsen / WCAG SC x.x.x / ISO / Baymard / otro]
Severidad:     [0–4]
Impacto:       [negocio / usuario / cumplimiento]
Recomendación: [Arreglo concreto y accionable]
Esfuerzo:      [Bajo / Medio / Alto]
Prioridad:     [P1 / P2 / P3]
```

---

## 14. Proceso estándar de auditoría

```
FASE 0 · Encuadre
  - Objetivos de negocio y metas UX; KPIs; alcance (qué se evalúa y qué no).
  - Contexto de uso (usuarios, tareas, dispositivos, plataforma) — ISO 9241-11/-210.
  - Riesgos y requisitos legales; jurisdicción aplicable.

FASE 1 · Análisis cuantitativo
  - Analítica, funnels, heatmaps, mapas de scroll, tickets de soporte.
  - Identificar DÓNDE duele (no por qué).

FASE 2 · Inspección experta
  - Evaluación heurística (Nielsen) + criterios de plataforma.
  - Cognitive walkthrough en flujos críticos.

FASE 3 · Accesibilidad
  - WCAG 2.2 AA vía WCAG-EM: alcance, muestra representativa, pruebas manuales + AT.

FASE 4 · Investigación IA y contenido (si aplica)
  - Card sorting para categorías; tree testing para validar navegación.
  - Revisión de contenido/microcopy.

FASE 5 · Validación empírica (si aplica)
  - Test con usuarios (~5) para confirmar causa raíz; medir SUS/SUPR-Q.

FASE 6 · Benchmarking
  - Comparación con competidores y/o directrices Baymard.

FASE 7 · Síntesis y priorización
  - Consolidar, deduplicar, asignar severidad/impacto/esfuerzo; estimar ROI.

FASE 8 · Informe y plan
  - Resumen ejecutivo, hallazgos y roadmap priorizado; recomendaciones de seguimiento.
```

**Criterio de cierre:** cada hallazgo tiene evidencia, estándar, severidad y recomendación accionable.

---

## 15. Estructura del informe profesional

1. **Resumen ejecutivo** — 3–5 hallazgos clave, score global, impacto de negocio, próximos pasos.
2. **Alcance y metodología** — qué se evaluó, con qué estándares, limitaciones y supuestos.
3. **Scorecard** — puntuación por categoría (Usabilidad, Accesibilidad, IA, Contenido, Conversión, Consistencia).
4. **Hallazgos detallados** — formato de 13.5, con capturas anotadas.
5. **Log priorizado** — ordenado por severidad/prioridad/esfuerzo.
6. **Recomendaciones y roadmap** — quick wins → proyectos clave → mejoras continuas.
7. **Anexos** — criterios WCAG usados, metodología de scoring, glosario, changelog.

**Método de scoring (transparencia obligatoria):** puntuar cada categoría de 0–100 a partir de la
severidad de los hallazgos (p. ej. penalización ponderada por severidad), **declarar la fórmula** y
acompañar el número de su interpretación. Un score sin metodología declarada no es defendible.

**Regla de redacción:** cada hallazgo sigue la fórmula **Problema → Impacto → Recomendación**.

---

## 16. Checklists operativas

### 16.1 Checklist heurística rápida (10 puntos)
- [ ] H1 Estado del sistema visible (carga, confirmación, progreso)
- [ ] H2 Lenguaje y conceptos del mundo real
- [ ] H3 Control y libertad (undo, cancelar, salir)
- [ ] H4 Consistencia interna y con estándares
- [ ] H5 Prevención de errores
- [ ] H6 Reconocer > recordar
- [ ] H7 Flexibilidad y atajos para expertos
- [ ] H8 Minimalismo y foco
- [ ] H9 Mensajes de error claros y recuperables
- [ ] H10 Ayuda y documentación útiles

### 16.2 Checklist de accesibilidad (WCAG 2.2 AA, resumen)
- [ ] Contraste de texto ≥ 4.5:1 (normal) / 3:1 (grande y componentes UI)
- [ ] Navegación completa por teclado y foco visible
- [ ] Foco no oculto (2.4.11)
- [ ] Alternativa a arrastrar (2.5.7)
- [ ] Tamaño de objetivo ≥ 24×24 CSS px (2.5.8)
- [ ] Textos alternativos en imágenes con significado
- [ ] Estructura semántica (encabezados, landmarks, listas)
- [ ] Formularios con etiquetas y errores asociados
- [ ] Sin dependencia exclusiva del color
- [ ] Alternativa a autenticación cognitivamente compleja (3.3.8)
- [ ] No reingreso redundante de datos (3.3.7)
- [ ] Ayuda en ubicación consistente (3.2.6)
- [ ] Funciona con zoom/ampliación (hasta 200%) y reflow
- [ ] Probado con lector de pantalla y sin uso de overlays como "solución"

### 16.3 Checklist de IA y navegación
- [ ] Etiquetas claras y orientadas al usuario (no al organigrama interno)
- [ ] Profundidad razonable (≤3 niveles para tareas clave)
- [ ] Búsqueda con filtros, tolerancia a errores y resultados relevantes
- [ ] Migas de pan / orientación de ubicación
- [ ] Arquitectura validada con tree testing
- [ ] Estados vacíos y de error informativos

### 16.4 Checklist de conversión (e-commerce / formularios)
- [ ] Fricción reducida en checkout (invitado, menos campos, progreso)
- [ ] Transparencia de costos desde el inicio
- [ ] Formularios con validación en vivo y ayuda contextual
- [ ] Jerarquía clara de CTAs
- [ ] Confianza (seguridad, devoluciones, reseñas)
- [ ] Recuperación de errores sin perder datos

### 16.5 Checklist de contenido y microcopy
- [ ] Lenguaje claro; sin jerga innecesaria
- [ ] Mensajes de error accionables (qué, por qué, cómo)
- [ ] Terminología consistente en todo el producto
- [ ] CTAs orientados a la acción y al resultado
- [ ] Escaneabilidad (encabezados, listas, párrafos cortos)
- [ ] Ayuda contextual donde se necesita

---

## 17. Ética, patrones oscuros, privacidad y consentimiento

**Patrones oscuros / deceptive patterns** (Harry Brignull; OECD "dark commercial patterns"):
técnicas que engañan o coaccionan. Categorías frecuentes: *trick questions, sneaking, roach motel
(difícil salir), confirmshaming, obstruction, forced action, hidden costs, fake scarcity, nagging.*

**Regulación relevante:**
- **DSA (UE)** — prohíbe interfaces que distorsionan la libre elección.
- **UCPD (UE)** — prácticas comerciales desleales/engañosas.
- **Digital Fairness Act (propuesta UE)** — foco en patrones oscuros y diseño adictivo.
- **FTC (EE.UU.)** — acciones contra diseños engañosos.
- **GDPR (UE)** — consentimiento informado y libre; afecta al diseño de cookies/privacidad.
- **SERNAC (Chile)** — estudios y acciones contra patrones engañosos.

**Regla ética:** todo diseño debe respetar la autonomía del usuario. Los patrones oscuros se
reportan como **hallazgos y riesgo legal**, nunca como "mejora de conversión".

---

## 18. Reglas de razonamiento y respuesta

### 18.1 Al evaluar o recomendar
1. **Preguntar contexto primero** si falta (producto, usuarios, plataforma, objetivo, jurisdicción, presupuesto/tiempo).
2. **Elegir el marco** con la tabla de la sección 4 y declararlo.
3. **Estructurar cada hallazgo** con el formato 13.5.
4. **Priorizar** con severidad + impacto × esfuerzo (+ ROI si hay datos).
5. **Recomendar** acciones concretas, no genéricas (no "mejorar UX", sino "dividir el formulario en 2 pasos con validación en vivo").

### 18.2 Reglas de incertidumbre (obligatorias)
- Sin datos suficientes → decirlo y proponer cómo obtenerlos.
- Hallazgo basado en supuestos → listarlos y proponer validación.
- Norma/ley que puede haber cambiado → indicar que debe verificarse la edición vigente.
- Nunca afirmar tasas, mejoras o cifras sin fuente.

### 18.3 Estilo profesional
- Claro, directo, orientado a la acción.
- Terminología precisa (número de estándar exacto).
- Separar **observación** vs **interpretación** vs **recomendación**.
- Explicar el "por qué" (impacto) y el "cómo" (arreglo).

### 18.4 Anti-patrones que el asesor debe evitar
- Citar heurísticas sin explicar la violación concreta.
- Confundir usabilidad con preferencia estética.
- Recomendar sin estimar esfuerzo/prioridad.
- Presentar NPS (o un solo dato) como "la usabilidad".
- Prometer cumplimiento legal o certificación.
- Proponer overlays de accesibilidad como solución.
- Concluir con un único evaluador sin triangulación.

---

## 19. Glosario

- **Heurística:** regla general de usabilidad que orienta la inspección experta.
- **Evaluación heurística:** método de inspección donde expertos juzgan la interfaz contra heurísticas.
- **Contexto de uso:** usuarios + tareas + equipos + entorno físico/social donde se usa el producto.
- **POUR:** Perceptible, Operable, Comprensible, Robusto (principios WCAG).
- **Conformidad AA:** nivel de WCAG que el mercado y la ley suelen exigir.
- **WCAG-EM:** metodología del W3C para evaluar conformidad con WCAG de forma reproducible.
- **VPAT/ACR:** documento que declara el grado de conformidad con estándares de accesibilidad.
- **Overlay de accesibilidad:** widget que "arregla" accesibilidad desde el front-end; no garantiza conformidad.
- **Severidad:** gravedad de un problema según frecuencia, impacto y persistencia.
- **ROI:** retorno de la inversión; relación beneficio (usuario/negocio) vs costo del arreglo.
- **Findability:** facilidad para encontrar contenido/navegación (tree testing).
- **Quick win:** mejora de alto impacto y bajo esfuerzo.
- **Patrón oscuro:** diseño que induce decisiones contrarias al interés del usuario.
- **Efecto del evaluador:** porcentaje de problemas detectados por un número dado de evaluadores.

---

## 20. Fuentes y changelog

### 20.1 Fuentes primarias de referencia
**Estándares formales**
- ISO 9241-11 / -110 / -210 — Ergonomía de la interacción humano-sistema.
- ISO/IEC 25010 / 25040 — Calidad de producto software y evaluación.
- W3C — WCAG 2.2 · **WCAG-EM** (metodología de evaluación).
- EN 301 549; Directive (EU) 2019/882 (EAA); Section 508; VPAT/ACR 2.5.
- ADA Title II Final Rule (DOJ, 2024).
- LatAm: México (LGIPD), Colombia (Ley 1618/2013), Chile (Ley 20.422), Argentina (Ley 26.653), Brasil (LBI/eMAG).

**Heurísticas y marcos**
- Nielsen Norman Group — 10 Usability Heuristics; Severity Ratings; Card Sorting vs Tree Testing; Why You Only Need to Test with 5 Users.
- Nielsen & Landauer — evaluator effect.
- Bruce Tognazzini — First Principles of Interaction Design.
- Baymard Institute — E-commerce UX research & guidelines.
- Jon Yablonski — Laws of UX.
- Card, Moran & Newell — GOMS / KLM; Lewis, Polson et al. — Cognitive Walkthrough.
- Rosenfeld & Morville — Information Architecture.
- Harry Brignull — Deceptive Patterns; OECD — Dark Commercial Patterns.

**Métricas**
- Brooke — SUS; Sauro & Lewis — SUPR-Q, UMUX-Lite, SUS benchmarks (Quantifying the User Experience).
- Bangor et al. — escala adjetival de SUS. MeasuringU — benchmarks.

**Métodos y práctica**
- Rubin & Chisnell — Handbook of Usability Testing.
- W3C WAI — Evaluating Web Accessibility / WCAG-EM.

### 20.2 Changelog
**v2.1 (2026-10-14) — cierre de gaps de alto valor**
- **Añadido:** definición de **UX (ISO 9241-210)** y distinción **usabilidad vs UX vs CX** (7.5) — terminología central que faltaba.
- **Añadido:** **perfiles de discapacidad** a probar en accesibilidad (8.5).
- **Añadido:** dominios **interfaces de IA/conversacionales** (10.8) y **consistencia/sistemas de diseño** (10.9) — el tipo "consistencia" estaba listado pero sin contenido.
- **Añadido:** métricas **conductuales vs actitudinales** (tasa de éxito, tiempo, errores) y **SEQ** (11).
- **Añadido:** **mapeo severidad → prioridad** por defecto (13.3) y **método de scoring** transparente (15).
- **Decidido NO añadir (evitar bloat):** detalle de los 86 criterios WCAG, especificaciones ARIA/HTML y fórmulas estadísticas — restarían precisión sin aportar valor al asesor.

**v2.0 (2026-10-14) — revisión crítica**
- **Corregido:** KLM ahora lista los **6 operadores** del modelo original (K, P, B, H, M, R); "D" marcado como extensión.
- **Corregido:** ISO 9241-11:2018 — se retira la atribución errónea de "freedom from risk" (pertenece a ISO/IEC 25010, calidad en uso) y se precisa "outcome of use".
- **Corregido:** ADA — se añade la regla Title II (DOJ 2024, WCAG 2.1 AA) y se matiza Title III.
- **Corregido:** SUS — media 68 atribuida a Sauro & Lewis; escala adjetival a Bangor et al.
- **Corregido:** lista de principios de Tognazzini (nombres y alcance precisos).
- **Añadido (gaps):** sección "Cheat sheet" (3); reescrita "Accesibilidad" con **WCAG-EM** y advertencia sobre **overlays** (8); nueva sección "Dominios específicos" con UX Writing, formularios, móvil, rendimiento percibido, confianza/seguridad, i18n y estados (10); nuevos métodos (test de usabilidad N=5, A/B, personas/journey maps) y **efecto del evaluador** (12); justificación de **ROI** (13); checklists de contenido (16.5); privacidad/GDPR (17); más fuentes y **changelog** (20).
- **Eficiencia:** añadidos códigos de cita, umbrales numéricos clave y reglas de decisión para acelerar respuestas correctas.

**v1.0 (2026-10-14):** versión inicial.

---

*Fin del documento. Fuente de verdad del conocimiento. Las reglas de comportamiento operativo están
en [`borrador-system-prompt.md`](../04-auditor-reutilizable/borrador-system-prompt.md).*
