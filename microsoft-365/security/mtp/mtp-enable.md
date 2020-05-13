---
title: Habilitar la Protección contra amenazas de Microsoft en el Centro de seguridad de Microsoft 365
description: Obtenga información acerca de cómo habilitar la Protección contra amenazas de Microsoft y empiece a integrar su gestión de incidentes de seguridad y la respuesta a ellos.
keywords: Introducción, habilitación de MTP, protección contra amenazas de Microsoft, M365, seguridad, ubicación de datos, permisos necesarios, requisitos de licencia, página de configuración
search.product: eADQiWindows 10XVcnh
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 9a57929e42f08db8abda170c889441d3a50ade72
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209252"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="34d9d-104">Habilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="34d9d-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="34d9d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="34d9d-105">**Applies to:**</span></span>
- <span data-ttu-id="34d9d-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="34d9d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="34d9d-107">La Protección contra amenazas de Microsoft unifica el proceso de respuesta a incidentes de seguridad mediante la integración de las capacidades clave en la Protección contra amenazas avanzada (ATP) de Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="34d9d-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="34d9d-108">Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34d9d-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="34d9d-109">Para obtener la mejor protección y optimizar la protección contra amenazas de Microsoft, se recomienda implementar todos los servicios admitidos aplicables en la red.</span><span class="sxs-lookup"><span data-stu-id="34d9d-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="34d9d-110">Para obtener más información, [Consulte acerca de la implementación de servicios compatibles](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="34d9d-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="34d9d-111">Comprobar la elegibilidad de la licencia y los permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="34d9d-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="34d9d-112">Una licencia de seguridad de Microsoft 365 E5, E5 Security, A5 o a5 o una combinación válida de licencias proporciona acceso a los servicios admitidos y le da derecho a usar Microsoft Threat Protection en el centro de seguridad de Microsoft 365 sin costo adicional de licencias.</span><span class="sxs-lookup"><span data-stu-id="34d9d-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span>

<span data-ttu-id="34d9d-113">Para obtener información detallada sobre la licencia, [Lea los requisitos de licencia](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="34d9d-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="34d9d-114">Comprobar el rol</span><span class="sxs-lookup"><span data-stu-id="34d9d-114">Check your role</span></span>
<span data-ttu-id="34d9d-115">Debe ser **administrador global** o **Administrador de seguridad** en Azure Active Directory para activar la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34d9d-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="34d9d-116">Ver sus roles en Azure AD</span><span class="sxs-lookup"><span data-stu-id="34d9d-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="34d9d-117">Empiece a usar el servicio</span><span class="sxs-lookup"><span data-stu-id="34d9d-117">Start using the service</span></span>

>[!IMPORTANT]
><span data-ttu-id="34d9d-118">A partir del 12 de mayo de 2020, Microsoft implementará gradualmente nuevas y optimizadas experiencias sobre [los requisitos de licencia](prerequisites.md#licensing-requirements) y activando la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34d9d-118">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around [licensing requirements](prerequisites.md#licensing-requirements) and turning on Microsoft Threat Protection.</span></span> <span data-ttu-id="34d9d-119">Durante varias semanas durante este período, algunos clientes empezarán a ver los cambios en sus experiencias de portal.</span><span class="sxs-lookup"><span data-stu-id="34d9d-119">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="34d9d-120">La información sobre las nuevas experiencias se marca como **nueva experiencia** en este artículo.</span><span class="sxs-lookup"><span data-stu-id="34d9d-120">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="34d9d-121">Microsoft Threat Protection agrega datos de los diversos servicios integrados.</span><span class="sxs-lookup"><span data-stu-id="34d9d-121">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="34d9d-122">Procesará y almacenará datos de forma centralizada para identificar nuevos conocimientos y hacer que los flujos de trabajo de respuesta centralizados sean posibles.</span><span class="sxs-lookup"><span data-stu-id="34d9d-122">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="34d9d-123">Lo hace sin afectar a las implementaciones, la configuración o los datos existentes asociados con los servicios integrados.</span><span class="sxs-lookup"><span data-stu-id="34d9d-123">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="34d9d-124">Antes de activar el servicio, el centro de seguridad de Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) muestra la página de bienvenida de Microsoft Threat Protection al seleccionar **incidentes**, **centro de actividades**o **caza** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="34d9d-124">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="34d9d-125">Estas opciones de navegación no se muestran si no es elegible para usar la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34d9d-125">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="34d9d-126">![Imagen de la página de bienvenida de Microsoft Threat Protection que se muestra si no se ha activado la protección contra amenazas de Microsoft en la ](../../media/mtp-welcome.png)
 *Página de bienvenida de Microsoft Threat Protection en el centro de seguridad de Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="34d9d-126">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="34d9d-127">Para activar la protección contra amenazas de Microsoft, simplemente complete el proceso desde la página de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="34d9d-127">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="34d9d-128">También puede activar Microsoft Threat Protection accediendo a la **configuración** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) en el panel de navegación y seleccionando **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="34d9d-128">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="34d9d-129">Si no ve la **configuración** en el panel de navegación o no pudo obtener acceso a la página, compruebe los permisos y las licencias.</span><span class="sxs-lookup"><span data-stu-id="34d9d-129">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="34d9d-130">Seleccionar la ubicación del centro de datos</span><span class="sxs-lookup"><span data-stu-id="34d9d-130">Select data center location</span></span>
<span data-ttu-id="34d9d-131">Si su organización dispone de ATP de Microsoft Defender, los datos se almacenarán y procesarán en la misma ubicación del centro de datos que seleccionara para [sus datos de ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="34d9d-131">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="34d9d-132">Si no tiene ATP de Microsoft defender, se le pedirá que elija una nueva ubicación del centro de datos específicamente para la Protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34d9d-132">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 
 
<span data-ttu-id="34d9d-133">Debe proporcionar el consentimiento antes de que los datos se compartan entre los servicios y se agreguen.</span><span class="sxs-lookup"><span data-stu-id="34d9d-133">You need to provide consent before data is shared between services and aggregated.</span></span>

<span data-ttu-id="34d9d-134">**Nueva experiencia:** A partir del 12 de mayo de 2020, los clientes recibirán gradualmente los cambios de esta experiencia.</span><span class="sxs-lookup"><span data-stu-id="34d9d-134">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="34d9d-135">Para los usuarios con la nueva experiencia, el servicio selecciona automáticamente la ubicación óptima del centro de datos para los datos agregados en función de los servicios de seguridad de Microsoft 365 existentes.</span><span class="sxs-lookup"><span data-stu-id="34d9d-135">For those with the new experience, the service automatically selects the optimal data center location for your aggregated data based on your existing Microsoft 365 security services.</span></span> <span data-ttu-id="34d9d-136">La ubicación del centro de datos seleccionada se muestra en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="34d9d-136">The selected data center location is shown in the screen.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="34d9d-137">Confirme que el servicio está activado</span><span class="sxs-lookup"><span data-stu-id="34d9d-137">Confirm that the service is on</span></span>
<span data-ttu-id="34d9d-138">Una vez que recibe el servicio, este agrega:</span><span class="sxs-lookup"><span data-stu-id="34d9d-138">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="34d9d-139">Administración de incidentes</span><span class="sxs-lookup"><span data-stu-id="34d9d-139">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="34d9d-140">Un centro de actividades para administrar [una investigación y respuestas automáticas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="34d9d-140">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="34d9d-141">Funcionalidades de [búsqueda avanzada](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="34d9d-141">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="34d9d-142">![Imagen del panel de navegación del centro de seguridad de Microsoft 365 con Microsoft Threat Protection características de ](../../media/mtp-on.png)
 *Microsoft 365 Security Center con incidentes de administración de incidentes y otras capacidades de protección contra amenazas de Microsoft*</span><span class="sxs-lookup"><span data-stu-id="34d9d-142">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="34d9d-143">Obtener datos de Azure ATP</span><span class="sxs-lookup"><span data-stu-id="34d9d-143">Getting Azure ATP data</span></span>
<span data-ttu-id="34d9d-144">Para compartir datos de Azure ATP con la Protección contra amenazas de Microsoft, asegúrese de que esté activada la integración entre Microsoft Cloud App Security y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="34d9d-144">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="34d9d-145">Infórmese de esta integración</span><span class="sxs-lookup"><span data-stu-id="34d9d-145">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="34d9d-146">Deshabilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="34d9d-146">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="34d9d-147">Para dejar de usar la Protección contra amenazas de Microsoft, vaya a **Configuración** > \*\*\*\* Protección contra amenazas de Microsoft > \*\*\*\* Participar/No participar en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34d9d-147">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="34d9d-148">Anule la selección de **Activar la Protección contra amenazas de Microsoft** y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="34d9d-148">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="34d9d-149">Se quitarán las características correspondientes del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34d9d-149">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="34d9d-150">Cómo recibir asistencia</span><span class="sxs-lookup"><span data-stu-id="34d9d-150">Get assistance</span></span>

<span data-ttu-id="34d9d-151">El personal de soporte técnico de Microsoft puede ayudarle a aprovisionar o desaprovisionar el servicio y los recursos relacionados en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="34d9d-151">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="34d9d-152">Para obtener ayuda, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34d9d-152">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="34d9d-153">Al ponerse en contacto con el soporte técnico, mencione Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="34d9d-153">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="34d9d-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="34d9d-154">Related topics</span></span>

- [<span data-ttu-id="34d9d-155">Introducción a la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="34d9d-155">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="34d9d-156">Requisitos de licencia y otros requisitos previos</span><span class="sxs-lookup"><span data-stu-id="34d9d-156">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="34d9d-157">Implementación de servicios compatibles</span><span class="sxs-lookup"><span data-stu-id="34d9d-157">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="34d9d-158">Introducción al ATP de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="34d9d-158">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="34d9d-159">Introducción al ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="34d9d-159">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="34d9d-160">Introducción a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="34d9d-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="34d9d-161">Introducción al ATP de Azure</span><span class="sxs-lookup"><span data-stu-id="34d9d-161">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="34d9d-162">Almacenamiento de datos del ATP de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="34d9d-162">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)