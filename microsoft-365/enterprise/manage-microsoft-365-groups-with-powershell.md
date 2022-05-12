---
title: Administración de Grupos de Microsoft 365 con PowerShell
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
- admindeeplinkMAC
- admindeeplinkEXCHANGE
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: En este artículo, aprenderá a realizar tareas de administración comunes para grupos de Microsoft 365 en PowerShell.
ms.openlocfilehash: 407e242728bf37ebf8c11b8094bfa4931229e4ef
ms.sourcegitcommit: 3226bdf213b290ec5262670873c3a75f17b66ddd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2022
ms.locfileid: "65372211"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Administración de Grupos de Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

En este artículo se proporcionan los pasos para realizar tareas de administración comunes para grupos en Microsoft PowerShell. También enumera los cmdlets de PowerShell para grupos. Para obtener información sobre cómo administrar sitios SharePoint, consulte [Administración de sitios en línea de SharePoint mediante PowerShell](/sharepoint/manage-team-and-communication-sites-in-powershell).

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Vínculo a las directrices de uso de Grupos de Microsoft 365

Cuando los usuarios [crean o editan un grupo en Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), puede mostrarles un vínculo a las directrices de uso de su organización. Por ejemplo, si necesita agregar un prefijo o sufijo específico a un nombre de grupo.

Use PowerShell Azure Active Directory (Azure AD) para señalar a los usuarios a las directrices de uso de su organización para grupos de Microsoft 365. Consulte [Azure Active Directory cmdlets para configurar la configuración de grupos](/azure/active-directory/enterprise-users/groups-settings-cmdlets) y siga los pasos descritos en **Crear configuración en el nivel de directorio** para definir el hipervínculo de la guía de uso. Una vez que ejecute el cmdlet de AAD, los usuarios verán el vínculo a las directrices cuando creen o editen un grupo en Outlook.

