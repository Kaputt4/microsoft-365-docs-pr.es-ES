---
title: Investigar una dirección IP asociada a una alerta
description: Use las opciones de investigación para examinar posibles comunicaciones entre dispositivos y direcciones IP externas.
keywords: investigar, investigar, investigar, dirección IP, alerta, atp de Microsoft Defender, IP externa
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 003abd854e34bb5a9a05f675313ba6c4f6ce1d71
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186046"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="670c7-104">Investigar una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="670c7-104">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="670c7-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="670c7-105">**Applies to:**</span></span>
- [<span data-ttu-id="670c7-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="670c7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="670c7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="670c7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="670c7-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="670c7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="670c7-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="670c7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="670c7-110">Examine la posible comunicación entre los dispositivos y las direcciones de protocolo de Internet externo (IP).</span><span class="sxs-lookup"><span data-stu-id="670c7-110">Examine possible communication between your devices and external internet protocol (IP) addresses.</span></span>

<span data-ttu-id="670c7-111">La identificación de todos los dispositivos de la organización que se comunicaron con una dirección IP malintencionada sospechosa o conocida, como los servidores de comando y control (C2), ayuda a determinar el alcance potencial de la infracción, los archivos asociados y los dispositivos infectados.</span><span class="sxs-lookup"><span data-stu-id="670c7-111">Identifying all devices in the organization that communicated with a suspected or known malicious IP address, such as Command and Control (C2) servers, helps determine the potential scope of breach, associated files, and infected devices.</span></span>

<span data-ttu-id="670c7-112">Puede encontrar información en las siguientes secciones de la vista Dirección IP:</span><span class="sxs-lookup"><span data-stu-id="670c7-112">You can find information from the following sections in the IP address view:</span></span>

- <span data-ttu-id="670c7-113">IP en todo el mundo</span><span class="sxs-lookup"><span data-stu-id="670c7-113">IP worldwide</span></span>
- <span data-ttu-id="670c7-114">Nombres DNS inversos</span><span class="sxs-lookup"><span data-stu-id="670c7-114">Reverse DNS names</span></span>
- <span data-ttu-id="670c7-115">Alertas relacionadas con esta IP</span><span class="sxs-lookup"><span data-stu-id="670c7-115">Alerts related to this IP</span></span>
- <span data-ttu-id="670c7-116">IP en la organización</span><span class="sxs-lookup"><span data-stu-id="670c7-116">IP in organization</span></span>
- <span data-ttu-id="670c7-117">Prevalencia</span><span class="sxs-lookup"><span data-stu-id="670c7-117">Prevalence</span></span>

## <a name="ip-worldwide-and-reverse-dns-names"></a><span data-ttu-id="670c7-118">Nombres DNS de IP en todo el mundo y inversos</span><span class="sxs-lookup"><span data-stu-id="670c7-118">IP Worldwide and Reverse DNS names</span></span>

<span data-ttu-id="670c7-119">La sección detalles de la dirección IP muestra los atributos de la dirección IP, como su ASN y sus nombres DNS inversos.</span><span class="sxs-lookup"><span data-stu-id="670c7-119">The IP address details section shows attributes of the IP address such as its ASN and its Reverse DNS names.</span></span>

## <a name="alerts-related-to-this-ip"></a><span data-ttu-id="670c7-120">Alertas relacionadas con esta IP</span><span class="sxs-lookup"><span data-stu-id="670c7-120">Alerts related to this IP</span></span>

<span data-ttu-id="670c7-121">La **sección Alertas relacionadas con esta IP** proporciona una lista de alertas asociadas con la IP.</span><span class="sxs-lookup"><span data-stu-id="670c7-121">The **Alerts related to this IP** section provides a list of alerts that are associated with the IP.</span></span>

## <a name="ip-in-organization"></a><span data-ttu-id="670c7-122">IP en la organización</span><span class="sxs-lookup"><span data-stu-id="670c7-122">IP in organization</span></span>

<span data-ttu-id="670c7-123">La **sección IP en la** organización proporciona detalles sobre la prevalencia de la dirección IP en la organización.</span><span class="sxs-lookup"><span data-stu-id="670c7-123">The **IP in organization** section provides details on the prevalence of the IP address in the organization.</span></span>

## <a name="prevalence"></a><span data-ttu-id="670c7-124">Prevalencia</span><span class="sxs-lookup"><span data-stu-id="670c7-124">Prevalence</span></span>

<span data-ttu-id="670c7-125">La **sección Prevalencia** muestra cuántos dispositivos se han conectado a esta dirección IP y cuándo se ha visto por primera y última vez.</span><span class="sxs-lookup"><span data-stu-id="670c7-125">The **Prevalence** section displays how many devices have connected to this IP address, and when the IP was first and last seen.</span></span> <span data-ttu-id="670c7-126">Puede filtrar los resultados de esta sección por período de tiempo; el período predeterminado es de 30 días.</span><span class="sxs-lookup"><span data-stu-id="670c7-126">You can filter the results of this section by time period; the default period is 30 days.</span></span>

## <a name="most-recent-observed-devices-with-ip"></a><span data-ttu-id="670c7-127">Dispositivos observados más recientes con IP</span><span class="sxs-lookup"><span data-stu-id="670c7-127">Most recent observed devices with IP</span></span>

<span data-ttu-id="670c7-128">La **sección Dispositivos observados** más recientes con IP proporciona una vista cronológica de los eventos y alertas asociadas que se observaron en la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="670c7-128">The **Most recent observed devices** with IP section provides a chronological view on the events and associated alerts that were observed on the IP address.</span></span>

<span data-ttu-id="670c7-129">**Investigar una IP externa:**</span><span class="sxs-lookup"><span data-stu-id="670c7-129">**Investigate an external IP:**</span></span>

1. <span data-ttu-id="670c7-130">Seleccione **IP** en el **menú** desplegable de la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="670c7-130">Select **IP** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="670c7-131">Escriba la dirección IP en el **campo** Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="670c7-131">Enter the IP address in the **Search** field.</span></span>
3. <span data-ttu-id="670c7-132">Haga clic en el icono de búsqueda o presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="670c7-132">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="670c7-133">Se muestran detalles sobre la dirección IP, incluidos: detalles de registro (si están disponibles), direcciones IP inversas (por ejemplo, dominios), prevalencia de dispositivos de la organización que se comunicaron con esta dirección IP (durante el período de tiempo seleccionable) y los dispositivos de la organización que se observaron comunicándose con esta dirección IP.</span><span class="sxs-lookup"><span data-stu-id="670c7-133">Details about the IP address are displayed, including: registration details (if available), reverse IPs (for example, domains), prevalence of devices in the organization that communicated with this IP Address (during selectable time period), and the devices in the organization that were observed communicating with this IP address.</span></span>

> [!NOTE]
> <span data-ttu-id="670c7-134">Los resultados de la búsqueda solo se devolverán para las direcciones IP observadas en la comunicación con dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="670c7-134">Search results will only be returned for IP addresses observed in communication with devices in the organization.</span></span>

<span data-ttu-id="670c7-135">Use los filtros de búsqueda para definir los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="670c7-135">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="670c7-136">También puede usar el cuadro de búsqueda de escala de tiempo para filtrar los resultados mostrados de todos los dispositivos de la organización observados que se comunican con la dirección IP, el archivo asociado a la comunicación y la última fecha observada.</span><span class="sxs-lookup"><span data-stu-id="670c7-136">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the IP address, the file associated with the communication and the last date observed.</span></span>

<span data-ttu-id="670c7-137">Hacer clic en cualquiera de los nombres de dispositivo te llevará a la vista de ese dispositivo, donde puedes seguir investigando alertas, comportamientos y eventos notificados.</span><span class="sxs-lookup"><span data-stu-id="670c7-137">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="670c7-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="670c7-138">Related topics</span></span>

- [<span data-ttu-id="670c7-139">Ver y organizar la cola de Alertas de punto de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="670c7-139">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="670c7-140">Administrar alertas de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="670c7-140">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="670c7-141">Investigar alertas de punto de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="670c7-141">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="670c7-142">Investigar un archivo asociado a una alerta de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="670c7-142">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="670c7-143">Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="670c7-143">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="670c7-144">Investigar un dominio asociado a una alerta de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="670c7-144">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="670c7-145">Investigar una cuenta de usuario en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="670c7-145">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
