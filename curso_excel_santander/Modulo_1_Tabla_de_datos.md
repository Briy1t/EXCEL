# Modulo 1 

**Objetivo**: 
- Dominar los fundamentos básicos de Excel: navegación por la interfaz, entrada de datos y organización de hojas de cálculo.
- Comprender y aplicar funciones comunes para cálculos simples y funciones más avanzadas.
- Adquirir habilidades para trabajar con tablas dinámicas mediante ejemplos prácticos y casos reales del entorno empresarial.

**Nota:** Los objetivos de aprendizaje de este módulo están adaptados del curso de 
Excel del Programa Santander. He redactado esta versión para uso personal y documentación
dentro de mi repositorio.

**Tablas de datos: Excel vs LibreOffice Calc**
He querido realizar los ejercicios en diferentes medios como Excel web y LibreOffice en lugar de Excel
para analizar las facilidades que tiene tener una licencia de office y sus beneficios.

---
Las **tablas de datos** aparecieron en Excel a partir de la `versión 2007` y se convirtieron en una herramienta muy útil para manejar listas grandes.
Permiten mantener cálculos y operaciones actualizados sin necesidad de modificar manualmente el tamaño del rango cada vez que añadimos filas o columnas.

- En `LibreOffice Calc`, como no existe el concepto de “tabla inteligente”, el equivalente es definir un Rango de datos.
Diferencia entre un rango y una tabla.

## ¿Qué es un rango?
Un rango es simplemente un conjunto de celdas normales.
No tiene inteligencia, no se actualiza solo y no tiene herramientas especiales.

---
**Características del rango:**
- Son celdas “normales”.
- No se expanden automáticamente.
- No tienen filtros automáticos.
- No tienen estilos automáticos.
- No tienen fila de totales dinámica.
- Si agregas datos debajo, Excel no lo reconoce como parte del conjunto.
- En Calc, todo funciona como rangos (aunque existe tabla dinamica).
  
---
**Ejemplo:**
A1:D20 es un rango. Nada más.

--- 

## ¿Qué es una tabla?
Una tabla es un rango “convertido” en un objeto inteligente.
Excel la reconoce como un conjunto de datos estructurados.

---

**Características de la tabla:**
- Tiene estilo automático (colores, bordes, formato).
- Agrega filtros automáticamente en los encabezados.
- Se expande sola cuando agregas filas o columnas.
- Permite activar la fila de totales.
- Tiene su propia pestaña de herramientas: Diseño de tabla.
- Se puede nombrar (Tabla1, Ventas2024, etc.).
- Funciona mejor con tablas dinámicas.
- Permite segmentación de datos (solo disponible para tablas).

---

**Ejemplo:**  
Cuando presionas Ctrl + T en Excel, el rango se convierte en una tabla inteligente.
---

 **Resumen rápido**
 
| Característica |	Rango | Tabla |
|:--|:--|:--|
|Celdas normales	|✔️	|❌ |
|Estilo automático |❌|✔️ |
|Filtros automáticos |	❌|	✔️ |
|Expansión automática |	❌ |	✔️ |
|Fila de totales dinámica	|❌ |	✔️|
|Segmentación de datos |	❌|	✔️ |
|Ideal para grandes volúmenes|	❌|	✔️|
|Existe en LibreOffice Calc	|❌ (solo rangos)|❌(existe tabla dinamica mas no tabla inteligente )


### Filtrar datos 


- Cómo crear un rango estructurado en Calc:
  - Seleccionar las filas y columnas.
  - Ir al menú Datos.
  - Activar Filtro automático.

       ![im_1](imagenes/im_1.png)

- En Excel Online aparece simplemente como Filtrar.
  - Esto le indica a Calc que ese bloque funcionará como una tabla estructurada.
![im_1](imagenes/im_2.png)

--- 
**Requisitos importantes**

- Todas las tablas deben tener fila de encabezados, Excel nunca permite eliminar esa fila.
- Antes de convertir un rango en tabla, la primera fila debe contener los títulos.

### Qué ocurre al convertir un rango en tabla (Excel)
- Formato especial automático
- Colores, bordes y estilo.
- No es solo estética: mejora la lectura.
- Botones de filtro en los encabezados  
  - Permiten:
      - Ordenar
      - Filtrar por valores
      - Buscar dentro de la columna
      - Mostrar solo ciertos datos
      - La tabla se vuelve “inteligente”
      - Se expande automáticamente al añadir filas.
      - Aparece la ficha Diseño de tabla.
      - Permite cambiar estilo, agregar fila de totales, renombrar la tabla, etc.
      - La ficha desaparece cuando no estamos dentro de una tabla para no saturar la interfaz.

