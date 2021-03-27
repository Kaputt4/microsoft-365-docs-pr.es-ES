---
title: Cancelar la asignación de licencias a usuarios
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- manage_licenses
- okr_smb
- commerce
search.appverid:
- MET150
description: Obtenga información sobre cómo desasignación de licencias de cuentas de usuario.
ms.date: 07/01/2020
ms.openlocfilehash: 550136c2cfa8d81a31e52a4313dc9c967a55d56e
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398198"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="048f3-103">Cancelar la asignación de licencias a usuarios</span><span class="sxs-lookup"><span data-stu-id="048f3-103">Unassign licenses from users</span></span>

<span data-ttu-id="048f3-104">Puede desasignación de licencias de usuarios en la **página Usuarios** activos o en la **página Licencias.**</span><span class="sxs-lookup"><span data-stu-id="048f3-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="048f3-105">El método que use depende de si desea desasignación de licencias de productos de usuarios específicos o desasignación de licencias de usuarios de un producto específico.</span><span class="sxs-lookup"><span data-stu-id="048f3-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="048f3-106">Como administrador, no puede asignar ni cancelar la asignación de licencias para una suscripción de compra sin servicio comprada por un usuario de su organización.</span><span class="sxs-lookup"><span data-stu-id="048f3-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="048f3-107">Puede asumir [una suscripción de compra de](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)autoservicio y, a continuación, asignar o cancelar la asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="048f3-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="048f3-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="048f3-108">Before you begin</span></span>

