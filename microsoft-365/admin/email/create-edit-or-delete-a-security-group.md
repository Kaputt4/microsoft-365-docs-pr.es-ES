---
title: Crear, editar o eliminar un grupo de seguridad en el centro de administración de Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Obtenga información sobre cómo crear, editar o eliminar un grupo de seguridad.
ms.openlocfilehash: 6f4daa66c11675674fdbfbfeb625128d8f817520
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140446"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="51d41-103">Crear, editar o eliminar un grupo de seguridad en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51d41-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="51d41-104">El centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="51d41-104">The admin center is changing.</span></span> <span data-ttu-id="51d41-105">Si su experiencia no coincide con los detalles que se presentan aquí, vea [acerca del nuevo centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="51d41-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="51d41-106">En la página Microsoft 365 **grupos** , puede crear grupos de cuentas de usuario que puede usar para asignar los mismos permisos en SharePoint Online y en CRM Online.</span><span class="sxs-lookup"><span data-stu-id="51d41-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="51d41-107">Por ejemplo, un administrador puede crear un grupo de seguridad para conceder acceso a un determinado grupo de personas a un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="51d41-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="51d41-108">Solo los administradores globales y de administración de usuarios tienen permisos para crear, editar o eliminar grupos de seguridad; para obtener más información acerca de los roles de administrador, vea [asignación de roles de administrador](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="51d41-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="51d41-109">También hay [Grupos de Exchange Online y SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) que puede usar para enviar correo electrónico o asignar permisos a un grupo de usuarios y [Grupos de Exchange Online y SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) que conceden a los usuarios permisos y acceso a sitios y colecciones de sitios.</span><span class="sxs-lookup"><span data-stu-id="51d41-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="51d41-110">¿Tiene previsto usar buzones del sitio?</span><span class="sxs-lookup"><span data-stu-id="51d41-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="51d41-111">Todos los usuarios que se agreguen a un sitio de SharePoint mediante un grupo de seguridad en lugar de individualmente podrán usar únicamente el buzón del sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="51d41-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="51d41-112">No podrán acceder al buzón del sitio de Outlook.</span><span class="sxs-lookup"><span data-stu-id="51d41-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="51d41-113">Para obtener más información, vea [usar grupos de Microsoft 365 en lugar de buzones de sitio](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span><span class="sxs-lookup"><span data-stu-id="51d41-113">For more information, see [Use Microsoft 365 groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="51d41-114">Administración de grupos de seguridad en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="51d41-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="51d41-115">Agregar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="51d41-115">Add a security group</span></span>

1. <span data-ttu-id="51d41-116">En el centro de administración de Microsoft 365, vaya **a la** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="51d41-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="51d41-117">En la página **grupos** , seleccione **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="51d41-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="51d41-118">En la página **elegir un tipo de grupo** , elija **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="51d41-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="51d41-119">Siga los pasos para completar la creación del grupo.</span><span class="sxs-lookup"><span data-stu-id="51d41-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="51d41-120">Adición de miembros a un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="51d41-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="51d41-121">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="51d41-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="51d41-122">Seleccione el nombre del grupo de seguridad en la página **grupos** y, en la pestaña **miembros** , seleccione **Ver todos y administrar miembros**.</span><span class="sxs-lookup"><span data-stu-id="51d41-122">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="51d41-123">En el panel de grupo, seleccione **Agregar miembros** y elija la persona de la lista o escriba el nombre de la persona que desea agregar en el cuadro de **búsqueda** y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="51d41-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="51d41-124">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="51d41-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="51d41-125">Seleccione el nombre del grupo de seguridad en la página **grupos** y, a continuación, seleccione **Editar** junto a **miembros**.</span><span class="sxs-lookup"><span data-stu-id="51d41-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="51d41-126">En el panel de grupo, seleccione **Agregar miembros** y elija la persona de la lista o escriba el nombre de la persona que desea agregar en el cuadro de **búsqueda** y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="51d41-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="51d41-127">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="51d41-127">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="51d41-128">Seleccione el nombre del grupo de seguridad en la página **grupos** y, a continuación, seleccione **Editar** junto a **miembros**.</span><span class="sxs-lookup"><span data-stu-id="51d41-128">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="51d41-129">En el panel de grupo, seleccione **Agregar miembros** y elija la persona de la lista o escriba el nombre de la persona que desea agregar en el cuadro de **búsqueda** y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="51d41-129">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="51d41-130">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="51d41-130">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="51d41-131">Editar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="51d41-131">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="51d41-132">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="51d41-132">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="51d41-133">En el centro de administración, vaya a **la** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="51d41-133">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="51d41-134">En la página **grupos** , seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="51d41-134">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="51d41-135">En el panel Configuración, seleccione la pestaña **General** o la pestaña **miembros** para editar los detalles o miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="51d41-135">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="51d41-136">En el centro de administración, vaya a **la** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="51d41-136">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="51d41-137">En la página **grupos** , seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="51d41-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="51d41-138">En el panel grupo de seguridad, seleccione **Editar** junto a **nombre** o en la ficha **miembros** para editar los detalles o los miembros de un grupo.</span><span class="sxs-lookup"><span data-stu-id="51d41-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="51d41-139">Después de realizar los cambios, seleccione **Guardar** \> **cierre**.</span><span class="sxs-lookup"><span data-stu-id="51d41-139">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="51d41-140">En el centro de administración, vaya a **la** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="51d41-140">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="51d41-141">En la página **grupos** , seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="51d41-141">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="51d41-142">En el panel grupo de seguridad, seleccione **Editar** junto a **nombre** o en la ficha **miembros** para editar los detalles o los miembros de un grupo.</span><span class="sxs-lookup"><span data-stu-id="51d41-142">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="51d41-143">Después de realizar los cambios, seleccione **Guardar** > **cierre**.</span><span class="sxs-lookup"><span data-stu-id="51d41-143">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="51d41-144">Eliminar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="51d41-144">Delete a security group</span></span>

1. <span data-ttu-id="51d41-145">En el centro de administración, vaya a **la** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="51d41-145">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="51d41-146">En la página **grupos** , seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="51d41-146">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="51d41-147">Seleccione **Eliminar grupo** (icono de wasetbin) y, a continuación, confirme seleccionando **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="51d41-147">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="51d41-148">Seleccione **cerrar** una vez que se elimine el grupo.</span><span class="sxs-lookup"><span data-stu-id="51d41-148">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="51d41-149">Grupos de Exchange Online y SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="51d41-149">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="51d41-150">Si desea crear grupos de usuarios para que pueda enviarles un correo electrónico a todos al mismo tiempo, puede hacerlo en el centro de administración de Exchange visitando los **grupos**de **destinatarios** \> de **Administración** \> de **Exchange** \> .</span><span class="sxs-lookup"><span data-stu-id="51d41-150">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="51d41-151">A continuación, **New**![seleccione Agregar](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)nuevo y seleccione el tipo de grupo que desea crear:</span><span class="sxs-lookup"><span data-stu-id="51d41-151">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="51d41-152">**Grupo de distribución**: se usa para distribuir mensajes a un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="51d41-152">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="51d41-153">También se denomina *grupo de distribución habilitado para correo*, o bien, *lista de distribución*.</span><span class="sxs-lookup"><span data-stu-id="51d41-153">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="51d41-154">Para más información, vea [Administrar grupos de distribución](https://technet.microsoft.com/library/bb124513.aspx).</span><span class="sxs-lookup"><span data-stu-id="51d41-154">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="51d41-155">**Grupo de seguridad**: se puede usar para distribuir mensajes a un grupo de usuarios o para conceder permisos de acceso a recursos.</span><span class="sxs-lookup"><span data-stu-id="51d41-155">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="51d41-156">Este grupo también se denomina *grupo de seguridad habilitado para correo*.</span><span class="sxs-lookup"><span data-stu-id="51d41-156">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="51d41-157">Para obtener más información, consulte [Administrar grupos de seguridad habilitados para correo](https://technet.microsoft.com/library/bb123521.aspx).</span><span class="sxs-lookup"><span data-stu-id="51d41-157">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="51d41-158">**Grupo de distribución dinámico**: un tipo de grupo de distribución cuya lista de destinatarios se vuelve a calcular cada vez que se envía un mensaje en función de filtros y condiciones definidos.</span><span class="sxs-lookup"><span data-stu-id="51d41-158">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="51d41-159">Para obtener más información, vea [Administrar grupos de distribución dinámica](https://technet.microsoft.com/library/bb123722.aspx).</span><span class="sxs-lookup"><span data-stu-id="51d41-159">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="51d41-160">Después de crear grupos de distribución y grupos de seguridad habilitados para correo en el centro de administración de Exchange, sus nombres y listas de usuarios aparecen en la página **grupos de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="51d41-160">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="51d41-161">Puede eliminar estos grupos en ambas ubicaciones, pero solamente puede modificarlos en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="51d41-161">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="51d41-162">Los grupos de distribución dinámicos no se muestran en la página **grupos de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="51d41-162">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="51d41-163">Los grupos de SharePoint se crean automáticamente al crear una colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="51d41-163">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="51d41-164">Los grupos predeterminados usan los niveles de permisos predeterminados de SharePoint (a veces llamados roles de SharePoint) para conceder permisos y acceso a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="51d41-164">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="51d41-165">Para obtener más información, vea [grupos de SharePoint predeterminados en SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="51d41-165">For more information, see [Default SharePoint groups in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="51d41-166">¿En qué se diferencia un grupo de seguridad de los grupos de seguridad creados en SharePoint?</span><span class="sxs-lookup"><span data-stu-id="51d41-166">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="51d41-167">Los grupos de seguridad se pueden usar con SharePoint, Exchange, MDM, Windows y más.</span><span class="sxs-lookup"><span data-stu-id="51d41-167">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="51d41-168">Un grupo de seguridad que se crea en SharePoint solo es reconocido por esa colección de sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="51d41-168">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="51d41-169">¿Es necesario usar grupos de seguridad para que mi organización sea segura?</span><span class="sxs-lookup"><span data-stu-id="51d41-169">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="51d41-170">No.</span><span class="sxs-lookup"><span data-stu-id="51d41-170">No.</span></span> <span data-ttu-id="51d41-171">Esto es sólo una forma más de administrar la seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="51d41-171">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="51d41-172">Siempre puede conceder permisos de usuario y acceso a los sitios de forma individual.</span><span class="sxs-lookup"><span data-stu-id="51d41-172">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="51d41-173">Pero con los grupos de seguridad, puede administrar fácilmente grupos de usuarios más grandes.</span><span class="sxs-lookup"><span data-stu-id="51d41-173">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="51d41-174">¿Se puede enviar correo electrónico a un grupo de seguridad?</span><span class="sxs-lookup"><span data-stu-id="51d41-174">Can I send email to a security group?</span></span>

<span data-ttu-id="51d41-175">Sí.</span><span class="sxs-lookup"><span data-stu-id="51d41-175">Yes.</span></span> <span data-ttu-id="51d41-176">Pero si quiere usar grupos para el correo electrónico y la colaboración, le recomendamos que [cree un grupo de 365 de Microsoft](../create-groups/create-groups.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="51d41-176">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
