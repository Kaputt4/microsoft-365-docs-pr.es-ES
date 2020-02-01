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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3cc4b00d21d64cf3800dd4b8cf51ab0fe835d4ce
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600287"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="c8eb1-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="c8eb1-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="c8eb1-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c8eb1-105">**Applies to:**</span></span>
- <span data-ttu-id="c8eb1-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c8eb1-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="c8eb1-107">La tabla `DeviceTvmSecureConfigurationAssessmentKB` en el esquema de búsqueda avanzada contiene información acerca de las distintas configuraciones seguras (por ejemplo, si un dispositivo tiene activadas las actualizaciones automáticas) que son evaluadas por la [Administración de amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="c8eb1-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="c8eb1-108">También incluye información de riesgos, bancos de pruebas del sector que están relacionados y técnicas y tácticas de MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="c8eb1-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="c8eb1-109">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c8eb1-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="c8eb1-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c8eb1-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c8eb1-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="c8eb1-111">Column name</span></span> | <span data-ttu-id="c8eb1-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c8eb1-112">Data type</span></span> | <span data-ttu-id="c8eb1-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8eb1-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="c8eb1-114">string</span><span class="sxs-lookup"><span data-stu-id="c8eb1-114">string</span></span> | <span data-ttu-id="c8eb1-115">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="c8eb1-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="c8eb1-116">string</span><span class="sxs-lookup"><span data-stu-id="c8eb1-116">string</span></span> | <span data-ttu-id="c8eb1-117">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="c8eb1-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="c8eb1-118">string</span><span class="sxs-lookup"><span data-stu-id="c8eb1-118">string</span></span> | <span data-ttu-id="c8eb1-119">Nombre para mostrar de la configuración</span><span class="sxs-lookup"><span data-stu-id="c8eb1-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="c8eb1-120">string</span><span class="sxs-lookup"><span data-stu-id="c8eb1-120">string</span></span> | <span data-ttu-id="c8eb1-121">Descripción de la configuración</span><span class="sxs-lookup"><span data-stu-id="c8eb1-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="c8eb1-122">string</span><span class="sxs-lookup"><span data-stu-id="c8eb1-122">string</span></span> | <span data-ttu-id="c8eb1-123">Descripción del riesgo asociado</span><span class="sxs-lookup"><span data-stu-id="c8eb1-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="c8eb1-124">string</span><span class="sxs-lookup"><span data-stu-id="c8eb1-124">string</span></span> | <span data-ttu-id="c8eb1-125">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="c8eb1-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="c8eb1-126">string</span><span class="sxs-lookup"><span data-stu-id="c8eb1-126">string</span></span> |<span data-ttu-id="c8eb1-127">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="c8eb1-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="c8eb1-128">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="c8eb1-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="c8eb1-129">string</span><span class="sxs-lookup"><span data-stu-id="c8eb1-129">string</span></span> | <span data-ttu-id="c8eb1-130">Lista de bancos de pruebas del sector que recomiendan la misma configuración u otra similar</span><span class="sxs-lookup"><span data-stu-id="c8eb1-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="c8eb1-131">string</span><span class="sxs-lookup"><span data-stu-id="c8eb1-131">string</span></span> | <span data-ttu-id="c8eb1-132">Lista de las técnicas de Mitre ATT&CK relacionadas con la configuración</span><span class="sxs-lookup"><span data-stu-id="c8eb1-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="c8eb1-133">string</span><span class="sxs-lookup"><span data-stu-id="c8eb1-133">string</span></span> | <span data-ttu-id="c8eb1-134">Lista de las tácticas de Mitre ATT&CK relacionadas con la configuración</span><span class="sxs-lookup"><span data-stu-id="c8eb1-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c8eb1-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c8eb1-135">Related topics</span></span>

- [<span data-ttu-id="c8eb1-136">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="c8eb1-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c8eb1-137">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="c8eb1-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c8eb1-138">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="c8eb1-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c8eb1-139">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c8eb1-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c8eb1-140">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="c8eb1-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c8eb1-141">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="c8eb1-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c8eb1-142">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="c8eb1-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
