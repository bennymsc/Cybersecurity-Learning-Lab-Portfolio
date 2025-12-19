Laboratorio de **Network Forensics** donde se analiza tráfico de red capturado en un archivo PCAP para investigar la aparición de un archivo sospechoso en un servidor web corporativo.

El objetivo es identificar cómo se introdujo el archivo, qué actividad maliciosa ocurrió y evaluar el alcance de una posible intrusión.

> Tipo de entorno: Análisis de tráfico HTTP (PCAP)

---

## 🎯 Objetivo
Analizar el archivo PCAP proporcionado para:
- Identificar actividad sospechosa contra un servidor web
- Determinar el vector de acceso inicial
- Detectar posibles fases de ejecución, comando y control o exfiltración
- Comprender el flujo completo del ataque a nivel de red

---

## 🛠️ Herramientas utilizadas
- **Wireshark**

---

## 🔍 Metodología

### 1. Análisis inicial del tráfico
Se cargó el archivo PCAP en Wireshark para obtener una visión general del tráfico capturado.

Acciones iniciales:
- Revisión de protocolos más frecuentes
- Identificación de tráfico HTTP
- Análisis de direcciones IP internas y externas

Esto permitió centrar la investigación en comunicaciones web potencialmente maliciosas.

---

### 2. Inspección de tráfico HTTP
Se aplicaron filtros para aislar tráfico HTTP relevante, prestando especial atención a:
- Solicitudes `POST`
- Descargas de archivos
- Respuestas del servidor con contenido anómalo

Durante esta fase se identificaron peticiones sospechosas que indicaban posible **subida o descarga de archivos no autorizados**.

---

### 3. Reconstrucción de la actividad
A partir del análisis del tráfico:
- Se siguió el flujo de las conversaciones HTTP
- Se correlacionaron las peticiones con el momento en que apareció el archivo sospechoso
- Se evaluó si existían indicios de comunicación posterior con el atacante

Esto permitió reconstruir la secuencia de eventos y entender el comportamiento observado en la red.

---

## ✅ Resultado
El análisis confirmó que:
- El servidor web recibió tráfico malicioso
- El archivo sospechoso fue introducido a través de peticiones HTTP
- Se observaron indicios de comportamiento compatible con acceso inicial y posible ejecución remota

No se incluyen flags ni datos sensibles, siguiendo las normas de la plataforma.

---

## 🧠 Aprendizajes clave
- Cómo analizar tráfico HTTP en un PCAP usando Wireshark
- Importancia de filtrar correctamente para reducir ruido
- Cómo reconstruir una línea temporal de ataque a partir de tráfico de red
- Identificación de comportamientos anómalos sin necesidad de acceso al host

---

## 🛡️ Mitigaciones y buenas prácticas
- Implementar validaciones estrictas en aplicaciones web para evitar subida de archivos maliciosos
- Monitorizar tráfico HTTP en busca de patrones anómalos
- Uso de WAF para detectar y bloquear solicitudes sospechosas
- Registro y correlación de logs de red y servidor web

---

## 🔖 Etiquetas
`#network-forensics` `#pcap` `#wireshark` `#http` `#initial-access` `#execution`
