---
title: Programar exámenes antivirus con la directiva de grupo
description: Usar la directiva de grupo para configurar exámenes antivirus
keywords: examen rápido, examen completo, programación, directiva de grupo, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 6f6018ec8b514234ab4f98e3d5416b472ff88739
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879795"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>Programar exámenes antivirus con la directiva de grupo

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

En este artículo se describe cómo configurar exámenes programados mediante la directiva de grupo. Para obtener más información sobre la programación de exámenes y sobre los tipos de examen, vea [Configure scheduled quick or full Antivirus de Microsoft Defender scans](schedule-antivirus-scans.md). 

## <a name="configure-antivirus-scans-using-group-policy"></a>Configurar exámenes antivirus mediante la directiva de grupo

1. En el equipo de administración de directivas de grupo, en el Editor de directivas de grupo, vaya a Configuración del equipo Plantillas administrativas  >    >  **Windows componentes**  >  **Antivirus de Microsoft Defender**  >  **Examinar**.

2. Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.

3. Especifique la configuración del objeto de directiva de grupo y, a continuación, seleccione **Aceptar**. 

4. Repita los pasos del 1 al 4 para cada configuración que desee configurar.

5. Implemente el objeto de directiva de grupo como lo hace normalmente. Si necesita ayuda con objetos de directiva de grupo, vea [Crear un objeto de directiva de grupo](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).

> [!TIP]
> Consulta Administrar [cuándo se deben descargar y](manage-protection-update-schedule-microsoft-defender-antivirus.md) aplicar las actualizaciones de protección y Evitar o permitir que los usuarios [modifiquen localmente los](configure-local-policy-overrides-microsoft-defender-antivirus.md) temas de configuración de directivas.

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