![Cree un nuevo grupo con el vínculo de directrices de uso.](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Haga clic en Directrices de uso de grupos para ver las directrices de grupos Office 365 las organizaciones.](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Permitir que los usuarios envíen como grupo de Microsoft 365

Si desea habilitar los grupos de Microsoft 365 para "Enviar como", use los cmdlets [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) y [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) para configurarlo. Una vez habilitada esta configuración, los usuarios de Microsoft 365 grupo pueden usar Outlook o Outlook en la Web para enviar y responder al correo electrónico como grupo Microsoft 365. Los usuarios pueden ir al grupo, crear un nuevo correo electrónico y cambiar el campo "Enviar como" a la dirección de correo electrónico del grupo.

([También puede hacerlo en el Centro de administración de Exchange](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)).

Use el siguiente script, reemplazando *\<GroupAlias\>* por el alias del grupo que desea actualizar y *\<UserAlias\>* por el alias del usuario al que desea conceder permisos. [Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para ejecutar este script.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

Una vez que se ejecuta el cmdlet, los usuarios pueden ir a Outlook o Outlook en la Web para enviar como grupo, agregando la dirección de correo electrónico del grupo al campo **Desde**.

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Creación de clasificaciones para Grupos de Microsoft 365 en la organización

Puede crear etiquetas de confidencialidad que los usuarios de su organización pueden establecer al crear un grupo de Microsoft 365. Si desea clasificar grupos, se recomienda usar etiquetas de confidencialidad en lugar de la característica de clasificación de grupos anterior. Para obtener información sobre el uso de etiquetas de confidencialidad, consulte [Uso de etiquetas de confidencialidad para proteger el contenido de Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md).

> [!IMPORTANT]
> Si actualmente usa etiquetas de clasificación, ya no estarán disponibles para los usuarios que creen grupos una vez habilitadas las etiquetas de confidencialidad.

Todavía puede usar la característica de clasificación de grupos anterior. Puede crear clasificaciones que los usuarios de su organización pueden establecer al crear un grupo de Microsoft 365. Por ejemplo, puede permitir que los usuarios establezcan "Estándar", "Secreto" y "Secreto superior" en los grupos que crean. Las clasificaciones de grupo no se establecen de forma predeterminada y debe crearla para que los usuarios la establezcan. Use Azure Active Directory PowerShell para señalar a los usuarios a las directrices de uso de la organización para Grupos de Microsoft 365.

Consulte [Azure Active Directory cmdlets para configurar la configuración de grupo](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) y siga los pasos descritos en **Crear configuración en el nivel de directorio** para definir la clasificación de Grupos de Microsoft 365.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Para asociar una descripción a cada clasificación, puede usar el atributo de configuración  *ClassificationDescriptions* para definir.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

Donde Classification coincide con las cadenas de ClassificationList.

Ejemplo:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

Después de ejecutar el cmdlet de Azure Active Directory anterior para establecer la clasificación, ejecute el cmdlet [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) si desea establecer la clasificación para un grupo específico.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

O bien, cree un nuevo grupo con una clasificación.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Consulte [Uso de PowerShell con Exchange Online](/powershell/exchange/exchange-online-powershell) y [Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obtener más información sobre el uso de Exchange Online PowerShell.

Una vez habilitada esta configuración, el propietario del grupo podrá elegir una clasificación en el menú desplegable de Outlook en la Web y Outlook, y guardarla en la página **Editar** grupo.

![Elija Microsoft 365 clasificación de grupo.](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Ocultar Grupos de Microsoft 365 de la lista global de direcciones.

Puede especificar si aparece un grupo de Microsoft 365 en la lista global de direcciones (GAL) y otras listas de su organización. Por ejemplo, si tiene un grupo de departamento legal que no quiere mostrar en la lista de direcciones, puede impedir que ese grupo aparezca en la GAL. Ejecute el cmdlet Set-Unified Group para ocultar el grupo de la lista de direcciones de la siguiente manera:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Permitir que solo los usuarios internos envíen mensajes a Grupos de Microsoft 365

Si no desea que los usuarios de otras organizaciones envíen correos electrónicos a un grupo de Microsoft 365, puede cambiar la configuración de ese grupo. Solo permitirá que los usuarios internos envíen un correo electrónico al grupo. Si un usuario externo intenta enviar un mensaje a ese grupo, se rechazará.

Ejecute el cmdlet Set-UnifiedGroup para actualizar esta configuración, de la siguiente manera:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Agregar sugerencias de correo electrónico a Grupos de Microsoft 365

Cada vez que un remitente intenta enviar un correo electrónico a un grupo de Microsoft 365, se le puede mostrar una sugerencia de correo electrónico.

Ejecute el cmdlet Set-Unified Group para agregar una sugerencia de correo al grupo:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Junto con MailTip, también puede establecer MailTipTranslations, que especifican otros idiomas para la información sobre correo electrónico. Supongamos que desea tener la traducción al español y, a continuación, ejecute el siguiente comando:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Cambiar el nombre para mostrar del grupo de Microsoft 365

El nombre para mostrar especifica el nombre del grupo de Microsoft 365. Puede ver este nombre en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a> o <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. Puede editar el nombre para mostrar del grupo o asignar un nombre para mostrar a un grupo de Microsoft 365 existente mediante la ejecución del comando Set-UnifiedGroup:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Cambie la configuración predeterminada de Grupos de Microsoft 365 para Outlook a Público o Privado.

Grupos de Microsoft 365 en Outlook se crean como Privados de forma predeterminada. Si su organización quiere que Grupos de Microsoft 365 se cree como Público de forma predeterminada (o de vuelta a Privado), use esta sintaxis de cmdlet de PowerShell:

 ```powershell
 Set-OrganizationConfig -DefaultGroupAccessType Public
 ```

Para establecer en Privado:

 ```powershell
 Set-OrganizationConfig -DefaultGroupAccessType Private
 ```

Para comprobar la configuración:

 ```powershell
 Get-OrganizationConfig | ft DefaultGroupAccessType
 ```

Para más información, consulte [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) y [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).

## <a name="microsoft-365-groups-cmdlets"></a>cmdlets de Grupos de Microsoft 365

Los siguientes cmdlets se pueden usar con Grupos de Microsoft 365.

|**Nombre de cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-UnifiedGroup](/powershell/module/exchange/get-unifiedgroup) <br/> |Use este cmdlet para buscar Grupos de Microsoft 365 existentes y ver las propiedades del objeto de grupo.  <br/> |
|[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) <br/> |Actualizar las propiedades de un grupo de Microsoft 365 específico  <br/> |
|[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) <br/> |Cree un nuevo grupo de Microsoft 365. Este cmdlet proporciona un conjunto mínimo de parámetros. Para establecer valores para las propiedades extendidas, use Set-UnifiedGroup después de crear el nuevo grupo.  <br/> |
|[Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) <br/> |Eliminación de un grupo de Microsoft 365 existente  <br/> |
|[Get-UnifiedGroupLinks](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |Recuperar la información de pertenencia y propietario de un grupo de Microsoft 365  <br/> |
|[Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |Agregar miembros, propietarios y suscriptores a un grupo de Microsoft 365 existente <br/> |
|[Remove-UnifiedGroupLinks](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |Quitar propietarios y miembros de un grupo de Microsoft 365 existente  <br/> |
|[Get-UserPhoto](/powershell/module/exchange/get-userphoto) <br/> |Se usa para ver información sobre la foto de usuario asociada a una cuenta. Las fotos de usuario se almacenan en Active Directory  <br/> |
|[Set-UserPhoto](/powershell/module/exchange/set-userphoto) <br/> |Se usa para asociar una foto de usuario a una cuenta. Las fotos de usuario se almacenan en Active Directory  <br/> |
|[Remove-UserPhoto](/powershell/module/exchange/remove-userphoto) <br/> |Quitar la foto de un grupo de Microsoft 365  <br/> |

## <a name="related-topics"></a>Temas relacionados

[Actualizar listas de distribución a Grupos de Microsoft 365](/office365/admin/manage/upgrade-distribution-lists)

[Administrar quién puede crear grupos de Microsoft 365](/office365/admin/create-groups/manage-creation-of-groups)

[Administración del acceso de invitado a Grupos de Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Cambiar la pertenencia a grupos estáticos a dinámico en](/azure/active-directory/users-groups-roles/groups-change-type)
