---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Para obtener información sobre las distintas configuraciones seguras evaluadas por la Administración de amenazas y vulnerabilidades, vea la tabla DeviceTvmSecureConfigurationAssessmentKB del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de & amenazas, TVM, administración de dispositivos, configuración de seguridad, marco CK de MITRE ATT&, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 4cd23b8f3ba99b38264b9bf1ba18e8ec2574bab6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931067"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="6348f-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="6348f-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6348f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6348f-105">**Applies to:**</span></span>
- <span data-ttu-id="6348f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6348f-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="6348f-107">La tabla `DeviceTvmSecureConfigurationAssessmentKB` en el esquema de búsqueda avanzada contiene información acerca de las distintas configuraciones seguras (por ejemplo, si un dispositivo tiene activadas las actualizaciones automáticas) que son evaluadas por la [Administración de amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="6348f-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="6348f-108">También incluye información de riesgos, bancos de pruebas del sector que están relacionados y técnicas y tácticas de MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="6348f-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="6348f-109">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6348f-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6348f-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6348f-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6348f-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="6348f-111">Column name</span></span> | <span data-ttu-id="6348f-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6348f-112">Data type</span></span> | <span data-ttu-id="6348f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6348f-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="6348f-114">string</span><span class="sxs-lookup"><span data-stu-id="6348f-114">string</span></span> | <span data-ttu-id="6348f-115">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="6348f-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="6348f-116">string</span><span class="sxs-lookup"><span data-stu-id="6348f-116">string</span></span> | <span data-ttu-id="6348f-117">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="6348f-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="6348f-118">string</span><span class="sxs-lookup"><span data-stu-id="6348f-118">string</span></span> | <span data-ttu-id="6348f-119">Nombre para mostrar de la configuración</span><span class="sxs-lookup"><span data-stu-id="6348f-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="6348f-120">string</span><span class="sxs-lookup"><span data-stu-id="6348f-120">string</span></span> | <span data-ttu-id="6348f-121">Descripción de la configuración</span><span class="sxs-lookup"><span data-stu-id="6348f-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="6348f-122">string</span><span class="sxs-lookup"><span data-stu-id="6348f-122">string</span></span> | <span data-ttu-id="6348f-123">Descripción del riesgo asociado</span><span class="sxs-lookup"><span data-stu-id="6348f-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="6348f-124">string</span><span class="sxs-lookup"><span data-stu-id="6348f-124">string</span></span> | <span data-ttu-id="6348f-125">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="6348f-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="6348f-126">string</span><span class="sxs-lookup"><span data-stu-id="6348f-126">string</span></span> |<span data-ttu-id="6348f-127">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="6348f-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="6348f-128">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="6348f-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="6348f-129">string</span><span class="sxs-lookup"><span data-stu-id="6348f-129">string</span></span> | <span data-ttu-id="6348f-130">Lista de bancos de pruebas del sector que recomiendan la misma configuración u otra similar</span><span class="sxs-lookup"><span data-stu-id="6348f-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="6348f-131">string</span><span class="sxs-lookup"><span data-stu-id="6348f-131">string</span></span> | <span data-ttu-id="6348f-132">Lista de las técnicas de Mitre ATT&CK relacionadas con la configuración</span><span class="sxs-lookup"><span data-stu-id="6348f-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="6348f-133">string</span><span class="sxs-lookup"><span data-stu-id="6348f-133">string</span></span> | <span data-ttu-id="6348f-134">Lista de las tácticas de Mitre ATT&CK relacionadas con la configuración</span><span class="sxs-lookup"><span data-stu-id="6348f-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6348f-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6348f-135">Related topics</span></span>

- [<span data-ttu-id="6348f-136">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="6348f-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6348f-137">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="6348f-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6348f-138">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="6348f-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6348f-139">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="6348f-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6348f-140">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="6348f-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6348f-141">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="6348f-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6348f-142">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="6348f-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