---

En conclusion las tablas nos facilitan el manejo de datos ya que nos ahorran tiempo y mejoran el rendimiento.

--- 
###  Comparativa Excel vs LibreOffice Calc

|Concepto|	Excel |	LibreOffice Calc |
|:--|:--|:--|
|Rango	|Celdas normales	|Celdas normales |
|Tabla	|Objeto inteligente con filtros, estilo y expansión	| No existe como objeto |
|Filtros |	Automáticos al crear tabla	Datos | Filtro selecionado manualmente |
|Tabla dinámica	|Sí |	Sí |
|Estilos automáticos	| Sí	|Manuales|
|Expansión automática	| Sí	|No |


- Congelar encabezados :“Dejar los rótulos estáticos arriba” = Congelar fila superior.
- Disponible en:Excel , Excel Online, LibreOffice Calc

### Formato rápido de encabezados
- (Calc)
  1. Ver
  2. Inmovilizar celdas
  3. Inmovilizar primera celda
![im_1](imagenes/im_3.png)
- Excel Online
  1. En la cinta de opciones debajo de insertar podemos ver la opcion
  2. Top Row
  3. la selecionamos
![im_1](imagenes/im_4.png)
---.
### Tablas en Excel Online
- Excel Online sí permite crear diseño de tablas.
- En Diseño de tabla se puede activar la fila de totales.
  - Se encontro en la cinta de opciones
  - Table Design
  - selecionamos table
- ![im_1](imagenes/im_6.png)
- ![im_1](imagenes/im_7.png)

imagen si hay table
---
- En LibreOffice Calc no existe esta opción automática.
- Aqui es un poco mas manual el diseño de tabla
- Configuración de la fila de totales
- ![im_1](imagenes/im_8.png)
- ![im_1](imagenes/im_s8.png)

### Actividad 1
1. Configurar las siguientes columnas:
  - CURSO: Recuento
  - DURACIÓN: Suma
  - IMPORTE CLIENTE: Suma
  - IMPORTE PROFESOR: Promedio
  - FECHA CURSO: Mínimo
En la parte inferior asignamos la configuracion pertinente:
- ![im_1](imagenes/im_s9.png)
  ![im_1](imagenes/im_9.png)
---
- **La fila de totales se actualiza automáticamente cuando aplicamos filtros**.
- En los siguiente ejercicios practicos se hicieron en Excel web porque cal no tienen las herramientas requeridas , por eso se llega
a la conclusion que Excel es muy util y tiene muchas herramientas.

### Prácticas realizadas
2. **1.4 Filtrar datos I**
   
  En el archivo 02. BD CURSOS: Se deben aaplicar los siguiente filtros
  - CURSO: DISEÑO, PROGRAMACIÓN, WORD
  - JORNADA CURSO: MAÑANA, TARDE
  - PAGADO CLIENTE: NO
  - PAÍS: ITALIA
  ![im_1](imagenes/im_10.png)
Luego consulté la fila de totales.
  ![im_1](imagenes/im_11.png)
---
posterior mente procedi a mirar el video y comprobar el resultado final 
  ![im_1](imagenes/im_12.png)



note que tenia el signo del dolar en lugar del euro , hago el cambio correspondientes
![im_1](imagenes/im_13.png)

### Filtrar por terminación o palabras
También practiqué filtros avanzados como:
  - Filtrar por valores que terminan en cierto texto
  - Filtrar por palabras específicas
![im_1](imagenes/im_14.png)

3. **Actividad 3**
- En el archivo 03. BD CURSOS:
    - Filtros aplicados:
    - CURSO: WORD, EXCEL, ACCESS
    - IMPORTE CLIENTE: menor que 1000
    - JORNADA CURSO: MAÑANA, NOCHE
    - PAÍS: ITALIA

Luego revisé la fila de totales.
![im_1](imagenes/im_15.png)

### 1.4 Filtrar datos II – Fechas
Los campos de fecha se agrupan automáticamente por: Año, Mes,Día .

--- 
**Importante:**
En una misma columna, no se puede filtrar por elemento y por tipo de dato al mismo tiempo.
El último filtro aplicado es el que prevalece.

4. **Actividad** 
- En el archivo 01. BD CURSOS:para practicar
- Filtros aplicados:
  - CLIENTE: CLIENTE-001, 003, 005, 008
  - ![im_1](imagenes/im_16.png)
