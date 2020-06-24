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
ms.openlocfilehash: 0badae0d81b52b89c47f950b889109d4b9d35dda
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844613"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="7e786-104">Habilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e786-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="7e786-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7e786-105">**Applies to:**</span></span>
- <span data-ttu-id="7e786-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e786-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7e786-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifica el proceso de respuesta ante incidentes mediante la integración de capacidades clave en la protección contra amenazas avanzada de Microsoft defender (ATP), Office 365 ATP, Microsoft Cloud App Security y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="7e786-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="7e786-108">Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e786-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="7e786-109">La protección contra amenazas de Microsoft se activa automáticamente cuando los clientes elegibles con los permisos necesarios visitan el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e786-109">Microsoft Threat Protection automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="7e786-110">Lea este artículo para conocer varios requisitos previos y cómo se aprovisiona la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e786-110">Read this article to understand various prerequisites and how Microsoft Threat Protection is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="7e786-111">Comprobar la elegibilidad de la licencia y los permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="7e786-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="7e786-112">Una licencia a un producto de seguridad 365 de Microsoft generalmente le da derecho a usar Microsoft Threat Protection en el centro de seguridad de Microsoft 365 sin costo adicional de licencias.</span><span class="sxs-lookup"><span data-stu-id="7e786-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="7e786-113">Le recomendamos que obtenga una licencia de seguridad de Microsoft 365 E5, E5 Security, A5 o a5 o una combinación válida de licencias que proporcione acceso a todos los servicios admitidos.</span><span class="sxs-lookup"><span data-stu-id="7e786-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="7e786-114">Para obtener información detallada sobre la licencia, [Lea los requisitos de licencia](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="7e786-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="7e786-115">Comprobar el rol</span><span class="sxs-lookup"><span data-stu-id="7e786-115">Check your role</span></span>
<span data-ttu-id="7e786-116">Debe ser **administrador global** o **Administrador de seguridad** en Azure Active Directory para activar la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e786-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="7e786-117">Ver sus roles en Azure AD</span><span class="sxs-lookup"><span data-stu-id="7e786-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="7e786-118">Servicios admitidos</span><span class="sxs-lookup"><span data-stu-id="7e786-118">Supported services</span></span>
<span data-ttu-id="7e786-119">Microsoft Threat Protection agrega datos de los diversos servicios compatibles que ya ha implementado.</span><span class="sxs-lookup"><span data-stu-id="7e786-119">Microsoft Threat Protection aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="7e786-120">Procesará y almacenará datos de forma centralizada para identificar nuevos conocimientos y hacer que los flujos de trabajo de respuesta centralizados sean posibles.</span><span class="sxs-lookup"><span data-stu-id="7e786-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="7e786-121">Lo hace sin afectar a las implementaciones, la configuración o los datos existentes asociados con los servicios integrados.</span><span class="sxs-lookup"><span data-stu-id="7e786-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="7e786-122">Para obtener la mejor protección y optimizar la protección contra amenazas de Microsoft, se recomienda implementar todos los servicios admitidos aplicables en la red.</span><span class="sxs-lookup"><span data-stu-id="7e786-122">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="7e786-123">Para obtener más información, [Consulte acerca de la implementación de servicios compatibles](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="7e786-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="7e786-124">Antes de iniciar el servicio</span><span class="sxs-lookup"><span data-stu-id="7e786-124">Before starting the service</span></span>
<span data-ttu-id="7e786-125">Antes de activar el servicio, el centro de seguridad 365 de Microsoft ([Security.Microsoft.com](https://security.microsoft.com)) muestra la página de configuración de Microsoft Threat Protection al seleccionar **incidentes**, **centro de actividades**o **caza** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="7e786-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="7e786-126">Estos elementos de navegación no se muestran si no es elegible para usar la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e786-126">These navigation items are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="7e786-127">![Imagen de la página de configuración de Microsoft Threat Protection que se muestra si no se ha activado la protección contra amenazas de Microsoft en la ](../../media/mtp-enable/mtp-settings.png)
 *configuración de protección contra amenazas de Microsoft en el centro de seguridad de Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="7e786-127">![Image of the Microsoft Threat Protection settings page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft Threat Protection settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="7e786-128">Inicio del servicio</span><span class="sxs-lookup"><span data-stu-id="7e786-128">Starting the service</span></span>
<span data-ttu-id="7e786-129">Para activar la protección contra amenazas de Microsoft, simplemente seleccione **activar la protección contra amenazas de Microsoft** y aplicar el cambio.</span><span class="sxs-lookup"><span data-stu-id="7e786-129">To turn on Microsoft Threat Protection, simply select **Turn on Microsoft Threat Protection** and apply the change.</span></span> <span data-ttu-id="7e786-130">También puede tener acceso a esta opción si selecciona **configuración** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) en el panel de navegación y, a continuación, selecciona protección contra **amenazas de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="7e786-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="7e786-131">Si no ve la **configuración** en el panel de navegación o no pudo obtener acceso a la página, compruebe los permisos y las licencias.</span><span class="sxs-lookup"><span data-stu-id="7e786-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="7e786-132">Ubicación del centro de datos</span><span class="sxs-lookup"><span data-stu-id="7e786-132">Data center location</span></span>
<span data-ttu-id="7e786-133">Microsoft Threat Protection almacenará y procesará los datos en la [misma ubicación usada por ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="7e786-133">Microsoft Threat Protection will store and process data in the [same location used by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="7e786-134">Si no tiene Microsoft defender ATP, se selecciona automáticamente una nueva ubicación del centro de datos en función de la ubicación de los servicios de seguridad de Microsoft 365 activos.</span><span class="sxs-lookup"><span data-stu-id="7e786-134">If you don't have Microsoft Defender ATP, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="7e786-135">La ubicación del centro de datos seleccionada se muestra en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="7e786-135">The selected data center location is shown in the screen.</span></span>

>[!NOTE]
><span data-ttu-id="7e786-136">Seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365, póngase en contacto con el soporte técnico de Microsoft sobre provisión de la protección contra amenazas de Microsoft en otra ubicación del centro de datos.</span><span class="sxs-lookup"><span data-stu-id="7e786-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provision Microsoft Threat Protection in a different data center location.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="7e786-137">Confirme que el servicio está activado</span><span class="sxs-lookup"><span data-stu-id="7e786-137">Confirm that the service is on</span></span>
<span data-ttu-id="7e786-138">Una vez que recibe el servicio, este agrega:</span><span class="sxs-lookup"><span data-stu-id="7e786-138">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="7e786-139">Administración de incidentes</span><span class="sxs-lookup"><span data-stu-id="7e786-139">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="7e786-140">Un centro de actividades para administrar [una investigación y respuestas automáticas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="7e786-140">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="7e786-141">Funcionalidades de [búsqueda avanzada](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7e786-141">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="7e786-142">![Imagen del panel de navegación del centro de seguridad de Microsoft 365 con Microsoft Threat Protection características de ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Security Center con incidentes de administración de incidentes y otras capacidades de protección contra amenazas de Microsoft*</span><span class="sxs-lookup"><span data-stu-id="7e786-142">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="7e786-143">Obtener datos de Azure ATP</span><span class="sxs-lookup"><span data-stu-id="7e786-143">Getting Azure ATP data</span></span>
<span data-ttu-id="7e786-144">Para compartir datos de Azure ATP con la Protección contra amenazas de Microsoft, asegúrese de que esté activada la integración entre Microsoft Cloud App Security y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="7e786-144">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="7e786-145">Infórmese de esta integración</span><span class="sxs-lookup"><span data-stu-id="7e786-145">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="7e786-146">Deshabilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e786-146">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="7e786-147">Para dejar de usar la Protección contra amenazas de Microsoft, vaya a **Configuración** > \*\*\*\* Protección contra amenazas de Microsoft > \*\*\*\* Participar/No participar en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e786-147">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="7e786-148">Anule la selección **de activar la protección contra amenazas de Microsoft** y aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="7e786-148">Unselect **Turn on Microsoft Threat Protection** and apply the changes.</span></span>

<span data-ttu-id="7e786-149">Se quitarán las características correspondientes del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e786-149">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="7e786-150">Cómo recibir asistencia</span><span class="sxs-lookup"><span data-stu-id="7e786-150">Get assistance</span></span>

<span data-ttu-id="7e786-151">Para obtener respuestas a las preguntas más comunes sobre la activación de la protección contra amenazas de Microsoft, [Lea las preguntas más frecuentes](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="7e786-151">To get answers to the most commonly asked questions about turning on Microsoft Threat Protection, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="7e786-152">El personal de soporte técnico de Microsoft puede ayudarle a aprovisionar o desaprovisionar el servicio y los recursos relacionados en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="7e786-152">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="7e786-153">Para obtener ayuda, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e786-153">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="7e786-154">Al ponerse en contacto con el soporte técnico, mencione Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="7e786-154">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7e786-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7e786-155">Related topics</span></span>

- [<span data-ttu-id="7e786-156">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="7e786-156">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="7e786-157">Requisitos de licencia y otros requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7e786-157">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="7e786-158">Implementación de servicios compatibles</span><span class="sxs-lookup"><span data-stu-id="7e786-158">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="7e786-159">Introducción a la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e786-159">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="7e786-160">Introducción al ATP de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7e786-160">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="7e786-161">Introducción al ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="7e786-161">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="7e786-162">Introducción a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7e786-162">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="7e786-163">Introducción al ATP de Azure</span><span class="sxs-lookup"><span data-stu-id="7e786-163">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="7e786-164">Almacenamiento de datos del ATP de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7e786-164">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)