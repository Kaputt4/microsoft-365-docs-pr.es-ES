---
title: Convertir un buzón de usuario en un buzón compartido
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Aprenda a convertir un buzón privado en un buzón compartido al que puedan tener acceso varios usuarios. '
ms.openlocfilehash: 481707b9d60d37b1d80d822467d17f66750f4f13
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255265"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="4a64a-103">Convertir un buzón de usuario en un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="4a64a-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="4a64a-104">Cuando se convierte el buzón de un usuario en un buzón compartido, se conservan todos los correos electrónicos y calendarios existentes.</span><span class="sxs-lookup"><span data-stu-id="4a64a-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="4a64a-105">Solo ahora está en un buzón compartido donde varias personas podrán tener acceso a él en lugar de una persona.</span><span class="sxs-lookup"><span data-stu-id="4a64a-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="4a64a-106">En una fecha posterior, puede volver a convertir un buzón de correo compartido en un buzón de usuario (privado).</span><span class="sxs-lookup"><span data-stu-id="4a64a-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="4a64a-107">**A continuación, se indican algunas cosas muy importantes que necesita saber:**</span><span class="sxs-lookup"><span data-stu-id="4a64a-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="4a64a-108">El buzón de usuario que está convirtiendo necesita una licencia asignada antes de convertirla en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4a64a-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="4a64a-109">De lo contrario, no verá la opción para convertir el buzón.</span><span class="sxs-lookup"><span data-stu-id="4a64a-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="4a64a-110">Si ha quitado la licencia, agréguela de nuevo para que pueda convertir el buzón.</span><span class="sxs-lookup"><span data-stu-id="4a64a-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="4a64a-111">Después de convertir el buzón en uno compartido, puede quitar la licencia de la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="4a64a-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="4a64a-112">Los buzones compartidos pueden tener hasta 50 GB de datos sin tener una licencia asignada a ellos.</span><span class="sxs-lookup"><span data-stu-id="4a64a-112">Shared mailboxes can have up to 50GB of data without a license assigned to them.</span></span> <span data-ttu-id="4a64a-113">Para contener más datos de los que necesita, necesita una licencia asignada.</span><span class="sxs-lookup"><span data-stu-id="4a64a-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="4a64a-114">Es posible que deba eliminar un grupo de correos electrónicos grandes (por ejemplo, con datos adjuntos) del buzón compartido para reducirlo para que pueda quitar la licencia.</span><span class="sxs-lookup"><span data-stu-id="4a64a-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="4a64a-115">No elimine la cuenta de usuario antigua.</span><span class="sxs-lookup"><span data-stu-id="4a64a-115">Don't delete the old user's account.</span></span> <span data-ttu-id="4a64a-116">Esto es necesario para anclar el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4a64a-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="4a64a-117">Si ya ha eliminado la cuenta de usuario, vea [convertir el buzón de un usuario eliminado](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="4a64a-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="4a64a-118">Las reglas permanecen intactas después de que el buzón se convierte en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4a64a-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="4a64a-119">Usar el centro de administración de Exchange para convertir un buzón</span><span class="sxs-lookup"><span data-stu-id="4a64a-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="4a64a-120">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="4a64a-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="4a64a-121">Seleccione **buzones**de **destinatarios** \> .</span><span class="sxs-lookup"><span data-stu-id="4a64a-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="4a64a-122">Seleccione el buzón de usuario.</span><span class="sxs-lookup"><span data-stu-id="4a64a-122">Select the user mailbox.</span></span> <span data-ttu-id="4a64a-123">En **convertir a buzón compartido**, seleccione **convertir**.</span><span class="sxs-lookup"><span data-stu-id="4a64a-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="4a64a-124">Si el buzón tiene un tamaño menor que 50 GB, puede quitar la [licencia del usuario](../manage/remove-licenses-from-users.md)y dejar de pagar por ella.</span><span class="sxs-lookup"><span data-stu-id="4a64a-124">If the mailbox is smaller than 50GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="4a64a-125">No elimine el buzón de correo antiguo del usuario.</span><span class="sxs-lookup"><span data-stu-id="4a64a-125">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="4a64a-126">El buzón compartido lo necesita como un delimitador.</span><span class="sxs-lookup"><span data-stu-id="4a64a-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="4a64a-127">Si va a convertir el buzón de un empleado que abandona su organización, debe realizar pasos adicionales para asegurarse de que ya no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="4a64a-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="4a64a-128">Consulte [quitar un antiguo empleado de Office 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="4a64a-128">Please see [Remove a former employee from Office 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="4a64a-129">Para todos los demás que necesite saber sobre los buzones compartidos, vea [About Shared mailboxes](about-shared-mailboxes.md) y [Create a Shared Mailbox](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="4a64a-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="4a64a-130">Usar el centro de administración de Microsoft 365 para convertir un buzón</span><span class="sxs-lookup"><span data-stu-id="4a64a-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4a64a-131">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="4a64a-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="4a64a-132">Seleccione el nombre del usuario cuyo buzón desea convertir.</span><span class="sxs-lookup"><span data-stu-id="4a64a-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="4a64a-133">Restablecer la contraseña del usuario.</span><span class="sxs-lookup"><span data-stu-id="4a64a-133">Reset the user's password.</span></span>

> [!NOTE]
> <span data-ttu-id="4a64a-134">No es necesario restablecer la contraseña del usuario durante la conversión de buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="4a64a-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="4a64a-135">Sin embargo, si no se restablece la contraseña, **el nombre de usuario y la contraseña originales seguirán funcionando** una vez finalizada la conversión del buzón.</span><span class="sxs-lookup"><span data-stu-id="4a64a-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="4a64a-136">En la ficha **correo** , en **más acciones**, seleccione **convertir a buzón compartido**.</span><span class="sxs-lookup"><span data-stu-id="4a64a-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4a64a-137">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="4a64a-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="4a64a-138">Seleccione el usuario cuyo buzón desea convertir.</span><span class="sxs-lookup"><span data-stu-id="4a64a-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="4a64a-139">En el panel derecho, expanda **configuración de correo**.</span><span class="sxs-lookup"><span data-stu-id="4a64a-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="4a64a-140">Junto a **configuración adicional**, seleccione **convertir a buzón compartido**.</span><span class="sxs-lookup"><span data-stu-id="4a64a-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4a64a-141">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="4a64a-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="4a64a-142">Seleccione el usuario cuyo buzón desea convertir.</span><span class="sxs-lookup"><span data-stu-id="4a64a-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="4a64a-143">En el panel derecho, expanda **configuración de correo**.</span><span class="sxs-lookup"><span data-stu-id="4a64a-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="4a64a-144">Junto a **configuración adicional**, seleccione **convertir a buzón compartido**.</span><span class="sxs-lookup"><span data-stu-id="4a64a-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="4a64a-145">Si el buzón tiene un tamaño menor que 50 GB, puede [quitar la licencia del usuario](../manage/remove-licenses-from-users.md)y dejar de pagar por ella.</span><span class="sxs-lookup"><span data-stu-id="4a64a-145">If the mailbox is smaller than 50GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="4a64a-146">No elimine el buzón de correo antiguo del usuario.</span><span class="sxs-lookup"><span data-stu-id="4a64a-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="4a64a-147">El buzón compartido lo necesita como un delimitador.</span><span class="sxs-lookup"><span data-stu-id="4a64a-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="4a64a-148">Si va a convertir el buzón de un empleado que abandona su organización, debe realizar pasos adicionales para asegurarse de que ya no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="4a64a-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="4a64a-149">Consulte [quitar un antiguo empleado de Office 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="4a64a-149">See [Remove a former employee from Office 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="4a64a-150">Para todos los demás que necesite saber sobre los buzones compartidos, vea [About Shared mailboxes](about-shared-mailboxes.md) y [Create a Shared Mailbox](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="4a64a-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="4a64a-151">Convertir el buzón de un usuario eliminado</span><span class="sxs-lookup"><span data-stu-id="4a64a-151">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="4a64a-152">Supongamos que ha eliminado una cuenta de usuario y ahora desea convertir su buzón antiguo en un buzón de correo compartido.</span><span class="sxs-lookup"><span data-stu-id="4a64a-152">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="4a64a-153">Esto es lo que necesita hacer:</span><span class="sxs-lookup"><span data-stu-id="4a64a-153">Here's what you need to do:</span></span>

1. <span data-ttu-id="4a64a-154">[Restaurar la cuenta del usuario](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="4a64a-154">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="4a64a-155">Asegúrese de que se le ha asignado una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a64a-155">Make sure an Office 365 license is assigned to it.</span></span>

3. <span data-ttu-id="4a64a-156">Restablecer la contraseña del usuario.</span><span class="sxs-lookup"><span data-stu-id="4a64a-156">Reset the user's password.</span></span>
    
4. <span data-ttu-id="4a64a-157">Espere 20-30 minutos para que se vuelva a crear el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="4a64a-157">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="4a64a-158">Ahora siga las instrucciones que se indican en esta página para convertir su buzón de correo en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4a64a-158">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="4a64a-159">Una vez hecho, puede quitar la licencia del buzón de correo del usuario.</span><span class="sxs-lookup"><span data-stu-id="4a64a-159">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="4a64a-160">No elimine el buzón de correo antiguo del usuario.</span><span class="sxs-lookup"><span data-stu-id="4a64a-160">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="4a64a-161">El buzón compartido lo necesita como un delimitador.</span><span class="sxs-lookup"><span data-stu-id="4a64a-161">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="4a64a-162">Agregar miembros al buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4a64a-162">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="4a64a-163">Volver a convertir un buzón de correo compartido en un buzón de correo (privado) de un usuario</span><span class="sxs-lookup"><span data-stu-id="4a64a-163">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="4a64a-164">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="4a64a-164">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="4a64a-165">Seleccione **destinatarios** \> **compartidos**.</span><span class="sxs-lookup"><span data-stu-id="4a64a-165">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="4a64a-166">Seleccione el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4a64a-166">Select the shared mailbox.</span></span> <span data-ttu-id="4a64a-167">En **convertir a buzón normal**, seleccione **convertir**.</span><span class="sxs-lookup"><span data-stu-id="4a64a-167">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="4a64a-168">Vuelva al centro de administración.</span><span class="sxs-lookup"><span data-stu-id="4a64a-168">Go back to the admin center.</span></span> <span data-ttu-id="4a64a-169">En **usuarios**, seleccione la cuenta de usuario asociada con el buzón compartido antiguo.</span><span class="sxs-lookup"><span data-stu-id="4a64a-169">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="4a64a-170">Asigne una licencia a la cuenta y restablezca la contraseña.</span><span class="sxs-lookup"><span data-stu-id="4a64a-170">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="4a64a-171">El buzón tardará unos minutos en configurarse, pero, después de eso, la persona que va a usar esa cuenta está lista.</span><span class="sxs-lookup"><span data-stu-id="4a64a-171">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="4a64a-172">Cuando inicien sesión, verán los elementos de calendario y correo electrónico que solían estar en el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="4a64a-172">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="4a64a-173">Convertir el buzón de un usuario en un entorno híbrido</span><span class="sxs-lookup"><span data-stu-id="4a64a-173">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="4a64a-174">Si este buzón compartido se encuentra en un entorno híbrido, se recomienda **encarecidamente** (casi necesario) que mueva el buzón de usuario de nuevo a local, convierta el buzón de correo del usuario en un buzón de correo compartido y, a continuación, vuelva a mover el buzón compartido a la nube.</span><span class="sxs-lookup"><span data-stu-id="4a64a-174">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span>

<span data-ttu-id="4a64a-175">Este es el motivo: Si convierte el buzón de correo en la nube, se puede convertir, pero local todavía considera que el buzón de correo es el buzón del usuario, porque la nueva realidad no se sincroniza de nuevo en local.</span><span class="sxs-lookup"><span data-stu-id="4a64a-175">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="4a64a-176">Normalmente esto no es un problema, pero hay algunos escenarios en los que los atributos locales (que consideran que el buzón de correo del usuario) pueden sobrescribir las nuevas versiones en la nube de esos atributos y, como resultado, el buzón de correo puede volver a convertirse.</span><span class="sxs-lookup"><span data-stu-id="4a64a-176">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="4a64a-177">Se trata de un problema porque los buzones de usuario requieren licencias **o se eliminan de forma Soft transcurridos 30 días**.</span><span class="sxs-lookup"><span data-stu-id="4a64a-177">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="4a64a-178">Hemos tratado la mayoría de los motivos por los que esto ocurre pero sigue teniendo lugar, aunque no con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="4a64a-178">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="4a64a-179">Es mejor ser seguro y volver a mover el buzón de correo a local.</span><span class="sxs-lookup"><span data-stu-id="4a64a-179">It's best to be safe and move the mailbox back to on-premises.</span></span>

> [!NOTE]
> <span data-ttu-id="4a64a-180">Si forma parte de la administración de la organización o de la administración de destinatarios, puede usar el shell de administración de Exchange para cambiar el buzón de un usuario a un buzón compartido local.</span><span class="sxs-lookup"><span data-stu-id="4a64a-180">If you are a part of Organization Management or Recipient Management, you can use the  Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="4a64a-181">Por ejemplo, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="4a64a-181">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="4a64a-182">Vea la solución alternativa en esta solución de soporte para instancias cuando los [buzones compartidos se convierten de forma inesperada en buzones de usuario](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span><span class="sxs-lookup"><span data-stu-id="4a64a-182">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="4a64a-183">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="4a64a-183">Related articles</span></span>

[<span data-ttu-id="4a64a-184">Acerca de los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="4a64a-184">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="4a64a-185">Crear un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="4a64a-185">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="4a64a-186">Configurar un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="4a64a-186">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="4a64a-187">Quitar una licencia de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="4a64a-187">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="4a64a-188">Resolver problemas con los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="4a64a-188">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
