---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Obtén más información sobre los eventos de evaluación de seguridad de la administración de amenazas y vulnerabilidades en la tabla DeviceTvmSecureConfigurationAssessment del esquema de caza avanzada. Estos eventos proporcionan información del equipo, así como detalles de la configuración de seguridad, consecuencias e información sobre el cumplimiento.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b186574cfc1307dfd8a01f7a77ef60bf91f4b162
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197002"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="d0238-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="d0238-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d0238-106">**Aplica para:**</span><span class="sxs-lookup"><span data-stu-id="d0238-106">**Applies to:**</span></span>
- <span data-ttu-id="d0238-107">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0238-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="d0238-108">Cada una de las filas de la tabla `DeviceTvmSecureConfigurationAssessment`contiene un evento de evaluación para una configuración de seguridad específica de la administración de [amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="d0238-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="d0238-109">Utilice esta referencia para comprobar los últimos resultados de la evaluación y determinar si los dispositivos son compatibles.</span><span class="sxs-lookup"><span data-stu-id="d0238-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="d0238-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d0238-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d0238-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="d0238-111">Column name</span></span> | <span data-ttu-id="d0238-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d0238-112">Data type</span></span> | <span data-ttu-id="d0238-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0238-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="d0238-114">string</span><span class="sxs-lookup"><span data-stu-id="d0238-114">string</span></span> | <span data-ttu-id="d0238-115">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="d0238-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d0238-116">cadena</span><span class="sxs-lookup"><span data-stu-id="d0238-116">string</span></span> | <span data-ttu-id="d0238-117">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="d0238-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="d0238-118">cadena</span><span class="sxs-lookup"><span data-stu-id="d0238-118">string</span></span> | <span data-ttu-id="d0238-119">Plataforma del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d0238-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="d0238-120">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d0238-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="d0238-121">datetime</span><span class="sxs-lookup"><span data-stu-id="d0238-121">datetime</span></span> | <span data-ttu-id="d0238-122">Fecha y hora en que se generó el registro</span><span class="sxs-lookup"><span data-stu-id="d0238-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="d0238-123">cadena</span><span class="sxs-lookup"><span data-stu-id="d0238-123">string</span></span> | <span data-ttu-id="d0238-124">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="d0238-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="d0238-125">string</span><span class="sxs-lookup"><span data-stu-id="d0238-125">string</span></span> | <span data-ttu-id="d0238-126">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="d0238-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="d0238-127">string</span><span class="sxs-lookup"><span data-stu-id="d0238-127">string</span></span> | <span data-ttu-id="d0238-128">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="d0238-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="d0238-129">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="d0238-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="d0238-130">string</span><span class="sxs-lookup"><span data-stu-id="d0238-130">string</span></span> | <span data-ttu-id="d0238-131">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="d0238-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="d0238-132">booleano</span><span class="sxs-lookup"><span data-stu-id="d0238-132">boolean</span></span> | <span data-ttu-id="d0238-133">Indica si la configuración o la directiva está configurada correctamente</span><span class="sxs-lookup"><span data-stu-id="d0238-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d0238-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d0238-134">Related topics</span></span>

- [<span data-ttu-id="d0238-135">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="d0238-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d0238-136">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="d0238-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d0238-137">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="d0238-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d0238-138">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="d0238-138">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d0238-139">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="d0238-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d0238-140">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="d0238-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d0238-141">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="d0238-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
