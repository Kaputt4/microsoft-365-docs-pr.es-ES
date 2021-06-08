---
title: Informes de firewall de host en Microsoft Defender para endpoint
description: Host and view firewall reporting in Microsoft 365 security center.
keywords: Windows Defender, firewall
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809343"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="77b84-104">Informes de firewall de host en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="77b84-104">Host firewall reporting in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="77b84-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="77b84-105">**Applies to:**</span></span>
- [<span data-ttu-id="77b84-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="77b84-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="77b84-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77b84-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="77b84-108">Si es administrador, ahora puede hospedar informes de firewall en Microsoft 365 [de seguridad](https://security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="77b84-108">If you are an admin, you can now host firewall reporting to [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="77b84-109">Esta característica le permite ver Windows 10 y Windows firewall de Server 2019 desde una ubicación centralizada.</span><span class="sxs-lookup"><span data-stu-id="77b84-109">This feature enables you to view Windows 10 and Windows Server 2019 firewall reporting from a centralized location.</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="77b84-110">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="77b84-110">What do you need to know before you begin?</span></span> 

- <span data-ttu-id="77b84-111">Debe ejecutar Windows 10 o Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="77b84-111">You must be running Windows 10 or Windows Server 2019.</span></span>
- <span data-ttu-id="77b84-112">Para incorporar dispositivos al servicio Microsoft Defender para endpoints, vea [aquí](onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="77b84-112">To onboard devices to the Microsoft Defender for Endpoint service, see [here](onboard-configure.md).</span></span> 
- <span data-ttu-id="77b84-113">Para que Microsoft 365 centro de seguridad comience a recibir los datos, debe habilitar **eventos** de auditoría para Firewall de Windows Defender con seguridad avanzada:</span><span class="sxs-lookup"><span data-stu-id="77b84-113">For Microsoft 365 security center to start receiving the data, you must enable **Audit Events** for Windows Defender Firewall with Advanced Security:</span></span> 
    - [<span data-ttu-id="77b84-114">Gota de paquetes de la plataforma de filtrado de auditoría</span><span class="sxs-lookup"><span data-stu-id="77b84-114">Audit Filtering Platform Packet Drop</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [<span data-ttu-id="77b84-115">Conexión de la plataforma de filtrado de auditoría</span><span class="sxs-lookup"><span data-stu-id="77b84-115">Audit Filtering Platform Connection</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- <span data-ttu-id="77b84-116">Habilite estos eventos mediante el Editor de objetos de directiva de grupo, la directiva de seguridad local o auditpol.exe comandos.</span><span class="sxs-lookup"><span data-stu-id="77b84-116">Enable these events by using Group Policy Object Editor, Local Security Policy, or the auditpol.exe commands.</span></span> <span data-ttu-id="77b84-117">Para obtener más información, [vea aquí](/windows/win32/fwp/auditing-and-logging).</span><span class="sxs-lookup"><span data-stu-id="77b84-117">For more information, see [here](/windows/win32/fwp/auditing-and-logging).</span></span> 
    - <span data-ttu-id="77b84-118">Los dos comandos de PowerShell son:</span><span class="sxs-lookup"><span data-stu-id="77b84-118">The two PowerShell commands are:</span></span>
        - <span data-ttu-id="77b84-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="77b84-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span></span> 
        - <span data-ttu-id="77b84-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="77b84-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span></span> 

## <a name="the-process"></a><span data-ttu-id="77b84-121">El proceso</span><span class="sxs-lookup"><span data-stu-id="77b84-121">The process</span></span>
> [!NOTE]
> <span data-ttu-id="77b84-122">Asegúrate de seguir las instrucciones de la sección anterior y de configurar correctamente los dispositivos para la participación en la vista previa anticipada.</span><span class="sxs-lookup"><span data-stu-id="77b84-122">Make sure to follow the instructions from the section above and properly configure your devices for the early preview participation.</span></span>

- <span data-ttu-id="77b84-123">Después de habilitar los eventos, Microsoft 365 de seguridad empezará a supervisar los datos.</span><span class="sxs-lookup"><span data-stu-id="77b84-123">After enabling the events, Microsoft 365 security center will start to monitor the data.</span></span>
    - <span data-ttu-id="77b84-124">IP remota, puerto remoto, puerto local, IP local, nombre del equipo, proceso entre conexiones entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="77b84-124">Remote IP, Remote Port, Local Port, Local IP, Computer Name, Process across inbound and outbound connections.</span></span>
- <span data-ttu-id="77b84-125">Los administradores ahora pueden ver Windows de firewall de host [aquí](https://security.microsoft.com/firewall).</span><span class="sxs-lookup"><span data-stu-id="77b84-125">Admins can now see Windows host firewall activity [here](https://security.microsoft.com/firewall).</span></span>
    - <span data-ttu-id="77b84-126">Para facilitar la creación de informes adicionales, descargue el [script de](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) informes personalizados para supervisar las actividades Firewall de Windows Defender mediante Power BI.</span><span class="sxs-lookup"><span data-stu-id="77b84-126">Additional reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 
    - <span data-ttu-id="77b84-127">Puede tardar hasta 12 horas antes de que se reflejen los datos.</span><span class="sxs-lookup"><span data-stu-id="77b84-127">It can take up to 12 hours before the data is reflected.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="77b84-128">Escenarios admitidos</span><span class="sxs-lookup"><span data-stu-id="77b84-128">Supported scenarios</span></span>
<span data-ttu-id="77b84-129">Los siguientes escenarios se admiten durante Ring0 Preview.</span><span class="sxs-lookup"><span data-stu-id="77b84-129">The following scenarios are supported during Ring0 Preview.</span></span> 

### <a name="firewall-reporting-in-security-center"></a><span data-ttu-id="77b84-130">Informes de firewall en el centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="77b84-130">Firewall reporting in security center</span></span>

<span data-ttu-id="77b84-131">Este es un par de ejemplos de las páginas de informe de firewall.</span><span class="sxs-lookup"><span data-stu-id="77b84-131">Here is a couple of examples of the firewall report pages.</span></span> <span data-ttu-id="77b84-132">Aquí encontrará un resumen de la actividad de entrada, salida y aplicación.</span><span class="sxs-lookup"><span data-stu-id="77b84-132">Here you will find a summary of inbound, outbound, and application activity.</span></span> <span data-ttu-id="77b84-133">Puede acceder a esta página directamente yendo a https://security.microsoft.com/firewall .</span><span class="sxs-lookup"><span data-stu-id="77b84-133">You can access this page directly by going to https://security.microsoft.com/firewall.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77b84-134">![Página de informes de firewall de host](\images\host-firewall-reporting-page.png)</span><span class="sxs-lookup"><span data-stu-id="77b84-134">![Host firewall reporting page](\images\host-firewall-reporting-page.png)</span></span>

<span data-ttu-id="77b84-135">También se puede obtener acceso a estos informes yendo a **Informes** de dispositivos de informes de seguridad (sección) ubicados en la parte inferior de la tarjeta Conexiones entrantes  >    >   **bloqueadas del firewall.**</span><span class="sxs-lookup"><span data-stu-id="77b84-135">These reports can also be accessed by going to **Reports** > **Security Report** > **Devices** (section) located at the bottom of the **Firewall Blocked Inbound Connections** card.</span></span>

### <a name="from-computers-with-a-blocked-connection-to-device"></a><span data-ttu-id="77b84-136">De "Equipos con una conexión bloqueada" al dispositivo</span><span class="sxs-lookup"><span data-stu-id="77b84-136">From "Computers with a blocked connection" to device</span></span>

<span data-ttu-id="77b84-137">Las tarjetas admiten objetos interactivos.</span><span class="sxs-lookup"><span data-stu-id="77b84-137">Cards support interactive objects.</span></span> <span data-ttu-id="77b84-138">Puedes profundizar en la actividad de un dispositivo haciendo clic en el nombre del dispositivo, que se iniciará en una nueva pestaña, y te llevará directamente a la pestaña Escala https://securitycenter.microsoft.com **de tiempo del** dispositivo.</span><span class="sxs-lookup"><span data-stu-id="77b84-138">You can drill into the activity of a device by clicking on the device name, which will launch https://securitycenter.microsoft.com in a new tab, and take you directly to the **Device Timeline** tab.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77b84-139">![Equipos con una conexión bloqueada](\images\firewall-reporting-blocked-connection.png)</span><span class="sxs-lookup"><span data-stu-id="77b84-139">![Computers with a blocked connection](\images\firewall-reporting-blocked-connection.png)</span></span>

<span data-ttu-id="77b84-140">Ahora puedes seleccionar la pestaña **Escala de** tiempo, que te dará una lista de eventos asociados con ese dispositivo.</span><span class="sxs-lookup"><span data-stu-id="77b84-140">You can now select the **Timeline** tab, which will give you a list of events associated with that device.</span></span> 

<span data-ttu-id="77b84-141">Después de hacer clic en el **botón** Filtros de la esquina superior derecha del panel de visualización, seleccione el tipo de evento que desee.</span><span class="sxs-lookup"><span data-stu-id="77b84-141">After clicking on the **Filters** button on the upper right-hand corner of the viewing pane, select the type of event you want.</span></span> <span data-ttu-id="77b84-142">En este caso, seleccione **Eventos de firewall y** el panel se filtrará a eventos de firewall.</span><span class="sxs-lookup"><span data-stu-id="77b84-142">In this case, select **Firewall events** and the pane will be filtered to Firewall events.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77b84-143">![Botón Filtros](\images\firewall-reporting-filters-button.png)</span><span class="sxs-lookup"><span data-stu-id="77b84-143">![Filters button](\images\firewall-reporting-filters-button.png)</span></span>

### <a name="drill-into-advanced-hunting-preview-refresh"></a><span data-ttu-id="77b84-144">Profundizar en la búsqueda avanzada (actualización de vista previa)</span><span class="sxs-lookup"><span data-stu-id="77b84-144">Drill into advanced hunting (preview refresh)</span></span>

<span data-ttu-id="77b84-145">Los informes de firewall admiten la perforación desde la tarjeta directamente en **búsqueda avanzada** haciendo clic en el **botón Abrir búsqueda** avanzada.</span><span class="sxs-lookup"><span data-stu-id="77b84-145">Firewall reports support drilling from the card directly into **Advanced Hunting** by clicking the **Open Advanced hunting** button.</span></span> <span data-ttu-id="77b84-146">La consulta se rellenará previamente.</span><span class="sxs-lookup"><span data-stu-id="77b84-146">The query will be pre-populated.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77b84-147">![Botón Abrir búsqueda avanzada](\images\firewall-reporting-advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="77b84-147">![Open Advanced hunting button](\images\firewall-reporting-advanced-hunting.png)</span></span>

<span data-ttu-id="77b84-148">Ahora se puede ejecutar la consulta y se pueden explorar todos los eventos de Firewall relacionados de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="77b84-148">The query can now be executed, and all related Firewall events from the last 30 days can be explored.</span></span> 

<span data-ttu-id="77b84-149">Para informes adicionales o cambios personalizados, la consulta se puede exportar a Power BI para un análisis posterior.</span><span class="sxs-lookup"><span data-stu-id="77b84-149">For additional reporting, or custom changes, the query can be exported into Power BI for further analysis.</span></span> <span data-ttu-id="77b84-150">Los informes personalizados se pueden facilitar descargando el [script de](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) informes personalizados para supervisar las actividades Firewall de Windows Defender mediante Power BI.</span><span class="sxs-lookup"><span data-stu-id="77b84-150">Custom reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 

 