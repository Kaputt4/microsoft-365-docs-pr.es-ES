---
title: Administrar el acceso de invitado en los grupos de Office 365
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.date: 12/18/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Obtenga información sobre cómo agregar invitados a un grupo de Office 365, ver usuarios invitados y usar PowerShell para controlar el acceso de invitado.
ms.openlocfilehash: 3314746e4d12c318eaae8fbfa34c2ed0b4d31aed
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610618"
---
# <a name="manage-guest-access-in-office-365-groups"></a>Administrar el acceso de invitado en los grupos de Office 365

De forma predeterminada, el acceso de invitado para los grupos de Office 365 está activado para su organización. Los administradores pueden controlar si se permite el acceso de invitado a grupos para toda la organización o para grupos individuales.

Cuando está activada, los miembros del grupo pueden invitar a los usuarios invitados a un grupo de Office 365 a través de Outlook en la Web. Las invitaciones se envían al propietario del grupo para su aprobación.

> [!Note]
> Las redes de Yammer Enterprise que están en modo nativo o el geográfico de la [UE](https://go.microsoft.com/fwlink/?linkid=2107357) no admiten invitados de red.
> Office 365 los grupos de Yammer conectados no admiten actualmente el acceso de invitado, pero puede crear grupos externos no conectados en su red Yammer. Consulte [crear y administrar grupos externos en Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) para obtener instrucciones.

### <a name="edit-guest-information"></a>Editar información de invitado

Una vez aprobado, el usuario invitado se agrega al directorio y al grupo.

El acceso de invitado en grupos suele usarse como parte de un escenario más amplio que incluye SharePoint o Teams. Estos servicios tienen su propia configuración de uso compartido de invitado. Para obtener instrucciones completas sobre cómo configurar el uso compartido de invitado en grupos, SharePoint y Teams, vea:

- [Colaborar con invitados en un sitio](../../solutions/collaborate-in-site.md)
- [Colaborar con invitados en un equipo](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Administrar grupos acceso de invitado

Si desea habilitar o deshabilitar el acceso de invitado en grupos, puede hacerlo en el centro de administración de 365 de Microsoft.

1. En el centro de administración, vaya a la página de los <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Complementos &</a> de los servicios de **configuración** \> .

2. Seleccione **Office 365 grupos**.
  
3. En la página **Office 365 grupos** , elija si desea permitir que los usuarios ajenos a la organización obtengan acceso a los recursos del grupo o permitir que los propietarios del grupo agreguen personas fuera de la organización a los grupos.

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a>Agregar invitados a un grupo de Office 365 desde el centro de administración

Si el invitado ya existe en su directorio, puede agregarlo a los grupos desde el centro de administración de Microsoft 365.
  
1. En el centro de administración, vaya a **la** > **Groups** página grupos de grupos.
  
2. Seleccione el grupo al que desea agregar el invitado y seleccione **Ver todos y administrar miembros** en la pestaña **miembros** . 
  
4. Seleccione **Agregar miembros**y, a continuación, elija el nombre del invitado que quiera agregar.
    
5. Haga clic en **Guardar**.

Si desea agregar un invitado directamente al directorio, puede [Agregar usuarios de colaboración B2B de Azure Active Directory en Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Si desea editar la información de algún invitado, puede [Agregar o actualizar la información de Perfil de un usuario con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).
  
## <a name="block-guest-users-from-a-specific-group"></a>Bloquear a usuarios invitados de un grupo específico

Si desea permitir el acceso de invitado a la mayoría de los grupos, pero tenga algunos en los que desea evitar el acceso de invitado, puede bloquear el acceso de invitado para grupos individuales mediante PowerShell de Microsoft.

Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado en el nivel de Grupo:

- Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) y siga las instrucciones para instalar la versión preliminar pública.

- Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.

- Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.

> [!NOTE]
> Debe tener derechos de administrador global para ejecutar estos comandos. 

Ejecute el siguiente script y cambie * / * al nombre del grupo en el que desea bloquear el acceso de invitado.

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
    
![Captura de pantalla de la ventana de PowerShell que muestra que el acceso al grupo de invitados se estableció en false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
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

[Administrar la pertenencia a grupos en el centro de administración de Microsoft 365](add-or-remove-members-from-groups.md)
  
[Revisiones de acceso de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
