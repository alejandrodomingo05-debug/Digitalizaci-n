# Guía de uso del UX-Auditor

**Versión 2.1 · Equipo UX · Digitalización Avanzada 2º DAM**

El UX-Auditor analiza una web y le da una nota de **0 a 10**, el **Índice IUX**, que mide la calidad de su experiencia de usuario. Además, genera un informe con cada problema encontrado, dónde está, qué norma incumple y cómo corregirlo.

> Esta guía está pensada para **Windows con CMD**. En Mac o Linux, al final hay una tabla con las diferencias.

---

## Índice

1. [Requisitos](#1-requisitos)
2. [Instalación (solo la primera vez)](#2-instalación-solo-la-primera-vez)
3. [Uso diario](#3-uso-diario)
4. [Tu primera auditoría](#4-tu-primera-auditoría)
5. [Auditar webs reales](#5-auditar-webs-reales)
6. [Cómo leer el informe](#6-cómo-leer-el-informe)
7. [Auditoría completa: cuestionario experto y SUS](#7-auditoría-completa-cuestionario-experto-y-sus)
8. [Todos los comandos y opciones](#8-todos-los-comandos-y-opciones)
9. [Configurar un proyecto (uxaudit.yaml)](#9-configurar-un-proyecto-uxaudityaml)
10. [Cómo se calcula la nota](#10-cómo-se-calcula-la-nota)
11. [Validar el auditor con webs reales (para el trabajo)](#11-validar-el-auditor-con-webs-reales-para-el-trabajo)
12. [Actualizar a una versión nueva](#12-actualizar-a-una-versión-nueva)
13. [Subir cambios a GitHub](#13-subir-cambios-a-github)
14. [Solución de problemas](#14-solución-de-problemas)
15. [Mac y Linux](#15-mac-y-linux)

---

## 1. Requisitos

| Necesitas | Cómo comprobarlo |
|---|---|
| **Python 3.10 o superior** | `python --version` |
| Unos **500 MB libres**, para el navegador interno | — |
| **Conexión a internet** para instalarlo y para auditar webs online | — |

Si `python --version` da error o abre la Microsoft Store, instala Python de una de estas formas:

- **Con winget, sin permisos de administrador:**
  ```cmd
  winget install -e --id Python.Python.3.12 --scope user
  ```
- **Desde la web:** descárgalo de [python.org/downloads](https://www.python.org/downloads/) y, en el instalador, marca **«Add python.exe to PATH»**.

Después **cierra la terminal y abre una nueva**.

---

## 2. Instalación (solo la primera vez)

1. Descomprime `ux-auditor.zip`. En esta guía suponemos que queda en `Descargas\ux-auditor`.
2. Abre la carpeta en el Explorador, escribe `cmd` en la barra de direcciones y pulsa Intro. Se abre CMD dentro de esa carpeta.
3. Ejecuta, una línea cada vez:

```cmd
python -m venv .venv
.venv\Scripts\activate.bat
pip install -e .
python -m playwright install chromium
uxaudit --version
```

| Línea | Qué hace |
|---|---|
| `python -m venv .venv` | Crea un entorno aislado para no mezclar con otros proyectos |
| `.venv\Scripts\activate.bat` | Lo activa: verás `(.venv)` al principio de la línea |
| `pip install -e .` | Instala el auditor y sus dependencias |
| `python -m playwright install chromium` | Descarga el navegador que usa el auditor (unos 150 MB) |
| `uxaudit --version` | Debe responder `uxaudit 2.1.0` |

> **¿La carpeta tiene otra carpeta dentro con el mismo nombre?** Por ejemplo, `ux-auditor (1)\ux-auditor`. Tienes que trabajar en la que contiene `pyproject.toml` y la carpeta `uxaudit`.

---

## 3. Uso diario

Cada vez que abras una terminal nueva:

```cmd
cd %USERPROFILE%\Downloads\ux-auditor
.venv\Scripts\activate.bat
```

Ya puedes usar `uxaudit`. Cambia la ruta del `cd` si lo descomprimiste en otro sitio. Si la ruta tiene espacios, ponla entre comillas:

```cmd
cd "%USERPROFILE%\Downloads\ux-auditor (1)\ux-auditor"
```

---

## 4. Tu primera auditoría

Prueba con las páginas de ejemplo que trae el proyecto:

```cmd
uxaudit run tests\fixtures\buena.html tests\fixtures\mala.html
start informes
```

`start informes` abre la carpeta de los informes. Haz doble clic en el `.html` para verlo en el navegador.

En la terminal verás un resumen como este:

```
■ Reservas · Restaurante La Marea
  D1 Accesibilidad ................................. 10.00
  D2 Usabilidad e interacción ...................... 10.00
  ...
  IUX = 8.90 / 10  →  BUENA  [modo estricto]   (0 problemas · cobertura 80 %)
  ⛔ «Excelente» exige una auditoría completa y sin fallos graves: 21 reglas de evaluación experta sin responder…
```

---

## 5. Auditar webs reales

**Una página:**
```cmd
uxaudit run https://www.gov.uk
```

**Varias páginas del mismo sitio.** Así también comprueba que el menú y la ayuda sean iguales en todas:
```cmd
uxaudit run https://www.gov.uk https://www.gov.uk/browse/driving https://www.gov.uk/contact --proyecto "GOV.UK"
```

**Un fichero o una carpeta de tu proyecto:**
```cmd
uxaudit run C:\ruta\a\mi-web\index.html
uxaudit run C:\ruta\a\mi-web
```

**Una web que tengas arrancada en local** (Vite, Live Server…):
```cmd
uxaudit run http://localhost:5173
```

**Con informe en los tres formatos:**
```cmd
uxaudit run https://mi-web.com -f html,json,md
```

> Cada página tarda alrededor de **1 minuto**. El auditor la abre en móvil y en escritorio, mide el rendimiento con un 4G lento, prueba el teclado, el modo oscuro, el alto contraste, la letra grande, varios anchos de pantalla, etc.

**Buenas prácticas:**

- Audita solo páginas públicas. Las que exigen iniciar sesión no se pueden auditar.
- No lances decenas de auditorías seguidas contra la misma web ajena.
- El auditor **nunca acepta las cookies**: evalúa lo que ve un visitante nuevo.

---

## 6. Cómo leer el informe

El informe HTML es un único fichero que puedes abrir sin conexión o enviar por correo. Tiene estas partes:

| Parte | Qué significa |
|---|---|
| **Nota grande (IUX)** | Nota final de 0 a 10 y su nivel: Excelente, Buena, Aceptable, Deficiente o Crítica |
| **Techos aplicados** (cuadro rojo) | Por qué la nota está limitada; por ejemplo, un fallo crítico la deja en 4,9 como máximo |
| **Nota provisional** (cuadro azul) | Faltan respuestas del cuestionario experto (ver apartado 7) |
| **Nota por dimensión** | Barras de D1 a D8 con su peso |
| **Rendimiento** | LCP (carga), CLS (estabilidad), TBT (bloqueo), peso de la página y peticiones |
| **Capturas** | Cómo se ve la página en móvil y escritorio |
| **Problemas detectados** | Lista ordenada por gravedad (ver abajo) |
| **Reglas superadas / No aplicables** | Lo que está bien y lo que no se pudo comprobar |

**Cada problema muestra:**

- la **gravedad**: Crítica, Alta, Media o Baja;
- el **estado**: No cumple o Cumple parcialmente;
- lo **medido**, por ejemplo «3 de 20 elementos correctos»;
- la **norma** que incumple, por ejemplo «WCAG 2.2 · 1.4.3»;
- **cómo corregirlo** y **qué evitar**;
- los **elementos afectados**, con el selector CSS para encontrarlos en el código;
- la recomendación de **UI UX Pro Max**, con un ejemplo de código correcto.

**Las 8 dimensiones:**

| | Dimensión | Peso | Ejemplos de lo que revisa |
|---|---|---|---|
| D1 | Accesibilidad | 25 % | Contraste, texto alternativo, teclado real, foco visible, letra al 200 %, alto contraste, modo oscuro |
| D2 | Usabilidad e interacción | 15 % | Tamaño de botones, que lo clicable se vea clicable, una sola acción principal |
| D3 | Rendimiento | 15 % | Velocidad de carga, estabilidad, peso, imágenes |
| D4 | Diseño visual y contenido | 10 % | Tamaño de letra, tablets y móvil en horizontal, legibilidad, palabras innecesarias |
| D5 | Formularios | 10 % | Etiquetas, campos obligatorios, autocompletado, permitir pegar contraseñas |
| D6 | Navegación | 10 % | Prueba del tronco de Krug, menús, «saltar al contenido», coherencia entre páginas |
| D7 | Satisfacción | 5 % | Prueba con usuarios (SUS) y pruebas al estilo de Krug |
| D8 | Ética, privacidad y sostenibilidad | 10 % | Banner de cookies justo, rastreo sin permiso, patrones oscuros, CO2 por visita |

---

## 7. Auditoría completa: cuestionario experto y SUS

Hay cosas que una máquina no puede juzgar, como si los textos se entienden o si la portada explica qué es la web. Para eso existen **21 preguntas expertas**: las heurísticas de Nielsen, los principios de Steve Krug, los costes ocultos, darse de baja, la transparencia de la IA…

> Mientras no las respondas, la nota es **provisional** y no puede pasar de **8,9**: «Excelente» exige la auditoría completa.

### 7.1 Responder el cuestionario

```cmd
uxaudit manual
```

Te hace las preguntas una a una. Responde con una letra:

| Tecla | Significa |
|---|---|
| `c` | Cumple |
| `p` | Cumple parcialmente |
| `n` | No cumple |
| `x` | No aplica (por ejemplo, la pregunta de IA si la web no usa IA) |
| `Intro` | Saltar o mantener la respuesta anterior |
| `q` | Guardar y salir |

Las respuestas se guardan en `respuestas.yaml`. También puedes editar ese fichero a mano con el Bloc de notas: `notepad respuestas.yaml`.

### 7.2 Prueba con usuarios (SUS)

1. Pide a **3–5 personas** que hagan una tarea real en la web, por ejemplo «reserva una mesa para dos».
2. Al terminar, cada una responde el cuestionario SUS: 10 preguntas puntuadas del 1 al 5.
3. Apunta las respuestas en un CSV con una fila por persona. Tienes un ejemplo en `ejemplos\sus.csv`:
   ```
   participante,q1,q2,q3,q4,q5,q6,q7,q8,q9,q10
   P1,4,2,4,2,5,1,4,2,4,2
   P2,5,1,4,2,4,2,5,1,4,1
   ```

### 7.3 Auditar con todo

```cmd
uxaudit run https://mi-web.com -r respuestas.yaml --sus-csv sus.csv -f html,json,md
```

Si ya tienes la nota SUS calculada, usa `--sus 78` en lugar de `--sus-csv`.

---

## 8. Todos los comandos y opciones

### Comandos

| Comando | Para qué sirve |
|---|---|
| `uxaudit run <web> [<web>…]` | Audita una o varias páginas (hasta 20) |
| `uxaudit init` | Crea `uxaudit.yaml` (configuración) y `respuestas.yaml` (cuestionario vacío) |
| `uxaudit manual` | Cuestionario experto interactivo |
| `uxaudit reglas` | Lista las 100 reglas; filtra con `--dimension D8` o `--tipo manual` |
| `uxaudit historial` | Evolución de la nota entre auditorías (▲ mejora, ▼ empeora) |
| `uxaudit kb "consulta"` | Busca en la base de conocimiento de UI UX Pro Max; por ejemplo, `uxaudit kb "touch target size"` |
| `uxaudit --version` | Muestra la versión |
| `uxaudit run --help` | Ayuda con todas las opciones |

### Opciones de `uxaudit run`

| Opción | Qué hace |
|---|---|
| `-o carpeta` | Carpeta donde se guardan los informes (por defecto `informes`) |
| `-f html,json,md` | Formatos del informe (por defecto `html,json`) |
| `-r respuestas.yaml` | Usa las respuestas del cuestionario experto |
| `--sus-csv sus.csv` / `--sus 78` | Añade la prueba con usuarios |
| `--proyecto "Nombre"` | Nombre que aparece en el informe |
| `--modo estricto` / `--modo estandar` | Nivel de exigencia (por defecto, estricto) |
| `--umbral 7` | Nota mínima; si no se alcanza, el programa termina con código 1 (útil en CI) |
| `--perfil web` / `movil` / `escritorio` | En qué pantallas se prueba (por defecto, móvil y escritorio) |
| `-c uxaudit.yaml` | Usa un fichero de configuración concreto |
| `--sin-capturas` | No incluye capturas; el informe pesa menos |
| `--sin-rendimiento` | No mide la velocidad; es más rápido |
| `--sin-teclado` | No hace la prueba con la tecla Tab |
| `--bloquear-redes-privadas` | No permite acceder a localhost ni a redes internas (recomendado en servidores compartidos) |
| `--urls-completas` | Muestra las URLs con sus parámetros (por defecto se ocultan, porque pueden llevar tokens) |
| `-q` | Modo silencioso: solo muestra errores |

### Códigos de salida (para scripts y CI)

| Código | Significado |
|---|---|
| `0` | Todo correcto (y, si hay umbral, superado) |
| `1` | Nota por debajo del umbral |
| `2` | Error de uso, de configuración o entrada rechazada por seguridad |
| `3` | Alguna página no se pudo auditar |

---

## 9. Configurar un proyecto (`uxaudit.yaml`)

Para no repetir opciones en cada comando, crea un fichero de configuración en la carpeta desde la que ejecutas el auditor:

```cmd
uxaudit init
notepad uxaudit.yaml
```

El auditor lo usa automáticamente si está en la carpeta actual. Las claves más útiles:

```yaml
proyecto: Web del restaurante
perfil: web                     # web | movil | escritorio
modo: estricto                  # estricto | estandar
pesos: {D1: 25, D2: 15, D3: 15, D4: 10, D5: 10, D6: 10, D7: 5, D8: 10}
umbral_ci: 7.0
reglas_desactivadas: [NAV-BARRA-INFERIOR]   # reglas que no aplican a tu proyecto
severidades: {INT-CURSOR: media}            # cambiar la gravedad de una regla
tiempo_maximo_s: 45             # súbelo (90) si la web es lenta
espera_tras_carga_ms: 1500
capturas: true
teclado: true
rendimiento: {activado: true, limitar_red_y_cpu: true}
bloquear_redes_privadas: false
redactar_urls: true
```

> Si escribes mal una clave, el auditor te avisa con un error en lugar de ignorarla. Para ver los identificadores de las reglas: `uxaudit reglas`.

---

## 10. Cómo se calcula la nota

1. **Cada regla tiene una gravedad** que fija su peso: Crítica 4, Alta 3, Media 2, Baja 1.
2. **Cada regla se valora** como Cumple (1), Parcial (0,5) o No cumple (0). Las métricas, como la velocidad o la legibilidad, usan una escala continua.
3. **Nota de cada dimensión:** `10 × Σ(peso × resultado) / Σ peso`.
4. **IUX:** media ponderada de las dimensiones según su peso (25 %, 15 %…). Si una dimensión no tiene datos, como D7 sin prueba con usuarios, se reparte su peso entre las demás.
5. **Techos en modo estricto** (el predeterminado):

| Situación | Nota máxima |
|---|---|
| Alguna regla **crítica** incumplida, en cualquier dimensión | **4,9** |
| Alguna regla **alta** de accesibilidad incumplida | **6,9** |
| Falta el cuestionario experto, la cobertura es menor del 90 % o hay reglas altas o críticas sin cumplir del todo | **8,9** (no puede ser «Excelente») |

**Niveles:** 9–10 Excelente · 7–8,9 Buena · 5–6,9 Aceptable · 3–4,9 Deficiente · 0–2,9 Crítica.

**El modo estándar** (`--modo estandar`) es más permisivo: solo limita los fallos críticos de accesibilidad y usa los umbrales de velocidad de Google. Sirve para las primeras versiones de una web.

---

## 11. Validar el auditor con webs reales (para el trabajo)

Así se demuestra que la nota tiene sentido y que el auditor cubre lo que otras herramientas no:

1. **Elige 5–10 webs variadas:**
   - un referente de accesibilidad: `https://www.gov.uk` o `https://www.w3.org/WAI/`;
   - una web de la Administración;
   - una tienda online grande;
   - un periódico digital;
   - una web pequeña: un restaurante, una tienda del barrio, la web del instituto.
2. **Antes de auditar**, cada miembro del equipo pone una nota de 0 a 10 solo navegando.
3. **Pasa el auditor** a cada web y apunta el IUX, el nivel y los 3 problemas principales.
4. **Pasa Lighthouse**: en Chrome, pulsa F12 → pestaña **Lighthouse** → **Analizar**. Apunta la nota de accesibilidad.
5. **Compara los resultados en una tabla:**

| Web | Nota del equipo | IUX | Lighthouse (accesibilidad) | Problemas que solo detecta el UX-Auditor |
|---|---|---|---|---|
| … | … | … | … | p. ej., banner sin «Rechazar», Google Analytics antes del consentimiento |

> Es habitual que una web tenga 90–100 en Lighthouse y suspenda en el UX-Auditor por las cookies, el rastreo o el teclado. Eso es justo lo que demuestra el análisis de huecos del apartado 2.3 del trabajo.

---

## 12. Actualizar a una versión nueva

1. Descomprime el zip nuevo **encima** de la carpeta anterior (sustituye los ficheros). Si Windows crea una carpeta nueva, como `ux-auditor (1)`, trabaja en ella y repite la instalación del apartado 2.
2. Con el entorno activado:
   ```cmd
   pip install -e .
   uxaudit --version
   ```

---

## 13. Subir cambios a GitHub

En el repositorio del equipo, la rama `main` está **protegida**: no se puede subir directamente a ella.

1. En GitHub Desktop: **Branch → New branch…** y ponle un nombre, por ejemplo `Inicial-ux`.
2. Haz commit de tus cambios en esa rama y pulsa **Publish branch** o **Push origin**.
3. Pulsa **Create Pull Request** y rellena el título y la descripción en el navegador.
4. El profesor o un administrador revisa la pull request y la fusiona con **Merge**.

> Si aparece «Merging is blocked · Cannot update this protected ref», solo puede fusionarla alguien con permisos especiales. Avisa al responsable del repositorio.

No subas las carpetas `.venv` ni `informes`. El fichero `.gitignore` del proyecto ya las excluye.

---

## 14. Solución de problemas

| Problema | Solución |
|---|---|
| `Python was not found` o se abre la Microsoft Store | Python no está instalado; ver el apartado 1 |
| `"uxaudit" no se reconoce como comando` | Activa el entorno: `.venv\Scripts\activate.bat`. O usa `python -m uxaudit run …` |
| `.venv\Scripts\activate.bat` da error en rojo con `Import-Module` | Estás en **PowerShell**: escribe `cmd` y repite. En PowerShell se usa `.venv\Scripts\Activate.ps1` |
| PowerShell: «la ejecución de scripts está deshabilitada» | Usa CMD, o ejecuta `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` (solo afecta a esa ventana) |
| `El módulo '.venv' no pudo cargarse` o no existe `.venv` | Estás en otra carpeta: entra en la que tiene `pyproject.toml`. Si es una carpeta nueva, repite el apartado 2 |
| `No se pudo iniciar Chromium` | `python -m playwright install chromium` |
| «Tiempo máximo de auditoría superado» | La web es lenta o tiene un bucle infinito. Sube `tiempo_maximo_s` a 90 en `uxaudit.yaml` |
| «No se pudo abrir la página» | Revisa la URL. Algunas webs bloquean navegadores automáticos (Cloudflare, captchas): prueba con otra |
| «El servidor respondió con el código HTTP 404/500» | La página no existe o da error; no se puntúa para no falsear la nota |
| «Bloqueado por seguridad» | La web intentó redirigir a una dirección interna o de metadatos de la nube; el auditor lo impide a propósito |
| La nota no pasa de 8,9 | Falta el cuestionario experto (`uxaudit manual`) o hay alguna regla alta sin cumplir del todo; mira el cuadro rojo del informe |
| «Aviso: se ejecuta como root…» | Solo aparece en Linux o Docker; usa un usuario normal para auditar webs desconocidas |

---

## 15. Mac y Linux

Todo es igual salvo:

| Windows (CMD) | Mac / Linux |
|---|---|
| `python` | `python3` |
| `.venv\Scripts\activate.bat` | `source .venv/bin/activate` |
| `start informes` | `open informes` (Mac) o `xdg-open informes` (Linux) |
| `tests\fixtures\buena.html` | `tests/fixtures/buena.html` |
| `notepad uxaudit.yaml` | `nano uxaudit.yaml` |

---

*Más detalles técnicos en `README.md` y medidas de seguridad en `SECURITY.md`.*
