---
title: Colaborar con invitados en un sitio
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Obtenga información sobre los pasos de configuración de Microsoft 365 necesarios para configurar un sitio de SharePoint para la colaboración con los invitados.
ms.openlocfilehash: 6862fe715fe2f19b968b773bc6df6c70c207a44f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663529"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="8b407-103">Colaborar con invitados en un sitio</span><span class="sxs-lookup"><span data-stu-id="8b407-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="8b407-104">Si necesita colaborar con invitados en documentos, datos y listas, puede usar un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8b407-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="8b407-105">Los sitios modernos de SharePoint están conectados a grupos de 365 de Microsoft y pueden administrar la pertenencia al sitio y proporcionar herramientas de colaboración adicionales, como un buzón compartido y un calendario.</span><span class="sxs-lookup"><span data-stu-id="8b407-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="8b407-106">En este artículo, analizaremos los pasos de configuración de Microsoft 365 necesarios para configurar un sitio de SharePoint para la colaboración con los invitados.</span><span class="sxs-lookup"><span data-stu-id="8b407-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="8b407-107">Vídeo de demostración</span><span class="sxs-lookup"><span data-stu-id="8b407-107">Video demonstration</span></span>

<span data-ttu-id="8b407-108">En este vídeo se muestran los pasos de configuración que se describen en este documento.</span><span class="sxs-lookup"><span data-stu-id="8b407-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="8b407-109">Configuración de colaboración externa de Azure</span><span class="sxs-lookup"><span data-stu-id="8b407-109">Azure external collaboration settings</span></span>

