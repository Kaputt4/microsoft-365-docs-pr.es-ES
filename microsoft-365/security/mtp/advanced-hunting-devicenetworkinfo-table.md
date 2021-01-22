---
title: Tabla DeviceNetworkInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la configuración de red en la tabla DeviceNetworkInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, machinenetworkinfo, DeviceNetworkInfo, dispositivo, máquina, mac, ip, adaptador, dns, dhcp, puerta de enlace, túnel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931211"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="2167b-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="2167b-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2167b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2167b-105">**Applies to:**</span></span>
- <span data-ttu-id="2167b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2167b-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="2167b-107">La tabla del esquema de búsqueda avanzada contiene información sobre la configuración de red de máquinas, incluidos adaptadores de red, direcciones IP y MAC, y redes o dominios `DeviceNetworkInfo` conectados. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2167b-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="2167b-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="2167b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="2167b-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2167b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2167b-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="2167b-110">Column name</span></span> | <span data-ttu-id="2167b-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2167b-111">Data type</span></span> | <span data-ttu-id="2167b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2167b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2167b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="2167b-113">datetime</span></span> | <span data-ttu-id="2167b-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="2167b-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="2167b-115">cadena</span><span class="sxs-lookup"><span data-stu-id="2167b-115">string</span></span> | <span data-ttu-id="2167b-116">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="2167b-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2167b-117">cadena</span><span class="sxs-lookup"><span data-stu-id="2167b-117">string</span></span> | <span data-ttu-id="2167b-118">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="2167b-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="2167b-119">largo</span><span class="sxs-lookup"><span data-stu-id="2167b-119">long</span></span> | <span data-ttu-id="2167b-120">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="2167b-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="2167b-121">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp</span><span class="sxs-lookup"><span data-stu-id="2167b-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="2167b-122">string</span><span class="sxs-lookup"><span data-stu-id="2167b-122">string</span></span> | <span data-ttu-id="2167b-123">Nombre del adaptador de red</span><span class="sxs-lookup"><span data-stu-id="2167b-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="2167b-124">string</span><span class="sxs-lookup"><span data-stu-id="2167b-124">string</span></span> | <span data-ttu-id="2167b-125">Dirección MAC del adaptador de red</span><span class="sxs-lookup"><span data-stu-id="2167b-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="2167b-126">string</span><span class="sxs-lookup"><span data-stu-id="2167b-126">string</span></span> | <span data-ttu-id="2167b-127">Tipo de adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="2167b-127">Network adapter type.</span></span> <span data-ttu-id="2167b-128">Para los valores posibles, consulte [esta enumeración](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="2167b-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="2167b-129">string</span><span class="sxs-lookup"><span data-stu-id="2167b-129">string</span></span> | <span data-ttu-id="2167b-130">Estado operativo del adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="2167b-130">Operational status of the network adapter.</span></span> <span data-ttu-id="2167b-131">Para los valores posibles, consulte [esta enumeración](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="2167b-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="2167b-132">string</span><span class="sxs-lookup"><span data-stu-id="2167b-132">string</span></span> | <span data-ttu-id="2167b-133">Protocolo de túnel, si la interfaz se usa para este propósito, por ejemplo 6to4, Teredo, ISATAP, PPTP, SSTP y SSH</span><span class="sxs-lookup"><span data-stu-id="2167b-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="2167b-134">string</span><span class="sxs-lookup"><span data-stu-id="2167b-134">string</span></span> | <span data-ttu-id="2167b-135">Redes a las que está conectado el adaptador.</span><span class="sxs-lookup"><span data-stu-id="2167b-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="2167b-136">Cada matriz JSON contiene el nombre de red, la categoría (público, privado o dominio), una descripción y una marca que indica si está conectada públicamente a Internet.</span><span class="sxs-lookup"><span data-stu-id="2167b-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="2167b-137">string</span><span class="sxs-lookup"><span data-stu-id="2167b-137">string</span></span> | <span data-ttu-id="2167b-138">Direcciones de servidor DNS en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="2167b-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="2167b-139">string</span><span class="sxs-lookup"><span data-stu-id="2167b-139">string</span></span> | <span data-ttu-id="2167b-140">Dirección IPv4 del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="2167b-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="2167b-141">string</span><span class="sxs-lookup"><span data-stu-id="2167b-141">string</span></span> | <span data-ttu-id="2167b-142">Dirección IPv6 del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="2167b-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="2167b-143">string</span><span class="sxs-lookup"><span data-stu-id="2167b-143">string</span></span> | <span data-ttu-id="2167b-144">Direcciones de puerta de enlace predeterminadas en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="2167b-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="2167b-145">string</span><span class="sxs-lookup"><span data-stu-id="2167b-145">string</span></span> | <span data-ttu-id="2167b-146">Matriz JSON que contiene todas las direcciones IP asignadas al adaptador, junto con su prefijo de subred respectivo y espacio de direcciones IP, como público, privado o vínculo local</span><span class="sxs-lookup"><span data-stu-id="2167b-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2167b-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2167b-147">Related topics</span></span>
- [<span data-ttu-id="2167b-148">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="2167b-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2167b-149">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="2167b-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2167b-150">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="2167b-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2167b-151">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="2167b-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2167b-152">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="2167b-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2167b-153">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="2167b-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
