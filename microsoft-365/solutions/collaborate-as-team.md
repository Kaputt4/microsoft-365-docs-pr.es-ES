---
title: Colaborar con invitados en un equipo
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
description: Obtenga información sobre los pasos de configuración de Microsoft 365 necesarios para configurar un equipo para la colaboración de tareas, conversaciones y documentación con invitados en Teams.
ms.openlocfilehash: 34b7d5d47d7fb0c9196beda70184fa6510b6cc33
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780549"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="32422-103">Colaborar con invitados en un equipo</span><span class="sxs-lookup"><span data-stu-id="32422-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="32422-104">Si necesita colaborar con invitados en documentos, tareas y conversaciones, se recomienda usar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="32422-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="32422-105">Teams proporciona todas las características de colaboración disponibles en Office y SharePoint con chat persistente y un conjunto personalizable y extensible de herramientas de colaboración en una experiencia de usuario unificada.</span><span class="sxs-lookup"><span data-stu-id="32422-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="32422-106">En este artículo, veremos los pasos de configuración de Microsoft 365 necesarios para configurar un equipo para la colaboración con invitados.</span><span class="sxs-lookup"><span data-stu-id="32422-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="32422-107">Vídeo de demostración</span><span class="sxs-lookup"><span data-stu-id="32422-107">Video demonstration</span></span>

<span data-ttu-id="32422-108">En este vídeo se muestran los pasos de configuración descritos en este documento.</span><span class="sxs-lookup"><span data-stu-id="32422-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="32422-109">Configuración de colaboración externa de Azure</span><span class="sxs-lookup"><span data-stu-id="32422-109">Azure External collaboration settings</span></span>

