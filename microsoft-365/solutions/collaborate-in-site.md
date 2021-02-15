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
description: Obtenga información sobre los pasos de configuración de Microsoft 365 necesarios para configurar un sitio de SharePoint para la colaboración con invitados.
ms.openlocfilehash: 6862fe715fe2f19b968b773bc6df6c70c207a44f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663529"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="34242-103">Colaborar con invitados en un sitio</span><span class="sxs-lookup"><span data-stu-id="34242-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="34242-104">Si necesita colaborar con invitados en documentos, datos y listas, puede usar un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="34242-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="34242-105">Los sitios de SharePoint modernos están conectados a grupos de Microsoft 365 y pueden administrar la pertenencia al sitio y proporcionar herramientas de colaboración adicionales, como un buzón compartido y un calendario.</span><span class="sxs-lookup"><span data-stu-id="34242-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="34242-106">En este artículo, veremos los pasos de configuración de Microsoft 365 necesarios para configurar un sitio de SharePoint para la colaboración con invitados.</span><span class="sxs-lookup"><span data-stu-id="34242-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="34242-107">Vídeo de demostración</span><span class="sxs-lookup"><span data-stu-id="34242-107">Video demonstration</span></span>

<span data-ttu-id="34242-108">En este vídeo se muestran los pasos de configuración descritos en este documento.</span><span class="sxs-lookup"><span data-stu-id="34242-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="34242-109">Configuración de colaboración externa de Azure</span><span class="sxs-lookup"><span data-stu-id="34242-109">Azure external collaboration settings</span></span>

<span data-ttu-id="34242-110">El uso compartido en Microsoft 365 se rige en su nivel más alto por la configuración de [colaboración externa B2B en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)</span><span class="sxs-lookup"><span data-stu-id="34242-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="34242-111">Si el uso compartido de invitados está deshabilitado o restringido en Azure AD, esta configuración invalida cualquier configuración de uso compartido que configure en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34242-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="34242-112">Compruebe la configuración de colaboración externa B2B para asegurarse de que no se bloquee el uso compartido con invitados.</span><span class="sxs-lookup"><span data-stu-id="34242-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de pantalla de la página Configuración de colaboración externa de Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="34242-114">Para establecer la configuración de colaboración externa</span><span class="sxs-lookup"><span data-stu-id="34242-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="34242-115">Inicie sesión en Azure Active Directory en [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="34242-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="34242-116">En el panel de navegación izquierdo, haga clic **en Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="34242-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="34242-117">Haga **clic en Identidades externas.**</span><span class="sxs-lookup"><span data-stu-id="34242-117">Click **External identities**.</span></span>
4. <span data-ttu-id="34242-118">En la **pantalla Introducción, en** el panel de navegación izquierdo, haga clic en **Configuración de colaboración externa.**</span><span class="sxs-lookup"><span data-stu-id="34242-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="34242-119">Asegúrese de **que los administradores y los usuarios del** rol de invitador de invitado pueden invitar y que **los** miembros pueden invitar están establecidos en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="34242-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="34242-120">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="34242-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="34242-121">Tenga en cuenta la configuración de la **sección Restricciones de colaboración.**</span><span class="sxs-lookup"><span data-stu-id="34242-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="34242-122">Asegúrese de que los dominios de los invitados con los que desea colaborar no están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="34242-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="34242-123">Si trabaja con invitados de varias organizaciones, es posible que desee restringir su capacidad para obtener acceso a los datos del directorio.</span><span class="sxs-lookup"><span data-stu-id="34242-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="34242-124">Esto les impedirá ver quién más es un invitado en el directorio.</span><span class="sxs-lookup"><span data-stu-id="34242-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="34242-125">Para ello, en Restricciones de  acceso de usuarios **invitados,** seleccione Los usuarios invitados tienen acceso limitado a las propiedades y la pertenencia a la configuración de objetos de directorio o el acceso de usuarios invitados está restringido a las propiedades y pertenencias de sus **propios** objetos de directorio.</span><span class="sxs-lookup"><span data-stu-id="34242-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="34242-126">Configuración de invitado de Grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="34242-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="34242-127">Los sitios de SharePoint modernos usan Grupos de Microsoft 365 para controlar el acceso a sitios.</span><span class="sxs-lookup"><span data-stu-id="34242-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="34242-128">La configuración de invitado de Grupos de Microsoft 365 debe estar activada para que funcione el acceso de invitado en los sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="34242-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Captura de pantalla de la configuración de invitados de los grupos de Microsoft 365 en el Centro de administración de Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="34242-130">Para establecer la configuración de invitado de Grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="34242-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="34242-131">En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, expanda **Configuración.**</span><span class="sxs-lookup"><span data-stu-id="34242-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="34242-132">Haga clic **en Configuración de la organización.**</span><span class="sxs-lookup"><span data-stu-id="34242-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="34242-133">En la lista, haga clic **en Grupos de Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="34242-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="34242-134">Asegúrese de que las casillas Permitir que los propietarios del grupo agreguen personas fuera de su organización a Grupos de **Microsoft 365** como invitados y permitir que los miembros del grupo invitados accedan a las casillas de contenido **del** grupo estén activadas.</span><span class="sxs-lookup"><span data-stu-id="34242-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="34242-135">Si realizó cambios, haga clic **en Guardar cambios.**</span><span class="sxs-lookup"><span data-stu-id="34242-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="34242-136">Configuración de uso compartido en el nivel de organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="34242-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="34242-137">Para que los invitados tengan acceso a los sitios de SharePoint, la configuración de uso compartido de nivel de organización de SharePoint debe permitir el uso compartido con invitados.</span><span class="sxs-lookup"><span data-stu-id="34242-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="34242-138">La configuración de nivel de organización determina la configuración que estará disponible para sitios individuales.</span><span class="sxs-lookup"><span data-stu-id="34242-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="34242-139">La configuración del sitio no puede ser más permisiva que la configuración de nivel de organización.</span><span class="sxs-lookup"><span data-stu-id="34242-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="34242-140">Si desea permitir el uso compartido de archivos y carpetas no autenticados, elija **Cualquiera**.</span><span class="sxs-lookup"><span data-stu-id="34242-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="34242-141">Si desea asegurarse de que todas las personas fuera de su organización tienen que autenticarse, elija **Invitados nuevos y existentes.**</span><span class="sxs-lookup"><span data-stu-id="34242-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="34242-142">Elija la configuración más permisiva que necesite cualquier sitio de su organización.</span><span class="sxs-lookup"><span data-stu-id="34242-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="34242-144">Para establecer la configuración de uso compartido en el nivel de organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="34242-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="34242-145">En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, en Centros de **administración,** haga clic **en SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="34242-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="34242-146">En el Centro de administración de SharePoint, en el panel de navegación izquierdo, en **Directivas,** haga clic en **Compartir.**</span><span class="sxs-lookup"><span data-stu-id="34242-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="34242-147">Asegúrese de que el uso compartido externo para SharePoint esté establecido en **Cualquiera** o **Nuevo y los invitados existentes.**</span><span class="sxs-lookup"><span data-stu-id="34242-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="34242-148">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="34242-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="34242-149">Crear un sitio</span><span class="sxs-lookup"><span data-stu-id="34242-149">Create a site</span></span>

