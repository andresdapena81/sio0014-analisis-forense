# SIO0014 · Análisis Forense en Sistemas de Información

Material del módulo **Análisis Forense en Sistemas de Información** de la **Especialización en Seguridad de la Información de las Organizaciones**, Facultad de Ingeniería de la **Institución Universitaria de Envigado**.

El módulo se dicta sobre un caso de estudio continuo: **Enlace Andino**, una empresa ficticia de mensajería y recaudo contra entrega. Hay seis encuentros, del 5 al 24 de noviembre de 2026. La evidencia se adquiere, se verifica y se analiza sesión a sesión. Todo el trabajo alimenta tres entregas: la adquisición, el informe técnico y el dictamen pericial.

> **Sitio del curso:** los laboratorios se abren con un clic en
> **https://andresdapena81.github.io/sio0014-analisis-forense/**

---

## Cómo se usan los laboratorios

Los laboratorios interactivos son **archivos HTML autocontenidos**. Se descargan y se abren con doble clic en cualquier navegador moderno.

- **No requieren conexión a internet** y **no envían información a ningún servidor.**
- Las respuestas se guardan en el navegador del estudiante (almacenamiento local). Si se borran los datos del navegador, se pierden.
- Para descargar uno: entren al archivo en [`laboratorios/`](laboratorios/), pulsen **Download raw file** y ábranlo.

| Laboratorio | Título | Sesión | Evidencia |
|---|---|---|---|
| [Práctica de resúmenes](laboratorios/Practica-resumenes-SIO0014.html) | ¿Qué cambia un resumen? | 2 | En el navegador |
| [Laboratorio 1](laboratorios/Laboratorio-1-SIO0014.html) | Verificar antes de creer | 2 | En el navegador |
| [Laboratorio 2](laboratorios/Laboratorio-2-SIO0014.html) | Del artefacto a la línea de tiempo | 3 | [`evidencia/sesion-3/`](evidencia/sesion-3/) |
| [Laboratorio 3](laboratorios/Laboratorio-3-SIO0014.html) | Lo que sobrevivió al reinicio (memoria) | 5 | En el laboratorio |
| [Laboratorio 4](laboratorios/Laboratorio%204%20-%20Practica%20con%20Autopsy%20-%20SIO0014.pdf) | El teléfono del repartidor: práctica con Autopsy (PDF) | 5 | [`evidencia/sesion-4/`](evidencia/sesion-4/) |
| [Laboratorio 5](laboratorios/Laboratorio-5-SIO0014.html) | La llave que estaba en la imagen (nube y contenedores) | 5 | En el laboratorio |

---

## Qué hay en cada carpeta

- **[`caso/`](caso/)**: el caso Enlace Andino. La Parte A se lee desde la sesión 1. La Parte B llega en la sesión 5 y trae la evidencia de la defensa.
- **[`guias/`](guias/)**: la guía del método forense, la guía de adquisición en la práctica, la guía del estudiante de la sesión 3 y las guías de las entregas 1, 2 y 3.
- **[`actividades/`](actividades/)**: las hojas de actividades de las sesiones 1, 2 y 5 y el diagnóstico inicial.
- **[`laboratorios/`](laboratorios/)**: los laboratorios, como en la tabla de arriba.
- **[`evidencia/`](evidencia/)**: las imágenes y registros que se analizan, cada uno con su archivo `RESUMENES-SHA256.txt`. Ver [`evidencia/README.md`](evidencia/README.md).
- **[`presentaciones/`](presentaciones/)**: las presentaciones de las sesiones 1 a 6, en PowerPoint y en PDF.
- **[`retos/`](retos/)**: prácticas voluntarias fuera del caso. La primera es el [Data Leakage Case del NIST](retos/data-leakage/): un computador con Windows, dos USB y un CD, analizados solo con Autopsy para Windows, en una sesión de dos horas.

---

## Herramientas

- **Un navegador moderno**, para los laboratorios HTML.
- **[Autopsy](https://www.autopsy.com/download/)** 4.22 o posterior, para Windows (gratuito). Se usa en el Laboratorio 4 y en el reto Data Leakage.
- **PowerShell** (viene con Windows), para calcular resúmenes: `Get-FileHash .\archivo -Algorithm SHA256`.
- Opcional: [The Sleuth Kit](https://www.sleuthkit.org/), en la línea de comandos de Linux o macOS.

---

## Verificar antes de analizar

Toda evidencia se verifica antes de abrirla. En la carpeta de cada sesión:

```powershell
Get-FileHash .\* -Algorithm SHA256 | Format-Table Hash, Path -AutoSize
```

Comparen cada valor con el de `RESUMENES-SHA256.txt`. Si uno no coincide, no lo analicen: descárguenlo otra vez. El repositorio marca estos archivos como binarios para que Git no les cambie los finales de línea.

---

## Sobre el caso

**Enlace Andino no existe.** Es un caso construido para este módulo. Las personas, empresas, cuentas, direcciones IP, teléfonos y documentos son inventados. Las imágenes forenses del curso se fabricaron a propósito y no salen de ningún equipo real. Las direcciones IP públicas del caso son de los rangos reservados para documentación (RFC 5737). El reto Data Leakage es material público del NIST, con sus propios personajes ficticios.

---

## Créditos y licencia

Material docente de la Institución Universitaria de Envigado, Facultad de Ingeniería.
Autor: Jorge Andrés Dapena Ossa.

Publicado bajo licencia **Creative Commons Atribución-CompartirIgual 4.0 Internacional (CC BY-SA 4.0)**. Se puede usar, adaptar y redistribuir citando la fuente y manteniendo la misma licencia. Ver [`LICENSE`](LICENSE).

El escudo y el nombre de la Institución Universitaria de Envigado son marcas de la Institución y no quedan cubiertos por la licencia. Las imágenes y preguntas del Data Leakage Case son del NIST (CFReDS); el repositorio solo trae la guía en español y una lista de resúmenes.
