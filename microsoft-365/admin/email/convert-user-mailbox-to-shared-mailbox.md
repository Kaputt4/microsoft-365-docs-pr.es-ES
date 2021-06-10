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
description: 'Aprenda a convertir un buzón privado en un buzón compartido al que puedan tener acceso varias personas en lugar de solo una persona. '
ms.openlocfilehash: 0beb85e5a69b72bcd244cd654c399e91ded06ba7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635479"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="4cd5e-103">Convertir un buzón de usuario en un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="4cd5e-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="4cd5e-104">Al convertir el buzón de un usuario en un buzón compartido, se conserva todo el correo electrónico y el calendario existentes.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="4cd5e-105">Solo ahora está en un buzón compartido en el que varias personas podrán tener acceso a él en lugar de una persona.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="4cd5e-106">En una fecha posterior, puede volver a convertir un buzón compartido en un buzón de usuario (privado).</span><span class="sxs-lookup"><span data-stu-id="4cd5e-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4cd5e-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="4cd5e-107">Before you begin</span></span>

<span data-ttu-id="4cd5e-108">**Estas son algunas cosas realmente importantes que necesita saber:**</span><span class="sxs-lookup"><span data-stu-id="4cd5e-108">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="4cd5e-109">El buzón de usuario que está convirtiendo necesita una licencia asignada antes de convertirlo en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-109">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="4cd5e-110">De lo contrario, no verá la opción para convertir el buzón.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-110">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="4cd5e-111">Si ha quitado la licencia, vuelva a agregarla para poder convertir el buzón.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-111">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="4cd5e-112">Después de convertir el buzón en uno compartido, puede quitar la licencia de la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-112">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="4cd5e-113">Los buzones compartidos pueden tener hasta 50 GB de datos sin una licencia asignada.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-113">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="4cd5e-114">Para contener más datos que eso, necesita una licencia asignada.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-114">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="4cd5e-115">Es posible que deba eliminar un montón de correos electrónicos grandes (por ejemplo, los que tienen datos adjuntos) del buzón compartido para reducirlo para poder quitar la licencia.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-115">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="4cd5e-116">No elimine la cuenta del usuario anterior.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-116">Don't delete the old user's account.</span></span> <span data-ttu-id="4cd5e-117">Eso es necesario para delimitar el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-117">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="4cd5e-118">Si ya eliminó la cuenta de usuario, vea [Convertir el buzón de un usuario eliminado.](#convert-the-mailbox-of-a-deleted-user)</span><span class="sxs-lookup"><span data-stu-id="4cd5e-118">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="4cd5e-119">Las reglas están intactas después de convertir el buzón en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-119">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="4cd5e-120">Usar el Centro Exchange administración para convertir un buzón</span><span class="sxs-lookup"><span data-stu-id="4cd5e-120">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="4cd5e-121">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="4cd5e-122">Seleccione **Destinatarios** \> **Buzones**.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-122">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="4cd5e-123">Seleccione el buzón de usuario.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-123">Select the user mailbox.</span></span> <span data-ttu-id="4cd5e-124">En **Convertir a buzón compartido,** seleccione **Convertir**.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-124">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="4cd5e-125">Si el buzón es inferior a 50 [](../manage/remove-licenses-from-users.md)GB, puede quitar la licencia del usuario y dejar de pagarla.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-125">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="4cd5e-126">No elimine la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-126">Don't delete the user's account.</span></span> <span data-ttu-id="4cd5e-127">El buzón compartido lo necesita allí como delimitador.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-127">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="4cd5e-128">Si va a convertir el buzón de un empleado que abandona la organización, debe seguir pasos adicionales para asegurarse de que ya no puedan iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-128">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="4cd5e-129">Consulte [Quitar un antiguo empleado de Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="4cd5e-129">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="4cd5e-130">No es necesario restablecer la contraseña del usuario durante la conversión del buzón.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-130">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="4cd5e-131">Sin embargo, si la contraseña no se restablece, el nombre de usuario y la contraseña originales siguen **funcionando** una vez finalizada la conversión del buzón.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-131">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="4cd5e-132">Para todo lo demás que necesita saber acerca de los buzones compartidos, vea Acerca de los buzones [compartidos](about-shared-mailboxes.md) y [Crear un buzón compartido.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="4cd5e-132">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4cd5e-133">Los buzones compartidos no requieren una licencia independiente.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-133">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="4cd5e-134">Sin embargo, si desea habilitar In-Place Archive o poner una retención de In-Place o una retención por juicio en un buzón compartido, debe asignar una licencia del Plan 1 de Exchange Online con una licencia del Plan 2 Archivado de Exchange Online o Exchange Online al buzón.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-134">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>

## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="4cd5e-135">Convertir el buzón de un usuario eliminado</span><span class="sxs-lookup"><span data-stu-id="4cd5e-135">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="4cd5e-136">Supongamos que ha eliminado una cuenta de usuario y ahora desea convertir su buzón antiguo en un buzón de recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-136">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="4cd5e-137">Esto es lo que debe hacer:</span><span class="sxs-lookup"><span data-stu-id="4cd5e-137">Here's what you need to do:</span></span>

1. <span data-ttu-id="4cd5e-138">[Restaurar la cuenta del usuario](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="4cd5e-138">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="4cd5e-139">Asegúrese de que Microsoft 365 licencia de usuario está asignada.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-139">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="4cd5e-140">Restablezca la contraseña del usuario.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-140">Reset the user's password.</span></span>
    
4. <span data-ttu-id="4cd5e-141">Espere entre 20 y 30 minutos para volver a crear su buzón.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-141">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="4cd5e-142">Ahora siga las instrucciones de esta página para convertir su buzón en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-142">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="4cd5e-143">Una vez hecho esto, puede quitar la licencia del buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-143">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="4cd5e-144">No elimine el buzón antiguo del usuario.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-144">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="4cd5e-145">El buzón compartido lo necesita allí como delimitador.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-145">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="4cd5e-146">Agregue miembros al buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-146">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="4cd5e-147">Convertir un buzón compartido de nuevo en el buzón (privado) de un usuario</span><span class="sxs-lookup"><span data-stu-id="4cd5e-147">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="4cd5e-148">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-148">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="4cd5e-149">Seleccione **Destinatarios** \> **compartidos**.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-149">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="4cd5e-150">Seleccione el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-150">Select the shared mailbox.</span></span> <span data-ttu-id="4cd5e-151">En **Convertir a buzón normal,** seleccione **Convertir**.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-151">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="4cd5e-152">Vuelva al Centro de administración.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-152">Go back to the admin center.</span></span> <span data-ttu-id="4cd5e-153">En **Usuarios,** elija la cuenta de usuario asociada al buzón compartido anterior.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-153">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="4cd5e-154">Asigne una licencia a la cuenta y restablezca la contraseña.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-154">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="4cd5e-155">El buzón de correo tardará unos minutos en configurarse, pero después de eso, la persona que va a usar esa cuenta está lista para usarse.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-155">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="4cd5e-156">Cuando inicien sesión, verán los elementos de correo electrónico y calendario que solían estar en el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-156">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="4cd5e-157">Convertir el buzón de un usuario en un entorno híbrido</span><span class="sxs-lookup"><span data-stu-id="4cd5e-157">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="4cd5e-158">Para obtener más información sobre cómo convertir un buzón de usuario en un buzón compartido en un Exchange híbrido, vea:</span><span class="sxs-lookup"><span data-stu-id="4cd5e-158">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="4cd5e-159">Cmdlets para crear o modificar un buzón compartido remoto en un entorno Exchange local</span><span class="sxs-lookup"><span data-stu-id="4cd5e-159">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="4cd5e-160">Los buzones compartidos se convierten inesperadamente en buzones de usuario después de que se ejecute la sincronización de directorios Exchange implementación híbrida</span><span class="sxs-lookup"><span data-stu-id="4cd5e-160">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="4cd5e-161">Si es miembro del grupo de roles Administración de la organización o Administración de destinatarios, puede usar el Shell de administración de Exchange para cambiar un buzón de usuario a un buzón compartido local.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-161">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="4cd5e-162">Por ejemplo, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="4cd5e-162">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-content"></a><span data-ttu-id="4cd5e-163">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="4cd5e-163">Related content</span></span>

<span data-ttu-id="4cd5e-164">[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="4cd5e-164">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="4cd5e-165">[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="4cd5e-165">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4cd5e-166">[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="4cd5e-166">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4cd5e-167">[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="4cd5e-167">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4cd5e-168">[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="4cd5e-168">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>