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
ms.openlocfilehash: 26b431a65035f2546bb44af2ecf31bfd327e53b6
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255240"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="0c42c-103">Crear, editar o eliminar un grupo de seguridad en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c42c-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="0c42c-104">En la página Office 365 **grupos** , puede crear grupos de cuentas de usuario que puede usar para asignar los mismos permisos en SharePoint Online y en CRM Online.</span><span class="sxs-lookup"><span data-stu-id="0c42c-104">On the Office 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="0c42c-105">Por ejemplo, un administrador puede crear un grupo de seguridad para conceder acceso a un determinado grupo de personas a un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0c42c-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="0c42c-106">Solo los administradores globales y de administración de usuarios tienen permisos para crear, editar o eliminar grupos de seguridad; para obtener más información acerca de los roles de administrador, vea [asignación de roles de administrador](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0c42c-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="0c42c-107">También hay [Grupos de Exchange Online y SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) que puede usar para enviar correo electrónico o asignar permisos a un grupo de usuarios y [Grupos de Exchange Online y SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) que conceden a los usuarios permisos y acceso a sitios y colecciones de sitios.</span><span class="sxs-lookup"><span data-stu-id="0c42c-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="0c42c-108">¿Tiene previsto usar buzones del sitio?</span><span class="sxs-lookup"><span data-stu-id="0c42c-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="0c42c-109">Todos los usuarios que se agreguen a un sitio de SharePoint mediante un grupo de seguridad en lugar de individualmente podrán usar únicamente el buzón del sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0c42c-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="0c42c-110">No podrán acceder al buzón del sitio de Outlook.</span><span class="sxs-lookup"><span data-stu-id="0c42c-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="0c42c-111">Para obtener más información, vea [usar los grupos de Office 365 en lugar de los buzones del sitio](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c42c-111">For more information, see [Use Office 365 Groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="0c42c-112">Administración de grupos de seguridad en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="0c42c-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="0c42c-113">Agregar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="0c42c-113">Add a security group</span></span>

1. <span data-ttu-id="0c42c-114">En el centro de administración, vaya a **la** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a> página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="0c42c-114">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="0c42c-115">En la página **grupos** , seleccione **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="0c42c-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="0c42c-116">En la página **elegir un tipo de grupo** , elija **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="0c42c-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="0c42c-117">Siga los pasos para completar la creación del grupo.</span><span class="sxs-lookup"><span data-stu-id="0c42c-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="0c42c-118">Adición de miembros a un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="0c42c-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="0c42c-119">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="0c42c-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="0c42c-120">Seleccione el nombre del grupo de seguridad en la página **grupos** y, en la pestaña **miembros** , seleccione **Ver todos y administrar miembros**.</span><span class="sxs-lookup"><span data-stu-id="0c42c-120">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="0c42c-121">En el panel de grupo, seleccione **Agregar miembros** y elija la persona de la lista o escriba el nombre de la persona que desea agregar en el cuadro de **búsqueda** y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0c42c-121">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="0c42c-122">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="0c42c-122">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0c42c-123">Seleccione el nombre del grupo de seguridad en la página **grupos** y, a continuación, seleccione **Editar** junto a **miembros**.</span><span class="sxs-lookup"><span data-stu-id="0c42c-123">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="0c42c-124">En el panel de grupo, seleccione **Agregar miembros** y elija la persona de la lista o escriba el nombre de la persona que desea agregar en el cuadro de **búsqueda** y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0c42c-124">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="0c42c-125">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="0c42c-125">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="0c42c-126">Seleccione el nombre del grupo de seguridad en la página **grupos** y, a continuación, seleccione **Editar** junto a **miembros**.</span><span class="sxs-lookup"><span data-stu-id="0c42c-126">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="0c42c-127">En el panel de grupo, seleccione **Agregar miembros** y elija la persona de la lista o escriba el nombre de la persona que desea agregar en el cuadro de **búsqueda** y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0c42c-127">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="0c42c-128">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="0c42c-128">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="0c42c-129">Editar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="0c42c-129">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="0c42c-130">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="0c42c-130">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="0c42c-131">En el centro de administración, vaya a **la** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a> página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="0c42c-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="0c42c-132">En la página **grupos** , seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="0c42c-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0c42c-133">En el panel Configuración, seleccione la pestaña **General** o la pestaña **miembros** para editar los detalles o miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="0c42c-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0c42c-134">En el centro de administración, vaya a **la** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a> página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="0c42c-134">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="0c42c-135">En la página **grupos** , seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="0c42c-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0c42c-136">En el panel grupo de seguridad, seleccione **Editar** junto a **nombre** o en la ficha **miembros** para editar los detalles o los miembros de un grupo.</span><span class="sxs-lookup"><span data-stu-id="0c42c-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="0c42c-137">Después de realizar los cambios, seleccione **Guardar** \> **cierre**.</span><span class="sxs-lookup"><span data-stu-id="0c42c-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0c42c-138">En el centro de administración, vaya a **la** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a> página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="0c42c-138">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="0c42c-139">En la página **grupos** , seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="0c42c-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0c42c-140">En el panel grupo de seguridad, seleccione **Editar** junto a **nombre** o en la ficha **miembros** para editar los detalles o los miembros de un grupo.</span><span class="sxs-lookup"><span data-stu-id="0c42c-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="0c42c-141">Después de realizar los cambios, seleccione **Guardar** \> **cierre**.</span><span class="sxs-lookup"><span data-stu-id="0c42c-141">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="0c42c-142">Eliminar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="0c42c-142">Delete a security group</span></span>

1. <span data-ttu-id="0c42c-143">En el centro de administración, vaya a **la** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a> página grupos de grupos.</span><span class="sxs-lookup"><span data-stu-id="0c42c-143">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="0c42c-144">En la página **grupos** , seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="0c42c-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0c42c-145">Seleccione **Eliminar grupo** (icono de wasetbin) y, a continuación, confirme seleccionando **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0c42c-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="0c42c-146">Seleccione **cerrar** una vez que se elimine el grupo.</span><span class="sxs-lookup"><span data-stu-id="0c42c-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="0c42c-147">Grupos de Exchange Online y SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0c42c-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="0c42c-148">Si desea crear grupos de usuarios para que pueda enviarles un correo electrónico a todos al mismo tiempo, puede hacerlo en el centro de administración de Exchange visitando los **grupos**de **destinatarios** \> de **Administración** \> de **Exchange** \> .</span><span class="sxs-lookup"><span data-stu-id="0c42c-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="0c42c-149">A continuación, \*\*\*\*![seleccione Agregar](../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)nuevo y seleccione el tipo de grupo que desea crear:</span><span class="sxs-lookup"><span data-stu-id="0c42c-149">Next, select **New**![Add](../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="0c42c-150">**Grupo de distribución**: se usa para distribuir mensajes a un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="0c42c-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="0c42c-151">También se denomina Grupo de *distribución habilitado para correo*, o bien, en Office 365, una *lista de distribución*.</span><span class="sxs-lookup"><span data-stu-id="0c42c-151">It's also called a  *mail-enabled distribution group*, or, in Office 365, a  *distribution list*.</span></span> <span data-ttu-id="0c42c-152">Para más información, vea [Administrar grupos de distribución](https://technet.microsoft.com/library/bb124513.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c42c-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="0c42c-153">**Grupo de seguridad**: se puede usar para distribuir mensajes a un grupo de usuarios o para conceder permisos de acceso a recursos.</span><span class="sxs-lookup"><span data-stu-id="0c42c-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="0c42c-154">Este grupo también se denomina *grupo de seguridad habilitado para correo*.</span><span class="sxs-lookup"><span data-stu-id="0c42c-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="0c42c-155">Para obtener más información, consulte [Administrar grupos de seguridad habilitados para correo](https://technet.microsoft.com/library/bb123521.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c42c-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="0c42c-156">**Grupo de distribución dinámico**: un tipo de grupo de distribución cuya lista de destinatarios se vuelve a calcular cada vez que se envía un mensaje en función de filtros y condiciones definidos.</span><span class="sxs-lookup"><span data-stu-id="0c42c-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="0c42c-157">Para obtener más información, vea [Administrar grupos de distribución dinámica](https://technet.microsoft.com/library/bb123722.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c42c-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="0c42c-p107">Tras crear los grupos de distribución y los grupos de seguridad habilitados para correo electrónico en el Centro de administración de Exchange, sus nombres y listas de usuarios aparecerán en la página **Grupos de seguridad** de Office 365. Puede eliminar estos grupos en ambas ubicaciones, pero solamente puede modificarlos en el Centro de administración de Exchange. Los grupos de distribución dinámicos no aparecen en la página **Grupos de seguridad** de Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c42c-p107">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the Office 365 **Security groups** page. You can delete these groups in both locations, but you can edit them only in the Exchange admin center. Dynamic distribution groups don't show up on the Office 365 **Security groups** page.</span></span> 
  
 <span data-ttu-id="0c42c-161">Los grupos de SharePoint se crean automáticamente al crear una colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="0c42c-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="0c42c-162">Los grupos predeterminados usan los niveles de permisos predeterminados de SharePoint (a veces llamados roles de SharePoint) para conceder permisos y acceso a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0c42c-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="0c42c-163">Para obtener más información, vea [grupos de SharePoint predeterminados en SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c42c-163">For more information, see [Default SharePoint groups in SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="0c42c-164">¿En qué se diferencia un grupo de seguridad de los grupos de seguridad creados en SharePoint?</span><span class="sxs-lookup"><span data-stu-id="0c42c-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="0c42c-165">Los grupos de seguridad se pueden usar con SharePoint, Exchange, MDM, Windows y más.</span><span class="sxs-lookup"><span data-stu-id="0c42c-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="0c42c-166">Un grupo de seguridad que se crea en SharePoint solo es reconocido por esa colección de sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0c42c-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="0c42c-167">¿Es necesario usar grupos de seguridad para que mi organización sea segura?</span><span class="sxs-lookup"><span data-stu-id="0c42c-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="0c42c-168">No.</span><span class="sxs-lookup"><span data-stu-id="0c42c-168">No.</span></span> <span data-ttu-id="0c42c-169">Esto es sólo una forma más de administrar la seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="0c42c-169">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="0c42c-170">Siempre puede conceder permisos de usuario y acceso a los sitios de forma individual.</span><span class="sxs-lookup"><span data-stu-id="0c42c-170">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="0c42c-171">Pero con los grupos de seguridad, puede administrar fácilmente grupos de usuarios más grandes.</span><span class="sxs-lookup"><span data-stu-id="0c42c-171">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="0c42c-172">¿Se puede enviar correo electrónico a un grupo de seguridad?</span><span class="sxs-lookup"><span data-stu-id="0c42c-172">Can I send email to a security group?</span></span>

<span data-ttu-id="0c42c-173">Sí.</span><span class="sxs-lookup"><span data-stu-id="0c42c-173">Yes.</span></span> <span data-ttu-id="0c42c-174">Pero si quiere usar grupos para el correo electrónico y la colaboración, le recomendamos que [cree un grupo de Office 365](../create-groups/create-groups.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0c42c-174">But if you want to use groups for email and collaboration, we recommend that you [create an Office 365 group](../create-groups/create-groups.md) instead.</span></span> 
  