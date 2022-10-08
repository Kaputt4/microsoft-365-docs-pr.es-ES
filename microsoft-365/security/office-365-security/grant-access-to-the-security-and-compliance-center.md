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
ms.collection: m365-security
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: A los usuarios se les deben asignar permisos en el Centro de cumplimiento de & de seguridad de Microsoft 365 para poder administrar cualquiera de sus características de seguridad o cumplimiento.
ms.custom: seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: f98d8bcceea4474bf0bc542c518b8901c43cced2
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68055136"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

A los usuarios se les deben asignar permisos en el Centro de cumplimiento de seguridad & para poder administrar cualquiera de sus características de seguridad o cumplimiento. Como administrador global o miembro del grupo de roles OrganizationManagement en el Centro de cumplimiento de seguridad &, puede conceder estos permisos a los usuarios. Los usuarios solo podrán administrar las características de seguridad o cumplimiento a las que les proporcione acceso.

Para obtener más información sobre los distintos permisos que puede conceder a los usuarios en el Centro de cumplimiento de seguridad &, consulte [Permisos en el Centro de cumplimiento de seguridad &](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Debe ser administrador global o miembro del grupo de roles OrganizationManagement en el Centro de cumplimiento de seguridad & para completar los pasos descritos en este artículo.

- Los grupos de roles del Centro de cumplimiento de seguridad & pueden tener nombres similares a los grupos de roles de Exchange Online, pero no son los mismos.

- Las pertenencias a grupos de roles no se comparten entre Exchange Online y el Centro de cumplimiento de seguridad &.

- Los asociados con permisos de acceso delegado (DAP) con permisos administrar en nombre de (AOBO) no pueden acceder al Centro de cumplimiento de seguridad &.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Use el Centro de cumplimiento de seguridad & para proporcionar a otro usuario acceso al Centro de cumplimiento de seguridad &

1. Abra el Centro de cumplimiento de seguridad & en <https://protection.office.com> y, a continuación, vaya a **Permisos**. Para ir directamente a la pestaña **Permisos** , abra <https://protection.office.com/permissions>.

2. En la lista de grupos de roles, elija el grupo de roles y, a continuación, haga clic en **el icono Editar** ![edición.](../../media/O365-MDM-CreatePolicy-EditIcon.gif)

3. En la página de propiedades del grupo de roles, en **Miembros**, haga clic en **Agregar**![icono.](../../media/ITPro-EAC-AddIcon.gif) y seleccione el nombre del usuario (o usuarios) que desea agregar.

4. Cuando haya seleccionado todos los usuarios que desea agregar al grupo de roles, haga clic en **agregar\>** y, a continuación, **en Aceptar**.

5. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-security--compliance-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Uso de Security & Compliance PowerShell para proporcionar a otro usuario acceso al Centro de cumplimiento de seguridad &

1. [Conéctese al PowerShell de Seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell)

2. Utilice la siguiente sintaxis:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Para ver problemas detallados de sintaxis y parámetros, consulte [Add-RoleGroupMember](/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha concedido correctamente acceso al Centro de cumplimiento de seguridad &, realice cualquiera de los pasos siguientes:

- En el Centro de cumplimiento de seguridad &, vaya a **Permisos** y seleccione el grupo de roles. En el control flotante de detalles que se abre, compruebe los miembros del grupo de roles.

- En PowerShell de cumplimiento de seguridad &, reemplace por \<RoleGroupName\> el nombre del grupo de roles y ejecute el siguiente comando:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Para obtener información detallada sobre la sintaxis y los parámetros, vea [Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember).
