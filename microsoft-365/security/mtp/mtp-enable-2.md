---
title: Habilitar la Protección contra amenazas de Microsoft en el Centro de seguridad de Microsoft 365
description: Obtenga información acerca de cómo habilitar la Protección contra amenazas de Microsoft y empiece a integrar su gestión de incidentes de seguridad y la respuesta a ellos.
keywords: Introducción, habilitación de MTP, protección contra amenazas de Microsoft, M365, seguridad, ubicación de datos, permisos requeridos, elegibilidad de licencia
search.product: eADQiWindows 10XVcnh
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: a024a261d216342cebfc3c28fcd159389ea422ec
ms.sourcegitcommit: a7ce1e9041d27aa85b825368887f41ea8e823541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "41165545"
---
# <a name="turn-on-microsoft-threat-protection-test-copy"></a><span data-ttu-id="ab214-104">Activar la copia de prueba de la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ab214-104">Turn on Microsoft Threat Protection TEST COPY</span></span>

<span data-ttu-id="ab214-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ab214-105">**Applies to:**</span></span>
- <span data-ttu-id="ab214-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ab214-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="ab214-107">La Protección contra amenazas de Microsoft unifica el proceso de respuesta a incidentes de seguridad mediante la integración de las capacidades clave en la Protección contra amenazas avanzada (ATP) de Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="ab214-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="ab214-108">Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab214-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="ab214-109">Comprobar la elegibilidad de la licencia y los permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="ab214-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="ab214-110">Los clientes con una licencia de Microsoft 365 E5 o equivalente pueden usar la Protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ab214-110">Customers with a Microsoft 365 E5 or equivalent license can use Microsoft Threat Protection.</span></span> <span data-ttu-id="ab214-111">Para obtener más información, [lea los requisitos de licencia](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="ab214-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

 <span data-ttu-id="ab214-112">Para poder activar la protección contra amenazas de Microsoft, debe ser **administrador global** o **Administrador de seguridad** en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).</span><span class="sxs-lookup"><span data-stu-id="ab214-112">To be able to turn on Microsoft Threat Protection, you need to be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="ab214-113">Empiece a usar el servicio</span><span class="sxs-lookup"><span data-stu-id="ab214-113">Start using the service</span></span>
<span data-ttu-id="ab214-114">Activar el servicio de Protección contra amenazas de Microsoft agrega datos de diferentes servicios integrados.</span><span class="sxs-lookup"><span data-stu-id="ab214-114">Turning on the Microsoft Threat Protection service aggregates data from the various integrated services.</span></span> <span data-ttu-id="ab214-115">Los datos se procesan y almacenan de forma centralizada para identificar nuevas perspectivas y posibilitar la centralización de flujos de trabajo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ab214-115">The data will be processed and stored centrally to identify new insights and to make centralized response workflows possible.</span></span>

