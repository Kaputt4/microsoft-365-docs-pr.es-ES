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
ms.openlocfilehash: 0ee0a649a9adb93ecdbb1cd9dbedbc04dfb46ba0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579751"
---
# <a name="close-your-account"></a><span data-ttu-id="51693-103">Cerrar la cuenta</span><span class="sxs-lookup"><span data-stu-id="51693-103">Close your account</span></span>

<span data-ttu-id="51693-104">Al cerrar la cuenta de Microsoft, se elimina toda la información relacionada con su cuenta.</span><span class="sxs-lookup"><span data-stu-id="51693-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="51693-105">Esta información incluye suscripciones, licencias, métodos de pago, usuarios y datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="51693-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="51693-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="51693-106">Before you begin</span></span>

<span data-ttu-id="51693-107">Antes de iniciar este proceso, asegúrese de realizar una copia de seguridad de los datos que desea conservar.</span><span class="sxs-lookup"><span data-stu-id="51693-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="51693-108">Para poder realizar las tareas de este artículo, debe ser un administrador global o de facturación.</span><span class="sxs-lookup"><span data-stu-id="51693-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="51693-109">Para más información, consulte[Sobre los roles de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="51693-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="51693-110">Paso 1: Eliminar usuarios</span><span class="sxs-lookup"><span data-stu-id="51693-110">Step 1: Delete users</span></span>

<span data-ttu-id="51693-111">Elimine todos los usuarios excepto un administrador global.</span><span class="sxs-lookup"><span data-stu-id="51693-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="51693-112">El administrador global completa los pasos para cerrar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="51693-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="51693-113">Antes de poder eliminar el directorio al final de este proceso, debe eliminar todos los demás usuarios.</span><span class="sxs-lookup"><span data-stu-id="51693-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="51693-114">Si los usuarios se sincronizan desde local, desactive primero la sincronización y, a continuación, elimine los usuarios del directorio en la nube mediante los cmdlets de Azure Portal o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51693-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="51693-115">Para eliminar usuarios, vea <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span><span class="sxs-lookup"><span data-stu-id="51693-115">To delete users, see <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="51693-116">También puede usar el cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> de PowerShell para eliminar usuarios en masa.</span><span class="sxs-lookup"><span data-stu-id="51693-116">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="51693-117">Si su organización usa Active Directory que se sincroniza con Microsoft Azure Active Directory (Azure AD), elimine la cuenta de usuario de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="51693-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="51693-118">Para obtener instrucciones, consulte <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Eliminación masiva de usuarios en Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="51693-118">For instructions, see <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="51693-119">Paso 2: Cancelar todas las suscripciones activas</span><span class="sxs-lookup"><span data-stu-id="51693-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="51693-120">En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="51693-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="51693-121">En la **pestaña Productos,** busque una suscripción activa.</span><span class="sxs-lookup"><span data-stu-id="51693-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="51693-122">Seleccione **Más acciones** (tres puntos) y luego seleccione **Cancelar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="51693-122">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="51693-123">En el panel **Cancelar suscripción**, seleccione una razón por la que cancela.</span><span class="sxs-lookup"><span data-stu-id="51693-123">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="51693-124">Opcionalmente, proporcione algún comentario.</span><span class="sxs-lookup"><span data-stu-id="51693-124">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="51693-125">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="51693-125">Select **Save**.</span></span>
5. <span data-ttu-id="51693-126">Repita los pasos del 1 al 4 para cancelar todas las suscripciones activas.</span><span class="sxs-lookup"><span data-stu-id="51693-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="51693-127">Paso 3: Eliminar todas las suscripciones deshabilitadas</span><span class="sxs-lookup"><span data-stu-id="51693-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="51693-128">En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="51693-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="51693-129">En la **pestaña Productos,** seleccione una suscripción deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="51693-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="51693-130">En la página detalles de la suscripción, en la sección Configuración de **suscripción y pago,** seleccione **Eliminar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="51693-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="51693-131">En el **panel Eliminar suscripción,** seleccione **Eliminar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="51693-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="51693-132">En el **cuadro de diálogo** Eliminar suscripción, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="51693-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="51693-133">Para cada suscripción deshabilitada, repita los pasos del 3 al 5 hasta que se eliminen todas las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="51693-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="51693-134">Si no puedes eliminar inmediatamente una suscripción deshabilitada, ponte en contacto <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">con el soporte técnico</a></span><span class="sxs-lookup"><span data-stu-id="51693-134">If you're unable to immediately delete a disabled subscription, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="51693-135">Paso 4: Deshabilitar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="51693-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="51693-136">Inicie sesión en el Centro de administración con una cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="51693-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="51693-137">Para comprobar qué roles tiene, vea [Comprobar roles de administrador en la organización](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="51693-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="51693-138">Vaya a la **página Usuarios**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">usuarios activos.</a></span><span class="sxs-lookup"><span data-stu-id="51693-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="51693-139">Elija **Autenticación multifactor**.</span><span class="sxs-lookup"><span data-stu-id="51693-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="51693-140">En la página autenticación multifactor, deshabilite todas las cuentas excepto la cuenta de administrador global que está usando actualmente.</span><span class="sxs-lookup"><span data-stu-id="51693-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="51693-141">También puede usar <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell para deshabilitar la autenticación multifactor para varios usuarios.</a></span><span class="sxs-lookup"><span data-stu-id="51693-141">You can also <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="51693-142">Paso 5: Eliminar el directorio en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="51693-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="51693-143">Inicie sesión en el <a href="https://aad.portal.azure.com/" target="_blank">Centro de administración de Azure AD</a> con una cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="51693-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="51693-144">Seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="51693-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="51693-145">Cambie a la organización que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="51693-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="51693-146">Seleccione **Eliminar inquilino**.</span><span class="sxs-lookup"><span data-stu-id="51693-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="51693-147">Si su organización falla una o más comprobaciones, verá un vínculo a más información sobre cómo pasar las comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="51693-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="51693-148">Después de pasar todas las comprobaciones, **seleccione Eliminar** para completar el proceso.</span><span class="sxs-lookup"><span data-stu-id="51693-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="51693-149">Después de completar este paso final, la cuenta con Microsoft se cierra y elimina.</span><span class="sxs-lookup"><span data-stu-id="51693-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>