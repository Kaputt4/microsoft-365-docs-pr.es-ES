---
title: Tabla DeviceTvmSoftwareVulnerabilitiesKB en el esquema de búsqueda avanzada
description: Obtenga más información sobre las vulnerabilidades de software controladas por la administración de amenazas y vulnerabilidades en la tabla DeviceTvmSoftwareVulnerabilitiesKB del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, esquema, referencia, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de & amenazas, TVM, administración de dispositivos, software, inventario, vulnerabilidades, IDENTIFICADOR CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 4b7447bce3d1859f71cd1f3f7ea100b9978641c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907245"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="63be8-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="63be8-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="63be8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="63be8-105">**Applies to:**</span></span>
- <span data-ttu-id="63be8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63be8-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="63be8-107">La tabla `DeviceTvmSoftwareVulnerabilitiesKB` en el esquema de búsqueda avanzada contiene la lista de vulnerabilidades de la [administración de amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) que evalúan los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="63be8-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="63be8-108">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="63be8-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="63be8-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="63be8-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="63be8-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="63be8-110">Column name</span></span> | <span data-ttu-id="63be8-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="63be8-111">Data type</span></span> | <span data-ttu-id="63be8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="63be8-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="63be8-113">string</span><span class="sxs-lookup"><span data-stu-id="63be8-113">string</span></span> | <span data-ttu-id="63be8-114">Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE)</span><span class="sxs-lookup"><span data-stu-id="63be8-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="63be8-115">string</span><span class="sxs-lookup"><span data-stu-id="63be8-115">string</span></span> | <span data-ttu-id="63be8-116">La puntuación de gravedad asignada a la vulnerabilidad de seguridad por debajo de sistema de puntuación de vulnerabilidades común (CVSS)</span><span class="sxs-lookup"><span data-stu-id="63be8-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="63be8-117">boolean</span><span class="sxs-lookup"><span data-stu-id="63be8-117">boolean</span></span> | <span data-ttu-id="63be8-118">Indica si el código que aprovecha la vulnerabilidad está disponible para el público</span><span class="sxs-lookup"><span data-stu-id="63be8-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="63be8-119">string</span><span class="sxs-lookup"><span data-stu-id="63be8-119">string</span></span> | <span data-ttu-id="63be8-120">Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas</span><span class="sxs-lookup"><span data-stu-id="63be8-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="63be8-121">datetime</span><span class="sxs-lookup"><span data-stu-id="63be8-121">datetime</span></span> | <span data-ttu-id="63be8-122">Fecha y hora en que se modificó por última vez el elemento o los metadatos relacionados</span><span class="sxs-lookup"><span data-stu-id="63be8-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="63be8-123">datetime</span><span class="sxs-lookup"><span data-stu-id="63be8-123">datetime</span></span> | <span data-ttu-id="63be8-124">Fecha en que se ha divulgado la vulnerabilidad al público</span><span class="sxs-lookup"><span data-stu-id="63be8-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="63be8-125">string</span><span class="sxs-lookup"><span data-stu-id="63be8-125">string</span></span> | <span data-ttu-id="63be8-126">Descripción de vulnerabilidad y riesgos asociados</span><span class="sxs-lookup"><span data-stu-id="63be8-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="63be8-127">string</span><span class="sxs-lookup"><span data-stu-id="63be8-127">string</span></span> | <span data-ttu-id="63be8-128">Lista de todos los productos de software afectados por la vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="63be8-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="63be8-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="63be8-129">Related topics</span></span>

- [<span data-ttu-id="63be8-130">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="63be8-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="63be8-131">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="63be8-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="63be8-132">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="63be8-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="63be8-133">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="63be8-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="63be8-134">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="63be8-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="63be8-135">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="63be8-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="63be8-136">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="63be8-136">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)