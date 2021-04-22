---
title: Tabla DeviceTvmSoftwareVulnerabilities en el esquema de búsqueda avanzada
description: Obtenga información sobre las vulnerabilidades de software encontradas en los dispositivos y la lista de actualizaciones de seguridad disponibles que abordan cada vulnerabilidad en la tabla DeviceTvmSoftwareVulnerabilities del esquema de búsqueda avanzada.
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
ms.openlocfilehash: 24da8f556fe9f8a3b8172afe87ea9a87e4522d44
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934830"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="26181-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="26181-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="26181-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="26181-105">**Applies to:**</span></span>
- <span data-ttu-id="26181-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26181-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="26181-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="26181-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="26181-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="26181-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="26181-109">La tabla del esquema de búsqueda avanzada contiene la lista de & de vulnerabilidades de los productos `DeviceTvmSoftwareVulnerabilities` de software [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) instalados.</span><span class="sxs-lookup"><span data-stu-id="26181-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="26181-110">Esta tabla también incluye información sobre el sistema operativo, IDs de CVE e información sobre la gravedad de la vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="26181-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="26181-111">Puedes usar esta tabla, por ejemplo, para buscar eventos que impliquen dispositivos con vulnerabilidades graves en su software.</span><span class="sxs-lookup"><span data-stu-id="26181-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="26181-112">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="26181-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="26181-113">Las `DeviceTvmSoftwareInventory` tablas y han reemplazado a la `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabla.</span><span class="sxs-lookup"><span data-stu-id="26181-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="26181-114">Juntos, las dos primeras tablas incluyen más columnas que puedes usar para ayudar a informar a tus actividades de administración de vulnerablidad o buscar dispositivos vulnerables.</span><span class="sxs-lookup"><span data-stu-id="26181-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="26181-115">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="26181-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="26181-116">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="26181-116">Column name</span></span> | <span data-ttu-id="26181-117">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="26181-117">Data type</span></span> | <span data-ttu-id="26181-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="26181-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="26181-119">string</span><span class="sxs-lookup"><span data-stu-id="26181-119">string</span></span> | <span data-ttu-id="26181-120">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="26181-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="26181-121">cadena</span><span class="sxs-lookup"><span data-stu-id="26181-121">string</span></span> | <span data-ttu-id="26181-122">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="26181-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="26181-123">cadena</span><span class="sxs-lookup"><span data-stu-id="26181-123">string</span></span> | <span data-ttu-id="26181-124">Plataforma del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="26181-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="26181-125">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="26181-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="26181-126">cadena</span><span class="sxs-lookup"><span data-stu-id="26181-126">string</span></span> | <span data-ttu-id="26181-127">Versión del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="26181-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="26181-128">cadena</span><span class="sxs-lookup"><span data-stu-id="26181-128">string</span></span> | <span data-ttu-id="26181-129">Arquitectura del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="26181-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="26181-130">cadena</span><span class="sxs-lookup"><span data-stu-id="26181-130">string</span></span> | <span data-ttu-id="26181-131">Nombre del proveedor de software</span><span class="sxs-lookup"><span data-stu-id="26181-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="26181-132">cadena</span><span class="sxs-lookup"><span data-stu-id="26181-132">string</span></span> | <span data-ttu-id="26181-133">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="26181-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="26181-134">cadena</span><span class="sxs-lookup"><span data-stu-id="26181-134">string</span></span> | <span data-ttu-id="26181-135">Número de versión del producto de software</span><span class="sxs-lookup"><span data-stu-id="26181-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="26181-136">cadena</span><span class="sxs-lookup"><span data-stu-id="26181-136">string</span></span> | <span data-ttu-id="26181-137">Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE)</span><span class="sxs-lookup"><span data-stu-id="26181-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="26181-138">cadena</span><span class="sxs-lookup"><span data-stu-id="26181-138">string</span></span> | <span data-ttu-id="26181-139">Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas</span><span class="sxs-lookup"><span data-stu-id="26181-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="26181-140">cadena</span><span class="sxs-lookup"><span data-stu-id="26181-140">string</span></span> | <span data-ttu-id="26181-141">Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="26181-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="26181-142">cadena</span><span class="sxs-lookup"><span data-stu-id="26181-142">string</span></span> | <span data-ttu-id="26181-143">Identificador de las actualizaciones de seguridad o el identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes</span><span class="sxs-lookup"><span data-stu-id="26181-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="26181-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="26181-144">Related topics</span></span>

- [<span data-ttu-id="26181-145">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="26181-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="26181-146">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="26181-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="26181-147">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="26181-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="26181-148">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="26181-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="26181-149">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="26181-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="26181-150">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="26181-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="26181-151">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="26181-151">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)