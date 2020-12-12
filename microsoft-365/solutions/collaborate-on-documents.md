---
title: Colaborar con invitados en un documento
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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: En este artículo, aprenderá a colaborar con invitados en un documento de SharePoint y OneDrive.
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663516"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="15a7d-103">Colaborar con invitados en un documento</span><span class="sxs-lookup"><span data-stu-id="15a7d-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="15a7d-104">Si necesita colaborar con personas fuera de su organización en documentos de SharePoint o OneDrive, puede enviarles un vínculo de uso compartido al documento.</span><span class="sxs-lookup"><span data-stu-id="15a7d-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="15a7d-105">En este artículo, analizaremos los pasos de configuración de Microsoft 365 necesarios para configurar los vínculos de uso compartido de SharePoint y OneDrive según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="15a7d-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="15a7d-106">Vídeo de demostración</span><span class="sxs-lookup"><span data-stu-id="15a7d-106">Video demonstration</span></span>

<span data-ttu-id="15a7d-107">En este vídeo se muestran los pasos de configuración que se describen en este documento.</span><span class="sxs-lookup"><span data-stu-id="15a7d-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="15a7d-108">Configuración de colaboración externa de Azure</span><span class="sxs-lookup"><span data-stu-id="15a7d-108">Azure external collaboration settings</span></span>

