---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de evaluación de seguridad en la tabla DeviceTvmSecureConfigurationAssessment del esquema de búsqueda avanzada. Estas amenazas & eventos de administración de vulnerabilidad proporcionan información de dispositivos, así como detalles de configuración de seguridad, impacto e información de cumplimiento.
keywords: búsqueda avanzada, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, amenaza & la administración de vulnerabilidades, TVM, administración de dispositivos, configuración de seguridad, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: bfe63397d194567a7d71de703363083d2fd4fe75
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847613"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="c2847-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="c2847-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c2847-106">**Aplica para:**</span><span class="sxs-lookup"><span data-stu-id="c2847-106">**Applies to:**</span></span>
- <span data-ttu-id="c2847-107">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="c2847-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="c2847-108">Cada una de las filas de la tabla `DeviceTvmSecureConfigurationAssessment`contiene un evento de evaluación para una configuración de seguridad específica de la administración de [amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="c2847-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="c2847-109">Utilice esta referencia para comprobar los últimos resultados de la evaluación y determinar si los dispositivos son compatibles.</span><span class="sxs-lookup"><span data-stu-id="c2847-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="c2847-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c2847-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c2847-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="c2847-111">Column name</span></span> | <span data-ttu-id="c2847-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c2847-112">Data type</span></span> | <span data-ttu-id="c2847-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2847-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="c2847-114">string</span><span class="sxs-lookup"><span data-stu-id="c2847-114">string</span></span> | <span data-ttu-id="c2847-115">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="c2847-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c2847-116">string</span><span class="sxs-lookup"><span data-stu-id="c2847-116">string</span></span> | <span data-ttu-id="c2847-117">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="c2847-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="c2847-118">string</span><span class="sxs-lookup"><span data-stu-id="c2847-118">string</span></span> | <span data-ttu-id="c2847-119">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2847-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="c2847-120">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="c2847-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="c2847-121">datetime</span><span class="sxs-lookup"><span data-stu-id="c2847-121">datetime</span></span> | <span data-ttu-id="c2847-122">Fecha y hora en que se generó el registro</span><span class="sxs-lookup"><span data-stu-id="c2847-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="c2847-123">cadena</span><span class="sxs-lookup"><span data-stu-id="c2847-123">string</span></span> | <span data-ttu-id="c2847-124">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="c2847-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="c2847-125">string</span><span class="sxs-lookup"><span data-stu-id="c2847-125">string</span></span> | <span data-ttu-id="c2847-126">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="c2847-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="c2847-127">string</span><span class="sxs-lookup"><span data-stu-id="c2847-127">string</span></span> | <span data-ttu-id="c2847-128">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="c2847-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="c2847-129">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="c2847-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="c2847-130">string</span><span class="sxs-lookup"><span data-stu-id="c2847-130">string</span></span> | <span data-ttu-id="c2847-131">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="c2847-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="c2847-132">booleano</span><span class="sxs-lookup"><span data-stu-id="c2847-132">boolean</span></span> | <span data-ttu-id="c2847-133">Indica si la configuración o la directiva está configurada correctamente</span><span class="sxs-lookup"><span data-stu-id="c2847-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="c2847-134">boolean</span><span class="sxs-lookup"><span data-stu-id="c2847-134">boolean</span></span> | <span data-ttu-id="c2847-135">Indica si la configuración o la Directiva se aplican al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2847-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="c2847-136">string</span><span class="sxs-lookup"><span data-stu-id="c2847-136">string</span></span> | <span data-ttu-id="c2847-137">Información contextual adicional acerca de la configuración o la Directiva</span><span class="sxs-lookup"><span data-stu-id="c2847-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="c2847-138">boolean</span><span class="sxs-lookup"><span data-stu-id="c2847-138">boolean</span></span> | <span data-ttu-id="c2847-139">Indica si habrá impacto en el usuario si se aplica la configuración o la Directiva.</span><span class="sxs-lookup"><span data-stu-id="c2847-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c2847-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c2847-140">Related topics</span></span>

- [<span data-ttu-id="c2847-141">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="c2847-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c2847-142">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="c2847-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c2847-143">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="c2847-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c2847-144">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="c2847-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c2847-145">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="c2847-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c2847-146">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="c2847-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c2847-147">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="c2847-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
