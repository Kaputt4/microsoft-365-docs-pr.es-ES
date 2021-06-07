---
title: Configure equipos con protección de datos confidenciales
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
recommendations: false
description: Obtenga información sobre cómo implementar equipos con la protección de datos confidenciales.
ms.openlocfilehash: a3f715cb05ad1d5acf3c93c58959f12ebec46978
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788347"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a><span data-ttu-id="86c2c-103">Configure equipos con protección de datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="86c2c-103">Configure teams with protection for sensitive data</span></span>

<span data-ttu-id="86c2c-104">En este artículo, observamos la configuración de un equipo con un nivel de protección confidencial.</span><span class="sxs-lookup"><span data-stu-id="86c2c-104">In this article, we look at setting up a team for a sensitive level of protection.</span></span> <span data-ttu-id="86c2c-105">Asegúrese de que ha completado los pasos descritos en [Implementar equipos con la protección de línea base](configure-teams-baseline-protection.md) antes de seguir los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="86c2c-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span> <span data-ttu-id="86c2c-106">El nivel confidencial ofrece las siguientes protecciones adicionales al nivel de línea base:</span><span class="sxs-lookup"><span data-stu-id="86c2c-106">The sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="86c2c-p102">Una etiqueta de confidencialidad para el equipo que le permite activar o desactivar el uso compartido de invitados, y limita el acceso al contenido de SharePoint a solo web para dispositivos no administrados. Esta etiqueta también se puede usar para clasificar archivos.</span><span class="sxs-lookup"><span data-stu-id="86c2c-p102">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices. This label can also be used to classify files.</span></span>
- <span data-ttu-id="86c2c-109">Un tipo de vínculo para compartir predeterminado más restrictivo</span><span class="sxs-lookup"><span data-stu-id="86c2c-109">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="86c2c-110">Solo los propietarios del equipo podrán crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="86c2c-110">Only team owners can create private channels.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="86c2c-111">Demostración de vídeo</span><span class="sxs-lookup"><span data-stu-id="86c2c-111">Video demonstration</span></span>

<span data-ttu-id="86c2c-112">Vea este vídeo para conocer los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="86c2c-112">Watch this video for a walkthrough of the procedures described in this article.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NMS6]

## <a name="guest-sharing"></a><span data-ttu-id="86c2c-113">Uso compartido de invitados</span><span class="sxs-lookup"><span data-stu-id="86c2c-113">Guest sharing</span></span>

<span data-ttu-id="86c2c-114">Según la naturaleza de su empresa, es posible que quiera habilitar o no el uso compartido para invitados para equipos que contienen datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="86c2c-114">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain sensitive data.</span></span> <span data-ttu-id="86c2c-115">Si tiene previsto colaborar con personas ajenas a su organización en el equipo, le recomendamos que habilite el uso compartido de invitados.</span><span class="sxs-lookup"><span data-stu-id="86c2c-115">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="86c2c-116">Microsoft 365 incluye una variedad de características de seguridad y cumplimiento para ayudarle a compartir contenido confidencial de forma segura.</span><span class="sxs-lookup"><span data-stu-id="86c2c-116">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="86c2c-117">Por lo general, se trata de una opción más segura que enviar correo directamente a las personas de fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="86c2c-117">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="86c2c-118">Para más información sobre el uso compartido de invitados de forma segura, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="86c2c-118">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="86c2c-119">Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización</span><span class="sxs-lookup"><span data-stu-id="86c2c-119">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="86c2c-120">Crear un entorno seguro de uso compartido para invitados</span><span class="sxs-lookup"><span data-stu-id="86c2c-120">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="86c2c-121">Para permitir o bloquear el uso compartido de invitados, utilizamos una combinación de una etiqueta de confidencialidad para el equipo y controles de uso compartido a nivel de sitio para el sitio de SharePoint asociado, ambos tratados más adelante.</span><span class="sxs-lookup"><span data-stu-id="86c2c-121">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="86c2c-122">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="86c2c-122">Sensitivity labels</span></span>

