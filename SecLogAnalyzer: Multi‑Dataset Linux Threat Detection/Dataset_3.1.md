# DATASET 3 (AUTENTICACIÓN EN SERVIDORES)
1. Introducción al Dataset 3
El Dataset 3 contiene tres archivos relacionados con la actividad interna de autenticación en servidores Linux.
A diferencia de los datasets de tráfico externo, este dataset permite analizar lo que ocurre dentro del servidor, no solo lo que llega desde fuera.

--- 
Esto permite:
- Comparar tráfico externo vs interno
- Ver si los patrones sospechosos del Dataset 1 coinciden con eventos internos
- Ver si los ataques del Dataset 2 dejan rastros en los logs de autenticación
- Construir conclusiones basadas en múltiples fuentes de datos
----
Los archivos incluyen:
- Versiones balanceadas
- Versiones etiquetadas
- Versiones con múltiples anomalías
---
Esto facilita:
- Comparar comportamiento normal vs anómalo
- Identificar patrones de autenticación sospechosos
- Detectar escaladas de privilegios
- Analizar intentos de login fallidos
- Observar actividad interna del sistema
---
## 2. Metodología de análisis
Para mantener coherencia con los datasets anteriores, se utiliza la misma estructura:

### 2.1 Revisión inicial
- Columnas disponibles
- Tipos de eventos
- Presencia o ausencia de etiquetas
- Volumen de registros

### 2.2 Limpieza
- Normalización de fechas
- Conversión de tipos
- Eliminación de filas corruptas
- Identificación de campos clave

### 2.3 Análisis
- Eventos más frecuentes
- Servicios más activos
- Usuarios con más actividad
- Intentos de login fallidos
- Patrones de escalada de privilegios
- Errores del sistema
- Anomalías etiquetadas


## 3. Dataset 3.1 – linux_auth_logs_full (balanced)
Este archivo contiene columnas clave:
- timestamp
- source_ip
- server
- username
- service
- attempts
- status
- port
- protocol
- comment
- anomaly_label
- Es un dataset completo porque incluye:
- Etiquetas de anomalía
- Información de autenticación
- Servicios internos
- IPs externas
- Puertos y protocolos

---
## Nombre del archivo 3.1 linux_auth_logs_full(balanced)
- Estructura del documento
- 1
- Tras la limpieza en python, se guardó como:
- 2 

- linux_auth_logs_(balanced)_clean
- Y se importó en DBeaver.
- 3

## 4. Resultados del análisis
4.1 Usuarios con más intentos fallidos
Consulta SQL:

```sql
SELECT username, COUNT(*) AS failed_attempts
FROM linux_auth_logs
WHERE status = 'Failed'
GROUP BY username
ORDER BY failed_attempts DESC;
```

4
--- 
### Interpretación:
- ec2-user y admin son usuarios genéricos muy comunes en servidores Linux. Son los primeros que un atacante prueba.
- nginx es un usuario de servicio y no debería tener intentos de login manual.
- Los demás usuarios (ithompson, amy87, etc.) parecen usuarios reales. Sus fallos son normales, pero deben vigilarse.

#### Conclusión:
- Los dos primeros representan actividad maliciosa clara.
- Los siguientes ocho son actividad normal o ruido.

### 4.2 IPs con más actividad total

```sql
SELECT source_ip, COUNT(*) AS total_events
FROM linux_auth_logs
GROUP BY source_ip
ORDER BY total_events DESC;
```
- 5
--- 
#### Interpretación:

- No hay una IP con miles de intentos
- No hay un patrón de ataque masivo desde una sola IP
- Parece un ataque distribuido (muchas IPs, pocos intentos cada una)
- Esto es típico de bots, escáneres automáticos y ataques de diccionario distribuidos.

### 4.3 Servicios más usados

```sql
SELECT service, COUNT(*) AS total_events
FROM linux_auth_logs
GROUP BY service
ORDER BY total_events DESC;
```
-6
---
#### Interpretación:
- ssh es el principal vector de ataque
- sudo y su indican escalada de privilegios
- cron representa actividad interna normal
- login representa actividad legítima dentro del servidor

### 4.4 Success vs Failed

```sql
SELECT status, COUNT(*) AS total
FROM linux_auth_logs
GROUP BY status;
```
- 7
---
#### Interpretación:
- Muchos fallos indican actividad de fuerza bruta
- Los éxitos corresponden a actividad normal del sistema
---
### 4.5 Actividad por servidor

```sql
SELECT server, COUNT(*) AS total_events
FROM linux_auth_logs
GROUP BY server
ORDER BY total_events DESC;
```
- 8
---
#### Interpretación:

- Los primeros cinco servidores tienen actividad muy similar, lo que indica que son servidores principales y reciben tráfico SSH constante
- vpn-thr-02 y proxy-mow-01 tienen poca actividad, lo que indica que son servidores secundarios o de soporte
---

### 4.6 Conteo de anomalías

```sql
SELECT anomaly_label, COUNT(*) AS total
FROM linux_auth_logs
GROUP BY anomaly_label;
```
- 9 
---
#### Interpretación:

- El dataset no incluye etiquetas de anomalía en esta versión
- Sin embargo, los patrones observados indican fuerza bruta distribuida y actividad sospechosa en SSH
---
### 4.7 Actividad por hora

```sql
SELECT strftime('%H', timestamp) AS hour, COUNT(*) AS total_events
FROM linux_auth_logs
GROUP BY hour
ORDER BY hour;
```
-10 
---
#### Interpretación:
- Pico significativo a medianoche, típico de tareas automáticas (cron, backups, rotación de logs)
- Resto del día estable, sin picos sospechosos
---
## Graficos
- Muestra actividad sospechosa clara (ec2-user, admin). usuarios y fallos
- 11
- Muestra ataque distribuido.
- 12
- Resume el comportamiento del sistema
- 13

## 5. Conclusión general del Dataset 3.1
- El sistema muestra una actividad intensa sobre el servicio SSH, con más de 200.000 intentos fallidos concentrados principalmente en usuarios genéricos como ec2-user y admin. Este patrón es característico de ataques de fuerza bruta distribuidos, donde múltiples IPs realizan pocos intentos cada una.
- Los servidores principales (NYC, Singapur, Londres, Berlín y Tokio) reciben una carga muy similar, lo que indica una infraestructura equilibrada. Además, se observan tareas internas normales asociadas a los servicios cron y login, y un pico significativo de actividad a medianoche debido a procesos automáticos del sistema.
- Aunque el dataset no incluye etiquetas de anomalías, los patrones observados permiten identificar actividad sospechosa clara sobre SSH.