<span data-ttu-id="32422-110">El uso compartido en Microsoft 365 se rige en su nivel más alto por la configuración de [colaboración externa B2B en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)</span><span class="sxs-lookup"><span data-stu-id="32422-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="32422-111">Si el uso compartido de invitados está deshabilitado o restringido en Azure AD, esta configuración invalida cualquier configuración de uso compartido que configure en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32422-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="32422-112">Compruebe la configuración de colaboración externa B2B para asegurarse de que no se bloquee el uso compartido con invitados.</span><span class="sxs-lookup"><span data-stu-id="32422-112">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de pantalla de la página de configuración de relaciones de organización de Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="32422-114">Para establecer la configuración de colaboración externa</span><span class="sxs-lookup"><span data-stu-id="32422-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="32422-115">Inicie sesión en Azure Active Directory en [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="32422-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="32422-116">En el panel de navegación izquierdo, haga clic **en Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="32422-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="32422-117">Haga **clic en Identidades externas.**</span><span class="sxs-lookup"><span data-stu-id="32422-117">Click **External identities**.</span></span>
4. <span data-ttu-id="32422-118">En la **pantalla Introducción,** en el panel de navegación izquierdo, haga clic en **Configuración de colaboración externa.**</span><span class="sxs-lookup"><span data-stu-id="32422-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="32422-119">Asegúrese de **que los administradores y los usuarios del** rol de invitador de invitado pueden invitar y que **los** miembros pueden invitar están establecidos en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="32422-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="32422-120">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="32422-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="32422-121">Tenga en cuenta la configuración de la **sección Restricciones de colaboración.**</span><span class="sxs-lookup"><span data-stu-id="32422-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="32422-122">Asegúrese de que los dominios de los invitados con los que desea colaborar no están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="32422-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="32422-123">Si trabaja con invitados de varias organizaciones, es posible que desee restringir su capacidad de acceso a los datos del directorio.</span><span class="sxs-lookup"><span data-stu-id="32422-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="32422-124">Esto les impedirá ver quién más es un invitado en el directorio.</span><span class="sxs-lookup"><span data-stu-id="32422-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="32422-125">Para ello, en Restricciones de  acceso de usuarios **invitados,** seleccione Los usuarios invitados tienen acceso limitado a las propiedades y la pertenencia a la configuración de objetos de directorio o el acceso de usuarios invitados está restringido a las propiedades y pertenencias de sus **propios** objetos de directorio.</span><span class="sxs-lookup"><span data-stu-id="32422-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="32422-126">Configuración de acceso de invitado de Teams</span><span class="sxs-lookup"><span data-stu-id="32422-126">Teams guest access settings</span></span>

<span data-ttu-id="32422-127">Teams tiene un conmutador maestro de encendido/apagado para el acceso de invitados y una variedad de configuraciones disponibles para controlar lo que los invitados pueden hacer en un equipo.</span><span class="sxs-lookup"><span data-stu-id="32422-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="32422-128">El modificador maestro, **Permitir el acceso de invitado en Teams** debe estar **encendido** para que el acceso de invitado funcione en Teams.</span><span class="sxs-lookup"><span data-stu-id="32422-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="32422-129">Compruebe que el acceso de invitado está habilitado en Teams y realice cualquier ajuste en la configuración de invitado en función de sus necesidades empresariales.</span><span class="sxs-lookup"><span data-stu-id="32422-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="32422-130">Tenga en cuenta que esta configuración afecta a todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="32422-130">Keep in mind that these settings affect all teams.</span></span>

![Captura de pantalla de la opción de acceso de invitados de Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="32422-132">Para establecer la configuración de acceso de invitados de Teams</span><span class="sxs-lookup"><span data-stu-id="32422-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="32422-133">Inicie sesión en el Centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="32422-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="32422-134">En el panel de navegación izquierdo, haga clic **en Mostrar todo**.</span><span class="sxs-lookup"><span data-stu-id="32422-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="32422-135">En **Centros de administración**, haga clic en **Teams**.</span><span class="sxs-lookup"><span data-stu-id="32422-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="32422-136">En el Centro de administración de Teams, en el panel de navegación izquierdo, **expanda** Configuración de toda la organización y haga clic en **Acceso de invitado.**</span><span class="sxs-lookup"><span data-stu-id="32422-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="32422-137">Asegúrese de que **Permitir el acceso de invitados en Teams** se haya establecido en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="32422-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="32422-138">Realice los cambios que quiera en la configuración de invitado adicional y luego haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="32422-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="32422-139">Una vez que el acceso de invitado de Teams está activado, también puede controlar el acceso de invitado a equipos individuales y a sus sitios de SharePoint asociados mediante etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="32422-139">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="32422-140">Para obtener más información, consulte [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="32422-140">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="32422-141">La configuración de invitado de Teams puede tardar hasta veinticuatro horas en activarse después de activarla.</span><span class="sxs-lookup"><span data-stu-id="32422-141">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="32422-142">Configuración de invitado de Grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="32422-142">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="32422-143">Teams usa Grupos de Microsoft 365 para la pertenencia a equipos.</span><span class="sxs-lookup"><span data-stu-id="32422-143">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="32422-144">La configuración de invitado de Grupos de Microsoft 365 debe estar activada para que el acceso de invitados en Teams funcione.</span><span class="sxs-lookup"><span data-stu-id="32422-144">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Captura de pantalla de la configuración de invitados de los grupos de Microsoft 365 en el Centro de administración de Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="32422-146">Para establecer la configuración de invitado de Grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="32422-146">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="32422-147">En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, expanda **Configuración.**</span><span class="sxs-lookup"><span data-stu-id="32422-147">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="32422-148">Haga clic **en Configuración de la organización.**</span><span class="sxs-lookup"><span data-stu-id="32422-148">Click **Org settings**.</span></span>
3. <span data-ttu-id="32422-149">En la lista, haga clic en **Grupos de Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="32422-149">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="32422-150">Asegúrese de que las casillas Permitir que los propietarios del grupo agreguen personas fuera de su organización a grupos de **Microsoft 365** como invitados y permitir que los miembros del grupo invitados accedan a las casillas de contenido **del** grupo están activadas.</span><span class="sxs-lookup"><span data-stu-id="32422-150">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="32422-151">Si realizó cambios, haga clic **en Guardar cambios.**</span><span class="sxs-lookup"><span data-stu-id="32422-151">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="32422-152">Configuración de uso compartido de nivel de organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="32422-152">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="32422-153">El contenido de Teams, como archivos, carpetas y listas, se almacena en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="32422-153">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="32422-154">Para que los invitados tengan acceso a estos elementos en Teams, la configuración de uso compartido en el nivel de organización de SharePoint debe permitir el uso compartido con invitados.</span><span class="sxs-lookup"><span data-stu-id="32422-154">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="32422-155">La configuración de nivel de organización determina qué configuración está disponible para sitios individuales, incluidos los sitios asociados con equipos.</span><span class="sxs-lookup"><span data-stu-id="32422-155">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="32422-156">La configuración del sitio no puede ser más permisiva que la configuración de nivel de organización.</span><span class="sxs-lookup"><span data-stu-id="32422-156">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="32422-157">Si desea permitir el uso compartido de archivos y carpetas con personas no autenticadas, elija **Cualquiera**.</span><span class="sxs-lookup"><span data-stu-id="32422-157">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="32422-158">Si desea asegurarse de que todos los invitados tienen que autenticarse, elija **Invitados nuevos y existentes.**</span><span class="sxs-lookup"><span data-stu-id="32422-158">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="32422-159">Elija la configuración más permisiva que necesite cualquier sitio de su organización.</span><span class="sxs-lookup"><span data-stu-id="32422-159">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="32422-161">Para establecer la configuración de uso compartido en el nivel de organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="32422-161">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="32422-162">En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, en Centros de **administración,** haga clic **en SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="32422-162">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="32422-163">En el Centro de administración de SharePoint, en el panel de navegación izquierdo, expanda **Directivas** y, a continuación, haga clic en **Compartir.**</span><span class="sxs-lookup"><span data-stu-id="32422-163">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="32422-164">Asegúrese de que el uso compartido externo para SharePoint esté establecido en **Cualquiera** o **Nuevo y los invitados existentes.**</span><span class="sxs-lookup"><span data-stu-id="32422-164">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="32422-165">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="32422-165">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="32422-166">Configuración de vínculos predeterminada en el nivel de organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="32422-166">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="32422-167">La configuración predeterminada de vínculos de archivos y carpetas determina la opción de vínculo que se mostrará a los usuarios de forma predeterminada cuando compartan un archivo o carpeta.</span><span class="sxs-lookup"><span data-stu-id="32422-167">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="32422-168">Los usuarios pueden cambiar el tipo de vínculo a una de las otras opciones antes de compartir, si lo desean.</span><span class="sxs-lookup"><span data-stu-id="32422-168">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="32422-169">Tenga en cuenta que esta configuración afecta a todos los equipos y sitios de SharePoint de su organización.</span><span class="sxs-lookup"><span data-stu-id="32422-169">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="32422-170">Elija uno de los siguientes tipos de vínculos que se seleccionarán de forma predeterminada cuando los usuarios compartan archivos y carpetas:</span><span class="sxs-lookup"><span data-stu-id="32422-170">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="32422-171">**Cualquiera con el vínculo:** elija esta opción si espera realizar una gran cantidad de uso compartido no autenticado de archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="32422-171">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="32422-172">Si desea permitir *vínculos* cualquiera pero le preocupa el uso compartido accidental no autenticado, considere una de las otras opciones como predeterminada.</span><span class="sxs-lookup"><span data-stu-id="32422-172">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="32422-173">Este tipo de vínculo solo está disponible si ha habilitado el uso compartido **cualquiera.**</span><span class="sxs-lookup"><span data-stu-id="32422-173">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="32422-174">**Solo las personas de su organización:** elija esta opción si espera que la mayoría del uso compartido de archivos y carpetas esté con personas dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="32422-174">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="32422-175">**Usuarios específicos:** considere esta opción si espera compartir muchos archivos y carpetas con invitados.</span><span class="sxs-lookup"><span data-stu-id="32422-175">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="32422-176">Este tipo de vínculo funciona con invitados y requiere que se autentiquen.</span><span class="sxs-lookup"><span data-stu-id="32422-176">This type of link works with guests and requires them to authenticate.</span></span>
 
![Captura de pantalla de la configuración de uso compartido de los archivos y carpetas de nivel de organización de SharePoint ](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="32422-178">Para establecer la configuración de vínculos predeterminada en el nivel de organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="32422-178">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="32422-179">Vaya a la página Uso compartido en el Centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="32422-179">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="32422-180">En **Vínculos de archivos y** carpetas, seleccione el vínculo para compartir predeterminado que desea usar.</span><span class="sxs-lookup"><span data-stu-id="32422-180">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="32422-181">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="32422-181">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="32422-182">Crear un equipo</span><span class="sxs-lookup"><span data-stu-id="32422-182">Create a team</span></span>

<span data-ttu-id="32422-183">El siguiente paso es crear el equipo que planea usar para colaborar con invitados.</span><span class="sxs-lookup"><span data-stu-id="32422-183">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="32422-184">Para crear un equipo</span><span class="sxs-lookup"><span data-stu-id="32422-184">To create a team</span></span>
1. <span data-ttu-id="32422-185">En Teams, en la **pestaña Teams,** haga clic en **Unirse o crear un** equipo en la parte inferior del panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="32422-185">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="32422-186">Haga **clic en Crear un equipo.**</span><span class="sxs-lookup"><span data-stu-id="32422-186">Click **Create a team**.</span></span>
3. <span data-ttu-id="32422-187">Haga **clic en Crear un equipo desde cero.**</span><span class="sxs-lookup"><span data-stu-id="32422-187">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="32422-188">Elija **Privado** o **Público.**</span><span class="sxs-lookup"><span data-stu-id="32422-188">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="32422-189">Escriba un nombre y una descripción para el equipo y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="32422-189">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="32422-190">Haga clic **en Omitir**.</span><span class="sxs-lookup"><span data-stu-id="32422-190">Click **Skip**.</span></span>

<span data-ttu-id="32422-191">Invitaremos a los usuarios más adelante.</span><span class="sxs-lookup"><span data-stu-id="32422-191">We'll invite users later.</span></span> <span data-ttu-id="32422-192">A continuación, es importante comprobar la configuración de uso compartido de nivel de sitio para el sitio de SharePoint asociado con el equipo.</span><span class="sxs-lookup"><span data-stu-id="32422-192">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="32422-193">Configuración de uso compartido en el nivel de sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="32422-193">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="32422-194">Compruebe la configuración de uso compartido de nivel de sitio para asegurarse de que permiten el tipo de acceso que desea para este equipo.</span><span class="sxs-lookup"><span data-stu-id="32422-194">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="32422-195">Por ejemplo, si establece la configuración de nivel de organización en **Cualquiera,** pero desea que todos los invitados se autentiquen para este equipo, asegúrese de que la configuración de uso compartido de nivel de sitio esté establecida en Invitados nuevos y **existentes.**</span><span class="sxs-lookup"><span data-stu-id="32422-195">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="32422-197">Para establecer la configuración de uso compartido de nivel de sitio</span><span class="sxs-lookup"><span data-stu-id="32422-197">To set site-level sharing settings</span></span>
1. <span data-ttu-id="32422-198">En el Centro de administración de SharePoint, en el panel de navegación izquierdo, expanda **Sitios** y haga clic **en Sitios activos.**</span><span class="sxs-lookup"><span data-stu-id="32422-198">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="32422-199">Seleccione el sitio para el equipo recién creado.</span><span class="sxs-lookup"><span data-stu-id="32422-199">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="32422-200">Haga clic en ... y elija **Compartir.**</span><span class="sxs-lookup"><span data-stu-id="32422-200">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="32422-201">Asegúrese de que el uso compartido está establecido en **Cualquiera** o **Invitados nuevos y existentes.**</span><span class="sxs-lookup"><span data-stu-id="32422-201">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="32422-202">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="32422-202">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="32422-203">Invitar a usuarios</span><span class="sxs-lookup"><span data-stu-id="32422-203">Invite users</span></span>

<span data-ttu-id="32422-204">La configuración de uso compartido de invitados ya está configurada, por lo que puede empezar a agregar usuarios e invitados internos a su equipo.</span><span class="sxs-lookup"><span data-stu-id="32422-204">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="32422-205">Para invitar a usuarios internos a un equipo</span><span class="sxs-lookup"><span data-stu-id="32422-205">To invite internal users to a team</span></span>
1. <span data-ttu-id="32422-206">En el equipo, haga **clic en Más opciones** ( ) **\*\*\*** y, a continuación, haga clic **en Agregar miembro**.</span><span class="sxs-lookup"><span data-stu-id="32422-206">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="32422-207">Escriba el nombre de la persona a la que desea invitar.</span><span class="sxs-lookup"><span data-stu-id="32422-207">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="32422-208">Haga clic en **Agregar** y, después, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="32422-208">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="32422-209">Para invitar a invitados a un equipo</span><span class="sxs-lookup"><span data-stu-id="32422-209">To invite guests to a team</span></span>
1. <span data-ttu-id="32422-210">En el equipo, haga **clic en Más opciones** ( ) **\*\*\*** y, a continuación, haga clic **en Agregar miembro**.</span><span class="sxs-lookup"><span data-stu-id="32422-210">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="32422-211">Escriba la dirección de correo electrónico del invitado al que desea invitar.</span><span class="sxs-lookup"><span data-stu-id="32422-211">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="32422-212">Haga **clic en Editar información de invitado.**</span><span class="sxs-lookup"><span data-stu-id="32422-212">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="32422-213">Escriba el nombre completo del invitado y haga clic en la marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="32422-213">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="32422-214">Haga clic en **Agregar** y, después, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="32422-214">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="32422-215">Vea también</span><span class="sxs-lookup"><span data-stu-id="32422-215">See also</span></span>

[<span data-ttu-id="32422-216">Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados</span><span class="sxs-lookup"><span data-stu-id="32422-216">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="32422-217">Reducir la exposición accidental de archivos al compartirlos con invitados</span><span class="sxs-lookup"><span data-stu-id="32422-217">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="32422-218">Crear un entorno seguro de uso compartido para invitados</span><span class="sxs-lookup"><span data-stu-id="32422-218">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="32422-219">Para obtener más información, consulte [Crear una extranet de B2B con invitados administrados](b2b-extranet.md).</span><span class="sxs-lookup"><span data-stu-id="32422-219">[Create a B2B extranet with managed guests](b2b-extranet.md)</span></span>

[<span data-ttu-id="32422-220">Integración de SharePoint y OneDrive con Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="32422-220">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="32422-221">Las opciones de uso compartido están en gris al compartir desde SharePoint o OneDrive</span><span class="sxs-lookup"><span data-stu-id="32422-221">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
