---
title: Sitios de grupo de SharePoint Online aislados
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Obtenga información sobre los sitios de grupo aislados de SharePoint Online incluidos usos, requisitos y características con los que se pueden usar.
ms.openlocfilehash: 0646ffc37256702844b550fd1beb841944b2d509
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819538"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="ee859-103">Sitios de grupo de SharePoint Online aislados</span><span class="sxs-lookup"><span data-stu-id="ee859-103">Isolated SharePoint Online team sites</span></span>

 <span data-ttu-id="ee859-104">**Resumen:** obtenga información sobre los usos de sitios de grupo de SharePoint Online aislados.</span><span class="sxs-lookup"><span data-stu-id="ee859-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="ee859-105">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee859-105">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span></span> <span data-ttu-id="ee859-106">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span><span class="sxs-lookup"><span data-stu-id="ee859-106">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span></span> <span data-ttu-id="ee859-107">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span><span class="sxs-lookup"><span data-stu-id="ee859-107">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>
  
<span data-ttu-id="ee859-108">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators.</span><span class="sxs-lookup"><span data-stu-id="ee859-108">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators.</span></span> <span data-ttu-id="ee859-109">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span><span class="sxs-lookup"><span data-stu-id="ee859-109">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="ee859-110">You might need an isolated site for the following:</span><span class="sxs-lookup"><span data-stu-id="ee859-110">You might need an isolated site for the following:</span></span>
  
- <span data-ttu-id="ee859-111">Un proyecto secreto en su organización.</span><span class="sxs-lookup"><span data-stu-id="ee859-111">A secret project within your organization.</span></span>
    
- <span data-ttu-id="ee859-112">La ubicación de propiedad intelectual altamente confidencial o valiosa para su organización.</span><span class="sxs-lookup"><span data-stu-id="ee859-112">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>
    
- <span data-ttu-id="ee859-113">Los recursos de una acción legal realizada por su organización o por la organización que sea objeto de esa acción legal.</span><span class="sxs-lookup"><span data-stu-id="ee859-113">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>
    
- <span data-ttu-id="ee859-114">Para compartir una suscripción de Microsoft 365 entre varias organizaciones que se superpongan parcialmente, pero que, en su mayoría, existan como entidades empresariales separadas.</span><span class="sxs-lookup"><span data-stu-id="ee859-114">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>
    
<span data-ttu-id="ee859-115">Estos son los requisitos para un sitio aislado:</span><span class="sxs-lookup"><span data-stu-id="ee859-115">Here are the requirements of an isolated site:</span></span>
  
- <span data-ttu-id="ee859-116">Solo los administradores de SharePoint Online pueden administrar el sitio, como la pertenencia a grupos para el acceso al sitio y la configuración de permisos personalizados.</span><span class="sxs-lookup"><span data-stu-id="ee859-116">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>
    
- <span data-ttu-id="ee859-117">Los miembros del sitio no pueden invitar a otros miembros al sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="ee859-117">Members of the site cannot invite other members to the team site.</span></span>
    
- <span data-ttu-id="ee859-118">Users who are not members of the isolated site cannot request access to the site.</span><span class="sxs-lookup"><span data-stu-id="ee859-118">Users who are not members of the isolated site cannot request access to the site.</span></span> <span data-ttu-id="ee859-119">They will receive an access denied web page when they attempt to access any URL associated with the site.</span><span class="sxs-lookup"><span data-stu-id="ee859-119">They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>
    
<span data-ttu-id="ee859-120">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span><span class="sxs-lookup"><span data-stu-id="ee859-120">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span></span> <span data-ttu-id="ee859-121">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span><span class="sxs-lookup"><span data-stu-id="ee859-121">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>
  
<span data-ttu-id="ee859-122">Un sitio aislado se puede usar con otras características, como:</span><span class="sxs-lookup"><span data-stu-id="ee859-122">An isolated site can be used with other features, such as:</span></span>
  
- <span data-ttu-id="ee859-123">Information Rights Management, para garantizar que los recursos del sitio permanezcan cifrados, incluso si se descargan localmente y se cargan en otro sitio que esté disponible para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="ee859-123">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>
    
- <span data-ttu-id="ee859-124">Prevención de pérdida de datos para impedir que los usuarios envíen los recursos del sitio, como archivos, por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ee859-124">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="ee859-125">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ee859-125">Next steps</span></span>

<span data-ttu-id="ee859-126">Para probar un sitio de grupo de SharePoint Online aislado en una suscripción de prueba, vea las instrucciones paso a paso en [Entorno de desarrollo y pruebas en un sitio de grupo aislado de SharePoint Online](isolated-sharepoint-online-team-site-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ee859-126">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>
  
<span data-ttu-id="ee859-127">Cuando esté preparado para implementar un sitio de grupo de SharePoint Online aislado en producción, vea las consideraciones de diseño paso a paso en [Diseñar un sitio de grupo aislado de SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="ee859-127">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ee859-128">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ee859-128">Related topics</span></span>

[<span data-ttu-id="ee859-129">Diseñar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="ee859-129">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="ee859-130">Administrar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="ee859-130">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="ee859-131">Implementar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="ee859-131">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)


