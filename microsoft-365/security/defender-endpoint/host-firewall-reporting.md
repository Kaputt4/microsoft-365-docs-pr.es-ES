---
title: Informes de firewalls de host en Microsoft Defender para punto de conexión
description: Hospedar y ver informes de firewall en Microsoft 365 Defender portal.
keywords: windows defender, firewall
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.subservice: mde
ms.collection: m365-security-compliance
ms.custom: admindeeplinkDEFENDER
search.appverid: met150
ms.openlocfilehash: d4a14519e296cedafe4179eaeb79320ec862fda4
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67702344"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>Informes de firewalls de host en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Si es administrador global o de seguridad, ahora puede hospedar informes de firewall en el [portal de Microsoft 365 Defender](https://security.microsoft.com). Esta característica le permite ver los informes de firewall de Windows desde una ubicación centralizada.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Debe ejecutar Windows 10 o posterior, Windows Server 2012 R2 o posterior.
     > [!NOTE]
     > Para que Windows2012 R2 y Windows Server 2016 aparezcan en los informes de firewall, estos dispositivos deben incorporarse mediante el paquete de solución unificada moderna. Para obtener más información, consulte [Nueva funcionalidad en la solución unificada moderna para Windows Server 2012 R2 y 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).
- Para incorporar dispositivos al servicio Microsoft Defender para punto de conexión, consulte [aquí](onboard-configure.md).
- Para <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">que Microsoft 365 Defender portal</a> empiece a recibir los datos, debe habilitar **Eventos de auditoría** para Windows Defender Firewall con seguridad avanzada:
  - [Eliminación de paquetes de la plataforma de filtrado de auditoría](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
  - [Conexión de la plataforma de filtrado de auditoría](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)
- Habilite estos eventos mediante directiva de grupo Editor de objetos, Directiva de seguridad local o los comandos de auditpol.exe. Para obtener más información, consulte [aquí](/windows/win32/fwp/auditing-and-logging).
  - Los dos comandos de PowerShell son:
    - `auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable`
    - `auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable`

```powershell
param (
    [switch]$remediate
)
try {

    $categories = "Filtering Platform Packet Drop,Filtering Platform Connection"
    $current = auditpol /get /subcategory:"$($categories)" /r | ConvertFrom-Csv    
    if ($current."Inclusion Setting" -ne "failure") {
        if ($remediate.IsPresent) {
            Write-Host "Remediating. No Auditing Enabled. $($current | ForEach-Object {$_.Subcategory + ":" + $_.'Inclusion Setting' + ";"})"
            $output = auditpol /set /subcategory:"$($categories)" /failure:enable
            if($output -eq "The command was successfully executed.") {
                Write-Host "$($output)"
                exit 0
            }
            else {
                Write-Host "$($output)"
                exit 1
            }
        }
        else {
            Write-Host "Remediation Needed. $($current | ForEach-Object {$_.Subcategory + ":" + $_.'Inclusion Setting' + ";"})."
            exit 1
        }
    }

}
catch {
    throw $_
} 
```

## <a name="the-process"></a>El proceso

> [!NOTE]
> Asegúrese de seguir las instrucciones de la sección anterior y de configurar correctamente los dispositivos para la participación en la versión preliminar temprana.

- Después de habilitar los eventos, Microsoft 365 Defender comenzará a supervisar los datos, lo que incluye: 
   - IP remota
   - Puerto remoto
   - Puerto local
   - Local IP
   - Nombre del equipo
   - Proceso entre conexiones entrantes y salientes
- Los administradores ahora pueden ver la actividad del firewall del host [de Windows aquí](https://security.microsoft.com/firewall).
   - Para facilitar la creación de informes adicionales, descargue el [script de informes personalizados](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) para supervisar las actividades de firewall de Windows Defender mediante Power BI.
   - Los datos pueden tardar hasta 12 horas en reflejarse.

## <a name="supported-scenarios"></a>Escenarios admitidos

- [Informes de firewall](#firewall-reporting)
- [Desde "Equipos con una conexión bloqueada" al dispositivo](#from-computers-with-a-blocked-connection-to-device)
- [Obtención de detalles de la búsqueda avanzada (actualización en versión preliminar)](#drill-into-advanced-hunting-preview-refresh)

### <a name="firewall-reporting"></a>Informes de firewall

Estos son algunos ejemplos de las páginas del informe de firewall. Aquí encontrará un resumen de la actividad entrante, saliente y de aplicación. Para acceder directamente a esta página, vaya a <https://security.microsoft.com/firewall>.

:::image type="content" source="images/host-firewall-reporting-page.png" alt-text="Página Informes de firewall de host" lightbox="\images\host-firewall-reporting-page.png":::

También se puede acceder a estos informes si va a **Los dispositivos** >  de **informes** >  de seguridad (sección) situados en la parte inferior de la tarjeta **Conexiones entrantes bloqueadas del firewall**.

### <a name="from-computers-with-a-blocked-connection-to-device"></a>Desde "Equipos con una conexión bloqueada" al dispositivo

Las tarjetas admiten objetos interactivos. Para profundizar en la actividad de un dispositivo, haga clic en el nombre del dispositivo, que iniciará el portal de Microsoft 365 Defender en una nueva pestaña y le llevará directamente a la pestaña Escala de **tiempo del dispositivo**.

:::image type="content" source="images/firewall-reporting-blocked-connection.png" alt-text="La página Equipos con una conexión bloqueada" lightbox="\images\firewall-reporting-blocked-connection.png":::

Ahora puede seleccionar la pestaña **Escala de tiempo** , que le proporcionará una lista de eventos asociados a ese dispositivo.

Después de hacer clic en el botón **Filtros** de la esquina superior derecha del panel de visualización, seleccione el tipo de evento que desee. En este caso, seleccione **Eventos de firewall** y el panel se filtrará por eventos de firewall.

:::image type="content" source="images/firewall-reporting-filters-button.png" alt-text="Botón Filtros" lightbox="\images\firewall-reporting-filters-button.png":::

### <a name="drill-into-advanced-hunting-preview-refresh"></a>Obtención de detalles de la búsqueda avanzada (actualización en versión preliminar)

Los informes de firewall admiten la exploración desde la tarjeta directamente en **Búsqueda avanzada** haciendo clic en el botón **Abrir búsqueda avanzada** . La consulta se rellenará previamente.

:::image type="content" source="images/firewall-reporting-advanced-hunting.png" alt-text="Botón Abrir búsqueda avanzada" lightbox="\images\firewall-reporting-advanced-hunting.png":::

Ahora se puede ejecutar la consulta y se pueden explorar todos los eventos de firewall relacionados de los últimos 30 días.

Para obtener más informes o cambios personalizados, la consulta se puede exportar a Power BI para su posterior análisis. Los informes personalizados se pueden facilitar descargando el [script de informes personalizados](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) para supervisar las actividades de firewall de Windows Defender mediante Power BI.
