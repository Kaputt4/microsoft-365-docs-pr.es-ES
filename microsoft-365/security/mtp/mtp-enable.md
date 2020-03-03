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
ms.openlocfilehash: 73c4c9864713432d318b0b3cec9fbaf395deff45
ms.sourcegitcommit: 0df099d2e1028bbba8b6371dc5fcd021dddc902b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374151"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="2095f-104">Habilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2095f-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="2095f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2095f-105">**Applies to:**</span></span>
- <span data-ttu-id="2095f-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2095f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2095f-107">La Protección contra amenazas de Microsoft unifica el proceso de respuesta a incidentes de seguridad mediante la integración de las capacidades clave en la Protección contra amenazas avanzada (ATP) de Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="2095f-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="2095f-108">Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2095f-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="2095f-109">Para obtener la mejor protección y optimizar la protección contra amenazas de Microsoft, se recomienda implementar todos los servicios admitidos aplicables en la red.</span><span class="sxs-lookup"><span data-stu-id="2095f-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="2095f-110">Para obtener más información, [Consulte acerca de la implementación de servicios compatibles](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="2095f-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="2095f-111">Comprobar la elegibilidad de la licencia y los permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="2095f-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="2095f-112">Una licencia de seguridad de Microsoft 365 E5, E5 Security, A5 o a5 o una combinación válida de licencias proporciona acceso a los servicios admitidos y le da derecho a usar la protección contra amenazas de Microsoft en el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2095f-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

<span data-ttu-id="2095f-113">Para obtener información detallada sobre la licencia, [Lea los requisitos de licencia](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="2095f-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="2095f-114">Comprobar el rol</span><span class="sxs-lookup"><span data-stu-id="2095f-114">Check your role</span></span>
<span data-ttu-id="2095f-115">Debe ser **administrador global** o **Administrador de seguridad** en Azure Active Directory para activar la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2095f-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="2095f-116">Ver sus roles en Azure AD</span><span class="sxs-lookup"><span data-stu-id="2095f-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="2095f-117">Empiece a usar el servicio</span><span class="sxs-lookup"><span data-stu-id="2095f-117">Start using the service</span></span>
<span data-ttu-id="2095f-118">Microsoft Threat Protection agrega datos de los diversos servicios integrados.</span><span class="sxs-lookup"><span data-stu-id="2095f-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="2095f-119">Procesará y almacenará datos de forma centralizada para identificar nuevos conocimientos y hacer que los flujos de trabajo de respuesta centralizados sean posibles.</span><span class="sxs-lookup"><span data-stu-id="2095f-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="2095f-120">Antes de activar el servicio, el centro de seguridad de Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) muestra la página de bienvenida de Microsoft Threat Protection al seleccionar **incidentes**, **centro de actividades**o **caza** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="2095f-120">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="2095f-121">Estas opciones de navegación no se muestran si no es elegible para usar la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2095f-121">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="2095f-122">![Imagen de la página de bienvenida de Microsoft Threat Protection que se muestra si no se ha activado](../../media/mtp-welcome.png)
la protección contra amenazas de Microsoft en la*Página de bienvenida de Microsoft Threat Protection en el centro de seguridad de Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="2095f-122">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="2095f-123">Para activar la protección contra amenazas de Microsoft, simplemente complete el proceso desde la página de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="2095f-123">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="2095f-124">También puede activar Microsoft Threat Protection accediendo a la **configuración** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) en el panel de navegación y seleccionando **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="2095f-124">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="2095f-125">Si no ve la **configuración** en el panel de navegación o no pudo obtener acceso a la página, compruebe los permisos y las licencias.</span><span class="sxs-lookup"><span data-stu-id="2095f-125">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="2095f-126">Seleccionar la ubicación del centro de datos</span><span class="sxs-lookup"><span data-stu-id="2095f-126">Select data center location</span></span>
<span data-ttu-id="2095f-127">Si su organización dispone de ATP de Microsoft Defender, los datos se almacenarán y procesarán en la misma ubicación del centro de datos que seleccionara para [sus datos de ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="2095f-127">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="2095f-128">Si no tiene ATP de Microsoft defender, se le pedirá que elija una nueva ubicación del centro de datos específicamente para la Protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2095f-128">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="2095f-129">Debe proporcionar el consentimiento antes de que los datos se compartan entre los servicios y se agreguen.</span><span class="sxs-lookup"><span data-stu-id="2095f-129">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="2095f-130">Confirme que el servicio está activado</span><span class="sxs-lookup"><span data-stu-id="2095f-130">Confirm that the service is on</span></span>
<span data-ttu-id="2095f-131">Una vez que recibe el servicio, este agrega:</span><span class="sxs-lookup"><span data-stu-id="2095f-131">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="2095f-132">Administración de incidentes</span><span class="sxs-lookup"><span data-stu-id="2095f-132">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="2095f-133">Un centro de actividades para administrar [una investigación y respuestas automáticas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="2095f-133">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="2095f-134">Funcionalidades de [búsqueda avanzada](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2095f-134">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="2095f-135">![Imagen del panel de navegación del centro de seguridad de Microsoft 365 con](../../media/mtp-on.png)
Microsoft Threat Protection características de*Microsoft 365 Security Center con incidentes de administración de incidentes y otras capacidades de protección contra amenazas de Microsoft*</span><span class="sxs-lookup"><span data-stu-id="2095f-135">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="2095f-136">Obtener datos de Azure ATP</span><span class="sxs-lookup"><span data-stu-id="2095f-136">Getting Azure ATP data</span></span>
<span data-ttu-id="2095f-137">Para compartir datos de Azure ATP con la Protección contra amenazas de Microsoft, asegúrese de que esté activada la integración entre Microsoft Cloud App Security y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="2095f-137">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="2095f-138">Infórmese de esta integración</span><span class="sxs-lookup"><span data-stu-id="2095f-138">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="2095f-139">Deshabilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2095f-139">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="2095f-140">Para dejar de usar la Protección contra amenazas de Microsoft, vaya a **Configuración** > \*\*\*\* Protección contra amenazas de Microsoft > \*\*\*\* Participar/No participar en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2095f-140">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="2095f-141">Anule la selección de **Activar la Protección contra amenazas de Microsoft** y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="2095f-141">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="2095f-142">Se quitarán las características correspondientes del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2095f-142">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="2095f-143">Cómo recibir asistencia</span><span class="sxs-lookup"><span data-stu-id="2095f-143">Get assistance</span></span>

<span data-ttu-id="2095f-144">El personal de soporte técnico de Microsoft puede ayudarle a aprovisionar o desaprovisionar el servicio y los recursos relacionados en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="2095f-144">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="2095f-145">Para obtener ayuda, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2095f-145">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="2095f-146">Al ponerse en contacto con el soporte técnico, mencione Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="2095f-146">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2095f-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2095f-147">Related topics</span></span>

- [<span data-ttu-id="2095f-148">Introducción a la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2095f-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="2095f-149">Requisitos de licencia y otros requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2095f-149">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="2095f-150">Implementación de servicios admitidos</span><span class="sxs-lookup"><span data-stu-id="2095f-150">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="2095f-151">Introducción al ATP de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2095f-151">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="2095f-152">Introducción al ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="2095f-152">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="2095f-153">Introducción a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2095f-153">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="2095f-154">Introducción al ATP de Azure</span><span class="sxs-lookup"><span data-stu-id="2095f-154">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="2095f-155">Almacenamiento de datos del ATP de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2095f-155">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
