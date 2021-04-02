---
title: Tabla DeviceNetworkInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la configuración de red en la tabla DeviceNetworkInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, devicenetworkinfo, dispositivo, dispositivo, mac, ip, adaptador, dns, dhcp, puerta de enlace, túnel, DeviceNetworkInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e63af4153804a09424c36fb03ac715da5f6d9485
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499137"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="6f0db-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="6f0db-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6f0db-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6f0db-105">**Applies to:**</span></span>
- [<span data-ttu-id="6f0db-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6f0db-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="6f0db-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6f0db-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6f0db-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6f0db-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="6f0db-109">La tabla del esquema de búsqueda avanzada contiene información sobre la configuración de redes de dispositivos, incluidos adaptadores de red, direcciones IP y MAC, y redes `DeviceNetworkInfo` o dominios conectados. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6f0db-109">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of devices, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="6f0db-110">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6f0db-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6f0db-111">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea la referencia de esquema [de búsqueda avanzada](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="6f0db-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="6f0db-112">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="6f0db-112">Column name</span></span> | <span data-ttu-id="6f0db-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6f0db-113">Data type</span></span> | <span data-ttu-id="6f0db-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f0db-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6f0db-115">datetime</span><span class="sxs-lookup"><span data-stu-id="6f0db-115">datetime</span></span> | <span data-ttu-id="6f0db-116">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="6f0db-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="6f0db-117">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-117">string</span></span> | <span data-ttu-id="6f0db-118">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="6f0db-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6f0db-119">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-119">string</span></span> | <span data-ttu-id="6f0db-120">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f0db-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ReportId` | <span data-ttu-id="6f0db-121">largo</span><span class="sxs-lookup"><span data-stu-id="6f0db-121">long</span></span> | <span data-ttu-id="6f0db-122">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="6f0db-122">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6f0db-123">Para identificar eventos únicos, esta columna debe usarse junto con las `DeviceName` columnas y `Timestamp`</span><span class="sxs-lookup"><span data-stu-id="6f0db-123">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="6f0db-124">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-124">string</span></span> | <span data-ttu-id="6f0db-125">Nombre del adaptador de red</span><span class="sxs-lookup"><span data-stu-id="6f0db-125">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="6f0db-126">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-126">string</span></span> | <span data-ttu-id="6f0db-127">Dirección MAC del adaptador de red</span><span class="sxs-lookup"><span data-stu-id="6f0db-127">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="6f0db-128">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-128">string</span></span> | <span data-ttu-id="6f0db-129">Tipo de adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="6f0db-129">Network adapter type.</span></span> <span data-ttu-id="6f0db-130">Para obtener los valores posibles, consulte [esta enumeración](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="6f0db-130">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="6f0db-131">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-131">string</span></span> | <span data-ttu-id="6f0db-132">Estado operativo del adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="6f0db-132">Operational status of the network adapter.</span></span> <span data-ttu-id="6f0db-133">Para obtener los valores posibles, consulte [esta enumeración](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="6f0db-133">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `TunnelType` | <span data-ttu-id="6f0db-134">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-134">string</span></span> | <span data-ttu-id="6f0db-135">Protocolo de túnel, si la interfaz se usa para este fin, por ejemplo, 6to4, Teredo, ISATAP, PPTP, SSTP y SSH</span><span class="sxs-lookup"><span data-stu-id="6f0db-135">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="6f0db-136">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-136">string</span></span> | <span data-ttu-id="6f0db-137">Redes a las que está conectado el adaptador.</span><span class="sxs-lookup"><span data-stu-id="6f0db-137">Networks that the adapter is connected to.</span></span> <span data-ttu-id="6f0db-138">Cada matriz JSON contiene el nombre de red, la categoría (público, privado o dominio), una descripción y una marca que indica si está conectada públicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="6f0db-138">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="6f0db-139">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-139">string</span></span> | <span data-ttu-id="6f0db-140">Direcciones de servidor DNS en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="6f0db-140">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="6f0db-141">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-141">string</span></span> | <span data-ttu-id="6f0db-142">Dirección IPv4 del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="6f0db-142">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="6f0db-143">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-143">string</span></span> | <span data-ttu-id="6f0db-144">Dirección IPv6 del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="6f0db-144">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="6f0db-145">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-145">string</span></span> | <span data-ttu-id="6f0db-146">Direcciones de puerta de enlace predeterminadas en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="6f0db-146">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="6f0db-147">cadena</span><span class="sxs-lookup"><span data-stu-id="6f0db-147">string</span></span> | <span data-ttu-id="6f0db-148">Matriz JSON que contiene todas las direcciones IP asignadas al adaptador, junto con su prefijo de subred y espacio de direcciones IP respectivos, como pública, privada o local de vínculos</span><span class="sxs-lookup"><span data-stu-id="6f0db-148">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6f0db-149">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6f0db-149">Related topics</span></span>
- [<span data-ttu-id="6f0db-150">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="6f0db-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6f0db-151">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="6f0db-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6f0db-152">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="6f0db-152">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
