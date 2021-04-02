---
title: 'Requisitos previos & permisos: administración de amenazas y vulnerabilidades'
description: Antes de empezar a usar la administración de amenazas y vulnerabilidades, asegúrese de que tiene las configuraciones y permisos pertinentes.
keywords: requisitos previos & permisos de administración de vulnerabilidades, permisos de administración de amenazas y vulnerabilidades, requisitos previos de permisos de MDATP TVM, administración de vulnerabilidades
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1d9c3233f72541ccd0463eefef93bde5e7d9900f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499959"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="3849a-104">Requisitos previos & permisos: administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="3849a-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3849a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3849a-105">**Applies to:**</span></span>

- [<span data-ttu-id="3849a-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3849a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3849a-107">Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="3849a-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3849a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3849a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3849a-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="3849a-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3849a-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="3849a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="3849a-111">Asegúrese de que los dispositivos:</span><span class="sxs-lookup"><span data-stu-id="3849a-111">Ensure that your devices:</span></span>

- <span data-ttu-id="3849a-112">Están incorporados a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="3849a-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="3849a-113">Ejecutar [sistemas operativos y plataformas compatibles](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="3849a-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="3849a-114">Haga que las siguientes actualizaciones obligatorias se instalen e implementen en la red para aumentar las tasas de detección de la evaluación de vulnerabilidades:</span><span class="sxs-lookup"><span data-stu-id="3849a-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="3849a-115">Versión</span><span class="sxs-lookup"><span data-stu-id="3849a-115">Release</span></span> | <span data-ttu-id="3849a-116">Número y vínculo kb de actualización de seguridad</span><span class="sxs-lookup"><span data-stu-id="3849a-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="3849a-117">Windows 10 Versión 1709</span><span class="sxs-lookup"><span data-stu-id="3849a-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="3849a-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) y [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="3849a-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="3849a-119">Windows 10 Versión 1803</span><span class="sxs-lookup"><span data-stu-id="3849a-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="3849a-120">[KB4493464](https://support.microsoft.com/help/4493464) y [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="3849a-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="3849a-121">Windows 10 Versión 1809</span><span class="sxs-lookup"><span data-stu-id="3849a-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="3849a-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="3849a-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="3849a-123">Windows 10 Versión 1903</span><span class="sxs-lookup"><span data-stu-id="3849a-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="3849a-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="3849a-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="3849a-125">Se incorpora a [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) y Microsoft Endpoint  [Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) para ayudar a corregir las amenazas encontradas por la administración de amenazas y vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="3849a-125">Are onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="3849a-126">Si usa Configuration Manager, actualice la consola a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="3849a-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="3849a-127">**Nota:** Si tienes habilitada la conexión de Intune, obtienes una opción para crear una tarea de seguridad de Intune al crear una solicitud de corrección.</span><span class="sxs-lookup"><span data-stu-id="3849a-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="3849a-128">Esta opción no aparece si la conexión no está establecida.</span><span class="sxs-lookup"><span data-stu-id="3849a-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="3849a-129">Tener al menos una recomendación de seguridad que se pueda ver en la página del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3849a-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="3849a-130">Se etiquetan o se marcan como administrados de forma co-administrada</span><span class="sxs-lookup"><span data-stu-id="3849a-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="3849a-131">Opciones de permisos relevantes</span><span class="sxs-lookup"><span data-stu-id="3849a-131">Relevant permission options</span></span>

1. <span data-ttu-id="3849a-132">Inicie sesión en el Centro de seguridad de Microsoft Defender con una cuenta con un administrador de seguridad o un rol de administrador global asignado.</span><span class="sxs-lookup"><span data-stu-id="3849a-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="3849a-133">En el panel de navegación, seleccione **Configuración > Roles**.</span><span class="sxs-lookup"><span data-stu-id="3849a-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="3849a-134">Para obtener más información, vea [Create and manage roles for role-based access control](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="3849a-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="3849a-135">Ver datos</span><span class="sxs-lookup"><span data-stu-id="3849a-135">View data</span></span>

- <span data-ttu-id="3849a-136">**Operaciones de seguridad:** ver todos los datos de operaciones de seguridad en el portal</span><span class="sxs-lookup"><span data-stu-id="3849a-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="3849a-137">**Administración de amenazas y vulnerabilidades:** ver los datos de administración de amenazas y vulnerabilidades en el portal</span><span class="sxs-lookup"><span data-stu-id="3849a-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="3849a-138">Acciones de corrección activas</span><span class="sxs-lookup"><span data-stu-id="3849a-138">Active remediation actions</span></span>

- <span data-ttu-id="3849a-139">**Operaciones de seguridad:** realizar acciones de respuesta, aprobar o descartar acciones de corrección pendientes, administrar listas permitidas o bloqueadas para automatización e indicadores</span><span class="sxs-lookup"><span data-stu-id="3849a-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="3849a-140">**Administración de amenazas y vulnerabilidades: control de excepciones:** crear nuevas excepciones y administrar excepciones activas</span><span class="sxs-lookup"><span data-stu-id="3849a-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="3849a-141">**Administración de amenazas y vulnerabilidades: control de** corrección: enviar nuevas solicitudes de corrección, crear vales y administrar las actividades de corrección existentes</span><span class="sxs-lookup"><span data-stu-id="3849a-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="3849a-142">Para obtener más información, vea [Opciones de permisos RBAC](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="3849a-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="3849a-143">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="3849a-143">Related articles</span></span>

- [<span data-ttu-id="3849a-144">Introducción a la administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="3849a-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3849a-145">Plataformas y sistemas operativos compatibles</span><span class="sxs-lookup"><span data-stu-id="3849a-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="3849a-146">Asignar valor de dispositivo</span><span class="sxs-lookup"><span data-stu-id="3849a-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="3849a-147">Panel de administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="3849a-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

