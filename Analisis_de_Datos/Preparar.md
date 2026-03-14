# Preparar los Datos para la Exploración
La fase Preparar del proceso analítico consiste en recopilar, seleccionar, estructurar y transformar los datos necesarios para responder una pregunta. Es una etapa estratégica: determina qué información estará disponible y en qué condiciones se podrá analizar.

## Fuentes de datos
Los datos pueden provenir de distintos orígenes, cada uno con ventajas y limitaciones. Elegir la fuente adecuada depende del problema, del tiempo disponible y del nivel de precisión necesario.

--- 
**Tipos de fuentes**
| Tipo de fuente |	Quién la genera	Ventajas	| Riesgos / Limitaciones	Ejemplos | 
|:--|:--|:--|
|Primaria	Tú o tu empresa	| Control total, datos exactos | 	Costosa, lenta	Encuestas propias, entrevistas | 
|Secundaria	Otra organización |	Rápida, económica	Puede no ajustarse al problema	| Informes de analítica, estudios |
|Terciaria 	Proveedores externos	| Gran volumen, múltiples fuentes	Menos control, calidad variable |	Datos agregados, cookies |

Selección de datos relevantes
- No todos los datos útiles son relevantes. La selección debe centrarse en la pregunta del negocio.
- Si analizas tendencias, necesitas datos con fechas.
- Si analizas segmentos, necesitas atributos que diferencien grupos.
- Si analizas comportamientos, necesitas datos transaccionales o de uso.
---
 **Regla clave**: un dato es relevante solo si contribuye directamente a responder la pregunta.

- Cantidad de datos necesaria :La cantidad depende del tipo de análisis.

| Tipo de proyecto	| Cantidad recomendada|	Ejemplo |
|:--|:--|:--|
| Exploratorio	| Muestra aleatoria	|Opiniones generales |
| Segmentado |	Muestra estratégica	|Solo clientes VIP|
| Profundo	| Gran volumen	|Series temporales largas|

---
**Marco temporal**
- El tiempo influye en la utilidad de los datos.

|Situación |	Tipo de datos |	Motivo |
|:--|:--|:--|
|Necesitas resultados rápidos |	Históricos	|Ya disponibles |
|Puedes esperar |	Nuevos	| Reflejan comportamiento actual |
|Proyecto continuo	| Tiempo real |	Ideal para dashboards

**Transformación de datos** :Transformar datos significa modificarlos para hacerlos más útiles, compatibles o claros.

### Acciones comunes
- Añadir o eliminar columnas
- Normalizar nombres
- Unir datasets
- Cambiar formatos (CSV, XLSX, JSON)
- Reorganizar filas y columnas

## Para qué sirve

| Objetivo |	Explicación |
|Organización	| Datos más ordenados → análisis más fácil |
| Compatibilidad	 | Permite usar datos en distintos sistemas |
| Migración |	Mover datos sin errores  |
| Fusión	| Combinar bases de datos |
| Mejora	| Añadir claridad o detalle | 
|Comparación| Facilita análisis entre datasets |

## Datos largos vs datos anchos
Formato	Características	Cuándo usarlo	**Ejemplo**:

- Largo (long)	Cada fila = un punto de dato	Modelos estadísticos, series temporales	AAPL – 01/01 – 150
- Ancho (wide)	Cada fila = varios datos del mismo sujeto	Gráficos simples, comparaciones	Fecha – AAPL – AMZN

## Tipos de datos en la práctica
| Clasificación	| Definición |	Ejemplos |
|:--|:--|:--|
| Primarios |	Recogidos por ti	|Encuestas|
|Secundarios	|Recogidos por otros| Datos censales | 
|Internos	|Dentro de la empresa |	Ventas |
|Externos	|Fuera de la empresa	| Datos demográficos |
|Continuos |	Se miden	| Temperatura |
|Discretos |	Se cuentan |	Número de visitas |
|Cualitativos |	Opiniones	| Preferencias |
|Cuantitativos	| Cantidades	| Porcentajes |
|Nominales |	Sin orden |	Color |
|Ordinales |	Con orden	| Satisfacción 1–5 |
|Estructurados |	Filas y columnas	| Bases de datos |
|No estructurados	| No caben en tablas	| Vídeos, emails |


## Lógica booleana para filtrar datos

|Operador	|Función	|Ejemplo	| Resultado |
|:--|:--|:--|:--|
|AND |	Ambas condiciones	|Gris AND Rosa |	Solo valores que cumplan ambas |
|OR	vUna condición |	Gris OR Rosa	| Cualquier valor que cumpla una |
|NOT	|Excluir	|Gris AND NOT Rosa	|Gris que no sea rosa |

## Selección de herramientas

|Herramienta	|Mejor para	Ventajas	|Limitaciones |
|Excel / Sheets|	Limpieza, informes rápidos	|Fácil, accesible	No ideal para grandes datasets |
|Tableau |	Dashboards interactivos |	Potente, visual	Requiere más tiempo |


### Small Data vs Big Data
|Small Data |	Big Data|
|:--|:--|
|Periodo corto |	Periodo largo |
|Específico|	Menos específico |
|Fácil de analizar |	Difícil de procesar |
|Hojas de cálculo	|Bases de datos |

- PYMES	Grandes empresas
- Las 3–4 V del Big Data: volumen, variedad, velocidad, veracidad.

## Ética, privacidad y anonimización
Los datos representan personas. Prepararlos implica proteger su identidad.

### Principios clave

