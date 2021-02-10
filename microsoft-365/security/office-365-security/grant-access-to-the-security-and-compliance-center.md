---
title: Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Los usuarios deben tener asignados permisos en el Centro de seguridad y & cumplimiento de Microsoft 365 para poder administrar cualquiera de sus características de seguridad o cumplimiento.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9e19825ce0f8224b2aee8e1419ef5d1ad425aadb
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165420"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Los usuarios deben tener asignados permisos en el Centro de seguridad & cumplimiento para poder administrar cualquiera de sus características de seguridad o cumplimiento. Como administrador global o miembro del grupo de roles OrganizationManagement en el Centro de seguridad & cumplimiento, puede conceder estos permisos a los usuarios. Los usuarios solo podrán administrar las características de seguridad o cumplimiento a las que les proporcione acceso.

Para obtener más información acerca de los diferentes permisos que puede conceder a los usuarios en el Centro de seguridad & cumplimiento, consulte Permisos en el Centro de seguridad [& cumplimiento.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Debe ser administrador global o miembro del grupo de roles OrganizationManagement en el Centro de seguridad y cumplimiento de &, para completar los pasos de este artículo.

- Los grupos de roles para el Centro de seguridad & cumplimiento pueden tener nombres similares a los grupos de roles en Exchange Online, pero no son los mismos.

- Las pertenencias a grupos de roles no se comparten entre Exchange Online y el Centro de & cumplimiento.

- Los asociados con permiso de acceso delegado (DAP) con permisos Administrar en nombre de (AOBO) no pueden acceder al Centro de seguridad & cumplimiento.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Usar el Centro de & cumplimiento para proporcionar a otro usuario acceso al Centro de & cumplimiento

1. Abra el Centro de seguridad & cumplimiento <https://protection.office.com> y, a continuación, vaya **a Permisos.** Para ir directamente a la **pestaña Permisos,** abra <https://protection.office.com/permissions> .

2. En la lista de grupos de roles, elija el grupo de roles y, a continuación, haga clic **en el icono** Editar ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) edición.

3. En la página de propiedades del grupo de roles, en Miembros, haga clic en Agregar icono y seleccione el nombre del usuario ![ ](../../media/ITPro-EAC-AddIcon.gif) (o usuarios) que desea agregar.

4. Cuando haya seleccionado todos los usuarios que desea agregar al grupo de roles, haga clic en **agregar \> y,** a continuación, en **Aceptar.**

5. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Usar PowerShell del Centro & seguridad y cumplimiento para proporcionar a otro usuario acceso al Centro de & cumplimiento

1. [Conectarse a PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Utilice la sintaxis siguiente:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Para obtener información detallada acerca de la sintaxis y los problemas de parámetros, [consulte Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha concedido acceso correctamente al Centro de seguridad & cumplimiento, siga uno de estos pasos:

- En el Centro de & cumplimiento, vaya a **Permisos** y seleccione el grupo de roles. En el menú desplegable de detalles que se abre, compruebe los miembros del grupo de roles.

- En PowerShell & centro de seguridad y cumplimiento, reemplace por el nombre del grupo de \<RoleGroupName\> roles y ejecute el siguiente comando:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
