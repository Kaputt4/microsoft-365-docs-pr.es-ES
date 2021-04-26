---
title: Tabla DeviceTvmSoftwareInventory en el esquema de búsqueda avanzada
description: Obtenga información sobre el inventario de software en sus dispositivos en la tabla DeviceTvmSoftwareInventory del esquema de búsqueda avanzado.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de & amenazas, TVM, administración de dispositivos, software, inventario, vulnerabilidades, IDENTIFICADOR CVE, Id. de dispositivo CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 5f82684ebb10b72ff83a6789c010f5ec9fa099e7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024234"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="d2602-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="d2602-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d2602-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d2602-105">**Applies to:**</span></span>
- <span data-ttu-id="d2602-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2602-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="d2602-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d2602-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="d2602-108">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="d2602-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d2602-109">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="d2602-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="d2602-110">La tabla del esquema de búsqueda avanzada contiene el inventario de administración de vulnerabilidades & amenazas del software instalado actualmente en dispositivos de la red, incluida la información de fin `DeviceTvmSoftwareInventory` de soporte técnico. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="d2602-110">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="d2602-111">Por ejemplo, puede buscar eventos que impliquen dispositivos instalados con una versión de software vulnerable actualmente.</span><span class="sxs-lookup"><span data-stu-id="d2602-111">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="d2602-112">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="d2602-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="d2602-113">Las `DeviceTvmSoftwareInventory` tablas y han reemplazado a la `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabla.</span><span class="sxs-lookup"><span data-stu-id="d2602-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="d2602-114">Juntos, las dos primeras tablas incluyen más columnas que puedes usar para ayudar a informar a tus actividades de administración de vulnerablidad o buscar dispositivos vulnerables.</span><span class="sxs-lookup"><span data-stu-id="d2602-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="d2602-115">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d2602-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d2602-116">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="d2602-116">Column name</span></span> | <span data-ttu-id="d2602-117">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d2602-117">Data type</span></span> | <span data-ttu-id="d2602-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2602-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="d2602-119">string</span><span class="sxs-lookup"><span data-stu-id="d2602-119">string</span></span> | <span data-ttu-id="d2602-120">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="d2602-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d2602-121">cadena</span><span class="sxs-lookup"><span data-stu-id="d2602-121">string</span></span> | <span data-ttu-id="d2602-122">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="d2602-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="d2602-123">cadena</span><span class="sxs-lookup"><span data-stu-id="d2602-123">string</span></span> | <span data-ttu-id="d2602-124">Plataforma del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d2602-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="d2602-125">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d2602-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="d2602-126">cadena</span><span class="sxs-lookup"><span data-stu-id="d2602-126">string</span></span> | <span data-ttu-id="d2602-127">Versión del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d2602-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="d2602-128">cadena</span><span class="sxs-lookup"><span data-stu-id="d2602-128">string</span></span> | <span data-ttu-id="d2602-129">Arquitectura del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d2602-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="d2602-130">cadena</span><span class="sxs-lookup"><span data-stu-id="d2602-130">string</span></span> | <span data-ttu-id="d2602-131">Nombre del proveedor de software</span><span class="sxs-lookup"><span data-stu-id="d2602-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="d2602-132">cadena</span><span class="sxs-lookup"><span data-stu-id="d2602-132">string</span></span> | <span data-ttu-id="d2602-133">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="d2602-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="d2602-134">cadena</span><span class="sxs-lookup"><span data-stu-id="d2602-134">string</span></span> | <span data-ttu-id="d2602-135">Número de versión del producto de software</span><span class="sxs-lookup"><span data-stu-id="d2602-135">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="d2602-136">cadena</span><span class="sxs-lookup"><span data-stu-id="d2602-136">string</span></span> | <span data-ttu-id="d2602-137">Indica la fase de ciclo de vida del producto de software en relación con la fecha de fin de soporte técnico (EOS) o de fin de vida (EOL) especificada</span><span class="sxs-lookup"><span data-stu-id="d2602-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="d2602-138">string</span><span class="sxs-lookup"><span data-stu-id="d2602-138">string</span></span> | <span data-ttu-id="d2602-139">Fecha de fin de soporte técnico (EOS) o de fin de vida (EOL) del producto de software</span><span class="sxs-lookup"><span data-stu-id="d2602-139">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="d2602-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d2602-140">Related topics</span></span>

- [<span data-ttu-id="d2602-141">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="d2602-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d2602-142">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="d2602-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d2602-143">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="d2602-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d2602-144">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="d2602-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d2602-145">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="d2602-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d2602-146">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="d2602-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d2602-147">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="d2602-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)