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
recommendations: false
description: Obtenga información sobre los Microsoft 365 de configuración necesarios para configurar un sitio SharePoint para la colaboración con invitados.
ms.openlocfilehash: f91b9c64dbdca8ed7e3ada3315cb57f1c728f838
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539256"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="1840f-103">Colaborar con invitados en un sitio</span><span class="sxs-lookup"><span data-stu-id="1840f-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="1840f-104">Si necesita colaborar con invitados en documentos, datos y listas, puede usar un SharePoint web.</span><span class="sxs-lookup"><span data-stu-id="1840f-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="1840f-105">Los SharePoint modernos están conectados a Microsoft 365 y pueden administrar la pertenencia al sitio y proporcionar herramientas de colaboración adicionales, como un buzón compartido y un calendario.</span><span class="sxs-lookup"><span data-stu-id="1840f-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="1840f-106">En este artículo, le explicamos los pasos de configuración de Microsoft 365 necesarios para configurar un sitio SharePoint para la colaboración con invitados.</span><span class="sxs-lookup"><span data-stu-id="1840f-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="1840f-107">Demostración de vídeo</span><span class="sxs-lookup"><span data-stu-id="1840f-107">Video demonstration</span></span>

<span data-ttu-id="1840f-108">En este vídeo se muestran los pasos de configuración descritos en este documento.</span><span class="sxs-lookup"><span data-stu-id="1840f-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="1840f-109">Configuración de colaboración externa de Azure</span><span class="sxs-lookup"><span data-stu-id="1840f-109">Azure external collaboration settings</span></span>

