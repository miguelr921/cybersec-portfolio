# Cybersecurity Lab Portfolio — Miguel Regalado

Auditor de TI/GRC y estudiante de Ciberseguridad (PUCMM, en curso). Este repositorio documenta laboratorios prácticos de seguridad defensiva, auditoría de controles de acceso y análisis de logs/red, enfocados en entornos Microsoft Azure, Active Directory y Windows/Linux.

**Enfoque honesto:** cada laboratorio refleja trabajo realmente ejecutado o, cuando corresponde, se marca claramente como *en progreso*. No se documentan resultados que no se hayan obtenido.

---

## Índice de Laboratorios

### 1. Auditoría de ciclo de vida de identidades — Active Directory (Event ID 4725)
**Objetivo:** auditar el offboarding forzado de un usuario en Active Directory.
**Herramientas:** Microsoft Azure · Windows Server 2025 · registros de auditoría de Windows.
**Aprendizaje:** validación del control preventivo (deshabilitación de cuenta) y del control detectivo mediante el Event ID 4725, garantizando trazabilidad y no repudio.
[Ver writeup »](./labs/lab-01-event-id-4725)

### 2. Hardening de VM en Azure + Detección de Fuerza Bruta
**Objetivo:** asegurar una VM Ubuntu en Azure con firewall sobre SSH y detectar un ataque de fuerza bruta.
**Herramientas:** Microsoft Azure · Ubuntu Linux · Warp.
**Aprendizaje:** reducción de la superficie de ataque vía firewall y análisis de logs en Azure para validar la detección del ataque.
[Ver writeup »](./labs/lab-02-azure-hardening-bruteforce)

### 3. Wireshark — Análisis de tráfico de red
**Objetivo:** analizar tráfico de red para identificar actividad sospechosa.
**Herramientas:** Wireshark.
**Aprendizaje:** detección de escaneos, ataques MITM y firmas de malware en capturas de red.
[Ver writeup »](./labs/lab-03-wireshark-network-analysis)

---

## Marcos y estándares de referencia
ISO/IEC 27001 · PCI DSS · NIST · CIS Benchmarks

## Contacto
Miguel Regalado — Santo Domingo, República Dominicana
