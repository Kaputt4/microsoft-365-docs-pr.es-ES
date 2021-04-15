---
title: Activar Microsoft 365 Defender en el Centro de seguridad de Microsoft 365
description: Obtenga información sobre cómo habilitar Microsoft 365 Defender y empezar a integrar el incidente de seguridad y la respuesta.
keywords: get started, enable MTP, Microsoft Threat Protection, M365, security, data location, required permissions, license eligibility, settings page
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: bf8fdb2a8a42ef7b70b744cbbb5663e6afe51989
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764390"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="919ff-104">Activar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="919ff-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="919ff-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="919ff-105">**Applies to:**</span></span>
- <span data-ttu-id="919ff-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="919ff-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="919ff-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifica el proceso de respuesta a incidentes integrando funciones clave en Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="919ff-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="919ff-108">Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="919ff-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="919ff-109">Microsoft 365 Defender se activa automáticamente cuando los clientes elegibles con los permisos necesarios visitan el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="919ff-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="919ff-110">Lea este artículo para comprender varios requisitos previos y cómo se aprovisiona Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="919ff-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="919ff-111">Comprobar la elegibilidad de la licencia y los permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="919ff-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="919ff-112">Por lo general, una licencia de un producto de seguridad de Microsoft 365 le da derecho a usar Microsoft 365 Defender en el centro de seguridad de Microsoft 365 sin costo de licencia adicional.</span><span class="sxs-lookup"><span data-stu-id="919ff-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="919ff-113">Recomendamos obtener una licencia de seguridad de Microsoft 365 E5, E5, A5 o A5 o una combinación válida de licencias que proporciona acceso a todos los servicios compatibles.</span><span class="sxs-lookup"><span data-stu-id="919ff-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="919ff-114">Para obtener información detallada sobre las licencias, [lea los requisitos de licencia](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="919ff-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="919ff-115">Comprobar el rol</span><span class="sxs-lookup"><span data-stu-id="919ff-115">Check your role</span></span>

<span data-ttu-id="919ff-116">Debe ser un administrador **global o** un administrador **de seguridad** en Azure Active Directory para activar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="919ff-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="919ff-117">Ver los roles en Azure AD</span><span class="sxs-lookup"><span data-stu-id="919ff-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="919ff-118">Servicios compatibles</span><span class="sxs-lookup"><span data-stu-id="919ff-118">Supported services</span></span>

<span data-ttu-id="919ff-119">Microsoft 365 Defender agrega datos de los distintos servicios compatibles que ya ha implementado.</span><span class="sxs-lookup"><span data-stu-id="919ff-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="919ff-120">Procesará y almacenará datos de forma centralizada para identificar nuevos conocimientos y hacer posibles los flujos de trabajo de respuesta centralizados.</span><span class="sxs-lookup"><span data-stu-id="919ff-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="919ff-121">Lo hace sin afectar a las implementaciones, la configuración o los datos existentes asociados con los servicios integrados.</span><span class="sxs-lookup"><span data-stu-id="919ff-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="919ff-122">Para obtener la mejor protección y optimizar Microsoft 365 Defender, se recomienda implementar todos los servicios compatibles aplicables en la red.</span><span class="sxs-lookup"><span data-stu-id="919ff-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="919ff-123">Para obtener más información, [lea acerca de la implementación de servicios compatibles.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="919ff-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="919ff-124">Incorporación al servicio</span><span class="sxs-lookup"><span data-stu-id="919ff-124">Onboard to the service</span></span>
<span data-ttu-id="919ff-125">La incorporación a Microsoft 365 Defender es sencilla.</span><span class="sxs-lookup"><span data-stu-id="919ff-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="919ff-126">En el menú de navegación, seleccione cualquier elemento de la sección Puntos de conexión, como Incidentes, Búsqueda, Centro de acción o Análisis de amenazas para iniciar el proceso de incorporación.</span><span class="sxs-lookup"><span data-stu-id="919ff-126">From the navigation menu, select any item under the Endpoints section, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="919ff-127">Ubicación del centro de datos</span><span class="sxs-lookup"><span data-stu-id="919ff-127">Data center location</span></span>

<span data-ttu-id="919ff-128">Microsoft 365 Defender almacenará y procesará datos en la misma ubicación usada por [Microsoft Defender para Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="919ff-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="919ff-129">Si no tiene Microsoft Defender para endpoint, se selecciona automáticamente una nueva ubicación del centro de datos en función de la ubicación de los servicios de seguridad de Microsoft 365 activos.</span><span class="sxs-lookup"><span data-stu-id="919ff-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="919ff-130">La ubicación del centro de datos seleccionada se muestra en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="919ff-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="919ff-131">Seleccione **¿Necesita ayuda?** en el Centro de seguridad de Microsoft 365 para ponerse en contacto con el soporte técnico de Microsoft sobre el aprovisionamiento de Microsoft 365 Defender en una ubicación diferente del centro de datos.</span><span class="sxs-lookup"><span data-stu-id="919ff-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="919ff-132">Microsoft Defender para endpoint aprovisiona automáticamente en centros de datos de la Unión Europea (UE) cuando se activa a través de Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="919ff-132">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="919ff-133">Microsoft 365 Defender aprovisionará automáticamente en el mismo centro de datos de la UE a los clientes que han aprovisionado Defender para Endpoint de esta manera.</span><span class="sxs-lookup"><span data-stu-id="919ff-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="919ff-134">Confirme que el servicio está activado</span><span class="sxs-lookup"><span data-stu-id="919ff-134">Confirm that the service is on</span></span>

<span data-ttu-id="919ff-135">Una vez que recibe el servicio, este agrega:</span><span class="sxs-lookup"><span data-stu-id="919ff-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="919ff-136">Administración de incidentes</span><span class="sxs-lookup"><span data-stu-id="919ff-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="919ff-137">Cola de alertas</span><span class="sxs-lookup"><span data-stu-id="919ff-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="919ff-138">Un centro de actividades para administrar [una investigación y respuestas automáticas](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="919ff-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="919ff-139">[Capacidades avanzadas de](advanced-hunting-overview.md) búsqueda</span><span class="sxs-lookup"><span data-stu-id="919ff-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="919ff-140">Análisis de amenazas</span><span class="sxs-lookup"><span data-stu-id="919ff-140">Threat analytics</span></span>

<span data-ttu-id="919ff-141">![Imagen del panel de navegación del centro de seguridad de Microsoft 365 con Microsoft 365 Defender cuenta con el Centro de seguridad de Microsoft 365 con administración de incidentes y otras funcionalidades de ](../../media/overview-incident.png)
 *Microsoft 365 Defender*</span><span class="sxs-lookup"><span data-stu-id="919ff-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/overview-incident.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="919ff-142">Obtener datos de Microsoft Defender para identidades</span><span class="sxs-lookup"><span data-stu-id="919ff-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="919ff-143">Para habilitar la integración con Microsoft Cloud App Security, tendrás que iniciar sesión en Microsoft Cloud App Security al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="919ff-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="919ff-144">Cómo recibir asistencia</span><span class="sxs-lookup"><span data-stu-id="919ff-144">Get assistance</span></span>

<span data-ttu-id="919ff-145">Para obtener respuestas a las preguntas más frecuentes sobre cómo activar Microsoft 365 Defender, [lea las preguntas más frecuentes](m365d-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="919ff-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="919ff-146">El personal de soporte técnico de Microsoft puede ayudar a aprovisionar o desaprovisionar el servicio y los recursos relacionados en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="919ff-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="919ff-147">Para obtener ayuda, seleccione **¿Necesita ayuda?** en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="919ff-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="919ff-148">Al ponerse en contacto con el soporte técnico, mencione Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="919ff-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="919ff-149">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="919ff-149">Related topics</span></span>

- [<span data-ttu-id="919ff-150">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="919ff-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="919ff-151">Requisitos de licencia y otros requisitos previos</span><span class="sxs-lookup"><span data-stu-id="919ff-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="919ff-152">Implementación de servicios compatibles</span><span class="sxs-lookup"><span data-stu-id="919ff-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="919ff-153">Introducción a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="919ff-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="919ff-154">Introducción a Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="919ff-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="919ff-155">Información general de Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="919ff-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="919ff-156">Introducción a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="919ff-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="919ff-157">Introducción a Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="919ff-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="919ff-158">Microsoft Defender para el almacenamiento de datos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="919ff-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
