---
title: Activar Microsoft 365 defender en el centro de seguridad de Microsoft 365
description: Obtenga información sobre cómo habilitar Microsoft 365 defender e iniciar la integración de su incidente de seguridad y respuesta.
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
ms.openlocfilehash: fbe98b814b253551432ea35102f2bd6eeba921f8
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602096"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="d4f36-104">Activar Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="d4f36-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d4f36-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d4f36-105">**Applies to:**</span></span>
- <span data-ttu-id="d4f36-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4f36-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d4f36-107">[Microsoft 365 defender](microsoft-threat-protection.md) unifica el proceso de respuesta ante incidentes mediante la integración de capacidades clave en Microsoft defender para el punto de conexión, Microsoft defender para Office 365, Microsoft Cloud App Security y Microsoft defender para identidad.</span><span class="sxs-lookup"><span data-stu-id="d4f36-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="d4f36-108">Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4f36-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="d4f36-109">Microsoft 365 defender se activa automáticamente cuando los clientes elegibles con los permisos necesarios visitan el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4f36-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="d4f36-110">Lea este artículo para conocer los diversos requisitos previos y la forma en que se aprovisionó Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="d4f36-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="d4f36-111">Comprobar la elegibilidad de la licencia y los permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="d4f36-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="d4f36-112">Una licencia a un producto de seguridad 365 de Microsoft generalmente le da derecho a usar Microsoft 365 defender en el centro de seguridad de Microsoft 365 sin costo de licencias adicional.</span><span class="sxs-lookup"><span data-stu-id="d4f36-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="d4f36-113">Le recomendamos que obtenga una licencia de seguridad de Microsoft 365 E5, E5 Security, A5 o a5 o una combinación válida de licencias que proporcione acceso a todos los servicios admitidos.</span><span class="sxs-lookup"><span data-stu-id="d4f36-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="d4f36-114">Para obtener información detallada sobre la licencia, [Lea los requisitos de licencia](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="d4f36-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="d4f36-115">Comprobar el rol</span><span class="sxs-lookup"><span data-stu-id="d4f36-115">Check your role</span></span>
<span data-ttu-id="d4f36-116">Debe ser **administrador global** o **Administrador de seguridad** en Azure active directory para activar Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="d4f36-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="d4f36-117">Ver sus roles en Azure AD</span><span class="sxs-lookup"><span data-stu-id="d4f36-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="d4f36-118">Servicios admitidos</span><span class="sxs-lookup"><span data-stu-id="d4f36-118">Supported services</span></span>
<span data-ttu-id="d4f36-119">Microsoft 365 defender agrega datos de los diversos servicios compatibles que ya ha implementado.</span><span class="sxs-lookup"><span data-stu-id="d4f36-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="d4f36-120">Procesará y almacenará datos de forma centralizada para identificar nuevos conocimientos y hacer que los flujos de trabajo de respuesta centralizados sean posibles.</span><span class="sxs-lookup"><span data-stu-id="d4f36-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="d4f36-121">Lo hace sin afectar a las implementaciones, la configuración o los datos existentes asociados con los servicios integrados.</span><span class="sxs-lookup"><span data-stu-id="d4f36-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="d4f36-122">Para obtener la mejor protección y optimizar Microsoft 365 defender, se recomienda implementar todos los servicios admitidos aplicables en la red.</span><span class="sxs-lookup"><span data-stu-id="d4f36-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="d4f36-123">Para obtener más información, [Consulte acerca de la implementación de servicios compatibles](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="d4f36-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="d4f36-124">Antes de iniciar el servicio</span><span class="sxs-lookup"><span data-stu-id="d4f36-124">Before starting the service</span></span>
<span data-ttu-id="d4f36-125">Antes de activar el servicio, el centro de seguridad 365 de Microsoft ([Security.Microsoft.com](https://security.microsoft.com)) muestra la página de configuración de Microsoft 365 defender al seleccionar **incidentes**, **centro de actividades** o **caza** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="d4f36-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="d4f36-126">Estos elementos de navegación no se muestran si no es elegible para usar Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="d4f36-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="d4f36-127">![Imagen de la página de configuración de Microsoft 365 defender que se muestra si no se activó la configuración de Microsoft 365 defender ](../../media/mtp-enable/mtp-settings.png)
 *365 en Microsoft 365 Security Center*</span><span class="sxs-lookup"><span data-stu-id="d4f36-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="d4f36-128">Inicio del servicio</span><span class="sxs-lookup"><span data-stu-id="d4f36-128">Starting the service</span></span>
<span data-ttu-id="d4f36-129">Para activar Microsoft 365 defender, simplemente seleccione **Activar microsoft 365 defender** y aplicar el cambio.</span><span class="sxs-lookup"><span data-stu-id="d4f36-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="d4f36-130">También puede tener acceso a esta opción si selecciona **configuración** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) en el panel de navegación y, a continuación, selecciona **Microsoft 365 defender**.</span><span class="sxs-lookup"><span data-stu-id="d4f36-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

>[!NOTE]
><span data-ttu-id="d4f36-131">Si no ve la **configuración** en el panel de navegación o no pudo obtener acceso a la página, compruebe los permisos y las licencias.</span><span class="sxs-lookup"><span data-stu-id="d4f36-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="d4f36-132">Ubicación del centro de datos</span><span class="sxs-lookup"><span data-stu-id="d4f36-132">Data center location</span></span>
<span data-ttu-id="d4f36-133">Microsoft 365 defender almacenará y procesará datos en la [misma ubicación usada por Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="d4f36-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="d4f36-134">Si no tiene Microsoft defender para el punto de conexión, se selecciona automáticamente una nueva ubicación del centro de datos en función de la ubicación de los servicios de seguridad de Microsoft 365 activos.</span><span class="sxs-lookup"><span data-stu-id="d4f36-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="d4f36-135">La ubicación del centro de datos seleccionada se muestra en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="d4f36-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="d4f36-136">Seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365, póngase en contacto con el soporte técnico de Microsoft sobre el aprovisionamiento de Microsoft 365 defender en una ubicación diferente del centro de datos.</span><span class="sxs-lookup"><span data-stu-id="d4f36-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="d4f36-137">Microsoft defender for Endpoint se aprovisiona automáticamente en los centros de datos de la Unión Europea (UE) cuando se activa a través de Azure defender.</span><span class="sxs-lookup"><span data-stu-id="d4f36-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="d4f36-138">Microsoft 365 defender aprovisionará automáticamente en el mismo centro de datos de la UE para los clientes que hayan proporcionado defender para el punto de conexión de esta manera.</span><span class="sxs-lookup"><span data-stu-id="d4f36-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="d4f36-139">Confirme que el servicio está activado</span><span class="sxs-lookup"><span data-stu-id="d4f36-139">Confirm that the service is on</span></span>
<span data-ttu-id="d4f36-140">Una vez que recibe el servicio, este agrega:</span><span class="sxs-lookup"><span data-stu-id="d4f36-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="d4f36-141">Administración de incidentes</span><span class="sxs-lookup"><span data-stu-id="d4f36-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="d4f36-142">Un centro de actividades para administrar [una investigación y respuestas automáticas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="d4f36-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="d4f36-143">Funcionalidades de [búsqueda avanzada](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d4f36-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="d4f36-144">![Imagen del panel de navegación del centro de seguridad de Microsoft 365 con Microsoft 365 para el ](../../media/mtp-enable/mtp-on.png)
 *centro de seguridad de Microsoft 365 con administración de incidentes y otras capacidades de Microsoft 365 defender*</span><span class="sxs-lookup"><span data-stu-id="d4f36-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="d4f36-145">Obtención de Microsoft defender para datos de identidad</span><span class="sxs-lookup"><span data-stu-id="d4f36-145">Getting Microsoft Defender for Identity data</span></span>
<span data-ttu-id="d4f36-146">Para compartir Microsoft defender para obtener datos de identidad con Microsoft 365 defender, asegúrese de que la opción Microsoft Cloud App Security y Microsoft defender para la integración de identidades están activadas.</span><span class="sxs-lookup"><span data-stu-id="d4f36-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> [<span data-ttu-id="d4f36-147">Infórmese de esta integración</span><span class="sxs-lookup"><span data-stu-id="d4f36-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="get-assistance"></a><span data-ttu-id="d4f36-148">Cómo recibir asistencia</span><span class="sxs-lookup"><span data-stu-id="d4f36-148">Get assistance</span></span>

<span data-ttu-id="d4f36-149">Para obtener respuestas a las preguntas más comunes sobre cómo activar Microsoft 365 defender, [Lea las preguntas más frecuentes](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d4f36-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="d4f36-150">El personal de soporte técnico de Microsoft puede ayudarle a aprovisionar o desaprovisionar el servicio y los recursos relacionados en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="d4f36-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="d4f36-151">Para obtener ayuda, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4f36-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="d4f36-152">Al ponerse en contacto con el soporte técnico, mencione Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="d4f36-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d4f36-153">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d4f36-153">Related topics</span></span>

- [<span data-ttu-id="d4f36-154">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="d4f36-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="d4f36-155">Requisitos de licencia y otros requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d4f36-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="d4f36-156">Implementación de servicios compatibles</span><span class="sxs-lookup"><span data-stu-id="d4f36-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="d4f36-157">Información general de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="d4f36-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="d4f36-158">Información general de Microsoft defender para Endpoint</span><span class="sxs-lookup"><span data-stu-id="d4f36-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="d4f36-159">Información general de defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d4f36-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="d4f36-160">Introducción a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d4f36-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="d4f36-161">Información general de Microsoft defender para identidad</span><span class="sxs-lookup"><span data-stu-id="d4f36-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="d4f36-162">Microsoft defender para el almacenamiento de datos de extremo</span><span class="sxs-lookup"><span data-stu-id="d4f36-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
