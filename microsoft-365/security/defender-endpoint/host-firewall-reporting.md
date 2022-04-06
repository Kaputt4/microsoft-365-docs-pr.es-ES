---
title: Informes de firewalls de host en Microsoft Defender para punto de conexión
description: Hospedar y ver informes de firewall en Microsoft 365 Defender portal.
keywords: Windows Defender, firewall
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
ms.openlocfilehash: e5bbdd77226f8649f2a781866fef614706e8a789
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475287"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>Informes de firewalls de host en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Si es administrador, ahora puede hospedar informes de firewall en el [portal Microsoft 365 Defender cliente](https://security.microsoft.com). Esta característica permite ver Windows 10, Windows 11, Windows Server 2019 y firewall de Windows Server 2022 desde una ubicación centralizada.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe ejecutar Windows 10 o Windows 11 o Windows Server 2019 o Windows Server 2022.
- Para incorporar dispositivos al servicio de Microsoft Defender para endpoints, vea [aquí](onboard-configure.md).
- Para <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">que Microsoft 365 Defender portal</a> comience a recibir los datos, debe habilitar **eventos** de auditoría para Windows Defender firewall con seguridad avanzada:
  - [Gota de paquetes de la plataforma de filtrado de auditoría](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
  - [Conexión de la plataforma de filtrado de auditoría](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)
- Habilite estos eventos mediante el Editor de objetos de directiva de grupo, la directiva de seguridad local o auditpol.exe comandos. Para obtener más información, [vea aquí](/windows/win32/fwp/auditing-and-logging).
  - Los dos comandos de PowerShell son:
    - **auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**
    - **auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**

## <a name="the-process"></a>El proceso

> [!NOTE]
> Asegúrate de seguir las instrucciones de la sección anterior y de configurar correctamente los dispositivos para la participación en la vista previa anticipada.

- Después de habilitar los eventos, Microsoft 365 Defender comenzará a supervisar los datos.
  - IP remota, puerto remoto, puerto local, IP local, nombre del equipo, proceso entre conexiones entrantes y salientes.
- Los administradores ahora pueden ver Windows de firewall de host [aquí](https://security.microsoft.com/firewall).
  - Los informes adicionales se pueden facilitar descargando el [script de](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) informes personalizados para supervisar las actividades de firewall Windows Defender mediante Power BI.
  - Puede tardar hasta 12 horas antes de que se reflejen los datos.

## <a name="supported-scenarios"></a>Escenarios admitidos

Los siguientes escenarios se admiten durante Ring0 Preview.

### <a name="firewall-reporting"></a>Informes de firewall

Este es un par de ejemplos de las páginas de informe de firewall. Aquí encontrará un resumen de la actividad de entrada, salida y aplicación. Puede acceder a esta página directamente yendo a <https://security.microsoft.com/firewall>.

> [!div class="mx-imgBorder"]
> :::image type="content" source="\images\host-firewall-reporting-page.png" alt-text="La página De informes de firewall de host" lightbox="\images\host-firewall-reporting-page.png":::

También se puede acceder a estos informes yendo a **ReportsSecurity** >  **ReportDevices** >  (sección) ubicado en la parte inferior de la tarjeta **Firewall Blocked Inbound Connections**.

### <a name="from-computers-with-a-blocked-connection-to-device"></a>De "Equipos con una conexión bloqueada" al dispositivo

Las tarjetas admiten objetos interactivos. Puedes profundizar en la actividad de un dispositivo haciendo clic en el nombre del dispositivo, que iniciará el portal de Microsoft 365 Defender en una pestaña nueva y te llevará directamente a la pestaña Escala de tiempo **del** dispositivo.

> [!div class="mx-imgBorder"]
> :::image type="content" source="\images\firewall-reporting-blocked-connection.png" alt-text="La página Equipos con una conexión bloqueada" lightbox="\images\firewall-reporting-blocked-connection.png":::

Ahora puedes seleccionar la pestaña **Escala de** tiempo, que te dará una lista de eventos asociados con ese dispositivo.

Después de hacer clic en el **botón** Filtros de la esquina superior derecha del panel de visualización, seleccione el tipo de evento que desee. En este caso, seleccione **Eventos de firewall y** el panel se filtrará a eventos de firewall.

> [!div class="mx-imgBorder"]
> :::image type="content" source="\images\firewall-reporting-filters-button.png" alt-text="El botón Filtros" lightbox="\images\firewall-reporting-filters-button.png":::

### <a name="drill-into-advanced-hunting-preview-refresh"></a>Profundizar en la búsqueda avanzada (actualización de vista previa)

Los informes de firewall admiten la perforación desde la tarjeta directamente en **búsqueda avanzada** haciendo clic en el **botón Abrir búsqueda** avanzada. La consulta se rellenará previamente.

> [!div class="mx-imgBorder"]
> :::image type="content" source="\images\firewall-reporting-advanced-hunting.png" alt-text="Botón Abrir búsqueda avanzada" lightbox="\images\firewall-reporting-advanced-hunting.png":::

Ahora se puede ejecutar la consulta y se pueden explorar todos los eventos de Firewall relacionados de los últimos 30 días.

Para informes adicionales o cambios personalizados, la consulta se puede exportar a Power BI para un análisis posterior. Los informes personalizados se pueden facilitar descargando el [script de](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) informes personalizados para supervisar las actividades de firewall Windows Defender mediante Power BI.