<span data-ttu-id="8b407-110">El uso compartido en Microsoft 365 se rige en su nivel más alto por la [configuración de colaboración externa B2B en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="8b407-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="8b407-111">Si el uso compartido de invitado está deshabilitado o restringido en Azure AD, esta configuración invalida cualquier configuración de uso compartido que configure en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b407-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="8b407-112">Compruebe la configuración de colaboración externa B2B para asegurarse de que no se bloquee el uso compartido con invitados.</span><span class="sxs-lookup"><span data-stu-id="8b407-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de pantalla de la página de configuración de colaboración externa de Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="8b407-114">Para establecer la configuración de colaboración externa</span><span class="sxs-lookup"><span data-stu-id="8b407-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="8b407-115">Inicie sesión en Azure Active Directory en [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="8b407-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="8b407-116">En el panel de navegación izquierdo, haga clic en **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="8b407-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="8b407-117">Haga clic en **identidades externas**.</span><span class="sxs-lookup"><span data-stu-id="8b407-117">Click **External identities**.</span></span>
4. <span data-ttu-id="8b407-118">En la **pantalla introducción** , en el panel de navegación de la izquierda, haga clic en **configuración de colaboración externa**.</span><span class="sxs-lookup"><span data-stu-id="8b407-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="8b407-119">Asegúrese de que los **administradores y los usuarios de la función invitador invitado puedan** invitar y que **los miembros puedan invitar** están establecidos en **sí**.</span><span class="sxs-lookup"><span data-stu-id="8b407-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="8b407-120">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b407-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="8b407-121">Anote la configuración de la sección **restricciones de colaboración** .</span><span class="sxs-lookup"><span data-stu-id="8b407-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="8b407-122">Asegúrese de que los dominios de los invitados con los que desea colaborar no están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="8b407-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="8b407-123">Si trabaja con invitados de varias organizaciones, es posible que desee restringir su capacidad para obtener acceso a los datos del directorio.</span><span class="sxs-lookup"><span data-stu-id="8b407-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="8b407-124">Esto impedirá que vean quién más es un invitado en el directorio.</span><span class="sxs-lookup"><span data-stu-id="8b407-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="8b407-125">Para ello, en **restricciones de acceso de usuarios invitados**, seleccione **los usuarios invitados tienen restringido el acceso a las propiedades y la pertenencia de los objetos de directorio la configuración** o **el acceso de usuario invitado está restringido a las propiedades y pertenencia de sus propios objetos de directorio**.</span><span class="sxs-lookup"><span data-stu-id="8b407-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="8b407-126">Configuración de invitado de Microsoft 365 Groups</span><span class="sxs-lookup"><span data-stu-id="8b407-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="8b407-127">Los sitios modernos de SharePoint usan grupos de Microsoft 365 para controlar el acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="8b407-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="8b407-128">La configuración de invitado de Microsoft 365 Groups debe estar activada para que el acceso de invitado en los sitios de SharePoint funcione.</span><span class="sxs-lookup"><span data-stu-id="8b407-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Captura de pantalla de la configuración de invitados de los grupos de Microsoft 365 en el Centro de administración de Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="8b407-130">Para establecer la configuración de invitado de Microsoft 365 Groups</span><span class="sxs-lookup"><span data-stu-id="8b407-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="8b407-131">En el centro de administración de Microsoft 365, en el panel de navegación izquierdo, expanda **configuración**.</span><span class="sxs-lookup"><span data-stu-id="8b407-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="8b407-132">Haga clic en configuración de la **organización**.</span><span class="sxs-lookup"><span data-stu-id="8b407-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="8b407-133">En la lista, haga clic en **grupos de 365 de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="8b407-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="8b407-134">Asegúrese de que los **propietarios del grupo Let agreguen personas externas a la organización a Microsoft 365 Groups As Guests** y **permita a los miembros del grupo de invitados tener acceso a** las casillas de verificación contenido del grupo.</span><span class="sxs-lookup"><span data-stu-id="8b407-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="8b407-135">Si ha realizado cambios, haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="8b407-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="8b407-136">Configuración de uso compartido en el nivel de la organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="8b407-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="8b407-137">Para que los invitados tengan acceso a los sitios de SharePoint, la configuración de uso compartido en el nivel de la organización de SharePoint debe permitir el uso compartido con invitados.</span><span class="sxs-lookup"><span data-stu-id="8b407-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="8b407-138">La configuración en el nivel de la organización determina la configuración que estará disponible para cada uno de los sitios.</span><span class="sxs-lookup"><span data-stu-id="8b407-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="8b407-139">La configuración del sitio no puede ser más permisiva que la configuración de nivel de organización.</span><span class="sxs-lookup"><span data-stu-id="8b407-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="8b407-140">Si desea permitir el uso compartido de archivos y carpetas sin autenticar, elija **cualquiera**.</span><span class="sxs-lookup"><span data-stu-id="8b407-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="8b407-141">Si desea asegurarse de que todos los usuarios ajenos a la organización tienen que autenticarse, elija los **invitados nuevos y existentes**.</span><span class="sxs-lookup"><span data-stu-id="8b407-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="8b407-142">Elija la configuración más permisiva que necesitará cualquier sitio de la organización.</span><span class="sxs-lookup"><span data-stu-id="8b407-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="8b407-144">Para establecer la configuración de uso compartido en el nivel de la organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="8b407-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="8b407-145">En el centro de administración de Microsoft 365, en el panel de navegación izquierdo, en **centros de administración**, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8b407-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="8b407-146">En el centro de administración de SharePoint, en el panel de navegación izquierdo, en **directivas**, haga clic en **uso compartido**.</span><span class="sxs-lookup"><span data-stu-id="8b407-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="8b407-147">Asegúrese de que el uso compartido externo para SharePoint está establecido en **todos** o en **invitados nuevos o existentes**.</span><span class="sxs-lookup"><span data-stu-id="8b407-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="8b407-148">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b407-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="8b407-149">Crear un sitio</span><span class="sxs-lookup"><span data-stu-id="8b407-149">Create a site</span></span>

<span data-ttu-id="8b407-150">El siguiente paso es crear el sitio que va a usar para colaborar con los invitados.</span><span class="sxs-lookup"><span data-stu-id="8b407-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="8b407-151">Para crear un sitio</span><span class="sxs-lookup"><span data-stu-id="8b407-151">To create a site</span></span>
1. <span data-ttu-id="8b407-152">En el Centro de administración de SharePoint, en **Sitios**, haga clic en **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="8b407-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="8b407-153">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="8b407-153">Click **Create**.</span></span>
3. <span data-ttu-id="8b407-154">Haga clic en **sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="8b407-154">Click **Team site**.</span></span>
4. <span data-ttu-id="8b407-155">Escriba un nombre de sitio y escriba un nombre para el propietario del grupo (propietario del sitio).</span><span class="sxs-lookup"><span data-stu-id="8b407-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="8b407-156">En **Configuración avanzada**, elija si desea que este sitio sea público o privado.</span><span class="sxs-lookup"><span data-stu-id="8b407-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="8b407-157">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8b407-157">Click **Next**.</span></span>
7. <span data-ttu-id="8b407-158">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="8b407-158">Click **Finish**.</span></span>

<span data-ttu-id="8b407-159">Invitaremos a los usuarios más adelante.</span><span class="sxs-lookup"><span data-stu-id="8b407-159">We'll invite users later.</span></span> <span data-ttu-id="8b407-160">A continuación, es importante comprobar la configuración de uso compartido de nivel de sitio para este sitio.</span><span class="sxs-lookup"><span data-stu-id="8b407-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="8b407-161">Configuración de uso compartido en el nivel de sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="8b407-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="8b407-162">Compruebe la configuración de uso compartido de nivel de sitio para asegurarse de que permite el tipo de acceso que desea para este sitio.</span><span class="sxs-lookup"><span data-stu-id="8b407-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="8b407-163">Por ejemplo, si establece la configuración de nivel de organización en **cualquiera**, pero desea que todos los invitados se autentiquen en este sitio, asegúrese de que la configuración de uso compartido de nivel de sitio esté establecida en **invitados nuevos y existentes**.</span><span class="sxs-lookup"><span data-stu-id="8b407-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="8b407-164">Tenga en cuenta que no se puede compartir el sitio con personas no autenticadas (configuración de **cualquier persona** ), pero puede que los archivos y las carpetas individuales.</span><span class="sxs-lookup"><span data-stu-id="8b407-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="8b407-165">También puede usar las [etiquetas de confidencialidad para controlar la configuración de uso compartido externo de los sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="8b407-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="8b407-167">Para establecer la configuración de uso compartido de nivel de sitio</span><span class="sxs-lookup"><span data-stu-id="8b407-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="8b407-168">En el Centro de administración de SharePoint, en el panel de navegación izquierdo, expanda **Sitios** y haga clic en **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="8b407-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="8b407-169">Seleccione el sitio que desea compartir.</span><span class="sxs-lookup"><span data-stu-id="8b407-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="8b407-170">Haga clic en... y haga clic en **compartir**.</span><span class="sxs-lookup"><span data-stu-id="8b407-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="8b407-171">Asegúrese de que el uso compartido está establecido en **todos** o en **invitados nuevos o existentes**.</span><span class="sxs-lookup"><span data-stu-id="8b407-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="8b407-172">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b407-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="8b407-173">Invitar a usuarios</span><span class="sxs-lookup"><span data-stu-id="8b407-173">Invite users</span></span>

<span data-ttu-id="8b407-174">La configuración de uso compartido de invitados ya está configurada, por lo que puede empezar a agregar invitados y usuarios internos a su sitio.</span><span class="sxs-lookup"><span data-stu-id="8b407-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="8b407-175">El acceso al sitio se controla a través del grupo de Microsoft 365 asociado, por lo que vamos a agregar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8b407-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="8b407-176">Para invitar a usuarios internos a un grupo</span><span class="sxs-lookup"><span data-stu-id="8b407-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="8b407-177">Navegue hasta el sitio en el que desea agregar usuarios.</span><span class="sxs-lookup"><span data-stu-id="8b407-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="8b407-178">Haga clic en el vínculo **miembros** en la esquina superior derecha, que denota el recuento de miembros.</span><span class="sxs-lookup"><span data-stu-id="8b407-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="8b407-179">Haga clic en **Agregar miembros**.</span><span class="sxs-lookup"><span data-stu-id="8b407-179">Click **Add members**.</span></span>
4. <span data-ttu-id="8b407-180">Escriba los nombres o las direcciones de correo electrónico de los usuarios que desea invitar al sitio y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b407-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="8b407-181">No se pueden agregar invitados desde el sitio.</span><span class="sxs-lookup"><span data-stu-id="8b407-181">Guests can't be added from the site.</span></span> <span data-ttu-id="8b407-182">Debe agregarlos mediante Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="8b407-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="8b407-183">Por lo tanto, como requisito previo para agregar e invitar invitados a un grupo, haga clic en la dirección URL del sitio en la columna **dirección URL**  para ir a la página específica del sitio.</span><span class="sxs-lookup"><span data-stu-id="8b407-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="8b407-184">En esta página, haga clic en el icono del **iniciador de aplicaciones** y seleccione **Outlook**.</span><span class="sxs-lookup"><span data-stu-id="8b407-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="8b407-185">Esta es la pantalla desde la que puede invitar a los invitados a un grupo, para qué procedimiento se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="8b407-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="8b407-186">Para invitar a invitados a un grupo</span><span class="sxs-lookup"><span data-stu-id="8b407-186">To invite guests to a group</span></span>
1. <span data-ttu-id="8b407-187">En **grupos**, haga clic en el grupo al que desea invitar a los invitados.</span><span class="sxs-lookup"><span data-stu-id="8b407-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="8b407-188">Abra la tarjeta de contacto de grupo y haga clic en vínculo de **miembros** en la esquina superior derecha (el vínculo que indica el recuento de miembros).</span><span class="sxs-lookup"><span data-stu-id="8b407-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="8b407-189">Haga clic en **Agregar miembros**.</span><span class="sxs-lookup"><span data-stu-id="8b407-189">click **Add members**.</span></span>
4. <span data-ttu-id="8b407-190">Escriba las direcciones de correo electrónico de los invitados que desea invitar y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8b407-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="8b407-191">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="8b407-191">Click **Close**.</span></span>
<span data-ttu-id="8b407-192">Tenga en cuenta que debe hacer clic en **cerrar** solo si no es el propietario del grupo y, como resultado, no tiene permiso para agregar el invitado al grupo.</span><span class="sxs-lookup"><span data-stu-id="8b407-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="8b407-193">En estos casos, la solicitud para agregar el invitado al grupo se transfiere al propietario del grupo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="8b407-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b407-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b407-194">See also</span></span>

[<span data-ttu-id="8b407-195">Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados</span><span class="sxs-lookup"><span data-stu-id="8b407-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="8b407-196">Reducir la exposición accidental de archivos al compartirlos con invitados</span><span class="sxs-lookup"><span data-stu-id="8b407-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="8b407-197">Crear un entorno seguro de uso compartido para invitados</span><span class="sxs-lookup"><span data-stu-id="8b407-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="8b407-198">Para obtener más información, consulte [Crear una extranet de B2B con invitados administrados](b2b-extranet.md).</span><span class="sxs-lookup"><span data-stu-id="8b407-198">[Create a B2B extranet with managed guests](b2b-extranet.md)</span></span>

[<span data-ttu-id="8b407-199">Integración de SharePoint y OneDrive con la B2B de Azure AD</span><span class="sxs-lookup"><span data-stu-id="8b407-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
