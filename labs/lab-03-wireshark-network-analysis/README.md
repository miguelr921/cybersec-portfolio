# Lab 03 — Análisis de Tráfico de Red con Wireshark

**Categoría:** Network Analysis · Threat Detection · Blue Team  
**Entorno:** Wireshark · Red de laboratorio  
**Fecha:** 2025  
**Dificultad:** Intermedio

---

## 1. Objetivo

- Capturar y analizar tráfico de red con Wireshark para identificar actividad sospechosa.
- Reconocer patrones asociados a escaneos de red, ataques de intermediario (MITM) y firmas de malware.
- Practicar el triaje de paquetes y la lectura de protocolos como parte del flujo de detección defensiva.

---

## 2. Herramientas

| Herramienta | Uso |
|---|---|
| Wireshark | Captura y análisis de paquetes |
| Filtros de visualización | Aislamiento de tráfico relevante por protocolo/host |

---

## 3. Análisis Realizado

### 3.1 Detección de escaneos de red

Análisis de capturas para identificar patrones de escaneo: ráfagas de paquetes hacia múltiples puertos o hosts, y handshakes TCP incompletos característicos de la fase de reconocimiento de un atacante.

### 3.2 Análisis de ataques de intermediario (MITM)

Revisión de tráfico en busca de indicadores de ataques MITM, observando anomalías en la resolución de direcciones y en el flujo esperado de las comunicaciones entre hosts de la red.

### 3.3 Identificación de firmas de malware

Inspección de payloads y patrones de comunicación para reconocer firmas e indicadores asociados a tráfico potencialmente malicioso.

---

## 4. Aprendizajes

- Uso de filtros de visualización para aislar rápidamente el tráfico relevante durante el triaje.
- Reconocimiento de los patrones de red que delatan reconocimiento, MITM y comunicación maliciosa.
- Refuerzo del enfoque defensivo: la visibilidad del tráfico es clave para la detección temprana de amenazas.

---

> **Nota sobre evidencias:** Por motivos de seguridad y privacidad, este writeup no incluye capturas de pantalla, ya que contendrían la dirección IP pública utilizada en el laboratorio. El análisis se describe a nivel de patrones y metodología.
