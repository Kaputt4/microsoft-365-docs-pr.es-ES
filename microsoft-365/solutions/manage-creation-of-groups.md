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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
recommendations: false
description: Obtenga información sobre cómo controlar qué usuarios pueden crear Grupos de Microsoft 365.
ms.openlocfilehash: 992f5c62654f23f90f910f62dc3bb78199b949b0
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64946932"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Administrar quién puede crear grupos de Microsoft 365

De forma predeterminada, todos los usuarios pueden crear grupos de Microsoft 365. Este es el enfoque recomendado, ya que permite a los usuarios empezar a colaborar sin necesidad de ayuda de TI.

Si su empresa requiere que restrinja quién puede crear grupos, puede restringir la creación de Grupos de Microsoft 365 a los miembros de un grupo o grupo de seguridad de Microsoft 365 determinado.

Si le preocupa que los usuarios creen equipos o grupos que no cumplan los estándares empresariales, considere la posibilidad de exigir a los usuarios que completen un curso de aprendizaje y, a continuación, agregarlos al grupo de usuarios permitidos.

Cuando se limita quién puede crear un grupo, afecta a todos los servicios que dependen de grupos para el acceso, incluidos los siguientes:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (clásico)
- Project para la web o la hoja de ruta

Los pasos de este artículo no impedirán que los miembros de determinados roles creen grupos. Microsoft 365 los administradores globales pueden crear grupos a través de Centro de administración de Microsoft 365, Planner, Exchange y SharePoint, pero no otras ubicaciones como Teams. Otros roles pueden crear Grupos de Microsoft 365 a través de medios limitados, que se enumeran a continuación.

- Administrador de Exchange: centro de administración de Exchange, Azure AD
- Soporte técnico de nivel 1 de partner: Centro de administración de Microsoft 365, centro de administración de Exchange, Azure AD
- Soporte técnico de nivel 2 de partner: Centro de administración de Microsoft 365, centro de administración de Exchange, Azure AD
- Escritores de directorios: Azure AD
- Administrador de SharePoint: centro de administración de SharePoint, Azure AD
- Administrador de servicios de Teams: centro de administración de Teams, Azure AD
- Administrador de usuarios: Centro de administración de Microsoft 365, Azure AD

Si es miembro de uno de estos roles, puede crear Grupos de Microsoft 365 para usuarios restringidos y, a continuación, asignar el usuario como propietario del grupo.

## <a name="licensing-requirements"></a>Requisitos de licencias

Para administrar quién crea grupos, las siguientes personas necesitan licencias de Azure AD Premium o Azure AD licencias EDU básicas asignadas a ellos:

- El administrador que configura estas opciones de creación de grupos
- Los miembros del grupo a los que se les permite crear grupos

> [!NOTE]
> Consulte [Asignación o eliminación de licencias en el portal de Azure Active Directory](/azure/active-directory/fundamentals/license-users-groups) para obtener más información sobre cómo asignar licencias de Azure.

Las siguientes personas no necesitan Azure AD Premium ni Azure AD licencias EDU básicas asignadas:

- Personas que son miembros de grupos Microsoft 365 y que no tienen la capacidad de crear otros grupos.

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>Paso 1: Crear un grupo para los usuarios que necesitan crear grupos de Microsoft 365

Solo se puede usar un grupo de la organización para controlar quién puede crear Grupos de Microsoft 365. Sin embargo, puede anidar otros grupos como miembros de este grupo.

Los administradores de los roles enumerados anteriormente no necesitan ser miembros de este grupo: conservan su capacidad de crear grupos.

1. En el centro de administración, vaya a la [página Grupos](https://admin.microsoft.com/adminportal/home#/groups).

2. Haga clic en **Agregar un grupo**.

3. Elija el tipo de grupo que desee. Recuerde que el nombre del grupo. Lo necesitará más adelante.

4. Termine de configurar el grupo, agregando personas u otros grupos que quiera que puedan crear grupos como miembros (no como propietarios).

Para obtener instrucciones detalladas, consulte [Creación, edición o eliminación de un grupo de seguridad en el Centro de administración de Microsoft 365](../admin/email/create-edit-or-delete-a-security-group.md).

## <a name="step-2-run-powershell-commands"></a>Paso 2: Ejecutar los comandos de PowerShell

Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph (AzureAD) (](/powershell/azure/active-directory/install-adv2)nombre de módulo **AzureADPreview**) para cambiar la configuración de acceso de invitado de nivel de grupo:

- Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) y siga las instrucciones para instalar la versión preliminar pública.

- Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.

- Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.

Copie el script siguiente en un editor de texto, como Bloc de notas o el [ISE de Windows PowerShell](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Reemplace por *\<GroupName\>* el nombre del grupo que creó. Por ejemplo:

`$GroupName = "Group Creators"`

Guarde el archivo como GroupCreators.ps1.

En la ventana de PowerShell, vaya a la ubicación donde guardó el archivo (escriba "CD \<FileLocation\>").

Ejecute el script escribiendo:

`.\GroupCreators.ps1`

e [inicie sesión con su cuenta de administrador](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) cuando se le solicite.

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
} else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

La última línea del script mostrará la configuración actualizada:

![Captura de pantalla de la salida del script de PowerShell.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Si en el futuro quiere cambiar qué grupo se usa, puede volver a ejecutar el script con el nombre del nuevo grupo.

Si desea desactivar la restricción de creación de grupos y volver a permitir que todos los usuarios creen grupos, establezca $GroupName en "" y $AllowGroupCreation en "True" y vuelva a ejecutar el script.

## <a name="step-3-verify-that-it-works"></a>Paso 3: Comprobar que funciona correctamente

Los cambios pueden tardar treinta minutos o más en surtir efecto. Para comprobar la nueva configuración, haga lo siguiente:

1. Inicie sesión en Microsoft 365 con una cuenta de usuario de alguien que no debería tener la capacidad de crear grupos. Es decir, no son miembros del grupo que creó ni de un administrador.

2. Seleccione el icono **de Planner** .

3. En Planner, seleccione **Nuevo plan** en el panel de navegación izquierdo para crear un plan.

4. Debería recibir un mensaje que indica que el plan y la creación de grupos están deshabilitados.

Vuelva a intentar el mismo procedimiento con un miembro del grupo.

> [!NOTE]
> Si los miembros del grupo no pueden crear grupos, compruebe que no se bloqueen a través de su [directiva de buzón de OWA](/powershell/module/exchange/set-owamailboxpolicy).

## <a name="related-topics"></a>Temas relacionados

[Recomendaciones de planeamiento de gobernanza de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[Creación del plan de gobernanza de colaboración](collaboration-governance-first.md)

[Introducción a PowerShell de Office 365](../enterprise/getting-started-with-microsoft-365-powershell.md)

[Configuración de la administración de grupos de autoservicio en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Cmdlets de Azure Active Directory para configurar configuraciones de grupo](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
