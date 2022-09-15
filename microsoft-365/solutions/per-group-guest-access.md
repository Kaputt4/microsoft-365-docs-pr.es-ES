---
title: Impedir que los invitados se agreguen a un grupo específico
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Aprenda a evitar que los invitados se agreguen a un grupo específico.
ms.openlocfilehash: c49dca69d1a5ba08032dce5fb8a12d923c835118
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67727290"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Impedir que los invitados se agreguen a un grupo específico de Microsoft 365 o a un equipo de Microsoft Teams

Si desea permitir el acceso de invitado a la mayoría de los grupos y equipos, pero tiene algún lugar donde quiera impedir el acceso de invitado, puede bloquear el acceso de invitado para grupos y equipos individuales. (Bloquear el acceso de invitado a un equipo se realiza bloqueando el acceso de invitado al grupo asociado). Esto impide que se agreguen nuevos invitados, pero no quita a los invitados que ya están en el grupo o en el equipo.

Si usa etiquetas de confidencialidad en su organización, se recomienda usarlas para controlar el acceso de invitado por grupo. Para obtener información sobre cómo hacerlo, [use etiquetas de confidencialidad para proteger el contenido de Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md). Este es el método recomendado.

## <a name="change-group-settings-using-microsoft-powershell"></a>Cambio de la configuración del grupo mediante Microsoft PowerShell

También puede evitar la adición de nuevos invitados a grupos individuales mediante PowerShell. (Recuerde que el sitio de SharePoint asociado del equipo tiene [controles de uso compartido de invitados independientes](/sharepoint/change-external-sharing-site)).

Debe usar la versión preliminar de [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado de nivel de grupo:

- Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) y siga las instrucciones para instalar la versión preliminar pública.

- Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.

- Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.

> [!NOTE]
> Debe tener derechos de administrador global para ejecutar estos comandos. 

Ejecute el siguiente script y cambie *\<GroupName\>* al nombre del grupo donde desea bloquear el acceso de invitado.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Para comprobar la configuración, ejecute este comando:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

La comprobación tiene el siguiente aspecto:
    
![Captura de pantalla de la ventana de PowerShell que muestra que el acceso al grupo invitado se ha establecido en false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)

Si desea volver a alternar la configuración para permitir el acceso de invitado a un grupo determinado, ejecute el siguiente script y cambie ```<GroupName>``` al nombre del grupo en el que desea permitir el acceso de invitado.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$True
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
$id = (get-AzureADObjectSetting -TargetType groups -TargetObjectId $groupID).id
Set-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy -id $id
```

## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Permitir o bloquear el acceso de invitado en función de su dominio

Puede permitir o bloquear invitados que usen un dominio específico. Por ejemplo, si su empresa (Contoso) tiene una asociación con otra empresa (Fabrikam), puede agregar Fabrikam a la lista de permitidos para que los usuarios puedan agregar esos invitados a sus grupos.

Para obtener más información, vea [Permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](/azure/active-directory/b2b/allow-deny-list).

## <a name="add-guests-to-the-global-address-list"></a>Agregar invitados a la lista global de direcciones

De forma predeterminada, los invitados no están visibles en la lista global de direcciones de Exchange. Siga los pasos que se indican a continuación para que un invitado sea visible en la lista global de direcciones.

Busque el ObjectID del invitado mediante la ejecución de:

```PowerShell
get-AzureADUser -all $true | ?{$_.CreationType -eq "Invitation"}
```

A continuación, ejecute lo siguiente con los valores adecuados para ObjectID, GivenName, Surname, DisplayName y TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>Temas relacionados

[Recomendaciones de planeamiento de gobernanza de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[Creación del plan de gobernanza de colaboración](collaboration-governance-first.md)

[Administración de la pertenencia a grupos en el Centro de administración de Microsoft 365](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[Revisiones de acceso de Azure Active Directory](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)
