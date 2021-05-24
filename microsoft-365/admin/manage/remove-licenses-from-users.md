---
title: Cancelar la asignación de licencias a usuarios
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: El método que use para desasignación de licencias de productos depende de si desasigna licencias de usuarios específicos o de un producto específico.
ms.date: 07/01/2020
ms.openlocfilehash: f7624432590a5731b57c45c25e7e7dc458a5b8f5
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623594"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="ee302-103">Cancelar la asignación de licencias a usuarios</span><span class="sxs-lookup"><span data-stu-id="ee302-103">Unassign licenses from users</span></span>

<span data-ttu-id="ee302-104">Puede desasignación de licencias de usuarios en la **página Usuarios** activos o en la **página Licencias.**</span><span class="sxs-lookup"><span data-stu-id="ee302-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="ee302-105">El método que use depende de si desea desasignación de licencias de productos de usuarios específicos o desasignación de licencias de usuarios de un producto específico.</span><span class="sxs-lookup"><span data-stu-id="ee302-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="ee302-106">Como administrador, no puede asignar o cancelar la asignación de licencias para una suscripción de compra de autoservicio adquirida por un usuario de su organización.</span><span class="sxs-lookup"><span data-stu-id="ee302-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="ee302-107">Puede [apoderarse de una suscripción de compra de autoservicio](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription) y, a continuación, asignar o cancelar la asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="ee302-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ee302-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="ee302-108">Before you begin</span></span>

- <span data-ttu-id="ee302-109">Debe ser un administrador global, de licencia y de usuario para desasignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="ee302-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="ee302-110">Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ee302-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="ee302-111">Puede [quitar licencias de cuentas de usuario con PowerShell de Office 365](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ee302-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="ee302-112">También puede eliminar [cuentas de usuario a](../add-users/delete-a-user.md) las que se asignó una licencia para que su licencia esté disponible para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="ee302-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="ee302-113">Al eliminar una cuenta de usuario, su licencia está disponible inmediatamente para asignarla a otra persona.</span><span class="sxs-lookup"><span data-stu-id="ee302-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="ee302-114">Usar la página Licencias para desasignación de licencias</span><span class="sxs-lookup"><span data-stu-id="ee302-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="ee302-115">Al usar la página **Licencias** para desasignar licencias, se desasigna licencias para un producto específico para un máximo de 20 usuarios.</span><span class="sxs-lookup"><span data-stu-id="ee302-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ee302-116">En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="ee302-116">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="ee302-117">En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="ee302-117">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="ee302-118">En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="ee302-118">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="ee302-119">Seleccione el producto para el que desea desasignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="ee302-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="ee302-120">Seleccione los usuarios para los que desea desasignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="ee302-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="ee302-121">Seleccione **Unassign licenses**.</span><span class="sxs-lookup"><span data-stu-id="ee302-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="ee302-122">En el **cuadro Unassign licenses,** seleccione **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="ee302-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="ee302-123">Usar la página Usuarios activos para desasignación de licencias</span><span class="sxs-lookup"><span data-stu-id="ee302-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="ee302-124">Al usar la página **Usuarios activos** para desasignación de licencias, se desasigna licencias de productos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ee302-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="ee302-125">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="ee302-125">Unassign licenses from one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ee302-126">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="ee302-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="ee302-127">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="ee302-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="ee302-128">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="ee302-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="ee302-129">Seleccione la fila del usuario para el que desea desasignación de una licencia.</span><span class="sxs-lookup"><span data-stu-id="ee302-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="ee302-130">En el panel derecho, seleccione **licencias y aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="ee302-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="ee302-131">Expanda la **sección Licencias,** desactive los cuadros de las licencias que desea desasignación y, a continuación, **seleccione Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="ee302-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

### <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="ee302-132">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="ee302-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ee302-133">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="ee302-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="ee302-134">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="ee302-134">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="ee302-135">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="ee302-135">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="ee302-136">Seleccione los círculos junto a los nombres de los usuarios para los que desea desasignar licencias.</span><span class="sxs-lookup"><span data-stu-id="ee302-136">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="ee302-137">En la parte superior, seleccione los tres puntos (Más acciones) y, después, seleccione **Administrar licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="ee302-137">At the top, select the three dots (more actions), then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="ee302-138">En el panel **administrar licencias de producto**, seleccione **reemplazar las asignaciones de licencias de producto existentes** \> **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ee302-138">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="ee302-139">En la parte inferior del panel **Reemplazar** productos **existentes,** active la casilla Quitar todas las licencias de productos de los usuarios seleccionados y, a continuación, **seleccione Reemplazar** \> **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ee302-139">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="ee302-140">¿Qué sucede con los datos de un usuario al quitar su licencia?</span><span class="sxs-lookup"><span data-stu-id="ee302-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="ee302-141">Cuando se quita una licencia de un usuario, Exchange datos en línea asociados con esa cuenta se mantienen durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="ee302-141">When a license is removed from a user, Exchange online data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="ee302-142">Después del período de gracia de 30 días, los datos se eliminan y no se pueden recuperar.</span><span class="sxs-lookup"><span data-stu-id="ee302-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="ee302-143">Los archivos guardados en OneDrive para la Empresa no se eliminan a menos que el usuario se elimine del centro de administración de Microsoft 365 o se quite a través de la sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ee302-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="ee302-144">Para obtener más información, [vea OneDrive retención y eliminación.](/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="ee302-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="ee302-145">Cuando se quita la licencia, el buzón del usuario ya no se puede buscar mediante una herramienta de exhibición de documentos electrónicos como búsqueda de contenido o Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ee302-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="ee302-146">Para obtener más información, vea "Buscar buzones desconectados o sin licencia" en Búsqueda de contenido [en Microsoft 365](../../compliance/content-search.md).</span><span class="sxs-lookup"><span data-stu-id="ee302-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md).</span></span>
- <span data-ttu-id="ee302-147">Si tiene una suscripción Enterprise, como Office 365 Enterprise E3, Exchange Online permite conservar los datos del buzón de una cuenta de usuario eliminada mediante buzones [inactivos.](../../compliance/inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="ee302-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="ee302-148">Para obtener más información, vea [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="ee302-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="ee302-149">Para obtener información sobre cómo bloquear el acceso de un usuario Microsoft 365 datos después de quitar su licencia y cómo obtener acceso a los datos después, vea [Remove a former employee](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="ee302-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="ee302-150">Si quitas la licencia de un usuario y aún tienen Office aplicaciones instaladas, verán Errores de activación y producto sin licencia en [Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) cuando usen Office aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ee302-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ee302-151">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ee302-151">Next steps</span></span>

<span data-ttu-id="ee302-152">Si no va a reasignar las licencias no [usadas](../../managed-desktop/get-started/assign-licenses.md)a otros usuarios, considere la posibilidad de quitar las licencias de la suscripción para que no pague más licencias de las que necesita. [](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="ee302-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="ee302-153">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="ee302-153">Related content</span></span>

<span data-ttu-id="ee302-154">[Quitar licencias de la suscripción](../../commerce/licenses/buy-licenses.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ee302-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="ee302-155">[Asignar licencias a los usuarios](assign-licenses-to-users.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ee302-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="ee302-156">[Comprender las suscripciones y licencias en Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ee302-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>
