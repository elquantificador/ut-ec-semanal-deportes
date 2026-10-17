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
  readr, srvyr, survey, tidyverse. Los scripts los instalan con
  `if(!require(...)) install.packages(...)`.

## Fuentes de datos

| Fuente | Institución | Periodo | Acceso | Script |
|---|---|---|---|---|
| Encuesta Específica de Uso del Tiempo (EUT) | INEC | 2012 | Lee `data/Base EUT 2012.zip`; si falta, lo descarga del GitHub del autor | `code/deportes_download.R` |
| Encuesta Nacional Multipropósito de Hogares, personas | INEC | Diciembre 2019 | Lee el CSV de `data/`; si falta, lo descarga del GitHub del autor | `code/deportes_data_manipulation.R` |
| Encuesta Nacional Multipropósito de Hogares, personas y educación, actividad física y TIC | INEC | Diciembre 2020 | Lee los CSV de `data/`; si faltan, los descarga del GitHub del autor | `code/deportes_data_manipulation.R` |

Enlaces oficiales citados en el artículo: EUT 2012,
https://www.ecuadorencifras.gob.ec/uso-del-tiempo-2/; Multipropósito 2019,
https://www.ecuadorencifras.gob.ec/encuesta-nacional-multiproposito-de-hogares-2019/;
Multipropósito 2020,
https://www.ecuadorencifras.gob.ec/encuesta-nacional-multiproposito-de-hogares/.
Los scripts leen primero las copias locales de `data/`; la URL del repositorio
`christianjaviersalasmarquez/ut-ec-semanal-deportes` (rama `main`) es solo respaldo.
Las copias locales tienen el mismo contenido que esa descarga.

## Salidas

- `images/grafico1-articulo-deporte.png`: horas semanales promedio de ejercicio o deporte por sexo, para 2012, 2019 y 2020.
- `images/grafico2-articulo-deporte.png`: horas semanales promedio por sexo y grupo de edad en los tres años.
- `images/grafico3-articulo-deporte.png`: horas semanales promedio por sexo en Azuay, Guayas y Pichincha, en los tres años.
- `report/texto-articulo-deporte.Rmd`, con sus versiones `.docx` y `.html`: texto del artículo.

## Cómo replicar en este repositorio

El README anterior solo ofrece dos formas generales (clonar con Git o
descargar el zip del repositorio) y pide tener el software instalado; los
pasos siguientes se deducen de los scripts. No hay `MASTER.R` ni `renv`.

1. Clona o descarga el repositorio y abre `ut-ec-semanal-deportes.Rproj`,
   o bien ejecuta R desde la raíz del repositorio. Las rutas son relativas a
   esa raíz, así que no hace falta RStudio.
2. Ejecuta `code/deportes_analysis.R`. Este script llama, en orden, a
   `code/deportes_download.R` (descomprime la base EUT 2012 desde
   `data/Base EUT 2012.zip` en un directorio temporal) y a
   `code/deportes_data_manipulation.R` (lee la EUT 2012 y las bases 2019 y
   2020 de `data/` y crea objetos como `UT111_UT2012`).
3. El análisis guarda los tres gráficos en `images/`. Para el texto,
   compila `report/texto-articulo-deporte.Rmd`.

Solo se necesita conexión a internet para instalar paquetes o si falta algún
archivo de `data/`.

## README anterior

Texto del README de este repositorio antes de adoptar el README estándar,
conservado sin cambios de contenido para no perder información.

### Artículo de "El Quantificador" sobre el uso del tiempo

El presente repositorio contiene todos los archivos necesarios para reproducir el análisis del artículo sobre la temática del uso del tiempo.

Existen dos formas para replicar el análisis: 

1. Clonar el repositorio utilizando Git y ejecutar los scripts.

2. Descargar un archivo comprimido desde la página web del repositorio y ejecutar los scripts. 

En ambos casos, es necesario tener instalado el software correspondiente.
