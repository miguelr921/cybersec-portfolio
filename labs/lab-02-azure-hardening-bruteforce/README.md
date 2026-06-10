# Lab 02 — Hardening de VM en Azure + Detección de Ataque de Fuerza Bruta

**Categoría:** Cloud Security · Hardening · Brute Force Detection · Log Analysis  
**Entorno:** Microsoft Azure · Linux  
**Fecha:** 2025  
**Dificultad:** Básico-Intermedio

---

## 1. Objetivo

- Desplegar y asegurar una máquina virtual en Azure aplicando reglas de firewall desde terminal.
- Simular un ataque de fuerza bruta controlado contra la propia VM.
- Analizar los logs generados y seguir el ciclo de vida de las alertas (alert triage).

---

## 2. Arquitectura del Entorno

| Componente | Detalle |
|---|---|
| Proveedor Cloud | Microsoft Azure |
| Sistema Operativo | [Completar: ej. Ubuntu 22.04 LTS] |
| Terminal Usada | Warp |
| Herramientas de Firewall | [Completar: ej. UFW / Azure NSG] |
| Herramienta de Ataque | [Completar: ej. Hydra / manual SSH] |

---

## 3. Fases de Ejecución

### Fase A — Despliegue de la VM en Azure

> 📝 *Describe aquí los pasos seguidos: tipo de instancia, SO elegido, configuración inicial de red.*

---

### Fase B — Hardening: Configuración del Firewall desde Terminal

Los comandos utilizados para aplicar las reglas de firewall fueron:

```bash
# [Pegar aquí los comandos UFW o Azure CLI utilizados]
# Ejemplo:
ufw default deny incoming
ufw default allow outgoing
ufw allow 22/tcp
ufw enable
ufw status verbose
```

> 📝 *Explica las decisiones tomadas: qué puertos bloqueaste, por qué, y cuál era la superficie de ataque antes y después.*

---

### Fase C — Simulación del Ataque de Fuerza Bruta

> 📝 *Describe el ataque que ejecutaste: herramienta usada, protocolo objetivo (SSH, RDP), número de intentos, resultado.*

```bash
# [Pegar aquí el comando del ataque, si aplica]
```

---

### Fase D — Análisis de Logs y Follow-up de Alertas

Ruta de los logs analizados:
```
[Completar: ej. /var/log/auth.log | /var/log/syslog | Azure Monitor]
```

Patrón identificado en los logs:

```
[Pegar aquí un extracto anonimizado del log que evidencia el ataque]
```

**Indicadores de Compromiso (IoCs) identificados:**
- IP de origen del ataque: `[Completar]`
- Número de intentos fallidos: `[Completar]`
- Ventana temporal del ataque: `[Completar]`
- Cuenta objetivo: `[Completar]`

---

## 4. Evidencias

> 📁 Ver: `evidence/01-firewall-rules-before.png`  
> 📁 Ver: `evidence/02-firewall-rules-after.png`  
> 📁 Ver: `evidence/03-bruteforce-logs.png`  
> 📁 Ver: `evidence/04-alert-triage.png`  

---

## 5. Análisis y Conclusiones

> 📝 *¿Qué demostró este laboratorio? ¿Qué hubiese pasado sin el hardening previo? ¿Las alertas fueron suficientemente claras para un analista?*

**Hallazgos clave:**
- [Completar con tus observaciones]

**Controles implementados:**
- ✅ Reducción de superficie de ataque mediante reglas de firewall granulares.
- ✅ Detección del ataque a través del análisis de logs nativos.
- ⚠️ [Agregar gaps o mejoras identificadas]

---

## 6. Lecciones Aprendidas

- [Completar con lo que aprendiste del proceso]

---

## 7. Referencias

- [Azure Network Security Groups](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-groups-overview)
- [Ubuntu UFW Documentation](https://help.ubuntu.com/community/UFW)
- [NIST SP 800-115 — Technical Guide to Information Security Testing](https://csrc.nist.gov/publications/detail/sp/800-115/final)

---

*Laboratorio realizado en entorno controlado con fines educativos. El ataque fue ejecutado contra infraestructura propia.*
