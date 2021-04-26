---
title: Tabla DeviceNetworkInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la configuración de red en la tabla DeviceNetworkInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, machinenetworkinfo, DeviceNetworkInfo, dispositivo, máquina, mac, ip, adaptador, dns, dhcp, puerta de enlace, túnel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 11a6fd00524e3dd7ad456f68da6f493d74deee69
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023198"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="ac91b-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="ac91b-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ac91b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ac91b-105">**Applies to:**</span></span>
- <span data-ttu-id="ac91b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac91b-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="ac91b-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ac91b-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="ac91b-108">La tabla del esquema de búsqueda avanzada contiene información sobre la configuración de redes de máquinas, incluidos adaptadores de red, direcciones IP y MAC, y redes `DeviceNetworkInfo` o dominios conectados. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ac91b-108">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="ac91b-109">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="ac91b-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="ac91b-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ac91b-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ac91b-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="ac91b-111">Column name</span></span> | <span data-ttu-id="ac91b-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ac91b-112">Data type</span></span> | <span data-ttu-id="ac91b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac91b-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ac91b-114">datetime</span><span class="sxs-lookup"><span data-stu-id="ac91b-114">datetime</span></span> | <span data-ttu-id="ac91b-115">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="ac91b-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="ac91b-116">cadena</span><span class="sxs-lookup"><span data-stu-id="ac91b-116">string</span></span> | <span data-ttu-id="ac91b-117">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="ac91b-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ac91b-118">cadena</span><span class="sxs-lookup"><span data-stu-id="ac91b-118">string</span></span> | <span data-ttu-id="ac91b-119">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="ac91b-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="ac91b-120">cadena</span><span class="sxs-lookup"><span data-stu-id="ac91b-120">string</span></span> | <span data-ttu-id="ac91b-121">Nombre del adaptador de red</span><span class="sxs-lookup"><span data-stu-id="ac91b-121">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="ac91b-122">string</span><span class="sxs-lookup"><span data-stu-id="ac91b-122">string</span></span> | <span data-ttu-id="ac91b-123">Dirección MAC del adaptador de red</span><span class="sxs-lookup"><span data-stu-id="ac91b-123">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="ac91b-124">string</span><span class="sxs-lookup"><span data-stu-id="ac91b-124">string</span></span> | <span data-ttu-id="ac91b-125">Tipo de adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="ac91b-125">Network adapter type.</span></span> <span data-ttu-id="ac91b-126">Para obtener los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="ac91b-126">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="ac91b-127">string</span><span class="sxs-lookup"><span data-stu-id="ac91b-127">string</span></span> | <span data-ttu-id="ac91b-128">Estado operativo del adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="ac91b-128">Operational status of the network adapter.</span></span> <span data-ttu-id="ac91b-129">Para obtener los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.operationalstatus)</span><span class="sxs-lookup"><span data-stu-id="ac91b-129">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus)</span></span> |
| `TunnelType` | <span data-ttu-id="ac91b-130">string</span><span class="sxs-lookup"><span data-stu-id="ac91b-130">string</span></span> | <span data-ttu-id="ac91b-131">Protocolo de túnel, si la interfaz se usa para este fin, por ejemplo, 6to4, Teredo, ISATAP, PPTP, SSTP y SSH</span><span class="sxs-lookup"><span data-stu-id="ac91b-131">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="ac91b-132">string</span><span class="sxs-lookup"><span data-stu-id="ac91b-132">string</span></span> | <span data-ttu-id="ac91b-133">Redes a las que está conectado el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ac91b-133">Networks that the adapter is connected to.</span></span> <span data-ttu-id="ac91b-134">Cada matriz JSON contiene el nombre de red, la categoría (público, privado o dominio), una descripción y una marca que indica si está conectada públicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="ac91b-134">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="ac91b-135">string</span><span class="sxs-lookup"><span data-stu-id="ac91b-135">string</span></span> | <span data-ttu-id="ac91b-136">Direcciones de servidor DNS en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="ac91b-136">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="ac91b-137">string</span><span class="sxs-lookup"><span data-stu-id="ac91b-137">string</span></span> | <span data-ttu-id="ac91b-138">Dirección IPv4 del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="ac91b-138">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="ac91b-139">string</span><span class="sxs-lookup"><span data-stu-id="ac91b-139">string</span></span> | <span data-ttu-id="ac91b-140">Dirección IPv6 del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="ac91b-140">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="ac91b-141">string</span><span class="sxs-lookup"><span data-stu-id="ac91b-141">string</span></span> | <span data-ttu-id="ac91b-142">Direcciones de puerta de enlace predeterminadas en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="ac91b-142">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="ac91b-143">string</span><span class="sxs-lookup"><span data-stu-id="ac91b-143">string</span></span> | <span data-ttu-id="ac91b-144">Matriz JSON que contiene todas las direcciones IP asignadas al adaptador, junto con su prefijo de subred y espacio de direcciones IP respectivos, como pública, privada o local de vínculos</span><span class="sxs-lookup"><span data-stu-id="ac91b-144">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="ac91b-145">largo</span><span class="sxs-lookup"><span data-stu-id="ac91b-145">long</span></span> | <span data-ttu-id="ac91b-146">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="ac91b-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="ac91b-147">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp</span><span class="sxs-lookup"><span data-stu-id="ac91b-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ac91b-148">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ac91b-148">Related topics</span></span>
- [<span data-ttu-id="ac91b-149">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="ac91b-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ac91b-150">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="ac91b-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ac91b-151">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="ac91b-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ac91b-152">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="ac91b-152">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ac91b-153">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="ac91b-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ac91b-154">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="ac91b-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)