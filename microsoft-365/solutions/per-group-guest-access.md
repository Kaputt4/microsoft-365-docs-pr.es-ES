---
title: Impedir que los invitados se agregó a un grupo específico
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Obtenga información sobre cómo evitar que los invitados se agregó a un grupo específico
ms.openlocfilehash: 1db2055f3e546c05905dbf4c854333387112f06e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538932"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Impedir que los invitados se agregó a un grupo Microsoft 365 grupo o Microsoft Teams grupo

Si desea permitir el acceso de invitado a la mayoría de grupos y equipos, pero tiene algunos en los que desea impedir el acceso de invitado, puede bloquear el acceso de invitado para grupos y equipos individuales. (Bloquear el acceso de invitado a un equipo se realiza bloqueando el acceso de invitado al grupo asociado). Esto evita que se agregó invitados nuevos, pero no quita los invitados que ya están en el grupo o el equipo.

Si usa etiquetas de confidencialidad en su organización, se recomienda usarlas para controlar el acceso de invitados por grupo. Para obtener información sobre cómo hacerlo, use etiquetas de confidencialidad para proteger el contenido de [Microsoft Teams, Microsoft 365 grupos](../compliance/sensitivity-labels-teams-groups-sites.md)y SharePoint web . Este es el método recomendado.

## <a name="change-group-settings-using-microsoft-powershell"></a>Cambiar la configuración de grupo con Microsoft PowerShell

También puede evitar la adición de nuevos invitados a grupos individuales mediante PowerShell. (Recuerde que el sitio asociado del equipo SharePoint cuenta con controles de uso [compartido de invitados independientes).)](/sharepoint/change-external-sharing-site)

Debe usar la versión preliminar de [Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2) para Graph (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado de nivel de grupo:

- Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) y siga las instrucciones para instalar la versión preliminar pública.

- Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.

- Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.

> [!NOTE]
> Debe tener derechos de administrador global para ejecutar estos comandos. 

Ejecute el siguiente script, cambiando por el nombre del grupo en el */<GroupName/>* que desea bloquear el acceso de invitado.

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

La comprobación tiene este aspecto:
    
![Captura de pantalla de la ventana de PowerShell que muestra que el acceso de grupo invitado se ha establecido en false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Permitir o bloquear el acceso de invitado en función de su dominio

Puede permitir o bloquear invitados que usan un dominio específico. Por ejemplo, si su empresa (Contoso) tiene una asociación con otra empresa (Fabrikam), puede agregar Fabrikam a la lista Permitir para que los usuarios puedan agregar a esos invitados a sus grupos.

Para obtener más información, vea [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).

## <a name="add-guests-to-the-global-address-list"></a>Agregar invitados a la lista global de direcciones

De forma predeterminada, los invitados no están visibles en la Exchange global de direcciones. Siga los pasos que se indican a continuación para que un invitado sea visible en la lista global de direcciones.

Para buscar el ObjectID del invitado, ejecute:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

A continuación, ejecute lo siguiente con los valores adecuados para ObjectID, GivenName, Surname, DisplayName y TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)

[Administrar la pertenencia a grupos en el centro Microsoft 365 administración](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[Azure Active Directory de acceso](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)