- <span data-ttu-id="048f3-109">Debe ser un administrador global, de licencia y de usuario para desasignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="048f3-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="048f3-110">Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="048f3-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="048f3-111">Puede [quitar licencias de cuentas de usuario con PowerShell de Office 365](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="048f3-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="048f3-112">También puede eliminar [cuentas de usuario a](../add-users/delete-a-user.md) las que se asignó una licencia para que su licencia esté disponible para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="048f3-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="048f3-113">Al eliminar una cuenta de usuario, su licencia está disponible inmediatamente para asignarla a otra persona.</span><span class="sxs-lookup"><span data-stu-id="048f3-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="048f3-114">Usar la página Licencias para desasignación de licencias</span><span class="sxs-lookup"><span data-stu-id="048f3-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="048f3-115">Al usar la página **Licencias** para desasignar licencias, se desasigna licencias para un producto específico para un máximo de 20 usuarios.</span><span class="sxs-lookup"><span data-stu-id="048f3-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="048f3-116">En el centro de administración, vaya a la página de **Facturación** ><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.</span><span class="sxs-lookup"><span data-stu-id="048f3-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="048f3-117">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Centro de administración,</a>vaya a la página **Licencias** > **de** facturación.</span><span class="sxs-lookup"><span data-stu-id="048f3-117">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="048f3-118">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración,</a>vaya a la página **Licencias** > **de** facturación.</span><span class="sxs-lookup"><span data-stu-id="048f3-118">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="048f3-119">Seleccione el producto para el que desea desasignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="048f3-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="048f3-120">Seleccione los usuarios para los que desea desasignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="048f3-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="048f3-121">Seleccione **Unassign licenses**.</span><span class="sxs-lookup"><span data-stu-id="048f3-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="048f3-122">En el **cuadro Unassign licenses,** seleccione **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="048f3-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="048f3-123">Usar la página Usuarios activos para desasignación de licencias</span><span class="sxs-lookup"><span data-stu-id="048f3-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="048f3-124">Al usar la página **Usuarios activos** para desasignación de licencias, se desasigna licencias de productos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="048f3-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="048f3-125">Unassign licenses from one user</span><span class="sxs-lookup"><span data-stu-id="048f3-125">Unassign licenses from one user</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="048f3-126">En el centro de administración, vaya a la página **Usuarios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="048f3-126">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="048f3-127">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Centro de administración,</a>vaya a la página **Usuarios activos** de > **facturación.**</span><span class="sxs-lookup"><span data-stu-id="048f3-127">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="048f3-128">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración,</a>vaya a la página **Usuarios activos** de > **facturación.**</span><span class="sxs-lookup"><span data-stu-id="048f3-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="048f3-129">Seleccione la fila del usuario para el que desea desasignación de una licencia.</span><span class="sxs-lookup"><span data-stu-id="048f3-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="048f3-130">En el panel derecho, seleccione **licencias y aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="048f3-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="048f3-131">Expanda la **sección Licencias,** desactive los cuadros de las licencias que desea desasignación y, a continuación, **seleccione Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="048f3-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="048f3-132">Unassign licenses from multiple users</span><span class="sxs-lookup"><span data-stu-id="048f3-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="048f3-133">En el centro de administración, vaya a la página **Usuarios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="048f3-133">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="048f3-134">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Centro de administración,</a>vaya a la página **Usuarios activos** de > **facturación.**</span><span class="sxs-lookup"><span data-stu-id="048f3-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="048f3-135">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración,</a>vaya a la página **Usuarios activos** de > **facturación.**</span><span class="sxs-lookup"><span data-stu-id="048f3-135">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="048f3-136">Seleccione los círculos junto a los nombres de los usuarios para los que desea desasignar licencias.</span><span class="sxs-lookup"><span data-stu-id="048f3-136">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="048f3-137">En la parte superior, seleccione **más opciones (...)** y seleccione **administrar licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="048f3-137">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="048f3-138">En el panel **administrar licencias de producto**, seleccione **reemplazar las asignaciones de licencias de producto existentes** \> **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="048f3-138">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="048f3-139">En la parte inferior del panel **Reemplazar** productos **existentes,** active la casilla Quitar todas las licencias de productos de los usuarios seleccionados y, a continuación, **seleccione Reemplazar** \> **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="048f3-139">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="048f3-140">¿Qué sucede con los datos de un usuario al quitar su licencia?</span><span class="sxs-lookup"><span data-stu-id="048f3-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="048f3-141">Cuando se quita una licencia de un usuario, los datos asociados a esa cuenta se mantienen durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="048f3-141">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="048f3-142">Después del período de gracia de 30 días, los datos se eliminan y no se pueden recuperar.</span><span class="sxs-lookup"><span data-stu-id="048f3-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="048f3-143">Los archivos guardados en OneDrive para la Empresa no se eliminan a menos que el usuario se elimine del Centro de administración de Microsoft 365 o se quite a través de la sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="048f3-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="048f3-144">Para obtener más información, vea [Retención y eliminación de OneDrive.](/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="048f3-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="048f3-145">Cuando se quita la licencia, el buzón del usuario ya no se puede buscar mediante una herramienta de exhibición de documentos electrónicos como la búsqueda de contenido o la exhibición de documentos electrónicos avanzada.</span><span class="sxs-lookup"><span data-stu-id="048f3-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="048f3-146">Para obtener más información, vea "Buscar buzones desconectados o sin licencia" en Búsqueda de contenido [en Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="048f3-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="048f3-147">Si tiene una suscripción enterprise, como Office 365 Enterprise E3, Exchange Online le permite conservar los datos de buzón de una cuenta de usuario eliminada mediante buzones [inactivos.](../../compliance/inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="048f3-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="048f3-148">Para obtener más información, vea [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="048f3-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="048f3-149">Para obtener información sobre cómo bloquear el acceso de un usuario a los datos de Microsoft 365 después de quitar su licencia y cómo obtener acceso a los datos después, vea [Remove a former employee](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="048f3-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="048f3-150">Si quita la licencia de un usuario y aún tiene instaladas aplicaciones de Office, verá Errores de activación y producto sin licencia en [Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) cuando usan aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="048f3-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="048f3-151">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="048f3-151">Next steps</span></span>

<span data-ttu-id="048f3-152">Si no va a reasignar las licencias no [usadas](../../managed-desktop/get-started/assign-licenses.md)a otros usuarios, considere la posibilidad de quitar las licencias de la suscripción para que no pague más licencias de las que necesita. [](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="048f3-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="048f3-153">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="048f3-153">Related content</span></span>

<span data-ttu-id="048f3-154">[Quitar licencias de la suscripción](../../commerce/licenses/buy-licenses.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="048f3-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="048f3-155">[Asignar licencias a los usuarios](assign-licenses-to-users.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="048f3-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="048f3-156">[Comprender las suscripciones y licencias en Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="048f3-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>