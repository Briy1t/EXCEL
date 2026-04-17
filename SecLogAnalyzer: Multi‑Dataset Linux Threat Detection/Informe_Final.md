# INFORME FINAL DEL PROYECTO
Análisis de Logs y Tráfico en Sistemas Expuestos a Internet

## 1. Introducción
Este proyecto tiene como objetivo analizar distintos tipos de logs y flujos de red para identificar patrones de comportamiento, actividad normal, actividad sospechosa, errores frecuentes e indicadores de posibles ataques.
A través de tres datasets principales : tráfico web, tráfico IoT y logs de autenticación Linux— se estudia cómo se comportan sistemas expuestos a Internet y qué señales permiten detectar amenazas de forma temprana.

## 2. Metodología General
Para todos los datasets se aplicó un proceso uniforme:
- Revisión inicial del archivo (estructura, formato, calidad del dato).
- Limpieza y normalización con Python (pandas).
- Exportación a CSV y análisis en Excel.
- Consultas SQL en DBeaver para identificar patrones.
- Generación de visualizaciones en Excel.
- Interpretación contextual desde la perspectiva de ciberseguridad.

## 3. Análisis de los Datasets
### 3.1 Dataset 1 — Web Server Access Logs
Hallazgos principales:
- 68% de las IP no tienen hostname resoluble → tráfico automatizado.
- Hostnames repetidos asociados a escáneres y VPS:
- unknown.puregig.net, AS51430, getmyip.co, zmap.sorengard.com.
- Dominio del rango 5.x.x.x, típico de proveedores internacionales con alto tráfico automatizado.
- Presencia de nodos TOR, ZMap y VPS de bajo coste.
- Actividad humana prácticamente inexistente.

#### Conclusión del Dataset 1
El Dataset 1 representa tráfico automatizado, distribuido e internacional, con fuerte presencia de bots, escáneres y servidores remotos. Refleja el “ruido” constante que recibe cualquier servidor expuesto a Internet.

### 3.2 Dataset 2 — Tráfico IoT
Hallazgos principales:
- Tráfico legítimo: MQTT, DNS, HTTP/HTTPS.
- Tráfico malicioso etiquetado:
- DOS_SYN_Hping (~94.659)
- ARP_poisoning (~7.750)
- ThingSpeak (~8.108)
- Escaneos NMAP
- Slowloris (~534)
- SSH brute force (~37)

#### Conclusión del Dataset 2
El Dataset 2 combina tráfico IoT legítimo con múltiples ataques reales. La variedad de técnicas lo convierte en un recurso ideal para estudiar clasificación de tráfico y detección de intrusiones.

### 3.3 Dataset 3 — Logs de Autenticación Linux (3.1, 3.2, 3.3)
Hallazgos principales: 
**3.1**:
- Más de 200.000 intentos fallidos sobre SSH.
- Usuarios atacados: ec2-user, admin, ubuntu.
- Actividad interna legítima: cron, login.
---
**3.2**:
- Ejecuciones de sudo desde cuentas de servicio.
- Escaneos internos.
- Accesos desde ubicaciones inesperadas.
---
**3.3**:
- IPs con exactamente 3 intentos fallidos → patrón de botnet.
- Usuarios atacados: root, nginx, www-data, admin, ec2-user.
- Diccionarios automáticos: XXmith, XXhnson.
- Servicios críticos: ssh, sudo, su, login, cron.
- Protocolos inseguros: TELNET, RDP.

## Conclusión del Dataset 3
Los tres subconjuntos muestran cómo se manifiestan fuerza bruta, escalada de privilegios y actividad automatizada en logs de autenticación Linux.

## 4. Comparación Final entre los Datasets 1, 2 y 3
|Aspecto	|Dataset 1	|Dataset 2	|Dataset 3 |
|:--|:--|:--|:--|
|Tipo de sistema|	Servidor web|	Red IoT |	Servidor Linux|
|Actividad |normal |	Muy baja	|Alta	|Media |
|Actividad |automatizada|	Muy alta	|Media |	Muy alta|
|Actividad| maliciosa	|Escaneos, bots	|Ataques etiquetados	|Fuerza bruta, escalada|
|Indicadores clave|	Hostnames, rangos| IP	attack_type|	usuarios, servicios, protocolos|

## Conclusión comparativa final
Los tres datasets muestran diferentes fases del ciclo de ataque:

- **Dataset 1** → Reconocimiento externo
- **Dataset 2** → Explotación y ataques activos
- **Dataset 3** → Intentos de acceso y persistencia

En conjunto, ofrecen una visión completa del comportamiento de sistemas expuestos a Internet.

## 5. Visualizaciones Finales

- **Gráfico 1** — Top IPs por intentos fallidos (Dataset 3.3)
- ![](imagenes/ii13.png)
- **Gráfico 2** — Usuarios más atacados (Dataset 3.3)
- ![](imagenes/ii14.png)
- **Gráfico 3** — Servicios más utilizados (Dataset 3.3)
- ![](imagenes/ii15.png)


## 6. Conclusiones Generales del Proyecto
El análisis conjunto de los tres datasets permite:
- Diferenciar entre actividad normal, automatizada y maliciosa.
- Identificar patrones de fuerza bruta, escaneo y escalada de privilegios.
- Comprender cómo se comportan servidores Linux y redes IoT expuestas a Internet.
- Detectar señales tempranas de ataque mediante análisis de logs y SQL.
- Reconocer el “ruido” constante de Internet frente a tráfico legítimo.
- El proyecto demuestra que el análisis sistemático de logs es fundamental para la detección temprana de amenazas.

## 7. Trabajo Futuro
- Integrar estos análisis en un dashboard interactivo (opcional).
- Aplicar machine learning para clasificación automática de eventos.
- Diseñar reglas de alerta basadas en los patrones detectados.
