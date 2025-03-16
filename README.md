# TÍTULO: EDA Dashboard Proyect G.Sheets
Primer Proyecto de EDA y Dashboard en Google Sheets.
Datos de Goodreads enfocados en las valoraciones otorgadas a diferentes libros y las caractreísticas de los mismos.


El README es la carta de presentación del proyecto, lo creo ahora para tenerlo y saber cómo editar y resuibr cosas. Luego tocará ir haciéndolo de verdad. 

## Paso a paso
Cargo los datos del archivo CSV en Google Sheets. Decido trabajar con la configuración de Google Sheets en EEUU porque debido al formato de columnas como el tipo fecha y después de haber tratado los datos inicialmente con la configuración de España, esta resulta la opción más conveniente. 

En primer lugar observo la información y trato de familiarizarme con ella. Hay dos tipos de datos, por un lado columnas sobre las características de los libros (título, autor, idioma, nº de páginas, fecha de publicación, y editorial); y por otro, sobre las opiniones de los usuarios de la plataforma sobre los mismos (valoración media, número de valoraciones y número de reseñas de texto). Esto hace que el análisis se enfoque hacia las valoraciones e interacciones con los libros en función de las diferentes características de estos.

## Transformación y lmpieza de datos
_Identificación de duplicados y tratamiento de nulos:_ En primer lugar, me fijo en la columna “BookId”, que indica el número de identificación de cada libro y al ser un valor único para cada libro no puede repetirse. En las estadísticas de la columna que nos ofrece Google Sheets, veo que hay 11.129 filas y 11.127 valores únicos, y se señala también la existencia de 2 celdas vacías. Hay por tanto dos valores nulos, pero no duplicados. Al filtrar en la columna por condición de celdas vacías, vemos que las filas que no tienen este valor no tienen ningún otro tampoco y son eliminadas. 
Observado las estadísticas de todas las otras columnas, no hay celdas vacías en ninguna otra a excepción de una en la columna ISBN.

Las columnas referentes al ISBN indican otros números identificadores de 10 dígitos y 13 en el caso de ISBN13, por lo que debería tratarse también de valores únicos. Las estadísticas de la columna indican que no es así, y al atender a los valores encuentro valores de escasos dígitos. Filtrándolos compruebo que se debe a un error de 4 filas en la carga de datos (las comas en las autorías de 4 lirbos han desplazado todas las columnas a la izquierda y ese número correspondería a la valoración). Corrijo este error y compruebo que tras esto finalmente no hay duplicados ni celdas vacías.

_Formato de los datos:_ Al trabajar con la configuración de EEUU no es necesario buscar y reemplazar puntos por comas para que los números se identifiquen como tales, así que puedo cambiar directamente en formato seleccionando la columna y el formato deseado. 

## Identificación de patrones y anomalías 
Creo una nueva hoja para generar en ella tablas dinámicas y gráficos que me ayuden con esta tarea.
Primero compruebo las tendencias que hay en la propia plataforma en el tipo de libros que contiene. 

_Títulos:_ Parametros por las estadísticas de columna

_Autores:_ Lo mismo, poner bonito ambos

_Idioma:_ Hay 27 idiomas diferentes, pero la mayoría de ellos cuentan con una cantidad irrelevante de libros (1, 3, 7...) teniendo en cuenta el conjunto de 11.127 con el que trabajamos. Por ello creo la categoría "otros" para reunir los idiomas minoritarios (menos de 100 libros) y poder lograr una visualización comprensible de los datos sin eliminar datos. Aun así la predominancia del inglés es absoluta.

_Número de páginas:_ 0 ¿OUTLIERS?

_Fecha de publicación:_ Muy pocos valores antes de 1950, considerar borrar esos datos porque pueden ser OUTLIERS

_Editorial:_ Las que más tienen rondan los 300 / 200 o así, habiendo muchas editoriales con un sólo libro publicado. Es problemático, considerar qué hacemos con ello.

LUEGO IRÁN LAS COLUMNAS DE INTERACIONES DE CLIENTES, TODAS NUMÉRICAS Y MÁS CHILL SUPONGO


## Estructura del repositorio
```bash
|--- Data
   |-- Nombre archivo de datos.csv #Datos originales
|--- G_Sheets #Enlace al google Sheets si lo pongo en un archivo aparte 
```
## Para un apartado
Y demás texto... Poner también conclusiones

Poner foto a modo de header
Se pueden añadir emojis para que no sea un tostón

Dice la profe que Chatgpt hace muy buenos readme.