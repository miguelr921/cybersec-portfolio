# Lab 01 — Auditoría de Active Directory: Offboarding y Event ID 4725

**Categoría:** Active Directory · Forense de Logs · Control de Accesos  
**Entorno:** Microsoft Azure · Windows Server 2025  
**Fecha:** 2025  
**Dificultad:** Básico-Intermedio

---

## 1. Objetivo

Simular y auditar el ciclo de vida completo del **offboarding forzado de un usuario** en un entorno corporativo controlado.

Los objetivos específicos fueron:
- Validar la eficacia de los controles de acceso lógico en Active Directory.
- Verificar la generación de rastros forenses en los registros de auditoría de Windows Server.
- Demostrar el principio de **no repudio y trazabilidad** ante marcos normativos.

---

## 2. Arquitectura del Entorno

| Componente | Detalle |
|---|---|
| Proveedor Cloud | Microsoft Azure |
| Sistema Operativo | Windows Server 2025 Datacenter |
| Nombre del Servidor | `AuditLogRule` |
| Dominio | `empresa.local` |
| Roles Instalados | AD DS, DNS Server |
| Acceso Externo | RDP sobre cliente nativo local |

El servidor fue promovido a **Controlador de Dominio (DC) raíz** de un nuevo bosque aislado, aplicando las directivas de seguridad base del sistema operativo.

---

## 3. Fases de Ejecución

### Fase A — Despliegue de Servicios de Identidad (AD DS)

1. Instalación del rol **Active Directory Domain Services (AD DS)** y **DNS Server** mediante Server Manager.
2. Promoción del servidor como DC raíz de un nuevo bosque (`empresa.local`).
3. Aplicación de políticas de seguridad base del SO.

---

### Fase B — Creación y Simulación de Sesión Activa

1. Se aprovisionó un usuario de prueba en la base de datos de AD (`NTDS.dit`) bajo el contenedor `Users`.
2. Se asignaron privilegios de **Remote Desktop** al usuario para simular una sesión interactiva activa, replicando un escenario realista de producción con conexiones concurrentes.

---

### Fase C — Aplicación del Control de Aislamiento (Offboarding)

Ante el escenario simulado de salida del colaborador, se ejecutaron las siguientes acciones de mitigación:

**Control Preventivo — Deshabilitación de la cuenta:**
- Se modificó el objeto de usuario en AD cambiando su estado a `Disabled`.
- Este control invalida de raíz los tokens de acceso, bloqueando cualquier intento futuro de autenticación en la red.

---

## 4. Evidencias y Resultados

### Evidencia 1 — Estado Estático de la Cuenta (Control Preventivo)

En la consola de **Active Directory Users and Computers**, el objeto del usuario muestra el icono estándar de Microsoft con una flecha negra apuntando hacia abajo, confirmando que la cuenta no tiene capacidad de autenticarse en el dominio.

> 📁 Ver: `evidence/01-cuenta-deshabilitada-ad.png`

---

### Evidencia 2 — Registro Forense del Evento (Control Detectivo)

Se analizó el registro de auditoría de Windows en:
```
Windows Logs > Security
```

Tras aplicar un filtro específico, se aisló el siguiente evento crítico:

| Campo | Valor |
|---|---|
| **Event ID** | `4725` |
| **Descripción** | *A user account was disabled* |
| **Timestamp** | Registrado con precisión milimétrica |
| **Cuenta afectada** | Usuario de prueba (`empresa.local`) |
| **Sujeto ejecutor** | Administrador del dominio |

> 📁 Ver: `evidence/02-event-id-4725-security-log.png`

---

## 5. Análisis y Conclusiones

La obtención del **Event ID 4725** confirma que la infraestructura implementada preserva una **trazabilidad forense íntegra**, garantizando:

- ✅ **No repudio:** El log registra la identidad exacta del administrador que ejecutó la acción.
- ✅ **Trazabilidad:** Timestamp preciso del bloqueo y datos de la cuenta afectada.
- ✅ **Cumplimiento normativo:** Los hallazgos poseen validez probatoria ante auditorías externas bajo marcos como ISO 27001, NIST o SOX.

Se optó por la auditoría mediante los registros nativos del sistema (Event Viewer) en lugar de soluciones externas, garantizando que las evidencias sean íntegras y admisibles en procesos de inspección legal.

---

## 6. Lecciones Aprendidas

- La correcta configuración de **políticas de auditoría** en Windows Server es fundamental para que los eventos de seguridad queden registrados. Sin `Audit Account Management` habilitado, el Event ID 4725 no se genera.
- El **offboarding inmediato** (deshabilitar la cuenta antes de notificar al usuario) es una mejor práctica crítica para mitigar riesgos de exfiltración de datos o sabotaje.
- Los Event IDs de la familia `4720–4740` son clave para cualquier SOC Analyst que monitoree entornos con Active Directory.

---

## 7. Referencias

- [Microsoft Docs — Event ID 4725](https://learn.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4725)
- [NIST SP 800-53 — Access Control (AC)](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
- [Active Directory Security Audit Best Practices](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/audit-policy-recommendations)

---

*Laboratorio realizado en entorno controlado con fines educativos.*
