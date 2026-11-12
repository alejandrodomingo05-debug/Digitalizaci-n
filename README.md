# UX-Auditor

**Auditor automático de experiencia de usuario para webs.** Analiza una página y le da una nota de 0 a 10, el **Índice IUX**, junto con un informe que explica cada problema: dónde está, qué norma incumple y cómo corregirlo.

Proyecto en equipo de 2º de DAM (Digitalización Avanzada · CIFP La Laboral, Gijón).

## Qué hace

- Abre la web en **móvil y escritorio** con un navegador real (Playwright + Chromium).
- Comprueba **100 reglas** repartidas en 8 dimensiones, con su peso en la nota:

| Dimensión | Peso | Ejemplos de lo que revisa |
|---|---|---|
| D1 Accesibilidad | 25 % | Contraste, texto alternativo, navegación con teclado, foco visible, letra al 200 % |
| D2 Usabilidad e interacción | 15 % | Tamaño de botones, elementos clicables reconocibles, una acción principal |
| D3 Rendimiento | 15 % | Velocidad de carga (LCP), estabilidad (CLS), bloqueo (TBT), peso de la página |
| D4 Diseño visual y contenido | 10 % | Tamaño de letra, legibilidad, tablet y móvil en horizontal |
| D5 Formularios | 10 % | Etiquetas, campos obligatorios, autocompletado |
| D6 Navegación | 10 % | Menús, «saltar al contenido», coherencia entre páginas |
| D7 Satisfacción | 5 % | Prueba con usuarios (cuestionario SUS) |
| D8 Ética, privacidad y sostenibilidad | 10 % | Banner de cookies justo, rastreo sin permiso, patrones oscuros, CO2 por visita |

- Incluye un **cuestionario experto** de 21 preguntas (heurísticas de Nielsen, principios de Steve Krug…) para lo que una máquina no puede juzgar.
- Genera el informe en **HTML, JSON y Markdown**, con capturas y el selector CSS de cada elemento afectado.
- Aplica **techos de nota**: por ejemplo, un fallo crítico limita la nota a 4,9 aunque el resto esté bien.

## Uso rápido

Requisitos: Python 3.10 o superior.

```bash
python -m venv .venv
source .venv/bin/activate          # Windows: .venv\Scripts\activate.bat
pip install -e .
python -m playwright install chromium

uxaudit run https://www.gov.uk
```

Más ejemplos:

```bash
# Varias páginas del mismo sitio
uxaudit run https://www.gov.uk https://www.gov.uk/contact --proyecto "GOV.UK"

# Una web en local, con informe en tres formatos
uxaudit run http://localhost:5173 -f html,json,md

# Auditoría completa con cuestionario experto y prueba con usuarios
uxaudit manual
uxaudit run https://mi-web.com -r respuestas.yaml --sus-csv sus.csv

# Usarlo en integración continua: falla si la nota baja de 7
uxaudit run https://mi-web.com --umbral 7
```

La guía completa, con todas las opciones, el cálculo de la nota y la solución de problemas, está en [GUIA_DE_USO.md](GUIA_DE_USO.md).

## Contenido del repositorio

| Archivo | Contenido |
|---|---|
| `ux-auditor (2).zip` | Código fuente del auditor (paquete Python `uxaudit`) |
| `GUIA_DE_USO.md` | Guía de instalación y uso paso a paso |
| `criterio-de-seleccion.md` | Qué estándares y referentes puntúan en la métrica, cuáles se descartan y por qué |
| `anexo-base-de-conocimiento.md` | Base de conocimiento de auditoría UX: estándares, criterios, reglas y checklists |
| `recursos/` | 18 fichas de referentes: heurísticas de Nielsen, ISO 9241 e ISO/IEC 25010, Laws of UX, Baymard, test de usabilidad, patrones oscuros… |
| `Trabajo_Equipo_UX.docx` | Memoria del trabajo en equipo |

## Tecnologías

Python · Playwright · WCAG 2.2 · Core Web Vitals · YAML · HTML

## Mi papel

- Programación del auditor.
- Diseño de las reglas de accesibilidad y UX.
- Coordinación del equipo.
- Documentación y guía de uso.

Desarrollado con apoyo de IA: Claude Code para la programación y Claude Design para el diseño.

## Autor

**Alejandro Domingo Varela** · [LinkedIn](https://www.linkedin.com/in/alejandrodomingovarela/) · [GitHub](https://github.com/alejandrodomingo05-debug)
