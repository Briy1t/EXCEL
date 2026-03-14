# Excel para la fase PREPARAR
Excel (o Google Sheets) es una herramienta fundamental en la fase Preparar, porque permite organizar, limpiar y estructurar los datos antes de procesarlos o analizarlos. 
Su objetivo aquí no es hacer análisis avanzados, sino dejar los datos listos, coherentes y utilizables.

## Organización inicial de los datos
- Encabezados claros, únicos y consistentes.
- Tipos de datos correctos (texto, número, fecha, booleano).
- Columnas bien definidas, sin mezclar información.
- Eliminación de filas vacías o irrelevantes.
- Revisión de formatos (fechas, decimales, separadores).

## Herramientas de limpieza

|Herramienta |	Para qué sirve |
|:--|:--|
|Buscar y reemplazar |	Corregir valores repetidos o inconsistentes.|
|Texto en columnas	|Separar datos combinados en una sola celda.|
|Quitar duplicados	|Eliminar registros repetidos. |
|Validación de datos	|Evitar errores de entrada (listas, rangos, reglas).|
|Formato condicional |	Detectar valores anómalos o inconsistentes. |
|Filtros	| Revisar valores únicos, detectar errores y vacíos. |

### Funciones esenciales para preparar datos

|Función |	Uso |
|:--|:--|
|TRIM() |	Eliminar espacios innecesarios. |
|CLEAN()	|Quitar caracteres no imprimibles.|
|UPPER() / LOWER() |	Normalizar texto. |
|LEFT() / RIGHT() / MID() |	Extraer partes de texto.|
|LEN()	|Contar caracteres.| 
|CONCAT() / TEXTJOIN() |	Unir columnas.|
|IF() |	Crear reglas condicionales.|
|COUNTIF() / COUNTIFS()	|Contar condiciones. |
|VLOOKUP() / XLOOKUP()	|Unir tablas o buscar valores. |
|UNIQUE()	|Obtener valores únicos. |
|SORT()	|Ordenar datos. |
|FILTER()	|Filtrar dinámicamente. |
|ISBLANK()	|Detectar celdas vacías. |

## Técnicas de normalización
- Convertir todo el texto a mayúsculas o minúsculas.
- Unificar formatos de fecha.
- Estandarizar categorías (ej.: “Sí”, “si”, “SI” → “Sí”).
- Separar datos combinados (nombre + apellido, ciudad + código postal).
- Crear columnas derivadas (año, mes, día, rango, categoría).

## Preparación estructural
- Crear una tabla oficial (Ctrl + T) para activar filtros y referencias estructuradas.
- Nombrar rangos y columnas para facilitar búsquedas.
- Dividir datasets grandes en hojas temáticas (ventas, clientes, productos).
- Documentar cambios importantes en una hoja de “registro”.

## Detección de errores comunes
- Fechas que Excel interpreta como texto.
- Números almacenados como texto.
- Celdas con espacios invisibles.
- Valores inconsistentes en categorías.
- Duplicados no detectados.
- Filas con desplazamientos (columnas corridas).

## Preparación para unir datos
- Excel permite combinar datasets antes de procesarlos:
- Unir por claves con `XLOOKUP()` o `VLOOKUP()`.
- Crear claves únicas concatenando columnas.
- Alinear encabezados entre hojas.
- Convertir todo a un mismo formato (CSV recomendado para limpieza).

## Preparación para análisis posterior
- Crear una hoja “limpia” separada del dataset original.
- Mantener una copia sin modificar para trazabilidad.
- Asegurar que cada columna contiene un solo tipo de dato.
- Verificar que no existan valores imposibles (ej.: edades negativas).
- Crear columnas auxiliares para facilitar filtros y segmentaciones.
