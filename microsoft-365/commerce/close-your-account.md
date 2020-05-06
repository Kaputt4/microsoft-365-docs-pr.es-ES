---
title: Cerrar la cuenta
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Obtenga información sobre cómo cerrar su cuenta con Microsoft.
ms.openlocfilehash: 43ec3fe2eedc354c0494818f97b01e8de63694c7
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045781"
---
# <a name="close-your-account"></a><span data-ttu-id="0435c-103">Cerrar la cuenta</span><span class="sxs-lookup"><span data-stu-id="0435c-103">Close your account</span></span>

<span data-ttu-id="0435c-104">Al cerrar la cuenta de Microsoft, se elimina toda la información relacionada con su cuenta.</span><span class="sxs-lookup"><span data-stu-id="0435c-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="0435c-105">Esta información incluye suscripciones, licencias, métodos de pago, usuarios y datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="0435c-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="0435c-106">Antes de iniciar este proceso, asegúrese de hacer una copia de seguridad de los datos que desee conservar.</span><span class="sxs-lookup"><span data-stu-id="0435c-106">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="0435c-107">Paso 1: eliminar usuarios</span><span class="sxs-lookup"><span data-stu-id="0435c-107">Step 1: Delete users</span></span>

<span data-ttu-id="0435c-108">Elimine todos los usuarios excepto un administrador global que complete los pasos para cerrar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="0435c-108">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="0435c-109">Antes de poder eliminar el directorio al final de este proceso, debe eliminar todos los demás usuarios.</span><span class="sxs-lookup"><span data-stu-id="0435c-109">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="0435c-110">Si los usuarios están sincronizados desde una ubicación local, primero desactive la sincronización y, a continuación, elimine los usuarios en el directorio de nube con los cmdlets de Azure portal o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0435c-110">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="0435c-111">Para eliminar usuarios, consulte <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Administrador de administración de usuarios: eliminar uno o más usuarios</a>.</span><span class="sxs-lookup"><span data-stu-id="0435c-111">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="0435c-112">También puede usar el cmdlet de PowerShell <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> para eliminar usuarios de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="0435c-112">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="0435c-113">Si su organización usa Active Directory que se sincroniza con Azure AD, elimine la cuenta de usuario de Active Directory en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0435c-113">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="0435c-114">Para obtener instrucciones, consulte <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">bulk Delete users in Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="0435c-114">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="0435c-115">Paso 2: cancelar todas las suscripciones activas</span><span class="sxs-lookup"><span data-stu-id="0435c-115">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="0435c-116">En el centro de administración, vaya a la página **facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de productos</a> .</span><span class="sxs-lookup"><span data-stu-id="0435c-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="0435c-117">Si la lista de suscripciones está en la vista de **tabla** , a la derecha, seleccione **tarjetas**.</span><span class="sxs-lookup"><span data-stu-id="0435c-117">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="0435c-118">Busque una suscripción activa y, en la sección **configuración & acciones** , seleccione **Cancelar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="0435c-118">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="0435c-119">Siga las indicaciones para finalizar el proceso.</span><span class="sxs-lookup"><span data-stu-id="0435c-119">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="0435c-120">Repita los pasos del 1 al 4 para cancelar todas las suscripciones activas.</span><span class="sxs-lookup"><span data-stu-id="0435c-120">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="0435c-121">Paso 3: eliminar todas las suscripciones deshabilitadas</span><span class="sxs-lookup"><span data-stu-id="0435c-121">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="0435c-122">En el centro de administración, vaya a la página **facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de productos</a> .</span><span class="sxs-lookup"><span data-stu-id="0435c-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="0435c-123">Si la lista de suscripciones está en la vista de **tabla** , a la derecha, seleccione **tarjetas**.</span><span class="sxs-lookup"><span data-stu-id="0435c-123">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="0435c-124">Junto a **Estado de suscripción**, seleccione **deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="0435c-124">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="0435c-125">Busque una suscripción deshabilitada y, en la sección **configuración & acciones** , seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0435c-125">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="0435c-126">En el cuadro de diálogo **eliminar suscripción** , active la casilla de verificación **entiendo el impacto** y, a continuación, seleccione **eliminar suscripción**.</span><span class="sxs-lookup"><span data-stu-id="0435c-126">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="0435c-127">Para cada suscripción deshabilitada, repita los pasos 4 y 5 hasta que se hayan eliminado todas las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="0435c-127">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="0435c-128">Paso 4: deshabilitar multi-factor Authentication</span><span class="sxs-lookup"><span data-stu-id="0435c-128">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="0435c-129">En el centro de administración, vaya a **la** > página usuarios<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">activos</a> .</span><span class="sxs-lookup"><span data-stu-id="0435c-129">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="0435c-130">Elija **multi-factor Authentication**.</span><span class="sxs-lookup"><span data-stu-id="0435c-130">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="0435c-131">En la página autenticación multifactor, deshabilite todas las cuentas excepto la cuenta de administrador global que está usando actualmente.</span><span class="sxs-lookup"><span data-stu-id="0435c-131">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="0435c-132">También puede <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">usar PowerShell para deshabilitar multi-factor Authentication para varios usuarios</a>.</span><span class="sxs-lookup"><span data-stu-id="0435c-132">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="0435c-133">Paso 5: eliminar el directorio en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0435c-133">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="0435c-134">Inicie sesión en el <a href="https://aad.portal.azure.com/" target="_blank">centro de administración de Azure ad</a> con una cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="0435c-134">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="0435c-135">Seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0435c-135">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="0435c-136">Cambie al directorio que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="0435c-136">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="0435c-137">Seleccione **eliminar directorio**.</span><span class="sxs-lookup"><span data-stu-id="0435c-137">Select **Delete directory**.</span></span>

5. <span data-ttu-id="0435c-138">Si el directorio produce un error en una o más comprobaciones, verá un vínculo para obtener más información sobre cómo pasar las comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="0435c-138">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="0435c-139">Después de pasar todas las comprobaciones, seleccione **eliminar** para completar el proceso.</span><span class="sxs-lookup"><span data-stu-id="0435c-139">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="0435c-140">Después de completar este paso final, su cuenta con Microsoft se cierra y se elimina.</span><span class="sxs-lookup"><span data-stu-id="0435c-140">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
