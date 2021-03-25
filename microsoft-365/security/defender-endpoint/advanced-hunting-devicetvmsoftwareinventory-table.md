---
title: Tabla DeviceTvmSoftwareInventory en el esquema de búsqueda avanzada
description: Obtenga información sobre el inventario de software en sus dispositivos en la tabla DeviceTvmSoftwareInventory del esquema de búsqueda avanzado.
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
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075544"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="e536c-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="e536c-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e536c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e536c-105">**Applies to:**</span></span>
- [<span data-ttu-id="e536c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e536c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="e536c-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e536c-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e536c-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e536c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e536c-109">La tabla del esquema de búsqueda avanzada contiene el inventario de administración de vulnerabilidades & amenazas del software instalado actualmente en dispositivos de la red, incluida la información de fin `DeviceTvmSoftwareInventory` de soporte técnico. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="e536c-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="e536c-110">Por ejemplo, puede buscar eventos que impliquen dispositivos instalados con una versión de software vulnerable actualmente.</span><span class="sxs-lookup"><span data-stu-id="e536c-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="e536c-111">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e536c-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="e536c-112">Las `DeviceTvmSoftwareInventory` tablas y han reemplazado a la `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabla.</span><span class="sxs-lookup"><span data-stu-id="e536c-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="e536c-113">Juntos, las dos primeras tablas incluyen más columnas que puede usar para ayudar a informar sobre las actividades de administración de vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="e536c-113">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="e536c-114">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="e536c-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="e536c-115">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="e536c-115">Column name</span></span> | <span data-ttu-id="e536c-116">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e536c-116">Data type</span></span> | <span data-ttu-id="e536c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="e536c-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="e536c-118">string</span><span class="sxs-lookup"><span data-stu-id="e536c-118">string</span></span> | <span data-ttu-id="e536c-119">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="e536c-119">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e536c-120">string</span><span class="sxs-lookup"><span data-stu-id="e536c-120">string</span></span> | <span data-ttu-id="e536c-121">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="e536c-121">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="e536c-122">string</span><span class="sxs-lookup"><span data-stu-id="e536c-122">string</span></span> | <span data-ttu-id="e536c-123">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e536c-123">Platform of the operating system running on the device.</span></span> <span data-ttu-id="e536c-124">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="e536c-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="e536c-125">cadena</span><span class="sxs-lookup"><span data-stu-id="e536c-125">string</span></span> | <span data-ttu-id="e536c-126">Versión del sistema operativo que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="e536c-126">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="e536c-127">string</span><span class="sxs-lookup"><span data-stu-id="e536c-127">string</span></span> | <span data-ttu-id="e536c-128">Arquitectura del sistema operativo que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="e536c-128">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="e536c-129">string</span><span class="sxs-lookup"><span data-stu-id="e536c-129">string</span></span> | <span data-ttu-id="e536c-130">Nombre del proveedor de software</span><span class="sxs-lookup"><span data-stu-id="e536c-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="e536c-131">cadena</span><span class="sxs-lookup"><span data-stu-id="e536c-131">string</span></span> | <span data-ttu-id="e536c-132">Nombre del producto de software</span><span class="sxs-lookup"><span data-stu-id="e536c-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="e536c-133">cadena</span><span class="sxs-lookup"><span data-stu-id="e536c-133">string</span></span> | <span data-ttu-id="e536c-134">Número de versión del producto de software</span><span class="sxs-lookup"><span data-stu-id="e536c-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="e536c-135">cadena</span><span class="sxs-lookup"><span data-stu-id="e536c-135">string</span></span> | <span data-ttu-id="e536c-136">Indica la fase de ciclo de vida del producto de software en relación con la fecha de fin de soporte técnico (EOS) o de fin de vida (EOL) especificada</span><span class="sxs-lookup"><span data-stu-id="e536c-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="e536c-137">string</span><span class="sxs-lookup"><span data-stu-id="e536c-137">string</span></span> | <span data-ttu-id="e536c-138">Fecha de fin de soporte técnico (EOS) o de fin de vida (EOL) del producto de software</span><span class="sxs-lookup"><span data-stu-id="e536c-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="e536c-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e536c-139">Related topics</span></span>

- [<span data-ttu-id="e536c-140">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="e536c-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e536c-141">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="e536c-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e536c-142">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="e536c-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="e536c-143">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="e536c-143">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

