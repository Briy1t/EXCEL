# Conclusión General del Grupo de Datasets (3.1, 3.2 y 3.3)

El análisis conjunto de los datasets 3.1, 3.2 y 3.3 permite comprender de forma clara cómo se comporta un servidor Linux expuesto a Internet y qué señales permiten diferenciar entre actividad normal,
actividad automatizada y actividad potencialmente maliciosa.


En el **Dataset 3.1**, se observa el funcionamiento típico de un servidor accesible públicamente: gran volumen de intentos de autenticación sobre SSH, tareas internas programadas **(cron)**,
accesos legítimos y un patrón horario coherente con procesos automáticos del sistema. Al mismo tiempo, la concentración de intentos fallidos sobre usuarios genéricos como `ec2-user` o `admin`
evidencia actividad sospechosa frecuente en servidores reales, donde **bots distribuidos** prueban credenciales comunes.


El **Dataset 3.2** introduce señales adicionales que ayudan a distinguir actividad normal de actividad anómala. 
Las ejecuciones de `sudo` desde cuentas de servicio, los escaneos de puertos y los accesos desde ubicaciones inesperadas muestran cómo ciertos comportamientos se desvían del uso legítimo 
y pueden servir como indicadores tempranos de riesgo. Este dataset permite identificar patrones que, en un entorno real, activarían alertas de seguridad.


El **Dataset 3.3** profundiza en la detección de actividad maliciosa mediante el análisis de intentos repetitivos desde múltiples IPs, variaciones automáticas de nombres de usuario y uso de servicios 
críticos como `ssh`, `sudo` y `su`.
La repetición exacta de intentos fallidos y la presencia de protocolos inseguros como **TELNET** permiten reconocer comportamientos automatizados que suelen pasar desapercibidos si no se analizan los logs de forma estructurada.
El análisis conjunto de los tres datasets permite comprender cómo se comportan distintos tipos de sistemas expuestos a Internet —servidores Linux, redes IoT y entornos simulados— y qué señales permiten diferenciar entre actividad normal, automatizada y claramente maliciosa.


El **Dataset 1** muestra un entorno con tráfico altamente automatizado y distribuido, donde predominan bots, escáneres y servidores remotos. La actividad humana es prácticamente inexistente.
Este comportamiento es típico de sistemas expuestos a Internet sin interacción directa de usuarios, donde la mayor parte del tráfico proviene de procesos automáticos, escaneos globales y sondas de reconocimiento. Este dataset permite identificar patrones de comportamiento “base” de Internet: ruido constante, escaneos y actividad no dirigida.
El **Dataset 2**, correspondiente a una red IoT, combina tráfico legítimo propio del ecosistema **(MQTT, DNS, HTTP/HTTPS)** con una presencia significativa de ataques reales. 
La variedad de técnicas detectadas —SYN Flood, ARP poisoning, escaneos NMAP, Slowloris, SSH brute force— muestra cómo una red IoT puede ser simultáneamente funcional y vulnerable. Este dataset permite distinguir con claridad entre flujos normales y flujos maliciosos, y demuestra cómo los dispositivos IoT pueden ser objetivo de campañas de ataque diversificadas.


**El grupo de datasets 3 (3.1, 3.2 y 3.3)**  profundiza en el análisis de logs de autenticación de servidores Linux. Aquí se observa una mezcla de actividad normal (cron, login, procesos internos) y actividad sospechosa o maliciosa (fuerza bruta distribuida, escalada de privilegios, diccionarios de usuarios, uso de protocolos inseguros). Los patrones repetitivos de intentos fallidos, la distribución geográfica del tráfico y la presencia de servicios críticos permiten identificar señales tempranas de ataque y comprender cómo se comporta un servidor Linux bajo presión externa.


**Conclusión final**: El estudio comparativo demuestra que, aunque cada entorno presenta comportamientos propios, todos comparten señales claras que permiten diferenciar entre tráfico legítimo, automatizado y malicioso. El análisis sistemático de logs —aplicando limpieza, consultas SQL y evaluación contextual— es fundamental para detectar amenazas de forma temprana y comprender el comportamiento real de sistemas expuestos a Internet. Estos datasets, analizados en conjunto, ofrecen una visión completa del ciclo de actividad, riesgo y ataque en infraestructuras modernas.

