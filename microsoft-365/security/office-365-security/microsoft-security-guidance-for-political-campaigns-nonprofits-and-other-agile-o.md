---
title: 'Guía de seguridad de Microsoft: campañas políticas y ONG'
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom:
- Strat_O365_Enterprise
- seo-marvel-apr2020
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: 'Resumen: instrucciones de planeamiento e implementación para organizaciones rápidas con un mayor perfil de amenaza.'
ms.openlocfilehash: 79384277ec470d5545e9fe8127a95532e892fb45
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307888"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="21421-103">Guía de seguridad de Microsoft para campañas políticas, ONG y otras organizaciones ágiles</span><span class="sxs-lookup"><span data-stu-id="21421-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

 <span data-ttu-id="21421-104">**Resumen:** instrucciones de planeamiento e implementación para organizaciones rápidas con un mayor perfil de amenaza.</span><span class="sxs-lookup"><span data-stu-id="21421-104">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>

<span data-ttu-id="21421-p101">Si su organización es ágil, tiene un pequeño equipo de TI y el perfil de amenaza es superior a la media, estas instrucciones están diseñadas para usted. Esta solución muestra cómo compilar rápidamente un entorno con servicios de nube esenciales que incluyen controles seguros desde el principio. Estas instrucciones incluyen recomendaciones de seguridad prescriptivas para proteger los datos, las identidades, el correo electrónico y el acceso desde dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="21421-p101">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you. This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start. This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>

## <a name="security-solution-guidance"></a><span data-ttu-id="21421-108">Instrucciones de solución de seguridad</span><span class="sxs-lookup"><span data-stu-id="21421-108">Security solution guidance</span></span>

<span data-ttu-id="21421-p102">Estas instrucciones explican cómo implementar un entorno de nube seguro. Las instrucciones de solución se pueden usar en cualquier organización. Incluyen ayuda adicional para organizaciones ágiles con cuentas de acceso BYOD e invitado. Puede usarlas como un punto de partida para diseñar un entorno propio. Agradecemos sus comentarios en [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="21421-p102">This guidance describes how to implement a secure cloud environment. The solution guidance can be used by any organization. It includes extra help for agile organizations with BYOD access and guest accounts. You can use this guidance as a starting-point for designing your own environment. We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span>

****

|<span data-ttu-id="21421-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="21421-114">Item</span></span>|<span data-ttu-id="21421-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="21421-115">Description</span></span>|
|---|---|
|<span data-ttu-id="21421-116">**Guía de seguridad de Microsoft para campañas políticas**</span><span class="sxs-lookup"><span data-stu-id="21421-116">**Microsoft Security Guidance for Political Campaigns**</span></span> <br/> <span data-ttu-id="21421-117">[![Miniatura de conjunto de minipósteres.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="21421-117">[![Thumbnail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br/> <span data-ttu-id="21421-118">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)  \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="21421-118">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)  \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span>|<span data-ttu-id="21421-p103">En esta guía, se usa una organización de campaña política como ejemplo. Use esta guía como punto inicial para cualquier entorno.</span><span class="sxs-lookup"><span data-stu-id="21421-p103">This guidance uses a political campaign organization as an example. Use this guidance as a starting point for any environment.</span></span>|
|<span data-ttu-id="21421-121">**Guía de seguridad de Microsoft para ONG**</span><span class="sxs-lookup"><span data-stu-id="21421-121">**Microsoft Security Guidance for Nonprofits**</span></span> <br/> <span data-ttu-id="21421-122">[![Imagen en miniatura de archivo descargable](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="21421-122">[![Thumbnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br/> <span data-ttu-id="21421-123">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)  \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="21421-123">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)  \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span>|<span data-ttu-id="21421-p104">Estas Instrucciones se han modificado ligeramente para las organizaciones sin ánimo de lucro. Por ejemplo, hacen referencia a los planes sin ánimo de lucro de Office 365. Las instrucciones técnicas son las mismas que las de campaña política.</span><span class="sxs-lookup"><span data-stu-id="21421-p104">This guide is slightly revised for nonprofit organizations. For example, it references Office 365 Nonprofit plans. The technical guidance is the same as the political campaign solution guide.</span></span>|
|

## <a name="test-lab-guides"></a><span data-ttu-id="21421-127">Guías del entorno de pruebas</span><span class="sxs-lookup"><span data-stu-id="21421-127">Test Lab Guides</span></span>

<span data-ttu-id="21421-128">Para crear un entorno de desarrollo y pruebas para esta solución, siga estas guías del entorno de pruebas:</span><span class="sxs-lookup"><span data-stu-id="21421-128">To create a dev/test environment for this solution, use the following test lab guides:</span></span>

- [<span data-ttu-id="21421-129">Configurar grupos y usuarios en un entorno de desarrollo y pruebas de campaña política</span><span class="sxs-lookup"><span data-stu-id="21421-129">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="21421-130">Cree suscripciones de prueba para Office 365 y EMS y, después, cree grupos y usuarios para una campaña política de un representante.</span><span class="sxs-lookup"><span data-stu-id="21421-130">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>

- [<span data-ttu-id="21421-131">Crear sitios de grupo en un entorno de desarrollo y pruebas de campaña política</span><span class="sxs-lookup"><span data-stu-id="21421-131">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="21421-132">Cree cuatro sitios de grupo de SharePoint Online con niveles de seguridad “Interno”, “Privado”, “Confidencial” y “Altamente confidencial”.</span><span class="sxs-lookup"><span data-stu-id="21421-132">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>

<span data-ttu-id="21421-133">Para obtener características de seguridad adicionales como demostración o prueba de concepto, vea [Guías del entorno de pruebas de Office 365](https://aka.ms/o365tlgs).</span><span class="sxs-lookup"><span data-stu-id="21421-133">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](https://aka.ms/o365tlgs).</span></span>

## <a name="see-also"></a><span data-ttu-id="21421-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="21421-134">See Also</span></span>

[<span data-ttu-id="21421-135">Guías del entorno de pruebas de adopción de la nube (TLG)</span><span class="sxs-lookup"><span data-stu-id="21421-135">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="21421-136">Recursos de arquitectura de TI de Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="21421-136">Microsoft Cloud IT architecture resources</span></span>](https://docs.microsoft.com/microsoft-365/solutions/cloud-architecture-models)
