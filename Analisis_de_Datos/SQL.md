# SQL — Preparación, Consultas Esenciales y Buenas Prácticas
SQL es el lenguaje estándar para trabajar con bases de datos relacionales. En la fase Preparar, SQL permite seleccionar, limpiar, transformar, unir y organizar datos antes de analizarlos. Esta hoja reúne los conceptos esenciales, las operaciones clave y las buenas prácticas profesionales.

## SQL en la fase PREPARAR
Estas operaciones son las más importantes para dejar los datos listos antes de procesarlos o analizarlos.

- Seleccionar columnas relevantes

- SELECT columna1, columna2
- FROM tabla;
- Filtrar datos incorrectos o irrelevantes
---
- WHERE columna IS NOT NULL;
- WHERE edad > 0;
- WHERE precio >= 0;

-Normalizar valores

### UPDATE tabla
- SET columna = LOWER(columna);
- Crear columnas derivadas
```text
SELECT *,
       precio * cantidad AS total
FROM ventas;
```
- Unir tablas (clave en PREPARAR)
```text
SELECT *
FROM clientes c
JOIN ventas v
ON c.id = v.id_cliente;
```text
- Eliminar duplicados
```text
SELECT DISTINCT columna
FROM tabla;
```
- Ordenar datos
- ORDER BY fecha ASC;
- Limitar datos para muestras
- LIMIT 500;
## Operaciones fundamentales de SQL
- Seleccionar columnas
```text
SELECT columna1, columna2
FROM tabla;
```
- Seleccionar todas las columnas
```text
SELECT *
FROM tabla;
```
- Filtrar datos
```text
WHERE columna = 'valor';
WHERE edad > 30;
WHERE fecha >= '2024-01-01';
```
- Ordenar resultados
```text
ORDER BY columna ASC;
ORDER BY columna DESC;
```
- Limitar filas
```text
LIMIT 100;
```text
Combinar condiciones
```text
WHERE pais = 'Spain' AND edad > 18;
WHERE ciudad = 'Madrid' OR ciudad = 'Valencia';
```
- Coincidencias parciales
```text
WHERE nombre LIKE 'A%';   -- empieza por A
WHERE nombre LIKE '%ez';  -- termina en ez
```
- Agrupar datos
```text
SELECT pais, COUNT(*)
FROM clientes
GROUP BY pais;
```
- Filtrar grupos
```text
HAVING COUNT(*) > 10;
```text
- Tipos de JOIN y cuándo usarlos
- INNER JOIN
- Devuelve solo coincidencias.
```text
SELECT *
FROM clientes c
INNER JOIN pedidos p
ON c.id = p.cliente_id;
```
- LEFT JOIN
- Devuelve todos los registros de la tabla izquierda y coincidencias de la derecha.
```text
SELECT *
FROM clientes c
LEFT JOIN pedidos p
ON c.id = p.cliente_id;
```
- RIGHT JOIN
- Devuelve todos los registros de la tabla derecha.

```text
SELECT *
FROM clientes c
RIGHT JOIN pedidos p
ON c.id = p.cliente_id;
```
- FULL JOIN
- Devuelve todos los registros de ambas tablas.
```text
SELECT *
FROM tabla1
FULL JOIN tabla2
ON tabla1.id = tabla2.id;
```text

- CROSS JOIN
- Combina todo con todo.

