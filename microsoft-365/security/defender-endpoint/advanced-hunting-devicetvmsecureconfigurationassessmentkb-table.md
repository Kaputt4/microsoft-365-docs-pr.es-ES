---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Obtenga información sobre las distintas configuraciones seguras evaluadas por threat & Vulnerability Management en la tabla DeviceTvmSecureConfigurationAssessmentKB del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda de wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de & amenazas, TVM, administración de dispositivos, configuración de seguridad, marco de CK&MITRE ATT, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075043"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="de27c-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="de27c-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="de27c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="de27c-105">**Applies to:**</span></span>
- [<span data-ttu-id="de27c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="de27c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="de27c-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="de27c-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="de27c-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="de27c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="de27c-109">La tabla `DeviceTvmSecureConfigurationAssessmentKB` en el esquema de búsqueda avanzada contiene información acerca de las distintas configuraciones seguras (por ejemplo, si un dispositivo tiene activadas las actualizaciones automáticas) que son evaluadas por la [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="de27c-109">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="de27c-110">También incluye información de riesgos, bancos de pruebas del sector que están relacionados y técnicas y tácticas de MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="de27c-110">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="de27c-111">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="de27c-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="de27c-112">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="de27c-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="de27c-113">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="de27c-113">Column name</span></span> | <span data-ttu-id="de27c-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="de27c-114">Data type</span></span> | <span data-ttu-id="de27c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="de27c-115">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="de27c-116">string</span><span class="sxs-lookup"><span data-stu-id="de27c-116">string</span></span> | <span data-ttu-id="de27c-117">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="de27c-117">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="de27c-118">string</span><span class="sxs-lookup"><span data-stu-id="de27c-118">string</span></span> | <span data-ttu-id="de27c-119">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="de27c-119">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="de27c-120">string</span><span class="sxs-lookup"><span data-stu-id="de27c-120">string</span></span> | <span data-ttu-id="de27c-121">Nombre para mostrar de la configuración</span><span class="sxs-lookup"><span data-stu-id="de27c-121">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="de27c-122">string</span><span class="sxs-lookup"><span data-stu-id="de27c-122">string</span></span> | <span data-ttu-id="de27c-123">Descripción de la configuración</span><span class="sxs-lookup"><span data-stu-id="de27c-123">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="de27c-124">string</span><span class="sxs-lookup"><span data-stu-id="de27c-124">string</span></span> | <span data-ttu-id="de27c-125">Descripción del riesgo asociado</span><span class="sxs-lookup"><span data-stu-id="de27c-125">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="de27c-126">string</span><span class="sxs-lookup"><span data-stu-id="de27c-126">string</span></span> | <span data-ttu-id="de27c-127">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="de27c-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="de27c-128">string</span><span class="sxs-lookup"><span data-stu-id="de27c-128">string</span></span> |<span data-ttu-id="de27c-129">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="de27c-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="de27c-130">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="de27c-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="de27c-131">string</span><span class="sxs-lookup"><span data-stu-id="de27c-131">string</span></span> | <span data-ttu-id="de27c-132">Lista de bancos de pruebas del sector que recomiendan la misma configuración u otra similar</span><span class="sxs-lookup"><span data-stu-id="de27c-132">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="de27c-133">string</span><span class="sxs-lookup"><span data-stu-id="de27c-133">string</span></span> | <span data-ttu-id="de27c-134">Lista de las técnicas de Mitre ATT&CK relacionadas con la configuración</span><span class="sxs-lookup"><span data-stu-id="de27c-134">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="de27c-135">string</span><span class="sxs-lookup"><span data-stu-id="de27c-135">string</span></span> | <span data-ttu-id="de27c-136">Lista de las tácticas de Mitre ATT&CK relacionadas con la configuración</span><span class="sxs-lookup"><span data-stu-id="de27c-136">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="de27c-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="de27c-137">Related topics</span></span>

- [<span data-ttu-id="de27c-138">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="de27c-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="de27c-139">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="de27c-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="de27c-140">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="de27c-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="de27c-141">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="de27c-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
