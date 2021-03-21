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
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Los administradores pueden aprender a asignar o quitar permisos en el Centro de administración de Exchange (EAC) en Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e712c47d49508934ec7dd2438beff00eb6e1a20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926885"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Administrar grupos de roles en EOP independiente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
-  [Exchange Online Protection independiente](exchange-online-protection-overview.md)

En organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, puede usar el Centro de administración de Exchange (EAC) para agregar usuarios a grupos de roles. La adición de usuarios a un grupo de roles permite al usuario realizar tareas de administración específicas. También puede quitar usuarios de grupos de roles.

Para obtener más información acerca de los roles y grupos de roles, vea [Permissions in standalone EOP](feature-permissions-in-eop.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el Centro de administración de Exchange (EAC), vea Centro de [administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Para abrir PowerShell de EOP independiente, vea [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Debe tener asignados permisos en Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo. En concreto, necesita el rol **Administración** de roles, que se asigna al grupo de roles **Administración** de la organización de forma predeterminada. Para obtener más información, vea [Permissions in standalone EOP](feature-permissions-in-eop.md) y [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este artículo, vea [Métodos abreviados](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para el Centro de administración de Exchange en Exchange Online .

> [!TIP]
> ¿Problemas? Pida ayuda en el foro de [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) .

## <a name="use-the-eac-to-manage-role-groups"></a>Usar el EAC para administrar grupos de roles

### <a name="use-the-eac-to-view-role-groups"></a>Usar el EAC para ver grupos de roles

1. En el EAC, vaya a **Permisos** \> **Roles de administrador**. Aquí aparecen todos los grupos de roles de la organización.

2. Seleccione un grupo de roles. El panel Detalles muestra **los valores Name**, **Description**, **Assigned roles** y Managed **by** del grupo de roles. También puede ver esta información haciendo clic en **Editar** ![ icono Editar ](../../media/ITPro-EAC-EditIcon.png) .

### <a name="use-the-eac-to-create-role-groups"></a>Usar el EAC para crear grupos de roles

Al crear un nuevo grupo de roles, puede configurar todas las opciones usted mismo (durante la creación del grupo o después). O bien, puede copiar un grupo de roles existente y modificarlo.

1. En el EAC, vaya a **Permisos** Roles de administrador y, a continuación, \> realice uno de los siguientes pasos:

   - **Crear manualmente un nuevo grupo de roles:** haga clic **en Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) .

   - **Copiar un grupo de funciones existente:** seleccione el grupo de funciones que desea copiar y, a continuación, haga clic **en Copiar** icono ![ Copiar ](../../media/ITPro-EAC-CopyIcon.png) .

2. En la **ventana Nuevo grupo de** roles que aparece, configure las siguientes opciones:

    - **Nombre:** escriba un nombre único para el grupo de roles.

    - **Descripción:** escriba una descripción opcional para el grupo de roles.

    - **Roles:** haga **clic en Agregar** icono Agregar o Quitar icono Quitar para seleccionar o modificar los roles asignados al grupo de ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) roles.

    - **Miembros:** haga **clic en Agregar** icono Agregar o Quitar icono Quitar para modificar la pertenencia al grupo de ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) roles.

3. Cuando haya terminado, haga clic en **Guardar** para crear el grupo de roles.

### <a name="use-the-eac-to-modify-role-groups"></a>Usar el EAC para modificar grupos de roles

En el EAC, vaya a **Permisos** Roles de administrador , seleccione el grupo de roles que desea modificar y, a continuación, haga clic \>  **en Editar** icono Editar ![ ](../../media/ITPro-EAC-EditIcon.png) .

Las mismas opciones están disponibles al modificar grupos de roles que al crear grupos de roles. Podrá:

- Cambie el nombre y la descripción.

- Agregar y quitar roles de administración (crear o quitar asignaciones de roles).

- Agregar y quitar miembros.

**Nota:** Algunos grupos de roles (por ejemplo, Administración de la organización) restringen los roles que puede quitar del grupo.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Usar el EAC modificar la lista de miembros en grupos de roles

1. En el EAC, vaya a **Permisos** Roles de administrador , seleccione el grupo de roles que desea modificar y, a continuación, haga clic \>  **en Editar** icono Editar ![ ](../../media/ITPro-EAC-EditIcon.png) .

2. En la página de propiedades del grupo de roles que se abre, en la **sección Miembros,** realice uno de los pasos siguientes:

   - Haga clic **en Agregar** icono ![ agregar ](../../media/ITPro-EAC-AddIcon.png) . En la página que aparece, busque el usuario que wou desea agregar y, a continuación, haga clic **en agregar ->**. Seleccione usuarios y haga clic **en agregar ->** veces según sea necesario. Cuando haya terminado, haga clic en **Aceptar**.

   - Seleccione los usuarios que desea quitar y, a continuación, haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Cuando haya terminado, haga clic en **Guardar**.

   > [!NOTE]
   > Puede que los usuarios tengan que cerrar la sesión e iniciarla de nuevo para ver los cambios en sus permisos administrativos después de agregar o quitar miembros de ese grupo de roles.

### <a name="use-the-eac-to-remove-role-groups"></a>Usar el EAC para quitar grupos de roles

No puede quitar grupos de roles integrados, pero puede quitar grupos de roles personalizados que haya creado.

1. En el EAC, vaya a **Permisos** \> **Roles de administrador**.

2. Seleccione el grupo de roles que desea quitar y, a continuación, haga clic **en Eliminar** icono ![ Eliminar ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Haga **clic en Sí** en la ventana de confirmación que aparece.

## <a name="use-powershell-to-manage-role-groups"></a>Usar PowerShell para administrar grupos de roles

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Usar PowerShell de EOP independiente para ver grupos de roles

Para ver un grupo de roles, use la sintaxis siguiente:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

En este ejemplo se devuelve una lista resumida de todos los grupos de roles.

```PowerShell
Get-RoleGroup
```

En este ejemplo se devuelve información detallada para el grupo de roles denominado Administradores de destinatarios.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

En este ejemplo se devuelven todos los grupos de roles en los que el usuario Julia es miembro. Debe usar el valor DistinguishedName (DN) para Julia, que puede encontrar ejecutando el comando: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Usar PowerShell de EOP independiente para crear grupos de roles

Al crear un nuevo grupo de roles, puede configurar todas las opciones manualmente (durante la creación del grupo o después). O bien, puede copiar un grupo de roles existente y modificarlo.

- Para crear manualmente un nuevo grupo de roles, use la siguiente sintaxis:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - El _parámetro Roles_ especifica los roles de administración que se asignarán al grupo de funciones mediante la sintaxis siguiente `"Role1","Role1",..."RoleN"` . Puede ver los roles disponibles mediante el cmdlet **Get-ManagementRole.**

  - El _parámetro Members_ especifica los miembros del grupo de roles mediante la siguiente sintaxis: `"Member1","Member2",..."MemberN"` . Puede especificar usuarios, grupos de seguridad universales (USG) habilitados para correo u otros grupos de roles (entidades de seguridad).

  En este ejemplo se crea un nuevo grupo de roles denominado "Limited Recipient Management" con la siguiente configuración:

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

     El _parámetro Members_ especifica los miembros del grupo de roles mediante la siguiente sintaxis: `"Member1","Member2",..."MemberN"` . Puede especificar usuarios, grupos de seguridad universales (USG) habilitados para correo u otros grupos de roles (entidades de seguridad).

     En este ejemplo se copia el grupo de roles Administración de la organización en el nuevo grupo de roles denominado "Limited Organization Management". Los miembros del grupo de roles son Isabelle, Carter y Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Para obtener información detallada acerca de la sintaxis y los parámetros, [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Usar PowerShell EOP independiente para modificar la lista de miembros en grupos de roles

- Los cmdlets **Add-RoleGroupMember** y **Remove-RoleGroupMember** agregan o quitan miembros individuales de uno en uno. El cmdlet **Update-RoleGroupMember** puede reemplazar o modificar la lista existente de miembros.

- Los miembros de un grupo de roles pueden ser usuarios, grupos de seguridad universales (USG) habilitados para correo u otros grupos de roles (entidades de seguridad).

Para modificar los miembros de un grupo de roles, use la sintaxis siguiente:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Para _reemplazar_ la lista existente de miembros por los valores especificados, use la sintaxis siguiente: `"Member1","Member2",..."MemberN"` .

- Para _modificar selectivamente_ la lista existente de miembros, use la siguiente sintaxis: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

En este ejemplo se reemplazan todos los miembros actuales del grupo de roles de Help Desk por los usuarios especificados.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

En este ejemplo se agrega Daigoro Akai y se quita Valeria Barrio de la lista de miembros del grupo de roles Help Desk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Update-RoleGroupMember](/powershell/module/exchange/Update-RoleGroupMember).

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Usar PowerShell de EOP independiente para quitar grupos de roles

No puede quitar grupos de roles integrados, pero puede quitar grupos de roles personalizados que haya creado.

Para quitar un grupo de roles personalizado, use la siguiente sintaxis:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

En este ejemplo se quita el grupo de roles de administradores de capacitación.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha copiado correctamente un grupo de roles, siga uno de estos pasos:

- En el EAC, vaya a **Permisos** Roles de administrador y compruebe que el grupo de roles \> aparece (o no aparece). Seleccione el grupo de roles y compruebe la configuración en el panel Detalles o haga clic **en Editar** icono Editar para comprobar ![ la ](../../media/ITPro-EAC-EditIcon.png) configuración.

- En Exchange Online PowerShell, reemplace por el nombre del grupo de funciones y ejecute el siguiente comando para comprobar que el grupo de funciones existe (o no existe) y compruebe la \<Role Group Name\> configuración:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```