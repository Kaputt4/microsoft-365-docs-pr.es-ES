---
title: 'Teams para datos altamente regulados '
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cree un equipo seguro para almacenar los archivos más importantes y confidenciales.
ms.openlocfilehash: 4ef4d4e9b8ab437c90aac434db158cfb40f066cb
ms.sourcegitcommit: 7ee256132358a86f8c6ad143816fcfdde011ca74
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "37628354"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="35bf1-103">Teams para datos altamente regulados </span><span class="sxs-lookup"><span data-stu-id="35bf1-103">Teams for highly regulated data</span></span>

<span data-ttu-id="35bf1-104">Este artículo contiene recomendaciones y pasos para configurar un equipo privado en Microsoft Teams que bloquea el acceso a las características de Teams (como chats, reuniones y archivos) únicamente a los miembros y propietarios del grupo de Office 365 para el equipo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="35bf1-105">Más allá del acceso privado basado en el grupo de Office 365, este artículo describe cómo configurar el sitio de grupo de SharePoint privado subyacente, al que puede obtener acceso desde la sección **Archivos** de un canal de equipo, para la seguridad adicional que necesita para almacenar datos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="35bf1-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="35bf1-106">En este sitio de grupo de SharePoint, puede almacenar y colaborar en archivos, páginas, un calendario compartido, tareas, un bloc de notas y listas.</span><span class="sxs-lookup"><span data-stu-id="35bf1-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

<span data-ttu-id="35bf1-107">Los elementos de configuración para un equipo para datos altamente regulados son:</span><span class="sxs-lookup"><span data-stu-id="35bf1-107">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="35bf1-108">Un equipo privado con el grupo de Office 365 correspondiente que tenga cuentas de usuario del propietario y de los miembros.</span><span class="sxs-lookup"><span data-stu-id="35bf1-108">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="35bf1-109">Seguridad adicional en el sitio de SharePoint subyacente para el equipo que:</span><span class="sxs-lookup"><span data-stu-id="35bf1-109">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="35bf1-110">Impide que los miembros del sitio concedan acceso a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="35bf1-110">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="35bf1-111">Impide que los usuarios que no sean miembros del sitio soliciten acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="35bf1-111">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="35bf1-112">Una etiqueta de retención de Office 365 para el sitio de SharePoint subyacente que se aplica automáticamente a los nuevos archivos en el sitio de forma predeterminada para definir directivas de retención.</span><span class="sxs-lookup"><span data-stu-id="35bf1-112">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="35bf1-113">Una directiva de prevención de pérdida de datos (DLP) que usa la etiqueta de retención y bloquea a los usuarios para que no puedan compartir o enviar archivos fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="35bf1-113">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="35bf1-114">Una etiqueta de confidencialidad de Office 365 o una subetiqueta de una etiqueta altamente regulada que tiene permisos de cifrado y coautoría en el grupo de Office 365 del equipo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-114">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="35bf1-115">Los usuarios pueden aplicar la etiqueta o subetiqueta a archivos almacenados en la sección **Archivos** del equipo desde la opción Sensibilidad de la barra de menú en Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="35bf1-115">Users apply the label or sublabel to files stored in **Files** section of the team from the Sensitivity menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="35bf1-116">Esta es la configuración resultante con una etiqueta de sensibilidad.</span><span class="sxs-lookup"><span data-stu-id="35bf1-116">Here is the resulting configuration with a sensitivity label.</span></span>