<span data-ttu-id="ab214-116">Antes de activar el servicio, el centro de seguridad 365 de Microsoft ([Security.Microsoft.com](https://security.microsoft.com)) no muestra los **incidentes** ni las opciones del **centro de actividades** en el menú.</span><span class="sxs-lookup"><span data-stu-id="ab214-116">Before you turn the service on, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) does not show the **Incidents** and the **Action center** options on the menu.</span></span>

<span data-ttu-id="ab214-117">![Imagen del menú del Centro de seguridad de Microsoft 365 sin características de la Protección contra amenazas de Microsoft](../images/mtp-off.png)
*Centro de seguridad de Microsoft 365 con la Protección contra amenazas de Microsoft desactivada*</span><span class="sxs-lookup"><span data-stu-id="ab214-117">![Image of Microsoft 365 security center menu without Microsoft Threat Protection features](../images/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="ab214-118">Para activar el servicio de Protección contra amenazas de Microsoft, vaya a **Configuración** > \*\*\*\* Protección contra amenazas de Microsoft > **Participar/No participar** en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab214-118">To turn the Microsoft Threat Protection service on, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span>

<span data-ttu-id="ab214-119">Si su organización dispone de ATP de Microsoft Defender, los datos se almacenarán y procesarán en la misma ubicación del centro de datos que seleccionara para [sus datos de ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="ab214-119">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="ab214-120">Si no tiene ATP de Microsoft defender, se le pedirá que elija una nueva ubicación del centro de datos específicamente para la Protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ab214-120">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> <span data-ttu-id="ab214-121">Tendrá que dar su consentimiento para que los datos se compartan entre los servicios y se agreguen.</span><span class="sxs-lookup"><span data-stu-id="ab214-121">You will need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="ab214-122">Confirme que el servicio está activado</span><span class="sxs-lookup"><span data-stu-id="ab214-122">Confirm that the service is on</span></span>
<span data-ttu-id="ab214-123">Una vez que recibe el servicio, este agrega:</span><span class="sxs-lookup"><span data-stu-id="ab214-123">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="ab214-124">Administración de incidentes</span><span class="sxs-lookup"><span data-stu-id="ab214-124">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="ab214-125">Un centro de actividades para administrar [una investigación y respuestas automáticas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="ab214-125">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="ab214-126">[Características de búsqueda](advanced-hunting-overview.md) avanzadas en la página de **Búsqueda**</span><span class="sxs-lookup"><span data-stu-id="ab214-126">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="ab214-127">![Imagen del menú del Centro de seguridad de Microsoft 365 con características de la Protección contra amenazas de Microsoft](../images/mtp-on.png)
*Centro de seguridad de Microsoft 365 con gestión de incidentes y otras características de Protección contra amenazas de Microsoft*</span><span class="sxs-lookup"><span data-stu-id="ab214-127">![Image of Microsoft 365 security center menu with Microsoft Threat Protection features](../images/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection features*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="ab214-128">Obtener datos de Azure ATP</span><span class="sxs-lookup"><span data-stu-id="ab214-128">Getting Azure ATP data</span></span>
<span data-ttu-id="ab214-129">Para compartir datos de Azure ATP con la Protección contra amenazas de Microsoft, asegúrese de que esté activada la integración entre Microsoft Cloud App Security y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="ab214-129">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="ab214-130">Infórmese de esta integración</span><span class="sxs-lookup"><span data-stu-id="ab214-130">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="ab214-131">Deshabilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ab214-131">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="ab214-132">Para dejar de usar la Protección contra amenazas de Microsoft, vaya a **Configuración** > \*\*\*\* Protección contra amenazas de Microsoft > \*\*\*\* Participar/No participar en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab214-132">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="ab214-133">Anule la selección de **Activar la Protección contra amenazas de Microsoft** y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="ab214-133">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="ab214-134">Los datos se eliminarán de forma permanente y se quitarán las características correspondientes del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab214-134">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="ab214-135">Cómo recibir asistencia</span><span class="sxs-lookup"><span data-stu-id="ab214-135">Get assistance</span></span>

<span data-ttu-id="ab214-136">El personal de Microsoft puede ayudarle a recibir o anular el servicio y los recursos relacionados en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="ab214-136">Microsoft staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="ab214-137">Para obtener ayuda, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab214-137">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="ab214-138">Al describir sus preocupaciones, mencione "protección contra amenazas de Microsoft".</span><span class="sxs-lookup"><span data-stu-id="ab214-138">When describing your concerns, mention "Microsoft Threat Protection".</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab214-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ab214-139">Related topics</span></span>

- [<span data-ttu-id="ab214-140">Introducción a la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ab214-140">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="ab214-141">Requisitos de licencia y otros requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ab214-141">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="ab214-142">Introducción al ATP de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ab214-142">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="ab214-143">Introducción al ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="ab214-143">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="ab214-144">Introducción a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ab214-144">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="ab214-145">Introducción al ATP de Azure</span><span class="sxs-lookup"><span data-stu-id="ab214-145">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="ab214-146">Almacenamiento de datos del ATP de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ab214-146">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
