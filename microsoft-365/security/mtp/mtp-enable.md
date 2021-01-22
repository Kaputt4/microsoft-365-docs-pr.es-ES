---
title: Activar Microsoft 365 Defender en el Centro de seguridad de Microsoft 365
description: Obtenga información sobre cómo habilitar Microsoft 365 Defender y empezar a integrar la respuesta y el incidente de seguridad.
keywords: introducción, habilitar MTP, Protección contra amenazas de Microsoft, M365, seguridad, ubicación de datos, permisos necesarios, elegibilidad de licencia, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930227"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="dd8bf-104">Activar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd8bf-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dd8bf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="dd8bf-105">**Applies to:**</span></span>
- <span data-ttu-id="dd8bf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd8bf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="dd8bf-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifica el proceso de respuesta a incidentes mediante la integración de funcionalidades clave en Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender para Identity.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="dd8bf-108">Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="dd8bf-109">Microsoft 365 Defender se activa automáticamente cuando los clientes elegibles con los permisos necesarios visitan el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="dd8bf-110">Lea este artículo para comprender varios requisitos previos y cómo se aprovisiona Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="dd8bf-111">Comprobar la elegibilidad de la licencia y los permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="dd8bf-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="dd8bf-112">Por lo general, una licencia para un producto de seguridad de Microsoft 365 le da derecho a usar Microsoft 365 Defender en el Centro de seguridad de Microsoft 365 sin costo de licencia adicional.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="dd8bf-113">Se recomienda obtener una licencia de Seguridad de Microsoft 365 E5, E5, A5 o A5 o una combinación válida de licencias que proporciona acceso a todos los servicios admitidos.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="dd8bf-114">Para obtener información detallada acerca de las licencias, [lea los requisitos de licencia.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="dd8bf-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="dd8bf-115">Comprobar el rol</span><span class="sxs-lookup"><span data-stu-id="dd8bf-115">Check your role</span></span>

<span data-ttu-id="dd8bf-116">Debe ser administrador **global o** **administrador** de seguridad en Azure Active Directory para activar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="dd8bf-117">Ver los roles en Azure AD</span><span class="sxs-lookup"><span data-stu-id="dd8bf-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="dd8bf-118">Servicios admitidos</span><span class="sxs-lookup"><span data-stu-id="dd8bf-118">Supported services</span></span>

