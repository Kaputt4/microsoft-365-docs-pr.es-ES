---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Para obtener información sobre las distintas configuraciones seguras evaluadas por la Administración de amenazas y vulnerabilidades, vea la tabla DeviceTvmSecureConfigurationAssessmentKB del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, amenaza & administración de vulnerabilidades, TVM, administración de dispositivos, configuración de seguridad, marco de CK&MITRE ATT, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 1dfa710b86afdcfd8a5643555564a0f34c7b4702
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024246"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="3fc31-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="3fc31-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3fc31-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3fc31-105">**Applies to:**</span></span>
- <span data-ttu-id="3fc31-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3fc31-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="3fc31-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3fc31-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="3fc31-108">La tabla `DeviceTvmSecureConfigurationAssessmentKB` en el esquema de búsqueda avanzada contiene información acerca de las distintas configuraciones seguras (por ejemplo, si un dispositivo tiene activadas las actualizaciones automáticas) que son evaluadas por la [Administración de amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="3fc31-108">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="3fc31-109">También incluye información de riesgos, bancos de pruebas del sector que están relacionados y técnicas y tácticas de MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="3fc31-109">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="3fc31-110">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3fc31-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="3fc31-111">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="3fc31-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3fc31-112">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="3fc31-112">Column name</span></span> | <span data-ttu-id="3fc31-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="3fc31-113">Data type</span></span> | <span data-ttu-id="3fc31-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3fc31-114">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="3fc31-115">string</span><span class="sxs-lookup"><span data-stu-id="3fc31-115">string</span></span> | <span data-ttu-id="3fc31-116">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="3fc31-116">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="3fc31-117">cadena</span><span class="sxs-lookup"><span data-stu-id="3fc31-117">string</span></span> | <span data-ttu-id="3fc31-118">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="3fc31-118">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="3fc31-119">string</span><span class="sxs-lookup"><span data-stu-id="3fc31-119">string</span></span> | <span data-ttu-id="3fc31-120">Nombre para mostrar de la configuración</span><span class="sxs-lookup"><span data-stu-id="3fc31-120">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="3fc31-121">string</span><span class="sxs-lookup"><span data-stu-id="3fc31-121">string</span></span> | <span data-ttu-id="3fc31-122">Descripción de la configuración</span><span class="sxs-lookup"><span data-stu-id="3fc31-122">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="3fc31-123">string</span><span class="sxs-lookup"><span data-stu-id="3fc31-123">string</span></span> | <span data-ttu-id="3fc31-124">Descripción del riesgo asociado</span><span class="sxs-lookup"><span data-stu-id="3fc31-124">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="3fc31-125">string</span><span class="sxs-lookup"><span data-stu-id="3fc31-125">string</span></span> | <span data-ttu-id="3fc31-126">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="3fc31-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="3fc31-127">cadena</span><span class="sxs-lookup"><span data-stu-id="3fc31-127">string</span></span> |<span data-ttu-id="3fc31-128">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="3fc31-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="3fc31-129">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="3fc31-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="3fc31-130">string</span><span class="sxs-lookup"><span data-stu-id="3fc31-130">string</span></span> | <span data-ttu-id="3fc31-131">Lista de bancos de pruebas del sector que recomiendan la misma configuración u otra similar</span><span class="sxs-lookup"><span data-stu-id="3fc31-131">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="3fc31-132">string</span><span class="sxs-lookup"><span data-stu-id="3fc31-132">string</span></span> | <span data-ttu-id="3fc31-133">Etiquetas que representan varios atributos usados para identificar o clasificar una configuración de seguridad</span><span class="sxs-lookup"><span data-stu-id="3fc31-133">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="3fc31-134">cadena</span><span class="sxs-lookup"><span data-stu-id="3fc31-134">string</span></span> | <span data-ttu-id="3fc31-135">Acciones recomendadas para reducir o solucionar los riesgos asociados</span><span class="sxs-lookup"><span data-stu-id="3fc31-135">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3fc31-136">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3fc31-136">Related topics</span></span>

- [<span data-ttu-id="3fc31-137">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="3fc31-137">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3fc31-138">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="3fc31-138">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3fc31-139">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="3fc31-139">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3fc31-140">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="3fc31-140">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3fc31-141">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="3fc31-141">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3fc31-142">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="3fc31-142">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="3fc31-143">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="3fc31-143">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)