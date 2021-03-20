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
# <a name="manage-microsoft-365-groups-with-powershell"></a>Administrar grupos de Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

En este artículo se proporcionan los pasos para realizar tareas de administración comunes para grupos en Microsoft PowerShell. También enumera los cmdlets de PowerShell para grupos. Para obtener información sobre la administración de sitios de SharePoint, vea [Manage SharePoint Online sites using PowerShell](/sharepoint/manage-team-and-communication-sites-in-powershell).

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Vínculo a las directrices de uso de grupos de Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Cuando los [usuarios crean o editan un grupo en Outlook,](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)puede mostrarles un vínculo a las directrices de uso de su organización. Por ejemplo, si necesita agregar un prefijo o sufijo específicos a un nombre de grupo.

Use Azure Active Directory (Azure AD) PowerShell para apuntar a los usuarios a las directrices de uso de su organización para grupos de Microsoft 365. Consulte [Cmdlets de Azure Active Directory](/azure/active-directory/enterprise-users/groups-settings-cmdlets) para configurar la configuración de grupo y siga los pasos descritos en **Crear** configuración en el nivel de directorio para definir el hipervínculo de la directriz de uso. Una vez que ejecute el cmdlet AAD, los usuarios verán el vínculo a sus directrices cuando creen o editan un grupo en Outlook.