<span data-ttu-id="34242-150">El siguiente paso es crear el sitio que tiene previsto usar para colaborar con invitados.</span><span class="sxs-lookup"><span data-stu-id="34242-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="34242-151">Para crear un sitio</span><span class="sxs-lookup"><span data-stu-id="34242-151">To create a site</span></span>
1. <span data-ttu-id="34242-152">En el Centro de administración de SharePoint, en **Sitios**, haga clic en **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="34242-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="34242-153">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="34242-153">Click **Create**.</span></span>
3. <span data-ttu-id="34242-154">Haga clic **en Sitio de grupo.**</span><span class="sxs-lookup"><span data-stu-id="34242-154">Click **Team site**.</span></span>
4. <span data-ttu-id="34242-155">Escriba un nombre de sitio y escriba un nombre para el propietario del grupo (propietario del sitio).</span><span class="sxs-lookup"><span data-stu-id="34242-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="34242-156">En **Configuración avanzada,** elija si desea que este sitio sea público o privado.</span><span class="sxs-lookup"><span data-stu-id="34242-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="34242-157">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="34242-157">Click **Next**.</span></span>
7. <span data-ttu-id="34242-158">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="34242-158">Click **Finish**.</span></span>

<span data-ttu-id="34242-159">Invitaremos a los usuarios más adelante.</span><span class="sxs-lookup"><span data-stu-id="34242-159">We'll invite users later.</span></span> <span data-ttu-id="34242-160">A continuación, es importante comprobar la configuración de uso compartido de nivel de sitio para este sitio.</span><span class="sxs-lookup"><span data-stu-id="34242-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="34242-161">Configuración de uso compartido en el nivel de sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="34242-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="34242-162">Compruebe la configuración de uso compartido de nivel de sitio para asegurarse de que permiten el tipo de acceso que desea para este sitio.</span><span class="sxs-lookup"><span data-stu-id="34242-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="34242-163">Por ejemplo, si establece la configuración de nivel de organización en **Cualquiera,** pero desea que todos los invitados se autentiquen para este sitio, asegúrese de que la configuración de uso compartido de nivel de sitio esté establecida en Invitados nuevos y **existentes.**</span><span class="sxs-lookup"><span data-stu-id="34242-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="34242-164">Tenga en cuenta que el sitio no se puede compartir con personas no autenticadas **(configuración** cualquiera), pero sí con archivos y carpetas individuales.</span><span class="sxs-lookup"><span data-stu-id="34242-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="34242-165">También puede usar [etiquetas de confidencialidad para controlar la configuración de uso compartido externo para sitios de SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)</span><span class="sxs-lookup"><span data-stu-id="34242-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="34242-167">Para establecer la configuración de uso compartido de nivel de sitio</span><span class="sxs-lookup"><span data-stu-id="34242-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="34242-168">En el Centro de administración de SharePoint, en el panel de navegación izquierdo, expanda **Sitios** y haga clic en **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="34242-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="34242-169">Seleccione el sitio que desea compartir.</span><span class="sxs-lookup"><span data-stu-id="34242-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="34242-170">Haga clic en ...y haga clic en **Compartir.**</span><span class="sxs-lookup"><span data-stu-id="34242-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="34242-171">Asegúrese de que el uso compartido está establecido en **Cualquiera** o **Invitados nuevos y existentes.**</span><span class="sxs-lookup"><span data-stu-id="34242-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="34242-172">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="34242-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="34242-173">Invitar a usuarios</span><span class="sxs-lookup"><span data-stu-id="34242-173">Invite users</span></span>

