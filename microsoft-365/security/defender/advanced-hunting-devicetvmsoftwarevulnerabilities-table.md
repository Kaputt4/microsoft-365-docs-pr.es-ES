---
title: Tabla DeviceTvmSoftwareVulnerabilities en el esquema de búsqueda avanzada
description: Obtenga información sobre las vulnerabilidades de software encontradas en los dispositivos y la lista de actualizaciones de seguridad disponibles que abordan cada vulnerabilidad en la tabla DeviceTvmSoftwareVulnerabilities del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, amenaza & administración de vulnerabilidades, TVM, administración de dispositivos, software, inventario, vulnerabilidades, IDENTIFICADOR CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 17faffc45cfd1f472dec3f423681aaa3f64944a3
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023814"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="ec8fb-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="ec8fb-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ec8fb-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ec8fb-105">**Applies to:**</span></span>
- <span data-ttu-id="ec8fb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec8fb-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="ec8fb-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ec8fb-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="ec8fb-108">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="ec8fb-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ec8fb-109">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="ec8fb-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ec8fb-110">La tabla del esquema de búsqueda avanzada contiene la lista de & de vulnerabilidades de los productos `DeviceTvmSoftwareVulnerabilities` de software [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) instalados.</span><span class="sxs-lookup"><span data-stu-id="ec8fb-110">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="ec8fb-111">Esta tabla también incluye información sobre el sistema operativo, IDs de CVE e información sobre la gravedad de la vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="ec8fb-111">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="ec8fb-112">Puedes usar esta tabla, por ejemplo, para buscar eventos que impliquen dispositivos con vulnerabilidades graves en su software.</span><span class="sxs-lookup"><span data-stu-id="ec8fb-112">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="ec8fb-113">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ec8fb-113">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="ec8fb-114">Las `DeviceTvmSoftwareInventory` tablas y han reemplazado a la `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabla.</span><span class="sxs-lookup"><span data-stu-id="ec8fb-114">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="ec8fb-115">Juntos, las dos primeras tablas incluyen más columnas que puedes usar para ayudar a informar a tus actividades de administración de vulnerablidad o buscar dispositivos vulnerables.</span><span class="sxs-lookup"><span data-stu-id="ec8fb-115">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="ec8fb-116">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ec8fb-116">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ec8fb-117">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="ec8fb-117">Column name</span></span> | <span data-ttu-id="ec8fb-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec8fb-118">Data type</span></span> | <span data-ttu-id="ec8fb-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec8fb-119">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="ec8fb-120">string</span><span class="sxs-lookup"><span data-stu-id="ec8fb-120">string</span></span> | <span data-ttu-id="ec8fb-121">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="ec8fb-121">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ec8fb-122">cadena</span><span class="sxs-lookup"><span data-stu-id="ec8fb-122">string</span></span> | <span data-ttu-id="ec8fb-123">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="ec8fb-123">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="ec8fb-124">cadena</span><span class="sxs-lookup"><span data-stu-id="ec8fb-124">string</span></span> | <span data-ttu-id="ec8fb-125">Plataforma del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ec8fb-125">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="ec8fb-126">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="ec8fb-126">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="ec8fb-127">cadena</span><span class="sxs-lookup"><span data-stu-id="ec8fb-127">string</span></span> | <span data-ttu-id="ec8fb-128">Versión del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ec8fb-128">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="ec8fb-129">cadena</span><span class="sxs-lookup"><span data-stu-id="ec8fb-129">string</span></span> | <span data-ttu-id="ec8fb-130">Arquitectura del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ec8fb-130">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="ec8fb-131">cadena</span><span class="sxs-lookup"><span data-stu-id="ec8fb-131">string</span></span> | <span data-ttu-id="ec8fb-132">Nombre del proveedor de software</span><span class="sxs-lookup"><span data-stu-id="ec8fb-132">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="ec8fb-133">cadena</span><span class="sxs-lookup"><span data-stu-id="ec8fb-133">string</span></span> | <span data-ttu-id="ec8fb-134">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="ec8fb-134">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="ec8fb-135">cadena</span><span class="sxs-lookup"><span data-stu-id="ec8fb-135">string</span></span> | <span data-ttu-id="ec8fb-136">Número de versión del producto de software</span><span class="sxs-lookup"><span data-stu-id="ec8fb-136">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="ec8fb-137">cadena</span><span class="sxs-lookup"><span data-stu-id="ec8fb-137">string</span></span> | <span data-ttu-id="ec8fb-138">Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE)</span><span class="sxs-lookup"><span data-stu-id="ec8fb-138">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="ec8fb-139">cadena</span><span class="sxs-lookup"><span data-stu-id="ec8fb-139">string</span></span> | <span data-ttu-id="ec8fb-140">Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas</span><span class="sxs-lookup"><span data-stu-id="ec8fb-140">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="ec8fb-141">cadena</span><span class="sxs-lookup"><span data-stu-id="ec8fb-141">string</span></span> | <span data-ttu-id="ec8fb-142">Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="ec8fb-142">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="ec8fb-143">cadena</span><span class="sxs-lookup"><span data-stu-id="ec8fb-143">string</span></span> | <span data-ttu-id="ec8fb-144">Identificador de las actualizaciones de seguridad o el identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes</span><span class="sxs-lookup"><span data-stu-id="ec8fb-144">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="ec8fb-145">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ec8fb-145">Related topics</span></span>

- [<span data-ttu-id="ec8fb-146">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="ec8fb-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ec8fb-147">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="ec8fb-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ec8fb-148">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="ec8fb-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ec8fb-149">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="ec8fb-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ec8fb-150">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="ec8fb-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ec8fb-151">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="ec8fb-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ec8fb-152">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="ec8fb-152">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)