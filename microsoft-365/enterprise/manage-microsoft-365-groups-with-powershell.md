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
ms.openlocfilehash: 1cad2aa39a6b106cbb4dbfbafa995899b2442ed1
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830620"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Administrar grupos de Microsoft 365 con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

En este artículo se proporcionan los pasos para realizar tareas de administración comunes para grupos en PowerShell de Microsoft. También enumera los cmdlets de PowerShell para grupos. Para obtener información acerca de la administración de sitios de SharePoint, vea [Administrar sitios de SharePoint Online con PowerShell.](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell)

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Vínculo a las directrices de uso de Grupos de Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Cuando los [usuarios crean o editan](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)un grupo en Outlook, puede mostrarles un vínculo a las directrices de uso de su organización. Por ejemplo, si necesita agregar un prefijo o sufijo específico a un nombre de grupo.

Use Azure Active Directory (Azure AD) PowerShell para apuntar a los usuarios a las directrices de uso de su organización para los grupos de Microsoft 365. Consulte los [cmdlets](https://go.microsoft.com/fwlink/?LinkID=827484) de Azure Active Directory para configurar  las opciones de grupo y siga los pasos descritos en La opción Crear en el nivel de directorio para definir el hipervínculo de las instrucciones de uso. Una vez que ejecute el cmdlet de AAD, los usuarios verán el vínculo a sus directrices cuando creen o editan un grupo en Outlook.

![Crear un nuevo grupo con un vínculo de directrices de uso](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Haga clic en Directrices de uso de grupos para ver las directrices de grupos de Office 365 de su organización](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Permitir que los usuarios envíen como el grupo de Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Si desea habilitar los grupos de Microsoft 365 para "Enviar como", use los cmdlets [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) y [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) para configurarlo. Una vez que habilite esta configuración, los usuarios del grupo de Microsoft 365 pueden usar Outlook o Outlook en la Web para enviar y responder correos electrónicos como el grupo de Microsoft 365. Los usuarios pueden ir al grupo, crear un nuevo correo electrónico y cambiar el campo "Enviar como" a la dirección de correo electrónico del grupo.

([También puede hacerlo en el Centro de administración de Exchange).](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)

Use el siguiente script, reemplazando con el alias del grupo que desea actualizar y con el alias del usuario al que desea conceder *\<GroupAlias\>* *\<UserAlias\>* permisos. [Conéctese a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) para ejecutar este script.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

Una vez ejecutado el cmdlet, los usuarios pueden ir a Outlook o Outlook en la Web para enviar como grupo, agregando la dirección de correo electrónico del grupo al **campo** De.

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Crear clasificaciones para grupos de Microsoft 365 en su organización

Puede crear etiquetas de confidencialidad que los usuarios de su organización pueden establecer al crear un grupo de Microsoft 365. Si desea clasificar grupos, se recomienda usar etiquetas de confidencialidad en lugar de la característica de clasificación de grupos anterior. Para obtener información sobre el uso de etiquetas de confidencialidad, vea Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de [Microsoft 365 y sitios de SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

> [!IMPORTANT]
> Si actualmente usa etiquetas de clasificación, estas ya no estarán disponibles para los usuarios que creen grupos una vez habilitadas las etiquetas de confidencialidad.

Aún puede usar la característica de clasificación de grupos anterior. Puede crear clasificaciones que los usuarios de su organización pueden establecer al crear un grupo de Microsoft 365. Por ejemplo, puede permitir que los usuarios establezcan "Standard", "Secret" y "Top Secret" en los grupos que crean. Las clasificaciones de grupo no se establecen de forma predeterminada y es necesario crearla para que los usuarios puedan establecerla. Use Azure Active Directory PowerShell para apuntar a los usuarios a las directrices de uso de su organización para Grupos de Microsoft 365.

Consulte los [cmdlets](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) de Azure Active Directory para configurar  las opciones de grupo y siga los pasos descritos en La creación de opciones en el nivel de directorio para definir la clasificación de Grupos de Microsoft 365.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Para asociar una descripción a cada clasificación, puedes usar el atributo de configuración  *ClassificationDescriptions* para definir.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

donde Classification coincide con las cadenas de ClassificationList.

Ejemplo:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

Después de ejecutar el cmdlet anterior de Azure Active Directory para establecer la clasificación, ejecute el cmdlet [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) si desea establecer la clasificación para un grupo específico.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

O cree un nuevo grupo con una clasificación.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Consulte Usar [PowerShell con Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) y conectarse a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) para obtener más información sobre el uso de Exchange Online PowerShell.

Una vez habilitada esta configuración, el propietario del grupo podrá elegir una clasificación en el menú desplegable  de Outlook en la Web y Outlook, y guardarla en la página Editar grupo.

![Elegir clasificación de grupo de Microsoft 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Ocultar Grupos de Microsoft 365 de la lista global de direcciones.
<a name="BKMK_CreateClassification"> </a>

Puede especificar si un grupo de Microsoft 365 aparece en la lista global de direcciones (GAL) y otras listas de su organización. Por ejemplo, si tiene un grupo de departamento legal que no desea que aparezca en la lista de direcciones, puede impedir que ese grupo aparezca en la GAL. Ejecute el cmdlet Set-Unified Group para ocultar el grupo de la lista de direcciones de la siguiente forma:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Permitir que solo los usuarios internos envíen mensajes a Grupos de Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Si no desea que los usuarios de otras organizaciones envíen correos electrónicos a un grupo de Microsoft 365, puede cambiar la configuración de ese grupo. Solo permitirá que los usuarios internos envíen un correo electrónico a su grupo. Si un usuario externo intenta enviar un mensaje a ese grupo, se rechazará.

Ejecute el cmdlet Set-UnifiedGroup para actualizar esta configuración, como se muestra a continuación:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Agregar sugerencias de correo electrónico a grupos de Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Cuando un remitente intenta enviar un correo electrónico a un grupo de Microsoft 365, se le puede mostrar una sugerencia de correo electrónico.

Ejecute el cmdlet Set-Unified Group para agregar una sugerencia de correo electrónico al grupo:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Junto con la sugerencia de correo electrónico, también puede establecer MailTipTranslations, que especifica idiomas adicionales para la sugerencia de correo electrónico. Supongamos que desea tener la traducción al español y, a continuación, ejecute el siguiente comando:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Cambiar el nombre para mostrar del grupo de Microsoft 365

El nombre para mostrar especifica el nombre del grupo de Microsoft 365. Puede ver este nombre en el Centro de administración de Exchange o en el Centro de administración de Microsoft 365. Puede editar el nombre para mostrar del grupo o asignar un nombre para mostrar a un grupo de Microsoft 365 existente ejecutando el Set-UnifiedGroup comando:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Cambiar la configuración predeterminada de Grupos de Microsoft 365 para Outlook a pública o privada
<a name="BKMK_CreateClassification"> </a>

Los grupos de Microsoft 365 en Outlook se crean como privados de forma predeterminada. Si su organización desea que los Grupos de Microsoft 365 se cree como Público de forma predeterminada (o de vuelta a Privado), use esta sintaxis de cmdlet de PowerShell:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

Para establecer en Privado:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

Para comprobar la configuración:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Para obtener más información, [vea Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) y [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).

## <a name="microsoft-365-groups-cmdlets"></a>Cmdlets de grupos de Microsoft 365

Los cmdlets siguientes se pueden usar con grupos de Microsoft 365.

|**Nombre de cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |Use este cmdlet para buscar grupos de Microsoft 365 existentes y ver las propiedades del objeto de grupo  <br/> |
|[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |Actualizar las propiedades de un grupo específico de Microsoft 365  <br/> |
|[New-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |Cree un nuevo grupo de Microsoft 365. Este cmdlet proporciona un conjunto mínimo de parámetros. Para establecer valores para propiedades extendidas, use Set-UnifiedGroup después de crear el nuevo grupo  <br/> |
|[Remove-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |Eliminar un grupo de Microsoft 365 existente  <br/> |
|[Get-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |Recuperar información de pertenencia y propietario de un grupo de Microsoft 365  <br/> |
|[Add-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |Agregar miembros, propietarios y suscriptores a un grupo de Microsoft 365 existente <br/> |
|[Remove-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |Quitar propietarios y miembros de un grupo de Microsoft 365 existente  <br/> |
|[Get-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |Se usa para ver información sobre la foto de usuario asociada con una cuenta. Las fotos de usuario se almacenan en Active Directory  <br/> |
|[Set-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |Se usa para asociar una foto de usuario con una cuenta. Las fotos de usuario se almacenan en Active Directory  <br/> |
|[Remove-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |Quitar la foto de un grupo de Microsoft 365  <br/> |

## <a name="related-topics"></a>Temas relacionados

[Actualizar listas de distribución a Grupos de Microsoft 365](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[Administrar quién puede crear grupos de Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[Administrar el acceso de invitado a grupos de Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Cambiar la pertenencia a grupos estáticos a dinámica en](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
