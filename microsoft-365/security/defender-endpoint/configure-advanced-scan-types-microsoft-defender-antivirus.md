---
title: Configurar opciones de análisis para Microsoft Defender AV
description: Puede configurar Microsoft Defender AV para examinar los archivos de almacenamiento de correo electrónico, los puntos de copia de seguridad o de repetición, los archivos de red y los archivos archivados (como los archivos .zip).
keywords: análisis avanzados, análisis, correo electrónico, archivo, zip, rar, archivo, análisis de repetición
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 625c84e79efe53cae2bc8f511726ad3f384ea505
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691068"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Configurar opciones de análisis de Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Usar Microsoft Intune para configurar opciones de examen

Para [obtener más información,](/intune/device-restrictions-configure) consulta Configurar la configuración de restricción de dispositivos de Microsoft Intune y Antivirus de Microsoft Defender para [Windows 10 en Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Usar Microsoft Endpoint Manager para configurar opciones de análisis

Vea [How to create and deploy antimalware policies: Scan settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) for details on configuring Microsoft Endpoint Manager (current branch).

## <a name="use-group-policy-to-configure-scanning-options"></a>Usar la directiva de grupo para configurar opciones de examen

Para configurar las opciones de directiva de grupo que se describen en la tabla siguiente:

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**

3. Expande el árbol a **componentes de Windows > Antivirus** de Microsoft Defender y, a continuación, la **ubicación** especificada en la tabla siguiente.

4. Haga doble clic en la configuración **de directiva** especificada en la tabla siguiente y establezca la opción en la configuración deseada. Haga **clic en** Aceptar y repita cualquier otra configuración.

Descripción | Ubicación y configuración | Configuración predeterminada (si no está configurada) | Parámetro de PowerShell `Set-MpPreference` o propiedad WMI para `MSFT_MpPreference` clase
---|---|---|---
Examen de correo electrónico Vea [Limitaciones de examen de correo electrónico](#ref1)| Examinar > Activar el examen de correo electrónico | Deshabilitada | `-DisableEmailScanning`
Examinar [puntos de repetición](/windows/win32/fileio/reparse-points) | Examinar > Activar el examen de puntos de repetición | Deshabilitada | No disponible
Examinar unidades de red asignadas | Examinar > realizar el examen completo en unidades de red asignadas | Deshabilitada | `-DisableScanningMappedNetworkDrivesForFullScan`
 Examinar archivos de archivo (como archivos .zip o .rar). La [lista de exclusiones de extensiones](configure-extension-file-exclusions-microsoft-defender-antivirus.md) tendrá prioridad sobre esta configuración. | Examinar > archivos de archivo | Habilitado | `-DisableArchiveScanning`
Examinar archivos en la red | Examinar > Detección de archivos de red | Deshabilitada | `-DisableScanningNetworkFiles`
Examinar archivos ejecutables empaquetados | Examinar > ejecutables empaquetados | Habilitado | No disponible
Examinar solo unidades extraíbles durante exámenes completos | Examinar > unidades extraíbles | Deshabilitada | `-DisableRemovableDriveScanning`
Especificar el nivel de subcarpetas dentro de una carpeta de archivo para examinar | Examinar > Especificar la profundidad máxima para examinar archivos de archivo | 0 | No disponible
 Especifique la carga máxima de CPU (como porcentaje) durante un examen. Nota: Este no es un límite difícil, sino una guía para que el motor de análisis no supere este máximo en promedio. | Examen > Especifica el porcentaje máximo de uso de LA CPU durante un examen | 50 |  `-ScanAvgCPULoadFactor`
 Especifique el tamaño máximo (en kilobytes) de los archivos de archivo que deben examinarse. El valor predeterminado, **0**, no aplica ningún límite | Examinar > especificar el tamaño máximo de los archivos de archivo que se examinarán | Sin límite | No disponible
 Configurar una prioridad de CPU baja para exámenes programados | Examen > configurar la prioridad de CPU baja para exámenes programados | Deshabilitada | No disponible
 
> [!NOTE]
> Si la protección en tiempo real está activada, los archivos se examinan antes de tener acceso a ellos y ejecutarse. El ámbito de examen incluye todos los archivos, incluidos los archivos en medios extraíbles montados, como las unidades USB. Si el dispositivo que realiza el examen tiene activada la protección en tiempo real o la protección en tiempo real, el examen también incluirá recursos compartidos de red.

## <a name="use-powershell-to-configure-scanning-options"></a>Usar PowerShell para configurar opciones de examen

Consulte [Manage Microsoft Defender Antivirus with PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.

## <a name="use-wmi-to-configure-scanning-options"></a>Usar WMI para configurar opciones de examen

Para usar clases WMI, [vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a>Limitaciones del examen de correo electrónico

El examen de correo electrónico permite examinar los archivos de correo electrónico usados por Outlook y otros clientes de correo durante los exámenes a petición y programados. También se examinan los objetos incrustados dentro de un archivo de correo electrónico (como datos adjuntos y archivos archivados). Los siguientes tipos de formato de archivo se pueden examinar y corregir:

- DBX
- MBX
- MIME

También se examinarán los archivos PST usados por Outlook 2003 o versiones anteriores (donde el tipo de archivo está establecido en no unicode), pero Windows Defender no puede corregir las amenazas detectadas dentro de los archivos PST.

Si Antivirus de Microsoft Defender detecta una amenaza dentro de un correo electrónico, le mostrará la siguiente información para ayudarle a identificar el correo electrónico en peligro, para que pueda corregir la amenaza manualmente:

- Asunto del correo electrónico
- Nombre de datos adjuntos

## <a name="related-topics"></a>Temas relacionados

- [Personalizar, iniciar y revisar los resultados de los exámenes y la corrección del Antivirus de Microsoft Defender](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Configurar y ejecutar exámenes de Antivirus de Microsoft Defender a petición](run-scan-microsoft-defender-antivirus.md)
- [Configurar exámenes programados de Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)