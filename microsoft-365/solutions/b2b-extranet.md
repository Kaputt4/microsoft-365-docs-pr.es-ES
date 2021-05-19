---
title: Para obtener más información, consulte Crear una extranet de B2B con invitados administrados.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: Obtenga información sobre cómo crear un sitio de extranet B2B o un equipo con invitados administrados de una organización asociada.
ms.openlocfilehash: d76951da5d8affa1dac08cbdc68a91329ca069ed
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538248"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="2e016-103">Para obtener más información, consulte Crear una extranet de B2B con invitados administrados.</span><span class="sxs-lookup"><span data-stu-id="2e016-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="2e016-104">Puede usar la [administración Azure Active Directory derechos](/azure/active-directory/governance/entitlement-management-overview) para crear una extranet B2B para colaborar con una organización asociada que use Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2e016-104">You can use [Azure Active Directory Entitlement Management](/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="2e016-105">Esto permite a los usuarios auto inscribirse en el sitio o equipo de extranet y recibir acceso a través de un flujo de trabajo de aprobación.</span><span class="sxs-lookup"><span data-stu-id="2e016-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="2e016-106">Con este método de compartir recursos para la colaboración, la organización asociada puede ayudar a mantener y aprobar a los invitados al final, lo que reduce la carga para el departamento de TI y permite a los más familiarizados con el contrato de colaboración administrar el acceso de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2e016-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="2e016-107">Este artículo describe los pasos para crear un paquete de recursos (en este caso, un sitio o un equipo) que puede compartir con una organización asociada a través de un modelo de registro de acceso autoservicio.</span><span class="sxs-lookup"><span data-stu-id="2e016-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="2e016-108">Antes de comenzar, cree el sitio o el equipo que desea compartir con la organización asociada y habilite para el uso compartido de invitados.</span><span class="sxs-lookup"><span data-stu-id="2e016-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="2e016-109">Consulta [Colaborar con invitados en un sitio](collaborate-in-site.md) o Colaborar con [invitados de un equipo](collaborate-as-team.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2e016-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="2e016-110">También se recomienda revisar Crear un entorno de uso compartido de invitados seguro para obtener información sobre las características de seguridad y cumplimiento que puede usar para ayudar [a](create-secure-guest-sharing-environment.md) mantener las directivas de gobierno al colaborar con invitados.</span><span class="sxs-lookup"><span data-stu-id="2e016-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="2e016-111">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="2e016-111">License requirements</span></span>

<span data-ttu-id="2e016-112">El uso de esta característica requiere una licencia de Azure AD Premium P2.</span><span class="sxs-lookup"><span data-stu-id="2e016-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="2e016-113">Las nubes especializadas, como Azure Germany y Azure China 21Vianet, no están disponibles actualmente para su uso.</span><span class="sxs-lookup"><span data-stu-id="2e016-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="2e016-114">Vídeo de demostración</span><span class="sxs-lookup"><span data-stu-id="2e016-114">Video demonstration</span></span>

<span data-ttu-id="2e016-115">En este vídeo se muestran los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2e016-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="2e016-116">Conectar la organización asociada</span><span class="sxs-lookup"><span data-stu-id="2e016-116">Connect the partner organization</span></span>

<span data-ttu-id="2e016-117">Para invitar invitados de una organización asociada, debe agregar el dominio del partner como una organización conectada en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2e016-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="2e016-118">Para agregar una organización conectada</span><span class="sxs-lookup"><span data-stu-id="2e016-118">To add a connected organization</span></span>
1. <span data-ttu-id="2e016-119">En [Azure Active Directory](https://aad.portal.azure.com), haga clic en **Gobierno de identidad**.</span><span class="sxs-lookup"><span data-stu-id="2e016-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="2e016-120">Haga clic **en Organizaciones conectadas**.</span><span class="sxs-lookup"><span data-stu-id="2e016-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="2e016-121">Haga clic **en Agregar organización conectada.**</span><span class="sxs-lookup"><span data-stu-id="2e016-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="2e016-122">Escriba un nombre y una descripción para la organización y, a continuación, haga clic **en Siguiente: Directorio + dominio**.</span><span class="sxs-lookup"><span data-stu-id="2e016-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="2e016-123">Haga **clic en Agregar directorio + dominio**.</span><span class="sxs-lookup"><span data-stu-id="2e016-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="2e016-124">Escriba el dominio de la organización que desea conectar y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2e016-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="2e016-125">Haga **clic Conectar** y, a continuación, haga clic en **Siguiente: Patrocinadores**.</span><span class="sxs-lookup"><span data-stu-id="2e016-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="2e016-126">Agrega personas de tu organización o de la organización a las que quieras aprobar el acceso para invitados.</span><span class="sxs-lookup"><span data-stu-id="2e016-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="2e016-127">Haga clic en **Siguiente: Revisar + Crear**.</span><span class="sxs-lookup"><span data-stu-id="2e016-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="2e016-128">Revise la configuración que ha elegido y, a continuación, haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="2e016-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Captura de pantalla de la página de organizaciones conectadas en Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="2e016-130">Elegir los recursos que se compartirán</span><span class="sxs-lookup"><span data-stu-id="2e016-130">Choose the resources to share</span></span>

<span data-ttu-id="2e016-131">El primer paso para seleccionar los recursos que se compartirán con una organización asociada es crear un catálogo que los contenga.</span><span class="sxs-lookup"><span data-stu-id="2e016-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="2e016-132">Para crear un catálogo</span><span class="sxs-lookup"><span data-stu-id="2e016-132">To create a catalog</span></span>
1. <span data-ttu-id="2e016-133">En [Azure Active Directory](https://aad.portal.azure.com), haga clic en **Gobierno de identidad**.</span><span class="sxs-lookup"><span data-stu-id="2e016-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="2e016-134">Haga **clic en Catálogos**.</span><span class="sxs-lookup"><span data-stu-id="2e016-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="2e016-135">Haga clic **en Nuevo catálogo**.</span><span class="sxs-lookup"><span data-stu-id="2e016-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="2e016-136">Escriba un nombre y una descripción para el catálogo y asegúrese de que **Enabled** y **Enabled para** usuarios externos estén establecidos en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2e016-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="2e016-137">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="2e016-137">Click **Create**.</span></span>

   ![Captura de pantalla de la página catálogos en Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

<span data-ttu-id="2e016-139">Una vez creado el catálogo, se agrega el SharePoint sitio o equipo que desea compartir con la organización asociada.</span><span class="sxs-lookup"><span data-stu-id="2e016-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="2e016-140">Para agregar recursos a un catálogo</span><span class="sxs-lookup"><span data-stu-id="2e016-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="2e016-141">En Gobierno de identidades de Azure AD, haga clic **en Catálogos** y, a continuación, haga clic en el catálogo donde desea agregar recursos.</span><span class="sxs-lookup"><span data-stu-id="2e016-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="2e016-142">Haga **clic en Recursos** y, a **continuación, en Agregar recursos.**</span><span class="sxs-lookup"><span data-stu-id="2e016-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="2e016-143">Seleccione los equipos o SharePoint que desea incluir en la extranet y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2e016-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Captura de pantalla de la página de recursos del catálogo Azure Active Directory identity governance](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="2e016-145">Una vez definidos los recursos que desea compartir, el siguiente paso es crear un paquete de acceso, que defina el tipo de acceso que se concede a los usuarios asociados y el proceso de aprobación de los nuevos usuarios asociados que solicitan acceso.</span><span class="sxs-lookup"><span data-stu-id="2e016-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="2e016-146">Para crear un paquete de acceso</span><span class="sxs-lookup"><span data-stu-id="2e016-146">To create an access package</span></span>
1. <span data-ttu-id="2e016-147">En Gobierno de identidades de Azure AD, haga clic **en Catálogos** y, a continuación, haga clic en el catálogo donde desea crear un paquete de acceso.</span><span class="sxs-lookup"><span data-stu-id="2e016-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="2e016-148">Haga clic **en Paquetes de** Access y, a continuación, **en Nuevo paquete de acceso.**</span><span class="sxs-lookup"><span data-stu-id="2e016-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="2e016-149">Escriba un nombre y una descripción para el paquete de acceso y, a continuación, haga clic **en Siguiente: Roles de recurso**.</span><span class="sxs-lookup"><span data-stu-id="2e016-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="2e016-150">Elija los recursos del catálogo que desea usar para la extranet.</span><span class="sxs-lookup"><span data-stu-id="2e016-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="2e016-151">Para cada recurso, en la **columna Rol,** elija el rol de usuario que desea conceder a los invitados que usan la extranet.</span><span class="sxs-lookup"><span data-stu-id="2e016-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="2e016-152">Haga **clic en Siguiente: Solicitudes**.</span><span class="sxs-lookup"><span data-stu-id="2e016-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="2e016-153">En **Usuarios que pueden solicitar acceso,** elija Para usuarios que no están en el **directorio**.</span><span class="sxs-lookup"><span data-stu-id="2e016-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="2e016-154">Asegúrese de que **la opción Organizaciones conectadas** específicas está seleccionada y, a continuación, haga clic **en Agregar directorios**.</span><span class="sxs-lookup"><span data-stu-id="2e016-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="2e016-155">Elija la organización conectada que agredía anteriormente y, a continuación, haga clic en **Seleccionar**</span><span class="sxs-lookup"><span data-stu-id="2e016-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="2e016-156">En **Aprobación,** elija **Sí** para **Requerir aprobación**.</span><span class="sxs-lookup"><span data-stu-id="2e016-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="2e016-157">En **Primer aprobador,** elija uno de los patrocinadores que agregó anteriormente o elija un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="2e016-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="2e016-158">Haga **clic en Agregar reserva** y seleccione un aprobador de reserva.</span><span class="sxs-lookup"><span data-stu-id="2e016-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="2e016-159">En **Habilitar**, elija **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2e016-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="2e016-160">Haga **clic en Siguiente: Ciclo de vida**.</span><span class="sxs-lookup"><span data-stu-id="2e016-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="2e016-161">Elija la configuración de expiración y acceso a la revisión que desea usar y, a continuación, haga clic en **Siguiente: Revisar + Crear**.</span><span class="sxs-lookup"><span data-stu-id="2e016-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="2e016-162">Revise la configuración y, a continuación, haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="2e016-162">Review your settings, and then click **Create**.</span></span>

    ![Captura de pantalla de la pantalla de paquetes de acceso Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

<span data-ttu-id="2e016-164">Si te asocias con una organización grande, es posible que quieras ocultar el paquete de acceso.</span><span class="sxs-lookup"><span data-stu-id="2e016-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="2e016-165">Si el paquete está oculto, los usuarios de la organización asociada no verán el paquete en su portal *de My Access.*</span><span class="sxs-lookup"><span data-stu-id="2e016-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="2e016-166">En su lugar, se les debe enviar un vínculo directo para registrarse en el paquete.</span><span class="sxs-lookup"><span data-stu-id="2e016-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="2e016-167">Ocultar el paquete de acceso puede reducir el número de solicitudes de acceso inadecuadas y también puede ayudar a mantener los paquetes de acceso disponibles organizados en el portal de la organización asociada.</span><span class="sxs-lookup"><span data-stu-id="2e016-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="2e016-168">Para establecer un paquete de acceso en oculto</span><span class="sxs-lookup"><span data-stu-id="2e016-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="2e016-169">En Gobierno de identidades de Azure AD, haga clic **en Paquetes de Access** y, a continuación, haga clic en el paquete de acceso.</span><span class="sxs-lookup"><span data-stu-id="2e016-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="2e016-170">En la **página Información** general, haga clic **en Editar**.</span><span class="sxs-lookup"><span data-stu-id="2e016-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="2e016-171">En **Propiedades**, elija **Sí** **para Oculto** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2e016-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Captura de pantalla de una pantalla de propiedades del paquete de acceso de edición](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="2e016-173">Invitar a usuarios asociados</span><span class="sxs-lookup"><span data-stu-id="2e016-173">Invite partner users</span></span>

<span data-ttu-id="2e016-174">Si establece el paquete de acceso en oculto, debe enviar un vínculo directo a la organización asociada para que puedan solicitar acceso a su sitio o equipo.</span><span class="sxs-lookup"><span data-stu-id="2e016-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="2e016-175">Para buscar el vínculo del portal de acceso</span><span class="sxs-lookup"><span data-stu-id="2e016-175">To find the access portal link</span></span>
1. <span data-ttu-id="2e016-176">En Gobierno de identidades de Azure AD, haga clic **en Paquetes de Access** y, a continuación, haga clic en el paquete de acceso.</span><span class="sxs-lookup"><span data-stu-id="2e016-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="2e016-177">En la **página Información** general, haga clic en Copiar **en el** portapapeles para el vínculo Portal de **My Access**.</span><span class="sxs-lookup"><span data-stu-id="2e016-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Captura de pantalla de las propiedades del paquete de acceso con el vínculo del portal de acceso](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="2e016-179">Una vez copiado el vínculo, puede compartirlo con su contacto en la organización asociada y puede enviarlo a los usuarios de su equipo de colaboración.</span><span class="sxs-lookup"><span data-stu-id="2e016-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e016-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e016-180">See Also</span></span>

[<span data-ttu-id="2e016-181">Crear un entorno seguro de uso compartido para invitados</span><span class="sxs-lookup"><span data-stu-id="2e016-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)