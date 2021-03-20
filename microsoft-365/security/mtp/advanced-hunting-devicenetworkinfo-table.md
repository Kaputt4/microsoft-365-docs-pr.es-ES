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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3e3b657d1c33e411f38a8f583adb96139cc85207
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907401"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="b8ab5-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="b8ab5-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b8ab5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b8ab5-105">**Applies to:**</span></span>
- <span data-ttu-id="b8ab5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8ab5-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="b8ab5-107">La tabla del esquema de búsqueda avanzada contiene información sobre la configuración de redes de máquinas, incluidos adaptadores de red, direcciones IP y MAC, y redes `DeviceNetworkInfo` o dominios conectados. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b8ab5-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="b8ab5-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="b8ab5-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b8ab5-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b8ab5-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b8ab5-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="b8ab5-110">Column name</span></span> | <span data-ttu-id="b8ab5-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b8ab5-111">Data type</span></span> | <span data-ttu-id="b8ab5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8ab5-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b8ab5-113">datetime</span><span class="sxs-lookup"><span data-stu-id="b8ab5-113">datetime</span></span> | <span data-ttu-id="b8ab5-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="b8ab5-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="b8ab5-115">cadena</span><span class="sxs-lookup"><span data-stu-id="b8ab5-115">string</span></span> | <span data-ttu-id="b8ab5-116">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="b8ab5-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b8ab5-117">cadena</span><span class="sxs-lookup"><span data-stu-id="b8ab5-117">string</span></span> | <span data-ttu-id="b8ab5-118">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="b8ab5-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="b8ab5-119">largo</span><span class="sxs-lookup"><span data-stu-id="b8ab5-119">long</span></span> | <span data-ttu-id="b8ab5-120">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="b8ab5-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="b8ab5-121">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp</span><span class="sxs-lookup"><span data-stu-id="b8ab5-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="b8ab5-122">string</span><span class="sxs-lookup"><span data-stu-id="b8ab5-122">string</span></span> | <span data-ttu-id="b8ab5-123">Nombre del adaptador de red</span><span class="sxs-lookup"><span data-stu-id="b8ab5-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="b8ab5-124">string</span><span class="sxs-lookup"><span data-stu-id="b8ab5-124">string</span></span> | <span data-ttu-id="b8ab5-125">Dirección MAC del adaptador de red</span><span class="sxs-lookup"><span data-stu-id="b8ab5-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="b8ab5-126">string</span><span class="sxs-lookup"><span data-stu-id="b8ab5-126">string</span></span> | <span data-ttu-id="b8ab5-127">Tipo de adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="b8ab5-127">Network adapter type.</span></span> <span data-ttu-id="b8ab5-128">Para obtener los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="b8ab5-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="b8ab5-129">string</span><span class="sxs-lookup"><span data-stu-id="b8ab5-129">string</span></span> | <span data-ttu-id="b8ab5-130">Estado operativo del adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="b8ab5-130">Operational status of the network adapter.</span></span> <span data-ttu-id="b8ab5-131">Para obtener los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="b8ab5-131">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="b8ab5-132">string</span><span class="sxs-lookup"><span data-stu-id="b8ab5-132">string</span></span> | <span data-ttu-id="b8ab5-133">Protocolo de túnel, si la interfaz se usa para este fin, por ejemplo, 6to4, Teredo, ISATAP, PPTP, SSTP y SSH</span><span class="sxs-lookup"><span data-stu-id="b8ab5-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="b8ab5-134">string</span><span class="sxs-lookup"><span data-stu-id="b8ab5-134">string</span></span> | <span data-ttu-id="b8ab5-135">Redes a las que está conectado el adaptador.</span><span class="sxs-lookup"><span data-stu-id="b8ab5-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="b8ab5-136">Cada matriz JSON contiene el nombre de red, la categoría (público, privado o dominio), una descripción y una marca que indica si está conectada públicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="b8ab5-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="b8ab5-137">string</span><span class="sxs-lookup"><span data-stu-id="b8ab5-137">string</span></span> | <span data-ttu-id="b8ab5-138">Direcciones de servidor DNS en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="b8ab5-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="b8ab5-139">string</span><span class="sxs-lookup"><span data-stu-id="b8ab5-139">string</span></span> | <span data-ttu-id="b8ab5-140">Dirección IPv4 del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="b8ab5-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="b8ab5-141">string</span><span class="sxs-lookup"><span data-stu-id="b8ab5-141">string</span></span> | <span data-ttu-id="b8ab5-142">Dirección IPv6 del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="b8ab5-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="b8ab5-143">string</span><span class="sxs-lookup"><span data-stu-id="b8ab5-143">string</span></span> | <span data-ttu-id="b8ab5-144">Direcciones de puerta de enlace predeterminadas en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="b8ab5-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="b8ab5-145">string</span><span class="sxs-lookup"><span data-stu-id="b8ab5-145">string</span></span> | <span data-ttu-id="b8ab5-146">Matriz JSON que contiene todas las direcciones IP asignadas al adaptador, junto con su prefijo de subred y espacio de direcciones IP respectivos, como pública, privada o local de vínculos</span><span class="sxs-lookup"><span data-stu-id="b8ab5-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b8ab5-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b8ab5-147">Related topics</span></span>
- [<span data-ttu-id="b8ab5-148">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="b8ab5-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b8ab5-149">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="b8ab5-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b8ab5-150">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="b8ab5-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b8ab5-151">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="b8ab5-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b8ab5-152">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="b8ab5-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b8ab5-153">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="b8ab5-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)