<span data-ttu-id="dd8bf-119">Microsoft 365 Defender agrega datos de los distintos servicios compatibles que ya ha implementado.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="dd8bf-120">Procesará y almacenará datos de forma centralizada para identificar nuevas perspectivas y hacer posibles los flujos de trabajo de respuesta centralizados.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="dd8bf-121">Lo hace sin afectar a las implementaciones, la configuración o los datos existentes asociados con los servicios integrados.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="dd8bf-122">Para obtener la mejor protección y optimizar Microsoft 365 Defender, se recomienda implementar todos los servicios compatibles aplicables en la red.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="dd8bf-123">Para obtener más información, [lea acerca de la implementación de los servicios admitidos.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="dd8bf-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="dd8bf-124">Antes de iniciar el servicio</span><span class="sxs-lookup"><span data-stu-id="dd8bf-124">Before starting the service</span></span>

<span data-ttu-id="dd8bf-125">Antes de activar el servicio, el Centro de seguridad de Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)) muestra la página de  configuración de Microsoft 365 Defender cuando selecciona **Incidentes,** Centro de actividades o Búsqueda en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="dd8bf-126">Estos elementos de navegación no se muestran si no es apto para usar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="dd8bf-127">![Imagen de la página de configuración de Microsoft 365 Defender que se muestra si Microsoft 365 Defender no se ha activado en la configuración de Microsoft 365 Defender en el Centro de seguridad de ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="dd8bf-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="dd8bf-128">Inicio del servicio</span><span class="sxs-lookup"><span data-stu-id="dd8bf-128">Starting the service</span></span>

<span data-ttu-id="dd8bf-129">Para activar Microsoft 365 Defender, solo tiene que seleccionar **Activar Microsoft 365 Defender** y aplicar el cambio.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="dd8bf-130">También puede obtener acceso a esta opción seleccionando Configuración **(** [security.microsoft.com/settings](https://security.microsoft.com/settings)) en el panel de navegación y, a continuación, **seleccionando Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="dd8bf-131">Si no ve Configuración **en** el panel de navegación o no puede acceder a la página, compruebe sus permisos y licencias.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="dd8bf-132">Ubicación del centro de datos</span><span class="sxs-lookup"><span data-stu-id="dd8bf-132">Data center location</span></span>

<span data-ttu-id="dd8bf-133">Microsoft 365 Defender almacenará y procesará datos en la misma ubicación usada por [Microsoft Defender para Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="dd8bf-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="dd8bf-134">Si no tiene Microsoft Defender para endpoint, se selecciona automáticamente una nueva ubicación del centro de datos en función de la ubicación de los servicios de seguridad de Microsoft 365 activos.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="dd8bf-135">La ubicación del centro de datos seleccionado se muestra en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="dd8bf-136">Seleccione **¿Necesita ayuda?** en el Centro de seguridad de Microsoft 365 para ponerse en contacto con el soporte técnico de Microsoft sobre el aprovisionamiento de Microsoft 365 Defender en una ubicación diferente del centro de datos.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="dd8bf-137">Microsoft Defender para puntos de conexión aprovisiona automáticamente en centros de datos de la Unión Europea (UE) cuando se activa a través de Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="dd8bf-138">Microsoft 365 Defender aprovisionará automáticamente en el mismo centro de datos de la UE a los clientes que han aprovisionado Defender para Endpoint de esta manera.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="dd8bf-139">Confirme que el servicio está activado</span><span class="sxs-lookup"><span data-stu-id="dd8bf-139">Confirm that the service is on</span></span>

<span data-ttu-id="dd8bf-140">Una vez que recibe el servicio, este agrega:</span><span class="sxs-lookup"><span data-stu-id="dd8bf-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="dd8bf-141">Administración de incidentes</span><span class="sxs-lookup"><span data-stu-id="dd8bf-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="dd8bf-142">Un centro de actividades para administrar [una investigación y respuestas automáticas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="dd8bf-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="dd8bf-143">[Capacidades avanzadas de](advanced-hunting-overview.md) búsqueda</span><span class="sxs-lookup"><span data-stu-id="dd8bf-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="dd8bf-144">![Imagen del panel de navegación del Centro de seguridad de Microsoft 365 con El Centro de seguridad de Microsoft 365 Defender incluye el Centro de seguridad de Microsoft 365 con la administración de incidentes y otras capacidades de ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender*</span><span class="sxs-lookup"><span data-stu-id="dd8bf-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="dd8bf-145">Obtener datos de Microsoft Defender para identidades</span><span class="sxs-lookup"><span data-stu-id="dd8bf-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="dd8bf-146">Para compartir datos de Identidad de Microsoft Defender con Microsoft 365 Defender, asegúrese de que la integración de Microsoft Cloud App Security y Microsoft Defender for Identity esté activada.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="dd8bf-147">[Obtenga más información sobre esta integración.](https://docs.microsoft.com/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="dd8bf-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="dd8bf-148">Cómo recibir asistencia</span><span class="sxs-lookup"><span data-stu-id="dd8bf-148">Get assistance</span></span>

<span data-ttu-id="dd8bf-149">Para obtener respuestas a las preguntas más frecuentes sobre cómo activar Microsoft 365 Defender, [lea las preguntas más frecuentes.](mtp-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="dd8bf-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="dd8bf-150">El personal de soporte técnico de Microsoft puede ayudar a aprovisionar o desaprovisionar el servicio y los recursos relacionados en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="dd8bf-151">Para obtener ayuda, seleccione **¿Necesita ayuda?** en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="dd8bf-152">Al ponerse en contacto con el soporte técnico, mencione Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="dd8bf-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dd8bf-153">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="dd8bf-153">Related topics</span></span>

- [<span data-ttu-id="dd8bf-154">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="dd8bf-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="dd8bf-155">Requisitos de licencia y otros requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dd8bf-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="dd8bf-156">Implementación de servicios compatibles</span><span class="sxs-lookup"><span data-stu-id="dd8bf-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="dd8bf-157">Introducción a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd8bf-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="dd8bf-158">Introducción a Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="dd8bf-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="dd8bf-159">Información general de Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="dd8bf-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="dd8bf-160">Introducción a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dd8bf-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="dd8bf-161">Introducción a Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="dd8bf-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="dd8bf-162">Microsoft Defender para el almacenamiento de datos de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="dd8bf-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
