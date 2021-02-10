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
ms.openlocfilehash: b53023521f477b5e864424ec648ccf7e5b749d0c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166992"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="e2dec-103">Administrar grupos de roles en EOP independiente</span><span class="sxs-lookup"><span data-stu-id="e2dec-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e2dec-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="e2dec-104">**Applies to**</span></span>
-  [<span data-ttu-id="e2dec-105">Exchange Online Protection independiente</span><span class="sxs-lookup"><span data-stu-id="e2dec-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="e2dec-106">En organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, puede usar el Centro de administración de Exchange (EAC) para agregar usuarios a grupos de roles.</span><span class="sxs-lookup"><span data-stu-id="e2dec-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="e2dec-107">La adición de usuarios a un grupo de roles proporciona al usuario permisos para realizar tareas de administración específicas.</span><span class="sxs-lookup"><span data-stu-id="e2dec-107">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="e2dec-108">También puede quitar usuarios de grupos de roles.</span><span class="sxs-lookup"><span data-stu-id="e2dec-108">You can also remove users from role groups.</span></span>

<span data-ttu-id="e2dec-109">Para obtener más información acerca de los roles y grupos de roles, vea [Permisos en EOP independiente.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="e2dec-109">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e2dec-110">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="e2dec-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e2dec-111">Para abrir el Centro de administración de Exchange (EAC), consulte [Centro de administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="e2dec-111">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="e2dec-112">Para abrir EOP PowerShell independiente, consulte Conectarse a [Exchange Online Protection PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="e2dec-112">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e2dec-113">Deberá tener asignados permisos en Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="e2dec-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="e2dec-114">Específicamente, necesita la función **Administración de** roles, que se asigna al grupo de roles **Administración** de la organización de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e2dec-114">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="e2dec-115">Para obtener más información, vea [Permisos en EOP](feature-permissions-in-eop.md) independiente y Usar el EAC modificar la lista [de miembros en grupos de roles.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="e2dec-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="e2dec-116">Para obtener información acerca de los métodos abreviados de teclado que pueden aplicarse a los procedimientos de este artículo, vea [Métodos abreviados](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para el Centro de administración de Exchange en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e2dec-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="e2dec-117">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="e2dec-117">Having problems?</span></span> <span data-ttu-id="e2dec-118">Pida ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="e2dec-118">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="e2dec-119">Usar el EAC para administrar grupos de roles</span><span class="sxs-lookup"><span data-stu-id="e2dec-119">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="e2dec-120">Usar el EAC para ver grupos de roles</span><span class="sxs-lookup"><span data-stu-id="e2dec-120">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="e2dec-121">En el EAC, vaya a **Roles de administrador** de \> **permisos.**</span><span class="sxs-lookup"><span data-stu-id="e2dec-121">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="e2dec-122">Aquí aparecen todos los grupos de roles de la organización.</span><span class="sxs-lookup"><span data-stu-id="e2dec-122">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="e2dec-123">Seleccione un grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="e2dec-123">Select a role group.</span></span> <span data-ttu-id="e2dec-124">El panel Detalles muestra **el nombre**, **la descripción**, los **roles asignados** y **administrados por** el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="e2dec-124">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="e2dec-125">También puede ver esta información haciendo clic en **el icono** ![ ](../../media/ITPro-EAC-EditIcon.png) Editar.</span><span class="sxs-lookup"><span data-stu-id="e2dec-125">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="e2dec-126">Usar el EAC para crear grupos de roles</span><span class="sxs-lookup"><span data-stu-id="e2dec-126">Use the EAC to create role groups</span></span>

<span data-ttu-id="e2dec-127">Al crear un nuevo grupo de roles, puede configurar todas las opciones usted mismo (durante la creación del grupo o después).</span><span class="sxs-lookup"><span data-stu-id="e2dec-127">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="e2dec-128">O bien, puede copiar un grupo de roles existente y modificarlo.</span><span class="sxs-lookup"><span data-stu-id="e2dec-128">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="e2dec-129">En el EAC, vaya a **Roles de** administrador de permisos y, a continuación, siga uno de estos \> pasos:</span><span class="sxs-lookup"><span data-stu-id="e2dec-129">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="e2dec-130">**Cree manualmente un nuevo grupo de roles:** haga clic **en el icono** ![ ](../../media/ITPro-EAC-AddIcon.png) Agregar.</span><span class="sxs-lookup"><span data-stu-id="e2dec-130">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="e2dec-131">**Copie un grupo de roles existente:** seleccione el grupo de funciones que desea copiar y, a continuación, haga clic **en el icono** Copiar ![ ](../../media/ITPro-EAC-CopyIcon.png) copia.</span><span class="sxs-lookup"><span data-stu-id="e2dec-131">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="e2dec-132">En la **ventana Nuevo grupo de** roles que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e2dec-132">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="e2dec-133">**Nombre:** escriba un nombre único para el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="e2dec-133">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="e2dec-134">**Descripción:** escriba una descripción opcional para el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="e2dec-134">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="e2dec-135">**Roles:** haga **clic en** agregar icono o quitar icono quitar para seleccionar o modificar los roles asignados ![ al grupo de ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) roles.</span><span class="sxs-lookup"><span data-stu-id="e2dec-135">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="e2dec-136">**Miembros:** haga **clic en el** icono Agregar agregar ![ ](../../media/ITPro-EAC-AddIcon.png) **o** quitar para modificar la pertenencia al grupo ![ de ](../../media/ITPro-EAC-RemoveIcon.gif) roles.</span><span class="sxs-lookup"><span data-stu-id="e2dec-136">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="e2dec-137">Cuando haya terminado, haga clic en **Guardar** para crear el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="e2dec-137">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="e2dec-138">Usar el EAC para modificar grupos de roles</span><span class="sxs-lookup"><span data-stu-id="e2dec-138">Use the EAC to modify role groups</span></span>

<span data-ttu-id="e2dec-139">En el EAC, vaya **a** Roles de administrador de permisos, seleccione el grupo de roles que desea modificar y, a continuación, haga clic en el icono \> Editar  ![ ](../../media/ITPro-EAC-EditIcon.png) edición.</span><span class="sxs-lookup"><span data-stu-id="e2dec-139">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="e2dec-140">Las mismas opciones están disponibles al modificar grupos de roles que al crear grupos de roles.</span><span class="sxs-lookup"><span data-stu-id="e2dec-140">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="e2dec-141">Puede:</span><span class="sxs-lookup"><span data-stu-id="e2dec-141">You can:</span></span>

- <span data-ttu-id="e2dec-142">Cambie el nombre y la descripción.</span><span class="sxs-lookup"><span data-stu-id="e2dec-142">Change the name and description.</span></span>

- <span data-ttu-id="e2dec-143">Agregar y quitar funciones de administración (crear o quitar asignaciones de roles).</span><span class="sxs-lookup"><span data-stu-id="e2dec-143">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="e2dec-144">Agregar y quitar miembros.</span><span class="sxs-lookup"><span data-stu-id="e2dec-144">Add and remove members.</span></span>

<span data-ttu-id="e2dec-145">**Nota:** Algunos grupos de roles (por ejemplo, Administración de la organización) restringen los roles que puede quitar del grupo.</span><span class="sxs-lookup"><span data-stu-id="e2dec-145">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="e2dec-146">Usar el EAC modificar la lista de miembros en grupos de roles</span><span class="sxs-lookup"><span data-stu-id="e2dec-146">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="e2dec-147">En el EAC,  vaya a Roles de administrador de permisos, seleccione el grupo de roles que desea modificar y, a continuación, haga clic en el icono \>   ![ Editar edición. ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="e2dec-147">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="e2dec-148">En la página de propiedades del grupo de roles que se abre, en la sección **Miembros,** siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e2dec-148">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="e2dec-149">Haga **clic en Agregar** icono agregar ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="e2dec-149">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="e2dec-150">En la página que aparece, busque el usuario que wou desea agregar y, a continuación, haga clic en **agregar ->**.</span><span class="sxs-lookup"><span data-stu-id="e2dec-150">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="e2dec-151">Seleccione usuarios y **haga clic en agregar >** veces según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e2dec-151">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="e2dec-152">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e2dec-152">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="e2dec-153">Seleccione los usuarios que desea quitar y, a continuación, haga clic **en el icono** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Quitar.</span><span class="sxs-lookup"><span data-stu-id="e2dec-153">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="e2dec-154">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e2dec-154">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e2dec-155">Puede que los usuarios tengan que cerrar la sesión e iniciarla de nuevo para ver los cambios en sus permisos administrativos después de agregar o quitar miembros de ese grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="e2dec-155">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="e2dec-156">Usar el EAC para quitar grupos de roles</span><span class="sxs-lookup"><span data-stu-id="e2dec-156">Use the EAC to remove role groups</span></span>

<span data-ttu-id="e2dec-157">No puede quitar grupos de roles integrados, pero puede quitar los grupos de roles personalizados que ha creado.</span><span class="sxs-lookup"><span data-stu-id="e2dec-157">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="e2dec-158">En el EAC, vaya a **Roles de administrador** de \> **permisos.**</span><span class="sxs-lookup"><span data-stu-id="e2dec-158">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="e2dec-159">Seleccione el grupo de roles que desea quitar y, a continuación, haga clic **en el icono** Eliminar ![ ](../../media/ITPro-EAC-DeleteIcon.png) eliminación.</span><span class="sxs-lookup"><span data-stu-id="e2dec-159">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="e2dec-160">Haga **clic en Sí** en la ventana de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="e2dec-160">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="e2dec-161">Usar PowerShell para administrar grupos de roles</span><span class="sxs-lookup"><span data-stu-id="e2dec-161">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="e2dec-162">Usar EOP PowerShell independiente para ver grupos de roles</span><span class="sxs-lookup"><span data-stu-id="e2dec-162">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="e2dec-163">Para ver un grupo de roles, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e2dec-163">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="e2dec-164">En este ejemplo se devuelve una lista resumida de todos los grupos de roles.</span><span class="sxs-lookup"><span data-stu-id="e2dec-164">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="e2dec-165">En este ejemplo se devuelve información detallada del grupo de roles denominado Recipient Administrators.</span><span class="sxs-lookup"><span data-stu-id="e2dec-165">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="e2dec-166">En este ejemplo se devuelven todos los grupos de roles en los que el usuario Julia es miembro.</span><span class="sxs-lookup"><span data-stu-id="e2dec-166">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="e2dec-167">Debe usar el valor DistinguishedName (DN) para Julia, que puede encontrar ejecutando el comando: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="e2dec-167">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="e2dec-168">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="e2dec-168">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="e2dec-169">Usar EOP PowerShell independiente para crear grupos de roles</span><span class="sxs-lookup"><span data-stu-id="e2dec-169">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="e2dec-170">Al crear un nuevo grupo de roles, puede configurar todas las opciones manualmente (durante la creación del grupo o después).</span><span class="sxs-lookup"><span data-stu-id="e2dec-170">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="e2dec-171">O bien, puede copiar un grupo de roles existente y modificarlo.</span><span class="sxs-lookup"><span data-stu-id="e2dec-171">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="e2dec-172">Para crear manualmente un nuevo grupo de roles, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e2dec-172">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="e2dec-173">El _parámetro Roles_ especifica las funciones de administración que se asignarán al grupo de funciones mediante la sintaxis `"Role1","Role1",..."RoleN"` siguiente.</span><span class="sxs-lookup"><span data-stu-id="e2dec-173">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="e2dec-174">Puede ver los roles disponibles con el cmdlet **Get-ManagementRole.**</span><span class="sxs-lookup"><span data-stu-id="e2dec-174">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="e2dec-175">El _parámetro Members_ especifica los miembros del grupo de roles mediante la siguiente sintaxis: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="e2dec-175">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="e2dec-176">Puede especificar usuarios, grupos de seguridad universal (USG) habilitados para correo u otros grupos de roles (entidades de seguridad).</span><span class="sxs-lookup"><span data-stu-id="e2dec-176">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="e2dec-177">En este ejemplo se crea un nuevo grupo de roles denominado "Limited Recipient Management" con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="e2dec-177">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="e2dec-178">La función de destinatarios de correo se asigna al grupo de funciones.</span><span class="sxs-lookup"><span data-stu-id="e2dec-178">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="e2dec-179">Los usuarios Kim y Martin se agregan como miembros.</span><span class="sxs-lookup"><span data-stu-id="e2dec-179">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="e2dec-180">Para copiar un grupo de roles existente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e2dec-180">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="e2dec-181">Almacene el grupo de funciones que desee copiar en una variable mediante la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e2dec-181">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="e2dec-182">Cree el nuevo grupo de roles con la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e2dec-182">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="e2dec-183">El _parámetro Members_ especifica los miembros del grupo de roles mediante la siguiente sintaxis: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="e2dec-183">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="e2dec-184">Puede especificar usuarios, grupos de seguridad universal (USG) habilitados para correo u otros grupos de roles (entidades de seguridad).</span><span class="sxs-lookup"><span data-stu-id="e2dec-184">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="e2dec-185">En este ejemplo se copia el grupo de funciones Administración de la organización al nuevo grupo de funciones denominado "Limited Organization Management".</span><span class="sxs-lookup"><span data-stu-id="e2dec-185">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="e2dec-186">Los miembros del grupo de roles son Isabelle, Carter y Lukas.</span><span class="sxs-lookup"><span data-stu-id="e2dec-186">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="e2dec-187">Para obtener información detallada acerca de la sintaxis y los parámetros, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="e2dec-187">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="e2dec-188">Usar EOP PowerShell independiente para modificar la lista de miembros en grupos de roles</span><span class="sxs-lookup"><span data-stu-id="e2dec-188">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="e2dec-189">Los **cmdlets Add-RoleGroupMember** y **Remove-RoleGroupMember** agregan o quitan miembros individuales de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="e2dec-189">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="e2dec-190">El cmdlet **Update-RoleGroupMember** puede reemplazar o modificar la lista existente de miembros.</span><span class="sxs-lookup"><span data-stu-id="e2dec-190">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="e2dec-191">Los miembros de un grupo de roles pueden ser usuarios, grupos de seguridad universal (USG) habilitados para correo u otros grupos de roles (entidades de seguridad).</span><span class="sxs-lookup"><span data-stu-id="e2dec-191">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="e2dec-192">Para modificar los miembros de un grupo de roles, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="e2dec-192">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="e2dec-193">Para _reemplazar_ la lista existente de miembros por los valores que especifique, use la siguiente sintaxis: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="e2dec-193">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="e2dec-194">Para _modificar selectivamente la_ lista existente de miembros, use la siguiente sintaxis: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="e2dec-194">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="e2dec-195">En este ejemplo se reemplazan todos los miembros actuales del grupo de roles Help Desk por los usuarios especificados.</span><span class="sxs-lookup"><span data-stu-id="e2dec-195">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="e2dec-196">En este ejemplo se agrega Daigoro Akai y se quita Valeria Distrito de la lista de miembros del grupo de roles Help Desk.</span><span class="sxs-lookup"><span data-stu-id="e2dec-196">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="e2dec-197">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="e2dec-197">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="e2dec-198">Usar EOP PowerShell independiente para quitar grupos de roles</span><span class="sxs-lookup"><span data-stu-id="e2dec-198">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="e2dec-199">No puede quitar grupos de roles integrados, pero puede quitar los grupos de roles personalizados que ha creado.</span><span class="sxs-lookup"><span data-stu-id="e2dec-199">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="e2dec-200">Para quitar un grupo de roles personalizado, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e2dec-200">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="e2dec-201">En este ejemplo se quita el grupo de roles de administradores de capacitación.</span><span class="sxs-lookup"><span data-stu-id="e2dec-201">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="e2dec-202">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="e2dec-202">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e2dec-203">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="e2dec-203">How do you know these procedures worked?</span></span>

<span data-ttu-id="e2dec-204">Para comprobar que copió correctamente un grupo de roles, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e2dec-204">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="e2dec-205">En el EAC, vaya a Roles **de** administrador de permisos y compruebe que el grupo de roles \> aparece (o no aparece).</span><span class="sxs-lookup"><span data-stu-id="e2dec-205">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="e2dec-206">Seleccione el grupo de roles y compruebe la  configuración en el panel Detalles o haga clic en el icono Editar ![ para comprobar la ](../../media/ITPro-EAC-EditIcon.png) configuración.</span><span class="sxs-lookup"><span data-stu-id="e2dec-206">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="e2dec-207">En Exchange Online PowerShell, reemplace por el nombre del grupo de roles y ejecute el siguiente comando para comprobar que el grupo de roles existe (o no existe) y compruebe la \<Role Group Name\> configuración:</span><span class="sxs-lookup"><span data-stu-id="e2dec-207">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
