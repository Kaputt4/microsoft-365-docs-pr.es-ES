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
ms.openlocfilehash: 55bdf2999610310babb60b6938afb97732e5a7a0
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845096"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="bf9f1-103">Sitios de grupo de SharePoint Online aislados</span><span class="sxs-lookup"><span data-stu-id="bf9f1-103">Isolated SharePoint Online team sites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="bf9f1-104">**Resumen:** obtenga información sobre los usos de sitios de grupo de SharePoint Online aislados.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="bf9f1-p101">Los sitios de grupo de SharePoint Online son una forma sencilla de crear rápidamente un espacio para la colaboración. Los usuarios pueden colaborar en notas, documentos, artículos, calendarios y otros recursos en Microsoft Office 365. Los sitios de grupo de SharePoint Online se basan en un grupo de Microsoft 365 y tienen un modelo de administración simplificado para permitir la colaboración abierta con un conjunto privado de miembros del grupo o con toda la organización. Un sitio de grupo predeterminado de SharePoint Online permite a los miembros del grupo de Microsoft 365 invitar a otros usuarios y controlar la configuración de los permisos.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-p101">SharePoint Online team sites are an easy way to quickly create a space for collaboration. Users can work together on notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>

<span data-ttu-id="bf9f1-109">Sin embargo, en ocasiones necesitará que el acceso al sitio esté controlado por pertenencias a grupos y que los niveles de permiso de SharePoint Online sean gestionados por administradores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-109">However, you'll sometimes need site access to be controlled by group memberships, and SharePoint Online permission levels managed by SharePoint administrators.</span></span> <span data-ttu-id="bf9f1-110">Esto se llama sitio aislado, y es aislado al conjunto de usuarios que colaboran, ven los contenidos o administran el sitio.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-110">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="bf9f1-111">Puede que necesite un sitio aislado por los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="bf9f1-111">You might need an isolated site for the following:</span></span>

- <span data-ttu-id="bf9f1-112">Un proyecto secreto en su organización.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-112">A secret project within your organization.</span></span>

- <span data-ttu-id="bf9f1-113">La ubicación de propiedad intelectual altamente confidencial o valiosa para su organización.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-113">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>

- <span data-ttu-id="bf9f1-114">Los recursos de una acción legal realizada por su organización o por la organización que sea objeto de esa acción legal.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-114">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>

- <span data-ttu-id="bf9f1-115">Para compartir una suscripción de Microsoft 365 entre varias organizaciones que se superpongan parcialmente, pero que, en su mayoría, existan como entidades empresariales separadas.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-115">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>

<span data-ttu-id="bf9f1-116">Estos son los requisitos para un sitio aislado:</span><span class="sxs-lookup"><span data-stu-id="bf9f1-116">Here are the requirements of an isolated site:</span></span>

- <span data-ttu-id="bf9f1-117">Solo los administradores de SharePoint Online pueden administrar el sitio, como la pertenencia a grupos para el acceso al sitio y la configuración de permisos personalizados.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-117">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>

- <span data-ttu-id="bf9f1-118">Los miembros del sitio no pueden invitar a otros miembros al sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-118">Members of the site cannot invite other members to the team site.</span></span>

- <span data-ttu-id="bf9f1-p103">Los usuarios que no sean miembros del sitio aislado no pueden solicitar acceso al sitio. Recibirán una página web de acceso denegado cuando intenten obtener acceso a cualquier dirección URL asociada con el sitio.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-p103">Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>

<span data-ttu-id="bf9f1-p104">La ventaja de exigir un control de acceso centralizado y permisos personalizados por los administradores de SharePoint Online es que el sitio permanecerá aislado con el paso del tiempo. Por ejemplo, los miembros actuales no pueden, ya sea de forma intencionada o por error, invitar o configurar permisos personalizados para otros usuarios de la suscripción de Microsoft 365 que no tendrían que ser miembros del sitio.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-p104">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>

<span data-ttu-id="bf9f1-123">Un sitio aislado se puede usar con otras características, como:</span><span class="sxs-lookup"><span data-stu-id="bf9f1-123">An isolated site can be used with other features, such as:</span></span>

- <span data-ttu-id="bf9f1-124">Information Rights Management, para garantizar que los recursos del sitio permanezcan cifrados, incluso si se descargan localmente y se cargan en otro sitio que esté disponible para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-124">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>

- <span data-ttu-id="bf9f1-125">Prevención de pérdida de datos para impedir que los usuarios envíen los recursos del sitio, como archivos, por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bf9f1-125">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf9f1-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bf9f1-126">Next steps</span></span>

<span data-ttu-id="bf9f1-127">Para probar un sitio de grupo de SharePoint Online aislado en una suscripción de prueba, vea las instrucciones paso a paso en [Entorno de desarrollo y pruebas en un sitio de grupo aislado de SharePoint Online](isolated-sharepoint-online-team-site-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="bf9f1-127">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>

<span data-ttu-id="bf9f1-128">Cuando esté preparado para implementar un sitio de grupo de SharePoint Online aislado en producción, vea las consideraciones de diseño paso a paso en [Diseñar un sitio de grupo aislado de SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="bf9f1-128">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="bf9f1-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bf9f1-129">Related topics</span></span>

[<span data-ttu-id="bf9f1-130">Diseñar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="bf9f1-130">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="bf9f1-131">Administrar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="bf9f1-131">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="bf9f1-132">Implementar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="bf9f1-132">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
