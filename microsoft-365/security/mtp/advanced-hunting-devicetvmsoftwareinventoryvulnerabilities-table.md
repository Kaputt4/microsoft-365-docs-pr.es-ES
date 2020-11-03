---
title: Tabla DeviceTvmSoftwareInventoryVulnerabilities en el esquema de búsqueda avanzada
description: Obtenga más información sobre el inventario de software en sus dispositivos y sus vulnerabilidades en la tabla DeviceTvmSoftwareInventoryVulnerabilities del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, amenaza & la administración de vulnerabilidades, TVM, administración de dispositivos, software, inventario, vulnerabilidades, identificador de CVE, so DeviceTvmSoftwareInventoryVulnerabilities
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 2eb194b2471d0324606a95b4ae7327ffc0751ff6
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847579"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="b2265-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="b2265-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b2265-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b2265-105">**Applies to:**</span></span>
- <span data-ttu-id="b2265-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="b2265-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="b2265-107">La tabla `DeviceTvmSoftwareInventoryVulnerabilities` en el esquema de búsqueda avanzada contiene el inventario de software de la [Administración de amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) en sus dispositivos, así como las vulnerabilidades conocidas de estos productos de software.</span><span class="sxs-lookup"><span data-stu-id="b2265-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="b2265-108">Esta tabla también incluye información sobre el sistema operativo, IDs de CVE e información sobre la gravedad de la vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="b2265-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="b2265-109">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="b2265-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="b2265-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b2265-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b2265-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="b2265-111">Column name</span></span> | <span data-ttu-id="b2265-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b2265-112">Data type</span></span> | <span data-ttu-id="b2265-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2265-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="b2265-114">string</span><span class="sxs-lookup"><span data-stu-id="b2265-114">string</span></span> | <span data-ttu-id="b2265-115">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="b2265-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b2265-116">cadena</span><span class="sxs-lookup"><span data-stu-id="b2265-116">string</span></span> | <span data-ttu-id="b2265-117">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="b2265-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="b2265-118">cadena</span><span class="sxs-lookup"><span data-stu-id="b2265-118">string</span></span> | <span data-ttu-id="b2265-119">Plataforma del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b2265-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="b2265-120">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b2265-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="b2265-121">cadena</span><span class="sxs-lookup"><span data-stu-id="b2265-121">string</span></span> | <span data-ttu-id="b2265-122">Versión del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b2265-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="b2265-123">cadena</span><span class="sxs-lookup"><span data-stu-id="b2265-123">string</span></span> | <span data-ttu-id="b2265-124">Arquitectura del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b2265-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="b2265-125">cadena</span><span class="sxs-lookup"><span data-stu-id="b2265-125">string</span></span> | <span data-ttu-id="b2265-126">Nombre del proveedor de software</span><span class="sxs-lookup"><span data-stu-id="b2265-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="b2265-127">cadena</span><span class="sxs-lookup"><span data-stu-id="b2265-127">string</span></span> | <span data-ttu-id="b2265-128">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="b2265-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="b2265-129">cadena</span><span class="sxs-lookup"><span data-stu-id="b2265-129">string</span></span> | <span data-ttu-id="b2265-130">Número de versión del producto de software</span><span class="sxs-lookup"><span data-stu-id="b2265-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="b2265-131">cadena</span><span class="sxs-lookup"><span data-stu-id="b2265-131">string</span></span> | <span data-ttu-id="b2265-132">Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE)</span><span class="sxs-lookup"><span data-stu-id="b2265-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="b2265-133">string</span><span class="sxs-lookup"><span data-stu-id="b2265-133">string</span></span> | <span data-ttu-id="b2265-134">Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas</span><span class="sxs-lookup"><span data-stu-id="b2265-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="b2265-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b2265-135">Related topics</span></span>

- [<span data-ttu-id="b2265-136">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="b2265-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b2265-137">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="b2265-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b2265-138">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="b2265-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b2265-139">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="b2265-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b2265-140">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="b2265-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b2265-141">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="b2265-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b2265-142">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="b2265-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