---
  - FECHA CURSO: primeros 6 meses de 2019 y 2021
  - ![im_1](imagenes/im_17.png)
---
  - DURACIÓN: mayor que 20
  - ![im_1](imagenes/im_18.png)
---
  - PAÍS: ESPAÑA e ITALIA
  - ![im_1](imagenes/im_19.png)
---
  - PAGADO CLIENTE: NO
  - ![im_1](imagenes/im_20.png)
---
Luego consulté la fila de totales.
  ![im_1](imagenes/im_21.png)
---
4.1 **Ejercicio**
- En el archivo 04. BD CURSOS:
- Filtros aplicados:
  - CLIENTE: CLIENTE-001, 003, 005, 008
  - ![im_1](imagenes/im_22.png)
---
  - FECHA CURSO: primeros 6 meses de 2019 y 2021
  - ![im_1](imagenes/im_23.png)
---
  - DURACIÓN: mayor que 20
  - ![im_1](imagenes/im_24.png)
---
  - PAÍS: ESPAÑA e ITALIA
  - ![im_1](imagenes/im_25.png)
---
  - PAGADO CLIENTE: NO
  - ![im_1](imagenes/im_26.png)
---
Luego consulté la fila de totales.
    - ![im_1](imagenes/im_27.png)

### 1.5 Segmentación de datos
La segmentación es una herramienta visual para filtrar tablas.Solo está disponible para:
- Tablas
- Tablas dinámicas
- Cada segmentación es un objeto independiente con un botón por cada elemento del campo.
---
- Podemos encontrar el segmento de datos en la cinta de opciones , Table Design , Slicer
- ![im_1](imagenes/im_28.png)
---
1. **Solo funcionan con tablas**: Necesitas una tabla de Excel (Ctrl + T).
- No funcionan con rangos normales.
- En LibreOffice no existen.

2. **Son filtros visuales**: En vez de usar los filtros del encabezado, te aparecen botones grandes con los valores.
- Es una forma más rápida y cómoda de filtrar.

3. **Cada segmentación controla una sola columna**: Si quieres filtrar por varias columnas, necesitas varias segmentaciones.

4. Puedes elegir **uno o varios valores**: 
- Un clic → filtra un valor
- Ctrl + clic → seleccionas varios
- Icono del embudo → quitas el filtro

5. Son objetos que puedes **mover y personalizar**: Puedes cambiar tamaño, estilo y posición.
- Se pueden conectar a varias tablas dinámicas si comparten origen.

6. **Se actualizan solas**:Si cambian los datos de la tabla, la segmentación también cambia.
- Nuevos valores → nuevos botones
- Valores eliminados → desaparecen

7. Ideales **para informes y dashboards**: Muy usadas en:
- Dashboards
- Informes interactivos
- Tablas dinámicas
- Paneles de control
- Permiten filtrar sin abrir menús.
---

“Generalmente, los campos numéricos o fecha no se suelen segmentar, ya que en las segmentaciones solo se puede filtrar por elemento y no por tipo de dato”

---
- Segmentacion
- ![im_1](imagenes/im_29.png)
- Eliminar Segmentacón
- ![im_1](imagenes/im_30.png)

---

1.6 **Odenar datos de la tabla por una sola columna**
- Sobre el fichero BD CURSOS quitamos todos los filtro que pueda estar aplicados, las segmentaciones que estén y,eliminar la fila de totales la ocultamos.

  - 1. Dejamos de mostrar la linea que muestra los resultados 
  - ![im_1](imagenes/im_31.png)
  - 2- Ordenar de forma acendente o decendente
  - ![im_1](imagenes/im_32.png)

1.6 **Ordenar datos de la tabla por más de una columna**
- En el botón ORDENAR colocamos primero la celda activa en cualquier celda dentro de la tabla que vamos a ordenar y en la ficha DATOS, grupo de botones ORDENAR Y FILTRAR, pulsamos el botón ORDENAR.
- ![im_1](imagenes/im_33.png)

---

1.7. Convertir una tabla en rango

- ![im_1](imagenes/im_33.png)

- haci  como podemos convertir un rango en tabla también podemos convertir una tabla en rango, si le das aceptar como resultado desaparecerán las segmentaciones y filtros 

---

1.8. Cambiar tamaño de la tabla

- ![im_1](imagenes/im_34.png)
  
- Cambiar el tamaño de la tabla es necesario dado el caso que intentemos agregar filas o columnas y no sea permitido  tendremos que  seleccionar el nuevo rango de celdas que incluyen las nuevas filas y/o columnas incorporadas.
  
