---
title: Tabla DeviceTvmSoftwareInventory en el esquema de búsqueda avanzada
description: Obtenga información sobre el inventario de software en sus dispositivos en la tabla DeviceTvmSoftwareInventory del esquema de búsqueda avanzado.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de & amenazas, TVM, administración de dispositivos, software, inventario, vulnerabilidades, IDENTIFICADOR CVE, Id. de dispositivo CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: cf899dc52450d2cab47eb0207eef46ac83eb01e3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071491"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="69037-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="69037-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="69037-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="69037-105">**Applies to:**</span></span>
- <span data-ttu-id="69037-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69037-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="69037-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="69037-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="69037-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="69037-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="69037-109">La tabla del esquema de búsqueda avanzada contiene el inventario de administración de vulnerabilidades & amenazas del software instalado actualmente en dispositivos de la red, incluida la información de fin `DeviceTvmSoftwareInventory` de soporte técnico. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="69037-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="69037-110">Por ejemplo, puede buscar eventos que impliquen dispositivos instalados con una versión de software vulnerable actualmente.</span><span class="sxs-lookup"><span data-stu-id="69037-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="69037-111">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="69037-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="69037-112">Las `DeviceTvmSoftwareInventory` tablas y han reemplazado a la `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabla.</span><span class="sxs-lookup"><span data-stu-id="69037-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="69037-113">Juntos, las dos primeras tablas incluyen más columnas que puedes usar para ayudar a informar a tus actividades de administración de vulnerablidad o buscar dispositivos vulnerables.</span><span class="sxs-lookup"><span data-stu-id="69037-113">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="69037-114">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="69037-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="69037-115">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="69037-115">Column name</span></span> | <span data-ttu-id="69037-116">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="69037-116">Data type</span></span> | <span data-ttu-id="69037-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="69037-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="69037-118">string</span><span class="sxs-lookup"><span data-stu-id="69037-118">string</span></span> | <span data-ttu-id="69037-119">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="69037-119">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="69037-120">cadena</span><span class="sxs-lookup"><span data-stu-id="69037-120">string</span></span> | <span data-ttu-id="69037-121">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="69037-121">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="69037-122">cadena</span><span class="sxs-lookup"><span data-stu-id="69037-122">string</span></span> | <span data-ttu-id="69037-123">Plataforma del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="69037-123">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="69037-124">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="69037-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="69037-125">cadena</span><span class="sxs-lookup"><span data-stu-id="69037-125">string</span></span> | <span data-ttu-id="69037-126">Versión del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="69037-126">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="69037-127">cadena</span><span class="sxs-lookup"><span data-stu-id="69037-127">string</span></span> | <span data-ttu-id="69037-128">Arquitectura del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="69037-128">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="69037-129">cadena</span><span class="sxs-lookup"><span data-stu-id="69037-129">string</span></span> | <span data-ttu-id="69037-130">Nombre del proveedor de software</span><span class="sxs-lookup"><span data-stu-id="69037-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="69037-131">cadena</span><span class="sxs-lookup"><span data-stu-id="69037-131">string</span></span> | <span data-ttu-id="69037-132">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="69037-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="69037-133">cadena</span><span class="sxs-lookup"><span data-stu-id="69037-133">string</span></span> | <span data-ttu-id="69037-134">Número de versión del producto de software</span><span class="sxs-lookup"><span data-stu-id="69037-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="69037-135">cadena</span><span class="sxs-lookup"><span data-stu-id="69037-135">string</span></span> | <span data-ttu-id="69037-136">Indica la fase de ciclo de vida del producto de software en relación con la fecha de fin de soporte técnico (EOS) o de fin de vida (EOL) especificada</span><span class="sxs-lookup"><span data-stu-id="69037-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="69037-137">string</span><span class="sxs-lookup"><span data-stu-id="69037-137">string</span></span> | <span data-ttu-id="69037-138">Fecha de fin de soporte técnico (EOS) o de fin de vida (EOL) del producto de software</span><span class="sxs-lookup"><span data-stu-id="69037-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="69037-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="69037-139">Related topics</span></span>

- [<span data-ttu-id="69037-140">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="69037-140">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="69037-141">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="69037-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="69037-142">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="69037-142">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="69037-143">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="69037-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="69037-144">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="69037-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="69037-145">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="69037-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="69037-146">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="69037-146">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)