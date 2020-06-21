---
title: Agregar usuarios individualmente o de forma masiva
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
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: Obtenga información sobre cómo agregar usuarios a Microsoft 365, uno por vez o varios usuarios al mismo tiempo desde un archivo CSV.
ms.openlocfilehash: af160b78317171bec98dcfa3d5877b53560f75a2
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780666"
---
# <a name="add-users-individually-or-in-bulk"></a><span data-ttu-id="938a1-103">Agregar usuarios individualmente o de forma masiva</span><span class="sxs-lookup"><span data-stu-id="938a1-103">Add users individually or in bulk</span></span>

<span data-ttu-id="938a1-104">Los usuarios de su equipo necesitan una cuenta de usuario para poder iniciar sesión y obtener acceso a [Microsoft 365 para la empresa](https://go.microsoft.com/fwlink/?LinkID=519395).</span><span class="sxs-lookup"><span data-stu-id="938a1-104">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="938a1-105">La forma más sencilla de agregar cuentas de usuario es agregarlas de una en una a la vez en el centro de administración de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="938a1-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="938a1-106">Después de realizar este paso, los usuarios tendrán licencias de 365 de Microsoft, credenciales de inicio de sesión y buzones de correo de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="938a1-106">After you do this step, your users will have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="938a1-107">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="938a1-107">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="938a1-108">Vaya a **usuarios** > **activos**y seleccione **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="938a1-108">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="938a1-109">En el panel **configurar los conceptos básicos** , rellene la información siguiente y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="938a1-109">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="938a1-110">**Nombre** de Rellene primero, último, nombre para mostrar y nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="938a1-110">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="938a1-111">**Dominio** Por ejemplo, si el nombre de usuario del usuario es Jakob y su dominio es contoso.com, tendrá que iniciar sesión escribiendo jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="938a1-111">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="938a1-112">**Configuración de contraseña** Elija usar contraseña generada automáticamente o crear su propia contraseña segura para el usuario.</span><span class="sxs-lookup"><span data-stu-id="938a1-112">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="938a1-113">Necesitará cambiar su contraseña después de 90 días.</span><span class="sxs-lookup"><span data-stu-id="938a1-113">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="938a1-114">O bien, puede optar por **requerir que este usuario cambie su contraseña la primera vez que inicie sesión**.</span><span class="sxs-lookup"><span data-stu-id="938a1-114">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="938a1-115">Elija si desea enviar la contraseña por correo electrónico cuando se haya agregado al usuario.</span><span class="sxs-lookup"><span data-stu-id="938a1-115">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="938a1-116">En el panel **asignar licencias de producto** , seleccione la ubicación y la licencia correspondiente para el usuario.</span><span class="sxs-lookup"><span data-stu-id="938a1-116">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="938a1-117">Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="938a1-117">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="938a1-118">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="938a1-118">Select **Next**.</span></span>

5. <span data-ttu-id="938a1-119">En la página **configuración opcional** , expanda **roles** si desea que el usuario sea administrador y expanda **información de perfil** si desea agregar información adicional sobre el usuario.</span><span class="sxs-lookup"><span data-stu-id="938a1-119">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="938a1-120">Seleccione **siguiente**, revise la configuración del nuevo usuario, realice los cambios que desee y, a continuación, seleccione **terminar de agregar**.</span><span class="sxs-lookup"><span data-stu-id="938a1-120">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="938a1-121">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="938a1-121">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="938a1-122">Vaya a **usuarios** > **activos**y seleccione **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="938a1-122">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="938a1-123">En el panel **nuevo usuario** , rellene la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="938a1-123">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="938a1-124">Seleccione **Agregar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="938a1-124">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="938a1-125">**Nombre** Rellene el nombre, apellido, nombre para mostrar y nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="938a1-125">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="938a1-126">**Dominio** Por ejemplo, si el nombre de usuario del usuario es Jakob y su dominio es contoso.com, tendrá que iniciar sesión escribiendo jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="938a1-126">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="938a1-127">**Información de contacto** Expándala para rellenar el número de teléfono móvil, la dirección y demás datos similares.</span><span class="sxs-lookup"><span data-stu-id="938a1-127">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="938a1-128">**Contraseña** Use la contraseña generada automáticamente o expándala para especificar una contraseña segura para el usuario.</span><span class="sxs-lookup"><span data-stu-id="938a1-128">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="938a1-129">They'll need to change their password after 90 days.</span><span class="sxs-lookup"><span data-stu-id="938a1-129">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="938a1-130">Or you can choose to **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="938a1-130">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="938a1-131">**Roles** Expándala si necesita hacer que este usuario sea administrador.</span><span class="sxs-lookup"><span data-stu-id="938a1-131">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="938a1-132">**Product licenses** Expand this section and select the appropriate license.</span><span class="sxs-lookup"><span data-stu-id="938a1-132">**Product licenses** Expand this section and select the appropriate license.</span></span> <span data-ttu-id="938a1-133">If you don't have any licenses available, you can still add a user and buy additional licenses.</span><span class="sxs-lookup"><span data-stu-id="938a1-133">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="938a1-134">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="938a1-134">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="938a1-135">Vaya a **usuarios** > **activos**y seleccione **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="938a1-135">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="938a1-136">En el panel **nuevo usuario** , rellene la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="938a1-136">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="938a1-137">Seleccione **Agregar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="938a1-137">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="938a1-138">**Nombre** Rellene el nombre, apellido, nombre para mostrar y nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="938a1-138">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="938a1-139">**Dominio** Por ejemplo, si el nombre de usuario del usuario es Jakob y su dominio es contoso.com, tendrá que iniciar sesión escribiendo jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="938a1-139">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="938a1-140">**Información de contacto** Expándala para rellenar el número de teléfono móvil, la dirección y demás datos similares.</span><span class="sxs-lookup"><span data-stu-id="938a1-140">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="938a1-141">**Contraseña** Use la contraseña generada automáticamente o expándala para especificar una contraseña segura para el usuario.</span><span class="sxs-lookup"><span data-stu-id="938a1-141">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="938a1-142">They'll need to change their password after 90 days.</span><span class="sxs-lookup"><span data-stu-id="938a1-142">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="938a1-143">Or you can choose to **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="938a1-143">Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="938a1-144">**Roles** Expándala si necesita hacer que este usuario sea administrador.</span><span class="sxs-lookup"><span data-stu-id="938a1-144">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="938a1-145">**Product licenses** Expand this section and select the appropriate license.</span><span class="sxs-lookup"><span data-stu-id="938a1-145">**Product licenses** Expand this section and select the appropriate license.</span></span> <span data-ttu-id="938a1-146">If you don't have any licenses available, you can still add a user and buy additional licenses.</span><span class="sxs-lookup"><span data-stu-id="938a1-146">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="938a1-147">Después de agregar un usuario, recibirá una notificación del equipo de Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="938a1-147">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="938a1-148">El correo electrónico contendrá el identificador de usuario y la contraseña de la persona para que puedan iniciar sesión en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="938a1-148">The email will contain the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="938a1-149">Debe informar a su nuevo usuario sobre la información de inicio de sesión de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="938a1-149">You need to tell your new user about their Microsoft 365 sign in information.</span></span> <span data-ttu-id="938a1-150">Use el proceso habitual para comunicar nuevas contraseñas.</span><span class="sxs-lookup"><span data-stu-id="938a1-150">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="938a1-151">Si crea usuarios mediante la migración de buzones de correo, tendrá que activar las cuentas de usuario mediante la asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="938a1-151">If you create users by migrating mail boxes, you will need to activate user accounts by assigning licenses.</span></span> <span data-ttu-id="938a1-152">Si no asigna una licencia a un usuario, su buzón se deshabilitará después de un período de gracia de 30 días.</span><span class="sxs-lookup"><span data-stu-id="938a1-152">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="938a1-153">Consulte cómo [asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) mediante el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="938a1-153">See how to [assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="938a1-154">Vídeo: agregar y administrar usuarios en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="938a1-154">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="938a1-155">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="938a1-155">Next steps</span></span>

<span data-ttu-id="938a1-156">Comparta la [Guía de inicio rápido de empleado](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) con los nuevos usuarios para realizar la configuración, como [Office en un equipo PC o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) y [Aplicaciones móviles de Office](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="938a1-156">Share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your new users to set things up, like [Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [Office mobile apps](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="938a1-157">¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="938a1-157">Need help?</span></span>

<span data-ttu-id="938a1-158">[Póngase en contacto con el soporte técnico de Microsoft 365 para empresas](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="938a1-158">[Contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="938a1-159">¿Tiene cientos o miles de usuarios que agregar?</span><span class="sxs-lookup"><span data-stu-id="938a1-159">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="938a1-160">Para agregar varios usuarios al mismo tiempo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="938a1-160">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="938a1-161">**Use una hoja de cálculo para agregar usuarios en masa.**</span><span class="sxs-lookup"><span data-stu-id="938a1-161">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="938a1-162">Consulte [agregar varios usuarios al mismo tiempo](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span><span class="sxs-lookup"><span data-stu-id="938a1-162">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="938a1-163">**Automatice la agregación de cuentas y la asignación de licencias.**</span><span class="sxs-lookup"><span data-stu-id="938a1-163">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="938a1-164">Consulte [Create User accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="938a1-164">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="938a1-165">Seleccione este método si ya está familiarizado con el uso de cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="938a1-165">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="938a1-166">**¿Usa ActiveDirectory?**</span><span class="sxs-lookup"><span data-stu-id="938a1-166">**Using ActiveDirectory?**</span></span> <span data-ttu-id="938a1-167">[Configurar la sincronización de directorios para Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="938a1-167">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="938a1-168">Use la herramienta Azure AD Connect para replicar cuentas de usuario de Active Directory (y otros objetos de Active Directory) en Office 365.</span><span class="sxs-lookup"><span data-stu-id="938a1-168">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="938a1-169">La sincronización solo agrega las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="938a1-169">The sync only adds the user accounts.</span></span> <span data-ttu-id="938a1-170">Deberá asignar licencias a los usuarios sincronizados para que puedan usar el correo electrónico y otras aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="938a1-170">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="938a1-171">**¿Va a migrar desde Exchange?**</span><span class="sxs-lookup"><span data-stu-id="938a1-171">**Migrating from Exchange?**</span></span> <span data-ttu-id="938a1-172">[Formas de migrar varias cuentas de correo electrónico a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="938a1-172">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="938a1-173">Al migrar varios buzones de correo a Microsoft 365 mediante transferencia, preconfigurada o un método de Exchange híbrido, agregará usuarios automáticamente como parte de la migración.</span><span class="sxs-lookup"><span data-stu-id="938a1-173">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="938a1-174">La migración solo agrega las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="938a1-174">The migration only adds the user accounts.</span></span> <span data-ttu-id="938a1-175">Deberá asignar licencias a los usuarios para que puedan usar el correo electrónico y las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="938a1-175">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="938a1-176">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="938a1-176">Related articles</span></span>

[<span data-ttu-id="938a1-177">Asignar licencias a usuarios</span><span class="sxs-lookup"><span data-stu-id="938a1-177">Assign licenses to users</span></span>](../manage/assign-licenses-to-users.md)

[<span data-ttu-id="938a1-178">Agregar un nuevo empleado a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="938a1-178">Add a new employee to Microsoft 365</span></span>](add-new-employee.md)

[<span data-ttu-id="938a1-179">Eliminar un usuario de la organización</span><span class="sxs-lookup"><span data-stu-id="938a1-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="938a1-180">Restaurar un usuario en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="938a1-180">Restore a user in Microsoft 365</span></span>](restore-user.md)

[<span data-ttu-id="938a1-181">Agregar varios usuarios al mismo tiempo a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="938a1-181">Add several users at the same time to Microsoft 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)