<span data-ttu-id="86c2c-123">Para el nivel de protección confidencial, usaremos una etiqueta de confidencialidad para clasificar el equipo.</span><span class="sxs-lookup"><span data-stu-id="86c2c-123">For the sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="86c2c-124">Esta etiqueta también se puede usar para clasificar archivos individuales en este o en otros equipos, o en otras ubicaciones de archivo como SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="86c2c-124">This label can also be used to classify individual files in this or other teams, or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="86c2c-125">Como primer paso, debe habilitar las etiquetas de confidencialidad para Teams.</span><span class="sxs-lookup"><span data-stu-id="86c2c-125">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="86c2c-126">Consulte [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, los grupos de Microsoft 365 y los sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md) para más información.</span><span class="sxs-lookup"><span data-stu-id="86c2c-126">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="86c2c-127">Si ya tiene las etiquetas de confidencialidad implementadas en la organización, tenga en cuenta que se adapta a la estrategia general de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="86c2c-127">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="86c2c-128">Si es necesario, puede cambiar el nombre o la configuración para satisfacer las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="86c2c-128">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="86c2c-129">Cuando haya habilitado las etiquetas de confidencialidad para Teams, el siguiente paso es crear la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="86c2c-129">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="86c2c-130">Crear una etiqueta de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="86c2c-130">To create a sensitivity label</span></span>
1. <span data-ttu-id="86c2c-131">Abra el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="86c2c-131">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="86c2c-132">En **Soluciones**, haga clic en **Protección de la información**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-132">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="86c2c-133">Haga clic en **Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-133">Click **Create a label**.</span></span>
4. <span data-ttu-id="86c2c-134">Asigne un nombre a la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="86c2c-134">Give the label a name.</span></span> <span data-ttu-id="86c2c-135">Le sugerimos **confidencial**, pero puede elegir otro nombre si ya está en uso.</span><span class="sxs-lookup"><span data-stu-id="86c2c-135">We suggest **Sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="86c2c-136">Escriba un nombre y una descripción para el complemento y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-136">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="86c2c-137">En la página **Definir el ámbito de la página de la etiqueta**, seleccione **Archivos & mensajes de correo electrónico** y **Grupos & sitios** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-137">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="86c2c-138">En la página **Elija la configuración de protección de archivos y mensajes de correo electrónico**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-138">On the **Choose protection settings for files and emails** page, click **Next**.</span></span>
8. <span data-ttu-id="86c2c-139">En la página \*Etiquetado automático para archivos y mensajes de correo electrónico\*\*, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-139">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
9. <span data-ttu-id="86c2c-140">En la página **Definir la configuración de protección de los sitios y grupos**, seleccione **Configuración de privacidad y acceso de usuarios externo** y **Configuración de acceso de dispositivo y uso compartido externo** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-140">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
10. <span data-ttu-id="86c2c-141">En la página **Definir privacidad y acceso a usuarios externos**, en **Privacidad**, seleccione la opción **Privado**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-141">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
11. <span data-ttu-id="86c2c-142">Si desea permitir el acceso de invitado, en **Acceso de usuarios externos**, seleccione **Permitir que los propietarios del grupo de Microsoft 365 agreguen personas de fuera de su organización al grupo como invitados**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-142">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
12. <span data-ttu-id="86c2c-143">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-143">Click **Next**.</span></span>
13. <span data-ttu-id="86c2c-144">En la página **Definir el uso compartido externo y el acceso al dispositivo**, seleccione **Controlar el uso compartido externo en sitios de SharePoint etiquetados**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-144">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
14. <span data-ttu-id="86c2c-145">En **El contenido se puede compartir con**, elija **Invitados nuevos y existentes** si va a permitir el acceso de invitado o **Solo los usuarios de su organización** en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="86c2c-145">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
15. <span data-ttu-id="86c2c-146">En **Dispositivos no administrados**, elija **Permitir el acceso limitado, sólo a través de la web**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-146">Under **Access from unmanaged devices**, choose **Allow limited, web-only access**.</span></span>
16. <span data-ttu-id="86c2c-147">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-147">Click **Next**.</span></span>
17. <span data-ttu-id="86c2c-148">En la página **Etiquetado automático para las columnas de la base de datos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-148">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
18. <span data-ttu-id="86c2c-149">Haga clic en **Crear etiqueta** y después en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-149">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="86c2c-150">Una vez que haya creado la etiqueta, debe comunicarla a los usuarios que la van a usar.</span><span class="sxs-lookup"><span data-stu-id="86c2c-150">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="86c2c-151">Para la protección confidencial, haremos que la etiqueta esté disponible para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="86c2c-151">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="86c2c-152">Publique la etiqueta en el Centro de cumplimiento de Microsoft 365, en la pestaña **Directivas de etiqueta** de la página **Protección de la información**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-152">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="86c2c-153">Si tiene una directiva existente que se aplica a todos los usuarios, agregue esta etiqueta a esa directiva.</span><span class="sxs-lookup"><span data-stu-id="86c2c-153">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="86c2c-154">Si necesita crear una directiva nueva, vea [Publicar etiquetas de confidencialidad creando una directiva de etiqueta](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="86c2c-154">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="86c2c-155">Crear un equipo</span><span class="sxs-lookup"><span data-stu-id="86c2c-155">Create a team</span></span>

<span data-ttu-id="86c2c-156">La configuración adicional del escenario confidencial se hace en el sitio de SharePoint asociado al equipo, por lo que el siguiente paso es crear un equipo.</span><span class="sxs-lookup"><span data-stu-id="86c2c-156">Further configuration of the sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="86c2c-157">Para crear un equipo para información confidencial</span><span class="sxs-lookup"><span data-stu-id="86c2c-157">To create a team for sensitive information</span></span>
1. <span data-ttu-id="86c2c-158">En Teams, haga clic en **Teams** en el lado izquierdo de la aplicación, luego haga clic en **Unirse o crear un equipo** en la parte inferior de la lista de equipos.</span><span class="sxs-lookup"><span data-stu-id="86c2c-158">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="86c2c-159">Haga clic en **Crear equipo** (primera tarjeta, esquina superior izquierda).</span><span class="sxs-lookup"><span data-stu-id="86c2c-159">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="86c2c-160">Elija **Crear un equipo desde cero**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-160">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="86c2c-161">En la lista **Confidencialidad**, elija la etiqueta **confidencial** que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="86c2c-161">In the **Sensitivity** list, choose the **sensitive** label that you just created.</span></span>
5. <span data-ttu-id="86c2c-162">En **Privacidad**, haga clic en **Privado**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-162">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="86c2c-163">Escriba un nombre para el equipo y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-163">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="86c2c-164">Agregue usuarios al equipo y, después, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-164">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="86c2c-165">Configuración de canal privado</span><span class="sxs-lookup"><span data-stu-id="86c2c-165">Private channel settings</span></span>

<span data-ttu-id="86c2c-166">En este nivel, restringimos la creación de canales privados a los propietarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="86c2c-166">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="86c2c-167">Para restringir la creación de un canal privado</span><span class="sxs-lookup"><span data-stu-id="86c2c-167">To restrict private channel creation</span></span>
1. <span data-ttu-id="86c2c-168">En el equipo, haga clic en **Más opciones** y después en **Administrar equipo**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-168">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="86c2c-169">En la pestaña **Configuración**, expanda **Permisos de los miembros**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-169">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="86c2c-170">Desactive la casilla de verificación **Permitir a los miembros crear canales privados**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-170">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="86c2c-171">También puede usar [Directivas de equipos](/MicrosoftTeams/teams-policies) para controlar quién puede crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="86c2c-171">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="86c2c-172">Configuración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="86c2c-172">SharePoint settings</span></span>

<span data-ttu-id="86c2c-173">Cada vez que cree un nuevo equipo con la etiqueta confidencial, debe realizar dos pasos en SharePoint:</span><span class="sxs-lookup"><span data-stu-id="86c2c-173">Each time you create a new team with the sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="86c2c-174">Actualice la configuración de uso compartido de invitado para el sitio en el Centro de administración de SharePoint Online para actualizar el vínculo para compartir predeterminado a *Personas específicas*.</span><span class="sxs-lookup"><span data-stu-id="86c2c-174">Update the guest sharing settings for the site in the SharePoint admin center to update the default sharing link to *Specific people*.</span></span>
- <span data-ttu-id="86c2c-175">Actualice la configuración de uso compartido del sitio en el propio sitio para evitar que los miembros compartan el sitio.</span><span class="sxs-lookup"><span data-stu-id="86c2c-175">Update the site sharing settings in the site itself to prevent members from sharing the site.</span></span>

### <a name="site-default-sharing-link-settings"></a><span data-ttu-id="86c2c-176">Configuración del vínculo para compartir predeterminado del sitio</span><span class="sxs-lookup"><span data-stu-id="86c2c-176">Site default sharing link settings</span></span>

<span data-ttu-id="86c2c-177">Para actualizar el tipo de vínculo para compartir predeterminado del sitio</span><span class="sxs-lookup"><span data-stu-id="86c2c-177">To update the site default sharing link type</span></span>

1. <span data-ttu-id="86c2c-178">Abra el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="86c2c-178">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="86c2c-179">En **Sitios**, haga clic en **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-179">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="86c2c-180">Haga clic en el sitio que está asociado al equipo.</span><span class="sxs-lookup"><span data-stu-id="86c2c-180">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="86c2c-181">En **Uso compartido externo** de la pestaña **Directivas**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-181">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="86c2c-182">En Tipo de vínculo de uso compartido predeterminado, desactive la casilla de verificación **Igual que la configuración de nivel de organización** y seleccione **Personas específicas (solo las personas que el usuario especifica)**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-182">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **Specific people (only the people the user specifies)**.</span></span>
6. <span data-ttu-id="86c2c-183">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-183">Click **Save**.</span></span>

<span data-ttu-id="86c2c-184">Si quiere utilizar un script para esto como parte del proceso de creación del equipo, puede usar [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) con el parámetro `-DefaultSharingLinkType Direct` para cambiar el vínculo de uso compartido predeterminado a *Usuarios específicos*.</span><span class="sxs-lookup"><span data-stu-id="86c2c-184">If you want to script this as part of your team creation process, you can use [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) with the `-DefaultSharingLinkType Direct` parameter to change the default sharing link to *Specific people*.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="86c2c-185">Canales privados</span><span class="sxs-lookup"><span data-stu-id="86c2c-185">Private channels</span></span>

<span data-ttu-id="86c2c-186">Si agrega canales privados al equipo, cada canal privado crea un sitio de SharePoint nuevo con la configuración de uso compartido predeterminada.</span><span class="sxs-lookup"><span data-stu-id="86c2c-186">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="86c2c-187">Estos sitios no están visibles en el Centro de administración de SharePoint, por lo que debe usar el cmdlet Set-SPOSite de PowerShell para actualizar la configuración de uso compartido de invitado.</span><span class="sxs-lookup"><span data-stu-id="86c2c-187">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="86c2c-188">Configuración de uso compartido del sitio </span><span class="sxs-lookup"><span data-stu-id="86c2c-188">Site sharing settings</span></span>

<span data-ttu-id="86c2c-189">Para ayudar a garantizar que el sitio de SharePoint no se comparta con personas que no son miembros del equipo, limitamos dicho uso compartido a los propietarios.</span><span class="sxs-lookup"><span data-stu-id="86c2c-189">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span>

<span data-ttu-id="86c2c-190">Para configurar el uso compartido del sitio solo para propietarios</span><span class="sxs-lookup"><span data-stu-id="86c2c-190">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="86c2c-191">En Teams, vaya a la pestaña **General** del equipo que quiere actualizar.</span><span class="sxs-lookup"><span data-stu-id="86c2c-191">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="86c2c-192">En la barra de herramientas del equipo, haga clic en **Archivos**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-192">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="86c2c-193">Haga clic en los puntos suspensivos y, luego, en **Abrir en SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-193">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="86c2c-194">En la barra de herramientas, haga clic en el sitio de SharePoint subyacente, en el icono de configuración y, luego, en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-194">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="86c2c-195">En el panel **Permisos del sitio**, en **Uso compartido del sitio**, haga clic en **Cambiar cómo pueden compartir los miembros**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-195">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="86c2c-196">En **Permisos de uso compartido**, elija **Los propietarios y miembros del sitio y las personas con permisos de edición pueden compartir archivos y carpetas, pero solo los propietarios de sitios pueden compartir el sitio** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86c2c-196">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>


## <a name="see-also"></a><span data-ttu-id="86c2c-197">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86c2c-197">See Also</span></span>

[<span data-ttu-id="86c2c-198">Crear y configurar etiquetas de confidencialidad y sus directivas</span><span class="sxs-lookup"><span data-stu-id="86c2c-198">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)