<span data-ttu-id="15a7d-109">El uso compartido en Microsoft 365 se rige en su nivel más alto por la [configuración de colaboración externa B2B en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="15a7d-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="15a7d-110">Si el uso compartido de invitado está deshabilitado o restringido en Azure AD, esta configuración invalida cualquier configuración de uso compartido que configure en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15a7d-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="15a7d-111">Compruebe la configuración de colaboración externa B2B para asegurarse de que no se bloquee el uso compartido con invitados.</span><span class="sxs-lookup"><span data-stu-id="15a7d-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de pantalla de la página de configuración de relaciones de organización de Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="15a7d-113">Para establecer la configuración de colaboración externa</span><span class="sxs-lookup"><span data-stu-id="15a7d-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="15a7d-114">Inicie sesión en Azure Active Directory en [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="15a7d-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="15a7d-115">En el panel de navegación izquierdo, haga clic en **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="15a7d-116">Haga clic en **identidades externas**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-116">Click **External identities**.</span></span>
4. <span data-ttu-id="15a7d-117">En la **pantalla introducción** , en el panel de navegación de la izquierda, haga clic en **configuración de colaboración externa**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="15a7d-118">Asegúrese de que los **administradores y los usuarios de la función invitador invitado puedan** invitar y que **los miembros puedan invitar** están establecidos en **sí**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="15a7d-119">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="15a7d-120">Anote la configuración de la sección **restricciones de colaboración** .</span><span class="sxs-lookup"><span data-stu-id="15a7d-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="15a7d-121">Asegúrese de que los dominios de los invitados con los que desea colaborar no están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="15a7d-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="15a7d-122">Si trabaja con invitados de varias organizaciones, es posible que desee restringir su capacidad para obtener acceso a los datos del directorio.</span><span class="sxs-lookup"><span data-stu-id="15a7d-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="15a7d-123">Esto impedirá que vean quién más es un invitado en el directorio.</span><span class="sxs-lookup"><span data-stu-id="15a7d-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="15a7d-124">Para ello, en **restricciones de acceso de usuarios invitados**, seleccione **los usuarios invitados tienen restringido el acceso a las propiedades y la pertenencia de los objetos de directorio la configuración** o **el acceso de usuario invitado está restringido a las propiedades y pertenencia de sus propios objetos de directorio**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="15a7d-125">Configuración de uso compartido en el nivel de la organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="15a7d-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="15a7d-126">Para que las personas de fuera de la organización tengan acceso a un documento en SharePoint o OneDrive, la configuración de uso compartido en el nivel de la organización de SharePoint y OneDrive debe permitir el uso compartido con personas de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="15a7d-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="15a7d-127">La configuración de nivel de organización para SharePoint determina la configuración que estará disponible para los sitios de SharePoint individuales.</span><span class="sxs-lookup"><span data-stu-id="15a7d-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="15a7d-128">La configuración del sitio no puede ser más permisiva que la configuración de nivel de organización.</span><span class="sxs-lookup"><span data-stu-id="15a7d-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="15a7d-129">La configuración en el nivel de la organización para OneDrive determina el nivel de uso compartido que estará disponible en las bibliotecas de OneDrive de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="15a7d-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="15a7d-130">Para SharePoint y OneDrive, si quiere permitir el uso compartido de archivos y carpetas sin autenticar, elija **cualquier persona**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="15a7d-131">Si quiere asegurarse de que las personas de fuera de su organización tengan que autenticarse, elija los **invitados nuevos y existentes**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="15a7d-132">*Todos* los vínculos es la forma más sencilla de compartir: los usuarios ajenos a la organización pueden abrir el vínculo sin autenticación y tienen la posibilidad de pasarlo a otros.</span><span class="sxs-lookup"><span data-stu-id="15a7d-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="15a7d-133">Para SharePoint, elija la configuración más permisiva que necesitará cualquier sitio de la organización.</span><span class="sxs-lookup"><span data-stu-id="15a7d-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="15a7d-135">Para establecer la configuración de uso compartido en el nivel de la organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="15a7d-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="15a7d-136">En el centro de administración de Microsoft 365, en el panel de navegación izquierdo, en **centros de administración**, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="15a7d-137">En el centro de administración de SharePoint, en el panel de navegación izquierdo, en **directivas**, haga clic en **uso compartido**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="15a7d-138">Asegúrese de que el uso compartido externo para SharePoint o OneDrive está establecido en **cualquiera** o **invitados nuevos o existentes**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="15a7d-139">(Tenga en cuenta que la configuración de OneDrive no puede ser más permisiva que la configuración de SharePoint).</span><span class="sxs-lookup"><span data-stu-id="15a7d-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="15a7d-140">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="15a7d-141">Configuración de vínculos predeterminados de nivel de organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="15a7d-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="15a7d-142">La configuración predeterminada de los vínculos de archivos y carpetas determina la opción de vínculo que se mostrará a los usuarios de forma predeterminada cuando compartan un archivo o una carpeta.</span><span class="sxs-lookup"><span data-stu-id="15a7d-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="15a7d-143">Los usuarios pueden cambiar el tipo de vínculo a una de las otras opciones antes de compartirlo, si lo deseas.</span><span class="sxs-lookup"><span data-stu-id="15a7d-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="15a7d-144">Tenga en cuenta que esta configuración afecta a los sitios de SharePoint de su organización, así como a OneDrive.</span><span class="sxs-lookup"><span data-stu-id="15a7d-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="15a7d-145">Elija un vínculo en cualquiera de los siguientes tipos que, a continuación, se selecciona de forma predeterminada cuando los usuarios comparten archivos y carpetas:</span><span class="sxs-lookup"><span data-stu-id="15a7d-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="15a7d-146">**Cualquiera que tenga el vínculo** : elija esta opción si tiene previsto compartir una gran cantidad de archivos y carpetas sin autenticar.</span><span class="sxs-lookup"><span data-stu-id="15a7d-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="15a7d-147">Si desea permitir que *todos* los vínculos, pero le preocupa el uso compartido no autenticado accidentalmente, considere una de las otras opciones como predeterminada.</span><span class="sxs-lookup"><span data-stu-id="15a7d-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="15a7d-148">Este tipo de vínculo solo está disponible si ha habilitado a **todos los usuarios** que comparten el mismo.</span><span class="sxs-lookup"><span data-stu-id="15a7d-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="15a7d-149">**Solo las personas de su organización** : elija esta opción si prevé que la mayoría del uso compartido de archivos y carpetas sea para personas dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="15a7d-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="15a7d-150">**Personas específicas** : considere esta opción si espera compartir muchos archivos y carpetas con los invitados.</span><span class="sxs-lookup"><span data-stu-id="15a7d-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="15a7d-151">Este tipo de vínculo funciona con los invitados y requiere que se autentiquen.</span><span class="sxs-lookup"><span data-stu-id="15a7d-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Captura de pantalla de la configuración de uso compartido de los archivos y carpetas de nivel de organización de SharePoint ](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="15a7d-153">Para establecer la configuración de vínculos predeterminados de nivel de organización de SharePoint y OneDrive</span><span class="sxs-lookup"><span data-stu-id="15a7d-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="15a7d-154">Vaya a la página de uso compartido en el centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="15a7d-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="15a7d-155">En **vínculos de archivos y carpetas**, seleccione el vínculo de uso compartido predeterminado que desee usar.</span><span class="sxs-lookup"><span data-stu-id="15a7d-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="15a7d-156">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="15a7d-157">Para establecer el permiso para el vínculo para compartir, en **elegir el permiso que está seleccionado de forma predeterminada para los vínculos para compartir.**</span><span class="sxs-lookup"><span data-stu-id="15a7d-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="15a7d-158">Seleccione **Ver** si no desea que los usuarios no autenticados realicen cambios en los archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="15a7d-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="15a7d-159">Seleccione **Editar** si desea permitir que los usuarios no autenticados realicen cambios en los archivos y las carpetas.</span><span class="sxs-lookup"><span data-stu-id="15a7d-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="15a7d-160">Tenga en cuenta que las dos opciones de PREUSO anteriores pueden aplicarse no solo a los usuarios invitados o externos, sino también a los usuarios internos.</span><span class="sxs-lookup"><span data-stu-id="15a7d-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="15a7d-161">La opción de permiso que elija está determinada por su propia discreción.</span><span class="sxs-lookup"><span data-stu-id="15a7d-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="15a7d-162">Para establecer permisos para vínculos que permiten el uso compartido con cualquiera</span><span class="sxs-lookup"><span data-stu-id="15a7d-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="15a7d-163">En **estos vínculos puede conceder estos permisos:** subpanel,</span><span class="sxs-lookup"><span data-stu-id="15a7d-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="15a7d-164">En la lista desplegable **archivos** ,</span><span class="sxs-lookup"><span data-stu-id="15a7d-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="15a7d-165">Seleccione **ver y editar** si desea permitir que los usuarios no autenticados realicen cambios en los archivos.</span><span class="sxs-lookup"><span data-stu-id="15a7d-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="15a7d-166">Seleccione **Ver** si no desea que los usuarios no autenticados realicen cambios en los archivos.</span><span class="sxs-lookup"><span data-stu-id="15a7d-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="15a7d-167">En la lista desplegable **carpetas** ,</span><span class="sxs-lookup"><span data-stu-id="15a7d-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="15a7d-168">Seleccione **ver, editar y cargar** si desea permitir que los usuarios no autenticados realicen cambios en las carpetas.</span><span class="sxs-lookup"><span data-stu-id="15a7d-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="15a7d-169">Seleccione **Ver** si no desea que los usuarios no autenticados realicen cambios en las carpetas.</span><span class="sxs-lookup"><span data-stu-id="15a7d-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="15a7d-170">Configuración de uso compartido en el nivel de sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="15a7d-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="15a7d-171">Si está compartiendo archivos y carpetas que están en un sitio de SharePoint, también debe comprobar la configuración de uso compartido de nivel de sitio para ese sitio.</span><span class="sxs-lookup"><span data-stu-id="15a7d-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="15a7d-173">Para establecer la configuración de uso compartido de nivel de sitio</span><span class="sxs-lookup"><span data-stu-id="15a7d-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="15a7d-174">En el centro de administración de SharePoint, en el panel de navegación izquierdo, expanda **sitios** y haga clic en **sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="15a7d-175">Seleccione el sitio en el que desea compartir archivos y carpetas con los invitados.</span><span class="sxs-lookup"><span data-stu-id="15a7d-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="15a7d-176">Desplácese hacia la derecha por la fila (en la que está presente el sitio seleccionado) y haga clic en cualquier lugar de la columna **uso compartido externo** .</span><span class="sxs-lookup"><span data-stu-id="15a7d-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="15a7d-177">En la página que aparece, haga clic en la ficha **directivas** .</span><span class="sxs-lookup"><span data-stu-id="15a7d-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="15a7d-178">En el panel **uso compartido externo** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="15a7d-179">Asegúrese de que el uso compartido está establecido en **todos** o en **invitados nuevos o existentes**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="15a7d-180">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="15a7d-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="15a7d-181">Invitar a usuarios</span><span class="sxs-lookup"><span data-stu-id="15a7d-181">Invite users</span></span>

<span data-ttu-id="15a7d-182">La configuración del uso compartido de invitados ya está configurada; por lo tanto, ahora los usuarios pueden compartir archivos y carpetas con personas de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="15a7d-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="15a7d-183">Consulte [compartir archivos y carpetas de OneDrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) y [compartir archivos o carpetas de SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="15a7d-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="15a7d-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="15a7d-184">See also</span></span>

[<span data-ttu-id="15a7d-185">Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados</span><span class="sxs-lookup"><span data-stu-id="15a7d-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="15a7d-186">Reducir la exposición accidental de archivos al compartirlos con invitados</span><span class="sxs-lookup"><span data-stu-id="15a7d-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="15a7d-187">Integración de SharePoint y OneDrive con la B2B de Azure AD</span><span class="sxs-lookup"><span data-stu-id="15a7d-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
