# Ficha del artículo

Completa esta ficha al crear el repositorio y mantenla al día. Es el único
lugar con datos propios del artículo; el README es igual en todos los
repositorios.

## Identificación

- **Título:** Uso del tiempo: ¿cuántas horas semanales dedican los ecuatorianos a la actividad física?
- **Descripción del repositorio:** Artículo para 'El Quantificador' sobre la temática del uso del tiempo
- **Autoría:** Christian Salas Márquez
- **Fecha de publicación:** 2023-06-02
- **Artículo publicado:** https://elquantificador.org/post/valores/2023-06-02-uso-del-tiempo-deportes/
- **Categoría:** Valores y comportamiento
- **Edición:** Febrero - Agosto 2023

## Estado

Publicado el 2023-06-02 (el `.Rmd` del repositorio está fechado el 2023-05-15).

## Pregunta y alcance

El artículo estudia cuántas horas semanales dedican los ecuatorianos al
ejercicio o al deporte y las compara con el tiempo que recomienda la OMS. Usa
la Encuesta Específica de Uso del Tiempo 2012 y la Encuesta Nacional
Multipropósito de Hogares de diciembre de 2019 y de diciembre de 2020, con
cobertura nacional. La unidad de análisis es la persona, y los resultados se
desagregan por sexo, grupo de edad y, para Azuay, Guayas y Pichincha, por provincia.

## Requisitos

- R: no documentada en el repositorio.
- Paquetes de R: foreign, grid, gridExtra, haven, patchwork, radiant.data,
  readr, rstudioapi, srvyr, survey, tidyverse. Los scripts los instalan con
  `if(!require(...)) install.packages(...)`; `rstudioapi` se usa con `::` sin
  instalación explícita.

## Fuentes de datos

| Fuente | Institución | Periodo | Acceso | Script |
|---|---|---|---|---|
| Encuesta Específica de Uso del Tiempo (EUT) | INEC | 2012 | Descarga automática del zip `Base EUT 2012.zip` desde el GitHub del autor; también está en `data/` | `code/deportes_download.R` |
| Encuesta Nacional Multipropósito de Hogares, personas | INEC | Diciembre 2019 | Descarga automática del CSV desde el GitHub del autor; también está en `data/` | `code/deportes_data_manipulation.R` |
| Encuesta Nacional Multipropósito de Hogares, personas y educación, actividad física y TIC | INEC | Diciembre 2020 | Descarga automática de los CSV desde el GitHub del autor; también están en `data/` | `code/deportes_data_manipulation.R` |

Enlaces oficiales citados en el artículo: EUT 2012,
https://www.ecuadorencifras.gob.ec/uso-del-tiempo-2/; Multipropósito 2019,
https://www.ecuadorencifras.gob.ec/encuesta-nacional-multiproposito-de-hogares-2019/;
Multipropósito 2020,
https://www.ecuadorencifras.gob.ec/encuesta-nacional-multiproposito-de-hogares/.
Los scripts leen las copias del repositorio `christianjaviersalasmarquez/ut-ec-semanal-deportes`
(rama `main`) mediante URL absolutas, no los archivos locales de `data/`.

## Salidas

- `images/grafico1-articulo-deporte.png`: horas semanales promedio de ejercicio o deporte por sexo, para 2012, 2019 y 2020.
- `images/grafico2-articulo-deporte.png`: horas semanales promedio por sexo y grupo de edad en los tres años.
- `images/grafico3-articulo-deporte.png`: horas semanales promedio por sexo en Azuay, Guayas y Pichincha, en los tres años.
- `report/texto-articulo-deporte.Rmd`, con sus versiones `.docx` y `.html`: texto del artículo.

## Cómo replicar en este repositorio

El README anterior solo ofrece dos formas generales (clonar con Git o
descargar el zip del repositorio) y pide tener el software instalado; los
pasos siguientes se deducen de los scripts. No hay `MASTER.R` ni `renv`.

1. Clona o descarga el repositorio y abre `ut-ec-semanal-deportes.Rproj`. El
   script de análisis fija el directorio con
   `rstudioapi::getActiveDocumentContext()`, así que hay que ejecutarlo
   desde RStudio.
2. Ejecuta `code/deportes_analysis.R`. Este script llama a
   `code/deportes_download.R`, que descarga y descomprime la base EUT 2012
   en un directorio temporal.
3. `code/deportes_analysis.R` no llama a `code/deportes_data_manipulation.R`,
   pero usa los objetos que ese script crea (por ejemplo `UT111_UT2012`).
   Ejecuta `code/deportes_data_manipulation.R` después de la descarga y
   antes del diseño muestral. Ese script lee las bases 2019 y 2020 desde
   GitHub con `read_csv2()`.
4. El análisis guarda los tres gráficos en `images/`. Para el texto,
   compila `report/texto-articulo-deporte.Rmd`.

Se requiere conexión a internet, porque ninguna base se lee de `data/`.

## README anterior

Texto del README de este repositorio antes de adoptar el README estándar,
conservado sin cambios de contenido para no perder información.

### Artículo de "El Quantificador" sobre el uso del tiempo

El presente repositorio contiene todos los archivos necesarios para reproducir el análisis del artículo sobre la temática del uso del tiempo.

Existen dos formas para replicar el análisis: 

1. Clonar el repositorio utilizando Git y ejecutar los scripts.

2. Descargar un archivo comprimido desde la página web del repositorio y ejecutar los scripts. 

En ambos casos, es necesario tener instalado el software correspondiente.
