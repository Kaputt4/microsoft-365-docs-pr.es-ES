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
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d3b85bcbc2cb65cc434c7af0ba078bd835d8203f
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210502"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="3b811-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="3b811-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

<span data-ttu-id="3b811-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3b811-105">**Applies to:**</span></span>
- <span data-ttu-id="3b811-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b811-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="3b811-107">La tabla `DeviceTvmSoftwareInventoryVulnerabilities` en el esquema de búsqueda avanzada contiene el inventario de software de la [Administración de amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) en sus dispositivos, así como las vulnerabilidades conocidas de estos productos de software.</span><span class="sxs-lookup"><span data-stu-id="3b811-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="3b811-108">Esta tabla también incluye información sobre el sistema operativo, IDs de CVE e información sobre la gravedad de la vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="3b811-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="3b811-109">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3b811-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="3b811-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="3b811-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3b811-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="3b811-111">Column name</span></span> | <span data-ttu-id="3b811-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="3b811-112">Data type</span></span> | <span data-ttu-id="3b811-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b811-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="3b811-114">string</span><span class="sxs-lookup"><span data-stu-id="3b811-114">string</span></span> | <span data-ttu-id="3b811-115">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="3b811-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="3b811-116">cadena</span><span class="sxs-lookup"><span data-stu-id="3b811-116">string</span></span> | <span data-ttu-id="3b811-117">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="3b811-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="3b811-118">cadena</span><span class="sxs-lookup"><span data-stu-id="3b811-118">string</span></span> | <span data-ttu-id="3b811-119">Plataforma del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3b811-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="3b811-120">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="3b811-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="3b811-121">cadena</span><span class="sxs-lookup"><span data-stu-id="3b811-121">string</span></span> | <span data-ttu-id="3b811-122">Versión del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3b811-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="3b811-123">cadena</span><span class="sxs-lookup"><span data-stu-id="3b811-123">string</span></span> | <span data-ttu-id="3b811-124">Arquitectura del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3b811-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="3b811-125">cadena</span><span class="sxs-lookup"><span data-stu-id="3b811-125">string</span></span> | <span data-ttu-id="3b811-126">Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas</span><span class="sxs-lookup"><span data-stu-id="3b811-126">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `SoftwareName` | <span data-ttu-id="3b811-127">cadena</span><span class="sxs-lookup"><span data-stu-id="3b811-127">string</span></span> | <span data-ttu-id="3b811-128">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="3b811-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="3b811-129">cadena</span><span class="sxs-lookup"><span data-stu-id="3b811-129">string</span></span> | <span data-ttu-id="3b811-130">Número de versión del producto de software</span><span class="sxs-lookup"><span data-stu-id="3b811-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="3b811-131">cadena</span><span class="sxs-lookup"><span data-stu-id="3b811-131">string</span></span> | <span data-ttu-id="3b811-132">Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE)</span><span class="sxs-lookup"><span data-stu-id="3b811-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="3b811-133">cadena</span><span class="sxs-lookup"><span data-stu-id="3b811-133">string</span></span> | <span data-ttu-id="3b811-134">Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas</span><span class="sxs-lookup"><span data-stu-id="3b811-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="3b811-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3b811-135">Related topics</span></span>

- [<span data-ttu-id="3b811-136">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="3b811-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3b811-137">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="3b811-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3b811-138">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="3b811-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3b811-139">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3b811-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3b811-140">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="3b811-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3b811-141">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="3b811-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="3b811-142">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="3b811-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
