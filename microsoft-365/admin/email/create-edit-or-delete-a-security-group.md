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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Obtenga información sobre cómo crear, editar o eliminar un grupo de seguridad.
ms.openlocfilehash: c7c8d57037d972cd89dad45358dc5a7aa3fb86e8
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780246"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="207c6-103">Crear, editar o eliminar un grupo de seguridad en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="207c6-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="207c6-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="207c6-104">The admin center is changing.</span></span> <span data-ttu-id="207c6-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="207c6-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="207c6-106">En la página Microsoft 365 **grupos** , puede crear grupos de cuentas de usuario que puede usar para asignar los mismos permisos en SharePoint Online y en CRM Online.</span><span class="sxs-lookup"><span data-stu-id="207c6-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="207c6-107">Por ejemplo, un administrador puede crear un grupo de seguridad para conceder acceso a un determinado grupo de personas a un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="207c6-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="207c6-108">Solo los administradores globales y de administración de usuarios tienen permisos para crear, editar o eliminar grupos de seguridad; para obtener más información acerca de los roles de administrador, vea [asignación de roles de administrador](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="207c6-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="207c6-109">También hay [Grupos de Exchange Online y SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) que puede usar para enviar correo electrónico o asignar permisos a un grupo de usuarios y [Grupos de Exchange Online y SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) que conceden a los usuarios permisos y acceso a sitios y colecciones de sitios.</span><span class="sxs-lookup"><span data-stu-id="207c6-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="207c6-110">¿Tiene previsto usar buzones del sitio?</span><span class="sxs-lookup"><span data-stu-id="207c6-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="207c6-111">Todos los usuarios que se agreguen a un sitio de SharePoint mediante un grupo de seguridad en lugar de individualmente podrán usar únicamente el buzón del sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="207c6-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="207c6-112">No podrán acceder al buzón del sitio de Outlook.</span><span class="sxs-lookup"><span data-stu-id="207c6-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="207c6-113">Para obtener más información, vea [usar grupos de Microsoft 365 en lugar de buzones de sitio](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span><span class="sxs-lookup"><span data-stu-id="207c6-113">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="207c6-114">Administración de grupos de seguridad en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="207c6-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="207c6-115">Agregar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="207c6-115">Add a security group</span></span>

1. <span data-ttu-id="207c6-116">En el centro de administración de Microsoft 365, vaya **a la**página grupos de grupos  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="207c6-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="207c6-117">En la página **grupos** , seleccione **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="207c6-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="207c6-118">En la página **elegir un tipo de grupo** , elija **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="207c6-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="207c6-119">Siga los pasos para completar la creación del grupo.</span><span class="sxs-lookup"><span data-stu-id="207c6-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="207c6-120">Adición de miembros a un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="207c6-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="207c6-121">Seleccione el nombre del grupo de seguridad en la página **grupos** y, en la pestaña **miembros** , seleccione **Ver todos y administrar miembros**.</span><span class="sxs-lookup"><span data-stu-id="207c6-121">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="207c6-122">En el panel de grupo, seleccione **Agregar miembros** y elija la persona de la lista o escriba el nombre de la persona que desea agregar en el cuadro de **búsqueda** y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="207c6-122">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="207c6-123">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="207c6-123">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="207c6-124">Seleccione el nombre del grupo de seguridad en la página **grupos** y, a continuación, seleccione **Editar** junto a **miembros**.</span><span class="sxs-lookup"><span data-stu-id="207c6-124">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="207c6-125">En el panel de grupo, seleccione **Agregar miembros** y elija la persona de la lista o escriba el nombre de la persona que desea agregar en el cuadro de **búsqueda** y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="207c6-125">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="207c6-126">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="207c6-126">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="207c6-127">Seleccione el nombre del grupo de seguridad en la página **grupos** y, a continuación, seleccione **Editar** junto a **miembros**.</span><span class="sxs-lookup"><span data-stu-id="207c6-127">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="207c6-128">En el panel de grupo, seleccione **Agregar miembros** y elija la persona de la lista o escriba el nombre de la persona que desea agregar en el cuadro de **búsqueda** y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="207c6-128">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="207c6-129">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="207c6-129">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="207c6-130">Editar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="207c6-130">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="207c6-131">En el centro de administración, vaya a **la** página grupos de grupos \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="207c6-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="207c6-132">En la página **grupos** , seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="207c6-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="207c6-133">En el panel Configuración, seleccione la pestaña **General** o la pestaña **miembros** para editar los detalles o miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="207c6-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="207c6-134">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a **la** página grupos de grupos \> **Groups** .</span><span class="sxs-lookup"><span data-stu-id="207c6-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="207c6-135">En la página **grupos** , seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="207c6-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="207c6-136">En el panel grupo de seguridad, seleccione **Editar** junto a **nombre** o en la ficha **miembros** para editar los detalles o los miembros de un grupo.</span><span class="sxs-lookup"><span data-stu-id="207c6-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="207c6-137">Después de realizar los cambios, seleccione **Guardar** \> **cierre**.</span><span class="sxs-lookup"><span data-stu-id="207c6-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="207c6-138">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a **la** página grupos de grupos \> **Groups** .</span><span class="sxs-lookup"><span data-stu-id="207c6-138">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="207c6-139">En la página **grupos** , seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="207c6-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="207c6-140">En el panel grupo de seguridad, seleccione **Editar** junto a **nombre** o en la ficha **miembros** para editar los detalles o los miembros de un grupo.</span><span class="sxs-lookup"><span data-stu-id="207c6-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="207c6-141">Después de realizar los cambios, seleccione **Guardar** > **cierre**.</span><span class="sxs-lookup"><span data-stu-id="207c6-141">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="207c6-142">Eliminar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="207c6-142">Delete a security group</span></span>

1. <span data-ttu-id="207c6-143">En el centro de administración, vaya a **la**página grupos de grupos  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="207c6-143">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="207c6-144">En la página **grupos** , seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="207c6-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="207c6-145">Seleccione **Eliminar grupo** (icono de wasetbin) y, a continuación, confirme seleccionando **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="207c6-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="207c6-146">Seleccione **cerrar** una vez que se elimine el grupo.</span><span class="sxs-lookup"><span data-stu-id="207c6-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="207c6-147">Grupos de Exchange Online y SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="207c6-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="207c6-148">Si desea crear grupos de usuarios para que pueda enviarles un correo electrónico a todos al mismo tiempo, puede hacerlo en el centro de administración de Exchange visitando los grupos de **Admin** \> **Exchange** \> **destinatarios** de administración de Exchange \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="207c6-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="207c6-149">A continuación, seleccione Agregar **nuevo** ![ ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) y seleccione el tipo de grupo que desea crear:</span><span class="sxs-lookup"><span data-stu-id="207c6-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="207c6-150">**Grupo de distribución**: se usa para distribuir mensajes a un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="207c6-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="207c6-151">También se denomina *grupo de distribución habilitado para correo*, o bien, *lista de distribución*.</span><span class="sxs-lookup"><span data-stu-id="207c6-151">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="207c6-152">Para más información, vea [Administrar grupos de distribución](https://technet.microsoft.com/library/bb124513.aspx).</span><span class="sxs-lookup"><span data-stu-id="207c6-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="207c6-153">**Grupo de seguridad**: se puede usar para distribuir mensajes a un grupo de usuarios o para conceder permisos de acceso a recursos.</span><span class="sxs-lookup"><span data-stu-id="207c6-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="207c6-154">Este grupo también se denomina *grupo de seguridad habilitado para correo*.</span><span class="sxs-lookup"><span data-stu-id="207c6-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="207c6-155">Para obtener más información, consulte [Administrar grupos de seguridad habilitados para correo](https://technet.microsoft.com/library/bb123521.aspx).</span><span class="sxs-lookup"><span data-stu-id="207c6-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="207c6-156">**Grupo de distribución dinámico**: un tipo de grupo de distribución cuya lista de destinatarios se vuelve a calcular cada vez que se envía un mensaje en función de filtros y condiciones definidos.</span><span class="sxs-lookup"><span data-stu-id="207c6-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="207c6-157">Para obtener más información, vea [Administrar grupos de distribución dinámica](https://technet.microsoft.com/library/bb123722.aspx).</span><span class="sxs-lookup"><span data-stu-id="207c6-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="207c6-158">Después de crear grupos de distribución y grupos de seguridad habilitados para correo en el centro de administración de Exchange, sus nombres y listas de usuarios aparecen en la página **grupos de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="207c6-158">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="207c6-159">Puede eliminar estos grupos en ambas ubicaciones, pero solamente puede modificarlos en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="207c6-159">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="207c6-160">Los grupos de distribución dinámicos no se muestran en la página **grupos de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="207c6-160">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="207c6-161">Los grupos de SharePoint se crean automáticamente al crear una colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="207c6-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="207c6-162">Los grupos predeterminados usan los niveles de permisos predeterminados de SharePoint (a veces llamados roles de SharePoint) para conceder permisos y acceso a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="207c6-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="207c6-163">Para obtener más información, vea [grupos de SharePoint predeterminados en SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="207c6-163">For more information, see [Default SharePoint groups in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="207c6-164">¿En qué se diferencia un grupo de seguridad de los grupos de seguridad creados en SharePoint?</span><span class="sxs-lookup"><span data-stu-id="207c6-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="207c6-165">Los grupos de seguridad se pueden usar con SharePoint, Exchange, MDM, Windows y más.</span><span class="sxs-lookup"><span data-stu-id="207c6-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="207c6-166">Un grupo de seguridad que se crea en SharePoint solo es reconocido por esa colección de sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="207c6-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="207c6-167">¿Es necesario usar grupos de seguridad para que mi organización sea segura?</span><span class="sxs-lookup"><span data-stu-id="207c6-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="207c6-168">No.</span><span class="sxs-lookup"><span data-stu-id="207c6-168">No.</span></span> <span data-ttu-id="207c6-169">Esto es sólo una forma más de administrar la seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="207c6-169">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="207c6-170">Siempre puede conceder permisos de usuario y acceso a los sitios de forma individual.</span><span class="sxs-lookup"><span data-stu-id="207c6-170">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="207c6-171">Pero con los grupos de seguridad, puede administrar fácilmente grupos de usuarios más grandes.</span><span class="sxs-lookup"><span data-stu-id="207c6-171">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="207c6-172">¿Se puede enviar correo electrónico a un grupo de seguridad?</span><span class="sxs-lookup"><span data-stu-id="207c6-172">Can I send email to a security group?</span></span>

<span data-ttu-id="207c6-173">Sí.</span><span class="sxs-lookup"><span data-stu-id="207c6-173">Yes.</span></span> <span data-ttu-id="207c6-174">Pero si quiere usar grupos para el correo electrónico y la colaboración, le recomendamos que [cree un grupo de 365 de Microsoft](../create-groups/create-groups.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="207c6-174">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
