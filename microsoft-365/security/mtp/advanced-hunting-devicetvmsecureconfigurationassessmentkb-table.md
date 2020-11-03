---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Para obtener información sobre las distintas configuraciones seguras evaluadas por la Administración de amenazas y vulnerabilidades, vea la tabla DeviceTvmSecureConfigurationAssessmentKB del esquema de búsqueda avanzada.
keywords: características avanzadas de búsqueda, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, amenaza & la administración de vulnerabilidades, TVM, administración de dispositivos, configuración de seguridad MITRE ATT&CK Framework, Knowledge base, KB
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
ms.openlocfilehash: 6186bd37735b5225fd33905395055228972fc27c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847589"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="b2149-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="b2149-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b2149-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b2149-105">**Applies to:**</span></span>
- <span data-ttu-id="b2149-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="b2149-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="b2149-107">La tabla `DeviceTvmSecureConfigurationAssessmentKB` en el esquema de búsqueda avanzada contiene información acerca de las distintas configuraciones seguras (por ejemplo, si un dispositivo tiene activadas las actualizaciones automáticas) que son evaluadas por la [Administración de amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="b2149-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="b2149-108">También incluye información de riesgos, bancos de pruebas del sector que están relacionados y técnicas y tácticas de MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="b2149-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="b2149-109">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="b2149-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="b2149-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b2149-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b2149-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="b2149-111">Column name</span></span> | <span data-ttu-id="b2149-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b2149-112">Data type</span></span> | <span data-ttu-id="b2149-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2149-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="b2149-114">string</span><span class="sxs-lookup"><span data-stu-id="b2149-114">string</span></span> | <span data-ttu-id="b2149-115">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="b2149-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="b2149-116">string</span><span class="sxs-lookup"><span data-stu-id="b2149-116">string</span></span> | <span data-ttu-id="b2149-117">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="b2149-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="b2149-118">string</span><span class="sxs-lookup"><span data-stu-id="b2149-118">string</span></span> | <span data-ttu-id="b2149-119">Nombre para mostrar de la configuración</span><span class="sxs-lookup"><span data-stu-id="b2149-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="b2149-120">string</span><span class="sxs-lookup"><span data-stu-id="b2149-120">string</span></span> | <span data-ttu-id="b2149-121">Descripción de la configuración</span><span class="sxs-lookup"><span data-stu-id="b2149-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="b2149-122">string</span><span class="sxs-lookup"><span data-stu-id="b2149-122">string</span></span> | <span data-ttu-id="b2149-123">Descripción del riesgo asociado</span><span class="sxs-lookup"><span data-stu-id="b2149-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="b2149-124">string</span><span class="sxs-lookup"><span data-stu-id="b2149-124">string</span></span> | <span data-ttu-id="b2149-125">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="b2149-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="b2149-126">string</span><span class="sxs-lookup"><span data-stu-id="b2149-126">string</span></span> |<span data-ttu-id="b2149-127">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="b2149-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="b2149-128">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="b2149-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="b2149-129">string</span><span class="sxs-lookup"><span data-stu-id="b2149-129">string</span></span> | <span data-ttu-id="b2149-130">Lista de bancos de pruebas del sector que recomiendan la misma configuración u otra similar</span><span class="sxs-lookup"><span data-stu-id="b2149-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="b2149-131">string</span><span class="sxs-lookup"><span data-stu-id="b2149-131">string</span></span> | <span data-ttu-id="b2149-132">Lista de las técnicas de Mitre ATT&CK relacionadas con la configuración</span><span class="sxs-lookup"><span data-stu-id="b2149-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="b2149-133">string</span><span class="sxs-lookup"><span data-stu-id="b2149-133">string</span></span> | <span data-ttu-id="b2149-134">Lista de las tácticas de Mitre ATT&CK relacionadas con la configuración</span><span class="sxs-lookup"><span data-stu-id="b2149-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b2149-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b2149-135">Related topics</span></span>

- [<span data-ttu-id="b2149-136">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="b2149-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b2149-137">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="b2149-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b2149-138">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="b2149-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b2149-139">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="b2149-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b2149-140">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="b2149-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b2149-141">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="b2149-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b2149-142">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="b2149-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
