---
title: Investigar eventos de conexión que ocurren tras los servidores proxy de reenvío
description: Obtenga información sobre cómo usar la supervisión avanzada del nivel HTTP a través de la protección de red en Microsoft Defender para endpoint, que muestra un destino real, en lugar de un proxy.
keywords: proxy, protección de red, proxy de reenvío, eventos de red, auditoría, bloqueo, nombres de dominio, dominio
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 55c001781ff016d7a23dc5db286d454b39fac5de
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841059"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a><span data-ttu-id="91318-104">Investigar eventos de conexión que ocurren tras los servidores proxy de reenvío</span><span class="sxs-lookup"><span data-stu-id="91318-104">Investigate connection events that occur behind forward proxies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="91318-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="91318-105">**Applies to:**</span></span>
- [<span data-ttu-id="91318-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="91318-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="91318-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91318-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="91318-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="91318-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="91318-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="91318-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="91318-110">Defender for Endpoint admite la supervisión de conexiones de red desde diferentes niveles de la pila de red.</span><span class="sxs-lookup"><span data-stu-id="91318-110">Defender for Endpoint supports network connection monitoring from different levels of the network stack.</span></span> <span data-ttu-id="91318-111">Un caso difícil es cuando la red usa un proxy de reenvío como puerta de enlace a Internet.</span><span class="sxs-lookup"><span data-stu-id="91318-111">A challenging case is when the network uses a forward proxy as a gateway to the Internet.</span></span>

<span data-ttu-id="91318-112">El proxy actúa como si fuera el extremo de destino.</span><span class="sxs-lookup"><span data-stu-id="91318-112">The proxy acts as if it was the target endpoint.</span></span>  <span data-ttu-id="91318-113">En estos casos, los monitores de conexión de red simples auditarán las conexiones con el proxy, que es correcto pero que tiene un valor de investigación inferior.</span><span class="sxs-lookup"><span data-stu-id="91318-113">In these cases, simple network connection monitors will audit the connections with the proxy which is correct but has lower investigation value.</span></span> 

<span data-ttu-id="91318-114">Defender for Endpoint admite la supervisión avanzada del nivel HTTP a través de la protección de red.</span><span class="sxs-lookup"><span data-stu-id="91318-114">Defender for Endpoint supports advanced HTTP level monitoring through network protection.</span></span> <span data-ttu-id="91318-115">Cuando está activado, se muestra un nuevo tipo de evento que expone los nombres de dominio de destino reales.</span><span class="sxs-lookup"><span data-stu-id="91318-115">When turned on, a new type of event is surfaced which exposes the real target domain names.</span></span>

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a><span data-ttu-id="91318-116">Usar la protección de red para supervisar la conexión de red detrás de un firewall</span><span class="sxs-lookup"><span data-stu-id="91318-116">Use network protection to monitor network connection behind a firewall</span></span>
<span data-ttu-id="91318-117">La supervisión de la conexión de red detrás de un proxy de reenvío es posible debido a eventos de red adicionales que se originan a partir de la protección de red.</span><span class="sxs-lookup"><span data-stu-id="91318-117">Monitoring network connection behind a forward proxy is possible due to additional network events that originate from network protection.</span></span> <span data-ttu-id="91318-118">Para verlos en una escala de tiempo del dispositivo, activa la protección de red (como mínimo en modo auditoría).</span><span class="sxs-lookup"><span data-stu-id="91318-118">To see them on a device timeline, turn network protection on (at the minimum in audit mode).</span></span> 

<span data-ttu-id="91318-119">La protección de red se puede controlar con los siguientes modos:</span><span class="sxs-lookup"><span data-stu-id="91318-119">Network protection can be controlled using the following modes:</span></span>

- <span data-ttu-id="91318-120">**Bloquear**</span><span class="sxs-lookup"><span data-stu-id="91318-120">**Block**</span></span> <br> <span data-ttu-id="91318-121">Los usuarios o aplicaciones no se conectarán a dominios peligrosos.</span><span class="sxs-lookup"><span data-stu-id="91318-121">Users or apps will be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="91318-122">Podrás ver esta actividad en Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="91318-122">You will be able to see this activity in Microsoft Defender Security Center.</span></span>
- <span data-ttu-id="91318-123">**Auditoría**</span><span class="sxs-lookup"><span data-stu-id="91318-123">**Audit**</span></span> <br> <span data-ttu-id="91318-124">Los usuarios o aplicaciones no se bloquearán para que no se conecten a dominios peligrosos.</span><span class="sxs-lookup"><span data-stu-id="91318-124">Users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="91318-125">Sin embargo, seguirás teniendo esta actividad en Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="91318-125">However, you will still see this activity in Microsoft Defender Security Center.</span></span>


<span data-ttu-id="91318-126">Si desactivas la protección de red, no se bloqueará la conexión de usuarios o aplicaciones a dominios peligrosos.</span><span class="sxs-lookup"><span data-stu-id="91318-126">If you turn network protection off, users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="91318-127">No verá ninguna actividad de red en Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="91318-127">You will not see any network activity in Microsoft Defender Security Center.</span></span>

<span data-ttu-id="91318-128">Si no lo configura, el bloqueo de red se desactivará de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="91318-128">If you do not configure it, network blocking will be turned off by default.</span></span>

<span data-ttu-id="91318-129">Para obtener más información, vea [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="91318-129">For more information, see [Enable network protection](enable-network-protection.md).</span></span>

## <a name="investigation-impact"></a><span data-ttu-id="91318-130">Impacto de la investigación</span><span class="sxs-lookup"><span data-stu-id="91318-130">Investigation impact</span></span>
<span data-ttu-id="91318-131">Cuando la protección de red esté activada, verás que en la escala de tiempo de un dispositivo la dirección IP seguirá representando el proxy, mientras que la dirección de destino real aparece.</span><span class="sxs-lookup"><span data-stu-id="91318-131">When network protection is turned on, you'll see that on a device's timeline the IP address will keep representing the proxy, while the real target address shows up.</span></span>

![Imagen de eventos de red en la escala de tiempo del dispositivo](images/atp-proxy-investigation.png)

<span data-ttu-id="91318-133">Los eventos adicionales desencadenados por la capa de protección de red ahora están disponibles para superficier los nombres de dominio reales incluso detrás de un proxy.</span><span class="sxs-lookup"><span data-stu-id="91318-133">Additional events triggered by the network protection layer are now available to surface the real domain names even behind a proxy.</span></span>

<span data-ttu-id="91318-134">Información del evento:</span><span class="sxs-lookup"><span data-stu-id="91318-134">Event's information:</span></span>

![Imagen de un solo evento de red](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a><span data-ttu-id="91318-136">Buscar eventos de conexión mediante la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="91318-136">Hunt for connection events using advanced hunting</span></span> 
<span data-ttu-id="91318-137">Todos los nuevos eventos de conexión están disponibles para que también se desatrase de la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="91318-137">All new connection events are available for you to hunt on through advanced hunting as well.</span></span> <span data-ttu-id="91318-138">Dado que estos eventos son eventos de conexión, puede encontrarlos en la tabla DeviceNetworkEvents en el tipo `ConnecionSuccess` de acción.</span><span class="sxs-lookup"><span data-stu-id="91318-138">Since these events are connection events, you can find them under the DeviceNetworkEvents table under the `ConnecionSuccess` action type.</span></span>

<span data-ttu-id="91318-139">Con esta consulta sencilla se mostrarán todos los eventos relevantes:</span><span class="sxs-lookup"><span data-stu-id="91318-139">Using this simple query will show you all the relevant events:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![Imagen de consulta de búsqueda avanzada](images/atp-proxy-investigation-ah.png)

<span data-ttu-id="91318-141">También puede filtrar los eventos relacionados con la conexión con el propio proxy.</span><span class="sxs-lookup"><span data-stu-id="91318-141">You can also filter out  events that are related to connection to the proxy itself.</span></span> 

<span data-ttu-id="91318-142">Use la siguiente consulta para filtrar las conexiones al proxy:</span><span class="sxs-lookup"><span data-stu-id="91318-142">Use the following query to filter out the connections to the proxy:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a><span data-ttu-id="91318-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="91318-143">Related topics</span></span>
- [<span data-ttu-id="91318-144">Aplicación de protección de red con GP: CSP de directiva</span><span class="sxs-lookup"><span data-stu-id="91318-144">Applying network protection with GP - policy CSP</span></span>](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
