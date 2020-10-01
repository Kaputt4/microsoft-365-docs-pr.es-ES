---
title: Bloquear a usuarios invitados de un grupo específico
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Bloquear a usuarios invitados de un grupo específico
ms.openlocfilehash: 2e9c9cae13932a33b8c486148f93901904e80006
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328022"
---
# <a name="block-guest-users-from-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Bloquear a los usuarios invitados de un grupo de Microsoft 365 específico o de un equipo de Microsoft Teams

Si desea permitir el acceso de invitado a la mayoría de grupos y equipos, pero con algunos en los que desea evitar el acceso de invitado, puede bloquear el acceso de invitado a grupos y equipos individuales. (Si se bloquea el acceso de invitado a un equipo, se bloquea el acceso de invitado al grupo asociado).

Si usa etiquetas de confidencialidad en su organización, se recomienda usarlas para controlar el acceso de invitado por grupo. Para obtener información sobre cómo hacerlo, [use las etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de 365 de Microsoft y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). Este es el método recomendado.

También puede bloquear el acceso de invitado a grupos individuales mediante PowerShell de Microsoft.

Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado en el nivel de Grupo:

- Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) y siga las instrucciones para instalar la versión preliminar pública.

- Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.

- Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.

> [!NOTE]
> Debe tener derechos de administrador global para ejecutar estos comandos. 

Ejecute el siguiente script y cambie */<GroupName/>* al nombre del grupo en el que desea bloquear el acceso de invitado.

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

La comprobación tiene un aspecto similar al siguiente:
    
![Captura de pantalla de la ventana de PowerShell que muestra que el acceso al grupo de invitados se estableció en false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Permitir o bloquear el acceso de invitado en función de su dominio

Puede permitir o bloquear a los usuarios invitados que usan un dominio específico. Por ejemplo, si su empresa (contoso) tiene una asociación con otro negocio (Fabrikam), puede Agregar a Fabrikam a la lista de permitidos para que los usuarios puedan agregar a esos invitados a sus grupos.

Para obtener más información, vea [permitir o bloquear invitaciones a usuarios B2B desde organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).

## <a name="add-guests-to-the-global-address-list"></a>Agregar invitados a la lista global de direcciones

De forma predeterminada, los invitados no están visibles en la lista global de direcciones de Exchange. Siga los pasos que se indican a continuación para hacer que un invitado esté visible en la lista global de direcciones.

Para buscar el ObjectID del usuario Guest, ejecute:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

A continuación, ejecute lo siguiente con los valores apropiados de ObjectID, GivenName, apellido, DisplayName y TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>Artículos relacionados

[Administrar la pertenencia a grupos en el centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Revisiones de acceso de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)