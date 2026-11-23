# Evidencia del curso

Imágenes y registros fabricados para el caso Enlace Andino. Ninguno sale de un equipo real. Antes de abrir cualquier archivo, verifiquen su SHA-256 contra el archivo `RESUMENES-SHA256.txt` de su carpeta.

## `sesion-3/`: memoria USB E-03 (Laboratorio 2)

| Archivo | Qué es |
|---|---|
| `E-03_abogada.dd`, `E-03_ref.dd`, `E-03_firma.dd` | Tres imágenes de la misma memoria USB E-03, de distinto origen. La guía del estudiante de la sesión 3 dice de dónde sale cada una |
| `RESUMENES-SHA256.txt` | SHA-256 de las tres |

Comparar los tres resúmenes y explicar las diferencias es parte del laboratorio.

## `sesion-4/`: teléfono EA-MV-0119 y servidor de la aplicación (Laboratorio 4)

| Archivo | Qué es |
|---|---|
| `EA-MV-0119_userdata.img` | Partición de datos (ext4) del teléfono corporativo, reducida a 32 MB para el curso |
| `EA-MV-0119_extraccion.tar` | La misma partición como extracción de sistema de archivos, el formato que procesa el analizador de Android de Autopsy |
| `E11_servidor_aplicacion.csv` | Registros del servidor de la aplicación, en UTC |
| `RESUMENES-SHA256.txt` | SHA-256 de los tres |

En Autopsy, la imagen `.img` se agrega como **Disk Image or VM File**, no como Logical Files. La guía del Laboratorio 4 explica el resto.

## Verificar

```powershell
Get-FileHash .\* -Algorithm SHA256 | Format-Table Hash, Path -AutoSize
```

En Linux o macOS: `sha256sum -c RESUMENES-SHA256.txt`.
