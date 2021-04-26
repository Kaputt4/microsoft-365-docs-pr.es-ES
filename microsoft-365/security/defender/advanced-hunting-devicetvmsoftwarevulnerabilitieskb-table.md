---
title: Tabla DeviceTvmSoftwareVulnerabilitiesKB en el esquema de búsqueda avanzada
description: Obtenga más información sobre las vulnerabilidades de software controladas por la administración de amenazas y vulnerabilidades en la tabla DeviceTvmSoftwareVulnerabilitiesKB del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, esquema, referencia, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de &, TVM, administración de dispositivos, software, inventario, vulnerabilidades, IDENTIFICADOR CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023802"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="d7a0b-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="d7a0b-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d7a0b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d7a0b-105">**Applies to:**</span></span>
- <span data-ttu-id="d7a0b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7a0b-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="d7a0b-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d7a0b-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="d7a0b-108">La tabla `DeviceTvmSoftwareVulnerabilitiesKB` en el esquema de búsqueda avanzada contiene la lista de vulnerabilidades de la [administración de amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) que evalúan los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d7a0b-108">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="d7a0b-109">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="d7a0b-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d7a0b-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d7a0b-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d7a0b-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="d7a0b-111">Column name</span></span> | <span data-ttu-id="d7a0b-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d7a0b-112">Data type</span></span> | <span data-ttu-id="d7a0b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7a0b-113">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="d7a0b-114">string</span><span class="sxs-lookup"><span data-stu-id="d7a0b-114">string</span></span> | <span data-ttu-id="d7a0b-115">Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE)</span><span class="sxs-lookup"><span data-stu-id="d7a0b-115">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="d7a0b-116">string</span><span class="sxs-lookup"><span data-stu-id="d7a0b-116">string</span></span> | <span data-ttu-id="d7a0b-117">La puntuación de gravedad asignada a la vulnerabilidad de seguridad por debajo de sistema de puntuación de vulnerabilidades común (CVSS)</span><span class="sxs-lookup"><span data-stu-id="d7a0b-117">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="d7a0b-118">boolean</span><span class="sxs-lookup"><span data-stu-id="d7a0b-118">boolean</span></span> | <span data-ttu-id="d7a0b-119">Indica si el código que aprovecha la vulnerabilidad está disponible para el público</span><span class="sxs-lookup"><span data-stu-id="d7a0b-119">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="d7a0b-120">string</span><span class="sxs-lookup"><span data-stu-id="d7a0b-120">string</span></span> | <span data-ttu-id="d7a0b-121">Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas</span><span class="sxs-lookup"><span data-stu-id="d7a0b-121">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="d7a0b-122">datetime</span><span class="sxs-lookup"><span data-stu-id="d7a0b-122">datetime</span></span> | <span data-ttu-id="d7a0b-123">Fecha y hora en que se modificó por última vez el elemento o los metadatos relacionados</span><span class="sxs-lookup"><span data-stu-id="d7a0b-123">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="d7a0b-124">datetime</span><span class="sxs-lookup"><span data-stu-id="d7a0b-124">datetime</span></span> | <span data-ttu-id="d7a0b-125">Fecha en que se ha divulgado la vulnerabilidad al público</span><span class="sxs-lookup"><span data-stu-id="d7a0b-125">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="d7a0b-126">string</span><span class="sxs-lookup"><span data-stu-id="d7a0b-126">string</span></span> | <span data-ttu-id="d7a0b-127">Descripción de vulnerabilidad y riesgos asociados</span><span class="sxs-lookup"><span data-stu-id="d7a0b-127">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="d7a0b-128">string</span><span class="sxs-lookup"><span data-stu-id="d7a0b-128">string</span></span> | <span data-ttu-id="d7a0b-129">Lista de todos los productos de software afectados por la vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="d7a0b-129">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d7a0b-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d7a0b-130">Related topics</span></span>

- [<span data-ttu-id="d7a0b-131">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="d7a0b-131">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d7a0b-132">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="d7a0b-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d7a0b-133">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="d7a0b-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d7a0b-134">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="d7a0b-134">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d7a0b-135">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="d7a0b-135">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d7a0b-136">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="d7a0b-136">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d7a0b-137">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="d7a0b-137">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)