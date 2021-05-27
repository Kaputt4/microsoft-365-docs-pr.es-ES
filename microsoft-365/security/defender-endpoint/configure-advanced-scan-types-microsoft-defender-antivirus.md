---
title: Configurar opciones de examen para Antivirus de Microsoft Defender
description: Puede configurar Microsoft Defender AV para examinar los archivos de almacenamiento de correo electrónico, los puntos de copia de seguridad o de repetición, los archivos de red y los archivos archivados (como .zip archivos).
keywords: análisis avanzados, análisis, correo electrónico, archivo, zip, rar, archivo, análisis de repetición
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.date: 05/26/2021
ms.topic: how-to
ms.openlocfilehash: 34f423222068236271afdda13afb95cffa58b709
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683816"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Configurar opciones de análisis del Antivirus de Microsoft Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Usar Microsoft Intune para configurar opciones de examen

Vea los siguientes recursos: 

- [Configurar las opciones de restricción de dispositivo en Microsoft Intune](/intune/device-restrictions-configure) 
- [Antivirus de Microsoft Defender de restricción de dispositivos para Windows 10 en Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Usar Microsoft Endpoint Manager para configurar opciones de examen

Vea [How to create and deploy antimalware policies: Scan settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).

## <a name="use-group-policy-to-configure-scanning-options"></a>Usar la directiva de grupo para configurar opciones de examen

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.

3. En el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**

4. Expanda el árbol para **Windows componentes Antivirus de Microsoft Defender** y, a continuación, seleccione una ubicación  >  (consulte Configuración [y ubicaciones](#settings-and-locations) de este artículo).

5. Edite el objeto de directiva. 

6. Haga **clic en** Aceptar y repita cualquier otra configuración.

### <a name="settings-and-locations"></a>Configuración y ubicaciones

| Ubicación y elemento de directiva | Configuración predeterminada (si no está configurada) | Parámetro de PowerShell `Set-MpPreference` o propiedad WMI para `MSFT_MpPreference` clase |
|---|---|---|
| Análisis de correo electrónico <p> **Examen**  >  **Activar el examen de correo electrónico**<p>Vea [Limitaciones del examen de correo](#email-scanning-limitations) electrónico (en este artículo) | Deshabilitada | `-DisableEmailScanning` |
|Examinar [puntos de repetición](/windows/win32/fileio/reparse-points) <p> **Examen**  >  **Activar el examen de puntos de repetición** | Deshabilitada | No disponible <p>Ver [Puntos de reanco](/windows/win32/fileio/reparse-points)  |
| Examinar unidades de red asignadas <p> **Examen**  >  **Ejecutar examen completo en unidades de red asignadas** | Deshabilitada | `-DisableScanningMappedNetworkDrivesForFullScan`|
| Examinar archivos de archivo (como .zip o .rar archivos).  <p> **Examen**  >  **Examinar archivos de archivo** | Habilitado | `-DisableArchiveScanning` <p>La [lista de exclusiones de extensiones](configure-extension-file-exclusions-microsoft-defender-antivirus.md) tendrá prioridad sobre esta configuración.|
| Examinar archivos en la red <p> **Examen**  >  **Examinar archivos de red** | Deshabilitada | `-DisableScanningNetworkFiles` |
| Examinar archivos ejecutables empaquetados <p> **Examen**  >  **Examinar archivos ejecutables empaquetados** | Habilitado | No disponible |
| Examinar solo unidades extraíbles durante exámenes completos <p> **Examen**  >  **Examinar unidades extraíbles** | Deshabilitada | `-DisableRemovableDriveScanning` |
| Especificar el nivel de subcarpetas dentro de una carpeta de archivo para examinar <p>**Examen**  >  **Especificar la profundidad máxima para examinar archivos de archivo** | 0 | No disponible |
| Especifique la carga máxima de CPU (como porcentaje) durante un examen. <p> **Examen**  >  **Especificar el porcentaje máximo de uso de CPU durante un examen** | 50 |  `-ScanAvgCPULoadFactor` <p>**NOTA:** La carga máxima de CPU no es un límite difícil, pero es una guía para que el motor de análisis no supere el máximo en promedio. Los exámenes de ejecución manual omitirán esta configuración y se ejecutarán sin límites de CPU. |
| Especifique el tamaño máximo (en kilobytes) de los archivos de archivo que deben examinarse. <p> **Examen**  >  **Especificar el tamaño máximo de los archivos de archivo que se examinarán** | Sin límite | No disponible <p>El valor predeterminado de 0 no aplica ningún límite |
| Configurar una prioridad de CPU baja para exámenes programados <p> **Examen**  >  **Configurar una prioridad de CPU baja para exámenes programados** | Deshabilitada | No disponible |
 
> [!NOTE]
> Si la protección en tiempo real está activada, los archivos se examinan antes de tener acceso a ellos y ejecutarse. El ámbito de examen incluye todos los archivos, incluidos los archivos en medios extraíbles montados, como las unidades USB. Si el dispositivo que realiza el examen tiene activada la protección en tiempo real o la protección en tiempo real, el examen también incluirá recursos compartidos de red.

## <a name="use-powershell-to-configure-scanning-options"></a>Usar PowerShell para configurar opciones de examen

Vea los siguientes recursos:

- [Administrar Antivirus de Microsoft Defender con cmdlets de PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Cmdlets de Defender](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>Usar WMI para configurar opciones de examen

Vea [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="email-scanning-limitations"></a>Limitaciones del examen de correo electrónico

El examen de correo electrónico permite examinar los archivos de correo Outlook y otros clientes de correo durante los exámenes a petición y programados. También se examinan los objetos incrustados en el correo electrónico (como datos adjuntos y archivos archivados). Los siguientes tipos de formato de archivo se pueden examinar y corregir:

- DBX
- MBX
- MIME

Los archivos PST usados por Outlook 2003 o versiones anteriores (donde el tipo de archivo está establecido en no unicode) también se examinan, pero Antivirus de Microsoft Defender no puede corregir las amenazas que se detectan dentro de los archivos PST.

Si Antivirus de Microsoft Defender detecta una amenaza dentro de un mensaje de correo electrónico, le mostrará la siguiente información para ayudarle a identificar el correo electrónico en peligro, para que pueda corregir la amenaza manualmente:

- Asunto del correo electrónico
- Nombre de datos adjuntos

## <a name="see-also"></a>Consulte también

- [Personalizar, iniciar y revisar los resultados de Antivirus de Microsoft Defender análisis y corrección](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Configurar y ejecutar análisis bajo petición en el Antivirus de Microsoft Defender](run-scan-microsoft-defender-antivirus.md)
- [Configurar exámenes Antivirus de Microsoft Defender programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
