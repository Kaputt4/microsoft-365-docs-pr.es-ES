---
title: Tabla DeviceNetworkInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la configuración de red en la tabla DeviceNetworkInfo del esquema de búsqueda avanzada.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, machinenetworkinfo, DeviceNetworkInfo, dispositivo, equipo, Mac, IP, adaptador, DNS, DHCP, puerta de enlace, túnel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 05812ec1c747c019bdba1c7ecffc2b33bd5f793a
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413883"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="20a6b-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="20a6b-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="20a6b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="20a6b-105">**Applies to:**</span></span>
- <span data-ttu-id="20a6b-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="20a6b-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="20a6b-107">La `DeviceNetworkInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre la configuración de red de los equipos, incluidos los adaptadores de red, las direcciones IP y Mac y las redes o los dominios conectados.</span><span class="sxs-lookup"><span data-stu-id="20a6b-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="20a6b-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="20a6b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="20a6b-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="20a6b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="20a6b-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="20a6b-110">Column name</span></span> | <span data-ttu-id="20a6b-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="20a6b-111">Data type</span></span> | <span data-ttu-id="20a6b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="20a6b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="20a6b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="20a6b-113">datetime</span></span> | <span data-ttu-id="20a6b-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="20a6b-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="20a6b-115">cadena</span><span class="sxs-lookup"><span data-stu-id="20a6b-115">string</span></span> | <span data-ttu-id="20a6b-116">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="20a6b-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="20a6b-117">cadena</span><span class="sxs-lookup"><span data-stu-id="20a6b-117">string</span></span> | <span data-ttu-id="20a6b-118">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="20a6b-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="20a6b-119">largo</span><span class="sxs-lookup"><span data-stu-id="20a6b-119">long</span></span> | <span data-ttu-id="20a6b-120">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="20a6b-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="20a6b-121">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y timestamp.</span><span class="sxs-lookup"><span data-stu-id="20a6b-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="20a6b-122">string</span><span class="sxs-lookup"><span data-stu-id="20a6b-122">string</span></span> | <span data-ttu-id="20a6b-123">Nombre del adaptador de red</span><span class="sxs-lookup"><span data-stu-id="20a6b-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="20a6b-124">string</span><span class="sxs-lookup"><span data-stu-id="20a6b-124">string</span></span> | <span data-ttu-id="20a6b-125">Dirección MAC del adaptador de red</span><span class="sxs-lookup"><span data-stu-id="20a6b-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="20a6b-126">string</span><span class="sxs-lookup"><span data-stu-id="20a6b-126">string</span></span> | <span data-ttu-id="20a6b-127">Tipo de adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="20a6b-127">Network adapter type.</span></span> <span data-ttu-id="20a6b-128">Para obtener los valores posibles, consulte [esta enumeración](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) .</span><span class="sxs-lookup"><span data-stu-id="20a6b-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="20a6b-129">string</span><span class="sxs-lookup"><span data-stu-id="20a6b-129">string</span></span> | <span data-ttu-id="20a6b-130">Estado operativo del adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="20a6b-130">Operational status of the network adapter.</span></span> <span data-ttu-id="20a6b-131">Para obtener los valores posibles, consulte [esta enumeración](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) .</span><span class="sxs-lookup"><span data-stu-id="20a6b-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="20a6b-132">string</span><span class="sxs-lookup"><span data-stu-id="20a6b-132">string</span></span> | <span data-ttu-id="20a6b-133">Protocolo de túnel, si se usa la interfaz para este propósito, por ejemplo, 6to4, Teredo, ISATAP, PPTP, SSTP y SSH</span><span class="sxs-lookup"><span data-stu-id="20a6b-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="20a6b-134">string</span><span class="sxs-lookup"><span data-stu-id="20a6b-134">string</span></span> | <span data-ttu-id="20a6b-135">Redes a las que está conectado el adaptador.</span><span class="sxs-lookup"><span data-stu-id="20a6b-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="20a6b-136">Cada matriz JSON contiene el nombre de red, la categoría (pública, privada o de dominio), una descripción y una marca que indica si está conectado públicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="20a6b-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="20a6b-137">string</span><span class="sxs-lookup"><span data-stu-id="20a6b-137">string</span></span> | <span data-ttu-id="20a6b-138">Direcciones de servidor DNS en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="20a6b-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="20a6b-139">string</span><span class="sxs-lookup"><span data-stu-id="20a6b-139">string</span></span> | <span data-ttu-id="20a6b-140">Dirección IPv4 del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="20a6b-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="20a6b-141">string</span><span class="sxs-lookup"><span data-stu-id="20a6b-141">string</span></span> | <span data-ttu-id="20a6b-142">Dirección IPv6 del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="20a6b-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="20a6b-143">string</span><span class="sxs-lookup"><span data-stu-id="20a6b-143">string</span></span> | <span data-ttu-id="20a6b-144">Direcciones de puerta de enlace predeterminadas en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="20a6b-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="20a6b-145">string</span><span class="sxs-lookup"><span data-stu-id="20a6b-145">string</span></span> | <span data-ttu-id="20a6b-146">Matriz JSON que contiene todas las direcciones IP asignadas al adaptador, junto con el prefijo de subred y el espacio de direcciones IP respectivos, como Public, Private o local Link</span><span class="sxs-lookup"><span data-stu-id="20a6b-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="20a6b-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="20a6b-147">Related topics</span></span>
- [<span data-ttu-id="20a6b-148">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="20a6b-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="20a6b-149">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="20a6b-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="20a6b-150">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="20a6b-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="20a6b-151">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="20a6b-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="20a6b-152">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="20a6b-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="20a6b-153">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="20a6b-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
