---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de evaluación de seguridad en la tabla DeviceTvmSecureConfigurationAssessment del esquema de búsqueda avanzado. Estos eventos de & de administración de vulnerabilidades proporcionan información del dispositivo, así como detalles de configuración de seguridad, impacto e información de cumplimiento.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades & amenazas, TVM, administración de dispositivos, configuración de seguridad, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 891bfcc775f8c8ebddea63d5490c1c9fef4e691a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907353"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="a2146-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="a2146-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a2146-106">**Aplica para:**</span><span class="sxs-lookup"><span data-stu-id="a2146-106">**Applies to:**</span></span>
- <span data-ttu-id="a2146-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2146-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="a2146-108">Cada una de las filas de la tabla `DeviceTvmSecureConfigurationAssessment`contiene un evento de evaluación para una configuración de seguridad específica de la administración de [amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="a2146-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="a2146-109">Utilice esta referencia para comprobar los últimos resultados de la evaluación y determinar si los dispositivos son compatibles.</span><span class="sxs-lookup"><span data-stu-id="a2146-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="a2146-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a2146-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a2146-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="a2146-111">Column name</span></span> | <span data-ttu-id="a2146-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a2146-112">Data type</span></span> | <span data-ttu-id="a2146-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2146-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="a2146-114">string</span><span class="sxs-lookup"><span data-stu-id="a2146-114">string</span></span> | <span data-ttu-id="a2146-115">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="a2146-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a2146-116">string</span><span class="sxs-lookup"><span data-stu-id="a2146-116">string</span></span> | <span data-ttu-id="a2146-117">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="a2146-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="a2146-118">string</span><span class="sxs-lookup"><span data-stu-id="a2146-118">string</span></span> | <span data-ttu-id="a2146-119">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a2146-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="a2146-120">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="a2146-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="a2146-121">datetime</span><span class="sxs-lookup"><span data-stu-id="a2146-121">datetime</span></span> | <span data-ttu-id="a2146-122">Fecha y hora en que se generó el registro</span><span class="sxs-lookup"><span data-stu-id="a2146-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="a2146-123">cadena</span><span class="sxs-lookup"><span data-stu-id="a2146-123">string</span></span> | <span data-ttu-id="a2146-124">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="a2146-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="a2146-125">string</span><span class="sxs-lookup"><span data-stu-id="a2146-125">string</span></span> | <span data-ttu-id="a2146-126">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="a2146-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="a2146-127">string</span><span class="sxs-lookup"><span data-stu-id="a2146-127">string</span></span> | <span data-ttu-id="a2146-128">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="a2146-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="a2146-129">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="a2146-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="a2146-130">string</span><span class="sxs-lookup"><span data-stu-id="a2146-130">string</span></span> | <span data-ttu-id="a2146-131">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="a2146-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="a2146-132">booleano</span><span class="sxs-lookup"><span data-stu-id="a2146-132">boolean</span></span> | <span data-ttu-id="a2146-133">Indica si la configuración o la directiva está configurada correctamente</span><span class="sxs-lookup"><span data-stu-id="a2146-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="a2146-134">boolean</span><span class="sxs-lookup"><span data-stu-id="a2146-134">boolean</span></span> | <span data-ttu-id="a2146-135">Indica si la configuración o directiva se aplica al dispositivo</span><span class="sxs-lookup"><span data-stu-id="a2146-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="a2146-136">string</span><span class="sxs-lookup"><span data-stu-id="a2146-136">string</span></span> | <span data-ttu-id="a2146-137">Información contextual adicional sobre la configuración o la directiva</span><span class="sxs-lookup"><span data-stu-id="a2146-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="a2146-138">boolean</span><span class="sxs-lookup"><span data-stu-id="a2146-138">boolean</span></span> | <span data-ttu-id="a2146-139">Indica si habrá impacto en el usuario si se aplica la configuración o la directiva</span><span class="sxs-lookup"><span data-stu-id="a2146-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a2146-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a2146-140">Related topics</span></span>

- [<span data-ttu-id="a2146-141">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="a2146-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a2146-142">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="a2146-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a2146-143">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="a2146-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a2146-144">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="a2146-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a2146-145">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="a2146-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a2146-146">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="a2146-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="a2146-147">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="a2146-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)