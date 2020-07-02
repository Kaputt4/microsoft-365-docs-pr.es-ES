---
title: Cancelar la asignación de licencias a usuarios
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Obtenga información sobre cómo cancelar la asignación de licencias desde cuentas de usuario.
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015940"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="9861c-103">Cancelar la asignación de licencias a usuarios</span><span class="sxs-lookup"><span data-stu-id="9861c-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9861c-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="9861c-104">The admin center is changing.</span></span> <span data-ttu-id="9861c-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="9861c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="9861c-106">Puede anular la asignación de licencias de los usuarios en la página **usuarios activos** o en la página **licencias** .</span><span class="sxs-lookup"><span data-stu-id="9861c-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="9861c-107">El método que use dependerá de si desea cancelar la asignación de licencias de producto de usuarios específicos o cancelar la asignación de licencias de usuarios de un producto específico.</span><span class="sxs-lookup"><span data-stu-id="9861c-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="9861c-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="9861c-108">Before you begin</span></span>

- <span data-ttu-id="9861c-109">Debe ser global, licencia, administrador de usuarios para cancelar la asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="9861c-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="9861c-110">Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9861c-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="9861c-111">Puede [quitar licencias de cuentas de usuario con PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="9861c-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span></span>
- <span data-ttu-id="9861c-112">También puede [eliminar cuentas de usuario a las](../add-users/delete-a-user.md) que se asignó una licencia para que su licencia esté disponible para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="9861c-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="9861c-113">Al eliminar una cuenta de usuario, su licencia está disponible de forma inmediata para asignarla a otra persona.</span><span class="sxs-lookup"><span data-stu-id="9861c-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="9861c-114">Usar la página licencias para cancelar la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="9861c-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="9861c-115">Cuando usa la página **licencias** para cancelar la asignación de licencias, puede cancelar la asignación de licencias para un producto específico para un máximo de 20 usuarios.</span><span class="sxs-lookup"><span data-stu-id="9861c-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="9861c-116">En el centro de administración, vaya a **Billing** la > página <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de facturación.</span><span class="sxs-lookup"><span data-stu-id="9861c-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="9861c-117">Seleccione el producto para el que desea cancelar la asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="9861c-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="9861c-118">Seleccione los usuarios para los que desea cancelar la asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="9861c-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="9861c-119">Seleccione **Cancelar asignación de licencias**.</span><span class="sxs-lookup"><span data-stu-id="9861c-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="9861c-120">En el cuadro cancelar la **asignación de licencias** , seleccione **quitar asignación**.</span><span class="sxs-lookup"><span data-stu-id="9861c-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="9861c-121">Usar la página usuarios activos para cancelar la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="9861c-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="9861c-122">Cuando se usa la página **usuarios activos** para cancelar la asignación de licencias, se desasignan las licencias de producto de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9861c-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="9861c-123">Cancelar la asignación de licencias de un usuario</span><span class="sxs-lookup"><span data-stu-id="9861c-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="9861c-124">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="9861c-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9861c-125">Seleccione la fila del usuario para la que desea quitar la asignación de una licencia.</span><span class="sxs-lookup"><span data-stu-id="9861c-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="9861c-126">En el panel derecho, seleccione **licencias y aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9861c-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="9861c-127">Expanda la sección **licencias** , desactive las casillas de las licencias cuya asignación desea cancelar y, a continuación, seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="9861c-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="9861c-128">Cancelar la asignación de licencias de un usuario</span><span class="sxs-lookup"><span data-stu-id="9861c-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="9861c-129">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="9861c-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9861c-130">Seleccione el usuario para el que desea quitar la asignación de la licencia.</span><span class="sxs-lookup"><span data-stu-id="9861c-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="9861c-131">En la parte derecha, en la fila **licencias de productos** , seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9861c-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="9861c-132">En el panel **licencias de productos** , cambie el botón de alternancia a la posición **desactivado** para la licencia que desea quitar para el usuario.</span><span class="sxs-lookup"><span data-stu-id="9861c-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="9861c-133">Por ejemplo, si desactiva la licencia Office 365 Enterprise E3, desasigna dicha licencia y todos los servicios de dicha licencia para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="9861c-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="9861c-134">En la parte inferior del panel **Licencias de producto**, elija **Guardar** \> **Cerrar** \> **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9861c-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="9861c-135">Cancelar la asignación de licencias de un usuario</span><span class="sxs-lookup"><span data-stu-id="9861c-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="9861c-136">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="9861c-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9861c-137">Seleccione el usuario para el que desea quitar la asignación de la licencia.</span><span class="sxs-lookup"><span data-stu-id="9861c-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="9861c-138">En la parte derecha, en la fila **licencias de productos** , seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9861c-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="9861c-139">En el panel **licencias de productos** , cambie el botón de alternancia a la posición **desactivado** para la licencia que desea quitar para el usuario.</span><span class="sxs-lookup"><span data-stu-id="9861c-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="9861c-140">Por ejemplo, si desactiva la licencia Office 365 Enterprise E3, desasigna dicha licencia y todos los servicios de dicha licencia para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="9861c-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="9861c-141">En la parte inferior del panel **Licencias de producto**, elija **Guardar** \> **Cerrar** \> **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9861c-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="9861c-142">Cancelar la asignación de licencias de varios usuarios</span><span class="sxs-lookup"><span data-stu-id="9861c-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="9861c-143">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="9861c-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9861c-144">Seleccione los círculos que se encuentra junto a los nombres de los usuarios para los que desea cancelar la asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="9861c-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="9861c-145">En la parte superior, seleccione **más opciones (...)** y seleccione **administrar licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="9861c-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="9861c-146">En el panel **administrar licencias de producto**, seleccione **reemplazar las asignaciones de licencias de producto existentes** \> **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9861c-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="9861c-147">En la parte inferior del panel **reemplazar productos existentes** , active la casilla **quitar todas las licencias de producto de los usuarios seleccionados** y, a continuación, seleccione **reemplazar** \> **cierre**.</span><span class="sxs-lookup"><span data-stu-id="9861c-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="9861c-148">Cancelar la asignación de licencias de varios usuarios</span><span class="sxs-lookup"><span data-stu-id="9861c-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="9861c-149">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="9861c-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9861c-150">Active las casillas situadas junto a los nombres de los usuarios para los que desea cancelar la asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="9861c-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="9861c-151">En el panel **Acciones en masa**, elija **Editar licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="9861c-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="9861c-152">En el panel **Reemplazar productos existentes**, seleccione **Reemplazar las asignaciones de licencias de producto existentes** \> **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9861c-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="9861c-153">En la parte inferior del panel **reemplazar productos existentes** , active la casilla **quitar todas las licencias de producto de los usuarios seleccionados** y, a continuación, seleccione **reemplazar** \> **cerrar** \> **cierre**.</span><span class="sxs-lookup"><span data-stu-id="9861c-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="9861c-154">Cancelar la asignación de licencias de varios usuarios</span><span class="sxs-lookup"><span data-stu-id="9861c-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="9861c-155">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="9861c-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="9861c-156">Active las casillas situadas junto a los nombres de los usuarios para los que desea cancelar la asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="9861c-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="9861c-157">En el panel **Acciones en masa**, elija **Editar licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="9861c-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="9861c-158">En el panel **Reemplazar productos existentes**, seleccione **Reemplazar las asignaciones de licencias de producto existentes** \> **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9861c-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="9861c-159">En la parte inferior del panel **reemplazar productos existentes** , active la casilla **quitar todas las licencias de producto de los usuarios seleccionados** y, a continuación, seleccione **reemplazar** \> **cerrar** \> **cierre**.</span><span class="sxs-lookup"><span data-stu-id="9861c-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="9861c-160">¿Qué pasa con los datos de un usuario cuando quita su licencia?</span><span class="sxs-lookup"><span data-stu-id="9861c-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="9861c-161">Cuando se quita una licencia de un usuario, los datos asociados con dicha cuenta se conservan durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="9861c-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="9861c-162">Después del período de gracia de 30 días, los datos se eliminan y no se pueden recuperar.</span><span class="sxs-lookup"><span data-stu-id="9861c-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="9861c-163">Los archivos guardados en OneDrive para la empresa no se eliminan a menos que el usuario se elimine del centro de administración de Microsoft 365 o se elimine mediante la sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9861c-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="9861c-164">Para obtener más información, vea [retención y eliminación de OneDrive](https://docs.microsoft.com/onedrive/retention-and-deletion).</span><span class="sxs-lookup"><span data-stu-id="9861c-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="9861c-165">Cuando se quita la licencia, ya no se pueden realizar búsquedas en el buzón de correo del usuario con una herramienta de eDiscovery, como la búsqueda de contenido o la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="9861c-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="9861c-166">Para obtener más información, vea "buscar buzones desconectados o no autorizados" en [búsqueda de contenido en Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="9861c-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="9861c-167">Si tiene una suscripción de Enterprise, como Office 365 Enterprise E3, Exchange Online le permite conservar los datos de buzón de una cuenta de usuario eliminada mediante el uso de [buzones inactivos](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="9861c-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="9861c-168">Para obtener más información, vea [crear y administrar buzones inactivos en Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="9861c-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="9861c-169">Para obtener información sobre cómo bloquear el acceso de un usuario a los datos de Microsoft 365 después de eliminar su licencia y cómo obtener acceso a los datos después, vea [quitar un antiguo empleado](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="9861c-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="9861c-170">Si quita la licencia de un usuario y aún tiene aplicaciones de Office instaladas, verán [errores de activación y de producto sin licencia en Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) cuando usen aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="9861c-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9861c-171">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9861c-171">Next steps</span></span>

<span data-ttu-id="9861c-172">Si no va a [reasignar las licencias sin usar a otros usuarios](../../managed-desktop/get-started/assign-licenses.md), considere la posibilidad [de quitar las licencias de la suscripción](../../commerce/licenses/buy-licenses.md) para no pagar más licencias de las que necesita.</span><span class="sxs-lookup"><span data-stu-id="9861c-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="9861c-173">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="9861c-173">Related content</span></span>

<span data-ttu-id="9861c-174">[Quitar licencias de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md) (artículo) </span><span class="sxs-lookup"><span data-stu-id="9861c-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="9861c-175">[Asignar licencias a usuarios](assign-licenses-to-users.md) (artículo) </span><span class="sxs-lookup"><span data-stu-id="9861c-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="9861c-176">[Descripción de las suscripciones y licencias de Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="9861c-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>