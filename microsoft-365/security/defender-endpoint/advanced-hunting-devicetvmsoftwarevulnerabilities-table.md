---
title: Tabla DeviceTvmSoftwareVulnerabilities en el esquema de búsqueda avanzada
description: Obtenga información sobre las vulnerabilidades de software encontradas en los dispositivos y la lista de actualizaciones de seguridad disponibles que abordan cada vulnerabilidad en la tabla DeviceTvmSoftwareVulnerabilities del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de & de amenazas, TVM, administración de dispositivos, software, inventario, vulnerabilidades, IDENTIFICADOR CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076035"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="d5319-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="d5319-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d5319-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d5319-105">**Applies to:**</span></span>
- [<span data-ttu-id="d5319-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d5319-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="d5319-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d5319-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d5319-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d5319-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="d5319-109">La tabla del esquema de búsqueda avanzada contiene la lista de & de vulnerabilidades de los productos `DeviceTvmSoftwareVulnerabilities` de software [](next-gen-threat-and-vuln-mgt.md) instalados.</span><span class="sxs-lookup"><span data-stu-id="d5319-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="d5319-110">Esta tabla también incluye información sobre el sistema operativo, IDs de CVE e información sobre la gravedad de la vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="d5319-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="d5319-111">Puedes usar esta tabla, por ejemplo, para buscar eventos que impliquen dispositivos con vulnerabilidades graves en su software.</span><span class="sxs-lookup"><span data-stu-id="d5319-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="d5319-112">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="d5319-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="d5319-113">Las `DeviceTvmSoftwareInventory` tablas y han reemplazado a la `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabla.</span><span class="sxs-lookup"><span data-stu-id="d5319-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="d5319-114">Juntos, las dos primeras tablas incluyen más columnas que puede usar para ayudar a informar sobre las actividades de administración de vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="d5319-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="d5319-115">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="d5319-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="d5319-116">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="d5319-116">Column name</span></span> | <span data-ttu-id="d5319-117">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d5319-117">Data type</span></span> | <span data-ttu-id="d5319-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5319-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="d5319-119">string</span><span class="sxs-lookup"><span data-stu-id="d5319-119">string</span></span> | <span data-ttu-id="d5319-120">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="d5319-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d5319-121">string</span><span class="sxs-lookup"><span data-stu-id="d5319-121">string</span></span> | <span data-ttu-id="d5319-122">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="d5319-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="d5319-123">string</span><span class="sxs-lookup"><span data-stu-id="d5319-123">string</span></span> | <span data-ttu-id="d5319-124">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5319-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="d5319-125">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d5319-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="d5319-126">cadena</span><span class="sxs-lookup"><span data-stu-id="d5319-126">string</span></span> | <span data-ttu-id="d5319-127">Versión del sistema operativo que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="d5319-127">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="d5319-128">string</span><span class="sxs-lookup"><span data-stu-id="d5319-128">string</span></span> | <span data-ttu-id="d5319-129">Arquitectura del sistema operativo que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="d5319-129">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="d5319-130">string</span><span class="sxs-lookup"><span data-stu-id="d5319-130">string</span></span> | <span data-ttu-id="d5319-131">Nombre del proveedor de software</span><span class="sxs-lookup"><span data-stu-id="d5319-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="d5319-132">cadena</span><span class="sxs-lookup"><span data-stu-id="d5319-132">string</span></span> | <span data-ttu-id="d5319-133">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="d5319-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="d5319-134">cadena</span><span class="sxs-lookup"><span data-stu-id="d5319-134">string</span></span> | <span data-ttu-id="d5319-135">Número de versión del producto de software</span><span class="sxs-lookup"><span data-stu-id="d5319-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="d5319-136">cadena</span><span class="sxs-lookup"><span data-stu-id="d5319-136">string</span></span> | <span data-ttu-id="d5319-137">Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE)</span><span class="sxs-lookup"><span data-stu-id="d5319-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="d5319-138">string</span><span class="sxs-lookup"><span data-stu-id="d5319-138">string</span></span> | <span data-ttu-id="d5319-139">Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas</span><span class="sxs-lookup"><span data-stu-id="d5319-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="d5319-140">cadena</span><span class="sxs-lookup"><span data-stu-id="d5319-140">string</span></span> | <span data-ttu-id="d5319-141">Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="d5319-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="d5319-142">string</span><span class="sxs-lookup"><span data-stu-id="d5319-142">string</span></span> | <span data-ttu-id="d5319-143">Identificador de las actualizaciones de seguridad o el identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes</span><span class="sxs-lookup"><span data-stu-id="d5319-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="d5319-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d5319-144">Related topics</span></span>

- [<span data-ttu-id="d5319-145">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="d5319-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d5319-146">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="d5319-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d5319-147">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="d5319-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="d5319-148">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="d5319-148">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
