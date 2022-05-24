---
title: Informes de firewalls de host en Microsoft Defender para punto de conexión
description: Hospedar y ver informes de firewall en Microsoft 365 Defender portal.
keywords: windows defender, firewall
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: 33eff726609db3d7f2d07f4a5bcf4955536c086c
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "65647291"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>Informes de firewalls de host en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Si es administrador global o de seguridad, ahora puede hospedar informes de firewall en el [portal de Microsoft 365 Defender](https://security.microsoft.com). Esta característica le permite ver los informes de firewall de Windows 10, Windows 11, Windows Server 2019 y Windows Server 2022 desde una ubicación centralizada.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe ejecutar Windows 10 o Windows 11, o Windows Server 2019 o Windows Server 2022.
- Para incorporar dispositivos al servicio Microsoft Defender para punto de conexión, consulte [aquí](onboard-configure.md).
- Para <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">que Microsoft 365 Defender portal</a> empiece a recibir los datos, debe habilitar Eventos de **auditoría** para Firewall de Windows Defender con Advanced Security:
  - [Eliminación de paquetes de la plataforma de filtrado de auditoría](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
  - [Conexión de la plataforma de filtrado de auditoría](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)
- Habilite estos eventos mediante directiva de grupo Editor de objetos, Directiva de seguridad local o los comandos de auditpol.exe. Para obtener más información, consulte [aquí](/windows/win32/fwp/auditing-and-logging).
  - Los dos comandos de PowerShell son:
    - **auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**
    - **auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**
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

- Después de habilitar los eventos, Microsoft 365 Defender comenzará a supervisar los datos.
  - Ip remota, puerto remoto, puerto local, dirección IP local, nombre del equipo, proceso entre conexiones entrantes y salientes.
- Los administradores ahora pueden ver Windows actividad del firewall de host [aquí](https://security.microsoft.com/firewall).
  - Para facilitar la creación de informes adicionales, descargue el [script de informes personalizados](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) para supervisar las actividades de Firewall de Windows Defender mediante Power BI.
  - Los datos pueden tardar hasta 12 horas en reflejarse.

## <a name="supported-scenarios"></a>Escenarios admitidos

Los siguientes escenarios se admiten durante la versión preliminar de Ring0.

### <a name="firewall-reporting"></a>Informes de firewall

Este es un par de ejemplos de las páginas de informe de firewall. Aquí encontrará un resumen de la actividad entrante, saliente y de aplicación. Para acceder directamente a esta página, vaya a <https://security.microsoft.com/firewall>.

:::image type="content" source="images/host-firewall-reporting-page.png" alt-text="Página Informes de firewall de host" lightbox="\images\host-firewall-reporting-page.png":::

También se puede acceder a estos informes si va a **InformesSeguridad** >  **ReportDevices** >  (sección) que se encuentra en la parte inferior de la tarjeta **Firewall Blocked Inbound Connections (Conexiones entrantes bloqueadas del firewall**).

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

Para informes adicionales o cambios personalizados, la consulta se puede exportar a Power BI para su posterior análisis. Los informes personalizados se pueden facilitar descargando el [script de informes personalizados](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) para supervisar las actividades de Firewall de Windows Defender mediante Power BI.
