---
title: Administrar quién puede crear grupos de Microsoft 365
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Obtenga información sobre cómo controlar qué usuarios pueden crear grupos de Microsoft 365.
ms.openlocfilehash: 9c3edf335ce09f04e9b0b538e69fa607a9c34044
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929161"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Administrar quién puede crear grupos de Microsoft 365

De forma predeterminada, todos los usuarios pueden crear grupos de Microsoft 365. Este es el enfoque recomendado porque permite a los usuarios empezar a colaborar sin necesidad de asistencia de TI.

Si su empresa requiere restringir quién puede crear grupos, puede restringir la creación de grupos de Microsoft 365 a los miembros de un grupo o grupo de seguridad de Microsoft 365 en particular.

Si le preocupa que los usuarios creen equipos o grupos que no cumplan con los estándares empresariales, considere la posibilidad de requerir a los usuarios que completen un curso de formación y, a continuación, agregarlos al grupo de usuarios permitidos.

Cuando se limita quién puede crear un grupo, afecta a todos los servicios que dependen de grupos para el acceso, incluidos:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (clásico)
- Project for the web /Roadmap

Los pasos de este artículo no impedirán que los miembros de determinados roles creen grupos. Los administradores globales de Office 365 pueden crear grupos por cualquier medio, como el Centro de administración de Microsoft 365, Planner, Teams, Exchange y SharePoint Online. Otros roles pueden crear grupos a través de medios limitados, que se enumeran a continuación.

- Administrador de Exchange: Centro de administración de Exchange, Azure AD
- Soporte técnico de nivel 1 de partner: Centro de administración de Microsoft 365, Centro de administración de Exchange, Azure AD
- Soporte técnico de nivel 2 de partner: Centro de administración de Microsoft 365, Centro de administración de Exchange, Azure AD
- Escritores de directorios: Azure AD
- Administrador de SharePoint: Centro de administración de SharePoint, Azure AD
- Administrador de servicio de Teams: Centro de administración de Teams, Azure AD
- Administrador de usuarios: Centro de administración de Microsoft 365, Azure AD

Si es miembro de uno de estos roles, puede crear grupos de Microsoft 365 para usuarios restringidos y, a continuación, asignar al usuario como propietario del grupo.

## <a name="licensing-requirements"></a>Requisitos de licencia

Para administrar quién crea grupos, las siguientes personas necesitan licencias de Azure AD Premium o licencias EDU básicas de Azure AD asignadas:

- El administrador que configura estas opciones de creación de grupos
- Los miembros del grupo a los que se les permite crear grupos

> [!NOTE]
> Consulta [Asignar o quitar licencias en el portal](/azure/active-directory/fundamentals/license-users-groups) de Azure Active Directory para obtener más información sobre cómo asignar licencias de Azure.

Las siguientes personas no necesitan licencias EDU de Azure AD Premium o Azure AD Basic asignadas:

- Personas que son miembros de grupos de Microsoft 365 y que no tienen la capacidad de crear otros grupos.

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>Paso 1: Crear un grupo para usuarios que necesiten crear grupos de Microsoft 365

Solo se puede usar un grupo de la organización para controlar quién puede crear grupos. Sin embargo, puede anidar otros grupos como miembros de este grupo.

Los administradores de los roles enumerados anteriormente no necesitan ser miembros de este grupo: conservan su capacidad para crear grupos.

1. En el Centro de administración, vaya a la [página Grupos](https://admin.microsoft.com/adminportal/home#/groups).

2. Haga clic **en Agregar un grupo**.

3. Elija el tipo de grupo que desee. Recuerde que el nombre del grupo. Lo necesitará más adelante.

4. Termina de configurar el grupo, agregando personas u otros grupos que quieras que puedan crear grupos en tu organización.

Para obtener instrucciones detalladas, vea Crear, editar o eliminar un grupo de seguridad en el Centro de administración [de Microsoft 365](../admin/email/create-edit-or-delete-a-security-group.md).

## <a name="step-2-run-powershell-commands"></a>Paso 2: Ejecutar los comandos de PowerShell

Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) (nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado de nivel de grupo:

- Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) y siga las instrucciones para instalar la versión preliminar pública.

- Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.

- Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.

Copie el script siguiente en un editor de texto, como bloc de notas, o el [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Reemplace *\<GroupName\>* por el nombre del grupo que creó. Por ejemplo:

`$GroupName = "Group Creators"`

Guarde el archivo como GroupCreators.ps1.

En la ventana de PowerShell, vaya a la ubicación donde guardó el archivo (escriba <FileLocation> "CD").

Ejecute el script escribiendo:

`.\GroupCreators.ps1`

e [inicie sesión con su cuenta de administrador](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) cuando se le pida.

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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

![Captura de pantalla del resultado del script de PowerShell.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Si en el futuro desea cambiar el grupo que se usa, puede volver a ejecutar el script con el nombre del nuevo grupo.

Si desea desactivar la restricción de creación de grupos y volver a permitir que todos los usuarios creen grupos, establezca $GroupName en "" y $AllowGroupCreation en "True" y vuelva a ejecutar el script.

## <a name="step-3-verify-that-it-works"></a>Paso 3: Comprobar que funciona correctamente

Los cambios pueden tardar treinta minutos o más en tener efecto. Para comprobar la nueva configuración, haga lo siguiente:

1. Inicie sesión en Microsoft 365 con una cuenta de usuario de alguien que NO debería tener la capacidad de crear grupos. Es decir, no son miembros del grupo que ha creado ni de un administrador.

2. Seleccione el **icono Planner.**

3. En Planner, seleccione **Nuevo plan** en la navegación izquierda para crear un plan.

4. Debe obtener un mensaje que indica que el plan y la creación de grupos están deshabilitados.

Vuelva a intentar el mismo procedimiento con un miembro del grupo.

> [!NOTE]
> Si los miembros del grupo no pueden crear grupos, compruebe que no se están bloqueando a través de su directiva [de buzón de OWA](/powershell/module/exchange/set-owamailboxpolicy).

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)

[Introducción a PowerShell de Office 365](../enterprise/getting-started-with-microsoft-365-powershell.md)

[Configurar la administración de grupos de autoservicio en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Cmdlets de Azure Active Directory para configurar configuraciones de grupo](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)