---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Para obtener información sobre las distintas configuraciones seguras evaluadas por la Administración de amenazas y vulnerabilidades, vea la tabla DeviceTvmSecureConfigurationAssessmentKB del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, buscar, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de amenazas y vulnerabilidades, TVM, administración de dispositivos, configuración de seguridad, marco MITRE ATT&CK, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: a3ae0a95af4a51d492c577e6a2ac1f2b96bba635
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806939"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="8cbc3-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="8cbc3-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="8cbc3-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8cbc3-105">**Applies to:**</span></span>
- <span data-ttu-id="8cbc3-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8cbc3-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8cbc3-107">La tabla `DeviceTvmSecureConfigurationAssessmentKB` en el esquema de búsqueda avanzada contiene información acerca de las distintas configuraciones seguras (por ejemplo, si un dispositivo tiene activadas las actualizaciones automáticas) que son evaluadas por la [Administración de amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="8cbc3-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="8cbc3-108">También incluye información de riesgos, bancos de pruebas del sector que están relacionados y técnicas y tácticas de MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="8cbc3-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="8cbc3-109">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="8cbc3-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="8cbc3-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="8cbc3-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8cbc3-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="8cbc3-111">Column name</span></span> | <span data-ttu-id="8cbc3-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8cbc3-112">Data type</span></span> | <span data-ttu-id="8cbc3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8cbc3-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="8cbc3-114">string</span><span class="sxs-lookup"><span data-stu-id="8cbc3-114">string</span></span> | <span data-ttu-id="8cbc3-115">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="8cbc3-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="8cbc3-116">string</span><span class="sxs-lookup"><span data-stu-id="8cbc3-116">string</span></span> | <span data-ttu-id="8cbc3-117">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="8cbc3-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="8cbc3-118">string</span><span class="sxs-lookup"><span data-stu-id="8cbc3-118">string</span></span> | <span data-ttu-id="8cbc3-119">Nombre para mostrar de la configuración</span><span class="sxs-lookup"><span data-stu-id="8cbc3-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="8cbc3-120">string</span><span class="sxs-lookup"><span data-stu-id="8cbc3-120">string</span></span> | <span data-ttu-id="8cbc3-121">Descripción de la configuración</span><span class="sxs-lookup"><span data-stu-id="8cbc3-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="8cbc3-122">string</span><span class="sxs-lookup"><span data-stu-id="8cbc3-122">string</span></span> | <span data-ttu-id="8cbc3-123">Descripción del riesgo asociado</span><span class="sxs-lookup"><span data-stu-id="8cbc3-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="8cbc3-124">string</span><span class="sxs-lookup"><span data-stu-id="8cbc3-124">string</span></span> | <span data-ttu-id="8cbc3-125">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="8cbc3-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="8cbc3-126">string</span><span class="sxs-lookup"><span data-stu-id="8cbc3-126">string</span></span> |<span data-ttu-id="8cbc3-127">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="8cbc3-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="8cbc3-128">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="8cbc3-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="8cbc3-129">string</span><span class="sxs-lookup"><span data-stu-id="8cbc3-129">string</span></span> | <span data-ttu-id="8cbc3-130">Lista de bancos de pruebas del sector que recomiendan la misma configuración u otra similar</span><span class="sxs-lookup"><span data-stu-id="8cbc3-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="8cbc3-131">string</span><span class="sxs-lookup"><span data-stu-id="8cbc3-131">string</span></span> | <span data-ttu-id="8cbc3-132">Lista de las técnicas de Mitre ATT&CK relacionadas con la configuración</span><span class="sxs-lookup"><span data-stu-id="8cbc3-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="8cbc3-133">string</span><span class="sxs-lookup"><span data-stu-id="8cbc3-133">string</span></span> | <span data-ttu-id="8cbc3-134">Lista de las tácticas de Mitre ATT&CK relacionadas con la configuración</span><span class="sxs-lookup"><span data-stu-id="8cbc3-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8cbc3-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8cbc3-135">Related topics</span></span>

- [<span data-ttu-id="8cbc3-136">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="8cbc3-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8cbc3-137">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="8cbc3-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8cbc3-138">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="8cbc3-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8cbc3-139">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="8cbc3-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8cbc3-140">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="8cbc3-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8cbc3-141">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="8cbc3-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="8cbc3-142">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="8cbc3-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
