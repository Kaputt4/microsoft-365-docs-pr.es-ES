---
title: Administrar un sitio de grupo de SharePoint Online aislado
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Administre un sitio de grupo de SharePoint Online aislado, agregue nuevos usuarios y grupos, quite usuarios y grupos y cree una subcarpeta de documentos con permisos personalizados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e354de77b70ea69d69e201bd3b1d40ea32cc5b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289526"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Administrar un sitio de grupo de SharePoint Online aislado

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 de Microsoft Defender para Office 365](office-365-atp.md)
- SharePoint Online 

 **Resumen:** Administre el sitio de grupo de SharePoint Online aislado con estos procedimientos.

En este artículo se describen las operaciones de administración comunes para un sitio de grupo de SharePoint Online aislado.

## <a name="add-a-new-user"></a>Agregar un nuevo usuario

Cuando alguien nuevo se une al sitio, debe decidir su nivel de participación en el sitio:

- Administración: agregar la nueva cuenta de usuario al grupo de acceso de administradores del sitio

- Colaboración activa: agregar la cuenta de usuario al grupo de acceso de miembros del sitio

- Visualización: agregar la cuenta de usuario al grupo de acceso de visores del sitio

Si administra cuentas de usuario y grupos a través de servicios de dominio de Active Directory (AD DS), agregue los usuarios adecuados a los grupos de acceso adecuados mediante los procedimientos normales de administración de usuarios y grupos de AD DS y espere a que se la sincronización con la suscripción.

Si administra cuentas de usuario y grupos a través de Microsoft 365, puede usar el Centro de administración de Microsoft 365 o PowerShell de Microsoft:

- Para el Centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario que tenga asignado el rol Administrador de cuentas de usuario o Administrador de la compañía y use Grupos para agregar los usuarios adecuados a los grupos de acceso adecuados.

- Para PowerShell, primero [conéctese con el módulo Azure Active Directory PowerShell para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) Para agregar una cuenta de usuario a un grupo de acceso con su nombre principal de usuario (UPN), use el siguiente bloque de comandos de PowerShell:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Para agregar una cuenta de usuario a un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Agregar un nuevo grupo

Para agregar acceso a un grupo completo, debe decidir el nivel de participación de todos los miembros del grupo en el sitio:

- Administración: agregar el grupo al grupo de acceso de administradores del sitio

- Colaboración activa: agregar el grupo al grupo de acceso de miembros del sitio

- Visualización: agregar el grupo al grupo de acceso de visores de sitio

Si está administrando cuentas de usuario y grupos a través de AD DS, agregue los grupos adecuados a los grupos adecuados mediante los procedimientos normales de administración de usuarios y grupos de AD DS y espere a la sincronización con la suscripción.

Si administra cuentas de usuario y grupos a través de Office 365, puede usar el Centro de administración de Microsoft 365 o PowerShell:

- Para el Centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario que tenga asignado el rol Administrador de cuentas de usuario o Administrador de la compañía y use Grupos para agregar los grupos adecuados a los grupos de acceso adecuados.

