---
title: Crear, editar o eliminar un grupo de seguridad en el Centro Microsoft 365 administración
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
ms.openlocfilehash: 8f76b5fa803ea43e53e89cf6479eb7572a2857c2
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537600"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="94b44-103">Crear, editar o eliminar un grupo de seguridad en el Centro Microsoft 365 administración</span><span class="sxs-lookup"><span data-stu-id="94b44-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="94b44-104">En la página Microsoft 365 **grupos,** puede crear grupos de cuentas de usuario que pueda usar para asignar los mismos permisos en SharePoint Online y CRM Online.</span><span class="sxs-lookup"><span data-stu-id="94b44-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="94b44-105">Por ejemplo, un administrador puede crear un grupo de seguridad para conceder a un determinado grupo de personas acceso a un SharePoint web.</span><span class="sxs-lookup"><span data-stu-id="94b44-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="94b44-106">Solo los administradores de administración global y de usuario tienen permisos para crear, editar o eliminar grupos de seguridad; para obtener más información acerca de los roles de administrador, vea [Assigning admin roles](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="94b44-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="94b44-107">También hay [Grupos de Exchange Online y SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) que puede usar para enviar correo electrónico o asignar permisos a un grupo de usuarios y [Grupos de Exchange Online y SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) que conceden a los usuarios permisos y acceso a sitios y colecciones de sitios.</span><span class="sxs-lookup"><span data-stu-id="94b44-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="94b44-108">¿Tiene previsto usar buzones del sitio?</span><span class="sxs-lookup"><span data-stu-id="94b44-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="94b44-109">Todos los usuarios que se agreguen a un sitio de SharePoint mediante un grupo de seguridad en lugar de individualmente podrán usar únicamente el buzón del sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="94b44-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="94b44-110">No podrán acceder al buzón del sitio de Outlook.</span><span class="sxs-lookup"><span data-stu-id="94b44-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="94b44-111">Para obtener más información, vea [Use Microsoft 365 Groups en lugar de Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span><span class="sxs-lookup"><span data-stu-id="94b44-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="94b44-112">Administrar grupos de seguridad en el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="94b44-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="94b44-113">Agregar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="94b44-113">Add a security group</span></span>

1. <span data-ttu-id="94b44-114">En el centro Microsoft 365 administración, vaya a la página **Grupos.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="94b44-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="94b44-115">En la **página Grupos,** seleccione **Agregar un grupo**.</span><span class="sxs-lookup"><span data-stu-id="94b44-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="94b44-116">En la **página Elegir un tipo de grupo,** elija **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="94b44-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="94b44-117">Siga los pasos para completar la creación del grupo.</span><span class="sxs-lookup"><span data-stu-id="94b44-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="94b44-118">Agregar miembros a un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="94b44-118">Add members to a security group</span></span>
    
1. <span data-ttu-id="94b44-119">Seleccione el nombre del grupo de seguridad en la **página Grupos** y, en la pestaña **Miembros,** seleccione **Ver todos y administrar miembros.**</span><span class="sxs-lookup"><span data-stu-id="94b44-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="94b44-120">En el panel  de grupos, seleccione Agregar miembros y elija la persona de la  lista o escriba el nombre de la persona que desea agregar en el cuadro Búsqueda y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="94b44-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="94b44-121">Para quitar miembros, seleccione la X junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="94b44-121">To remove members, select the X next to their name.</span></span> 
  
### <a name="edit-a-security-group"></a><span data-ttu-id="94b44-122">Editar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="94b44-122">Edit a security group</span></span>

1. <span data-ttu-id="94b44-123">En el Centro de administración, vaya a la **página Grupos.** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="94b44-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="94b44-124">En la **página** Grupos, seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="94b44-124">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="94b44-125">En el panel de configuración, seleccione la **pestaña General** o la **pestaña** Miembros para editar los detalles del grupo o los miembros.</span><span class="sxs-lookup"><span data-stu-id="94b44-125">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

### <a name="delete-a-security-group"></a><span data-ttu-id="94b44-126">Eliminar un grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="94b44-126">Delete a security group</span></span>

1. <span data-ttu-id="94b44-127">En el Centro de administración, vaya a la **página Grupos.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="94b44-127">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="94b44-128">En la **página** Grupos, seleccione el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="94b44-128">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="94b44-129">Seleccione **Eliminar grupo** (icono wasetbin) y, a continuación, confirme **seleccionando Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="94b44-129">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="94b44-130">Seleccione **Cerrar una** vez eliminado el grupo.</span><span class="sxs-lookup"><span data-stu-id="94b44-130">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="94b44-131">Grupos de Exchange Online y SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="94b44-131">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="94b44-132">Si desea crear grupos de usuarios para que pueda enviarles correo electrónico a todos al mismo tiempo,  puede hacerlo en el Centro de administración de Exchange yendo Exchange Grupos de destinatarios \>  \>  \> .</span><span class="sxs-lookup"><span data-stu-id="94b44-132">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="94b44-133">A continuación, **seleccione Nuevo** ![ agregar y seleccione el tipo de grupo que desea ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) crear:</span><span class="sxs-lookup"><span data-stu-id="94b44-133">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="94b44-134">**Grupo de distribución**: se usa para distribuir mensajes a un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="94b44-134">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="94b44-135">También se denomina grupo de *distribución habilitado* para correo o, una lista *de distribución.*</span><span class="sxs-lookup"><span data-stu-id="94b44-135">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="94b44-136">Para más información, vea [Administrar grupos de distribución](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="94b44-136">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="94b44-137">**Grupo de seguridad**: se puede usar para distribuir mensajes a un grupo de usuarios o para conceder permisos de acceso a recursos.</span><span class="sxs-lookup"><span data-stu-id="94b44-137">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="94b44-138">Este grupo también se denomina grupo *de seguridad habilitado para correo*.</span><span class="sxs-lookup"><span data-stu-id="94b44-138">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="94b44-139">Para obtener más información, consulte [Administrar grupos de seguridad habilitados para correo](/Exchange/recipients/mail-enabled-security-groups).</span><span class="sxs-lookup"><span data-stu-id="94b44-139">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="94b44-140">**Grupo de distribución dinámico**: un tipo de grupo de distribución cuya lista de destinatarios se vuelve a calcular cada vez que se envía un mensaje en función de filtros y condiciones definidos.</span><span class="sxs-lookup"><span data-stu-id="94b44-140">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="94b44-141">Para obtener más información, vea [Administrar grupos de distribución dinámica](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="94b44-141">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="94b44-142">Después de crear grupos de distribución y grupos de seguridad habilitados para correo en el centro de administración de Exchange, sus nombres y listas de usuarios aparecen en la **página Grupos de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="94b44-142">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="94b44-143">Puede eliminar estos grupos en ambas ubicaciones, pero solamente puede modificarlos en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="94b44-143">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="94b44-144">Los grupos de distribución dinámicos no se muestran en la **página Grupos de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="94b44-144">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="94b44-145">Los grupos de SharePoint se crean automáticamente al crear una colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="94b44-145">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="94b44-146">Los grupos predeterminados usan los niveles de permisos predeterminados de SharePoint (a veces llamados roles de SharePoint) para conceder permisos y acceso a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="94b44-146">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="94b44-147">Para obtener más información, vea [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="94b44-147">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="94b44-148">¿En qué se diferencia un grupo de seguridad de los grupos de seguridad que creo en SharePoint?</span><span class="sxs-lookup"><span data-stu-id="94b44-148">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="94b44-149">Los grupos de seguridad se pueden usar SharePoint, Exchange, MDM, Windows y mucho más.</span><span class="sxs-lookup"><span data-stu-id="94b44-149">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="94b44-150">Un grupo de seguridad que cree en SharePoint solo lo reconoce esa SharePoint de sitios.</span><span class="sxs-lookup"><span data-stu-id="94b44-150">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="94b44-151">¿Tengo que usar grupos de seguridad para que mi organización sea segura?</span><span class="sxs-lookup"><span data-stu-id="94b44-151">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="94b44-152">No.</span><span class="sxs-lookup"><span data-stu-id="94b44-152">No.</span></span> <span data-ttu-id="94b44-153">Esta es solo una forma más de administrar la seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="94b44-153">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="94b44-154">Siempre puede conceder permisos de usuario y acceso a los sitios individualmente.</span><span class="sxs-lookup"><span data-stu-id="94b44-154">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="94b44-155">Pero con los grupos de seguridad, puede administrar fácilmente grupos de usuarios más grandes.</span><span class="sxs-lookup"><span data-stu-id="94b44-155">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="94b44-156">¿Puedo enviar correo electrónico a un grupo de seguridad?</span><span class="sxs-lookup"><span data-stu-id="94b44-156">Can I send email to a security group?</span></span>

<span data-ttu-id="94b44-157">Sí.</span><span class="sxs-lookup"><span data-stu-id="94b44-157">Yes.</span></span> <span data-ttu-id="94b44-158">Pero si desea usar grupos para correo electrónico y colaboración, le recomendamos que cree un grupo Microsoft 365 en su [lugar.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="94b44-158">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