![Crear un nuevo grupo con el vínculo directrices de uso](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Haga clic en Directrices de uso de grupos para ver las directrices de grupos de Office 365 de las organizaciones](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Permitir que los usuarios envíen como grupo de Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Si desea habilitar los grupos de Microsoft 365 para "Enviar como", use los cmdlets [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) y [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) para configurar esto. Una vez que habilite esta configuración, los usuarios del grupo de Microsoft 365 pueden usar Outlook o Outlook en la web para enviar y responder al correo electrónico como grupo de Microsoft 365. Los usuarios pueden ir al grupo, crear un nuevo correo electrónico y cambiar el campo "Enviar como" a la dirección de correo electrónico del grupo.

([También puede hacerlo en el Centro de administración de Exchange](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)

Use el siguiente script, reemplazando con el alias del grupo que desea actualizar y con el alias del usuario al que desea conceder *\<GroupAlias\>* *\<UserAlias\>* permisos. [Conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para ejecutar este script.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

Una vez ejecutado el cmdlet, los usuarios pueden ir a Outlook o Outlook en la web para enviar como grupo, agregando la dirección de correo electrónico del grupo al **campo** De.

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Crear clasificaciones para grupos de Microsoft 365 en su organización

Puede crear etiquetas de confidencialidad que los usuarios de su organización pueden establecer al crear un grupo de Microsoft 365. Si desea clasificar grupos, se recomienda usar etiquetas de confidencialidad en lugar de la característica de clasificación de grupos anterior. Para obtener información sobre el uso de etiquetas de confidencialidad, vea Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de [Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md).

> [!IMPORTANT]
> Si actualmente usa etiquetas de clasificación, ya no estarán disponibles para los usuarios que creen grupos una vez habilitadas las etiquetas de confidencialidad.

Todavía puede usar la característica de clasificación de grupos anterior. Puede crear clasificaciones que los usuarios de su organización pueden establecer al crear un grupo de Microsoft 365. Por ejemplo, puede permitir que los usuarios establezcan "Standard", "Secret" y "Top Secret" en los grupos que creen. Las clasificaciones de grupos no se establecen de forma predeterminada y es necesario crearla para que los usuarios puedan establecerla. Use Azure Active Directory PowerShell para apuntar a los usuarios a las directrices de uso de su organización para grupos de Microsoft 365.

Consulte [Los cmdlets](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) de Azure Active Directory para configurar la configuración de grupos y siga los pasos descritos en Create **settings at the directory level** para definir la clasificación de Grupos de Microsoft 365.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Para asociar una descripción a cada clasificación, puede usar el atributo de configuración  *ClassificationDescriptions* para definir.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

donde Classification coincide con las cadenas de ClassificationList.

Ejemplo:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

Después de ejecutar el cmdlet de Azure Active Directory anterior para establecer la clasificación, ejecute el cmdlet [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) si desea establecer la clasificación de un grupo específico.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

O cree un nuevo grupo con una clasificación.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Consulte [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) y [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obtener más información sobre el uso de Exchange Online PowerShell.

Una vez habilitada esta configuración, el propietario del grupo podrá elegir una clasificación en el menú desplegable  de Outlook en la Web y Outlook y guardarla en la página Editar grupo.

![Elegir clasificación de grupo de Microsoft 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Ocultar grupos de Microsoft 365 de la lista global de direcciones.
<a name="BKMK_CreateClassification"> </a>

Puede especificar si un grupo de Microsoft 365 aparece en la lista global de direcciones (GAL) y otras listas de la organización. Por ejemplo, si tiene un grupo de departamento legal que no desea que aparezca en la lista de direcciones, puede impedir que ese grupo aparezca en la GAL. Ejecute el cmdlet Set-Unified Group para ocultar el grupo de la lista de direcciones como esta:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Permitir que solo los usuarios internos envíen mensajes a grupos de Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Si no desea que los usuarios de otras organizaciones envíen correos electrónicos a un grupo de Microsoft 365, puede cambiar la configuración de ese grupo. Solo permitirá que los usuarios internos envíen un correo electrónico a su grupo. Si un usuario externo intenta enviar un mensaje a ese grupo, se rechazará.

Ejecute el cmdlet Set-UnifiedGroup para actualizar esta configuración, como esta:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Agregar sugerencias de correo electrónico a grupos de Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Siempre que un remitente intente enviar un correo electrónico a un grupo de Microsoft 365, se les puede mostrar una sugerencia de correo electrónico.

Ejecute el cmdlet Set-Unified group para agregar una sugerencia de correo al grupo:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Junto con mailtip, también puede establecer MailTipTranslations, que especifica idiomas adicionales para la sugerencia de correo electrónico. Supongamos que desea tener la traducción al español y, a continuación, ejecute el siguiente comando:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Cambiar el nombre para mostrar del grupo de Microsoft 365

El nombre para mostrar especifica el nombre del grupo de Microsoft 365. Puede ver este nombre en el Centro de administración de Exchange o en el Centro de administración de Microsoft 365. Puede editar el nombre para mostrar del grupo o asignar un nombre para mostrar a un grupo de Microsoft 365 existente ejecutando el Set-UnifiedGroup usuario:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Cambiar la configuración predeterminada de Grupos de Microsoft 365 para Outlook a Pública o Privada
<a name="BKMK_CreateClassification"> </a>

Los grupos de Microsoft 365 en Outlook se crean como privados de forma predeterminada. Si su organización desea que grupos de Microsoft 365 se cree como público de forma predeterminada (o de vuelta a Private), use esta sintaxis de cmdlet de PowerShell:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

Para establecer en Privado:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

Para comprobar la configuración:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Para obtener más información, [vea Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) y [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).

## <a name="microsoft-365-groups-cmdlets"></a>Cmdlets de grupos de Microsoft 365

Los siguientes cmdlets se pueden usar con grupos de Microsoft 365.

|**Nombre de cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-UnifiedGroup](/powershell/module/exchange/get-unifiedgroup) <br/> |Use este cmdlet para buscar grupos de Microsoft 365 existentes y ver las propiedades del objeto group  <br/> |
|[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) <br/> |Actualizar las propiedades de un grupo específico de Microsoft 365  <br/> |
|[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) <br/> |Crear un nuevo grupo de Microsoft 365. Este cmdlet proporciona un conjunto mínimo de parámetros. Para establecer valores para propiedades extendidas, use Set-UnifiedGroup después de crear el nuevo grupo  <br/> |
|[Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) <br/> |Eliminar un grupo de Microsoft 365 existente  <br/> |
|[Get-UnifiedGroupLinks](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |Recuperar la información de pertenencia y propietario de un grupo de Microsoft 365  <br/> |
|[Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |Agregar miembros, propietarios y suscriptores a un grupo de Microsoft 365 existente <br/> |
|[Remove-UnifiedGroupLinks](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |Quitar propietarios y miembros de un grupo de Microsoft 365 existente  <br/> |
|[Get-UserPhoto](/powershell/module/exchange/get-userphoto) <br/> |Se usa para ver información sobre la foto de usuario asociada a una cuenta. Las fotos de usuario se almacenan en Active Directory  <br/> |
|[Set-UserPhoto](/powershell/module/exchange/set-userphoto) <br/> |Se usa para asociar una foto de usuario con una cuenta. Las fotos de usuario se almacenan en Active Directory  <br/> |
|[Remove-UserPhoto](/powershell/module/exchange/remove-userphoto) <br/> |Quitar la foto de un grupo de Microsoft 365  <br/> |

## <a name="related-topics"></a>Temas relacionados

[Actualizar listas de distribución a grupos de Microsoft 365](/office365/admin/manage/upgrade-distribution-lists)

[Administrar quién puede crear grupos de Microsoft 365](/office365/admin/create-groups/manage-creation-of-groups)

[Administrar el acceso de invitado a grupos de Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Cambiar la pertenencia a grupos estáticos a dinámica en](/azure/active-directory/users-groups-roles/groups-change-type)