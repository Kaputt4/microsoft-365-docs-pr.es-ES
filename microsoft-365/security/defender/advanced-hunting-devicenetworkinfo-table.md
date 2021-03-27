---
title: Tabla DeviceNetworkInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la configuración de red en la tabla DeviceNetworkInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, machinenetworkinfo, DeviceNetworkInfo, dispositivo, máquina, mac, ip, adaptador, dns, dhcp, puerta de enlace, túnel
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9a3806d3e2bff66e04f4adb50217fc1c6f267364
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382608"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="aeebd-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="aeebd-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="aeebd-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="aeebd-105">**Applies to:**</span></span>
- <span data-ttu-id="aeebd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aeebd-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="aeebd-107">La tabla del esquema de búsqueda avanzada contiene información sobre la configuración de redes de máquinas, incluidos adaptadores de red, direcciones IP y MAC, y redes `DeviceNetworkInfo` o dominios conectados. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="aeebd-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="aeebd-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="aeebd-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="aeebd-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="aeebd-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="aeebd-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="aeebd-110">Column name</span></span> | <span data-ttu-id="aeebd-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="aeebd-111">Data type</span></span> | <span data-ttu-id="aeebd-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="aeebd-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="aeebd-113">datetime</span><span class="sxs-lookup"><span data-stu-id="aeebd-113">datetime</span></span> | <span data-ttu-id="aeebd-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="aeebd-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="aeebd-115">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-115">string</span></span> | <span data-ttu-id="aeebd-116">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="aeebd-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="aeebd-117">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-117">string</span></span> | <span data-ttu-id="aeebd-118">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="aeebd-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="aeebd-119">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-119">string</span></span> | <span data-ttu-id="aeebd-120">Nombre del adaptador de red</span><span class="sxs-lookup"><span data-stu-id="aeebd-120">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="aeebd-121">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-121">string</span></span> | <span data-ttu-id="aeebd-122">Dirección MAC del adaptador de red</span><span class="sxs-lookup"><span data-stu-id="aeebd-122">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="aeebd-123">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-123">string</span></span> | <span data-ttu-id="aeebd-124">Tipo de adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="aeebd-124">Network adapter type.</span></span> <span data-ttu-id="aeebd-125">Para obtener los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="aeebd-125">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="aeebd-126">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-126">string</span></span> | <span data-ttu-id="aeebd-127">Estado operativo del adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="aeebd-127">Operational status of the network adapter.</span></span> <span data-ttu-id="aeebd-128">Para obtener los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="aeebd-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="aeebd-129">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-129">string</span></span> | <span data-ttu-id="aeebd-130">Protocolo de túnel, si la interfaz se usa para este fin, por ejemplo, 6to4, Teredo, ISATAP, PPTP, SSTP y SSH</span><span class="sxs-lookup"><span data-stu-id="aeebd-130">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="aeebd-131">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-131">string</span></span> | <span data-ttu-id="aeebd-132">Redes a las que está conectado el adaptador.</span><span class="sxs-lookup"><span data-stu-id="aeebd-132">Networks that the adapter is connected to.</span></span> <span data-ttu-id="aeebd-133">Cada matriz JSON contiene el nombre de red, la categoría (público, privado o dominio), una descripción y una marca que indica si está conectada públicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="aeebd-133">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="aeebd-134">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-134">string</span></span> | <span data-ttu-id="aeebd-135">Direcciones de servidor DNS en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="aeebd-135">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="aeebd-136">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-136">string</span></span> | <span data-ttu-id="aeebd-137">Dirección IPv4 del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="aeebd-137">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="aeebd-138">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-138">string</span></span> | <span data-ttu-id="aeebd-139">Dirección IPv6 del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="aeebd-139">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="aeebd-140">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-140">string</span></span> | <span data-ttu-id="aeebd-141">Direcciones de puerta de enlace predeterminadas en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="aeebd-141">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="aeebd-142">cadena</span><span class="sxs-lookup"><span data-stu-id="aeebd-142">string</span></span> | <span data-ttu-id="aeebd-143">Matriz JSON que contiene todas las direcciones IP asignadas al adaptador, junto con su prefijo de subred y espacio de direcciones IP respectivos, como pública, privada o local de vínculos</span><span class="sxs-lookup"><span data-stu-id="aeebd-143">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="aeebd-144">largo</span><span class="sxs-lookup"><span data-stu-id="aeebd-144">long</span></span> | <span data-ttu-id="aeebd-145">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="aeebd-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="aeebd-146">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp</span><span class="sxs-lookup"><span data-stu-id="aeebd-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="aeebd-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aeebd-147">Related topics</span></span>
- [<span data-ttu-id="aeebd-148">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="aeebd-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="aeebd-149">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="aeebd-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="aeebd-150">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="aeebd-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="aeebd-151">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="aeebd-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="aeebd-152">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="aeebd-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="aeebd-153">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="aeebd-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)