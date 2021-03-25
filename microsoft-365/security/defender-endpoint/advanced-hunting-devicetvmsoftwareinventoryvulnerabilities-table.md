---
title: Tabla DeviceTvmSoftwareInventoryVulnerabilities en el esquema de búsqueda avanzada
description: Obtenga más información sobre el inventario de software en sus dispositivos y sus vulnerabilidades en la tabla DeviceTvmSoftwareInventoryVulnerabilities del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de & de amenazas, TVM, administración de dispositivos, software, inventario, vulnerabilidades, IDENTIFICADOR CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163464"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="a0b69-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="a0b69-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a0b69-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a0b69-105">**Applies to:**</span></span>

- [<span data-ttu-id="a0b69-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a0b69-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="a0b69-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a0b69-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a0b69-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="a0b69-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a0b69-109">La tabla `DeviceTvmSoftwareInventoryVulnerabilities` en el esquema de búsqueda avanzada contiene el inventario de software de la [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md) en sus dispositivos, así como las vulnerabilidades conocidas de estos productos de software.</span><span class="sxs-lookup"><span data-stu-id="a0b69-109">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="a0b69-110">Esta tabla también incluye información sobre el sistema operativo, IDs de CVE e información sobre la gravedad de la vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="a0b69-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="a0b69-111">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a0b69-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="a0b69-112">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="a0b69-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="a0b69-113">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="a0b69-113">Column name</span></span> | <span data-ttu-id="a0b69-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a0b69-114">Data type</span></span> | <span data-ttu-id="a0b69-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0b69-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="a0b69-116">string</span><span class="sxs-lookup"><span data-stu-id="a0b69-116">string</span></span> | <span data-ttu-id="a0b69-117">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="a0b69-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a0b69-118">string</span><span class="sxs-lookup"><span data-stu-id="a0b69-118">string</span></span> | <span data-ttu-id="a0b69-119">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="a0b69-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="a0b69-120">string</span><span class="sxs-lookup"><span data-stu-id="a0b69-120">string</span></span> | <span data-ttu-id="a0b69-121">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a0b69-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="a0b69-122">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="a0b69-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="a0b69-123">cadena</span><span class="sxs-lookup"><span data-stu-id="a0b69-123">string</span></span> | <span data-ttu-id="a0b69-124">Versión del sistema operativo que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="a0b69-124">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="a0b69-125">string</span><span class="sxs-lookup"><span data-stu-id="a0b69-125">string</span></span> | <span data-ttu-id="a0b69-126">Arquitectura del sistema operativo que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="a0b69-126">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="a0b69-127">string</span><span class="sxs-lookup"><span data-stu-id="a0b69-127">string</span></span> | <span data-ttu-id="a0b69-128">Nombre del proveedor de software</span><span class="sxs-lookup"><span data-stu-id="a0b69-128">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="a0b69-129">cadena</span><span class="sxs-lookup"><span data-stu-id="a0b69-129">string</span></span> | <span data-ttu-id="a0b69-130">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="a0b69-130">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="a0b69-131">cadena</span><span class="sxs-lookup"><span data-stu-id="a0b69-131">string</span></span> | <span data-ttu-id="a0b69-132">Número de versión del producto de software</span><span class="sxs-lookup"><span data-stu-id="a0b69-132">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="a0b69-133">cadena</span><span class="sxs-lookup"><span data-stu-id="a0b69-133">string</span></span> | <span data-ttu-id="a0b69-134">Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE)</span><span class="sxs-lookup"><span data-stu-id="a0b69-134">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="a0b69-135">string</span><span class="sxs-lookup"><span data-stu-id="a0b69-135">string</span></span> | <span data-ttu-id="a0b69-136">Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas</span><span class="sxs-lookup"><span data-stu-id="a0b69-136">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="a0b69-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a0b69-137">Related topics</span></span>

- [<span data-ttu-id="a0b69-138">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="a0b69-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a0b69-139">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="a0b69-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a0b69-140">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="a0b69-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="a0b69-141">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="a0b69-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