```text
SELECT *
FROM productos
CROSS JOIN colores;
```
- Manejo de valores NULL
- Detectar valores nulos
```text
WHERE columna IS NULL;
```
Detectar valores no nulos
```text
WHERE columna IS NOT NULL;
```text
- Sustituir valores nulos
```text
SELECT COALESCE(columna, 'Sin dato')
```text
- FROM tabla;
- Alternativa en MySQL
```text
SELECT IFNULL(columna, 'Sin dato')
FROM tabla;
```
- Funciones de texto para preparar datos
```text
LOWER(columna)     -- convertir a minúsculas
UPPER(columna)     -- convertir a mayúsculas
TRIM(columna)      -- quitar espacios
REPLACE(columna,'-',' ')  -- reemplazar caracteres
SUBSTR(columna,1,3)       -- extraer parte del texto
```
- Funciones de fecha para preparar datos
```text
DATE(fecha)                     -- convertir a fecha
EXTRACT(YEAR FROM fecha)        -- año
EXTRACT(MONTH FROM fecha)       -- mes
DATE_ADD(fecha, INTERVAL 7 DAY) -- sumar días
DATE_DIFF(fecha2, fecha1)       -- diferencia
```
- Funciones numéricas útiles
```text
ROUND(columna,2)   -- redondear
ABS(columna)       -- valor absoluto
CEIL(columna)      -- redondeo hacia arriba
FLOOR(columna)     -- redondeo hacia abajo
```
- Subconsultas esenciales
- Subconsulta en WHERE
```text
SELECT *
FROM ventas
WHERE cliente_id IN (
    SELECT id
    FROM clientes
    WHERE ciudad = 'Madrid'
);
```
- Subconsulta en FROM (tabla derivada)
```text
SELECT ciudad, total
FROM (
    SELECT ciudad, SUM(importe) AS total
    FROM ventas
    GROUP BY ciudad
) t;
```
- Crear tablas limpias (CTAS)
- Muy útil en PREPARAR.
```text
CREATE TABLE ventas_limpias AS
SELECT *
FROM ventas
WHERE importe > 0;
```
- UPDATE, DELETE e INSERT (solo lo esencial)
- Actualizar datos
```text
UPDATE clientes
SET ciudad = 'Valencia'
WHERE ciudad = 'Valéncia';
```
- Eliminar datos
```text
DELETE FROM ventas
WHERE importe < 0;
```
- Insertar datos
```text
INSERT INTO clientes (nombre, ciudad)
VALUES ('Ana', 'Madrid');
```
## Buenas prácticas profesionales en SQL
- Nombres claros y consistentes
- Evitar t1, tabla2.
- Usar clientes, ventas, pedidos.

- Seleccionar solo lo necesario
- Evitar SELECT *.

### Orden correcto de cláusulas
- Código
- SELECT
- FROM
- JOIN
- WHERE
- GROUP BY
- HAVING
- ORDER BY
- LIMIT
- Usar alias

```text
SELECT c.nombre, p.total
FROM clientes c
JOIN pedidos p ON c.id = p.cliente_id;
```text
- Filtrar lo antes posible
- El WHERE reduce datos antes de agrupar.

- Comillas correctas
- 'texto' para valores

- BigQuery usa comillas invertidas: \tabla\

- Evitar duplicados innecesarios
```text
SELECT DISTINCT ciudad
FROM clientes;
```
- Documentar consultas largas
-- Clientes con más de 5 pedidos
SELECT ...
- Probar la consulta por partes
- Primero SELECT + FROM, luego WHERE, luego GROUP BY.

- Cuidar el rendimiento
- Evitar funciones en columnas del WHERE.

- Evitar subconsultas innecesarias.

- Preferir JOINs a consultas anidadas.

- Organización, mantenimiento y protección de datos
- Convenciones de nombres
- Nombre del proyectoFecha AAAAMMDD
- Número de versión

### Ejemplo:

```text
SalesReport_20231125_v02
Organización de carpetas
Jerarquía lógica
```

- Separar archivos finalizados y en curso
- Archivar versiones antiguas
- Coherencia en todo el equipo
- Seguridad de datos
- Encriptación
- Tokenización
- Control de versiones
- Protección de celdas y permisos en hojas de cálculo

### Síntesis final
SQL permite preparar datos de forma eficiente mediante selección, limpieza, normalización, uniones y creación de tablas limpias. Las buenas prácticas garantizan claridad, rendimiento y seguridad. Una organización adecuada de archivos y versiones asegura trazabilidad y trabajo colaborativo sin errores.
