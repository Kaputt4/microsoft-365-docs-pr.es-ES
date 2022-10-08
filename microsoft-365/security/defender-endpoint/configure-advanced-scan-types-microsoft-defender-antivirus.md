---
title: Configuración de opciones de examen para Microsoft Defender Antivirus
description: Puede configurar Microsoft Defender Antivirus para examinar archivos de almacenamiento de correo electrónico, puntos de copia de seguridad o de reanálisis, archivos de red y archivos archivados (por ejemplo, archivos .zip).
keywords: análisis avanzados, escaneo, correo electrónico, archivo, zip, rar, archivo, examen de repetición de análisis
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.date: 12/03/2021
ms.collection:
- m365-security
- tier2
ms.topic: how-to
search.appverid: met150
ms.openlocfilehash: 9280bb06c6701c05b42be5fa5c5686bfedfaf434
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68151483"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Configurar opciones de análisis del Antivirus de Microsoft Defender

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows 

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Uso de Microsoft Intune para configurar opciones de examen

Para obtener más información, consulte [Configuración de las opciones de restricción de dispositivos en Microsoft Intune](/intune/device-restrictions-configure) y [Microsoft Defender Configuración de restricciones de dispositivos antivirus para Windows 10 en Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Uso de Microsoft Endpoint Manager para configurar opciones de examen

Para obtener más información sobre cómo configurar Microsoft Endpoint Manager (rama actual), consulte [Creación e implementación de directivas antimalware: Configuración de examen](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).

## <a name="use-group-policy-to-configure-scanning-options"></a>Uso de directiva de grupo para configurar opciones de examen

> [!TIP]
> Descargue la hoja de cálculo de referencia de directiva de grupo, que muestra la configuración de directiva para las configuraciones de equipo y usuario que se incluyen en los archivos de plantilla administrativa entregados con para Windows. Puede configurar la referencia a la hoja de cálculo al editar directiva de grupo Objetos. <br/><br/> Estas son las versiones más recientes:
> - [Hoja de cálculo de referencia de configuración de directiva de grupo para Windows 10 actualización de mayo de 2020 (2004)](https://www.microsoft.com/download/details.aspx?id=101451)
> - [Hoja de cálculo de referencia de configuración de directiva de grupo para Windows 11 actualización de octubre de 2021 (21H2)](https://www.microsoft.com/download/details.aspx?id=103506)

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y, a continuación, seleccione **Editar**.

3. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y haga clic en **Plantillas administrativas**.

4. Expanda el árbol a **componentes** \> **de Windows Microsoft Defender Antivirus** y, a continuación, seleccione una ubicación (consulte [Configuración y ubicaciones](#settings-and-locations) de este artículo).

5. Edite el objeto de directiva.

6. Haga clic en **Aceptar** y repita cualquier otra configuración.

### <a name="settings-and-locations"></a>Configuración y ubicaciones

|Elemento de directiva y ubicación|Configuración predeterminada (si no está configurada)|Parámetro de PowerShell `Set-MpPreference` o propiedad WMI para la `MSFT_MpPreference` clase|
|---|---|---|
|examen de Email <p> **Escanear** \> **Activar el examen de correo electrónico**<p>Consulte [Email limitaciones de examen](#email-scanning-limitations) (en este artículo)|Deshabilitada|`-DisableEmailScanning`|
| Examen de scripts | Habilitado  | Esta configuración de directiva le permite configurar el examen de scripts. Si habilita o no establece esta configuración, se habilitará el examen de scripts. <p>Consulte [Defender/AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender)  | 
|Examen [de puntos de reanálisis](/windows/win32/fileio/reparse-points) <p> **Escanear** \> **Activar el examen del punto de reanálisis**|Deshabilitada|No disponible <p>Consulte [Puntos de reanálisis](/windows/win32/fileio/reparse-points)|
|Examen de las unidades de red asignadas <p> **Escanear** \> **Ejecución del examen completo en unidades de red asignadas**|Deshabilitada|`-DisableScanningMappedNetworkDrivesForFullScan`|
|Examinar archivos de archivo (como archivos .zip o .rar). <p> **Escanear** \> **Examen de archivos de archivo**|Habilitado|`-DisableArchiveScanning` <p>La [lista de exclusiones de extensiones](configure-extension-file-exclusions-microsoft-defender-antivirus.md) tendrá prioridad sobre esta configuración.|
|Examen de archivos en la red <p> **Escanear** \> **Examen de archivos de red**|Deshabilitada|`-DisableScanningNetworkFiles`|
|Examen de archivos ejecutables empaquetados <p> **Escanear** \> **Examen de archivos ejecutables empaquetados**|Habilitado|No disponible|
|Examen de unidades extraíbles solo durante exámenes completos <p> **Escanear** \> **Examen de unidades extraíbles**|Deshabilitada|`-DisableRemovableDriveScanning`|
|Especificar el nivel de subcarpetas dentro de una carpeta de archivo que se va a examinar <p>**Escanear** \> **Especificar la profundidad máxima para examinar archivos de archivo**|0|No disponible|
|Especifique la carga máxima de CPU (como porcentaje) durante un examen. <p> **Escanear** \> **Especificar el porcentaje máximo de uso de CPU durante un examen**|50|`-ScanAvgCPULoadFactor` <p>**NOTA**: La carga máxima de CPU no es un límite duro, pero es una guía para que el motor de análisis no supere el máximo en promedio. Los exámenes de ejecución manual omitirán esta configuración y se ejecutarán sin ningún límite de CPU.|
|Especifique el tamaño máximo (en kilobytes) de los archivos de archivo que se deben examinar. <p> **Escanear** \> **Especificar el tamaño máximo de los archivos de archivo que se van a examinar**|Sin límite|No disponible <p>El valor predeterminado de 0 no aplica ningún límite|
|Configuración de prioridad de CPU baja para exámenes programados <p> **Escanear** \> **Configuración de prioridad de CPU baja para exámenes programados**|Deshabilitada|No disponible|

> [!NOTE]
> Si la protección en tiempo real está activada, los archivos se examinan antes de que se acceda a ellos y se ejecuten. El ámbito de examen incluye todos los archivos, incluidos los archivos en medios extraíbles montados, como unidades USB. Si el dispositivo que realiza el examen tiene activada la protección en tiempo real o la protección de acceso, el examen también incluirá recursos compartidos de red.

## <a name="use-powershell-to-configure-scanning-options"></a>Uso de PowerShell para configurar opciones de examen

Para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus, consulte

- [Administración de Microsoft Defender Antivirus con cmdlets de PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [cmdlets Microsoft Defender Antivirus](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>Uso de WMI para configurar opciones de examen

Consulte [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="email-scanning-limitations"></a>limitaciones de examen de Email

Email examen permite examinar los archivos de correo electrónico utilizados por Outlook y otros clientes de correo durante los exámenes a petición y programados. Los objetos incrustados dentro del correo electrónico (como los datos adjuntos y los archivos archivados) también se examinan. Los siguientes tipos de formato de archivo se pueden examinar y corregir:

- Dbx
- Mbx
- MIME

Los archivos PST utilizados por Outlook 2003 o versiones anteriores (donde el tipo de archivo está establecido en no Unicode) también se examinan, pero Microsoft Defender Antivirus no puede corregir las amenazas que se detectan dentro de los archivos PST.

Si Microsoft Defender Antivirus detecta una amenaza dentro de un mensaje de correo electrónico, le mostrará la siguiente información para ayudarle a identificar el correo electrónico en peligro, de modo que pueda corregir la amenaza manualmente:

- Asunto del correo electrónico
- Nombre de datos adjuntos

## <a name="scanning-mapped-network-drives"></a>Examen de unidades de red asignadas

En cualquier sistema operativo, solo se examinan las unidades de red asignadas en el nivel del sistema. Las unidades de red asignadas a nivel de usuario no se examinan. Las unidades de red asignadas a nivel de usuario son aquellas que un usuario asigna en su sesión manualmente y con sus propias credenciales.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [Personalización, inicio y revisión de los resultados de los exámenes y correcciones de Microsoft Defender Antivirus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Configurar y ejecutar análisis bajo petición en el Antivirus de Microsoft Defender](run-scan-microsoft-defender-antivirus.md)
- [Configuración de exámenes programados Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
