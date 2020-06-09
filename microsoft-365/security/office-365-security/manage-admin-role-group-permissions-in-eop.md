---
title: Administrar grupos de roles en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Los administradores pueden obtener información sobre cómo asignar o quitar permisos en el centro de administración de Exchange (EAC) en Exchange Online Protection.
ms.openlocfilehash: 3555d3bd7fa4c53802eb214747735223cccc21e5
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616519"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="33194-103">Administrar grupos de roles en EOP independiente</span><span class="sxs-lookup"><span data-stu-id="33194-103">Manage role groups in standalone EOP</span></span>

<span data-ttu-id="33194-104">En las organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, puede usar el centro de administración de Exchange (EAC) para agregar usuarios a los grupos de roles.</span><span class="sxs-lookup"><span data-stu-id="33194-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="33194-105">Al agregar un usuario a un grupo de funciones, se concede a los usuarios permisos para realizar tareas de administración específicas.</span><span class="sxs-lookup"><span data-stu-id="33194-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="33194-106">También puede quitar usuarios de los grupos de roles.</span><span class="sxs-lookup"><span data-stu-id="33194-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="33194-107">Para obtener más información acerca de los roles y los grupos de roles, consulte [Permissions in Standalone EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="33194-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="33194-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="33194-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="33194-109">Para abrir el centro de administración de Exchange (EAC), consulte [centro de administración de Exchange en EOP independiente](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="33194-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="33194-110">Para abrir PowerShell independiente de EOP, consulte [conectarse a PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="33194-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="33194-111">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="33194-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="33194-112">En concreto, necesita la función de administración de funciones, que se asigna al grupo de funciones OrganizationManagement (administrador global) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="33194-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="33194-113">Para obtener más información, vea [permisos en EOP independiente](feature-permissions-in-eop.md) y [usar el EAC para modificar la lista de miembros de los grupos de roles](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="33194-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="33194-114">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="33194-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="33194-115">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="33194-115">Having problems?</span></span> <span data-ttu-id="33194-116">Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="33194-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="33194-117">Usar el EAC para administrar grupos de roles</span><span class="sxs-lookup"><span data-stu-id="33194-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="33194-118">Usar el EAC para ver grupos de roles</span><span class="sxs-lookup"><span data-stu-id="33194-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="33194-119">En el EAC, vaya a **Permissions** \> **roles de administrador**de permisos.</span><span class="sxs-lookup"><span data-stu-id="33194-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="33194-120">Aquí aparecen todos los grupos de roles de la organización.</span><span class="sxs-lookup"><span data-stu-id="33194-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="33194-121">Seleccione un grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="33194-121">Select a role group.</span></span> <span data-ttu-id="33194-122">El panel de detalles muestra el **nombre**, la **Descripción**, los **roles asignados**y los **administrados por** el grupo de funciones.</span><span class="sxs-lookup"><span data-stu-id="33194-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="33194-123">También puede ver esta información si hace clic en **Editar** ![ icono Editar ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="33194-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="33194-124">Usar el EAC para crear grupos de roles</span><span class="sxs-lookup"><span data-stu-id="33194-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="33194-125">Cuando se crea un nuevo grupo de roles, puede configurar usted mismo todas las opciones de configuración (durante la creación del grupo o después).</span><span class="sxs-lookup"><span data-stu-id="33194-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="33194-126">O bien, puede copiar un grupo de roles existente y modificarlo.</span><span class="sxs-lookup"><span data-stu-id="33194-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="33194-127">En el EAC, vaya a **Permissions** \> **roles de administrador**de permisos y, a continuación, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="33194-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="33194-128">**Cree manualmente un nuevo grupo de funciones**: haga clic en **Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="33194-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="33194-129">**Copiar un grupo de roles existente**: seleccione el grupo de roles que desea copiar y, a continuación, haga clic en el icono **copiar** ![ copia ](../../media/ITPro-EAC-CopyIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="33194-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="33194-130">En la ventana **nuevo grupo de roles** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="33194-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="33194-131">**Name**: escriba un nombre único para el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="33194-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="33194-132">**Descripción**: escriba una descripción opcional para el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="33194-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="33194-133">**Roles**: haga clic en **Agregar** ![ icono ](../../media/ITPro-EAC-AddIcon.png) de agregar o **quitar** ![ itpro-EAC-RemoveIcon. gif ](../../media/ITPro-EAC-RemoveIcon.gif) para seleccionar o modificar los roles asignados al grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="33194-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="33194-134">**Miembros**: haga clic en **Agregar** ![ icono ](../../media/ITPro-EAC-AddIcon.png) de agregar o en **quitar** ![ itpro-EAC-RemoveIcon. gif ](../../media/ITPro-EAC-RemoveIcon.gif) para modificar la pertenencia al grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="33194-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="33194-135">Cuando haya terminado, haga clic en **Guardar** para crear el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="33194-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="33194-136">Usar el EAC para modificar grupos de roles</span><span class="sxs-lookup"><span data-stu-id="33194-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="33194-137">En el EAC, vaya a **Permissions** \> **roles de administrador**de permisos, seleccione el grupo de roles que desea modificar y, a continuación, haga clic en **Editar** ![ icono de edición ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="33194-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="33194-138">Las mismas opciones están disponibles cuando se modifican grupos de roles como cuando se crean grupos de roles.</span><span class="sxs-lookup"><span data-stu-id="33194-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="33194-139">Puede:</span><span class="sxs-lookup"><span data-stu-id="33194-139">You can:</span></span>

- <span data-ttu-id="33194-140">Cambie el nombre y la descripción.</span><span class="sxs-lookup"><span data-stu-id="33194-140">Change the name and description.</span></span>

- <span data-ttu-id="33194-141">Agregar y quitar roles de administración (crear o quitar asignaciones de roles).</span><span class="sxs-lookup"><span data-stu-id="33194-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="33194-142">Agregar y quitar miembros.</span><span class="sxs-lookup"><span data-stu-id="33194-142">Add and remove members.</span></span>

<span data-ttu-id="33194-143">**Nota**: algunos grupos de roles (por ejemplo, administración de la organización) restringen los roles que puede quitar del grupo.</span><span class="sxs-lookup"><span data-stu-id="33194-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="33194-144">Usar el EAC modificar la lista de miembros de los grupos de roles</span><span class="sxs-lookup"><span data-stu-id="33194-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="33194-145">En el EAC, vaya a **Permissions** \> **roles de administrador**de permisos, seleccione el grupo de roles que desea modificar y, a continuación, haga clic en **Editar** ![ icono de edición ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="33194-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="33194-146">En la página de propiedades del grupo de roles que se abre, en la sección **memebers** , siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="33194-146">In the role group properties page that opens, in the **Memebers** section, do either of the following steps:</span></span>

   - <span data-ttu-id="33194-147">Haga clic en **Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="33194-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="33194-148">En la página que aparece, busque el usuario que Wou desea agregar y, a continuación, haga clic en **agregar >**.</span><span class="sxs-lookup"><span data-stu-id="33194-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="33194-149">Seleccione usuarios y haga clic en **agregar >** tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="33194-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="33194-150">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="33194-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="33194-151">Seleccione los usuarios que desea quitar y, a continuación, haga clic en **quitar** ![ icono quitar ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="33194-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="33194-152">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="33194-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="33194-153">Puede que los usuarios tengan que cerrar la sesión e iniciarla de nuevo para ver los cambios en sus permisos administrativos después de agregar o quitar miembros de ese grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="33194-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="33194-154">Usar el EAC para quitar grupos de roles</span><span class="sxs-lookup"><span data-stu-id="33194-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="33194-155">No puede quitar los grupos de roles integrados, pero puede quitar los grupos de roles personalizados que haya creado.</span><span class="sxs-lookup"><span data-stu-id="33194-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="33194-156">En el EAC, vaya a **Permissions** \> **roles de administrador**de permisos.</span><span class="sxs-lookup"><span data-stu-id="33194-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="33194-157">Seleccione el grupo de roles que desee quitar y, a continuación, haga clic en **eliminar** ![ icono de eliminación ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="33194-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="33194-158">Haga clic en **sí** en la ventana de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="33194-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="33194-159">Usar PowerShell para administrar grupos de roles</span><span class="sxs-lookup"><span data-stu-id="33194-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="33194-160">Usar PowerShell independiente de EOP para ver grupos de roles</span><span class="sxs-lookup"><span data-stu-id="33194-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="33194-161">Para ver un grupo de roles, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="33194-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="33194-162">En este ejemplo se devuelve una lista resumida de todos los grupos de funciones.</span><span class="sxs-lookup"><span data-stu-id="33194-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="33194-163">En este ejemplo se devuelve información detallada sobre el grupo de funciones denominado administradores de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="33194-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="33194-164">En este ejemplo se devuelven todos los grupos de funciones en los que el usuario Julia es miembro.</span><span class="sxs-lookup"><span data-stu-id="33194-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="33194-165">Debe usar el valor DistinguishedName (DN) para Julia, que puede encontrar al ejecutar el comando: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="33194-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="33194-166">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="33194-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="33194-167">Usar PowerShell independiente de EOP para crear grupos de roles</span><span class="sxs-lookup"><span data-stu-id="33194-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="33194-168">Al crear un nuevo grupo de roles, puede configurar todas las opciones de forma manual (durante la creación del grupo o después).</span><span class="sxs-lookup"><span data-stu-id="33194-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="33194-169">O bien, puede copiar un grupo de roles existente y modificarlo.</span><span class="sxs-lookup"><span data-stu-id="33194-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="33194-170">Para crear manualmente un nuevo grupo de funciones, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="33194-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="33194-171">El parámetro _roles_ especifica los roles de administración que se asignarán al grupo de roles mediante la siguiente sintaxis `"Role1","Role1",..."RoleN"` .</span><span class="sxs-lookup"><span data-stu-id="33194-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="33194-172">Puede ver los roles disponibles mediante el cmdlet **Get-ManagementRole** .</span><span class="sxs-lookup"><span data-stu-id="33194-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="33194-173">El parámetro _Members_ especifica los miembros del grupo de funciones mediante la siguiente sintaxis: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="33194-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="33194-174">Puede especificar los usuarios, los grupos de seguridad universal habilitados para correo (USG) u otros grupos de roles (entidades de seguridad).</span><span class="sxs-lookup"><span data-stu-id="33194-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="33194-175">En este ejemplo se crea un nuevo grupo de funciones denominado "administración de destinatarios limitados" con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="33194-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="33194-176">La función de destinatarios de correo se asigna al grupo de funciones.</span><span class="sxs-lookup"><span data-stu-id="33194-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="33194-177">Los usuarios Kim y Martin se agregan como miembros.</span><span class="sxs-lookup"><span data-stu-id="33194-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="33194-178">Para copiar un grupo de roles existente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="33194-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="33194-179">Almacene el grupo de funciones que desee copiar en una variable mediante la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="33194-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="33194-180">Cree el nuevo grupo de roles con la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="33194-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="33194-181">El parámetro _Members_ especifica los miembros del grupo de funciones mediante la siguiente sintaxis: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="33194-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="33194-182">Puede especificar los usuarios, los grupos de seguridad universal habilitados para correo (USG) u otros grupos de roles (entidades de seguridad).</span><span class="sxs-lookup"><span data-stu-id="33194-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="33194-183">En este ejemplo se copia el grupo de funciones administración de la organización en el nuevo grupo de funciones denominado "administración de la organización limitada".</span><span class="sxs-lookup"><span data-stu-id="33194-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="33194-184">Los miembros del grupo de roles son Isabelle, Carter y Lucas.</span><span class="sxs-lookup"><span data-stu-id="33194-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="33194-185">Para obtener información detallada acerca de la sintaxis y los parámetros, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="33194-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="33194-186">Usar EOP independiente PowerShell modificar la lista de miembros de los grupos de roles</span><span class="sxs-lookup"><span data-stu-id="33194-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="33194-187">Los cmdlets **Add-rolegroupmember** y **Remove-rolegroupmember** agregan o quitan miembros individuales de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="33194-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="33194-188">El cmdlet **Update-RoleGroupMember** puede reemplazar o modificar la lista de miembros existente.</span><span class="sxs-lookup"><span data-stu-id="33194-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="33194-189">Los miembros de un grupo de funciones pueden ser usuarios, grupos de seguridad universal habilitados para correo (USG) u otros grupos de roles (entidades de seguridad).</span><span class="sxs-lookup"><span data-stu-id="33194-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="33194-190">Para modificar los miembros de un grupo de funciones, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="33194-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="33194-191">Para _reemplazar_ la lista de miembros existente con los valores que especifique, use la siguiente sintaxis: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="33194-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="33194-192">Para _modificar selectivamente_ la lista de miembros existente, use la siguiente sintaxis: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="33194-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="33194-193">En este ejemplo se reemplazan todos los miembros actuales del grupo de funciones del servicio de asistencia con los usuarios especificados.</span><span class="sxs-lookup"><span data-stu-id="33194-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="33194-194">En este ejemplo se agrega Daigoro Akai y se quita Valeria barrio de la lista de miembros del grupo de funciones Help Desk.</span><span class="sxs-lookup"><span data-stu-id="33194-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="33194-195">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="33194-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="33194-196">Usar PowerShell independiente de EOP para quitar grupos de roles</span><span class="sxs-lookup"><span data-stu-id="33194-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="33194-197">No puede quitar los grupos de roles integrados, pero puede quitar los grupos de roles personalizados que haya creado.</span><span class="sxs-lookup"><span data-stu-id="33194-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="33194-198">Para quitar un grupo de roles personalizado, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="33194-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="33194-199">En este ejemplo se quita el grupo de roles de administradores de capacitación.</span><span class="sxs-lookup"><span data-stu-id="33194-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="33194-200">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="33194-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="33194-201">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="33194-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="33194-202">Para comprobar que el grupo de roles se copió correctamente, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="33194-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="33194-203">En el EAC, vaya a **Permissions** \> **roles de administrador**de permisos y compruebe que el grupo de roles aparece (o no aparece en la lista).</span><span class="sxs-lookup"><span data-stu-id="33194-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="33194-204">Seleccione el grupo de roles y Compruebe la configuración en el panel de detalles o haga clic en el icono **Editar** ![ Edición ](../../media/ITPro-EAC-EditIcon.png) para comprobar la configuración.</span><span class="sxs-lookup"><span data-stu-id="33194-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="33194-205">En Exchange Online PowerShell, reemplace \<Role Group Name\> por el nombre del grupo de roles y ejecute el siguiente comando para comprobar que el grupo de roles existe (o no existe) y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="33194-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