- Privacidad
- Responsabilidad
- Transparencia
- Propiedad
- Apertura (cuando es seguro)
- Técnicas de anonimización
- Eliminar datos personales
- Enmascarar valores
- Sustituir por códigos o hash
- Reducir precisión (rangos de edad)
- Datos que deben anonimizarse
- Identificadores directos (nombre, dirección)
- Identificadores digitales (IP, email)
- Datos financieros
- Datos médicos
- Datos sensibles (fotos, biometría)

## Bases de datos y claves relacionales
Conceptos esenciales:
- Tabla: conjunto de datos organizado
- Clave primaria: identificador único
- Clave externa: conecta tablas
- Relación: enlace entre tablas
- Normalización: reduce duplicados
- Inspección inicial de un dataset
- Antes de analizar, verifica si los datos:

### Existen para responder la pregunta
- Son suficientes
- Son correctos y razonables
- Están organizados adecuadamente

## Metadatos
Los metadatos describen origen, estructura y contexto.

|Tipo	|Qué describe	| Ejemplos |
|:--|:--|:--|
|Descriptivos |	Identificación	| Título, etiquetas |
|Estructurales |	Organización	| Relación entre tablas |
|Administrativos |	Gestión |	Permisos, fechas |
|Procedencia |	Origen	| Historial de cambios |
|Técnicos |	Archivo |	Tamaño, formato |
|Estadísticos	| Variables	| Rango, unidades |
|Geoespaciales	| Ubicación |	Latitud, longitud |

- Importación : dinámica en Google Sheets
- Funciones útiles:
  - IMPORTRANGE — traer datos de otra hoja
  - IMPORTHTML — extraer tablas de webs
  - IMPORTDATA — cargar CSV o TSV desde URL

## Conjuntos de datos públicos
Plataformas comunes:
- Google Cloud Public Datasets
- Google Dataset Search
- Kaggle
- BigQuery Public Datasets

### Categorías:
- Salud
- Clima
- Sociedad
---
tener encuenta que:

- **Validación de datos** : La validación garantiza que los datos tienen sentido antes de procesarlos. Es una comprobación lógica, no técnica.

## Qué validar
- Rangos válidos: edades entre 0 y 120, porcentajes entre 0 y 100.
- Valores imposibles: ventas negativas, fechas futuras, tiempos negativos.
- Coherencia entre columnas: si “estado = entregado”, debe existir “fecha_entrega”.
- Unidades consistentes: kg vs g, €, $, horas vs minutos.
- Outliers sospechosos: valores extremadamente altos o bajos que requieren revisión.

### Por qué es importante
Evita conclusiones erróneas, errores en modelos y visualizaciones engañosas.

### Documentación del dataset (Diccionario de datos)
Documentar los datos permite entender su estructura, origen y significado.

### Qué incluir en un diccionario de datos
- Nombre de cada columna.
- Descripción clara de lo que representa.
- Tipo de dato (texto, número, fecha, booleano).
- Unidades (€, %, kg, horas).
- Valores permitidos o categorías válidas.
- Transformaciones aplicadas.Notas sobre calidad o limitaciones.

### Beneficios
- Facilita el trabajo en equipo.
- Evita malentendidos.
- Permite reproducir el análisis.
- Control de versiones de datos
- Los datasets cambian con el tiempo; mantener versiones evita confusiones.

## Buenas prácticas
- Guardar una copia del dataset original sin modificar.
- Crear versiones numeradas: dataset_v1, dataset_v2, dataset_final.
- Registrar cambios importantes: qué se añadió, eliminó o transformó.
- Mantener trazabilidad para auditorías o revisiones.
- Preparación para uniones (joins)
- Antes de unir datos en Excel o SQL, es necesario preparar las claves.

## Pasos esenciales
- Normalizar mayúsculas/minúsculas.
- Eliminar espacios invisibles.
- Convertir tipos de datos (texto → número si corresponde).
- Verificar que no existan claves duplicadas.
- Crear claves compuestas si es necesario (cliente + fecha).
- Alinear nombres de columnas entre tablas.

### Por qué importa
- Evita uniones incorrectas, duplicados inesperados y pérdida de información.
- Preparación temporal (fechas y tiempos)
- Los datos con fechas requieren preparación especial.

- Acciones recomendadas
- Convertir fechas a formato estándar ISO: YYYY-MM-DD.
- Crear columnas derivadas: año, mes, día, trimestre, semana.
- Ordenar cronológicamente.
- Detectar huecos en la serie temporal.
- Unificar zonas horarias si existen.

### Beneficio
Facilita análisis de tendencias, estacionalidad y comparaciones temporales.

- Preparación categórica :Las categorías suelen estar llenas de inconsistencias.
- Qué hacer :Normalizar categorías: “Sí”, “si”, “SI” → “Sí”.
- Unificar nombres de ciudades, países o productos.
- Agrupar categorías raras en “Otros”.
- Crear categorías derivadas (rango de edad, nivel de gasto).
- Verificar que no existan duplicados por errores tipográficos.
- Preparación numérica
- Los números también requieren limpieza.

- Acciones clave
- Convertir texto a número.
- Unificar separadores decimales.
- Detectar ceros sospechosos.
- Revisar valores negativos.
- Crear columnas de ratios o proporciones si serán necesarias.

## Preparación geográfica
Si el dataset contiene ubicaciones, conviene prepararlas.

## Pasos recomendados
- Normalizar nombres de ciudades, provincias y países.
- Convertir direcciones a coordenadas (geocodificación).
- Verificar que las coordenadas sean válidas.
- Crear columnas de región, provincia, país.

## Preparación de texto
- Los datos textuales requieren limpieza antes de analizarlos.

## Técnicas básicas
- Convertir todo a minúsculas.
- Eliminar caracteres especiales.
- Quitar espacios dobles o invisibles.
- Separar texto largo en campos útiles.
- Detectar palabras clave si se usarán después.

