---
title: Introducción a la detección de dispositivos
description: Obtenga información sobre cómo aprovechar la detección de puntos de conexión en Microsoft 365 Defender para buscar dispositivos no administrados en la red
keywords: detección de dispositivos, detección, pasiva, proactiva, red, visibilidad, servidor, estación de trabajo, incorporación, dispositivos no administrados
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2e58b6048f9d815d759cd78ceb3316eb2ed6f66d
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698482"
---
# <a name="device-discovery-overview"></a><span data-ttu-id="96c39-104">Introducción a la detección de dispositivos</span><span class="sxs-lookup"><span data-stu-id="96c39-104">Device discovery overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="96c39-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="96c39-105">**Applies to:**</span></span>
- [<span data-ttu-id="96c39-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="96c39-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="96c39-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96c39-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="96c39-108">Proteger el entorno requiere realizar un inventario de los dispositivos que están en la red.</span><span class="sxs-lookup"><span data-stu-id="96c39-108">Protecting your environment requires taking inventory of the devices that are in your network.</span></span> <span data-ttu-id="96c39-109">Sin embargo, la asignación de dispositivos en una red a menudo puede ser costosa, desafiante y consume mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="96c39-109">However, mapping devices in a network can often be expensive, challenging, and time-consuming.</span></span> 

<span data-ttu-id="96c39-110">Microsoft Defender para endpoint proporciona una funcionalidad de detección de dispositivos que te ayuda a encontrar dispositivos no administrados conectados a la red corporativa sin necesidad de dispositivos adicionales o cambios engorrosos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="96c39-110">Microsoft Defender for Endpoint provides a device discovery capability that helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span>


<span data-ttu-id="96c39-111">La funcionalidad de detección de dispositivos te permite:</span><span class="sxs-lookup"><span data-stu-id="96c39-111">The device discovery capability allows you to:</span></span>

- <span data-ttu-id="96c39-112">**Detectar puntos de conexión empresariales conectados a la red corporativa**</span><span class="sxs-lookup"><span data-stu-id="96c39-112">**Discover enterprise endpoints connected to your corporate network**</span></span> <br>
<span data-ttu-id="96c39-113">Con las opciones de detección básicas o estándar, puede detectar estaciones de trabajo, servidores y puntos de conexión móviles que aún no están incorporados a Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="96c39-113">Using either basic or standard discovery options, you can discover workstations, servers, and mobile endpoints that are not yet onboarded to Microsoft Defender for Endpoint.</span></span>  

- <span data-ttu-id="96c39-114">**Extremos detectados incorporados**</span><span class="sxs-lookup"><span data-stu-id="96c39-114">**Onboard discovered endpoints**</span></span><br>
<span data-ttu-id="96c39-115">Los puntos de conexión no administrados de la red introducen vulnerabilidades y riesgos en la red.</span><span class="sxs-lookup"><span data-stu-id="96c39-115">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="96c39-116">Incorporarlos al servicio puede aumentar la visibilidad de seguridad en ellos.</span><span class="sxs-lookup"><span data-stu-id="96c39-116">Onboarding them to the service can increase the security visibility on them.</span></span> 

<span data-ttu-id="96c39-117">Junto con esta funcionalidad, una nueva recomendación de seguridad para incorporar dispositivos a Microsoft Defender para endpoint estará disponible como parte de la experiencia existente de administración de amenazas y vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="96c39-117">In conjunction with this capability, a new security recommendation to onboard devices to Microsoft Defender for Endpoint will be available as part of the existing Threat and Vulnerability Management experience.</span></span>



## <a name="discovery-methods"></a><span data-ttu-id="96c39-118">Métodos de detección</span><span class="sxs-lookup"><span data-stu-id="96c39-118">Discovery methods</span></span>
<span data-ttu-id="96c39-119">Hay dos modos de detección:</span><span class="sxs-lookup"><span data-stu-id="96c39-119">There are two modes of discovery:</span></span> 

-   <span data-ttu-id="96c39-120">Detección básica</span><span class="sxs-lookup"><span data-stu-id="96c39-120">Basic discovery</span></span> 
-   <span data-ttu-id="96c39-121">Detección estándar (recomendado)</span><span class="sxs-lookup"><span data-stu-id="96c39-121">Standard discovery (recommended)</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="96c39-122">La detección se establece en modo básico.</span><span class="sxs-lookup"><span data-stu-id="96c39-122">Discovery is set to basic mode.</span></span> <span data-ttu-id="96c39-123">Puede elegir conservar esta configuración a través de la página de configuración.</span><span class="sxs-lookup"><span data-stu-id="96c39-123">You can choose to retain this configuration through the settings page.</span></span> <span data-ttu-id="96c39-124">La detección estándar será el modo predeterminado para todos los clientes de vista previa a partir del 10 de mayo de 2021, a menos que se modifique a través de la página de configuración antes de esta fecha.</span><span class="sxs-lookup"><span data-stu-id="96c39-124">Standard discovery will be the default mode for all preview customers starting May 10, 2021 - unless modified through the settings page before this date.</span></span>

### <a name="basic-discovery"></a><span data-ttu-id="96c39-125">Detección básica</span><span class="sxs-lookup"><span data-stu-id="96c39-125">Basic discovery</span></span> 

<span data-ttu-id="96c39-126">En este modo, los puntos de conexión recopilarán pasivamente eventos en la red y extraerán información del dispositivo de ellos.</span><span class="sxs-lookup"><span data-stu-id="96c39-126">In this mode, endpoints will passively collect events in your network and extract device information from them.</span></span> <span data-ttu-id="96c39-127">La detección básica usa el SenseNDR.exe binario para la recopilación de datos de red pasiva y no se iniciará tráfico de red.</span><span class="sxs-lookup"><span data-stu-id="96c39-127">Basic discovery uses the SenseNDR.exe binary for passive network data collection and no network traffic will be initiated.</span></span> <span data-ttu-id="96c39-128">Los puntos de conexión simplemente extraerán datos de cada tráfico de red que ve un dispositivo incorporado.</span><span class="sxs-lookup"><span data-stu-id="96c39-128">Endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> 

### <a name="standard-discovery"></a><span data-ttu-id="96c39-129">Detección estándar</span><span class="sxs-lookup"><span data-stu-id="96c39-129">Standard discovery</span></span> 

<span data-ttu-id="96c39-130">Este modo permite a los puntos de conexión sondear activamente los dispositivos observados en la red para enriquecer los datos recopilados, lo que le ayuda a crear un inventario de dispositivos confiable y coherente.</span><span class="sxs-lookup"><span data-stu-id="96c39-130">This mode allows endpoints to actively probe observed devices in the network to enrich collected data - helping you build a reliable and coherent device inventory.</span></span> <span data-ttu-id="96c39-131">El modo estándar usa sondeos inteligentes y activos para descubrir aún más información sobre los dispositivos observados para enriquecer la información del dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="96c39-131">Standard mode uses smart, active probing to discover even more information about observed devices to enrich existing device information.</span></span>  

<span data-ttu-id="96c39-132">Cuando el modo estándar está habilitado, las herramientas de supervisión de red de la organización pueden observar una actividad de red mínima y insignificante generada por el sensor de detección.</span><span class="sxs-lookup"><span data-stu-id="96c39-132">When Standard mode is enabled, minimal and negligible network activity generated by the discovery sensor might be observed by network monitoring tools in your organization.</span></span>  

 <span data-ttu-id="96c39-133">Si decide no habilitar este modo, solo obtendrá una visibilidad limitada de los puntos de conexión no administrados en la red.</span><span class="sxs-lookup"><span data-stu-id="96c39-133">If you choose not to enable this mode, you will only gain limited visibility of unmanaged endpoints in your network.</span></span>

<span data-ttu-id="96c39-134">La detección estándar usa varios scripts de PowerShell para sondear activamente los dispositivos de la red.</span><span class="sxs-lookup"><span data-stu-id="96c39-134">Standard discovery uses various PowerShell scripts to actively probe devices in the network.</span></span> <span data-ttu-id="96c39-135">Esos scripts de PowerShell están firmados por Microsoft y se ejecutan desde la siguiente ubicación: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` .</span><span class="sxs-lookup"><span data-stu-id="96c39-135">Those PowerShell scripts are Microsoft signed and are executed from the following location: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`.</span></span> <span data-ttu-id="96c39-136">Por ejemplo, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span><span class="sxs-lookup"><span data-stu-id="96c39-136">For example, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span></span>

<span data-ttu-id="96c39-137">Puedes cambiar y personalizar la configuración de detección, para obtener más información, consulta [Configurar la detección de dispositivos.](configure-device-discovery.md)</span><span class="sxs-lookup"><span data-stu-id="96c39-137">You can change and customize your discovery settings, for more information see [Configure device discovery](configure-device-discovery.md).</span></span>

> [!NOTE]
> <span data-ttu-id="96c39-138">El motor de detección distingue entre los eventos de red que se reciben en la red corporativa frente a fuera de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="96c39-138">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="96c39-139">Los dispositivos que no están conectados a redes corporativas no se detectarán ni se mostrarán en el inventario de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="96c39-139">Devices that are not connected to corporate networks will not be discovered or listed in the device inventory.</span></span> 



## <a name="device-inventory"></a><span data-ttu-id="96c39-140">Inventario de dispositivos</span><span class="sxs-lookup"><span data-stu-id="96c39-140">Device Inventory</span></span> 
<span data-ttu-id="96c39-141">Los dispositivos que se han detectado pero aún no se han incorporado y protegidos por Microsoft Defender para endpoint aparecerán en el Inventario de dispositivos en la pestaña Puntos de conexión. Ahora puedes usar un nuevo filtro en la lista de inventario de dispositivos denominada Estado de incorporación que puede tener cualquiera de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="96c39-141">Devices that have been discovered but have not yet been onboarded and secured by Microsoft Defender for Endpoint will be listed in Device Inventory within the Endpoints tab. You can now use a new filter in the device inventory list called Onboarding status which can have any of the following values:</span></span>

- <span data-ttu-id="96c39-142">Incorporado: el punto de conexión se incorpora a Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="96c39-142">Onboarded – The endpoint is onboarded to Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="96c39-143">Se puede incorporar: el punto de conexión se descubrió en la red y el sistema operativo se identificó como uno compatible con Microsoft Defender para endpoint, pero no está incorporado actualmente.</span><span class="sxs-lookup"><span data-stu-id="96c39-143">Can be onboarded – The endpoint was discovered in the network and the Operating System was identified as one that is supported by Microsoft Defender for Endpoint, but it is not currently onboarded.</span></span> <span data-ttu-id="96c39-144">Recomendamos encarecidamente la incorporación de estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="96c39-144">We highly recommend onboarding these devices.</span></span>
- <span data-ttu-id="96c39-145">No compatible: el punto de conexión se ha detectado en la red, pero Microsoft Defender no admite endpoint.</span><span class="sxs-lookup"><span data-stu-id="96c39-145">Unsupported – The endpoint was discovered in the network but is not supported by Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="96c39-146">Información insuficiente: el sistema no pudo determinar la compatibilidad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="96c39-146">Insufficient info – The system could not determine the supportability of the device.</span></span> <span data-ttu-id="96c39-147">Habilitar la detección estándar en más dispositivos de la red puede enriquecer los atributos detectados.</span><span class="sxs-lookup"><span data-stu-id="96c39-147">Enabling standard discovery on more devices in the network can enrich the discovered attributes.</span></span> 
 

![Imagen del panel de inventario de dispositivos](images/2b62255cd3a9dd42f3219e437b956fb9.png)



## <a name="vulnerability-assessment-on-discovered-devices"></a><span data-ttu-id="96c39-149">Evaluación de vulnerabilidad en dispositivos detectados</span><span class="sxs-lookup"><span data-stu-id="96c39-149">Vulnerability assessment on discovered devices</span></span>
<span data-ttu-id="96c39-150">Las vulnerabilidades y riesgos en los dispositivos, así como otros dispositivos no administrados detectados en la red, forman parte de los flujos actuales de TVM en "Recomendaciones de seguridad" y se representan en páginas de entidades en el portal.</span><span class="sxs-lookup"><span data-stu-id="96c39-150">Vulnerabilities and risks on your devices as well as other discovered unmanaged devices in the network are part of the current TVM flows under "Security Recommendations" and represented in entity pages across the portal.</span></span> <span data-ttu-id="96c39-151">Busque recomendaciones de seguridad relacionadas con "SSH" para buscar vulnerabilidades SSH relacionadas con dispositivos administrados y no administrados.</span><span class="sxs-lookup"><span data-stu-id="96c39-151">Search for "SSH" related security recommendations to find SSH vulnerabilities that are related for unmanaged and managed devices.</span></span> 

![Imagen del panel de recomendaciones de seguridad](images/1156c82ffadd356ce329d1cf551e806c.png)  

## <a name="use-advanced-hunting-on-discovered-devices"></a><span data-ttu-id="96c39-153">Usar la búsqueda avanzada en dispositivos detectados</span><span class="sxs-lookup"><span data-stu-id="96c39-153">Use Advanced Hunting on discovered devices</span></span>
<span data-ttu-id="96c39-154">Puedes usar consultas de búsqueda avanzada para obtener visibilidad en dispositivos detectados.</span><span class="sxs-lookup"><span data-stu-id="96c39-154">You can use Advanced Hunting queries to gain visibility on discovered devices.</span></span>
<span data-ttu-id="96c39-155">Encuentre detalles sobre los puntos de conexión detectados en la tabla DeviceInfo o información relacionada con la red sobre esos dispositivos en la tabla DeviceNetworkInfo.</span><span class="sxs-lookup"><span data-stu-id="96c39-155">Find details about discovered Endpoints in the DeviceInfo table, or network-related information about those devices in the DeviceNetworkInfo table.</span></span>
  

![Imagen del uso avanzado de la búsqueda](images/f48ba1779eddee9872f167453c24e5c9.png)


<span data-ttu-id="96c39-157">La detección de dispositivos aprovecha los dispositivos integrados de Microsoft Defender para endpoint como origen de datos de red para atribuir actividades a dispositivos no incorporados.</span><span class="sxs-lookup"><span data-stu-id="96c39-157">Device discovery leverages Microsoft Defender for Endpoint onboarded devices as a network data source to attribute activities to non-onboarded devices.</span></span> <span data-ttu-id="96c39-158">Esto significa que si un dispositivo integrado de Microsoft Defender para endpoint se comunica con un dispositivo no incorporado, las actividades del dispositivo no incorporado se pueden ver en la escala de tiempo y a través de la tabla DeviceNetworkEvents de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="96c39-158">This means that if a Microsoft Defender for Endpoint onboarded device communicated with a non-onboarded device, activities on the non-onboarded device can be seen on the timeline and through the Advanced hunting DeviceNetworkEvents table.</span></span> 



<span data-ttu-id="96c39-159">Los nuevos eventos están basados en conexiones del Protocolo de control de transmisión (TCP) y se ajustarán al esquema DeviceNetworkEvents actual.</span><span class="sxs-lookup"><span data-stu-id="96c39-159">New events are Transmission Control Protocol (TCP) connections-based and will fit to the current DeviceNetworkEvents scheme.</span></span> <span data-ttu-id="96c39-160">Entrada tcp al dispositivo habilitado para Microsoft Defender para endpoint desde un dispositivo que no es de Microsoft Defender para endpoint habilitado.</span><span class="sxs-lookup"><span data-stu-id="96c39-160">TCP ingress to the Microsoft Defender for Endpoint enabled device from a non-Microsoft Defender for Endpoint enabled.</span></span>  

<span data-ttu-id="96c39-161">También se han agregado los siguientes tipos de acción:</span><span class="sxs-lookup"><span data-stu-id="96c39-161">The following action types have also been added:</span></span>  

- <span data-ttu-id="96c39-162">ConnectionAttempt: un intento de establecer una conexión TCP (syn)</span><span class="sxs-lookup"><span data-stu-id="96c39-162">ConnectionAttempt - An attempt to establish a TCP connection (syn)</span></span>  
- <span data-ttu-id="96c39-163">ConnectionAcknowledged: confirmación de que se aceptó una conexión TCP (syn\ack)</span><span class="sxs-lookup"><span data-stu-id="96c39-163">ConnectionAcknowledged - An acknowledgment that a TCP connection was accepted (syn\ack)</span></span>  

<span data-ttu-id="96c39-164">Puede probar esta consulta de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="96c39-164">You can try this example query:</span></span>  

```
DeviceNetworkEvents  
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"  
| take 10  
```


## <a name="changed-behaviour"></a><span data-ttu-id="96c39-165">Comportamiento modificado</span><span class="sxs-lookup"><span data-stu-id="96c39-165">Changed behaviour</span></span>
<span data-ttu-id="96c39-166">En la siguiente sección se enumeran los cambios que observará en Microsoft Defender para endpoint y/o El Centro de seguridad de Microsoft 365 cuando esta funcionalidad esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="96c39-166">The following section lists the changes you'll observe in Microsoft Defender for Endpoint and/or Microsoft 365 Security Center when this capability is enabled.</span></span> 
 
1.  <span data-ttu-id="96c39-167">Se espera que los dispositivos que no están incorporados a Microsoft Defender a Endpoint aparezcan en el inventario de dispositivos, la búsqueda avanzada y las consultas api.</span><span class="sxs-lookup"><span data-stu-id="96c39-167">Devices that are not onboarded to Microsoft Defender to Endpoint are expected to appear in the device inventory, advanced hunting, and API queries.</span></span> <span data-ttu-id="96c39-168">Esto puede aumentar significativamente el tamaño de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="96c39-168">This may significantly increase the size of query results.</span></span> 
    1. <span data-ttu-id="96c39-169">Las tablas "DeviceInfo" y "DeviceNetworkInfo" en la búsqueda avanzada ahora mantendrán el dispositivo detectado.</span><span class="sxs-lookup"><span data-stu-id="96c39-169">"DeviceInfo" and "DeviceNetworkInfo" tables in Advanced Hunting will now hold discovered device.</span></span> <span data-ttu-id="96c39-170">Puedes filtrar esos dispositivos mediante el atributo "OnboardingStatus".</span><span class="sxs-lookup"><span data-stu-id="96c39-170">You can filter out those devices by using “OnboardingStatus” attribute.</span></span>

    2. <span data-ttu-id="96c39-171">Se espera que los dispositivos detectados aparezcan en los resultados de consulta de la API de streaming.</span><span class="sxs-lookup"><span data-stu-id="96c39-171">Discovered devices are expected to appear in Streaming API query results.</span></span> <span data-ttu-id="96c39-172">Puede filtrar esos dispositivos mediante el `OnboardingStatus` filtro de la consulta.</span><span class="sxs-lookup"><span data-stu-id="96c39-172">You can filter out those devices by using the `OnboardingStatus` filter in your query.</span></span> 

2.  <span data-ttu-id="96c39-173">Los dispositivos no administrados se asignarán a grupos de dispositivos existentes según los criterios definidos.</span><span class="sxs-lookup"><span data-stu-id="96c39-173">Unmanaged devices will be assigned to existing device groups based on the defined criteria.</span></span> 
3.  <span data-ttu-id="96c39-174">En raras ocasiones, la detección estándar puede desencadenar alertas en monitores de red o herramientas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="96c39-174">In rare cases, Standard discovery might trigger alerts on network monitors or security tools.</span></span> <span data-ttu-id="96c39-175">Proporcione comentarios, si experimenta este tipo de eventos, para evitar que estos problemas se repitan.</span><span class="sxs-lookup"><span data-stu-id="96c39-175">Please provide feedback, if you experience such events, to help prevent these issues from recurring.</span></span> <span data-ttu-id="96c39-176">Puede excluir explícitamente destinos específicos o subredes enteras de ser sondeados activamente por la detección estándar.</span><span class="sxs-lookup"><span data-stu-id="96c39-176">You can explicitly exclude specific targets or entire subnets from being actively probed by Standard discovery.</span></span> 



## <a name="next-steps"></a><span data-ttu-id="96c39-177">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="96c39-177">Next steps</span></span>
- [<span data-ttu-id="96c39-178">Configurar la detección de dispositivos</span><span class="sxs-lookup"><span data-stu-id="96c39-178">Configure device discovery</span></span>](configure-device-discovery.md)
- [<span data-ttu-id="96c39-179">Preguntas frecuentes sobre detección de dispositivos</span><span class="sxs-lookup"><span data-stu-id="96c39-179">Device discovery FAQs</span></span>](device-discovery-faq.md)