<span data-ttu-id="1840f-110">El uso compartido en Microsoft 365 se rige en su nivel más alto por la [configuración de colaboración externa B2B en Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="1840f-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="1840f-111">Si el uso compartido con invitados está deshabilitado o restringido en Azure AD, esta configuración invalida cualquier configuración de uso compartido que configure en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1840f-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="1840f-112">Compruebe la configuración de colaboración externa B2B para asegurarse de que no se bloquee el uso compartido con invitados.</span><span class="sxs-lookup"><span data-stu-id="1840f-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de pantalla Azure Active Directory página Colaboración Configuración externa](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="1840f-114">Para establecer la configuración de colaboración externa</span><span class="sxs-lookup"><span data-stu-id="1840f-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="1840f-115">Inicie sesión en Azure Active Directory en [https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="1840f-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="1840f-116">En el panel de navegación izquierdo, haga clic en **Azure Active Directory**</span><span class="sxs-lookup"><span data-stu-id="1840f-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="1840f-117">Haga clic en **Identidades externas**.</span><span class="sxs-lookup"><span data-stu-id="1840f-117">Click **External identities**.</span></span>
4. <span data-ttu-id="1840f-118">En la pantalla **introducción**, en el panel de navegación izquierdo, haga clic en **Configuración de colaboración externa**.</span><span class="sxs-lookup"><span data-stu-id="1840f-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="1840f-119">Asegúrese de que **Los administradores y usuarios con el rol de invitador pueden invitar** y **Los miembros pueden invitar** están establecidos en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="1840f-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="1840f-120">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1840f-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="1840f-121">Fíjese en la configuración en la sección **Restricciones de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="1840f-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="1840f-122">Asegúrese de que los dominios de los invitados con los que quiere colaborar no están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="1840f-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="1840f-123">Si trabaja con invitados de varias organizaciones, tal vez quiera restringir su capacidad para acceder a los datos del directorio.</span><span class="sxs-lookup"><span data-stu-id="1840f-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="1840f-124">Esto les impedirá ver quién más es un invitado en el directorio.</span><span class="sxs-lookup"><span data-stu-id="1840f-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="1840f-125">Para ello, en **Restricciones de acceso de usuario invitado**, seleccione **Los usuarios invitados tienen acceso limitado a las propiedades y a la pertenencia de la configuración de objetos de directorio** o **El acceso de usuarios invitados está restringido a las propiedades y pertenencias de sus propios objetos de directorio**.</span><span class="sxs-lookup"><span data-stu-id="1840f-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="1840f-126">Configuración de invitado de Grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1840f-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="1840f-127">Los SharePoint modernos usan Microsoft 365 para controlar el acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="1840f-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="1840f-128">La configuración Microsoft 365 invitado de grupos de usuarios debe estar activada para que el acceso de invitado en SharePoint sitios funcione.</span><span class="sxs-lookup"><span data-stu-id="1840f-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Captura de pantalla de la configuración de invitados de Grupos de Microsoft 365 en el Centro de administración de Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="1840f-130">Para establecer la configuración de invitado de Grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1840f-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="1840f-131">En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, expanda **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="1840f-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="1840f-132">Haga clic en **Configuración de la organización**.</span><span class="sxs-lookup"><span data-stu-id="1840f-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="1840f-133">En la lista, haga clic en **Grupos de Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="1840f-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="1840f-134">Asegúrese de que las casillas **Permitir que los propietarios del grupo agreguen personas de fuera de la organización a Grupos de Microsoft 365 como invitados** y **Permitir que los miembros del grupo invitados accedan al contenido del grupo** están activadas.</span><span class="sxs-lookup"><span data-stu-id="1840f-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="1840f-135">Si ha realizado cambios, haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="1840f-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="1840f-136">SharePoint de uso compartido a nivel de organización</span><span class="sxs-lookup"><span data-stu-id="1840f-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="1840f-137">Para que los invitados tengan acceso a SharePoint sitios, la configuración de uso compartido SharePoint nivel de organización debe permitir el uso compartido con invitados.</span><span class="sxs-lookup"><span data-stu-id="1840f-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="1840f-138">La configuración de nivel de organización determina la configuración que estará disponible para sitios individuales.</span><span class="sxs-lookup"><span data-stu-id="1840f-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="1840f-139">La configuración del sitio no puede ser más permisiva que la configuración de nivel de organización.</span><span class="sxs-lookup"><span data-stu-id="1840f-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="1840f-140">Si desea permitir el uso compartido de archivos y carpetas sin autenticar, elija **Cualquiera**.</span><span class="sxs-lookup"><span data-stu-id="1840f-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="1840f-141">Si desea asegurarse de que todas las personas fuera de la organización tienen que autenticarse, elija **Invitados nuevos y existentes.**</span><span class="sxs-lookup"><span data-stu-id="1840f-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="1840f-142">Elija la configuración más permisiva que cualquier sitio de su organización necesite.</span><span class="sxs-lookup"><span data-stu-id="1840f-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="1840f-144">Para establecer la configuración de uso compartido de nivel de organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="1840f-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="1840f-145">En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, en **Centros de administración**, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="1840f-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="1840f-146">En el centro SharePoint administración, en el panel de navegación izquierdo, en **Directivas**, haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="1840f-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="1840f-147">Asegúrese de que el uso compartido externo de SharePoint está establecido en **Cualquier usuario** o **Invitados nuevos y existentes**.</span><span class="sxs-lookup"><span data-stu-id="1840f-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="1840f-148">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1840f-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="1840f-149">Crear un sitio</span><span class="sxs-lookup"><span data-stu-id="1840f-149">Create a site</span></span>

<span data-ttu-id="1840f-150">El siguiente paso es crear el sitio que tiene previsto usar para colaborar con invitados.</span><span class="sxs-lookup"><span data-stu-id="1840f-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="1840f-151">Para crear un sitio</span><span class="sxs-lookup"><span data-stu-id="1840f-151">To create a site</span></span>
1. <span data-ttu-id="1840f-152">En el Centro de administración de SharePoint, en **Sitios**, haga clic en **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="1840f-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="1840f-153">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1840f-153">Click **Create**.</span></span>
3. <span data-ttu-id="1840f-154">Haga clic **en Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="1840f-154">Click **Team site**.</span></span>
4. <span data-ttu-id="1840f-155">Escriba un nombre de sitio y escriba un nombre para el propietario del grupo (propietario del sitio).</span><span class="sxs-lookup"><span data-stu-id="1840f-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="1840f-156">En **Configuración avanzada,** elija si desea que este sitio sea público o privado.</span><span class="sxs-lookup"><span data-stu-id="1840f-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="1840f-157">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1840f-157">Click **Next**.</span></span>
7. <span data-ttu-id="1840f-158">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1840f-158">Click **Finish**.</span></span>

<span data-ttu-id="1840f-159">Invitaremos a los usuarios más tarde.</span><span class="sxs-lookup"><span data-stu-id="1840f-159">We'll invite users later.</span></span> <span data-ttu-id="1840f-160">A continuación, es importante comprobar la configuración de uso compartido de nivel de sitio para este sitio.</span><span class="sxs-lookup"><span data-stu-id="1840f-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="1840f-161">Configuración de uso compartido de nivel de sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="1840f-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="1840f-162">Compruebe la configuración de uso compartido de nivel de sitio para asegurarse de que permiten el tipo de acceso que desea para este sitio.</span><span class="sxs-lookup"><span data-stu-id="1840f-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="1840f-163">Por ejemplo, si establece la configuración de nivel de organización en **Cualquiera,** pero desea que todos los invitados se autentiquen para este sitio, asegúrese de que la configuración de uso compartido de nivel de sitio esté establecida en Invitados nuevos y **existentes.**</span><span class="sxs-lookup"><span data-stu-id="1840f-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="1840f-164">Tenga en cuenta que el sitio no se puede compartir con personas no autenticadas **(configuración** cualquiera), pero los archivos y carpetas individuales pueden hacerlo.</span><span class="sxs-lookup"><span data-stu-id="1840f-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="1840f-165">También puede usar etiquetas [de confidencialidad para controlar la configuración de uso compartido externo para SharePoint sitios](../compliance/sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="1840f-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="1840f-167">Para establecer la configuración de uso compartido de nivel de sitio</span><span class="sxs-lookup"><span data-stu-id="1840f-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="1840f-168">En el Centro de administración de SharePoint, en el panel de navegación izquierdo, expanda **Sitios** y haga clic en **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="1840f-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="1840f-169">Seleccione el sitio que desea compartir.</span><span class="sxs-lookup"><span data-stu-id="1840f-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="1840f-170">Haga clic en ...y haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="1840f-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="1840f-171">Asegúrese de que el uso compartido está establecido en **Cualquiera** o en **Invitados nuevos y existentes**.</span><span class="sxs-lookup"><span data-stu-id="1840f-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="1840f-172">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1840f-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="1840f-173">Invitar a usuarios</span><span class="sxs-lookup"><span data-stu-id="1840f-173">Invite users</span></span>

<span data-ttu-id="1840f-174">La configuración de uso compartido de invitados ya está configurada, por lo que puede empezar a agregar usuarios e invitados internos al sitio.</span><span class="sxs-lookup"><span data-stu-id="1840f-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="1840f-175">El acceso al sitio se controla a través del grupo Microsoft 365 asociado, por lo que vamos a agregar usuarios allí.</span><span class="sxs-lookup"><span data-stu-id="1840f-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="1840f-176">Para invitar usuarios internos a un grupo</span><span class="sxs-lookup"><span data-stu-id="1840f-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="1840f-177">Navegue hasta el sitio donde desea agregar usuarios.</span><span class="sxs-lookup"><span data-stu-id="1840f-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="1840f-178">Haga **clic en** El vínculo Miembros en la parte superior derecha que indica el recuento de miembros.</span><span class="sxs-lookup"><span data-stu-id="1840f-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="1840f-179">Haga clic en **Agregar miembros**.</span><span class="sxs-lookup"><span data-stu-id="1840f-179">Click **Add members**.</span></span>
4. <span data-ttu-id="1840f-180">Escriba los nombres o direcciones de correo electrónico de los usuarios que desea invitar al sitio y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1840f-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="1840f-181">Los invitados no se pueden agregar desde el sitio.</span><span class="sxs-lookup"><span data-stu-id="1840f-181">Guests can't be added from the site.</span></span> <span data-ttu-id="1840f-182">Debe agregarlos mediante Outlook en la web.</span><span class="sxs-lookup"><span data-stu-id="1840f-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="1840f-183">Por lo tanto, como requisito previo para agregar e invitar invitados a un grupo, haga clic en la dirección URL del sitio en la columna **DIRECCIÓN URL**  para navegar a la página específica del sitio.</span><span class="sxs-lookup"><span data-stu-id="1840f-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="1840f-184">En esta página, haga clic en el **icono del iniciador** de aplicaciones y **seleccione Outlook**.</span><span class="sxs-lookup"><span data-stu-id="1840f-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="1840f-185">Esta es la pantalla desde la que puedes invitar invitados a un grupo, para el que se describe el procedimiento a continuación.</span><span class="sxs-lookup"><span data-stu-id="1840f-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="1840f-186">Para invitar invitados a un grupo</span><span class="sxs-lookup"><span data-stu-id="1840f-186">To invite guests to a group</span></span>
1. <span data-ttu-id="1840f-187">En **Grupos**, haga clic en el grupo al que desea invitar invitados.</span><span class="sxs-lookup"><span data-stu-id="1840f-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="1840f-188">Abra la tarjeta de contacto de grupo, haga clic en El vínculo **Miembros** en la parte superior derecha (el vínculo que indica el número de miembros).</span><span class="sxs-lookup"><span data-stu-id="1840f-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="1840f-189">haga **clic en Agregar miembros**.</span><span class="sxs-lookup"><span data-stu-id="1840f-189">click **Add members**.</span></span>
4. <span data-ttu-id="1840f-190">Escriba las direcciones de correo electrónico de los invitados que desea invitar y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1840f-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="1840f-191">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1840f-191">Click **Close**.</span></span>
<span data-ttu-id="1840f-192">Tenga en cuenta  que solo debe hacer clic en Cerrar si no es el propietario del grupo y, como resultado, no puede agregar el invitado al grupo.</span><span class="sxs-lookup"><span data-stu-id="1840f-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="1840f-193">En tales casos, la solicitud para agregar el invitado al grupo se transfiere al propietario del grupo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="1840f-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="1840f-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="1840f-194">See also</span></span>

[<span data-ttu-id="1840f-195">Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados</span><span class="sxs-lookup"><span data-stu-id="1840f-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="1840f-196">Reducir la exposición accidental de archivos al compartirlos con invitados</span><span class="sxs-lookup"><span data-stu-id="1840f-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="1840f-197">Crear un entorno seguro de uso compartido para invitados</span><span class="sxs-lookup"><span data-stu-id="1840f-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="1840f-198">Crear una extranet B2B con invitados administrados</span><span class="sxs-lookup"><span data-stu-id="1840f-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="1840f-199">Integración de SharePoint y OneDrive con Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="1840f-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)