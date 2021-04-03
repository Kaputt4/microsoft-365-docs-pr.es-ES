---
title: Crear, editar o eliminar un grupo de seguridad en el Centro de administración de Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Aprenda a crear, editar o eliminar un grupo de seguridad.
ms.openlocfilehash: 03e391727f9a61b1fc8e819e92d5a119017c38e0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579343"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="0c71c-103">Crear, editar o eliminar un grupo de seguridad en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c71c-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="0c71c-104">En la página Grupos  de Microsoft 365, puede crear grupos de cuentas de usuario que puede usar para asignar los mismos permisos en SharePoint Online y CRM Online.</span><span class="sxs-lookup"><span data-stu-id="0c71c-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="0c71c-105">Por ejemplo, un administrador puede crear un grupo de seguridad para conceder a un determinado grupo de personas acceso a un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0c71c-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="0c71c-106">Solo los administradores de administración global y de usuario tienen permisos para crear, editar o eliminar grupos de seguridad; para obtener más información acerca de los roles de administrador, vea [Assigning admin roles](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0c71c-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="0c71c-107">También hay [Grupos de Exchange Online y SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) que puede usar para enviar correo electrónico o asignar permisos a un grupo de usuarios y [Grupos de Exchange Online y SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) que conceden a los usuarios permisos y acceso a sitios y colecciones de sitios.</span><span class="sxs-lookup"><span data-stu-id="0c71c-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="0c71c-108">¿Tiene previsto usar buzones del sitio?</span><span class="sxs-lookup"><span data-stu-id="0c71c-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="0c71c-109">Todos los usuarios que se agreguen a un sitio de SharePoint mediante un grupo de seguridad en lugar de individualmente podrán usar únicamente el buzón del sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0c71c-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="0c71c-110">No podrán acceder al buzón del sitio de Outlook.</span><span class="sxs-lookup"><span data-stu-id="0c71c-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="0c71c-111">Para obtener más información, vea [Usar grupos de Microsoft 365 en lugar de buzones de sitio](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span><span class="sxs-lookup"><span data-stu-id="0c71c-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="0c71c-112">Administrar grupos de seguridad en el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="0c71c-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="0c71c-113">Agregar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="0c71c-113">Add a security group</span></span>

1. <span data-ttu-id="0c71c-114">En el Centro de administración de Microsoft 365, vaya a la **página Grupos.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="0c71c-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="0c71c-115">En la **página Grupos,** seleccione **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="0c71c-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="0c71c-116">En la **página Elegir un tipo de grupo,** elija **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="0c71c-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="0c71c-117">Siga los pasos para completar la creación del grupo.</span><span class="sxs-lookup"><span data-stu-id="0c71c-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="0c71c-118">Agregar miembros a un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="0c71c-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="0c71c-119">Seleccione el nombre del grupo de seguridad en la **página Grupos** y, en la pestaña **Miembros,** seleccione **Ver todos y administrar miembros.**</span><span class="sxs-lookup"><span data-stu-id="0c71c-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="0c71c-120">En el panel  de grupos, seleccione Agregar miembros y elija la persona de la  lista o escriba el nombre de la persona que desea agregar en el cuadro Búsqueda y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0c71c-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="0c71c-121">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="0c71c-121">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0c71c-122">Seleccione el nombre del grupo de seguridad en la **página Grupos** y, a continuación, **seleccione Editar** junto a **Miembros**.</span><span class="sxs-lookup"><span data-stu-id="0c71c-122">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="0c71c-123">En el panel  de grupos, seleccione Agregar miembros y elija la persona de la  lista o escriba el nombre de la persona que desea agregar en el cuadro Búsqueda y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0c71c-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="0c71c-124">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="0c71c-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="0c71c-125">Seleccione el nombre del grupo de seguridad en la **página Grupos** y, a continuación, **seleccione Editar** junto a **Miembros**.</span><span class="sxs-lookup"><span data-stu-id="0c71c-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="0c71c-126">En el panel  de grupos, seleccione Agregar miembros y elija la persona de la  lista o escriba el nombre de la persona que desea agregar en el cuadro Búsqueda y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0c71c-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="0c71c-127">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="0c71c-127">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="0c71c-128">Editar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="0c71c-128">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0c71c-129">En el Centro de administración, vaya a la **página Grupos.** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="0c71c-129">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="0c71c-130">En la **página** Grupos, seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="0c71c-130">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0c71c-131">En el panel de configuración, seleccione la **pestaña General** o la **pestaña** Miembros para editar los detalles del grupo o los miembros.</span><span class="sxs-lookup"><span data-stu-id="0c71c-131">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0c71c-132">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Centro de administración,</a>vaya a la **página** \> **Grupos.**</span><span class="sxs-lookup"><span data-stu-id="0c71c-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="0c71c-133">En la **página** Grupos, seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="0c71c-133">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0c71c-134">En el panel grupo de seguridad,  seleccione **Editar** junto a la pestaña **Nombre** o Miembros para editar los detalles del grupo o los miembros.</span><span class="sxs-lookup"><span data-stu-id="0c71c-134">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="0c71c-135">Después de realizar los cambios, seleccione **Guardar** \> **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0c71c-135">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0c71c-136">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración,</a>vaya a la **página** \> **Grupos.**</span><span class="sxs-lookup"><span data-stu-id="0c71c-136">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="0c71c-137">En la **página** Grupos, seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="0c71c-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0c71c-138">En el panel grupo de seguridad,  seleccione **Editar** junto a la pestaña **Nombre** o Miembros para editar los detalles del grupo o los miembros.</span><span class="sxs-lookup"><span data-stu-id="0c71c-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="0c71c-139">Después de realizar los cambios, seleccione **Guardar** > **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0c71c-139">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="0c71c-140">Eliminar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="0c71c-140">Delete a security group</span></span>

1. <span data-ttu-id="0c71c-141">En el Centro de administración, vaya a la **página Grupos.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="0c71c-141">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="0c71c-142">En la **página** Grupos, seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="0c71c-142">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0c71c-143">Seleccione **Eliminar grupo** (icono wasetbin) y, a continuación, confirme **seleccionando Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0c71c-143">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="0c71c-144">Seleccione **Cerrar una** vez eliminado el grupo.</span><span class="sxs-lookup"><span data-stu-id="0c71c-144">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="0c71c-145">Grupos de Exchange Online y SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0c71c-145">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="0c71c-146">Si desea crear grupos de usuarios para que pueda enviarles correo electrónico a todos al mismo  tiempo, puede hacerlo en el Centro de administración de Exchange yendo a Grupos de destinatarios de Exchange de \>  \>  \> **administración.**</span><span class="sxs-lookup"><span data-stu-id="0c71c-146">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="0c71c-147">A continuación, **seleccione Nuevo** ![ agregar y seleccione el tipo de grupo que desea ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) crear:</span><span class="sxs-lookup"><span data-stu-id="0c71c-147">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="0c71c-148">**Grupo de distribución**: se usa para distribuir mensajes a un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="0c71c-148">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="0c71c-149">También se denomina grupo de *distribución habilitado* para correo o, una lista *de distribución.*</span><span class="sxs-lookup"><span data-stu-id="0c71c-149">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="0c71c-150">Para más información, vea [Administrar grupos de distribución](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="0c71c-150">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="0c71c-151">**Grupo de seguridad**: se puede usar para distribuir mensajes a un grupo de usuarios o para conceder permisos de acceso a recursos.</span><span class="sxs-lookup"><span data-stu-id="0c71c-151">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="0c71c-152">Este grupo también se denomina grupo *de seguridad habilitado para correo*.</span><span class="sxs-lookup"><span data-stu-id="0c71c-152">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="0c71c-153">Para obtener más información, consulte [Administrar grupos de seguridad habilitados para correo](/Exchange/recipients/mail-enabled-security-groups).</span><span class="sxs-lookup"><span data-stu-id="0c71c-153">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="0c71c-154">**Grupo de distribución dinámico**: un tipo de grupo de distribución cuya lista de destinatarios se vuelve a calcular cada vez que se envía un mensaje en función de filtros y condiciones definidos.</span><span class="sxs-lookup"><span data-stu-id="0c71c-154">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="0c71c-155">Para obtener más información, vea [Administrar grupos de distribución dinámica](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="0c71c-155">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="0c71c-156">Después de crear grupos de distribución y grupos de seguridad habilitados para correo en el Centro de administración de Exchange, sus nombres y listas de usuarios aparecen en la **página Grupos de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="0c71c-156">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="0c71c-157">Puede eliminar estos grupos en ambas ubicaciones, pero solamente puede modificarlos en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0c71c-157">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="0c71c-158">Los grupos de distribución dinámicos no se muestran en la **página Grupos de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="0c71c-158">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="0c71c-159">Los grupos de SharePoint se crean automáticamente al crear una colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="0c71c-159">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="0c71c-160">Los grupos predeterminados usan los niveles de permisos predeterminados de SharePoint (a veces llamados roles de SharePoint) para conceder permisos y acceso a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0c71c-160">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="0c71c-161">Para obtener más información, vea [Grupos predeterminados de SharePoint en SharePoint Online](/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="0c71c-161">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="0c71c-162">¿En qué se diferencia un grupo de seguridad de los grupos de seguridad que creo en SharePoint?</span><span class="sxs-lookup"><span data-stu-id="0c71c-162">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="0c71c-163">Los grupos de seguridad se pueden usar con SharePoint, Exchange, MDM, Windows y mucho más.</span><span class="sxs-lookup"><span data-stu-id="0c71c-163">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="0c71c-164">Un grupo de seguridad que cree en SharePoint solo lo reconoce esa colección de sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0c71c-164">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="0c71c-165">¿Tengo que usar grupos de seguridad para que mi organización sea segura?</span><span class="sxs-lookup"><span data-stu-id="0c71c-165">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="0c71c-166">No.</span><span class="sxs-lookup"><span data-stu-id="0c71c-166">No.</span></span> <span data-ttu-id="0c71c-167">Esta es solo una forma más de administrar la seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="0c71c-167">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="0c71c-168">Siempre puede conceder permisos de usuario y acceso a los sitios individualmente.</span><span class="sxs-lookup"><span data-stu-id="0c71c-168">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="0c71c-169">Pero con los grupos de seguridad, puede administrar fácilmente grupos de usuarios más grandes.</span><span class="sxs-lookup"><span data-stu-id="0c71c-169">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="0c71c-170">¿Puedo enviar correo electrónico a un grupo de seguridad?</span><span class="sxs-lookup"><span data-stu-id="0c71c-170">Can I send email to a security group?</span></span>

<span data-ttu-id="0c71c-171">Sí.</span><span class="sxs-lookup"><span data-stu-id="0c71c-171">Yes.</span></span> <span data-ttu-id="0c71c-172">Pero si quieres usar grupos para correo electrónico y colaboración, te recomendamos que crees un grupo [de Microsoft 365 en](../create-groups/create-groups.md) su lugar.</span><span class="sxs-lookup"><span data-stu-id="0c71c-172">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
