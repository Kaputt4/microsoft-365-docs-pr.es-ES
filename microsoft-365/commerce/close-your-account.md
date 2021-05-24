---
title: Cerrar la cuenta
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
search.appverid: MET150
description: Al cerrar su cuenta con Microsoft, se elimina toda la información relacionada con su cuenta, incluidas las licencias, los usuarios y los datos de usuario.
ms.date: 04/02/2021
ms.openlocfilehash: b212911707b5d6a967ab833a5a06bc76f5ceeb3b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624330"
---
# <a name="close-your-account"></a><span data-ttu-id="0df5d-103">Cerrar la cuenta</span><span class="sxs-lookup"><span data-stu-id="0df5d-103">Close your account</span></span>

<span data-ttu-id="0df5d-104">Al cerrar la cuenta de Microsoft, se elimina toda la información relacionada con su cuenta.</span><span class="sxs-lookup"><span data-stu-id="0df5d-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="0df5d-105">Esta información incluye suscripciones, licencias, métodos de pago, usuarios y datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="0df5d-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0df5d-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="0df5d-106">Before you begin</span></span>

<span data-ttu-id="0df5d-107">Antes de iniciar este proceso, asegúrese de realizar una copia de seguridad de los datos que desea conservar.</span><span class="sxs-lookup"><span data-stu-id="0df5d-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="0df5d-108">Para poder realizar las tareas de este artículo, debe ser un administrador global o de facturación.</span><span class="sxs-lookup"><span data-stu-id="0df5d-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="0df5d-109">Para más información, vea [Sobre los roles de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0df5d-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="0df5d-110">Paso 1: Eliminar usuarios</span><span class="sxs-lookup"><span data-stu-id="0df5d-110">Step 1: Delete users</span></span>

<span data-ttu-id="0df5d-111">Elimine todos los usuarios excepto un administrador global.</span><span class="sxs-lookup"><span data-stu-id="0df5d-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="0df5d-112">El administrador global completa los pasos para cerrar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="0df5d-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="0df5d-113">Antes de poder eliminar el directorio al final de este proceso, debe eliminar todos los demás usuarios.</span><span class="sxs-lookup"><span data-stu-id="0df5d-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="0df5d-114">Si los usuarios se sincronizan desde local, desactive primero la sincronización y, a continuación, elimine los usuarios del directorio en la nube mediante Azure Portal o Azure PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0df5d-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="0df5d-115">Para eliminar usuarios, vea [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span><span class="sxs-lookup"><span data-stu-id="0df5d-115">To delete users, see [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span></span>

<span data-ttu-id="0df5d-116">También puede usar el cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) de PowerShell para eliminar usuarios en masa.</span><span class="sxs-lookup"><span data-stu-id="0df5d-116">You can also use the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="0df5d-117">Si su organización usa Active Directory que se sincroniza con Microsoft Azure Active Directory (Azure AD), elimine la cuenta de usuario de Active Directory en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0df5d-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="0df5d-118">Para obtener instrucciones, vea [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).</span><span class="sxs-lookup"><span data-stu-id="0df5d-118">For instructions, see [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="0df5d-119">Paso 2: Cancelar todas las suscripciones activas</span><span class="sxs-lookup"><span data-stu-id="0df5d-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="0df5d-120">En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="0df5d-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="0df5d-121">En la **pestaña Productos,** busque una suscripción activa.</span><span class="sxs-lookup"><span data-stu-id="0df5d-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="0df5d-122">Seleccione los tres puntos (más acciones) y, después, seleccione **Cancelar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="0df5d-122">Select the three dots (more actions), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="0df5d-p106">En el panel **Cancelar suscripción**, seleccione una razón por la que cancela. Opcionalmente, proporcione algún comentario.</span><span class="sxs-lookup"><span data-stu-id="0df5d-p106">In the **Cancel subscription** pane, choose a reason why you're canceling. Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="0df5d-125">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0df5d-125">Select **Save**.</span></span>
5. <span data-ttu-id="0df5d-126">Repita los pasos del 1 al 4 para cancelar todas las suscripciones activas.</span><span class="sxs-lookup"><span data-stu-id="0df5d-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="0df5d-127">Paso 3: Eliminar todas las suscripciones deshabilitadas</span><span class="sxs-lookup"><span data-stu-id="0df5d-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="0df5d-128">En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="0df5d-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="0df5d-129">En la **pestaña Productos,** seleccione una suscripción deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="0df5d-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="0df5d-130">En la página detalles de la suscripción, en la sección Configuración de **suscripción y pago,** seleccione **Eliminar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="0df5d-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="0df5d-131">En el **panel Eliminar suscripción,** seleccione **Eliminar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="0df5d-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="0df5d-132">En el **cuadro de diálogo** Eliminar suscripción, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0df5d-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="0df5d-133">Para cada suscripción deshabilitada, repita los pasos del 3 al 5 hasta que se eliminen todas las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="0df5d-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="0df5d-134">Si no puede eliminar inmediatamente una suscripción deshabilitada, póngase [en contacto con el soporte técnico](../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="0df5d-134">If you're unable to immediately delete a disabled subscription, [contact support](../business-video/get-help-support.md).</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="0df5d-135">Paso 4: Deshabilitar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="0df5d-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="0df5d-136">Inicie sesión en el Centro de administración con una cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="0df5d-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="0df5d-137">Para comprobar qué roles tiene, vea [Comprobar roles de administrador en la organización](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="0df5d-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="0df5d-138">Vaya a la **página Usuarios**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">usuarios activos.</a></span><span class="sxs-lookup"><span data-stu-id="0df5d-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="0df5d-139">Elija **Autenticación multifactor**.</span><span class="sxs-lookup"><span data-stu-id="0df5d-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="0df5d-140">En la página autenticación multifactor, deshabilite todas las cuentas excepto la cuenta de administrador global que está usando actualmente.</span><span class="sxs-lookup"><span data-stu-id="0df5d-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="0df5d-141">También puede usar [PowerShell para deshabilitar la autenticación multifactor para varios usuarios.](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="0df5d-141">You can also [use PowerShell to disable multi-factor authentication for multiple users](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell).</span></span>


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="0df5d-142">Paso 5: Eliminar el directorio en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0df5d-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="0df5d-143">Inicie sesión en el <a href="https://aad.portal.azure.com/" target="_blank">Centro de administración de Azure AD</a> con una cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="0df5d-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="0df5d-144">Seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0df5d-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="0df5d-145">Cambie a la organización que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="0df5d-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="0df5d-146">Seleccione **Eliminar inquilino**.</span><span class="sxs-lookup"><span data-stu-id="0df5d-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="0df5d-147">Si su organización falla una o más comprobaciones, verá un vínculo a más información sobre cómo pasar las comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="0df5d-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="0df5d-148">Después de pasar todas las comprobaciones, **seleccione Eliminar** para completar el proceso.</span><span class="sxs-lookup"><span data-stu-id="0df5d-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="0df5d-149">Después de completar este paso final, la cuenta con Microsoft se cierra y elimina.</span><span class="sxs-lookup"><span data-stu-id="0df5d-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>

## <a name="related-content"></a><span data-ttu-id="0df5d-150">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="0df5d-150">Related content</span></span> 

<span data-ttu-id="0df5d-151">[Comprender la factura o factura de Microsoft 365 para empresas](./billing-and-payments/understand-your-invoice2.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="0df5d-151">[Understand your bill or invoice for Microsoft 365 for business](./billing-and-payments/understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="0df5d-152">[Cancelar la suscripción](./subscriptions/cancel-your-subscription.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="0df5d-152">[Cancel your subscription](./subscriptions/cancel-your-subscription.md) (article)</span></span>

