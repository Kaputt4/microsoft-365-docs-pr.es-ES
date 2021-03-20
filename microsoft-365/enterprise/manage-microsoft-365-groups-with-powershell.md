---
title: Administrar grupos de Microsoft 365 con PowerShell
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: En este artículo, obtenga información sobre cómo realizar tareas de administración comunes para grupos de Microsoft 365 en PowerShell.
ms.openlocfilehash: adf796ad2f2ee7a304c578cd42c700f2b44e7a5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911055"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="d11e6-103">Administrar grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d11e6-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="d11e6-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d11e6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d11e6-105">En este artículo se proporcionan los pasos para realizar tareas de administración comunes para grupos en Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d11e6-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="d11e6-106">También enumera los cmdlets de PowerShell para grupos.</span><span class="sxs-lookup"><span data-stu-id="d11e6-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="d11e6-107">Para obtener información sobre la administración de sitios de SharePoint, vea [Manage SharePoint Online sites using PowerShell](/sharepoint/manage-team-and-communication-sites-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="d11e6-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="d11e6-108">Vínculo a las directrices de uso de grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d11e6-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="d11e6-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="d11e6-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="d11e6-110">Cuando los [usuarios crean o editan un grupo en Outlook,](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)puede mostrarles un vínculo a las directrices de uso de su organización.</span><span class="sxs-lookup"><span data-stu-id="d11e6-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="d11e6-111">Por ejemplo, si necesita agregar un prefijo o sufijo específicos a un nombre de grupo.</span><span class="sxs-lookup"><span data-stu-id="d11e6-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="d11e6-112">Use Azure Active Directory (Azure AD) PowerShell para apuntar a los usuarios a las directrices de uso de su organización para grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d11e6-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="d11e6-113">Consulte [Cmdlets de Azure Active Directory](/azure/active-directory/enterprise-users/groups-settings-cmdlets) para configurar la configuración de grupo y siga los pasos descritos en **Crear** configuración en el nivel de directorio para definir el hipervínculo de la directriz de uso.</span><span class="sxs-lookup"><span data-stu-id="d11e6-113">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/enterprise-users/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="d11e6-114">Una vez que ejecute el cmdlet AAD, los usuarios verán el vínculo a sus directrices cuando creen o editan un grupo en Outlook.</span><span class="sxs-lookup"><span data-stu-id="d11e6-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![Crear un nuevo grupo con el vínculo directrices de uso](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Haga clic en Directrices de uso de grupos para ver las directrices de grupos de Office 365 de las organizaciones](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="d11e6-117">Permitir que los usuarios envíen como grupo de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d11e6-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="d11e6-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="d11e6-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="d11e6-119">Si desea habilitar los grupos de Microsoft 365 para "Enviar como", use los cmdlets [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) y [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) para configurar esto.</span><span class="sxs-lookup"><span data-stu-id="d11e6-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="d11e6-120">Una vez que habilite esta configuración, los usuarios del grupo de Microsoft 365 pueden usar Outlook o Outlook en la web para enviar y responder al correo electrónico como grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d11e6-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="d11e6-121">Los usuarios pueden ir al grupo, crear un nuevo correo electrónico y cambiar el campo "Enviar como" a la dirección de correo electrónico del grupo.</span><span class="sxs-lookup"><span data-stu-id="d11e6-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="d11e6-122">([También puede hacerlo en el Centro de administración de Exchange](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span><span class="sxs-lookup"><span data-stu-id="d11e6-122">([You can also do this in the Exchange Admin Center](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="d11e6-123">Use el siguiente script, reemplazando con el alias del grupo que desea actualizar y con el alias del usuario al que desea conceder *\<GroupAlias\>* *\<UserAlias\>* permisos.</span><span class="sxs-lookup"><span data-stu-id="d11e6-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="d11e6-124">[Conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para ejecutar este script.</span><span class="sxs-lookup"><span data-stu-id="d11e6-124">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="d11e6-125">Una vez ejecutado el cmdlet, los usuarios pueden ir a Outlook o Outlook en la web para enviar como grupo, agregando la dirección de correo electrónico del grupo al **campo** De.</span><span class="sxs-lookup"><span data-stu-id="d11e6-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="d11e6-126">Crear clasificaciones para grupos de Microsoft 365 en su organización</span><span class="sxs-lookup"><span data-stu-id="d11e6-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="d11e6-127">Puede crear etiquetas de confidencialidad que los usuarios de su organización pueden establecer al crear un grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d11e6-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="d11e6-128">Si desea clasificar grupos, se recomienda usar etiquetas de confidencialidad en lugar de la característica de clasificación de grupos anterior.</span><span class="sxs-lookup"><span data-stu-id="d11e6-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="d11e6-129">Para obtener información sobre el uso de etiquetas de confidencialidad, vea Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de [Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="d11e6-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d11e6-130">Si actualmente usa etiquetas de clasificación, ya no estarán disponibles para los usuarios que creen grupos una vez habilitadas las etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="d11e6-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="d11e6-131">Todavía puede usar la característica de clasificación de grupos anterior.</span><span class="sxs-lookup"><span data-stu-id="d11e6-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="d11e6-132">Puede crear clasificaciones que los usuarios de su organización pueden establecer al crear un grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d11e6-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="d11e6-133">Por ejemplo, puede permitir que los usuarios establezcan "Standard", "Secret" y "Top Secret" en los grupos que creen.</span><span class="sxs-lookup"><span data-stu-id="d11e6-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="d11e6-134">Las clasificaciones de grupos no se establecen de forma predeterminada y es necesario crearla para que los usuarios puedan establecerla.</span><span class="sxs-lookup"><span data-stu-id="d11e6-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="d11e6-135">Use Azure Active Directory PowerShell para apuntar a los usuarios a las directrices de uso de su organización para grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d11e6-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="d11e6-136">Consulte [Los cmdlets](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) de Azure Active Directory para configurar la configuración de grupos y siga los pasos descritos en Create **settings at the directory level** para definir la clasificación de Grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d11e6-136">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="d11e6-137">Para asociar una descripción a cada clasificación, puede usar el atributo de configuración  *ClassificationDescriptions* para definir.</span><span class="sxs-lookup"><span data-stu-id="d11e6-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="d11e6-138">donde Classification coincide con las cadenas de ClassificationList.</span><span class="sxs-lookup"><span data-stu-id="d11e6-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="d11e6-139">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d11e6-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="d11e6-140">Después de ejecutar el cmdlet de Azure Active Directory anterior para establecer la clasificación, ejecute el cmdlet [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) si desea establecer la clasificación de un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="d11e6-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="d11e6-141">O cree un nuevo grupo con una clasificación.</span><span class="sxs-lookup"><span data-stu-id="d11e6-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="d11e6-142">Consulte [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) y [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obtener más información sobre el uso de Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d11e6-142">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="d11e6-143">Una vez habilitada esta configuración, el propietario del grupo podrá elegir una clasificación en el menú desplegable  de Outlook en la Web y Outlook y guardarla en la página Editar grupo.</span><span class="sxs-lookup"><span data-stu-id="d11e6-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![Elegir clasificación de grupo de Microsoft 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="d11e6-145">Ocultar grupos de Microsoft 365 de la lista global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="d11e6-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="d11e6-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d11e6-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="d11e6-147">Puede especificar si un grupo de Microsoft 365 aparece en la lista global de direcciones (GAL) y otras listas de la organización.</span><span class="sxs-lookup"><span data-stu-id="d11e6-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="d11e6-148">Por ejemplo, si tiene un grupo de departamento legal que no desea que aparezca en la lista de direcciones, puede impedir que ese grupo aparezca en la GAL.</span><span class="sxs-lookup"><span data-stu-id="d11e6-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="d11e6-149">Ejecute el cmdlet Set-Unified Group para ocultar el grupo de la lista de direcciones como esta:</span><span class="sxs-lookup"><span data-stu-id="d11e6-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="d11e6-150">Permitir que solo los usuarios internos envíen mensajes a grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d11e6-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="d11e6-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d11e6-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="d11e6-152">Si no desea que los usuarios de otras organizaciones envíen correos electrónicos a un grupo de Microsoft 365, puede cambiar la configuración de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="d11e6-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="d11e6-153">Solo permitirá que los usuarios internos envíen un correo electrónico a su grupo.</span><span class="sxs-lookup"><span data-stu-id="d11e6-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="d11e6-154">Si un usuario externo intenta enviar un mensaje a ese grupo, se rechazará.</span><span class="sxs-lookup"><span data-stu-id="d11e6-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="d11e6-155">Ejecute el cmdlet Set-UnifiedGroup para actualizar esta configuración, como esta:</span><span class="sxs-lookup"><span data-stu-id="d11e6-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="d11e6-156">Agregar sugerencias de correo electrónico a grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d11e6-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="d11e6-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d11e6-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="d11e6-158">Siempre que un remitente intente enviar un correo electrónico a un grupo de Microsoft 365, se les puede mostrar una sugerencia de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d11e6-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="d11e6-159">Ejecute el cmdlet Set-Unified group para agregar una sugerencia de correo al grupo:</span><span class="sxs-lookup"><span data-stu-id="d11e6-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="d11e6-160">Junto con mailtip, también puede establecer MailTipTranslations, que especifica idiomas adicionales para la sugerencia de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d11e6-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="d11e6-161">Supongamos que desea tener la traducción al español y, a continuación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d11e6-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="d11e6-162">Cambiar el nombre para mostrar del grupo de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d11e6-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="d11e6-163">El nombre para mostrar especifica el nombre del grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d11e6-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="d11e6-164">Puede ver este nombre en el Centro de administración de Exchange o en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d11e6-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="d11e6-165">Puede editar el nombre para mostrar del grupo o asignar un nombre para mostrar a un grupo de Microsoft 365 existente ejecutando el Set-UnifiedGroup usuario:</span><span class="sxs-lookup"><span data-stu-id="d11e6-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="d11e6-166">Cambiar la configuración predeterminada de Grupos de Microsoft 365 para Outlook a Pública o Privada</span><span class="sxs-lookup"><span data-stu-id="d11e6-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="d11e6-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d11e6-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="d11e6-168">Los grupos de Microsoft 365 en Outlook se crean como privados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d11e6-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="d11e6-169">Si su organización desea que grupos de Microsoft 365 se cree como público de forma predeterminada (o de vuelta a Private), use esta sintaxis de cmdlet de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d11e6-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="d11e6-170">Para establecer en Privado:</span><span class="sxs-lookup"><span data-stu-id="d11e6-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="d11e6-171">Para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="d11e6-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="d11e6-172">Para obtener más información, [vea Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) y [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).</span><span class="sxs-lookup"><span data-stu-id="d11e6-172">To learn more, see [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="d11e6-173">Cmdlets de grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d11e6-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="d11e6-174">Los siguientes cmdlets se pueden usar con grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d11e6-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="d11e6-175">**Nombre de cmdlet**</span><span class="sxs-lookup"><span data-stu-id="d11e6-175">**Cmdlet name**</span></span>|<span data-ttu-id="d11e6-176">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d11e6-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d11e6-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="d11e6-177">Get-UnifiedGroup</span></span>](/powershell/module/exchange/get-unifiedgroup) <br/> |<span data-ttu-id="d11e6-178">Use este cmdlet para buscar grupos de Microsoft 365 existentes y ver las propiedades del objeto group</span><span class="sxs-lookup"><span data-stu-id="d11e6-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="d11e6-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="d11e6-179">Set-UnifiedGroup</span></span>](/powershell/module/exchange/set-unifiedgroup) <br/> |<span data-ttu-id="d11e6-180">Actualizar las propiedades de un grupo específico de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d11e6-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d11e6-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="d11e6-181">New-UnifiedGroup</span></span>](/powershell/module/exchange/new-unifiedgroup) <br/> |<span data-ttu-id="d11e6-182">Crear un nuevo grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d11e6-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="d11e6-183">Este cmdlet proporciona un conjunto mínimo de parámetros.</span><span class="sxs-lookup"><span data-stu-id="d11e6-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="d11e6-184">Para establecer valores para propiedades extendidas, use Set-UnifiedGroup después de crear el nuevo grupo</span><span class="sxs-lookup"><span data-stu-id="d11e6-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="d11e6-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="d11e6-185">Remove-UnifiedGroup</span></span>](/powershell/module/exchange/remove-unifiedgroup) <br/> |<span data-ttu-id="d11e6-186">Eliminar un grupo de Microsoft 365 existente</span><span class="sxs-lookup"><span data-stu-id="d11e6-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d11e6-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="d11e6-187">Get-UnifiedGroupLinks</span></span>](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |<span data-ttu-id="d11e6-188">Recuperar la información de pertenencia y propietario de un grupo de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d11e6-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d11e6-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="d11e6-189">Add-UnifiedGroupLinks</span></span>](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |<span data-ttu-id="d11e6-190">Agregar miembros, propietarios y suscriptores a un grupo de Microsoft 365 existente</span><span class="sxs-lookup"><span data-stu-id="d11e6-190">Add members, owners, and subscribers to an existing Microsoft 365 Group</span></span> <br/> |
|[<span data-ttu-id="d11e6-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="d11e6-191">Remove-UnifiedGroupLinks</span></span>](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |<span data-ttu-id="d11e6-192">Quitar propietarios y miembros de un grupo de Microsoft 365 existente</span><span class="sxs-lookup"><span data-stu-id="d11e6-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="d11e6-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="d11e6-193">Get-UserPhoto</span></span>](/powershell/module/exchange/get-userphoto) <br/> |<span data-ttu-id="d11e6-194">Se usa para ver información sobre la foto de usuario asociada a una cuenta.</span><span class="sxs-lookup"><span data-stu-id="d11e6-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="d11e6-195">Las fotos de usuario se almacenan en Active Directory</span><span class="sxs-lookup"><span data-stu-id="d11e6-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="d11e6-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="d11e6-196">Set-UserPhoto</span></span>](/powershell/module/exchange/set-userphoto) <br/> |<span data-ttu-id="d11e6-197">Se usa para asociar una foto de usuario con una cuenta.</span><span class="sxs-lookup"><span data-stu-id="d11e6-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="d11e6-198">Las fotos de usuario se almacenan en Active Directory</span><span class="sxs-lookup"><span data-stu-id="d11e6-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="d11e6-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="d11e6-199">Remove-UserPhoto</span></span>](/powershell/module/exchange/remove-userphoto) <br/> |<span data-ttu-id="d11e6-200">Quitar la foto de un grupo de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d11e6-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="d11e6-201">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d11e6-201">Related topics</span></span>

[<span data-ttu-id="d11e6-202">Actualizar listas de distribución a grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d11e6-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="d11e6-203">Administrar quién puede crear grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d11e6-203">Manage who can create Microsoft 365 Groups</span></span>](/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="d11e6-204">Administrar el acceso de invitado a grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d11e6-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="d11e6-205">Cambiar la pertenencia a grupos estáticos a dinámica en</span><span class="sxs-lookup"><span data-stu-id="d11e6-205">Change static group membership to dynamic in</span></span>](/azure/active-directory/users-groups-roles/groups-change-type)