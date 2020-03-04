---
title: Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint (versión preliminar pública)
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Puede aplicar etiquetas en Microsoft Teams, en grupos de Office 365 y en sitios de SharePoint.
ms.openlocfilehash: 1e08df688a62d6c15ef0100b5379e62482ed7b50
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372038"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="31167-103">Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint (versión preliminar pública)</span><span class="sxs-lookup"><span data-stu-id="31167-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="31167-104">Al crear etiquetas de confidencialidad en el [Centro de cumplimiento de Microsoft 365](https://protection.office.com/), ahora puede aplicarlas a los siguientes contenedores: Microsoft Teams, grupos de Office 365 y sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31167-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="31167-105">Utilice la configuración de la etiqueta para controlar las siguientes opciones de estos contenedores:</span><span class="sxs-lookup"><span data-stu-id="31167-105">Use label settings to control the following options for these containers:</span></span>

- <span data-ttu-id="31167-106">La privacidad (pública o privada) de los sitios de los equipos conectados a grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="31167-106">Privacy (public or private) of Office 365 group-connected teams sites</span></span>
- <span data-ttu-id="31167-107">Acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="31167-107">External users access</span></span>
- <span data-ttu-id="31167-108">Acceso desde dispositivos no administrados</span><span class="sxs-lookup"><span data-stu-id="31167-108">Access from unmanaged devices</span></span> 

<span data-ttu-id="31167-109">Cuando aplica esta etiqueta a uno de los contenedores compatibles, la etiqueta aplica automáticamente las opciones configuradas en el sitio de SharePoint o en el sitio de grupo conectado.</span><span class="sxs-lookup"><span data-stu-id="31167-109">When you apply this label to one of the supported containers, the label automatically applies the configured options to the connected SharePoint site or team site.</span></span> 

<span data-ttu-id="31167-110">Sin embargo, el contenido de esos contenedores no hereda las etiquetas para configuraciones como el nombre de la etiqueta, las marcas visuales o el cifrado.</span><span class="sxs-lookup"><span data-stu-id="31167-110">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="31167-111">Para etiquetar archivos en sitios de SharePoint o sitios de grupo, [habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="31167-111">To label files in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="31167-112">Acerca de la versión preliminar pública para Microsoft Teams, grupos de Office 365 y sitios de SharePoint</span><span class="sxs-lookup"><span data-stu-id="31167-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="31167-113">Las etiquetas de confidencialidad de Microsoft Teams, grupos de Office 365 y sitios de SharePoint se están introduciendo gradualmente para los inquilinos y es posible que haya cambios antes de la versión final.</span><span class="sxs-lookup"><span data-stu-id="31167-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span> <span data-ttu-id="31167-114">Esta versión preliminar pública no funciona con las redes de entrega de contenido (CDN) de Office 365.</span><span class="sxs-lookup"><span data-stu-id="31167-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="31167-115">Antes de habilitar esta versión preliminar y configurar las etiquetas de confidencialidad para la nueva configuración, los usuarios pueden ver y aplicar etiquetas de confidencialidad en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="31167-115">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="31167-116">Por ejemplo, en Word:</span><span class="sxs-lookup"><span data-stu-id="31167-116">For example, from Word:</span></span>

![Una etiqueta de sensibilidad que se muestra en la aplicación de escritorio de Word](../media/sensitivity-label-word.png)

<span data-ttu-id="31167-118">Después de habilitar y configurar esta versión preliminar, los usuarios también pueden ver y aplicar etiquetas de confidencialidad en Microsoft Teams, en los grupos de Office 365 y en los sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31167-118">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="31167-119">Por ejemplo, al crear un sitio de grupo de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="31167-119">For example, when you create a new team site from SharePoint:</span></span>

![Una etiqueta de sensibilidad al crear un sitio de equipo desde SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="31167-121">Habilitar versión preliminar y sincronizar etiquetas</span><span class="sxs-lookup"><span data-stu-id="31167-121">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="31167-122">Dado que esta característica usa la funcionalidad de Azure AD, siga las instrucciones de la documentación de Azure AD para habilitar la versión preliminar: [asignar etiquetas de confidencialidad a grupos de Office 365 en Azure Active Directory (versión preliminar)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="31167-122">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Office 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="31167-123">En una sesión de PowerShell, conéctese al Centro de seguridad y cumplimiento con una cuenta profesional o educativa con privilegios de administrador global.</span><span class="sxs-lookup"><span data-stu-id="31167-123">In a PowerShell session, connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="31167-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="31167-124">For example:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```
    
    <span data-ttu-id="31167-125">Para obtener instrucciones completas, consulte [Conectarse al Powershell del Centro de seguridad y cumplimiento de Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="31167-125">For full instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="31167-126">Ejecute los siguientes comandos para sincronizar las etiquetas de confidencialidad en Azure AD, de modo que se puedan usar con los grupos de Office 365:</span><span class="sxs-lookup"><span data-stu-id="31167-126">Run the following command to synchronize your sensitivity labels to Azure AD, so that they can be used with Office 365 groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="31167-127">Cómo configurar opciones del sitio y los grupos al crear o editar etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="31167-127">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="31167-128">Ya está listo para crear o editar las etiquetas de confidencialidad que quiera y que estén disponibles para sitios y grupos.</span><span class="sxs-lookup"><span data-stu-id="31167-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="31167-129">El habilitar la versión preliminar hace que una nueva página sea visible en los asistentes de etiquetas de confidencialidad: **Configuración de sitio y grupo**</span><span class="sxs-lookup"><span data-stu-id="31167-129">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="31167-130">Si necesita ayuda para crear o editar una etiquetas de confidencialidad, vea las instrucciones en [Crear y configurar etiquetas de confidencialidad](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="31167-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="31167-131">En la nueva página **Configuración de sitio y grupo**, configure las opciones:</span><span class="sxs-lookup"><span data-stu-id="31167-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="31167-132">**Privacidad de los sitios de equipos conectados a grupos de Office 365**: la configuración predeterminada como **pública** está seleccionada automáticamente, lo que significa que cualquier persona de su organización puede tener acceso al sitio de grupo en el que se aplica esta etiqueta.</span><span class="sxs-lookup"><span data-stu-id="31167-132">**Privacy of Office 365 group-connected teams sites**: The default setting of **Public** is automatically selected, which means anyone in your organization can access the team site where this label is applied.</span></span> <span data-ttu-id="31167-133">Seleccione **Privado** cuando quiera que solo los miembros aprobados en la organización tengan acceso al sitio de grupo del grupo.</span><span class="sxs-lookup"><span data-stu-id="31167-133">Select **Private** when you want only approved members in your organization to access the group's team site.</span></span> 
    
    <span data-ttu-id="31167-134">La configuración seleccionada reemplaza a la configuración de privacidad anterior que puede estar configurada para el grupo y bloquea el valor de privacidad, para que solo se pueda modificar quitando primero la etiqueta de confidencialidad del sitio o grupo de equipo.</span><span class="sxs-lookup"><span data-stu-id="31167-134">The setting selected replaces a previous privacy setting that might be configured for the group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the team site or group.</span></span> <span data-ttu-id="31167-135">Después de quitar la etiqueta de confidencialidad, la configuración de privacidad de la etiqueta permanece y ahora puede cambiarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="31167-135">After you remove the sensitivity label, the privacy setting from the label remains and you can now change it if necessary.</span></span>

- <span data-ttu-id="31167-136">**Acceso de usuarios externos**: controla si el propietario del grupo puede [agregar invitados al grupo](/office365/admin/create-groups/manage-guest-access-in-groups).</span><span class="sxs-lookup"><span data-stu-id="31167-136">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="31167-137">**Dispositivos no administrados**: para [dispositivos sin administrar](/sharepoint/control-access-from-unmanaged-devices), permite acceso total, acceso de solo Web, o bloquear el acceso completamente.</span><span class="sxs-lookup"><span data-stu-id="31167-137">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![La pestaña de configuración del sitio y del grupo](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="31167-139">La configuración de sitio y grupo solo surte efecto al aplicar una etiqueta a un equipo, grupo o sitio.</span><span class="sxs-lookup"><span data-stu-id="31167-139">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="31167-140">El resto de opciones de configuración de etiqueta, como el cifrado y la marcación de contenido, no se aplican a todo el contenido del equipo, grupo o sitio.</span><span class="sxs-lookup"><span data-stu-id="31167-140">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="31167-141">De forma similar, si crea una etiqueta y no activa la configuración de sitio y de grupo, la etiqueta seguirá estando disponible cuando los usuarios creen equipos, grupos y sitios, pero solo se aplicará el nombre de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="31167-141">Similarly, if you create a label and don't turn on these site and group settings, the label will still be available when users create teams, groups, and sites, but only the label name will be applied.</span></span>

<span data-ttu-id="31167-142">Si la etiqueta de confidencialidad aún no se ha publicado, publíquela [agregándola a una directiva de etiqueta de confidencialidad](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="31167-142">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="31167-143">Los usuarios que tienen asignada una directiva de etiqueta de confidencialidad que incluye esta etiqueta podrán seleccionarla para sitios y grupos.</span><span class="sxs-lookup"><span data-stu-id="31167-143">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="31167-144">Administración de etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="31167-144">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="31167-145">Para crear, modificar y eliminar las etiquetas de confidencialidad que usa para Microsoft Teams, grupos de Office 365 y sitios de SharePoint se requiere una cuidadosa coordinación con las directivas de etiquetas de publicación para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="31167-145">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="31167-146">Evite errores de creación de sitios y grupos que puedan afectar a todos los usuarios con las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="31167-146">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="31167-147">**Guardar y publicar etiquetas:**</span><span class="sxs-lookup"><span data-stu-id="31167-147">**Creating and publishing labels:**</span></span>

<span data-ttu-id="31167-148">Una vez se crea y se publica una etiqueta de confidencialidad, puede tardar hasta 24 horas en ser visible para los usuarios en los equipos, grupos y sitios.</span><span class="sxs-lookup"><span data-stu-id="31167-148">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="31167-149">Siga los pasos siguientes para publicar una etiqueta para todos los usuarios en el espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="31167-149">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="31167-150">Cree la etiqueta de confidencialidad y publíquela solo para algunas cuentas de usuario del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="31167-150">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="31167-151">Espere 24 horas.</span><span class="sxs-lookup"><span data-stu-id="31167-151">Wait for 24 hours.</span></span>

3. <span data-ttu-id="31167-152">Cuando transcurran 24 horas, utilice una de las cuentas de usuario que especificó en el paso 1 para crear un equipo, un grupo de Office 365 o un sitio de SharePoint con la etiqueta creada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="31167-152">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="31167-153">Si no se han producido errores durante la operación de creación del paso 3, publique la etiqueta para todos los usuarios de su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="31167-153">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="31167-154">Si hay errores, póngase en contacto con el [Soporte técnico de Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="31167-154">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="31167-155">**Modificar y eliminar etiquetas publicadas:**</span><span class="sxs-lookup"><span data-stu-id="31167-155">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="31167-156">Si modifica o elimina una etiqueta de confidencialidad incluida en una o varias directivas de etiquetas, estas acciones pueden ocasionar errores en la creación de todos los equipos, grupos y sitios.</span><span class="sxs-lookup"><span data-stu-id="31167-156">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="31167-157">Para evitarlo, siga las instrucciones que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="31167-157">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="31167-158">Elimine la etiqueta de confidencialidad de todas las directivas de etiqueta que la incluyan.</span><span class="sxs-lookup"><span data-stu-id="31167-158">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="31167-159">Espere 48 horas.</span><span class="sxs-lookup"><span data-stu-id="31167-159">Wait for 48 hours.</span></span>

3. <span data-ttu-id="31167-160">Transcurrida la espera de 48 horas, pruebe a crear un equipo, grupo o sitio y compruebe que la etiqueta ya no es visible.</span><span class="sxs-lookup"><span data-stu-id="31167-160">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="31167-161">Si la etiqueta de confidencialidad no es visible, ya la puede modificar o eliminar de forma segura.</span><span class="sxs-lookup"><span data-stu-id="31167-161">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="31167-162">Si la etiqueta sigue visible, póngase en contacto con el [Soporte técnico de Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="31167-162">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-office-365-groups"></a><span data-ttu-id="31167-163">Asignar etiquetas de confidencialidad a grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="31167-163">Assign sensitivity labels to Office 365 groups</span></span>

<span data-ttu-id="31167-164">Ya está listo para aplicar la etiqueta o las etiquetas de confidencialidad a los grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="31167-164">You're now ready to apply the sensitivity label or labels to Office 365 groups.</span></span> <span data-ttu-id="31167-165">Regrese a la documentación de Azure AD para obtener instrucciones:</span><span class="sxs-lookup"><span data-stu-id="31167-165">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="31167-166">Asignar una etiqueta a un grupo nuevo en Azure Portal</span><span class="sxs-lookup"><span data-stu-id="31167-166">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="31167-167">Asignar una etiqueta a un grupo existente en Azure Portal</span><span class="sxs-lookup"><span data-stu-id="31167-167">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="31167-168">[Quitar una etiqueta a un grupo existente en Azure Portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="31167-168">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="31167-169">Aplicar una etiqueta de confidencialidad a un nuevo equipo</span><span class="sxs-lookup"><span data-stu-id="31167-169">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="31167-170">Los usuarios pueden seleccionar etiquetas de confidencialidad al crear nuevos equipos en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31167-170">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="31167-171">Cuando seleccionan el nivel de confidencialidad, la configuración de privacidad cambia según las necesidades.</span><span class="sxs-lookup"><span data-stu-id="31167-171">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="31167-172">En función de la configuración de acceso de usuarios externos que haya seleccionado para la etiqueta, los usuarios pueden o no, agregar al equipo personas de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="31167-172">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="31167-173">Más información sobre las etiquetas de confidencialidad para Teams</span><span class="sxs-lookup"><span data-stu-id="31167-173">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![La configuración de privacidad al crear un nuevo equipo](../media/privacy-setting-new-team.png)

<span data-ttu-id="31167-175">Después de crear el equipo, se muestra la etiqueta de confidencialidad en la esquina superior derecha de todos los canales.</span><span class="sxs-lookup"><span data-stu-id="31167-175">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![La etiqueta de confidencialidad se muestra en el equipo](../media/privacy-setting-teams.png)

<span data-ttu-id="31167-177">El servicio aplica automáticamente la misma etiqueta de confidencialidad al grupo de Office 365 y al sitio de grupo de SharePoint conectado.</span><span class="sxs-lookup"><span data-stu-id="31167-177">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="31167-178">Aplicar una etiqueta de confidencialidad a un nuevo grupo en Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="31167-178">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="31167-179">En Outlook en la Web, al crear un grupo, puede seleccionar o cambiar la opción **confidencialidad** para las etiquetas publicadas:</span><span class="sxs-lookup"><span data-stu-id="31167-179">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![Crear un grupo y seleccionar una opción en Confidencialidad](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="31167-181">Aplicar una etiqueta de confidencialidad a un nuevo sitio</span><span class="sxs-lookup"><span data-stu-id="31167-181">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="31167-182">Los administradores y los usuarios finales pueden seleccionar etiquetas de confidencialidad cuando [crean sitios de grupo y de comunicación modernos](/sharepoint/create-site-collection).</span><span class="sxs-lookup"><span data-stu-id="31167-182">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection).</span></span>

<span data-ttu-id="31167-183">Cuando los usuarios crean sitios modernos de equipo y comunicación, ya hay una etiqueta de confidencialidad seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="31167-183">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="31167-184">Los usuarios pueden seleccionar el icono de ayuda para obtener más información sobre las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="31167-184">Users can select the help icon to learn more about the labels.</span></span>

![Crear un sitio y seleccionar una opción en Confidencialidad](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="31167-186">Cuando los usuarios exploren el sitio, podrán ver el nombre de la etiqueta y las directivas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="31167-186">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Un sitio en el que se ha aplicado una etiqueta de confidencialidad](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="31167-188">Ver etiquetas de confidencialidad en el Centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="31167-188">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="31167-189">Para ver las etiquetas de confidencialidad aplicadas, use la página **Sitios activos** en el nuevo Centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31167-189">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="31167-190">Es posible que primero tenga que agregar la columna **confidencialidad**:</span><span class="sxs-lookup"><span data-stu-id="31167-190">You might need to first add the **Sensitivity** column:</span></span>

![La columna Confidencialidad en la página Sitios activos](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="31167-192">[Obtenga más información para administrar sitios en el nuevo centro de administración de SharePoint](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="31167-192">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="31167-193">Cambiar la configuración de sitio y grupo para una etiqueta</span><span class="sxs-lookup"><span data-stu-id="31167-193">Change site and group settings for a label</span></span>

<span data-ttu-id="31167-194">Siempre que haga un cambio en la configuración de sitio y de grupo de una etiqueta, debe ejecutar los comandos de PowerShell que se indican a continuación para que los equipos, sitios y grupos puedan usar la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="31167-194">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="31167-195">Se recomienda no cambiar la configuración del sitio y el grupo de una etiqueta después de haber aplicado la etiqueta a varios equipos, grupos o sitios.</span><span class="sxs-lookup"><span data-stu-id="31167-195">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="31167-196">Ejecute los siguientes comandos para conectarse al PowerShell del Centro de seguridad y cumplimiento de Office 365 y obtener la lista de etiquetas de confidencialidad y sus GUID.</span><span class="sxs-lookup"><span data-stu-id="31167-196">Run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="31167-197">Tome nota del GUID para la(s) etiqueta(s) que ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="31167-197">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="31167-198">Ahora, conéctese al PowerShell de Exchange Online y ejecute el cmdlet Get-UnifiedGroup, especificando el GUID de la etiqueta en vez del GUID de ejemplo de "e48058ea-98e8-4940-8db0-ba1310fd955e":</span><span class="sxs-lookup"><span data-stu-id="31167-198">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="31167-199">Para cada grupo, vuelva a aplicar la etiqueta de confidencialidad, especificando el GUID de la etiqueta en vez del GUID de ejemplo de "e48058ea-98e8-4940-8db0-ba1310fd955e":</span><span class="sxs-lookup"><span data-stu-id="31167-199">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="31167-200">Soporte técnico para las etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="31167-200">Support for the sensitivity labels</span></span>

<span data-ttu-id="31167-201">Puede usar las etiquetas de confidencialidad que ha configurado para la configuración del sitio y el grupo con las siguientes aplicaciones y servicios:</span><span class="sxs-lookup"><span data-stu-id="31167-201">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="31167-202">SharePoint en linea</span><span class="sxs-lookup"><span data-stu-id="31167-202">SharePoint Online</span></span>
- <span data-ttu-id="31167-203">Teams</span><span class="sxs-lookup"><span data-stu-id="31167-203">Teams</span></span>
- <span data-ttu-id="31167-204">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="31167-204">Outlook on the web</span></span>
- <span data-ttu-id="31167-205">Centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="31167-205">SharePoint admin center</span></span>
- <span data-ttu-id="31167-206">Centro de administración de Azure AD</span><span class="sxs-lookup"><span data-stu-id="31167-206">Azure AD admin center</span></span>

<span data-ttu-id="31167-207">Otras aplicaciones y servicios que actualmente no puede usar las etiquetas de confidencialidad que ha configurado para la configuración del sitio y el grupo incluyen:</span><span class="sxs-lookup"><span data-stu-id="31167-207">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="31167-208">Outlook para Mac</span><span class="sxs-lookup"><span data-stu-id="31167-208">Outlook for the Mac</span></span>
- <span data-ttu-id="31167-209">Outlook para dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="31167-209">Outlook mobile</span></span>
- <span data-ttu-id="31167-210">Outlook de escritorio para Windows</span><span class="sxs-lookup"><span data-stu-id="31167-210">Outlook desktop for Windows</span></span>
- <span data-ttu-id="31167-211">Formularios</span><span class="sxs-lookup"><span data-stu-id="31167-211">Forms</span></span>
- <span data-ttu-id="31167-212">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="31167-212">Dynamics 365</span></span>
- <span data-ttu-id="31167-213">Yammer</span><span class="sxs-lookup"><span data-stu-id="31167-213">Yammer</span></span>
- <span data-ttu-id="31167-214">Stream</span><span class="sxs-lookup"><span data-stu-id="31167-214">Stream</span></span>
- <span data-ttu-id="31167-215">Planner</span><span class="sxs-lookup"><span data-stu-id="31167-215">Planner</span></span>
- <span data-ttu-id="31167-216">Proyecto</span><span class="sxs-lookup"><span data-stu-id="31167-216">Project</span></span>
- <span data-ttu-id="31167-217">PowerBI</span><span class="sxs-lookup"><span data-stu-id="31167-217">PowerBI</span></span>
- <span data-ttu-id="31167-218">Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="31167-218">Teams admin center</span></span>
- <span data-ttu-id="31167-219">Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="31167-219">Microsoft 365 admin center</span></span>
- <span data-ttu-id="31167-220">Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="31167-220">Exchange admin center</span></span>


## <a name="classic-azure-ad-site-classification"></a><span data-ttu-id="31167-221">Clasificación clásica de sitio de Azure AD</span><span class="sxs-lookup"><span data-stu-id="31167-221">Classic Azure AD site classification</span></span>

<span data-ttu-id="31167-222">Office 365 ya no admite las antiguas clasificaciones para los nuevos grupos y sitios de SharePoint cuando se habilita esta vista previa.</span><span class="sxs-lookup"><span data-stu-id="31167-222">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="31167-223">Sin embargo, los grupos y sitios existentes aún muestran las clasificaciones antiguas a menos que las convierta para usar etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="31167-223">However, existing groups and sites still display the old classifications unless you convert them to use sensitivity labels.</span></span> <span data-ttu-id="31167-224">Entre las clasificaciones antiguas se incluyen la clasificación de sitios "modernos" que usted haya configurado, probablemente a través de PowerShell de Azure AD o la biblioteca principal PnP, donde se definían valores para la configuración de `ClassificationList`.</span><span class="sxs-lookup"><span data-stu-id="31167-224">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="31167-225">Por ejemplo, en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="31167-225">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="31167-226">Para obtener más información sobre el método antiguo de clasificación, consulte [Clasificación de sitios "modernos" de SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="31167-226">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="31167-227">Para convertir las clasificaciones antiguas en etiquetas de confidencialidad, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="31167-227">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="31167-228">Usar etiquetas existentes: especifique la configuración de la etiqueta que desee para los sitios y grupos al editar las etiquetas de confidencialidad existentes que ya están publicadas.</span><span class="sxs-lookup"><span data-stu-id="31167-228">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="31167-229">Crear etiquetas nuevas: especifique la configuración de la etiqueta que desee para los sitios y grupos creando y publicando nuevas etiquetas de confidencialidad que tengan los mismos nombres que las de las clasificaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="31167-229">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="31167-230">Luego:</span><span class="sxs-lookup"><span data-stu-id="31167-230">Then:</span></span> 

1. <span data-ttu-id="31167-231">Use PowerShell para aplicar las etiquetas de confidencialidad a los grupos de Office 365 y a los sitios de SharePoint mediante la asignación de nombres.</span><span class="sxs-lookup"><span data-stu-id="31167-231">Use PowerShell to apply the sensitivity labels to existing Office 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="31167-232">Vea la siguiente sección para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="31167-232">See the next section for instructions.</span></span>

2. <span data-ttu-id="31167-233">Quitar las clasificaciones antiguas de los grupos y sitios existentes.</span><span class="sxs-lookup"><span data-stu-id="31167-233">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="31167-234">Aunque no se puede impedir que los usuarios creen grupos nuevos en aplicaciones y servicios que aún no admiten las etiquetas de confidencialidad, puede ejecutar un script de PowerShell periódico para buscar grupos nuevos que los usuarios han creado con las clasificaciones anteriores y convertirlos para usar etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="31167-234">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-office-365-groups-to-sensitivity-labels"></a><span data-ttu-id="31167-235">Usar PowerShell para convertir clasificaciones de grupos de Office 365 a etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="31167-235">Use PowerShell to convert classifications for Office 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="31167-236">Asegúrese de que utiliza la versión 16.0.19418.12000 (o posterior) de Shell de SharePoint Online Management.</span><span class="sxs-lookup"><span data-stu-id="31167-236">Ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="31167-237">Si ya tiene la versión más reciente, vaya al paso 4.</span><span class="sxs-lookup"><span data-stu-id="31167-237">If you already have the latest version, skip to step 4.</span></span>

2. <span data-ttu-id="31167-238">Si tiene instalada una versión anterior de Shell de SharePoint Online Management de la galería de PowerShell, puede actualizar el módulo ejecutando el siguiente cmdlet.</span><span class="sxs-lookup"><span data-stu-id="31167-238">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>
    
    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

3. <span data-ttu-id="31167-239">Si tiene instalada una versión anterior de Shell de SharePoint Online Management del Centro de descarga de Microsoft, vaya a **agregar o quitar programas** y desinstale el Shell de SharePoint Online Management.</span><span class="sxs-lookup"><span data-stu-id="31167-239">If you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span> <span data-ttu-id="31167-240">Después, instale el último Shell de SharePoint Online Management desde el [Centro de descarga](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="31167-240">Then, install the latest SharePoint Online Management Shell from the [Download Center](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="31167-241">Utilice una cuenta profesional o educativa con privilegios de administrador global o de administrador de SharePoint en Office 365 para conectarse al Shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="31167-241">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="31167-242">Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="31167-242">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

5. <span data-ttu-id="31167-243">Ejecute los comandos siguientes para obtener la lista de etiquetas de confidencialidad y sus GUID.</span><span class="sxs-lookup"><span data-stu-id="31167-243">Run the following commands to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

6. <span data-ttu-id="31167-244">Tome nota de los GUID para las etiquetas de confidencialidad que quiere aplicar a los grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="31167-244">Make a note of the GUIDs for the sensitivity labels you want to apply to your Office 365 groups.</span></span>

7. <span data-ttu-id="31167-245">Use el comando siguiente como ejemplo para obtener la lista de grupos que actualmente tienen la clasificación de "general":</span><span class="sxs-lookup"><span data-stu-id="31167-245">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="31167-246">Para cada grupo, agregue la nueva etiqueta de sensibilidad GUID.</span><span class="sxs-lookup"><span data-stu-id="31167-246">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="31167-247">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="31167-247">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="31167-248">Auditar actividades de etiqueta de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="31167-248">Auditing sensitivity label activities</span></span>

<span data-ttu-id="31167-249">Si alguien carga un documento en un sitio protegido con una etiqueta de confidencialidad y el documento tiene una etiqueta de confidencialidad de [mayor prioridad](sensitivity-labels.md#label-priority-order-matters) que la etiqueta de confidencialidad que se aplica al sitio, esta acción no está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="31167-249">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="31167-250">Por ejemplo, aplicó la etiqueta **general** a un sitio de SharePoint y alguien carga en este sitio un documento etiquetado como **confidencial**.</span><span class="sxs-lookup"><span data-stu-id="31167-250">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="31167-251">Debido a que una etiqueta de confidencialidad con mayor prioridad identifica el contenido que es más confidencial que el contenido que tiene un orden de menor prioridad, esta situación podría ser un problema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="31167-251">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="31167-252">Aunque la acción no está bloqueada, se audita, por lo que puede identificar los documentos que no están alineados con la prioridad de las etiquetas y tomar las medidas necesarias.</span><span class="sxs-lookup"><span data-stu-id="31167-252">Although the action isn't blocked, it is audited, so you can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="31167-253">Por ejemplo, eliminar o mover el documento cargado del sitio.</span><span class="sxs-lookup"><span data-stu-id="31167-253">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="31167-254">No sería un problema de seguridad si el documento tiene una etiqueta de confidencialidad de menor prioridad que la etiqueta de confidencialidad aplicada al sitio.</span><span class="sxs-lookup"><span data-stu-id="31167-254">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="31167-255">Por ejemplo, un documento con la etiqueta **general** se carga en un sitio con la etiqueta **confidencial**.</span><span class="sxs-lookup"><span data-stu-id="31167-255">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="31167-256">En este escenario, no se genera un evento de auditoría.</span><span class="sxs-lookup"><span data-stu-id="31167-256">In this scenario, an auditing event isn't generated.</span></span>

<span data-ttu-id="31167-257">Para buscar el registro de auditoría para este evento, busque **Desfase detectado de la confidencialidad del documento** en la categoría de las **actividades de archivos y páginas**.</span><span class="sxs-lookup"><span data-stu-id="31167-257">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="31167-258">Cuando alguien agrega o quita una etiqueta de confidencialidad a un sitio o grupo, estas actividades también se auditan.</span><span class="sxs-lookup"><span data-stu-id="31167-258">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited.</span></span> <span data-ttu-id="31167-259">Estos eventos se pueden encontrar en la categoría de [actividades de etiqueta de confidencialidad](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities).</span><span class="sxs-lookup"><span data-stu-id="31167-259">These events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> 

<span data-ttu-id="31167-260">Para obtener instrucciones sobre cómo buscar el registro de auditoría, vea [buscar el registro de auditoría en el Centro de seguridad y cumplimiento](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="31167-260">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="31167-261">Solucionar el despliegue de la etiqueta de sensibilidad</span><span class="sxs-lookup"><span data-stu-id="31167-261">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="31167-262">¿Tiene problemas con las etiquetas de confidencialidad de Microsoft Teams, Grupos de Office 365 y sitios de SharePoint?</span><span class="sxs-lookup"><span data-stu-id="31167-262">Having problems with sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="31167-263">Compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="31167-263">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="31167-264">Las etiquetas no son visibles tras su publicación</span><span class="sxs-lookup"><span data-stu-id="31167-264">Labels not visible after publishing</span></span>
<span data-ttu-id="31167-265">Si tiene problemas al crear un equipo o grupo de Office 365 después de habilitar estas opciones de configuración o modificar la descripción de una etiqueta de confidencialidad, espere unas horas después de guardar los cambios en la etiqueta y, después, intente crear de nuevo el equipo o grupo.</span><span class="sxs-lookup"><span data-stu-id="31167-265">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="31167-266">Para obtener más información, consulte [Programar la implementación tras crear o cambiar una etiqueta de confidencialidad](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="31167-266">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="31167-267">Si sigue sin poder ver la nueva etiqueta de confidencialidad desde SharePoint Online, póngase en contacto con el [Soporte técnico de Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="31167-267">If you are still not able to see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="31167-268">Errores de creación de equipo, grupo o sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="31167-268">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="31167-269">Si experimenta errores de creación durante la versión preliminar pública, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="31167-269">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="31167-270">Asegúrese de que las etiquetas de confidencialidad no son obligatorias para algún usuario.</span><span class="sxs-lookup"><span data-stu-id="31167-270">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="31167-271">Puede desactivar las etiquetas de confidencialidad de Microsoft Teams, los grupos de Office 365 y los sitios de SharePoint siguiendo las mismas instrucciones que se indican en [Habilitar la compatibilidad con las etiquetas de confidencialidad en PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="31167-271">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="31167-272">Sin embargo, para deshabilitar la versión preliminar, en el paso 5, deshabilite la característica con `$setting["EnableMIPLabels"] = "False"`.</span><span class="sxs-lookup"><span data-stu-id="31167-272">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

