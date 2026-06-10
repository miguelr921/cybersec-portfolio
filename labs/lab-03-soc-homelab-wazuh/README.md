# Lab 03 — SOC Home Lab: Despliegue de Wazuh SIEM + Análisis de Tráfico

**Categoría:** SIEM · Blue Team · Network Analysis · Threat Detection  
**Entorno:** VMware/VirtualBox · Ubuntu · Windows · Wazuh  
**Fecha:** 2025 - Presente  
**Dificultad:** Intermedio

---

## 1. Objetivo

Implementar un entorno de SOC doméstico funcional que permita:
- Monitoreo continuo de endpoints Windows y Linux mediante Wazuh (SIEM/XDR).
- Análisis de tráfico de red con Wireshark para identificar amenazas reales.
- Practicar el ciclo completo de detección y triaje de alertas.

---

## 2. Arquitectura del Home Lab

```
┌─────────────────────────────────────────────┐
│              HOST MACHINE                    │
│         (VMware / VirtualBox)               │
│                                             │
│  ┌──────────────┐    ┌──────────────────┐  │
│  │  Wazuh       │    │  Endpoint(s)     │  │
│  │  Manager     │◄───│  Windows / Linux │  │
│  │  (Ubuntu)    │    │  (con agente)    │  │
│  └──────┬───────┘    └──────────────────┘  │
│         │                                   │
│  ┌──────▼───────┐                          │
│  │  Wazuh       │                          │
│  │  Dashboard   │                          │
│  │  (Web UI)    │                          │
│  └──────────────┘                          │
└─────────────────────────────────────────────┘
```

| Componente | Detalle |
|---|---|
| SIEM/XDR | Wazuh [Completar versión] |
| Plataforma de Virtualización | [VMware / VirtualBox] |
| Servidor Wazuh | Ubuntu [Completar versión] |
| Endpoints Monitoreados | Windows [Completar] · Ubuntu [Completar] |

---

## 3. Despliegue de Wazuh

### 3.1 Instalación del Wazuh Manager

> 📝 *Describe el proceso de instalación: método usado (script oficial, Docker, manual), pasos de configuración iniciales.*

```bash
# [Comandos de instalación utilizados]
```

### 3.2 Registro de Agentes

> 📝 *¿Cómo registraste los endpoints? ¿Qué reglas o decoders customizaste?*

---

## 4. Casos de Uso y Detecciones

### Caso 1 — [Completar: ej. Detección de Escaneo Nmap]

**Descripción:** [Qué hiciste y qué detectó Wazuh]  
**Rule ID activada:** [Completar]  
**Nivel de alerta:** [Completar]

> 📁 Ver: `evidence/caso1-nmap-alerta.png`

---

### Caso 2 — [Completar: ej. Análisis de tráfico MITM con Wireshark]

**Descripción:** [Qué capturaste y cómo lo analizaste]  
**Hallazgo:** [Completar]

> 📁 Ver: `evidence/caso2-wireshark-mitm.png`

---

### Caso 3 — [Completar: ej. Firma de malware en PCAP]

> 📁 Ver: `evidence/caso3-malware-pcap.png`

---

## 5. Análisis y Conclusiones

> 📝 *¿Qué valor aporta este entorno para practicar habilidades de SOC? ¿Qué diferencias notaste entre el análisis de logs nativos y tener un SIEM centralizado?*

**Capacidades validadas:**
- ✅ Ingesta de logs en tiempo real desde múltiples endpoints.
- ✅ Correlación de eventos y generación de alertas automáticas.
- ✅ Detección de técnicas de reconocimiento (Nmap, MITM).
- ✅ Análisis forense de capturas de red (PCAP) con Wireshark.

---

## 6. Lecciones Aprendidas

- [Completar con tus observaciones más importantes del proceso]

---

## 7. Referencias

- [Wazuh Documentation](https://documentation.wazuh.com)
- [MITRE ATT&CK Framework](https://attack.mitre.org)
- [Wireshark User Guide](https://www.wireshark.org/docs/wsug_html_chunked/)

---

*Laboratorio en operación continua. Se actualiza con nuevos casos de uso.*