![Configuración segura del escenario de equipo](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a><span data-ttu-id="35bf1-118">Fase 1: Configure un equipo para datos altamente regulados</span><span class="sxs-lookup"><span data-stu-id="35bf1-118">Phase 1: Configure a team for highly regulated data</span></span>

<span data-ttu-id="35bf1-119">La configuración descentralizada consta de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="35bf1-119">The end-to-end configuration consists of these steps:</span></span>

1. <span data-ttu-id="35bf1-120">Configure el acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="35bf1-120">Configure identity and device access.</span></span>
2. <span data-ttu-id="35bf1-121">Cree un equipo privado</span><span class="sxs-lookup"><span data-stu-id="35bf1-121">Create a team</span></span>
3. <span data-ttu-id="35bf1-122">Configure la seguridad adicional en el sitio de SharePoint subyacente.</span><span class="sxs-lookup"><span data-stu-id="35bf1-122">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="35bf1-123">Cree una etiqueta de retención y una directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="35bf1-123">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="35bf1-124">Cree la etiqueta o subetiqueta de la etiqueta altamente regulada.</span><span class="sxs-lookup"><span data-stu-id="35bf1-124">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="35bf1-125">Paso 1: Configure el acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="35bf1-125">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="35bf1-126">Para proteger el acceso al equipo de SharePoint subyacente, asegúrese de haber configurado las [directivas de acceso de identidades y dispositivos](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) y las [directivas de acceso recomendadas de SharePoint Online](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="35bf1-126">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the [recommended SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="35bf1-127">Paso 2: Cree un equipo privado</span><span class="sxs-lookup"><span data-stu-id="35bf1-127">Step 2: Create a private team</span></span>

<span data-ttu-id="35bf1-128">Siga [estas instrucciones](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) para crear un equipo privado.</span><span class="sxs-lookup"><span data-stu-id="35bf1-128">Follow [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private SharePoint team site.</span></span>

<span data-ttu-id="35bf1-129">Cuando se crea un equipo privado, estos son los permisos predeterminados:</span><span class="sxs-lookup"><span data-stu-id="35bf1-129">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="35bf1-130">El grupo de Office 365 para el equipo (el grupo de equipo) tiene propietarios de grupos y miembros de grupos</span><span class="sxs-lookup"><span data-stu-id="35bf1-130">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="35bf1-131">Para el sitio de SharePoint subyacente del equipo (el sitio de Equipo):</span><span class="sxs-lookup"><span data-stu-id="35bf1-131">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="35bf1-132">Los administradores de la colección de sitios están configurados para los propietarios del grupo de Equipo</span><span class="sxs-lookup"><span data-stu-id="35bf1-132">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="35bf1-133">Para el sitio de Equipo:</span><span class="sxs-lookup"><span data-stu-id="35bf1-133">For the Team Site:</span></span> 
    - <span data-ttu-id="35bf1-134">El grupo de SharePoint de propietarios del sitio de Equipo (con el nivel de permisos control total) está configurado en los propietarios del grupo de Equipo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-134">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="35bf1-135">El grupo de SharePoint de miembros del sitio de Equipo (con el nivel de permisos de edición) está configurado para los miembros del grupo de Equipo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-135">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="35bf1-136">El grupo de SharePoint de visitantes del sitio de Equipo (con el nivel de permisos de lectura) no tiene grupos ni cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="35bf1-136">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="35bf1-137">Estos son los permisos predeterminados para el sitio de Equipo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-137">Here are the default permissions for the Team Site.</span></span>

![Los permisos predeterminados de un sitio de Equipo](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="35bf1-139">Si ve el grupo de SharePoint \<nombre de equipo> grupo de propietarios de SharePoint para el nivel de permisos de edición, no se mostrará \<nombre de equipo> Propietarios.</span><span class="sxs-lookup"><span data-stu-id="35bf1-139">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="35bf1-140">Los permisos resultantes permiten lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="35bf1-140">The resulting permissions allow:</span></span>

- <span data-ttu-id="35bf1-141">Que los propietarios de los grupos de Team administren el sitio y tengan control total sobre el contenido del sitio.</span><span class="sxs-lookup"><span data-stu-id="35bf1-141">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="35bf1-142">Que los miembros de los grupos de Team puedan crear y editar archivos en el sitio.</span><span class="sxs-lookup"><span data-stu-id="35bf1-142">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="35bf1-143">El mantenimiento de permisos es el mismo que el mantenimiento del miembro del equipo y del propietario.</span><span class="sxs-lookup"><span data-stu-id="35bf1-143">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="35bf1-144">Esta es la configuración resultante hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="35bf1-144">Here’s the resulting configuration so far.</span></span>

![Paso 2 de la configuración segura del escenario de equipo](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="35bf1-146">Paso 3: Configure la seguridad adicional en el sitio de SharePoint subyacente</span><span class="sxs-lookup"><span data-stu-id="35bf1-146">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="35bf1-147">Desde el sitio de Equipo, configure estos ajustes de permisos.</span><span class="sxs-lookup"><span data-stu-id="35bf1-147">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="35bf1-148">En la barra de herramientas, haga clic en el icono de configuración y luego en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="35bf1-148">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="35bf1-149">En el panel **Permisos del sitio**, en **Configuración de uso compartido**, haga clic en **Cambiar configuración de uso compartido**.</span><span class="sxs-lookup"><span data-stu-id="35bf1-149">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="35bf1-150">En **Permisos de uso compartido**, seleccione **Solo los propietarios del sitio pueden compartir archivos, carpetas y el sitio**.</span><span class="sxs-lookup"><span data-stu-id="35bf1-150">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="35bf1-151">Desactive **Permitir solicitudes de acceso** y, después, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="35bf1-151">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="35bf1-152">Con estos ajustes de configuración, se deshabilita la posibilidad de que los miembros del grupo de Equipo compartan el sitio con otros miembros o que los usuarios que no son miembros soliciten el acceso al sitio de Equipo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-152">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

<span data-ttu-id="35bf1-153">Esta es la configuración resultante hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="35bf1-153">Here’s the resulting configuration so far.</span></span>

![Paso 3 de la configuración segura del escenario de equipo](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="35bf1-155">Paso 4: Cree una etiqueta de retención y una directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="35bf1-155">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="35bf1-156">Siga [estas instrucciones](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:</span><span class="sxs-lookup"><span data-stu-id="35bf1-156">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="35bf1-157">Crear y publicar una etiqueta de retención para datos altamente regulados (si es necesario).</span><span class="sxs-lookup"><span data-stu-id="35bf1-157">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="35bf1-158">Configurar el sitio de Equipo para la etiqueta de retención que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="35bf1-158">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="35bf1-159">Crear una directiva DLP para datos altamente regulados que usen la etiqueta de retención creada en el paso 2 y bloquee el envío de archivos fuera de la organización por parte de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="35bf1-159">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span> <span data-ttu-id="35bf1-160">También puede configurar la directiva para requerimientos adicionales, como por ejemplo, las regulaciones de las industrias de salud y finanzas, en función de las [plantillas de directiva de DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="35bf1-160">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="35bf1-161">Esta es la configuración resultante hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="35bf1-161">Here’s the resulting configuration so far.</span></span>

![Paso 4 de la configuración segura del escenario de equipo](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a><span data-ttu-id="35bf1-163">Paso 5: Cree la etiqueta o una subetiqueta de la etiqueta altamente regulada.</span><span class="sxs-lookup"><span data-stu-id="35bf1-163">Step 5: Create the label or a sublabel of the highly regulated label</span></span>

<span data-ttu-id="35bf1-164">A diferencia de una etiqueta de confidencialidad para datos altamente regulados que cualquier persona puede aplicar a cualquier archivo, un equipo seguro necesita su propia etiqueta o sub-etiqueta para que los archivos asignados:</span><span class="sxs-lookup"><span data-stu-id="35bf1-164">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="35bf1-165">Se cifren y el cifrado se desplace con el archivo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-165">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="35bf1-166">Contengan permisos personalizados para que solo los miembros del grupo de Equipo puedan abrirlo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-166">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="35bf1-167">Para lograr este nivel adicional de seguridad para los archivos almacenados en el sitio de Equipo, debe configurar una nueva etiqueta de confidencialidad que sea su propia etiqueta o una sub-etiqueta de la etiqueta general para archivos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="35bf1-167">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="35bf1-168">Solo los miembros del grupo de Equipo la verán en su lista de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="35bf1-168">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="35bf1-169">Usar una etiqueta de confidencialidad cuando necesite un número reducido de etiquetas tanto para los equipos de uso global como para los individuales privados.</span><span class="sxs-lookup"><span data-stu-id="35bf1-169">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="35bf1-170">Utilice una subetiqueta de confidencialidad cuando tenga un gran número de etiquetas o cuando desee organizar las etiquetas para equipos privados bajo su etiqueta altamente regulada.</span><span class="sxs-lookup"><span data-stu-id="35bf1-170">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams the under the highly regulated label.</span></span>

<span data-ttu-id="35bf1-171">[Siga estas instrucciones ](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar una etiqueta independiente o subetiqueta con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="35bf1-171">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="35bf1-172">El nombre de la etiqueta contiene el nombre del equipo</span><span class="sxs-lookup"><span data-stu-id="35bf1-172">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="35bf1-173">El cifrado está habilitado</span><span class="sxs-lookup"><span data-stu-id="35bf1-173">Encryption is enabled.</span></span>
- <span data-ttu-id="35bf1-174">El grupo de Equipo tiene permisos de Coautor</span><span class="sxs-lookup"><span data-stu-id="35bf1-174">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="35bf1-175">Esta es la configuración resultante con la nueva etiqueta.</span><span class="sxs-lookup"><span data-stu-id="35bf1-175">Here’s the resulting configuration with the new label.</span></span>

![Paso 5 de la configuración segura del escenario de equipo](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="35bf1-177">Esta es la relación entre la etiqueta de confidencialidad y el grupo de Equipo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-177">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![Relación entre el grupo de Equipo y los permisos de etiqueta](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="35bf1-179">Si configura la etiqueta o subetiqueta de confidencialidad para los permisos definidos por el usuario o con una fecha de expiración, no podrá abrir el archivo desde Teams o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="35bf1-179">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint.</span></span> <span data-ttu-id="35bf1-180">Debe usar una aplicación de Office.</span><span class="sxs-lookup"><span data-stu-id="35bf1-180">You must use an Office app.</span></span>
>

### <a name="custom-permissions"></a><span data-ttu-id="35bf1-181">Permisos personalizados</span><span class="sxs-lookup"><span data-stu-id="35bf1-181">Custom permissions</span></span>

<span data-ttu-id="35bf1-182">También puede configurar permisos personalizados de sitio de SharePoint para el sitio de Equipo y, si es necesario, su etiqueta de confidencialidad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="35bf1-182">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="35bf1-183">Aquí se muestran dos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="35bf1-183">Here are two examples.</span></span>

#### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="35bf1-184">Ejemplo 1: Delegar la administración del sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="35bf1-184">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="35bf1-185">Si el propietario del equipo no tiene la experiencia de administración de SharePoint o desea delegar la administración del sitio de Equipo, puede agregar la cuenta de usuario de un administrador del servicio de SharePoint a la lista de los propietarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-185">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="35bf1-186">Sin embargo, el administrador del servicio de SharePoint tendría acceso total al equipo y a todos sus recursos, y podrá abrir un archivo con la etiqueta de sensibilidad aplicada.</span><span class="sxs-lookup"><span data-stu-id="35bf1-186">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="35bf1-187">Para impedir que esto otorgue demasiados privilegios, agregue la cuenta de usuario del administrador del servicio de SharePoint al grupo de SharePoint Propietarios del sitio de Equipo en la configuración de permisos avanzados del sitio.</span><span class="sxs-lookup"><span data-stu-id="35bf1-187">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="35bf1-188">El administrador del servicio de SharePoint puede administrar el sitio, pero no podrá tener acceso al equipo y a ninguno de sus recursos, ni abrir los archivos con la etiqueta de sensibilidad asignada.</span><span class="sxs-lookup"><span data-stu-id="35bf1-188">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="35bf1-189">Ejemplo 2: Permitir el acceso de solo lectura a archivos etiquetados</span><span class="sxs-lookup"><span data-stu-id="35bf1-189">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="35bf1-190">Si el personal solo necesita ver el contenido de los archivos con etiquetas en el sitio de Equipo, agregue sus cuentas de usuario individuales al:</span><span class="sxs-lookup"><span data-stu-id="35bf1-190">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="35bf1-191">\<nombre de equipo > Grupo de visitantes de SharePoint, que tiene el nivel de permisos de lectura de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="35bf1-191">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="35bf1-192">La etiqueta de sensibilidad con los permisos del Visualizador.</span><span class="sxs-lookup"><span data-stu-id="35bf1-192">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="35bf1-193">Estos son los permisos resultantes en la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="35bf1-193">Here are the resulting permissions on the label.</span></span>

![Ejemplo de permisos personalizados para ver archivos etiquetados](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="35bf1-195">Los visitantes del sitio podrán tener acceso al sitio de Equipo directamente y ver el contenido de los archivos que tienen la subetiqueta aplicada.</span><span class="sxs-lookup"><span data-stu-id="35bf1-195">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="35bf1-196">Pero como no son miembros del grupo de Equipo no tendrán acceso al equipo ni a ninguno de sus recursos.</span><span class="sxs-lookup"><span data-stu-id="35bf1-196">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>


## <a name="phase-2-drive-user-adoption-for-team-members"></a><span data-ttu-id="35bf1-197">Fase 2: Fomentar que los miembros del equipo usen las funcionalidades</span><span class="sxs-lookup"><span data-stu-id="35bf1-197">Phase 2: Drive user adoption for remote workers</span></span>

<span data-ttu-id="35bf1-198">Una vez que el equipo esté listo, es hora de impulsar la adopción de este equipo y la seguridad adicional para los miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-198">With the team in place, it’s time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="35bf1-199">Paso 1: Entrenar a los usuarios</span><span class="sxs-lookup"><span data-stu-id="35bf1-199">Step 1: Train your users</span></span>

<span data-ttu-id="35bf1-200">Los miembros del grupo de Equipo pueden acceder al equipo y a todos sus recursos, incluidos los chats, las reuniones y otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="35bf1-200">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="35bf1-201">Al trabajar con archivos de la sección **Archivos** de un canal, los miembros del grupo de Equipo deben asignar la etiqueta o subetiqueta de confidencialidad a los archivos creados para el equipo seguro.</span><span class="sxs-lookup"><span data-stu-id="35bf1-201">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="35bf1-202">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-202">Here’s an example.</span></span>

![Ejemplo de una etiqueta aplicada a un archivo de un equipo seguro](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="35bf1-204">Cuando la etiqueta se aplica al archivo está protegido.</span><span class="sxs-lookup"><span data-stu-id="35bf1-204">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="35bf1-205">Los miembros del grupo de Equipo pueden abrirlo en Teams y colaborar en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="35bf1-205">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="35bf1-206">Se cifra y se incluyen los permisos de coautoría establecidos para los miembros del grupo de Equipo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-206">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="35bf1-207">Si el archivo abandona el sitio y se reenvía a un usuario malintencionado, el mismo tendrá que proporcionar credenciales de una cuenta de usuario que sea miembro del grupo de Equipo para abrir el archivo y ver su contenido.</span><span class="sxs-lookup"><span data-stu-id="35bf1-207">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="35bf1-208">Entrenar a los miembros del equipo:</span><span class="sxs-lookup"><span data-stu-id="35bf1-208">Train your team members:</span></span>

- <span data-ttu-id="35bf1-209">Sobre la importancia de usar el nuevo equipo para los chats, las reuniones, los archivos y los demás recursos del sitio del equipo y las consecuencias de la filtración de datos altamente regulados, tales como las repercusiones legales, las multas, el ramsonware o la pérdida de ventaja frente a la competencia.</span><span class="sxs-lookup"><span data-stu-id="35bf1-209">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="35bf1-210">Cómo acceder al equipo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-210">How to access the team.</span></span>
- <span data-ttu-id="35bf1-211">Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.</span><span class="sxs-lookup"><span data-stu-id="35bf1-211">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="35bf1-212">Cómo la directiva DLP les impide compartir archivos de forma externa.</span><span class="sxs-lookup"><span data-stu-id="35bf1-212">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="35bf1-213">Cómo etiquetar archivos con la etiqueta o la subetiqueta personalizada para el equipo.</span><span class="sxs-lookup"><span data-stu-id="35bf1-213">How to label files with the custom label or sublabel for the team.</span></span>
- <span data-ttu-id="35bf1-214">Cómo la etiqueta o subetiqueta protege los archivos incluso cuando se filtran del sitio.</span><span class="sxs-lookup"><span data-stu-id="35bf1-214">How the label or sublabel protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="35bf1-215">Esta formación debería incluir ejercicios prácticos para que los miembros del equipo puedan experimentar con las funcionalidades y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="35bf1-215">This training should include hands-on exercises so that your students can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="35bf1-216">Paso 2: Realice revisiones periódicas de uso y responda a los comentarios de los miembros del equipo</span><span class="sxs-lookup"><span data-stu-id="35bf1-216">Step 2: Conduct periodic reviews of usage and address worker feedback</span></span>

<span data-ttu-id="35bf1-217">En las semanas después de la formación haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="35bf1-217">In the weeks after training:</span></span>

- <span data-ttu-id="35bf1-218">Responda rápidamente a los comentarios de los miembros del equipo y ajuste las directivas y las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="35bf1-218">Quickly address remote worker feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="35bf1-219">Analice el uso del equipo y compárelo con las expectativas de uso.</span><span class="sxs-lookup"><span data-stu-id="35bf1-219">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="35bf1-220">Compruebe que los archivos altamente regulados se hayan etiquetado de forma correcta con la etiqueta o subetiqueta de confidencialidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="35bf1-220">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

  <span data-ttu-id="35bf1-221">Puede ver qué archivos tienen una etiqueta asignada viendo una carpeta en SharePoint y añadiendo la columna **Confidencialidad** a través de la opción **Mostrar/ocultar columnas** que está en **Añadir columna**.</span><span class="sxs-lookup"><span data-stu-id="35bf1-221">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="35bf1-222">Vuelva a entrenar a los usuarios cuando lo necesiten.</span><span class="sxs-lookup"><span data-stu-id="35bf1-222">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="35bf1-223">Vea también</span><span class="sxs-lookup"><span data-stu-id="35bf1-223">See also</span></span>

[<span data-ttu-id="35bf1-224">Sitios de SharePoint para datos altamente regulados</span><span class="sxs-lookup"><span data-stu-id="35bf1-224">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="35bf1-225">Cargas de trabajo y escenarios de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="35bf1-225">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="35bf1-226">[Biblioteca de productividad de Microsoft 365](https://aka.ms/productivitylibrary)(https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="35bf1-226">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="35bf1-227">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="35bf1-227">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
