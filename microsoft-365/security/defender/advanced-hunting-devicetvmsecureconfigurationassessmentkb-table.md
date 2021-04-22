---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Para obtener información sobre las distintas configuraciones seguras evaluadas por la Administración de amenazas y vulnerabilidades, vea la tabla DeviceTvmSecureConfigurationAssessmentKB del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de amenazas &, TVM, administración de dispositivos, configuración de seguridad, mitre ATT&marco de CK, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: a387d917e5ae93a6289aa2af527d52f1ce1195f4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934876"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="7a091-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="7a091-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7a091-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7a091-105">**Applies to:**</span></span>
- <span data-ttu-id="7a091-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7a091-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="7a091-107">La tabla `DeviceTvmSecureConfigurationAssessmentKB` en el esquema de búsqueda avanzada contiene información acerca de las distintas configuraciones seguras (por ejemplo, si un dispositivo tiene activadas las actualizaciones automáticas) que son evaluadas por la [Administración de amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="7a091-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="7a091-108">También incluye información de riesgos, bancos de pruebas del sector que están relacionados y técnicas y tácticas de MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="7a091-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="7a091-109">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="7a091-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="7a091-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7a091-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7a091-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="7a091-111">Column name</span></span> | <span data-ttu-id="7a091-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7a091-112">Data type</span></span> | <span data-ttu-id="7a091-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a091-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="7a091-114">string</span><span class="sxs-lookup"><span data-stu-id="7a091-114">string</span></span> | <span data-ttu-id="7a091-115">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="7a091-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="7a091-116">cadena</span><span class="sxs-lookup"><span data-stu-id="7a091-116">string</span></span> | <span data-ttu-id="7a091-117">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="7a091-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="7a091-118">string</span><span class="sxs-lookup"><span data-stu-id="7a091-118">string</span></span> | <span data-ttu-id="7a091-119">Nombre para mostrar de la configuración</span><span class="sxs-lookup"><span data-stu-id="7a091-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="7a091-120">string</span><span class="sxs-lookup"><span data-stu-id="7a091-120">string</span></span> | <span data-ttu-id="7a091-121">Descripción de la configuración</span><span class="sxs-lookup"><span data-stu-id="7a091-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="7a091-122">string</span><span class="sxs-lookup"><span data-stu-id="7a091-122">string</span></span> | <span data-ttu-id="7a091-123">Descripción del riesgo asociado</span><span class="sxs-lookup"><span data-stu-id="7a091-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="7a091-124">string</span><span class="sxs-lookup"><span data-stu-id="7a091-124">string</span></span> | <span data-ttu-id="7a091-125">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="7a091-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="7a091-126">cadena</span><span class="sxs-lookup"><span data-stu-id="7a091-126">string</span></span> |<span data-ttu-id="7a091-127">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="7a091-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="7a091-128">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="7a091-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="7a091-129">string</span><span class="sxs-lookup"><span data-stu-id="7a091-129">string</span></span> | <span data-ttu-id="7a091-130">Lista de bancos de pruebas del sector que recomiendan la misma configuración u otra similar</span><span class="sxs-lookup"><span data-stu-id="7a091-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="7a091-131">string</span><span class="sxs-lookup"><span data-stu-id="7a091-131">string</span></span> | <span data-ttu-id="7a091-132">Etiquetas que representan varios atributos usados para identificar o clasificar una configuración de seguridad</span><span class="sxs-lookup"><span data-stu-id="7a091-132">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="7a091-133">cadena</span><span class="sxs-lookup"><span data-stu-id="7a091-133">string</span></span> | <span data-ttu-id="7a091-134">Acciones recomendadas para reducir o solucionar los riesgos asociados</span><span class="sxs-lookup"><span data-stu-id="7a091-134">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7a091-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7a091-135">Related topics</span></span>

- [<span data-ttu-id="7a091-136">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="7a091-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7a091-137">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="7a091-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7a091-138">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="7a091-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7a091-139">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="7a091-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7a091-140">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="7a091-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7a091-141">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="7a091-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="7a091-142">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="7a091-142">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)