<span data-ttu-id="34242-174">La configuración de uso compartido de invitados ya está configurada, por lo que puede empezar a agregar usuarios e invitados internos a su sitio.</span><span class="sxs-lookup"><span data-stu-id="34242-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="34242-175">El acceso al sitio se controla a través del grupo asociado de Microsoft 365, por lo que agregaremos usuarios allí.</span><span class="sxs-lookup"><span data-stu-id="34242-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="34242-176">Para invitar a usuarios internos a un grupo</span><span class="sxs-lookup"><span data-stu-id="34242-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="34242-177">Vaya al sitio donde desea agregar usuarios.</span><span class="sxs-lookup"><span data-stu-id="34242-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="34242-178">Haga **clic en** el vínculo Miembros en la esquina superior derecha, que indica el recuento de miembros.</span><span class="sxs-lookup"><span data-stu-id="34242-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="34242-179">Haga clic en **Agregar miembros**.</span><span class="sxs-lookup"><span data-stu-id="34242-179">Click **Add members**.</span></span>
4. <span data-ttu-id="34242-180">Escriba los nombres o las direcciones de correo electrónico de los usuarios a los que desea invitar al sitio y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="34242-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="34242-181">Los invitados no se pueden agregar desde el sitio.</span><span class="sxs-lookup"><span data-stu-id="34242-181">Guests can't be added from the site.</span></span> <span data-ttu-id="34242-182">Debe agregarlos con Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="34242-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="34242-183">Por lo tanto, como requisito previo para agregar e invitar invitados a un grupo, haga clic en la dirección URL del sitio en la columna **dirección URL**  para navegar a la página específica del sitio.</span><span class="sxs-lookup"><span data-stu-id="34242-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="34242-184">En esta página, haga clic en el icono **del iniciador** de aplicaciones y seleccione **Outlook**.</span><span class="sxs-lookup"><span data-stu-id="34242-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="34242-185">Esta es la pantalla desde la que puede invitar a invitados a un grupo, para lo cual se describe el procedimiento a continuación.</span><span class="sxs-lookup"><span data-stu-id="34242-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="34242-186">Para invitar a invitados a un grupo</span><span class="sxs-lookup"><span data-stu-id="34242-186">To invite guests to a group</span></span>
1. <span data-ttu-id="34242-187">En **Grupos,** haga clic en el grupo al que desea invitar a invitados.</span><span class="sxs-lookup"><span data-stu-id="34242-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="34242-188">Abra la tarjeta de  contacto del grupo y haga clic en el vínculo Miembros en la esquina superior derecha (vínculo que indica el recuento de miembros).</span><span class="sxs-lookup"><span data-stu-id="34242-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="34242-189">haga clic **en Agregar miembros.**</span><span class="sxs-lookup"><span data-stu-id="34242-189">click **Add members**.</span></span>
4. <span data-ttu-id="34242-190">Escriba las direcciones de correo electrónico de los invitados que desea invitar y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="34242-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="34242-191">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="34242-191">Click **Close**.</span></span>
<span data-ttu-id="34242-192">Tenga en cuenta  que solo necesita hacer clic en Cerrar si no es el propietario del grupo y, como resultado, no puede agregar el invitado al grupo.</span><span class="sxs-lookup"><span data-stu-id="34242-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="34242-193">En estos casos, la solicitud para agregar el invitado al grupo se transfiere al propietario del grupo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="34242-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="34242-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="34242-194">See also</span></span>

[<span data-ttu-id="34242-195">Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados</span><span class="sxs-lookup"><span data-stu-id="34242-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="34242-196">Reducir la exposición accidental de archivos al compartirlos con invitados</span><span class="sxs-lookup"><span data-stu-id="34242-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="34242-197">Crear un entorno seguro de uso compartido para invitados</span><span class="sxs-lookup"><span data-stu-id="34242-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="34242-198">Para obtener más información, consulte [Crear una extranet de B2B con invitados administrados](b2b-extranet.md).</span><span class="sxs-lookup"><span data-stu-id="34242-198">[Create a B2B extranet with managed guests](b2b-extranet.md)</span></span>

[<span data-ttu-id="34242-199">Integración de SharePoint y OneDrive con Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="34242-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
