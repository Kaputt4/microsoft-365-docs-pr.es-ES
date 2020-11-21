---
title: Cerrar la cuenta
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
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Obtenga información sobre cómo cerrar su cuenta con Microsoft.
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376322"
---
# <a name="close-your-account"></a><span data-ttu-id="5c758-103">Cerrar la cuenta</span><span class="sxs-lookup"><span data-stu-id="5c758-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5c758-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="5c758-104">The admin center is changing.</span></span> <span data-ttu-id="5c758-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="5c758-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="5c758-106">Al cerrar la cuenta de Microsoft, se elimina toda la información relacionada con su cuenta.</span><span class="sxs-lookup"><span data-stu-id="5c758-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="5c758-107">Esta información incluye suscripciones, licencias, métodos de pago, usuarios y datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="5c758-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5c758-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="5c758-108">Before you begin</span></span>

<span data-ttu-id="5c758-109">Antes de iniciar este proceso, asegúrese de realizar una copia de seguridad de los datos que desea conservar.</span><span class="sxs-lookup"><span data-stu-id="5c758-109">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="5c758-110">Debe ser administrador global o de facturación para realizar las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="5c758-110">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="5c758-111">Para obtener más información, vea [Asignar roles de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5c758-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="5c758-112">Paso 1: eliminar usuarios</span><span class="sxs-lookup"><span data-stu-id="5c758-112">Step 1: Delete users</span></span>

<span data-ttu-id="5c758-113">Eliminar todos los usuarios excepto un administrador global.</span><span class="sxs-lookup"><span data-stu-id="5c758-113">Delete all users except for one global administrator.</span></span> <span data-ttu-id="5c758-114">El administrador global completa los pasos para cerrar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="5c758-114">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="5c758-115">Antes de poder eliminar el directorio al final de este proceso, debe eliminar todos los demás usuarios.</span><span class="sxs-lookup"><span data-stu-id="5c758-115">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="5c758-116">Si los usuarios están sincronizados desde una ubicación local, primero desactive la sincronización y, a continuación, elimine los usuarios en el directorio de nube con los cmdlets de Azure portal o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c758-116">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="5c758-117">Para eliminar usuarios, consulte <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Administrador de administración de usuarios: eliminar uno o más usuarios</a>.</span><span class="sxs-lookup"><span data-stu-id="5c758-117">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="5c758-118">También puede usar el cmdlet de PowerShell <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> para eliminar usuarios de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="5c758-118">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="5c758-119">Si su organización usa Active Directory que se sincroniza con Microsoft Azure Active Directory (Azure AD), elimine la cuenta de usuario de Active Directory en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5c758-119">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="5c758-120">Para obtener instrucciones, consulte <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">bulk Delete users in Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="5c758-120">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="5c758-121">Paso 2: cancelar todas las suscripciones activas</span><span class="sxs-lookup"><span data-stu-id="5c758-121">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="5c758-122">En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="5c758-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="5c758-123">En la pestaña **productos** , busque una suscripción activa.</span><span class="sxs-lookup"><span data-stu-id="5c758-123">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="5c758-124">Seleccione **Más acciones** (tres puntos) y luego seleccione **Cancelar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="5c758-124">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="5c758-125">En el panel **Cancelar suscripción**, seleccione una razón por la que cancela.</span><span class="sxs-lookup"><span data-stu-id="5c758-125">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="5c758-126">Opcionalmente, proporcione algún comentario.</span><span class="sxs-lookup"><span data-stu-id="5c758-126">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="5c758-127">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5c758-127">Select **Save**.</span></span>
5. <span data-ttu-id="5c758-128">Repita los pasos del 1 al 4 para cancelar todas las suscripciones activas.</span><span class="sxs-lookup"><span data-stu-id="5c758-128">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="5c758-129">Paso 3: eliminar todas las suscripciones deshabilitadas</span><span class="sxs-lookup"><span data-stu-id="5c758-129">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="5c758-130">En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="5c758-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="5c758-131">En la pestaña **productos** , seleccione una suscripción deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="5c758-131">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="5c758-132">En la sección **configuración de suscripción y pagos** de la página Detalles de la suscripción, seleccione **eliminar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="5c758-132">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="5c758-133">En el panel **eliminar suscripción** , seleccione **eliminar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="5c758-133">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="5c758-134">En el cuadro de diálogo **eliminar suscripción** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="5c758-134">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="5c758-135">Para cada suscripción deshabilitada, repita los pasos del 3 al 5 hasta que se eliminen todas las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="5c758-135">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="5c758-136">Si no puede eliminar inmediatamente una suscripción deshabilitada, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">póngase en contacto con el soporte técnico</a></span><span class="sxs-lookup"><span data-stu-id="5c758-136">If you're unable to immediately delete a disabled subscription, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="5c758-137">Paso 4: deshabilitar multi-factor Authentication</span><span class="sxs-lookup"><span data-stu-id="5c758-137">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="5c758-138">Inicie sesión en el centro de administración con una cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5c758-138">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="5c758-139">Para comprobar qué roles tiene, consulte [check admin roles in your Organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="5c758-139">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="5c758-140">Vaya **a la**  >  Página usuarios <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">activos</a> .</span><span class="sxs-lookup"><span data-stu-id="5c758-140">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="5c758-141">Elija **multi-factor Authentication**.</span><span class="sxs-lookup"><span data-stu-id="5c758-141">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="5c758-142">En la página autenticación multifactor, deshabilite todas las cuentas excepto la cuenta de administrador global que está usando actualmente.</span><span class="sxs-lookup"><span data-stu-id="5c758-142">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="5c758-143">También puede <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">usar PowerShell para deshabilitar multi-factor Authentication para varios usuarios</a>.</span><span class="sxs-lookup"><span data-stu-id="5c758-143">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="5c758-144">Paso 5: eliminar el directorio en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5c758-144">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="5c758-145">Inicie sesión en el <a href="https://aad.portal.azure.com/" target="_blank">centro de administración de Azure ad</a> con una cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5c758-145">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="5c758-146">Seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5c758-146">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="5c758-147">Cambie a la organización que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="5c758-147">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="5c758-148">Seleccione **eliminar inquilino**.</span><span class="sxs-lookup"><span data-stu-id="5c758-148">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="5c758-149">Si la organización da error en una o más comprobaciones, verá un vínculo para obtener más información sobre cómo pasar las comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="5c758-149">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="5c758-150">Después de pasar todas las comprobaciones, seleccione **eliminar** para completar el proceso.</span><span class="sxs-lookup"><span data-stu-id="5c758-150">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="5c758-151">Después de completar este paso final, su cuenta con Microsoft se cierra y se elimina.</span><span class="sxs-lookup"><span data-stu-id="5c758-151">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>