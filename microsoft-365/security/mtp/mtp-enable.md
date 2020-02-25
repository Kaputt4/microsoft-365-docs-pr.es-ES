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
ms.openlocfilehash: 73f76dee8a59229138f906e593a84220c7f70aee
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235219"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="8ca0a-104">Habilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ca0a-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="8ca0a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8ca0a-105">**Applies to:**</span></span>
- <span data-ttu-id="8ca0a-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ca0a-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="8ca0a-107">La Protección contra amenazas de Microsoft unifica el proceso de respuesta a incidentes de seguridad mediante la integración de las capacidades clave en la Protección contra amenazas avanzada (ATP) de Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="8ca0a-108">Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="8ca0a-109">Comprobar la elegibilidad de la licencia y los permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="8ca0a-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="8ca0a-110">Los clientes con Microsoft 365 E5, la seguridad de Microsoft 365 E5 o una combinación equivalente de licencias pueden usar la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-110">Customers with Microsoft 365 E5, Microsoft 365 E5 Security, or an equivalent combination of licenses can use Microsoft Threat Protection.</span></span> <span data-ttu-id="8ca0a-111">Para obtener más información, [lea los requisitos de licencia](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="8ca0a-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

<span data-ttu-id="8ca0a-112">Debe ser **administrador global** o **Administrador de seguridad** en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para activar la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-112">You must be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to turn on Microsoft Threat Protection.</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="8ca0a-113">Empiece a usar el servicio</span><span class="sxs-lookup"><span data-stu-id="8ca0a-113">Start using the service</span></span>
<span data-ttu-id="8ca0a-114">Microsoft Threat Protection agrega datos de los diversos servicios integrados.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-114">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="8ca0a-115">Procesará y almacenará datos de forma centralizada para identificar nuevos conocimientos y hacer que los flujos de trabajo de respuesta centralizados sean posibles.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-115">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="8ca0a-116">Antes de activar el servicio, el centro de seguridad 365 de Microsoft ([Security.Microsoft.com](https://security.microsoft.com)) no muestra los **incidentes** ni las opciones del **centro de actividades** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-116">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) doesn't show the **Incidents** and the **Action center** options in the navigation pane.</span></span>

<span data-ttu-id="8ca0a-117">![Imagen del panel de navegación del centro de seguridad de Microsoft 365 sin](../../media/mtp-off.png)
Microsoft Threats Features Microsoft*365 centro de seguridad con Microsoft Threat Protection* desactivado</span><span class="sxs-lookup"><span data-stu-id="8ca0a-117">![Image of Microsoft 365 security center navigation pane without Microsoft Threat Protection features](../../media/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="8ca0a-118">Para activar la protección contra amenazas de Microsoft, seleccione **configuración** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-118">To turn on Microsoft Threat Protection, select **Settings** in the navigation pane.</span></span> <span data-ttu-id="8ca0a-119">En la **[página Configuración](https://security.microsoft.com/settings)**, vaya a la**opción de activación/exclusión**de **Microsoft Threat Protection** > .</span><span class="sxs-lookup"><span data-stu-id="8ca0a-119">In the **[Settings page](https://security.microsoft.com/settings)**, go to **Microsoft Threat Protection** > **Opt-in / Opt-out**.</span></span>

>[!NOTE]
><span data-ttu-id="8ca0a-120">Si no ve la **configuración** en el panel de navegación o no pudo obtener acceso a la página, compruebe los permisos y las licencias.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-120">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="8ca0a-121">Seleccionar la ubicación del centro de datos</span><span class="sxs-lookup"><span data-stu-id="8ca0a-121">Select data center location</span></span>
<span data-ttu-id="8ca0a-122">Si su organización dispone de ATP de Microsoft Defender, los datos se almacenarán y procesarán en la misma ubicación del centro de datos que seleccionara para [sus datos de ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="8ca0a-122">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="8ca0a-123">Si no tiene ATP de Microsoft defender, se le pedirá que elija una nueva ubicación del centro de datos específicamente para la Protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-123">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="8ca0a-124">Debe proporcionar el consentimiento antes de que los datos se compartan entre los servicios y se agreguen.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-124">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="8ca0a-125">Confirme que el servicio está activado</span><span class="sxs-lookup"><span data-stu-id="8ca0a-125">Confirm that the service is on</span></span>
<span data-ttu-id="8ca0a-126">Una vez que recibe el servicio, este agrega:</span><span class="sxs-lookup"><span data-stu-id="8ca0a-126">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="8ca0a-127">Administración de incidentes</span><span class="sxs-lookup"><span data-stu-id="8ca0a-127">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="8ca0a-128">Un centro de actividades para administrar [una investigación y respuestas automáticas](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="8ca0a-128">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="8ca0a-129">[Características de búsqueda](advanced-hunting-overview.md) avanzadas en la página de **Búsqueda**</span><span class="sxs-lookup"><span data-stu-id="8ca0a-129">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="8ca0a-130">![Imagen del panel de navegación del centro de seguridad de Microsoft 365 con](../../media/mtp-on.png)
Microsoft Threat Protection características de*Microsoft 365 Security Center con incidentes de administración de incidentes y otras capacidades de protección contra amenazas de Microsoft*</span><span class="sxs-lookup"><span data-stu-id="8ca0a-130">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="8ca0a-131">Obtener datos de Azure ATP</span><span class="sxs-lookup"><span data-stu-id="8ca0a-131">Getting Azure ATP data</span></span>
<span data-ttu-id="8ca0a-132">Para compartir datos de Azure ATP con la Protección contra amenazas de Microsoft, asegúrese de que esté activada la integración entre Microsoft Cloud App Security y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-132">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="8ca0a-133">Infórmese de esta integración</span><span class="sxs-lookup"><span data-stu-id="8ca0a-133">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="8ca0a-134">Deshabilitar la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ca0a-134">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="8ca0a-135">Para dejar de usar la Protección contra amenazas de Microsoft, vaya a **Configuración** > \*\*\*\* Protección contra amenazas de Microsoft > \*\*\*\* Participar/No participar en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-135">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="8ca0a-136">Anule la selección de **Activar la Protección contra amenazas de Microsoft** y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-136">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="8ca0a-137">Los datos se eliminarán de forma permanente y se quitarán las características correspondientes del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-137">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="8ca0a-138">Cómo recibir asistencia</span><span class="sxs-lookup"><span data-stu-id="8ca0a-138">Get assistance</span></span>

<span data-ttu-id="8ca0a-139">El personal de soporte técnico de Microsoft puede ayudarle a aprovisionar o desaprovisionar el servicio y los recursos relacionados en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-139">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="8ca0a-140">Para obtener ayuda, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-140">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="8ca0a-141">Al ponerse en contacto con el soporte técnico, mencione Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-141">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8ca0a-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8ca0a-142">Related topics</span></span>

- [<span data-ttu-id="8ca0a-143">Introducción a la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ca0a-143">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="8ca0a-144">Requisitos de licencia y otros requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8ca0a-144">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="8ca0a-145">Introducción al ATP de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8ca0a-145">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="8ca0a-146">Introducción al ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="8ca0a-146">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="8ca0a-147">Introducción a Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8ca0a-147">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="8ca0a-148">Introducción al ATP de Azure</span><span class="sxs-lookup"><span data-stu-id="8ca0a-148">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="8ca0a-149">Almacenamiento de datos del ATP de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8ca0a-149">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
