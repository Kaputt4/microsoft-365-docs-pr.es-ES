---
title: Programar los exámenes de antivirus con la directiva de grupo
description: Usar la directiva de grupo para configurar exámenes antivirus
keywords: examen rápido, examen completo, programación, directiva de grupo, antivirus
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 339f98bf8e25fe1795db98739020c36789f8e844
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555697"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>Programar los exámenes de antivirus con la directiva de grupo

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

En este artículo se describe cómo configurar exámenes programados mediante la directiva de grupo. Para obtener más información sobre la programación de exámenes y sobre los tipos de examen, vea [Configure scheduled quick or full Antivirus de Microsoft Defender scans](schedule-antivirus-scans.md). 

## <a name="configure-antivirus-scans-using-group-policy"></a>Configurar exámenes antivirus mediante la directiva de grupo

1. En el equipo de administración de directivas de  grupo, en el Editor de directivas de grupo, vaya a Configuración del equipo Plantillas administrativas \>  \> **Windows componentes** \> **Antivirus de Microsoft Defender** \> **Examinar**.

2. Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.

3. Especifique la configuración del objeto de directiva de grupo y, a continuación, seleccione **Aceptar**. 

4. Repita los pasos del 1 al 4 para cada configuración que desee configurar.

5. Implemente el objeto de directiva de grupo como lo hace normalmente. Si necesita ayuda con objetos de directiva de grupo, vea [Crear un objeto de directiva de grupo](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).

> [!NOTE]
> Al configurar exámenes programados, la configuración Iniciar el examen programado solo cuando el equipo está activado pero no está en uso **,** que está habilitado de forma predeterminada, puede afectar a la hora programada esperada al requerir que el equipo esté inactivo primero.
>
> Para los exámenes semanales, el comportamiento predeterminado en Windows Server es examinar fuera del mantenimiento automático cuando la máquina está inactiva. El valor predeterminado en Windows 10 y posteriores es examinar durante el mantenimiento automático cuando la máquina está inactiva. Para cambiar este comportamiento, modifique la configuración **deshabilitando ScanOnlyIfIdle** y, a continuación, defina una programación.

Para obtener más información, vea [administrar](manage-protection-update-schedule-microsoft-defender-antivirus.md) cuándo se deben descargar y aplicar las actualizaciones de protección y evitar o permitir a los usuarios [modificar localmente los](configure-local-policy-overrides-microsoft-defender-antivirus.md) temas de configuración de directivas.

## <a name="group-policy-settings-for-scheduling-scans"></a>Configuración de directiva de grupo para la programación de exámenes

| Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|:---|:---|:---|:---|
| Examinar | Especificar el tipo de examen que se usará para un examen programado | Examen rápido |
| Examinar | Especificar el día de la semana para ejecutar un examen programado | Especifique el día (o nunca) para ejecutar un examen. | Nunca |
| Examinar | Especificar la hora del día para ejecutar un examen programado | Especifique el número de minutos después de medianoche (por ejemplo, escriba **60** para la 1 a.m.). | 2 a. m. |
| Raíz | Randomize scheduled task times |En Antivirus de Microsoft Defender, aleatorice la hora de inicio del examen a cualquier intervalo de 0 a 4 horas. <p>En [SCEP,](/mem/intune/protect/certificates-scep-configure)aleatorice los exámenes a cualquier intervalo más o menos 30 minutos. Esto puede ser útil en máquinas virtuales o implementaciones de VDI. | Habilitado |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>Configuración de directiva de grupo para la programación de exámenes cuando un extremo no está en uso

| Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|:---|:---|:---|:---|
| Examinar | Iniciar el examen programado solo cuando el equipo está en uso pero no está en uso | Los exámenes programados no se ejecutarán, a menos que el equipo esté en uso pero no esté en uso | Habilitado |

> [!NOTE]
> Al programar exámenes para las horas en las que los puntos de conexión no están en uso, los exámenes no respetan la configuración de limitación de CPU y aprovechan al máximo los recursos disponibles para completar el examen lo más rápido posible.

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>Configuración de directiva de grupo para programar exámenes necesarios para la corrección

| Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|---|---|---|---|
| Corrección | Especificar el día de la semana para ejecutar un examen completo programado para completar la corrección | Especifique el día (o nunca) para ejecutar un examen. | Nunca |
| Corrección | Especificar la hora del día para ejecutar un examen completo programado para completar la corrección | Especifique el número de minutos después de la medianoche (por ejemplo, escriba **60** para la 1 a.m.) | 2 a. m. |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>Configuración de directiva de grupo para programar exámenes diarios

| Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|:---|:---|:---|:---|
| Examinar | Especificar el intervalo para ejecutar exámenes rápidos por día | Especifique cuántas horas debe transcurrir antes del siguiente examen rápido. Por ejemplo, para ejecutarse cada dos horas, escriba **2**, para una vez al día, escriba **24**. Escriba **0** para nunca ejecutar un examen rápido diario. | Nunca |
| Examinar | Especificar la hora de un examen rápido diario | Especifique el número de minutos después de la medianoche (por ejemplo, escriba **60** para la 1 a.m.) | 2 a. m. |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>Configuración de directiva de grupo para programar exámenes después de actualizaciones de protección

| Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada)|
|:---|:---|:---|:---|
| Actualizaciones de firmas | Activar el examen después de la actualización de inteligencia de seguridad | Un examen se realizará inmediatamente después de descargar una nueva actualización de protección | Habilitado |