- ![im_1](imagenes/im_35.png)

- insertamos el rango que requerimos con las nuevas filas o columnas añadidas

---

1.9. Nombrar una tabla

"El nombre de la tabla nos sirve para poder llamar a la tabla desde cualquier celda de cualquier hoja del libro en el que estamos trabajando, sin necesidad de cambiar de hoja y seleccionar los datos (como hacemos en los rangos). Basta con escribir el nombre de la tabla a la que queremos llamar y Excel de manera automática la identifica. Por ello, es muy importante dar a cada tabla el nombre adecuado, para que cuando queramos llamar a dicha tabla la reconozcamos por su nombre (como haremos más adelante)."

---
- El nombre de la tabla tiene que ser texto, puede contener números, pero ha de ser texto.
- No se admiten ni espacios ni caracteres especiales, el único separador que se admite es el guion bajo: _

---
- ![im_1](imagenes/im_36.png)
- cambiamos el hombre por T_curso 

### Ejecicio

1. Descarga el fichero 09. BD FACTURAS :En este hay una base de datos en la que se registran diferentes facturas.
- tiene las siguientes columnas:
- 1. NUMERO FACTURA CLIENTE: se indica el número de la factura.
- 2. CONCEPTO: el concepto que estamos facturando.
- 3. CLIENTE: el cliente al que le emitimos la factura.
  4. PROVINCIA: provincia en la que reside el cliente al que le facturamos.
  5. SECTOR: sector de actividad empresarial al que pertenece el cliente al que facturamos.
  6. IMPORTE CLIENTE: importe que facturamos al cliente.
  7. FECHA FACTURA CLIENTE: fecha de emisión de la factura.
  8. PAGADA CLIENTE: indicamos si el cliente ha pagado o no la factura.
  9. PROVEEDOR: cada factura que hacemos es un servicio que contratamos a un proveedor, por tanto, en esta columna indicamos el nombre del proveedor que estamos contratando para dar el servicio que estamos facturando.
  10. ZONA: la zona geográfica que cubre el proveedor.
  11. TIPO: qué tipo de proveedor es.
  12. IMPORTE PROVEEDOR: el importe que nos cobra el proveedor por darnos el servicio contratado.
A continuación, realiza las siguientes acciones y configuraciones en los datos del documento:
- Insertar una tabla sobre el rango.
- Nombrar la tabla con el nombre T_FACTURAS.
- Ordenar la tabla por las columnas: concepto e importe cliente ambas columnas en orden ascendente.
- Mostrar la fila de totales con la siguiente configuración:
- NUMERO FACTURA CLIENTE: recuento.
- IMPORTE CLIENTE: suma.
- IMPORTE PROVEEDOR: suma.
- Mostrar las segmentaciones de las columnas: PROVINCIA y TIPO.
- Filtrar las facturas en las provincias MADRID y BARCELONA, con FECHA FACTURA de los 4 primeros meses de los años 2019 y 2020 de TIPO INTERNO e IMPORTE CLIENTE MAYOR de 1000.
- Consultar el resultado de la fila de totales.
- Quitar todos los filtros aplicados.
- Ocultar la fila de totales.
- Eliminar la segmentación del campo PROVINCIA

## solución
- paso 1: creamos la tabla
- ![im_1](imagenes/im_37.png)
- paso 2: procedemos a cambiar el hombre
- ![im_1](imagenes/im_38.png)
- paso 3: ordenar la tabla por las columnas
- ![im_1](imagenes/im_39.png)
- paso 4: configuración de la fila de totales
- ![im_1](imagenes/im_40.png)
- paso 5: segmentación de provincia y tipo
- ![im_1](imagenes/im_41.png)
- ![im_1](imagenes/im_42.png)
- ![im_1](imagenes/im_43.png)
- ![im_1](imagenes/im_44.png)
- ![im_1](imagenes/im_45.png)
- ![im_1](imagenes/im_46.png)
- ![im_1](imagenes/im_47.png)
- paso 6: mirar la fila de resultados
- ![im_1](imagenes/im_48.png)
- paso 8: quitar todos los filtros aplicados
- ![im_1](imagenes/im_49.png)
- paso 9: ocultar la fila de resultados totales
- ![im_1](imagenes/im_50.png)
- paso 10: eliminamos las segmentaciones
- ![im_1](imagenes/im_51.png)
- paso 11: final del ejercicio
- ![im_1](imagenes/im_52.png)
---

