---
title: Tabla DeviceTvmSecureConfigurationAssessmentKB en el esquema de búsqueda avanzada
description: Obtenga información sobre los & de seguridad de Administración de vulnerabilidades en la tabla DeviceTvmSecureConfigurationAssessment del esquema de búsqueda avanzada. Estos eventos proporcionan información del dispositivo, así como detalles de configuración de seguridad, impacto e información de cumplimiento.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de & de amenazas, TVM, administración de dispositivos, configuración de seguridad, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075048"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="5bb3d-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="5bb3d-105">DeviceTvmSecureConfigurationAssessment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5bb3d-106">**Aplica para:**</span><span class="sxs-lookup"><span data-stu-id="5bb3d-106">**Applies to:**</span></span>
- [<span data-ttu-id="5bb3d-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5bb3d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="5bb3d-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5bb3d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5bb3d-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="5bb3d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="5bb3d-110">Cada una de las filas de la tabla `DeviceTvmSecureConfigurationAssessment`contiene un evento de evaluación para una configuración de seguridad específica de la administración de [amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="5bb3d-110">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="5bb3d-111">Utilice esta referencia para comprobar los últimos resultados de la evaluación y determinar si los dispositivos son compatibles.</span><span class="sxs-lookup"><span data-stu-id="5bb3d-111">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="5bb3d-112">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="5bb3d-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="5bb3d-113">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="5bb3d-113">Column name</span></span> | <span data-ttu-id="5bb3d-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5bb3d-114">Data type</span></span> | <span data-ttu-id="5bb3d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bb3d-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="5bb3d-116">string</span><span class="sxs-lookup"><span data-stu-id="5bb3d-116">string</span></span> | <span data-ttu-id="5bb3d-117">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="5bb3d-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5bb3d-118">string</span><span class="sxs-lookup"><span data-stu-id="5bb3d-118">string</span></span> | <span data-ttu-id="5bb3d-119">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="5bb3d-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="5bb3d-120">string</span><span class="sxs-lookup"><span data-stu-id="5bb3d-120">string</span></span> | <span data-ttu-id="5bb3d-121">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5bb3d-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="5bb3d-122">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="5bb3d-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="5bb3d-123">datetime</span><span class="sxs-lookup"><span data-stu-id="5bb3d-123">datetime</span></span> |<span data-ttu-id="5bb3d-124">Fecha y hora en que se generó el registro</span><span class="sxs-lookup"><span data-stu-id="5bb3d-124">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="5bb3d-125">cadena</span><span class="sxs-lookup"><span data-stu-id="5bb3d-125">string</span></span> | <span data-ttu-id="5bb3d-126">Identificador único para una configuración específica</span><span class="sxs-lookup"><span data-stu-id="5bb3d-126">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="5bb3d-127">string</span><span class="sxs-lookup"><span data-stu-id="5bb3d-127">string</span></span> | <span data-ttu-id="5bb3d-128">Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="5bb3d-128">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="5bb3d-129">string</span><span class="sxs-lookup"><span data-stu-id="5bb3d-129">string</span></span> |<span data-ttu-id="5bb3d-130">Subcategoría o subagrupación a la que pertenece la configuración.</span><span class="sxs-lookup"><span data-stu-id="5bb3d-130">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="5bb3d-131">En muchos casos, describe funciones o características específicas.</span><span class="sxs-lookup"><span data-stu-id="5bb3d-131">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="5bb3d-132">string</span><span class="sxs-lookup"><span data-stu-id="5bb3d-132">string</span></span> | <span data-ttu-id="5bb3d-133">Impacto valorado de la configuración en el resultado general de la configuración (1-10)</span><span class="sxs-lookup"><span data-stu-id="5bb3d-133">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="5bb3d-134">booleano</span><span class="sxs-lookup"><span data-stu-id="5bb3d-134">boolean</span></span> | <span data-ttu-id="5bb3d-135">Indica si la configuración o la directiva está configurada correctamente</span><span class="sxs-lookup"><span data-stu-id="5bb3d-135">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="5bb3d-136">boolean</span><span class="sxs-lookup"><span data-stu-id="5bb3d-136">boolean</span></span> | <span data-ttu-id="5bb3d-137">Indica si la configuración o directiva se aplica al dispositivo</span><span class="sxs-lookup"><span data-stu-id="5bb3d-137">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="5bb3d-138">string</span><span class="sxs-lookup"><span data-stu-id="5bb3d-138">string</span></span> | <span data-ttu-id="5bb3d-139">Información contextual adicional sobre la configuración o la directiva</span><span class="sxs-lookup"><span data-stu-id="5bb3d-139">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="5bb3d-140">boolean</span><span class="sxs-lookup"><span data-stu-id="5bb3d-140">boolean</span></span> | <span data-ttu-id="5bb3d-141">Indica si habrá impacto en el usuario si se aplica la configuración o la directiva</span><span class="sxs-lookup"><span data-stu-id="5bb3d-141">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5bb3d-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5bb3d-142">Related topics</span></span>

- [<span data-ttu-id="5bb3d-143">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="5bb3d-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5bb3d-144">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="5bb3d-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5bb3d-145">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="5bb3d-145">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="5bb3d-146">Información general sobre la Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="5bb3d-146">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)