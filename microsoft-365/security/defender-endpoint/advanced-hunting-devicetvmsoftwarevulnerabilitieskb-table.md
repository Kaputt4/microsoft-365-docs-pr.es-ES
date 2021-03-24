---
title: Tabla DeviceTvmSoftwareVulnerabilitiesKB en el esquema de búsqueda avanzada
description: Obtenga más información sobre las vulnerabilidades de software controladas por la administración de amenazas y vulnerabilidades en la tabla DeviceTvmSoftwareVulnerabilitiesKB del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de & de amenazas, TVM, administración de dispositivos, software, inventario, vulnerabilidades, IDENTIFICADOR CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070923"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="bc9cd-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="bc9cd-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bc9cd-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bc9cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="bc9cd-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bc9cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="bc9cd-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="bc9cd-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bc9cd-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="bc9cd-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="bc9cd-109">La tabla `DeviceTvmSoftwareVulnerabilitiesKB` en el esquema de búsqueda avanzada contiene la lista de vulnerabilidades de la [administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md) que evalúan los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bc9cd-109">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) assesses devices for.</span></span> <span data-ttu-id="bc9cd-110">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="bc9cd-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="bc9cd-111">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="bc9cd-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="bc9cd-112">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="bc9cd-112">Column name</span></span> | <span data-ttu-id="bc9cd-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="bc9cd-113">Data type</span></span> | <span data-ttu-id="bc9cd-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc9cd-114">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="bc9cd-115">string</span><span class="sxs-lookup"><span data-stu-id="bc9cd-115">string</span></span> | <span data-ttu-id="bc9cd-116">Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE)</span><span class="sxs-lookup"><span data-stu-id="bc9cd-116">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="bc9cd-117">string</span><span class="sxs-lookup"><span data-stu-id="bc9cd-117">string</span></span> | <span data-ttu-id="bc9cd-118">La puntuación de gravedad asignada a la vulnerabilidad de seguridad por debajo de sistema de puntuación de vulnerabilidades común (CVSS)</span><span class="sxs-lookup"><span data-stu-id="bc9cd-118">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="bc9cd-119">boolean</span><span class="sxs-lookup"><span data-stu-id="bc9cd-119">boolean</span></span> | <span data-ttu-id="bc9cd-120">Indica si el código que aprovecha la vulnerabilidad está disponible para el público</span><span class="sxs-lookup"><span data-stu-id="bc9cd-120">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="bc9cd-121">string</span><span class="sxs-lookup"><span data-stu-id="bc9cd-121">string</span></span> | <span data-ttu-id="bc9cd-122">Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas</span><span class="sxs-lookup"><span data-stu-id="bc9cd-122">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="bc9cd-123">datetime</span><span class="sxs-lookup"><span data-stu-id="bc9cd-123">datetime</span></span> | <span data-ttu-id="bc9cd-124">Fecha y hora en que se modificó por última vez el elemento o los metadatos relacionados</span><span class="sxs-lookup"><span data-stu-id="bc9cd-124">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="bc9cd-125">datetime</span><span class="sxs-lookup"><span data-stu-id="bc9cd-125">datetime</span></span> | <span data-ttu-id="bc9cd-126">Fecha en que se ha divulgado la vulnerabilidad al público</span><span class="sxs-lookup"><span data-stu-id="bc9cd-126">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="bc9cd-127">string</span><span class="sxs-lookup"><span data-stu-id="bc9cd-127">string</span></span> | <span data-ttu-id="bc9cd-128">Descripción de vulnerabilidad y riesgos asociados</span><span class="sxs-lookup"><span data-stu-id="bc9cd-128">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="bc9cd-129">string</span><span class="sxs-lookup"><span data-stu-id="bc9cd-129">string</span></span> | <span data-ttu-id="bc9cd-130">Lista de todos los productos de software afectados por la vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="bc9cd-130">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="bc9cd-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bc9cd-131">Related topics</span></span>

- [<span data-ttu-id="bc9cd-132">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="bc9cd-132">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bc9cd-133">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="bc9cd-133">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bc9cd-134">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="bc9cd-134">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="bc9cd-135">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="bc9cd-135">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
