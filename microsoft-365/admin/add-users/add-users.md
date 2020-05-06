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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: Obtenga información sobre cómo agregar usuarios a Microsoft 365, uno por vez o varios usuarios al mismo tiempo desde un archivo CSV.
ms.openlocfilehash: 6d7a9d97d4cca25bac6579ea4427136351110658
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049476"
---
# <a name="add-users-individually-or-in-bulk"></a><span data-ttu-id="003ea-103">Agregar usuarios individualmente o de forma masiva</span><span class="sxs-lookup"><span data-stu-id="003ea-103">Add users individually or in bulk</span></span>

<span data-ttu-id="003ea-104">Los usuarios de su equipo necesitan una cuenta de usuario para poder iniciar sesión y obtener acceso a [Microsoft 365 para la empresa](https://go.microsoft.com/fwlink/?LinkID=519395).</span><span class="sxs-lookup"><span data-stu-id="003ea-104">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="003ea-105">La forma más sencilla de agregar cuentas de usuario es agregarlas de una en una a la vez en el centro de administración de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="003ea-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="003ea-106">Después de realizar este paso, los usuarios tendrán licencias de 365 de Microsoft, credenciales de inicio de sesión y buzones de correo de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="003ea-106">After you do this step, your users will have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="003ea-107">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="003ea-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="003ea-108">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="003ea-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="003ea-109">Vaya a **Users** > usuarios **activos**y seleccione **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="003ea-109">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="003ea-110">En el panel **configurar los conceptos básicos** , rellene la información siguiente y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="003ea-110">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="003ea-111">**Nombre** de Rellene primero, último, nombre para mostrar y nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="003ea-111">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="003ea-112">**Dominio** Por ejemplo, si el nombre de usuario del usuario es Jakob y su dominio es contoso.com, tendrá que iniciar sesión escribiendo jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="003ea-112">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="003ea-113">**Configuración de contraseña** Elija usar contraseña generada automáticamente o crear su propia contraseña segura para el usuario.</span><span class="sxs-lookup"><span data-stu-id="003ea-113">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="003ea-114">Necesitará cambiar su contraseña después de 90 días.</span><span class="sxs-lookup"><span data-stu-id="003ea-114">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="003ea-115">O bien, puede optar por **requerir que este usuario cambie su contraseña la primera vez que inicie sesión**.</span><span class="sxs-lookup"><span data-stu-id="003ea-115">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="003ea-116">Elija si desea enviar la contraseña por correo electrónico cuando se haya agregado al usuario.</span><span class="sxs-lookup"><span data-stu-id="003ea-116">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="003ea-117">En el panel **asignar licencias de producto** , seleccione la ubicación y la licencia correspondiente para el usuario.</span><span class="sxs-lookup"><span data-stu-id="003ea-117">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="003ea-118">Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="003ea-118">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="003ea-119">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="003ea-119">Select **Next**.</span></span>

5. <span data-ttu-id="003ea-120">En la página **configuración opcional** , expanda **roles** si desea que el usuario sea administrador y expanda **información de perfil** si desea agregar información adicional sobre el usuario.</span><span class="sxs-lookup"><span data-stu-id="003ea-120">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="003ea-121">Seleccione **siguiente**, revise la configuración del nuevo usuario, realice los cambios que desee y, a continuación, seleccione **terminar de agregar**.</span><span class="sxs-lookup"><span data-stu-id="003ea-121">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="003ea-122">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="003ea-122">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="003ea-123">Vaya a **Users** > usuarios **activos**y seleccione **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="003ea-123">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="003ea-124">En el panel **nuevo usuario** , rellene la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="003ea-124">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="003ea-125">Seleccione **Agregar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="003ea-125">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="003ea-126">**Nombre** Rellene el nombre, apellido, nombre para mostrar y nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="003ea-126">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="003ea-127">**Dominio** Por ejemplo, si el nombre de usuario del usuario es Jakob y su dominio es contoso.com, tendrá que iniciar sesión escribiendo jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="003ea-127">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="003ea-128">**Información de contacto** Expándala para rellenar el número de teléfono móvil, la dirección y demás datos similares.</span><span class="sxs-lookup"><span data-stu-id="003ea-128">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="003ea-129">**Contraseña** Use la contraseña generada automáticamente o expándala para especificar una contraseña segura para el usuario.</span><span class="sxs-lookup"><span data-stu-id="003ea-129">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="003ea-p105">Necesitará cambiar su contraseña después de 90 días. También puede elegir la opción **Solicitar a este usuario que cambie su contraseña la primera vez que inicie sesión**.</span><span class="sxs-lookup"><span data-stu-id="003ea-p105">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="003ea-132">**Roles** Expándala si necesita hacer que este usuario sea administrador.</span><span class="sxs-lookup"><span data-stu-id="003ea-132">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="003ea-p106">**Licencias de producto** Expanda esta sección y seleccione la licencia adecuada. Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="003ea-p106">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="003ea-135">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="003ea-135">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="003ea-136">Vaya a **Users** > usuarios **activos**y seleccione **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="003ea-136">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="003ea-137">En el panel **nuevo usuario** , rellene la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="003ea-137">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="003ea-138">Seleccione **Agregar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="003ea-138">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="003ea-139">**Nombre** Rellene el nombre, apellido, nombre para mostrar y nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="003ea-139">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="003ea-140">**Dominio** Por ejemplo, si el nombre de usuario del usuario es Jakob y su dominio es contoso.com, tendrá que iniciar sesión escribiendo jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="003ea-140">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="003ea-141">**Información de contacto** Expándala para rellenar el número de teléfono móvil, la dirección y demás datos similares.</span><span class="sxs-lookup"><span data-stu-id="003ea-141">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="003ea-142">**Contraseña** Use la contraseña generada automáticamente o expándala para especificar una contraseña segura para el usuario.</span><span class="sxs-lookup"><span data-stu-id="003ea-142">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="003ea-p108">Necesitará cambiar su contraseña después de 90 días. También puede elegir la opción **Solicitar a este usuario que cambie su contraseña la primera vez que inicie sesión**.</span><span class="sxs-lookup"><span data-stu-id="003ea-p108">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="003ea-145">**Roles** Expándala si necesita hacer que este usuario sea administrador.</span><span class="sxs-lookup"><span data-stu-id="003ea-145">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="003ea-p109">**Licencias de producto** Expanda esta sección y seleccione la licencia adecuada. Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="003ea-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="003ea-148">Después de agregar un usuario, recibirá una notificación del equipo de Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="003ea-148">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="003ea-149">El correo electrónico contendrá el identificador de usuario y la contraseña de la persona para que puedan iniciar sesión en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="003ea-149">The email will contain the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="003ea-150">Debe informar a su nuevo usuario sobre la información de inicio de sesión de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="003ea-150">You need to tell your new user about their Microsoft 365 sign in information.</span></span> <span data-ttu-id="003ea-151">Use el proceso habitual para comunicar nuevas contraseñas.</span><span class="sxs-lookup"><span data-stu-id="003ea-151">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="003ea-152">Si crea usuarios mediante la migración de buzones de correo, tendrá que activar las cuentas de usuario mediante la asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="003ea-152">If you create users by migrating mail boxes, you will need to activate user accounts by assigning licenses.</span></span> <span data-ttu-id="003ea-153">Si no asigna una licencia a un usuario, su buzón se deshabilitará después de un período de gracia de 30 días.</span><span class="sxs-lookup"><span data-stu-id="003ea-153">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="003ea-154">Consulte cómo [asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) mediante el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="003ea-154">See how to [assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="003ea-155">Vídeo: agregar y administrar usuarios en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="003ea-155">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="003ea-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="003ea-156">Next steps</span></span>

<span data-ttu-id="003ea-157">Comparta la [Guía de inicio rápido de empleado](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) con los nuevos usuarios para realizar la configuración, como [Office en un equipo PC o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) y [Aplicaciones móviles de Office](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span><span class="sxs-lookup"><span data-stu-id="003ea-157">Share the [Employee quick start guide](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) with your new users to set things up, like [Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) and [Office mobile apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="003ea-158">¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="003ea-158">Need help?</span></span>

<span data-ttu-id="003ea-159">[Póngase en contacto con el soporte técnico de Microsoft 365 para empresas](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="003ea-159">[Contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="003ea-160">¿Tiene cientos o miles de usuarios que agregar?</span><span class="sxs-lookup"><span data-stu-id="003ea-160">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="003ea-161">Para agregar varios usuarios al mismo tiempo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="003ea-161">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="003ea-162">**Use una hoja de cálculo para agregar usuarios en masa.**</span><span class="sxs-lookup"><span data-stu-id="003ea-162">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="003ea-163">Consulte [agregar varios usuarios al mismo tiempo](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span><span class="sxs-lookup"><span data-stu-id="003ea-163">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="003ea-164">**Automatice la agregación de cuentas y la asignación de licencias.**</span><span class="sxs-lookup"><span data-stu-id="003ea-164">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="003ea-165">Consulte [Create User accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="003ea-165">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="003ea-166">Seleccione este método si ya está familiarizado con el uso de cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="003ea-166">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="003ea-167">**¿Usa ActiveDirectory?**</span><span class="sxs-lookup"><span data-stu-id="003ea-167">**Using ActiveDirectory?**</span></span> <span data-ttu-id="003ea-168">[Configurar la sincronización de directorios para Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="003ea-168">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="003ea-169">Use la herramienta Azure AD Connect para replicar cuentas de usuario de Active Directory (y otros objetos de Active Directory) en Office 365.</span><span class="sxs-lookup"><span data-stu-id="003ea-169">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="003ea-170">La sincronización solo agrega las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="003ea-170">The sync only adds the user accounts.</span></span> <span data-ttu-id="003ea-171">Deberá asignar licencias a los usuarios sincronizados para que puedan usar el correo electrónico y otras aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="003ea-171">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="003ea-172">**¿Va a migrar desde Exchange?**</span><span class="sxs-lookup"><span data-stu-id="003ea-172">**Migrating from Exchange?**</span></span> <span data-ttu-id="003ea-173">[Formas de migrar varias cuentas de correo electrónico a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="003ea-173">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="003ea-174">Al migrar varios buzones de correo a Microsoft 365 mediante transferencia, preconfigurada o un método de Exchange híbrido, agregará usuarios automáticamente como parte de la migración.</span><span class="sxs-lookup"><span data-stu-id="003ea-174">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="003ea-175">La migración solo agrega las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="003ea-175">The migration only adds the user accounts.</span></span> <span data-ttu-id="003ea-176">Deberá asignar licencias a los usuarios para que puedan usar el correo electrónico y las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="003ea-176">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="003ea-177">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="003ea-177">Related articles</span></span>

[<span data-ttu-id="003ea-178">Agregar un nuevo empleado a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="003ea-178">Add a new employee to Microsoft 365</span></span>](add-new-employee.md)

[<span data-ttu-id="003ea-179">Eliminar un usuario de la organización</span><span class="sxs-lookup"><span data-stu-id="003ea-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="003ea-180">Restaurar un usuario en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="003ea-180">Restore a user in Microsoft 365</span></span>](restore-user.md)

[<span data-ttu-id="003ea-181">Agregar varios usuarios al mismo tiempo a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="003ea-181">Add several users at the same time to Microsoft 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)

