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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Los usuarios deben tener asignados permisos en el centro de seguridad & cumplimiento de Microsoft 365 para que puedan administrar cualquiera de sus características de seguridad o cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d586684d44545f7aea94c30f5474b1fe5fa4651
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202812"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Los usuarios deben tener asignados permisos en el centro de seguridad & cumplimiento antes de que puedan administrar cualquiera de sus características de seguridad o cumplimiento. Como administrador global o miembro del grupo de funciones OrganizationManagement en el centro de seguridad & cumplimiento, puede conceder estos permisos a los usuarios. Los usuarios solo podrán administrar las características de seguridad o cumplimiento a las que les proporcione acceso.

Para obtener más información acerca de los distintos permisos que puede conceder a los usuarios en el centro de seguridad & cumplimiento, consulte [permisos en el centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Debe ser un administrador global o miembro del grupo de funciones OrganizationManagement en el centro de seguridad & cumplimiento para completar los pasos de este artículo.

- Los grupos de roles para el centro de seguridad & cumplimiento pueden tener nombres similares a los grupos de roles en Exchange Online, pero no son los mismos.

- Las pertenencias a grupos de roles no se comparten entre Exchange Online y el centro de seguridad & cumplimiento.

- Los permisos de acceso delegado (DAP) asociados con administrar en nombre de (AOBO) no pueden obtener acceso al centro de seguridad & cumplimiento.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Usar el centro de seguridad & cumplimiento para conceder a otro usuario acceso al centro de seguridad & cumplimiento

1. Abra el centro de seguridad & cumplimiento en <https://protection.office.com> y vaya a **permisos**. Para ir directamente a la pestaña **permisos** , Abra <https://protection.office.com/permissions> .

2. En la lista de grupos de roles, elija el grupo de roles y, a continuación, haga clic en **Editar** ![ icono de edición ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

3. En la página de propiedades del grupo de roles, en **miembros**, haga clic en **Agregar** ![ icono de agregar ](../../media/ITPro-EAC-AddIcon.gif) y seleccione el nombre del usuario (o usuarios) que desea agregar.

4. Cuando haya seleccionado todos los usuarios que desee agregar al grupo de roles, haga clic en **agregar \> ** y, a continuación, en **Aceptar**.

5. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Usar el PowerShell del centro de cumplimiento de & de seguridad para proporcionar a otro usuario acceso al centro de seguridad & cumplimiento

1. [Conectarse al Centro de seguridad y cumplimiento PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Utilice la sintaxis siguiente:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que se ha concedido correctamente el acceso al centro de seguridad & cumplimiento, siga uno de estos pasos:

- En el centro de seguridad & cumplimiento, vaya a **permisos** y seleccione el grupo de roles. En el control flotante detalles que se abre, compruebe los miembros del grupo de roles. 

- En el PowerShell del centro de cumplimiento de & de seguridad, reemplace \<RoleGroupName\> por el nombre del grupo de roles y ejecute el siguiente comando:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
