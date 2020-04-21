---
title: Elimine un usuario de su organización
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Obtenga información sobre cómo eliminar una cuenta de usuario. Decida qué hacer con el correo electrónico del usuario, el contenido de OneDrive y si quiere mantener la licencia del producto o dejar de pagar por él.
ms.openlocfilehash: 1d529627841c648684c8a9fe217a761b29749150
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43617253"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="85f31-104">Elimine un usuario de su organización</span><span class="sxs-lookup"><span data-stu-id="85f31-104">Delete a user from your organization</span></span>
  
||
|:-----|
|<span data-ttu-id="85f31-105">**¿Busca cómo eliminar su *propia* cuenta de usuario de Microsoft 365 que usa en el trabajo o en la escuela? Póngase en contacto con el soporte técnico en su trabajo o Universidad para realizar estos pasos.**</span><span class="sxs-lookup"><span data-stu-id="85f31-105">**Looking for how to delete your *own* Microsoft 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>|
   
## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="85f31-106">Información importante acerca de cómo eliminar usuarios</span><span class="sxs-lookup"><span data-stu-id="85f31-106">What you need to know about deleting users</span></span>

- <span data-ttu-id="85f31-107">Solo las personas que tienen permisos de [administrador global de Microsoft 365](about-admin-roles.md) o de administración de usuarios para la empresa o el centro educativo pueden eliminar cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="85f31-107">Only people who have [Microsoft 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span> 
    
- <span data-ttu-id="85f31-108">Tiene 30 días para [restaurar](restore-user.md) la cuenta antes de que los datos del usuario se eliminen de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="85f31-108">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span> 
    
- <span data-ttu-id="85f31-p102">Si desea conservar los datos del usuario de OneDrive, muévalos a otra ubicación. Incluso puede hacerlo hasta 30 días después de eliminar la cuenta. Vea [Acceder a los datos de usuario antiguos y realizar una copia de seguridad de ellos](get-access-to-and-back-up-a-former-user-s-data.md). No es necesario mover sus archivos de SharePoint, pues seguirá teniendo acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="85f31-p102">If you want to keep the user's OneDrive data, move it to a different location. You can even do this up to 30 days after deleting the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md). You don't need to move their SharePoint files; you'll still have access to them.</span></span>
    
- <span data-ttu-id="85f31-p103">Si desea mantener el correo electrónico del usuario, **ANTES** de eliminar la cuenta, mueva el correo electrónico a otra ubicación. Si ya ha eliminado la cuenta: si hace menos de 30 días puede restaurarla, mover los datos del correo y eliminarla. Vea cómo [acceder a los datos de un antiguo usuario y realizar copia de seguridad de ellos](get-access-to-and-back-up-a-former-user-s-data.md).</span><span class="sxs-lookup"><span data-stu-id="85f31-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
    
- <span data-ttu-id="85f31-116">Si tiene una suscripción de Enterprise como Office 365 Enterprise E3, puede conservar los datos de buzón de una cuenta de usuario eliminada convirtiéndola en un *buzón inactivo*.</span><span class="sxs-lookup"><span data-stu-id="85f31-116">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="85f31-117">Para obtener más información, vea [Administrar buzones inactivos en Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="85f31-117">To learn more, see [Manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span>


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="85f31-118">Administrador global: eliminar un usuario, dejar de pagar por su licencia y elegir qué hacer con el correo electrónico y el contenido de OneDrive</span><span class="sxs-lookup"><span data-stu-id="85f31-118">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="85f31-119">Si es un administrador global, al eliminar un usuario, también puede conceder a otro usuario acceso a su correo electrónico y elegir qué hacer con su contenido de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="85f31-119">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span> 

  
### <a name="things-to-consider"></a><span data-ttu-id="85f31-120">Aspectos que se deben tener en cuenta...</span><span class="sxs-lookup"><span data-stu-id="85f31-120">Things to consider...</span></span>

<span data-ttu-id="85f31-121">Antes de empezar, piense en lo que desea hacer con el correo electrónico del usuario y en el contenido de OneDrive, y si desea mantener la licencia o dejar de pagar por ella.</span><span class="sxs-lookup"><span data-stu-id="85f31-121">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="85f31-122">Licencias de producto</span><span class="sxs-lookup"><span data-stu-id="85f31-122">Product licenses</span></span>  <br/> |<span data-ttu-id="85f31-123">Puede quitar la licencia del usuario y quitarla de sus suscripciones para dejar de pagar por esa licencia.</span><span class="sxs-lookup"><span data-stu-id="85f31-123">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="85f31-124">Si selecciona esta opción, la licencia se quitará automáticamente de sus suscripciones.</span><span class="sxs-lookup"><span data-stu-id="85f31-124">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="85f31-125">**No puede quitar la licencia si la** compró a través de un partner o un licencia por volumen.</span><span class="sxs-lookup"><span data-stu-id="85f31-125">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="85f31-126">Si va a pagar por un plan anual o si se encuentra en medio de un ciclo de facturación, no podrá quitar la licencia de la suscripción hasta que se complete el compromiso.</span><span class="sxs-lookup"><span data-stu-id="85f31-126">If you are paying for an annual plan or if you are in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="85f31-127">Contenido de OneDrive</span><span class="sxs-lookup"><span data-stu-id="85f31-127">OneDrive content</span></span>  <br/> |<span data-ttu-id="85f31-128">Si el usuario guardó sus archivos en OneDrive, puede conceder a otro usuario acceso a estos archivos.</span><span class="sxs-lookup"><span data-stu-id="85f31-128">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="85f31-129">Deberá mover los archivos que quiera conservar dentro del período de retención establecido para los archivos de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="85f31-129">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="85f31-130">**De forma predeterminada, el período de retención es de 30 días.**</span><span class="sxs-lookup"><span data-stu-id="85f31-130">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="85f31-131">Si no mueve los archivos dentro del período de retención después de eliminar el usuario, el contenido de OneDrive se eliminará permanentemente.</span><span class="sxs-lookup"><span data-stu-id="85f31-131">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="85f31-132">Para aumentar el número de días que se conservan los archivos de OneDrive para las cuentas eliminadas, consulte [Set the onedrive Retention for Deleted users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).</span><span class="sxs-lookup"><span data-stu-id="85f31-132">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).</span></span>  <br/><br/> <span data-ttu-id="85f31-133">**¡Importante!**</span><span class="sxs-lookup"><span data-stu-id="85f31-133">**Important!**</span></span> <span data-ttu-id="85f31-134">Si el usuario eliminado usó un equipo personal para descargar archivos de SharePoint y OneDrive, no hay forma de borrar los archivos almacenados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="85f31-134">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="85f31-135">Seguirán teniendo acceso a todos los archivos que se hayan sincronizado desde OneDrive.</span><span class="sxs-lookup"><span data-stu-id="85f31-135">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="85f31-136">Correo electrónico</span><span class="sxs-lookup"><span data-stu-id="85f31-136">Email</span></span>  <br/> | <span data-ttu-id="85f31-137">Al conceder a otro usuario acceso al correo electrónico del usuario eliminado, se convertirá el buzón del usuario eliminado en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="85f31-137">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="85f31-138">El nuevo propietario del buzón puede tener acceso al buzón y supervisar el correo electrónico nuevo.</span><span class="sxs-lookup"><span data-stu-id="85f31-138">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="85f31-139">También tendrá las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="85f31-139">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="85f31-140">Cambiar el nombre para mostrar: se recomienda cambiar el nombre para mostrar para que sea fácil identificar el buzón compartido en la lista de usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="85f31-140">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the Active users list.</span></span>  <br/>  <span data-ttu-id="85f31-141">Activar respuestas automáticas: ya hemos escrito una respuesta automática de un educado por usted.</span><span class="sxs-lookup"><span data-stu-id="85f31-141">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="85f31-142">Puede enviar respuestas automáticas diferentes a personas de su organización y personas que no pertenezcan a su organización.</span><span class="sxs-lookup"><span data-stu-id="85f31-142">You can send a different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="85f31-143">Limpiar alias: los alias son direcciones de correo electrónico adicionales para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="85f31-143">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="85f31-144">Algunas organizaciones no las usan, por lo que, si no tiene ninguno, no es necesario que realice ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="85f31-144">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="85f31-145">Si el usuario tiene alias, le recomendamos que los quite para que pueda volver a usar esas direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="85f31-145">If the user does have aliases, we recommend removing them so that you can re-use those email addresses.</span></span> <span data-ttu-id="85f31-146">De lo contrario, no podrá volver a usar esas direcciones de correo electrónico hasta que transcurra el período de retención para los buzones eliminados.</span><span class="sxs-lookup"><span data-stu-id="85f31-146">Otherwise, you can't re-use those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="85f31-147">De forma predeterminada, un buzón eliminado es recuperable durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="85f31-147">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="85f31-148">Para obtener más información, vea [eliminar o restaurar buzones de usuario en Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span><span class="sxs-lookup"><span data-stu-id="85f31-148">For more information, see  [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="85f31-149">Active Directory</span><span class="sxs-lookup"><span data-stu-id="85f31-149">Active Directory</span></span>  <br/> |<span data-ttu-id="85f31-150">Si su empresa usa **Active Directory** que está sincronizando con Azure AD, debe eliminar la cuenta de usuario de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85f31-150">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="85f31-151">No podrá hacerlo a través de Office 365.</span><span class="sxs-lookup"><span data-stu-id="85f31-151">You can't do it through Office 365.</span></span> <span data-ttu-id="85f31-152">Para obtener instrucciones, consulte [eliminar una cuenta de usuario](https://go.microsoft.com/fwlink/p/?linkid=841808).</span><span class="sxs-lookup"><span data-stu-id="85f31-152">For instructions, see [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808).</span></span>  <br/> |
   
### <a name="get-started"></a><span data-ttu-id="85f31-153">Introducción</span><span class="sxs-lookup"><span data-stu-id="85f31-153">Get started</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="85f31-154">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="85f31-154">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="85f31-155">Dado que la experiencia guiada recorre los pasos para eliminar un usuario, esta es la manera de empezar.</span><span class="sxs-lookup"><span data-stu-id="85f31-155">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="85f31-156">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="85f31-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="85f31-157">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="85f31-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="85f31-158">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="85f31-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="85f31-159">Seleccione el usuario que desea eliminar y, a continuación, seleccione **eliminar usuario**.</span><span class="sxs-lookup"><span data-stu-id="85f31-159">Select the user you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="85f31-160">Administrador de administración de usuarios: eliminar uno o más usuarios de Office 365</span><span class="sxs-lookup"><span data-stu-id="85f31-160">User management admin: Delete one or more users from Office 365</span></span>


> [!IMPORTANT]
> <span data-ttu-id="85f31-161">No elimine una cuenta de usuario si la ha [convertido en un buzón compartido](../email/convert-user-mailbox-to-shared-mailbox.md) o si ha configurado el reenvío de correo electrónico en la cuenta.</span><span class="sxs-lookup"><span data-stu-id="85f31-161">Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account.</span></span> <span data-ttu-id="85f31-162">Estas funciones todavía necesitan la cuenta.</span><span class="sxs-lookup"><span data-stu-id="85f31-162">Those functions still need the account.</span></span> <span data-ttu-id="85f31-163">Un buzón compartido no requiere una licencia.</span><span class="sxs-lookup"><span data-stu-id="85f31-163">A shared mailbox doesn't require a license.</span></span> <span data-ttu-id="85f31-164">Si ha convertido la cuenta en un buzón compartido, puede [dejar de pagar por la licencia](#stop-paying-for-the-license).</span><span class="sxs-lookup"><span data-stu-id="85f31-164">If you've converted the account to a shared mailbox you can [Stop paying for the license](#stop-paying-for-the-license).</span></span> <span data-ttu-id="85f31-165">Si ha configurado el reenvío de correo electrónico en la cuenta, no podrá quitar la licencia.</span><span class="sxs-lookup"><span data-stu-id="85f31-165">If you've set up email forwarding on the account, you can't remove the license.</span></span> <span data-ttu-id="85f31-166">Al hacerlo, se detendrá el reenvío de correo y se desactivará el buzón.</span><span class="sxs-lookup"><span data-stu-id="85f31-166">Doing so will stop email forwarding and deactivate the mailbox.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="85f31-167">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="85f31-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="85f31-168">Seleccione los nombres de los usuarios que desea eliminar, seleccione **más opciones** (**...**) y, a continuación, elija **eliminar usuario**.</span><span class="sxs-lookup"><span data-stu-id="85f31-168">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="85f31-169">Aunque eliminó la cuenta del usuario, **aún está pagando por la licencia**.</span><span class="sxs-lookup"><span data-stu-id="85f31-169">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="85f31-170">Consulte el siguiente procedimiento para dejar de pagar por la licencia.</span><span class="sxs-lookup"><span data-stu-id="85f31-170">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="85f31-171">O bien, puede asignar la licencia a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="85f31-171">Or, you can assign the license to another user.</span></span> <span data-ttu-id="85f31-172">No se asignará a nadie automáticamente.</span><span class="sxs-lookup"><span data-stu-id="85f31-172">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="85f31-173">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="85f31-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="85f31-174">Seleccione los nombres de los usuarios que desea eliminar y, en el panel **acciones en masa** , elija **eliminar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="85f31-174">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="85f31-175">Aunque eliminó la cuenta del usuario, **aún está pagando por la licencia**.</span><span class="sxs-lookup"><span data-stu-id="85f31-175">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="85f31-176">Consulte el siguiente procedimiento para dejar de pagar por la licencia.</span><span class="sxs-lookup"><span data-stu-id="85f31-176">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="85f31-177">O bien, puede asignar la licencia a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="85f31-177">Or, you can assign the license to another user.</span></span> <span data-ttu-id="85f31-178">No se asignará a nadie automáticamente.</span><span class="sxs-lookup"><span data-stu-id="85f31-178">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="85f31-179">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="85f31-179">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="85f31-180">Seleccione los nombres de los usuarios que desea eliminar y, en el panel **acciones en masa** , elija **eliminar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="85f31-180">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="85f31-181">Aunque eliminó la cuenta del usuario, **aún está pagando por la licencia**.</span><span class="sxs-lookup"><span data-stu-id="85f31-181">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="85f31-182">Consulte el siguiente procedimiento para dejar de pagar por la licencia.</span><span class="sxs-lookup"><span data-stu-id="85f31-182">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="85f31-183">O bien, puede asignar la licencia a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="85f31-183">Or, you can assign the license to another user.</span></span> <span data-ttu-id="85f31-184">No se asignará a nadie automáticamente.</span><span class="sxs-lookup"><span data-stu-id="85f31-184">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="85f31-185">Dejar de pagar por la licencia</span><span class="sxs-lookup"><span data-stu-id="85f31-185">Stop paying for the license</span></span>

<span data-ttu-id="85f31-186">La reducción del número de licencias es un paso independiente que solo puede realizar el administrador global o el administrador de facturación.</span><span class="sxs-lookup"><span data-stu-id="85f31-186">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="85f31-187">En el centro de administración, vaya a **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Productos y servicios</a>.</span><span class="sxs-lookup"><span data-stu-id="85f31-187">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span> <span data-ttu-id="85f31-188">Si no ve esta opción, no es un administrador global o administrador de facturación y no puede realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="85f31-188">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="85f31-189">Seleccione la suscripción (si tiene más de una) y, a continuación, seleccione **Agregar o quitar licencias** para eliminar la licencia y no pagar por ella hasta que contrate a otra persona.</span><span class="sxs-lookup"><span data-stu-id="85f31-189">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="85f31-190">Más adelante, cuando siga los pasos para agregar a otra persona a su empresa, se le pedirá que compre una licencia al mismo tiempo, con un solo paso.</span><span class="sxs-lookup"><span data-stu-id="85f31-190">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="85f31-191">En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Suscripciones</a>.</span><span class="sxs-lookup"><span data-stu-id="85f31-191">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="85f31-192">Si no ve esta opción, no es un administrador global o administrador de facturación y no puede realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="85f31-192">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="85f31-193">Seleccione la suscripción (si tiene más de una) y, a continuación, seleccione **Agregar o quitar licencias** para eliminar la licencia y no pagar por ella hasta que contrate a otra persona.</span><span class="sxs-lookup"><span data-stu-id="85f31-193">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="85f31-194">Más adelante, cuando siga los pasos para agregar a otra persona a su empresa, se le pedirá que compre una licencia al mismo tiempo, con un solo paso.</span><span class="sxs-lookup"><span data-stu-id="85f31-194">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="85f31-195">En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Suscripciones</a>.</span><span class="sxs-lookup"><span data-stu-id="85f31-195">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="85f31-196">Si no ve esta opción, no es un administrador global o administrador de facturación y no puede realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="85f31-196">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="85f31-197">Seleccione la suscripción (si tiene más de una) y, a continuación, seleccione **Agregar o quitar licencias** para eliminar la licencia y no pagar por ella hasta que contrate a otra persona.</span><span class="sxs-lookup"><span data-stu-id="85f31-197">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="85f31-198">Más adelante, cuando siga los pasos para agregar a otra persona a su empresa, se le pedirá que compre una licencia al mismo tiempo, con un solo paso.</span><span class="sxs-lookup"><span data-stu-id="85f31-198">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="85f31-199">Eliminar varios usuarios al mismo tiempo</span><span class="sxs-lookup"><span data-stu-id="85f31-199">Delete many users at the same time</span></span>

<span data-ttu-id="85f31-200">Consulte el cmdlet [de PowerShell Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) .</span><span class="sxs-lookup"><span data-stu-id="85f31-200">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="85f31-201">Corregir problemas relacionados con la eliminación de un usuario</span><span class="sxs-lookup"><span data-stu-id="85f31-201">Fix issues with deleting a user</span></span>

<span data-ttu-id="85f31-202">Estos son los problemas más comunes que se encuentran los usuarios al eliminar un usuario:</span><span class="sxs-lookup"><span data-stu-id="85f31-202">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="85f31-203">**Recibe un mensaje de error similar a "No se puede eliminar el usuario. Inténtelo de nuevo más tarde".**</span><span class="sxs-lookup"><span data-stu-id="85f31-203">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="85f31-204">Compruebe de nuevo si se ha establecido una regla de reenvío de correo en la cuenta o si esta se convertido en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="85f31-204">Doublecheck whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="85f31-205">Ambas opciones causarán dicho error.</span><span class="sxs-lookup"><span data-stu-id="85f31-205">Both of these will cause that error.</span></span> <span data-ttu-id="85f31-206">No elimine la cuenta si tiene un reenvío de correo electrónico o se ha convertido en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="85f31-206">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="85f31-207">**No tiene los permisos adecuados para eliminar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="85f31-207">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="85f31-208">Solo los usuarios que son [administradores globales de Microsoft 365 o administradores de administración de usuarios](about-admin-roles.md) pueden eliminar usuarios.</span><span class="sxs-lookup"><span data-stu-id="85f31-208">Only people who are [Microsoft 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="85f31-209">Normalmente se trata del soporte técnico de su escuela o empresa.</span><span class="sxs-lookup"><span data-stu-id="85f31-209">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="85f31-p122">**Ha eliminado el usuario, pero el nombre todavía aparece en la libreta de direcciones global**. Esto ocurre cuando una empresa usa Active Directory. Debe eliminar la cuenta del usuario de Active Directory. Para obtener instrucciones, consulte este artículo de TechNet: [Eliminar una cuenta de usuario.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span><span class="sxs-lookup"><span data-stu-id="85f31-p122">**You delete the user but their name continues appear in your global address book**. This happens when a business is using Active Directory. You have to delete the users account from Active Directory. For instructions, see this TechNet article: [Delete a User Account.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span></span>

||
|:-----|
|<span data-ttu-id="85f31-214">**¿Desea eliminar Microsoft 365 del equipo? Vaya a [cancelar la suscripción](../../commerce/subscriptions/cancel-your-subscription.md).**</span><span class="sxs-lookup"><span data-stu-id="85f31-214">**Do you want to delete Microsoft 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="85f31-215">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="85f31-215">Related articles</span></span>

[<span data-ttu-id="85f31-216">Restaurar un usuario</span><span class="sxs-lookup"><span data-stu-id="85f31-216">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="85f31-217">Eliminar un buzón de forma permanente</span><span class="sxs-lookup"><span data-stu-id="85f31-217">Permanently delete a mailbox</span></span>](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[<span data-ttu-id="85f31-218">Quitar un antiguo empleado de Office 365</span><span class="sxs-lookup"><span data-stu-id="85f31-218">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="85f31-219">Agregar un nuevo empleado a Office 365</span><span class="sxs-lookup"><span data-stu-id="85f31-219">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="85f31-220">[Eliminar una cuenta de usuario](https://go.microsoft.com/fwlink/p/?linkid=841808): siga estas instrucciones si su empresa usa **Active** Directory que se está sincronizando con Azure ad.</span><span class="sxs-lookup"><span data-stu-id="85f31-220">[Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="85f31-221">No podrá hacerlo a través de Office 365.</span><span class="sxs-lookup"><span data-stu-id="85f31-221">You can't do it through Office 365.</span></span>