---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Obtén más información sobre los eventos de evaluación de seguridad de la administración de amenazas y vulnerabilidades en la tabla DeviceTvmSecureConfigurationAssessment del esquema de caza avanzada. Estos eventos proporcionan información del equipo, así como detalles de la configuración de seguridad, consecuencias e información sobre el cumplimiento.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, buscar, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de amenazas y vulnerabilidades, TVM, administración de dispositivos, configuración de seguridad, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2fee44c0d9c9ff30ca23ccef863e056cadee7de8
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911611"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="be09a-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="be09a-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="be09a-106">**Aplica para:**</span><span class="sxs-lookup"><span data-stu-id="be09a-106">**Applies to:**</span></span>
- <span data-ttu-id="be09a-107">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="be09a-107">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="be09a-108">Cada una de las filas de la tabla `DeviceTvmSecureConfigurationAssessment`contiene un evento de evaluación para una configuración de seguridad específica de la administración de [amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="be09a-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="be09a-109">Utilice esta referencia para comprobar los últimos resultados de la evaluación y determinar si los dispositivos son compatibles.</span><span class="sxs-lookup"><span data-stu-id="be09a-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="be09a-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="be09a-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="be09a-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="be09a-111">Column name</span></span> | <span data-ttu-id="be09a-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="be09a-112">Data type</span></span> | <span data-ttu-id="be09a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="be09a-113">Description</span></span> |
|-------------|-----------|-------------|
| `MachineId` | <span data-ttu-id="be09a-114">string</span><span class="sxs-lookup"><span data-stu-id="be09a-114">string</span></span> | <span data-ttu-id="be09a-115">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="be09a-115">Unique identifier for the machine in the service</span></span> |
| `ComputerName` | <span data-ttu-id="be09a-116">cadena</span><span class="sxs-lookup"><span data-stu-id="be09a-116">string</span></span> | <span data-ttu-id="be09a-117">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="be09a-117">Fully qualified domain name (FQDN) of the pool</span></span> |
| `OSPlatform` | <span data-ttu-id="be09a-118">cadena</span><span class="sxs-lookup"><span data-stu-id="be09a-118">string</span></span> | <span data-ttu-id="be09a-119">Plataforma del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="be09a-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="be09a-120">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="be09a-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="be09a-121">datetime</span><span class="sxs-lookup"><span data-stu-id="be09a-121">dateTime</span></span> | <span data-ttu-id="be09a-122">Fecha y hora en que se generó el registro</span><span class="sxs-lookup"><span data-stu-id="be09a-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="be09a-123">cadena</span><span class="sxs-lookup"><span data-stu-id="be09a-123">string</span></span> | <span data-ttu-id="be09a-124">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="be09a-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="be09a-125">cadena</span><span class="sxs-lookup"><span data-stu-id="be09a-125">string</span></span> | <span data-ttu-id="be09a-126">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="be09a-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="be09a-127">cadena</span><span class="sxs-lookup"><span data-stu-id="be09a-127">string</span></span> | <span data-ttu-id="be09a-128">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="be09a-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="be09a-129">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="be09a-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="be09a-130">cadena</span><span class="sxs-lookup"><span data-stu-id="be09a-130">string</span></span> | <span data-ttu-id="be09a-131">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="be09a-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="be09a-132">booleano</span><span class="sxs-lookup"><span data-stu-id="be09a-132">boolean</span></span> | <span data-ttu-id="be09a-133">Indica si la configuración o la directiva está configurada correctamente</span><span class="sxs-lookup"><span data-stu-id="be09a-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="be09a-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="be09a-134">Related topics</span></span>

- [<span data-ttu-id="be09a-135">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="be09a-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="be09a-136">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="be09a-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="be09a-137">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="be09a-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="be09a-138">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="be09a-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="be09a-139">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="be09a-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="be09a-140">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="be09a-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="be09a-141">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="be09a-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
