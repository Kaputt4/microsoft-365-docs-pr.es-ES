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
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408628"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="ada28-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="ada28-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ada28-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ada28-105">**Applies to:**</span></span>
- [<span data-ttu-id="ada28-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ada28-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="ada28-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ada28-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ada28-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="ada28-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ada28-109">La tabla del esquema de búsqueda avanzada contiene el inventario de administración de amenazas y vulnerabilidades del software instalado actualmente en dispositivos de la red, incluida la información de fin `DeviceTvmSoftwareInventory` de soporte técnico. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="ada28-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="ada28-110">Por ejemplo, puede buscar eventos que impliquen dispositivos instalados con una versión de software vulnerable actualmente.</span><span class="sxs-lookup"><span data-stu-id="ada28-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="ada28-111">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ada28-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="ada28-112">DeviceTVMSoftwareInventory contiene todo el software que la administración de amenazas y vulnerabilidades pudo hacer coincidir con una enumeración de plataforma común (CPE), independientemente de si es vulnerable o no.</span><span class="sxs-lookup"><span data-stu-id="ada28-112">DeviceTVMSoftwareInventory contains all the software which threat and vulnerability management was able to match to a Common Platform Enumeration (CPE) – whether it is vulnerable or not.</span></span>

>[!NOTE]
><span data-ttu-id="ada28-113">Las `DeviceTvmSoftwareInventory` tablas y han reemplazado a la `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabla.</span><span class="sxs-lookup"><span data-stu-id="ada28-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="ada28-114">Juntos, las dos primeras tablas incluyen más columnas que puede usar para ayudar a informar sobre las actividades de administración de vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="ada28-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="ada28-115">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="ada28-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="ada28-116">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="ada28-116">Column name</span></span> | <span data-ttu-id="ada28-117">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ada28-117">Data type</span></span> | <span data-ttu-id="ada28-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="ada28-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="ada28-119">string</span><span class="sxs-lookup"><span data-stu-id="ada28-119">string</span></span> | <span data-ttu-id="ada28-120">Identificador único del dispositivo en el servicio.</span><span class="sxs-lookup"><span data-stu-id="ada28-120">Unique identifier for the device in the service.</span></span> |
| `DeviceName` | <span data-ttu-id="ada28-121">cadena</span><span class="sxs-lookup"><span data-stu-id="ada28-121">string</span></span> | <span data-ttu-id="ada28-122">Nombre de dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ada28-122">Fully qualified domain name (FQDN) of the device.</span></span> |
| `OSPlatform` | <span data-ttu-id="ada28-123">cadena</span><span class="sxs-lookup"><span data-stu-id="ada28-123">string</span></span> | <span data-ttu-id="ada28-124">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ada28-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="ada28-125">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="ada28-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="ada28-126">cadena</span><span class="sxs-lookup"><span data-stu-id="ada28-126">string</span></span> | <span data-ttu-id="ada28-127">Versión del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ada28-127">Version of the operating system running on the device.</span></span> |
| `OSArchitecture` | <span data-ttu-id="ada28-128">cadena</span><span class="sxs-lookup"><span data-stu-id="ada28-128">string</span></span> | <span data-ttu-id="ada28-129">Arquitectura del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ada28-129">Architecture of the operating system running on the device.</span></span> |
| `SoftwareVendor` | <span data-ttu-id="ada28-130">cadena</span><span class="sxs-lookup"><span data-stu-id="ada28-130">string</span></span> | <span data-ttu-id="ada28-131">Nombre del proveedor de software.</span><span class="sxs-lookup"><span data-stu-id="ada28-131">Name of the software vendor.</span></span> |
| `SoftwareName` | <span data-ttu-id="ada28-132">cadena</span><span class="sxs-lookup"><span data-stu-id="ada28-132">string</span></span> | <span data-ttu-id="ada28-133">Nombre del producto de software.</span><span class="sxs-lookup"><span data-stu-id="ada28-133">Name of the software product.</span></span> |
| `SoftwareVersion` | <span data-ttu-id="ada28-134">cadena</span><span class="sxs-lookup"><span data-stu-id="ada28-134">string</span></span> | <span data-ttu-id="ada28-135">Número de versión del producto de software.</span><span class="sxs-lookup"><span data-stu-id="ada28-135">Version number of the software product.</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="ada28-136">cadena</span><span class="sxs-lookup"><span data-stu-id="ada28-136">string</span></span> | <span data-ttu-id="ada28-137">Indica la fase de ciclo de vida del producto de software en relación con la fecha de fin de soporte técnico (EOS) o de fin de vida (EOL) especificada.</span><span class="sxs-lookup"><span data-stu-id="ada28-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date.</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="ada28-138">cadena</span><span class="sxs-lookup"><span data-stu-id="ada28-138">string</span></span> | <span data-ttu-id="ada28-139">Fecha de fin de soporte técnico (EOS) o de fin de vida (EOL) del producto de software.</span><span class="sxs-lookup"><span data-stu-id="ada28-139">End-of-support (EOS) or end-of-life (EOL) date of the software product.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ada28-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ada28-140">Related topics</span></span>

- [<span data-ttu-id="ada28-141">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="ada28-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ada28-142">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="ada28-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ada28-143">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="ada28-143">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="ada28-144">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="ada28-144">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