2. Referencias relativas y absolutas I
   
```text
“Las referencias de celdas se refieren a cuando realizamos cálculos en Excel. A cada celda que llamamos dentro de un cálculo, estamos haciendo que sea una referencia. De tal modo, que si en la celda B3 de una hoja de cálculo tenemos la fórmula: B3= A1 * C2, en dicha fórmula estamos haciendo dos referencias, una a la celda A1 y otra a la celda C2.”

“La referencia es la manera en la que se comportan las celdas cuando copiamos un cálculo.”

Referencia relativa
Permite repetir cálculos rápidamente sin tener que reescribir fórmulas.
Son ideales para listas, tablas y cálculos repetitivos.
no tienen el símbolo de $ =la referencia no sería relativa
```
### Ejercicio

- En el fichero 11. REFERENCIAS RELATIVAS descargado antes, calcula la columna % BENEFICIO del ejercicio que sería:
- % BENEFICIO = MARGEN BENEFICIO / PRECIO COMPRA 
- Ajusta el formato de número para que se vea como porcentaje (%)
- Copia la fórmula al resto de productos
Pasos
- 1 
- ![im_1](imagenes/im_53.png)
- 2
- ![im_1](imagenes/im_54.png)
- 3
- ![im_1](imagenes/im_55.png)
- 4
- ![im_1](imagenes/im_56.png)
- 5
- ![im_1](imagenes/im_57.png)

---
### Referencia absoluta
Una referencia absoluta en Excel es una referencia de celda que no cambia nunca, aunque copies o arrastres la fórmula a otra celda. Es lo contrario de una referencia relativa.
- sirve para:
- Un valor fijo en muchas fórmulas, por ejemplo:
  - Un IVA fijo (21%)
  - Un tipo de cambio
  - Un descuento
  - Un precio base
  - Un límite o meta que no cambia


| Tipo | Ejemplo | 
|:--|:--|
|Relativa | A1 Uso típico |
|Absoluta |$A$1 Valores fijos |


---

**pulsamos la tecla de función F4 para convertir una referencia en absoluta**



### Ejercicio

- En el fichero 13. REFERENCIA ABSOLUTA descargado antes, calcula las columnas SUELDO BRUTO, IMPORTE RETENCION y SUELDO NETO con las siguientes fórmulas:
- SUELDO BRUTO: SALARIO BASE + IMPORTE COMISION
- IMPORTE RETENCION: SUELDO BRUTO * RETENCION
- SUELDO NETO: SUELDO BRUTO – IMPORTE RETENCION
- Ajusta bien la referencia en cada fórmula para copiarla al resto de vendedores

- Solución
- 1
- ![im_1](imagenes/im_58.png)
- 2
- ![im_1](imagenes/im_59.png)
- 3
- ![im_1](imagenes/im_60.png)

---
2. Referencias relativas y absolutas III
- Calcular columnas en una tabla
- Cuando conviertes un rango en tabla inteligente, Excel permite que:
  - Escribas una fórmula en una celda de la columna.
  - Automáticamente la replica hacia abajo en toda la columna.
  - Usa nombres de columnas, no letras.


---

“La @ quiere decir FILA ACTUAL, es decir, nos indica que estamos cogiendo un dato de la tabla que está situado en la misma fila en la que estamos calculando,
en concreto de la columna IMPORTE PROFESOR, ya que es el nombre de la columna que ha quedado escrito en la fórmula.
De manera similar, ocurre con el campo [@[IMPORTE COMERCIAL]], donde Excel nos indica que estamos seleccionando un dato que está en la misma fila que estamos calculando y que pertenece a la columna IMPORTE COMERCIAL.”

- la fórmula se copia de manera automática para toda la columna de la tabla
podemos escribir manualmente el cálculo usando las direcciones de las celdas dentro de la tabla.

- ![im_1](imagenes/im_61.png)
añadimos una nueva columna

---
### Ejercicio
- Agrega en el fichero 15. BD CURSOS, a continuación de la columna GASTO, las siguientes columnas: BENEFICIO y % BENEFICIO. Calcula dichas columnas con las siguientes fórmulas:
- Beneficio: importe cliente – gasto
- % beneficio: beneficio / importe cliente. Aplica a esta columna un formato %.

- ![im_1](imagenes/im_62.png)
- las dos nuevas columnas
- ![im_1](imagenes/im_63.png)
- ![im_1](imagenes/im_64.png)
- resultado
- ![im_1](imagenes/im_65.png)





