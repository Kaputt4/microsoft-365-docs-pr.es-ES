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
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="d5082-103">Convertir un buzón de usuario en un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="d5082-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="d5082-104">Al convertir el buzón de un usuario en un buzón compartido, se conserva todo el correo electrónico y el calendario existentes.</span><span class="sxs-lookup"><span data-stu-id="d5082-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="d5082-105">Solo ahora está en un buzón compartido donde varias personas podrán acceder a él en lugar de a una persona.</span><span class="sxs-lookup"><span data-stu-id="d5082-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="d5082-106">En una fecha posterior, puede volver a convertir un buzón compartido en un buzón de usuario (privado).</span><span class="sxs-lookup"><span data-stu-id="d5082-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="d5082-107">**Estas son algunas cosas realmente importantes que necesita saber:**</span><span class="sxs-lookup"><span data-stu-id="d5082-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="d5082-108">El buzón de usuario que va a convertir necesita una licencia asignada antes de convertirlo en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="d5082-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="d5082-109">De lo contrario, no verá la opción de convertir el buzón.</span><span class="sxs-lookup"><span data-stu-id="d5082-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="d5082-110">Si ha quitado la licencia, vuelva a agregarla para poder convertir el buzón.</span><span class="sxs-lookup"><span data-stu-id="d5082-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="d5082-111">Después de convertir el buzón en uno compartido, puede quitar la licencia de la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="d5082-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="d5082-112">Los buzones compartidos pueden tener hasta 50 GB de datos sin tener asignada una licencia.</span><span class="sxs-lookup"><span data-stu-id="d5082-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="d5082-113">Para contener más datos, necesita una licencia asignada.</span><span class="sxs-lookup"><span data-stu-id="d5082-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="d5082-114">Es posible que tenga que eliminar un montón de correos electrónicos grandes (por ejemplo, mensajes con datos adjuntos) del buzón compartido para reducirlo para poder quitar la licencia.</span><span class="sxs-lookup"><span data-stu-id="d5082-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="d5082-115">No elimine la cuenta del usuario anterior.</span><span class="sxs-lookup"><span data-stu-id="d5082-115">Don't delete the old user's account.</span></span> <span data-ttu-id="d5082-116">Esto es necesario para delimitar el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="d5082-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="d5082-117">Si ya ha eliminado la cuenta de usuario, consulte [Convertir el buzón de un usuario eliminado.](#convert-the-mailbox-of-a-deleted-user)</span><span class="sxs-lookup"><span data-stu-id="d5082-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="d5082-118">Las reglas están intactas después de convertir el buzón en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="d5082-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="d5082-119">Usar el Centro de administración de Exchange para convertir un buzón</span><span class="sxs-lookup"><span data-stu-id="d5082-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="d5082-120">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="d5082-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="d5082-121">Seleccionar **buzones** \> **de destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="d5082-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="d5082-122">Seleccione el buzón de usuario.</span><span class="sxs-lookup"><span data-stu-id="d5082-122">Select the user mailbox.</span></span> <span data-ttu-id="d5082-123">En **Convertir a buzón compartido,** seleccione **Convertir**.</span><span class="sxs-lookup"><span data-stu-id="d5082-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="d5082-124">Si el buzón es inferior a 50 [](../manage/remove-licenses-from-users.md)GB, puede quitar la licencia del usuario y dejar de pagar por ella.</span><span class="sxs-lookup"><span data-stu-id="d5082-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="d5082-125">No elimines la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="d5082-125">Don't delete the user's account.</span></span> <span data-ttu-id="d5082-126">El buzón compartido lo necesita como delimitador.</span><span class="sxs-lookup"><span data-stu-id="d5082-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="d5082-127">Si va a convertir el buzón de un empleado que abandona la organización, debe realizar pasos adicionales para asegurarse de que ya no puedan iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="d5082-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="d5082-128">Consulte Quitar [un antiguo empleado de Microsoft 365.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="d5082-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="d5082-129">No es necesario restablecer la contraseña del usuario durante la conversión del buzón.</span><span class="sxs-lookup"><span data-stu-id="d5082-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="d5082-130">Sin embargo, si no se restablece la contraseña, el nombre de usuario y la contraseña **originales** seguirán funcionando una vez finalizada la conversión del buzón.</span><span class="sxs-lookup"><span data-stu-id="d5082-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="d5082-131">Para todo lo que necesita saber sobre los buzones compartidos, consulte Acerca de los buzones [compartidos](about-shared-mailboxes.md) y [Crear un buzón compartido.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="d5082-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d5082-132">Los buzones compartidos no requieren una licencia independiente.</span><span class="sxs-lookup"><span data-stu-id="d5082-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="d5082-133">Sin embargo, si desea habilitar In-Place Archive o poner una retención In-Place o una retención por juicio en un buzón compartido, debe asignar una licencia de Exchange Online Plan 1 con Archivado de Exchange Online o Exchange Online Plan 2 al buzón.</span><span class="sxs-lookup"><span data-stu-id="d5082-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="d5082-134">Convertir el buzón de un usuario eliminado</span><span class="sxs-lookup"><span data-stu-id="d5082-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="d5082-135">Supongamos que ha eliminado una cuenta de usuario y ahora quiere convertir su buzón antiguo en un buzón de recursos compartidos.</span><span class="sxs-lookup"><span data-stu-id="d5082-135">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="d5082-136">Esto es lo que debe hacer:</span><span class="sxs-lookup"><span data-stu-id="d5082-136">Here's what you need to do:</span></span>

1. <span data-ttu-id="d5082-137">[Restaure la cuenta del usuario.](../add-users/restore-user.md)</span><span class="sxs-lookup"><span data-stu-id="d5082-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="d5082-138">Asegúrese de que tiene asignada una licencia de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5082-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="d5082-139">Restablezca la contraseña del usuario.</span><span class="sxs-lookup"><span data-stu-id="d5082-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="d5082-140">Espere entre 20 y 30 minutos para volver a crear su buzón.</span><span class="sxs-lookup"><span data-stu-id="d5082-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="d5082-141">Ahora siga las instrucciones de esta página para convertir su buzón en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="d5082-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="d5082-142">Una vez hecho esto, puede quitar la licencia del buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="d5082-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="d5082-143">No elimine el buzón antiguo del usuario.</span><span class="sxs-lookup"><span data-stu-id="d5082-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="d5082-144">El buzón compartido lo necesita como delimitador.</span><span class="sxs-lookup"><span data-stu-id="d5082-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="d5082-145">Agregue miembros al buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="d5082-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="d5082-146">Volver a convertir un buzón compartido en el buzón (privado) de un usuario</span><span class="sxs-lookup"><span data-stu-id="d5082-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="d5082-147">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="d5082-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="d5082-148">Seleccionar **destinatarios** \> **compartidos**.</span><span class="sxs-lookup"><span data-stu-id="d5082-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="d5082-149">Seleccione el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="d5082-149">Select the shared mailbox.</span></span> <span data-ttu-id="d5082-150">En **Convertir a buzón normal,** seleccione **Convertir**.</span><span class="sxs-lookup"><span data-stu-id="d5082-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="d5082-151">Vuelva al centro de administración.</span><span class="sxs-lookup"><span data-stu-id="d5082-151">Go back to the admin center.</span></span> <span data-ttu-id="d5082-152">En **Usuarios,** elija la cuenta de usuario asociada con el buzón compartido antiguo.</span><span class="sxs-lookup"><span data-stu-id="d5082-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="d5082-153">Asigne una licencia a la cuenta y restablezca la contraseña.</span><span class="sxs-lookup"><span data-stu-id="d5082-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="d5082-154">El buzón de correo puede tardar unos minutos en configurarse, pero después de eso, la persona que va a usar esa cuenta está lista para empezar.</span><span class="sxs-lookup"><span data-stu-id="d5082-154">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="d5082-155">Cuando inicien sesión, verán el correo electrónico y los elementos del calendario que solían estar en el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="d5082-155">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="d5082-156">Convertir el buzón de un usuario en un entorno híbrido</span><span class="sxs-lookup"><span data-stu-id="d5082-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="d5082-157">Para obtener más información sobre cómo convertir un buzón de usuario en un buzón compartido en un entorno híbrido de Exchange, vea:</span><span class="sxs-lookup"><span data-stu-id="d5082-157">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="d5082-158">Cmdlets para crear o modificar un buzón compartido remoto en un entorno de Exchange local</span><span class="sxs-lookup"><span data-stu-id="d5082-158">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="d5082-159">Los buzones compartidos se convierten inesperadamente en buzones de usuario después de que se ejecute la sincronización de directorios en una implementación híbrida de Exchange</span><span class="sxs-lookup"><span data-stu-id="d5082-159">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](https://docs.microsoft.com/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="d5082-160">Si es miembro del grupo de roles Administración de la organización o Administración de destinatarios, puede usar el Shell de administración de Exchange para cambiar un buzón de usuario a un buzón compartido local.</span><span class="sxs-lookup"><span data-stu-id="d5082-160">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="d5082-161">Por ejemplo, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="d5082-161">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d5082-162">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="d5082-162">Related articles</span></span>

[<span data-ttu-id="d5082-163">Acerca de los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="d5082-163">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="d5082-164">Crear un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="d5082-164">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="d5082-165">Configurar un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="d5082-165">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="d5082-166">Quitar la licencia de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="d5082-166">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="d5082-167">Resolver problemas con los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="d5082-167">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
