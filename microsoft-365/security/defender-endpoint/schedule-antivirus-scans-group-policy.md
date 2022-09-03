---
title: Programar los exámenes de antivirus con la directiva de grupo
description: Uso de directiva de grupo para configurar exámenes antivirus
keywords: examen rápido, examen completo, programación, directiva de grupo, antivirus
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/10/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.subservice: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 522c565d98c2b90f3eec6faef699d627b5e941f0
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67582238"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>Programar los exámenes de antivirus con la directiva de grupo

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

En este artículo se describe cómo configurar exámenes programados mediante directiva de grupo. Para más información sobre la programación de exámenes y sobre los tipos de examen, consulte [Configuración de exámenes programados rápidos o completos del Antivirus de Microsoft Defender](schedule-antivirus-scans.md). 

## <a name="configure-antivirus-scans-using-group-policy"></a>Configuración de exámenes antivirus mediante directiva de grupo

1. En la máquina de administración de directiva de grupo, en el Editor de directiva de grupo, vaya a Configuración del **equipo** \> **Plantillas** \> administrativas **Componentes de Windows Antivirus** \> \> de **Microsoft Defender** **Examen**.

2. Haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y, a continuación, seleccione **Editar**.

3. Especifique la configuración del objeto directiva de grupo y, a continuación, seleccione **Aceptar**. 

4. Repita los pasos del 1 al 4 para cada configuración que quiera configurar.

5. Implemente el objeto directiva de grupo como lo hace normalmente. Si necesita ayuda con directiva de grupo Objects, consulte [Creación de un objeto directiva de grupo](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).

> [!NOTE]
> Al configurar exámenes programados, la opción **Iniciar el examen programado solo cuando el equipo está encendido pero no en uso**, que está habilitado de forma predeterminada, puede afectar a la hora programada esperada al requerir que la máquina esté inactiva primero.
>
> En el caso de los exámenes semanales, el comportamiento predeterminado en Windows Server es examinar fuera del mantenimiento automático cuando la máquina está inactiva. El valor predeterminado de Windows 10 y versiones posteriores es examinar durante el mantenimiento automático cuando la máquina está inactiva. Para cambiar este comportamiento, modifique la configuración deshabilitando **ScanOnlyIfIdle** y, a continuación, defina una programación.

Para obtener más información, consulte los temas [Administrar cuándo se deben descargar y aplicar las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md) y [Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) .

## <a name="group-policy-settings-for-scheduling-scans"></a>configuración de directiva de grupo para la programación de exámenes

| Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|:---|:---|:---|:---|
| Examinar | Especificar el tipo de examen que se va a usar para un examen programado | Examen rápido |
| Examinar | Especificar el día de la semana para ejecutar un examen programado | Especifique el día (o nunca) para ejecutar un examen. | Nunca |
| Examinar | Especificar la hora del día para ejecutar un examen programado | Especifique el número de minutos después de medianoche (por ejemplo, escriba **60** para la 1 a.m.). | 2 a.m. |
| Raíz | Aleatorizar los tiempos de las tareas programadas |En Antivirus de Microsoft Defender, aleatorice la hora de inicio del examen a cualquier intervalo de 0 a 23 horas. <p>En [SCEP](/mem/intune/protect/certificates-scep-configure), aleatorice los exámenes a cualquier intervalo más o menos 30 minutos. Esto puede ser útil en máquinas virtuales o implementaciones de VDI. | Habilitado |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>directiva de grupo la configuración de los exámenes de programación para cuando un punto de conexión no está en uso

| Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|:---|:---|:---|:---|
| Examinar | Iniciar el examen programado solo cuando el equipo está encendido, pero no en uso | Los exámenes programados no se ejecutarán, a menos que el equipo esté activado pero no en uso. | Habilitado |

> [!NOTE]
> Al programar exámenes en busca de tiempos en los que los puntos de conexión no están en uso, los exámenes no respetan la configuración de limitación de CPU y aprovecharán al máximo los recursos disponibles para completar el examen lo más rápido posible.

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>directiva de grupo configuración para programar los exámenes necesarios para la corrección

| Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|---|---|---|---|
| Remediación | Especificar el día de la semana para ejecutar un examen completo programado para completar la corrección | Especifique el día (o nunca) para ejecutar un examen. | Nunca |
| Remediación | Especificar la hora del día para ejecutar un examen completo programado para completar la corrección | Especifique el número de minutos después de medianoche (por ejemplo, escriba **60** para la 1 a.m.) | 2 a.m. |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>directiva de grupo configuración para programar exámenes diarios

| Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|:---|:---|:---|:---|
| Examinar | Especificar el intervalo para ejecutar exámenes rápidos al día | Especifique cuántas horas deben transcurrir antes del siguiente examen rápido. Por ejemplo, para ejecutarse cada dos horas, escriba **2**; para una vez al día, escriba **24**. Escriba **0** para no ejecutar nunca un examen rápido diario. | Nunca |
| Examinar | Especificar la hora de un examen rápido diario | Especifique el número de minutos después de medianoche (por ejemplo, escriba **60** para la 1 a.m.) | 2 a.m. |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>directiva de grupo configuración para programar exámenes después de las actualizaciones de protección

| Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada)|
|:---|:---|:---|:---|
| Actualizaciones de firma | Activar el examen después de la actualización de Inteligencia de seguridad | Un examen se producirá inmediatamente después de descargar una nueva actualización de protección. | Habilitado |

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)