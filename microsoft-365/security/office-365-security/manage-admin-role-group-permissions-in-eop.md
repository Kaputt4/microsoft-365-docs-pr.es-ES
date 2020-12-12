---
title: Administrar grupos de roles en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Los administradores pueden obtener información sobre cómo asignar o quitar permisos en el centro de administración de Exchange (EAC) en Exchange Online Protection.
ms.openlocfilehash: 4a1353963e5e3eadc1a07f8b4aa3a765b06c86ec
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659302"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Administrar grupos de roles en EOP independiente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En las organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, puede usar el centro de administración de Exchange (EAC) para agregar usuarios a los grupos de roles. Al agregar un usuario a un grupo de funciones, se concede a los usuarios permisos para realizar tareas de administración específicas. También puede quitar usuarios de los grupos de roles.

Para obtener más información acerca de los roles y los grupos de roles, consulte [Permissions in Standalone EOP](feature-permissions-in-eop.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el centro de administración de Exchange (EAC), consulte [centro de administración de Exchange en EOP independiente](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para abrir PowerShell independiente de EOP, consulte [conectarse a PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Debe tener asignados permisos en Exchange Online Protection para poder realizar los procedimientos descritos en este artículo. En concreto, necesita el rol de **Administración de roles** , que se asigna al grupo de roles administración de la **organización** de forma predeterminada. Para obtener más información, vea [permisos en EOP independiente](feature-permissions-in-eop.md) y [usar el EAC para modificar la lista de miembros de los grupos de roles](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este artículo, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> ¿Problemas? Pida ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-manage-role-groups"></a>Usar el EAC para administrar grupos de roles

### <a name="use-the-eac-to-view-role-groups"></a>Usar el EAC para ver grupos de roles

1. En el EAC, vaya a  \> **roles de administrador** de permisos. Aquí aparecen todos los grupos de roles de la organización.

2. Seleccione un grupo de roles. El panel de detalles muestra el **nombre**, la **Descripción**, los **roles asignados** y los **administrados por** el grupo de funciones. También puede ver esta información si hace clic en **Editar** ![ icono Editar ](../../media/ITPro-EAC-EditIcon.png) .

### <a name="use-the-eac-to-create-role-groups"></a>Usar el EAC para crear grupos de roles

Cuando se crea un nuevo grupo de roles, puede configurar usted mismo todas las opciones de configuración (durante la creación del grupo o después). O bien, puede copiar un grupo de roles existente y modificarlo.

1. En el EAC, vaya a  \> **roles de administrador** de permisos y, a continuación, siga uno de estos pasos:

   - **Cree manualmente un nuevo grupo de funciones**: haga clic en **Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) .

   - **Copiar un grupo de roles existente**: seleccione el grupo de roles que desea copiar y, a continuación, haga clic en el icono **copiar** ![ copia ](../../media/ITPro-EAC-CopyIcon.png) .

2. En la ventana **nuevo grupo de roles** que aparece, configure las siguientes opciones:

    - **Name**: escriba un nombre único para el grupo de roles.

    - **Descripción**: escriba una descripción opcional para el grupo de roles.

    - **Roles**: haga clic en **Agregar** icono ![ ](../../media/ITPro-EAC-AddIcon.png) o **quitar** icono ![ quitar ](../../media/ITPro-EAC-RemoveIcon.gif) para seleccionar o modificar los roles asignados al grupo de roles.

    - **Miembros**: haga clic en **Agregar** ![ icono ](../../media/ITPro-EAC-AddIcon.png) o **quitar** icono ![ quitar ](../../media/ITPro-EAC-RemoveIcon.gif) para modificar la pertenencia al grupo de roles.

3. Cuando haya terminado, haga clic en **Guardar** para crear el grupo de roles.

### <a name="use-the-eac-to-modify-role-groups"></a>Usar el EAC para modificar grupos de roles

En el EAC, vaya a  \> **roles de administrador** de permisos, seleccione el grupo de roles que desea modificar y, a continuación, haga clic en **Editar** ![ icono de edición ](../../media/ITPro-EAC-EditIcon.png) .

Las mismas opciones están disponibles cuando se modifican grupos de roles como cuando se crean grupos de roles. Puede:

- Cambie el nombre y la descripción.

- Agregar y quitar roles de administración (crear o quitar asignaciones de roles).

- Agregar y quitar miembros.

**Nota**: algunos grupos de roles (por ejemplo, administración de la organización) restringen los roles que puede quitar del grupo.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Usar el EAC modificar la lista de miembros de los grupos de roles

1. En el EAC, vaya a  \> **roles de administrador** de permisos, seleccione el grupo de roles que desea modificar y, a continuación, haga clic en **Editar** ![ icono de edición ](../../media/ITPro-EAC-EditIcon.png) .

2. En la página de propiedades del grupo de roles que se abre, en la sección **miembros** , siga uno de estos pasos:

   - Haga clic en **Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) . En la página que aparece, busque el usuario que Wou desea agregar y, a continuación, haga clic en **agregar >**. Seleccione usuarios y haga clic en **agregar >** tantas veces como sea necesario. Cuando haya terminado, haga clic en **Aceptar**.

   - Seleccione los usuarios que desea quitar y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Cuando haya terminado, haga clic en **Guardar**.

   > [!NOTE]
   > Puede que los usuarios tengan que cerrar la sesión e iniciarla de nuevo para ver los cambios en sus permisos administrativos después de agregar o quitar miembros de ese grupo de roles.

### <a name="use-the-eac-to-remove-role-groups"></a>Usar el EAC para quitar grupos de roles

No puede quitar los grupos de roles integrados, pero puede quitar los grupos de roles personalizados que haya creado.

1. En el EAC, vaya a  \> **roles de administrador** de permisos.

2. Seleccione el grupo de roles que desee quitar y, a continuación, haga clic en **eliminar** ![ icono de eliminación ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Haga clic en **sí** en la ventana de confirmación que aparece.

## <a name="use-powershell-to-manage-role-groups"></a>Usar PowerShell para administrar grupos de roles

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Usar PowerShell independiente de EOP para ver grupos de roles

Para ver un grupo de roles, use la siguiente sintaxis:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

En este ejemplo se devuelve una lista resumida de todos los grupos de funciones.

```PowerShell
Get-RoleGroup
```

En este ejemplo se devuelve información detallada sobre el grupo de funciones denominado administradores de destinatarios.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

En este ejemplo se devuelven todos los grupos de funciones en los que el usuario Julia es miembro. Debe usar el valor DistinguishedName (DN) para Julia, que puede encontrar al ejecutar el comando: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Usar PowerShell independiente de EOP para crear grupos de roles

Al crear un nuevo grupo de roles, puede configurar todas las opciones de forma manual (durante la creación del grupo o después). O bien, puede copiar un grupo de roles existente y modificarlo.

- Para crear manualmente un nuevo grupo de funciones, use la siguiente sintaxis:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - El parámetro _roles_ especifica los roles de administración que se asignarán al grupo de roles mediante la siguiente sintaxis `"Role1","Role1",..."RoleN"` . Puede ver los roles disponibles mediante el cmdlet **Get-ManagementRole** .

  - El parámetro _Members_ especifica los miembros del grupo de funciones mediante la siguiente sintaxis: `"Member1","Member2",..."MemberN"` . Puede especificar los usuarios, los grupos de seguridad universal habilitados para correo (USG) u otros grupos de roles (entidades de seguridad).

  En este ejemplo se crea un nuevo grupo de funciones denominado "administración de destinatarios limitados" con la siguiente configuración:

  - La función de destinatarios de correo se asigna al grupo de funciones.

  - Los usuarios Kim y Martin se agregan como miembros.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Para copiar un grupo de roles existente, siga estos pasos:

  1. Almacene el grupo de funciones que desee copiar en una variable mediante la siguiente sintaxis:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Cree el nuevo grupo de roles con la siguiente sintaxis:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     El parámetro _Members_ especifica los miembros del grupo de funciones mediante la siguiente sintaxis: `"Member1","Member2",..."MemberN"` . Puede especificar los usuarios, los grupos de seguridad universal habilitados para correo (USG) u otros grupos de roles (entidades de seguridad).

     En este ejemplo se copia el grupo de funciones administración de la organización en el nuevo grupo de funciones denominado "administración de la organización limitada". Los miembros del grupo de roles son Isabelle, Carter y Lucas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Para obtener información detallada acerca de la sintaxis y los parámetros, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Usar EOP independiente PowerShell modificar la lista de miembros de los grupos de roles

- Los cmdlets **Add-rolegroupmember** y **Remove-rolegroupmember** agregan o quitan miembros individuales de uno en uno. El cmdlet **Update-RoleGroupMember** puede reemplazar o modificar la lista de miembros existente.

- Los miembros de un grupo de funciones pueden ser usuarios, grupos de seguridad universal habilitados para correo (USG) u otros grupos de roles (entidades de seguridad).

Para modificar los miembros de un grupo de funciones, use la sintaxis siguiente:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Para _reemplazar_ la lista de miembros existente con los valores que especifique, use la siguiente sintaxis: `"Member1","Member2",..."MemberN"` .

- Para _modificar selectivamente_ la lista de miembros existente, use la siguiente sintaxis: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

En este ejemplo se reemplazan todos los miembros actuales del grupo de funciones del servicio de asistencia con los usuarios especificados.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

En este ejemplo se agrega Daigoro Akai y se quita Valeria barrio de la lista de miembros del grupo de funciones Help Desk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Usar PowerShell independiente de EOP para quitar grupos de roles

No puede quitar los grupos de roles integrados, pero puede quitar los grupos de roles personalizados que haya creado.

Para quitar un grupo de roles personalizado, use la siguiente sintaxis:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

En este ejemplo se quita el grupo de roles de administradores de capacitación.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que el grupo de roles se copió correctamente, siga uno de estos pasos:

- En el EAC, vaya a  \> **roles de administrador** de permisos y compruebe que el grupo de roles aparece (o no aparece en la lista). Seleccione el grupo de roles y Compruebe la configuración en el panel de detalles o haga clic en el icono **Editar** ![ Edición ](../../media/ITPro-EAC-EditIcon.png) para comprobar la configuración.

- En Exchange Online PowerShell, reemplace \<Role Group Name\> por el nombre del grupo de roles y ejecute el siguiente comando para comprobar que el grupo de roles existe (o no existe) y Compruebe la configuración:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
