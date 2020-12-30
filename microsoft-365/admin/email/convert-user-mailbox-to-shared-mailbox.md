---
title: Convertir un buzón de usuario en un buzón compartido
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Aprenda a convertir un buzón privado en un buzón compartido al que puedan tener acceso varios usuarios. '
ms.openlocfilehash: f716bbd16be9f67189b19358ddf16a289f57f8e7
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2020
ms.locfileid: "49737970"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="11d51-103">Convertir un buzón de usuario en un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="11d51-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="11d51-104">Cuando se convierte el buzón de un usuario en un buzón compartido, se conservan todos los correos electrónicos y calendarios existentes.</span><span class="sxs-lookup"><span data-stu-id="11d51-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="11d51-105">Solo ahora está en un buzón compartido donde varias personas podrán tener acceso a él en lugar de una persona.</span><span class="sxs-lookup"><span data-stu-id="11d51-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="11d51-106">En una fecha posterior, puede volver a convertir un buzón de correo compartido en un buzón de usuario (privado).</span><span class="sxs-lookup"><span data-stu-id="11d51-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="11d51-107">**A continuación, se indican algunas cosas muy importantes que necesita saber:**</span><span class="sxs-lookup"><span data-stu-id="11d51-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="11d51-108">El buzón de usuario que está convirtiendo necesita una licencia asignada antes de convertirla en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="11d51-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="11d51-109">De lo contrario, no verá la opción para convertir el buzón.</span><span class="sxs-lookup"><span data-stu-id="11d51-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="11d51-110">Si ha quitado la licencia, agréguela de nuevo para que pueda convertir el buzón.</span><span class="sxs-lookup"><span data-stu-id="11d51-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="11d51-111">Después de convertir el buzón en uno compartido, puede quitar la licencia de la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="11d51-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="11d51-112">Los buzones compartidos pueden tener hasta 50 GB de datos sin una licencia asignada a ellos.</span><span class="sxs-lookup"><span data-stu-id="11d51-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="11d51-113">Para contener más datos de los que necesita, necesita una licencia asignada.</span><span class="sxs-lookup"><span data-stu-id="11d51-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="11d51-114">Es posible que deba eliminar un grupo de correos electrónicos grandes (por ejemplo, con datos adjuntos) del buzón compartido para reducirlo para que pueda quitar la licencia.</span><span class="sxs-lookup"><span data-stu-id="11d51-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="11d51-115">No elimine la cuenta de usuario antigua.</span><span class="sxs-lookup"><span data-stu-id="11d51-115">Don't delete the old user's account.</span></span> <span data-ttu-id="11d51-116">Esto es necesario para anclar el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="11d51-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="11d51-117">Si ya ha eliminado la cuenta de usuario, vea [convertir el buzón de un usuario eliminado](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="11d51-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="11d51-118">Las reglas permanecen intactas después de que el buzón se convierte en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="11d51-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="11d51-119">Usar el centro de administración de Exchange para convertir un buzón</span><span class="sxs-lookup"><span data-stu-id="11d51-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="11d51-120">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="11d51-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="11d51-121">Seleccione  \> **buzones** de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="11d51-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="11d51-122">Seleccione el buzón de usuario.</span><span class="sxs-lookup"><span data-stu-id="11d51-122">Select the user mailbox.</span></span> <span data-ttu-id="11d51-123">En **convertir a buzón compartido**, seleccione **convertir**.</span><span class="sxs-lookup"><span data-stu-id="11d51-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="11d51-124">Si el buzón es inferior a 50 GB, puede quitar la [licencia del usuario](../manage/remove-licenses-from-users.md)y dejar de pagar por ella.</span><span class="sxs-lookup"><span data-stu-id="11d51-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="11d51-125">No elimine la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="11d51-125">Don't delete the user's account.</span></span> <span data-ttu-id="11d51-126">El buzón compartido lo necesita como un delimitador.</span><span class="sxs-lookup"><span data-stu-id="11d51-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="11d51-127">Si va a convertir el buzón de un empleado que abandona su organización, debe realizar pasos adicionales para asegurarse de que ya no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="11d51-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="11d51-128">Consulte [quitar un antiguo empleado de Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="11d51-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="11d51-129">No es necesario restablecer la contraseña del usuario durante la conversión de buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="11d51-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="11d51-130">Sin embargo, si no se restablece la contraseña, **el nombre de usuario y la contraseña originales seguirán funcionando** una vez finalizada la conversión del buzón.</span><span class="sxs-lookup"><span data-stu-id="11d51-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="11d51-131">Para todos los demás que necesite saber sobre los buzones compartidos, vea [About Shared mailboxes](about-shared-mailboxes.md) y [Create a Shared Mailbox](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="11d51-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="11d51-132">Los buzones compartidos no requieren una licencia independiente.</span><span class="sxs-lookup"><span data-stu-id="11d51-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="11d51-133">Sin embargo, si desea habilitar In-Place archivo o poner una retención de In-Place o una retención por juicio en un buzón compartido, debe asignar una licencia de Exchange Online plan 1 con archivado de Exchange online o Exchange Online plan 2 al buzón.</span><span class="sxs-lookup"><span data-stu-id="11d51-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="11d51-134">Convertir el buzón de un usuario eliminado</span><span class="sxs-lookup"><span data-stu-id="11d51-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="11d51-135">Supongamos que ha eliminado una cuenta de usuario y ahora desea convertir su buzón antiguo en un buzón de correo compartido.</span><span class="sxs-lookup"><span data-stu-id="11d51-135">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="11d51-136">Esto es lo que necesita hacer:</span><span class="sxs-lookup"><span data-stu-id="11d51-136">Here's what you need to do:</span></span>

1. <span data-ttu-id="11d51-137">[Restaurar la cuenta del usuario](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="11d51-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="11d51-138">Asegúrese de que se le ha asignado una licencia de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="11d51-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="11d51-139">Restablecer la contraseña del usuario.</span><span class="sxs-lookup"><span data-stu-id="11d51-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="11d51-140">Espere 20-30 minutos para que se vuelva a crear el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="11d51-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="11d51-141">Ahora siga las instrucciones que se indican en esta página para convertir su buzón de correo en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="11d51-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="11d51-142">Una vez hecho, puede quitar la licencia del buzón de correo del usuario.</span><span class="sxs-lookup"><span data-stu-id="11d51-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="11d51-143">No elimine el buzón de correo antiguo del usuario.</span><span class="sxs-lookup"><span data-stu-id="11d51-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="11d51-144">El buzón compartido lo necesita como un delimitador.</span><span class="sxs-lookup"><span data-stu-id="11d51-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="11d51-145">Agregar miembros al buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="11d51-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="11d51-146">Volver a convertir un buzón de correo compartido en un buzón de correo (privado) de un usuario</span><span class="sxs-lookup"><span data-stu-id="11d51-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="11d51-147">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="11d51-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="11d51-148">Seleccione **destinatarios** \> **compartidos**.</span><span class="sxs-lookup"><span data-stu-id="11d51-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="11d51-149">Seleccione el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="11d51-149">Select the shared mailbox.</span></span> <span data-ttu-id="11d51-150">En **convertir a buzón normal**, seleccione **convertir**.</span><span class="sxs-lookup"><span data-stu-id="11d51-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="11d51-151">Vuelva al centro de administración.</span><span class="sxs-lookup"><span data-stu-id="11d51-151">Go back to the admin center.</span></span> <span data-ttu-id="11d51-152">En **usuarios**, seleccione la cuenta de usuario asociada con el buzón compartido antiguo.</span><span class="sxs-lookup"><span data-stu-id="11d51-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="11d51-153">Asigne una licencia a la cuenta y restablezca la contraseña.</span><span class="sxs-lookup"><span data-stu-id="11d51-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="11d51-154">El buzón tardará unos minutos en configurarse, pero, después de eso, la persona que va a usar esa cuenta está lista.</span><span class="sxs-lookup"><span data-stu-id="11d51-154">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="11d51-155">Cuando inicien sesión, verán los elementos de calendario y correo electrónico que solían estar en el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="11d51-155">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="11d51-156">Convertir el buzón de un usuario en un entorno híbrido</span><span class="sxs-lookup"><span data-stu-id="11d51-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="11d51-157">Para obtener más información sobre cómo convertir un buzón de usuario en un buzón compartido en un entorno híbrido de Exchange, consulte:</span><span class="sxs-lookup"><span data-stu-id="11d51-157">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="11d51-158">Cmdlets para crear o modificar un buzón de correo compartido remoto en un entorno de Exchange local</span><span class="sxs-lookup"><span data-stu-id="11d51-158">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="11d51-159">Los buzones compartidos se convierten inesperadamente en buzones de usuario después de ejecutar la sincronización de directorios en una implementación híbrida de Exchange</span><span class="sxs-lookup"><span data-stu-id="11d51-159">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](https://docs.microsoft.com/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="11d51-160">Si es miembro del grupo de funciones administración de la organización o administración de destinatarios, puede usar el shell de administración de Exchange para cambiar el buzón de un usuario a un buzón compartido local.</span><span class="sxs-lookup"><span data-stu-id="11d51-160">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="11d51-161">Por ejemplo, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="11d51-161">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-articles"></a><span data-ttu-id="11d51-162">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="11d51-162">Related articles</span></span>

[<span data-ttu-id="11d51-163">Acerca de los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="11d51-163">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="11d51-164">Crear un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="11d51-164">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="11d51-165">Configurar un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="11d51-165">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="11d51-166">Quitar la licencia de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="11d51-166">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="11d51-167">Resolver problemas con los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="11d51-167">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
