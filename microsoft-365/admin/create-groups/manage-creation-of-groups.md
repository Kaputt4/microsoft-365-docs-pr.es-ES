---
title: Administrar quién puede crear grupos de Office 365
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Obtenga información sobre cómo controlar qué usuarios pueden crear grupos de Office 365.
ms.openlocfilehash: d31690cb6438c6563b01e0597f7f2b1ff96e3b9a
ms.sourcegitcommit: 0da80ba7b504841c502ab06fea659a985c06fe8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "43547591"
---
# <a name="manage-who-can-create-office-365-groups"></a>Administrar quién puede crear grupos de Office 365

  
Puesto que es extremadamente fácil para los usuarios crear grupos de Office 365, no va a recibir una infinidad de solicitudes para crearlos en nombre de otros usuarios. Sin embargo, dependiendo de su empresa, es posible que quiera controlar quién tiene la capacidad de crear grupos.
  
En este artículo se explica cómo deshabilitar la capacidad de crear grupos en todos los servicios de Office 365 que usan grupos, entre los que se incluyen:
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream
    
- StaffHub
    
- Planner
    
- PowerBI

- Plan de desarrollo
    
Puede restringir la creación de grupos de Office 365 a los miembros de un grupo de seguridad en particular. Para configurar esto, use Windows PowerShell. Este artículo le guiará por los pasos necesarios.
  
Los pasos de este artículo no impiden que los miembros de determinados roles creen grupos. Office 365 los administradores globales pueden crear grupos a través de cualquier medio, como el centro de administración de Microsoft 365, Planner, Teams, Exchange y SharePoint Online. Otros roles pueden crear grupos a través de medios limitados, que se enumeran a continuación.
        
  - Administrador de Exchange: Centro de administración de Exchange, Azure AD
    
  - Soporte técnico de nivel 1 de asociado: Centro de administración de Microsoft 365, centro de administración de Exchange, Azure AD
    
  - Soporte técnico del nivel 2 del asociado: Centro de administración de Microsoft 365, centro de administración de Exchange, Azure AD
    
  - Escritores de directorios: Azure AD

  - Administrador de SharePoint: Centro de administración de SharePoint, Azure AD
  
  - Team Service Administrator: Centro de administración de Teams, Azure AD
  
  - Administrador de administración de usuarios: Centro de administración de Microsoft 365, Yammer, Azure AD
     
Si es miembro de uno de estos roles, puede crear Grupos de Office 365 para usuarios restringidos y, después, asignar al usuario la propiedad del grupo. Los usuarios que tienen este rol pueden crear grupos conectados en Yammer, independientemente de la configuración de PowerShell que pueda impedir la creación.

## <a name="licensing-requirements"></a>Requisitos de licencia

Para administrar quién crea grupos, las siguientes personas necesitan licencias de Azure AD Premium o de Azure AD Basic EDU asignadas:

- El administrador que configura la configuración de creación de grupos
- Los miembros del grupo de seguridad que tienen permiso para crear grupos

> [!NOTE]
> Consulte [asignar o quitar licencias en el portal de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) para obtener más información sobre cómo asignar licencias de Azure.

Los siguientes usuarios no necesitan que se les asignen licencias de Azure AD Premium o Azure AD Basic EDU:

- Personas que son miembros de los grupos de Office 365 y que no tienen la capacidad de crear otros grupos.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a>Paso 1: Crear un grupo de seguridad para los usuarios que necesiten crear Grupos de Office 365

Solo se puede usar un grupo de seguridad de la organización para controlar quién puede crear grupos. Sin embargo, puede anidar otros grupos de seguridad como miembros de este grupo. Por ejemplo, el grupo denominado Permitir la creación de grupos es el grupo de seguridad designado, y los grupos denominados Usuarios de Microsoft Planner y Usuarios de Exchange Online son miembros de ese grupo.

Los administradores de los roles enumerados anteriormente no tienen que ser miembros de este grupo: conservan la capacidad de crear grupos.

> [!IMPORTANT]
> Asegúrese de usar un **grupo de seguridad** para restringir quién puede crear grupos. Si intenta usar un grupo de Office 365, los miembros no podrán crear un grupo desde SharePoint porque busca un grupo de seguridad. 
    
1. En el centro de administración, vaya a **la** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> página grupos de grupos.

2. Haga clic en **Agregar un grupo**.

3. Elija **seguridad** como tipo de grupo. Recuerde que el nombre del grupo. Lo necesitará más adelante.
  
4. Termine de configurar el grupo de seguridad, agregando personas u otros grupos de seguridad que quiera que puedan crear grupos en su organización.
    
Para obtener instrucciones detalladas, vea [crear, editar o eliminar un grupo de seguridad en el centro de administración de Microsoft 365](../email/create-edit-or-delete-a-security-group.md).
 
## <a name="step-2-run-powershell-commands"></a>Paso 2: Ejecutar los comandos de PowerShell

Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado en el nivel de Grupo:

- Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) y siga las instrucciones para instalar la versión preliminar pública.

- Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.

- Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.



Copie el script siguiente en un editor de texto, como el Bloc de notas o [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Reemplace * \<SecurityGroupName\> * por el nombre del grupo de seguridad que ha creado. Por ejemplo:

`$GroupName = "Group Creators"`

Guarde el archivo como GroupCreators. ps1. 

En la ventana de PowerShell, navegue hasta la ubicación donde guardó el archivo (escriba "CD <FileLocation>").

Para ejecutar el script, escriba:

`.\GroupCreators.ps1`

e [inicie sesión con su cuenta de administrador](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) cuando se le solicite.

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

La última línea del script mostrará la configuración actualizada:

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

Si en el futuro desea cambiar el grupo de seguridad que se va a usar, puede volver a ejecutar el script con el nombre del nuevo grupo de seguridad.

Si desea desactivar la restricción de creación de grupos y volver a permitir que todos los usuarios creen grupos, establezca $GroupName en "" y $AllowGroupCreation en "true" y vuelva a ejecutar el script.
    
## <a name="step-4-verify-that-it-works"></a>Paso 4: comprobar que funciona

1. Inicie sesión en Office 365 con la cuenta de usuario de alguien que NO debe tener la capacidad de crear grupos. Es decir, no son miembros del grupo de seguridad que ha creado o administrador.
    
2. Seleccione el mosaico de **Planner** . 
    
3. En Planner, seleccione **nuevo plan** en el panel de navegación izquierdo para crear un plan. 
  
4. Debe obtener un mensaje que indica que la creación de grupos y el plan está deshabilitada.

Vuelva a probar el mismo procedimiento con un miembro del grupo de seguridad.

> [!NOTE]
> Si los miembros del grupo de seguridad no pueden crear grupos, compruebe que no se bloquean a través de la [Directiva de buzón de OWA](https://go.microsoft.com/fwlink/?linkid=852135).
    
## <a name="related-articles"></a>Artículos relacionados

[Introducción a PowerShell de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Configurar la administración de grupos de autoservicio en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Cmdlets de Azure Active Directory para configurar configuraciones de grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