- Para PowerShell, primero [conéctese con el módulo Azure Active Directory PowerShell para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 A continuación, use los siguientes comandos de PowerShell:

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Eliminar a un usuario

Cuando se debe quitar el acceso de alguien del sitio, se quita del grupo de acceso del que es miembro actualmente en función de su participación en el sitio:

- Administración: quitar la cuenta de usuario del grupo de acceso de administradores del sitio

- Colaboración activa: quitar la cuenta de usuario del grupo de acceso de miembros del sitio

- Visualización: quitar la cuenta de usuario del grupo de acceso de visores del sitio

Si está administrando cuentas de usuario y grupos a través de AD DS, quite los usuarios adecuados de los grupos de acceso adecuados mediante los procedimientos normales de administración de usuarios y grupos de AD DS y espere a la sincronización con la suscripción.

Si administra cuentas de usuario y grupos a través de Office 365, puede usar el Centro de administración de Microsoft 365 o PowerShell:

- Para el Centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario que tenga asignado el rol Administrador de cuentas de usuario o Administrador de la compañía y use Grupos para quitar los usuarios adecuados de los grupos de acceso adecuados.

- Para PowerShell, primero [conéctese con el módulo Azure Active Directory PowerShell para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
Para quitar una cuenta de usuario de un grupo de acceso con su UPN, use el siguiente bloque de comandos de PowerShell:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Para quitar una cuenta de usuario de un grupo de acceso con su nombre para mostrar, use el siguiente bloque de comandos de PowerShell:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Quitar un grupo

Para quitar el acceso de un grupo completo, debe quitar el grupo del grupo de acceso del que es miembro actualmente en función de su participación en el sitio:

- Administración: quitar el grupo del grupo de acceso de administradores del sitio

- Colaboración activa: quitar el grupo del grupo de acceso de miembros del sitio

- Visualización: quitar el grupo del grupo de acceso de visores del sitio

Si está administrando cuentas de usuario y grupos a través de Windows Server Active Directory, quite los grupos adecuados de los grupos de acceso adecuados mediante los procedimientos normales de administración de usuarios y grupos de AD DS y espere a la sincronización con la suscripción.

Si administra cuentas de usuario y grupos a través de Office 365, puede usar el Centro de administración de Microsoft 365 o PowerShell:

- Para el Centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario a la que se haya asignado el rol administrador de cuentas de usuario o administrador de la compañía y use Grupos para quitar los grupos adecuados de los grupos de acceso adecuados.

- Para PowerShell, primero [conéctese con el módulo Azure Active Directory PowerShell para Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
Para quitar un grupo de un grupo de acceso con sus nombres para mostrar, use el siguiente bloque de comandos de PowerShell:

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Crear una subcarpeta de documentos con permisos personalizados

En algunos casos, un subconjunto de las personas que trabajan en el sitio aislado necesitan un lugar más privado para colaborar. Para los sitios de SharePoint Online, puede crear una subcarpeta en la carpeta Documentos del sitio y asignar permisos personalizados. Aquellos que no tienen permisos no verán la subcarpeta.

Para crear una subcarpeta de documentos con permisos personalizados, haga lo siguiente:

1. Inicie sesión en una cuenta que sea miembro del grupo de acceso de administradores del sitio. Para obtener ayuda, vea [Dónde iniciar sesión en Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Vaya al sitio de grupo aislado y haga clic en **Documentos.**

3. Vaya a la carpeta de la carpeta de documentos que contendrá la subcarpeta con permisos personalizados, cree la carpeta y, a continuación, ábrala.

4. Haga clic en **Compartir**.

5. Haga **clic en Compartido > opciones avanzadas.**

6. Haga **clic en Detener la herencia de permisos** y, a continuación, haga clic en **Aceptar.**

7. Haga clic en **Compartir**.

8. Haga **clic en Compartido > opciones avanzadas.**

9. Haga **clic en Conceder permisos > compartido con > avanzadas.**

10. En la página de permisos, haga clic **\<site name> en Miembros de la lista.**

11. En la **\<site name> página Miembros,** seleccione la marca de verificación junto al grupo de acceso de miembros del sitio, haga clic en Acciones **,** haga clic en Quitar usuarios del grupo y, a continuación, haga clic en **Aceptar.**

12. Para agregar miembros específicos a esta subcarpeta, haga clic en **> Agregar usuarios.**

13. En el **cuadro de** diálogo Compartir, escriba los nombres de las cuentas de usuario que pueden colaborar en archivos de la subcarpeta y, a continuación, haga clic en **Compartir**.

14. Actualice la página web para ver los nuevos resultados.

15. En **Grupos** del panel de **\<site name>** navegación izquierdo, haga clic en el grupo Visitantes y siga los pasos del 11 al 14 para especificar el conjunto de cuentas de usuario que pueden ver los archivos en la subcarpeta (según sea necesario).

16. En **Grupos** del panel de **\<site name>** navegación izquierdo, haga clic en el grupo Propietarios y siga los pasos del 11 al 14 para especificar el conjunto de cuentas de usuario que pueden administrar los permisos en la subcarpeta (según sea necesario).

17. Cierre la **pestaña Personas y grupos** en el explorador.

## <a name="see-also"></a>Consulte también

[Sitios de grupo de SharePoint Online aislados](isolated-sharepoint-online-team-sites.md)

[Diseñar un sitio de grupo de SharePoint Online aislado](design-an-isolated-sharepoint-online-team-site.md)

[Implementar un sitio de grupo de SharePoint Online aislado](deploy-an-isolated-sharepoint-online-team-site.md)
