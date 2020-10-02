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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Aprenda a convertir un buzón privado en un buzón compartido al que puedan tener acceso varios usuarios. '
ms.openlocfilehash: 027236afb5a77e950083f254a154c491d6abc6ac
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341197"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="85a7a-103">Convertir un buzón de usuario en un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="85a7a-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="85a7a-104">Cuando se convierte el buzón de un usuario en un buzón compartido, se conservan todos los correos electrónicos y calendarios existentes.</span><span class="sxs-lookup"><span data-stu-id="85a7a-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="85a7a-105">Solo ahora está en un buzón compartido donde varias personas podrán tener acceso a él en lugar de una persona.</span><span class="sxs-lookup"><span data-stu-id="85a7a-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="85a7a-106">En una fecha posterior, puede volver a convertir un buzón de correo compartido en un buzón de usuario (privado).</span><span class="sxs-lookup"><span data-stu-id="85a7a-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="85a7a-107">**A continuación, se indican algunas cosas muy importantes que necesita saber:**</span><span class="sxs-lookup"><span data-stu-id="85a7a-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="85a7a-108">El buzón de usuario que está convirtiendo necesita una licencia asignada antes de convertirla en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="85a7a-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="85a7a-109">De lo contrario, no verá la opción para convertir el buzón.</span><span class="sxs-lookup"><span data-stu-id="85a7a-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="85a7a-110">Si ha quitado la licencia, agréguela de nuevo para que pueda convertir el buzón.</span><span class="sxs-lookup"><span data-stu-id="85a7a-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="85a7a-111">Después de convertir el buzón en uno compartido, puede quitar la licencia de la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="85a7a-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="85a7a-112">Los buzones compartidos pueden tener hasta 50 GB de datos sin una licencia asignada a ellos.</span><span class="sxs-lookup"><span data-stu-id="85a7a-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="85a7a-113">Para contener más datos de los que necesita, necesita una licencia asignada.</span><span class="sxs-lookup"><span data-stu-id="85a7a-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="85a7a-114">Es posible que deba eliminar un grupo de correos electrónicos grandes (por ejemplo, con datos adjuntos) del buzón compartido para reducirlo para que pueda quitar la licencia.</span><span class="sxs-lookup"><span data-stu-id="85a7a-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="85a7a-115">No elimine la cuenta de usuario antigua.</span><span class="sxs-lookup"><span data-stu-id="85a7a-115">Don't delete the old user's account.</span></span> <span data-ttu-id="85a7a-116">Esto es necesario para anclar el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="85a7a-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="85a7a-117">Si ya ha eliminado la cuenta de usuario, vea [convertir el buzón de un usuario eliminado](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="85a7a-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="85a7a-118">Las reglas permanecen intactas después de que el buzón se convierte en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="85a7a-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="85a7a-119">Usar el centro de administración de Exchange para convertir un buzón</span><span class="sxs-lookup"><span data-stu-id="85a7a-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="85a7a-120">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="85a7a-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="85a7a-121">Seleccione **Recipients** \> **buzones**de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="85a7a-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="85a7a-122">Seleccione el buzón de usuario.</span><span class="sxs-lookup"><span data-stu-id="85a7a-122">Select the user mailbox.</span></span> <span data-ttu-id="85a7a-123">En **convertir a buzón compartido**, seleccione **convertir**.</span><span class="sxs-lookup"><span data-stu-id="85a7a-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="85a7a-124">Si el buzón es inferior a 50 GB, puede quitar la [licencia del usuario](../manage/remove-licenses-from-users.md)y dejar de pagar por ella.</span><span class="sxs-lookup"><span data-stu-id="85a7a-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="85a7a-125">No elimine la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="85a7a-125">Don't delete the user's account.</span></span> <span data-ttu-id="85a7a-126">El buzón compartido lo necesita como un delimitador.</span><span class="sxs-lookup"><span data-stu-id="85a7a-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="85a7a-127">Si va a convertir el buzón de un empleado que abandona su organización, debe realizar pasos adicionales para asegurarse de que ya no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="85a7a-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="85a7a-128">Consulte [quitar un antiguo empleado de Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="85a7a-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="85a7a-129">No es necesario restablecer la contraseña del usuario durante la conversión de buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="85a7a-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="85a7a-130">Sin embargo, si no se restablece la contraseña, **el nombre de usuario y la contraseña originales seguirán funcionando** una vez finalizada la conversión del buzón.</span><span class="sxs-lookup"><span data-stu-id="85a7a-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="85a7a-131">Para todos los demás que necesite saber sobre los buzones compartidos, vea [About Shared mailboxes](about-shared-mailboxes.md) y [Create a Shared Mailbox](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="85a7a-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="85a7a-132">Los buzones compartidos no requieren una licencia independiente.</span><span class="sxs-lookup"><span data-stu-id="85a7a-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="85a7a-133">Sin embargo, si desea habilitar el archivado local o colocar una conservación local o una retención por juicio en un buzón compartido, debe asignar una licencia de Exchange Online plan 1 con archivado de Exchange online o Exchange Online plan 2 al buzón.</span><span class="sxs-lookup"><span data-stu-id="85a7a-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="85a7a-134">Convertir el buzón de un usuario eliminado</span><span class="sxs-lookup"><span data-stu-id="85a7a-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="85a7a-135">Supongamos que ha eliminado una cuenta de usuario y ahora desea convertir su buzón antiguo en un buzón de correo compartido.</span><span class="sxs-lookup"><span data-stu-id="85a7a-135">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="85a7a-136">Esto es lo que necesita hacer:</span><span class="sxs-lookup"><span data-stu-id="85a7a-136">Here's what you need to do:</span></span>

1. <span data-ttu-id="85a7a-137">[Restaurar la cuenta del usuario](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="85a7a-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="85a7a-138">Asegúrese de que se le ha asignado una licencia de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="85a7a-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="85a7a-139">Restablecer la contraseña del usuario.</span><span class="sxs-lookup"><span data-stu-id="85a7a-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="85a7a-140">Espere 20-30 minutos para que se vuelva a crear el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="85a7a-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="85a7a-141">Ahora siga las instrucciones que se indican en esta página para convertir su buzón de correo en un buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="85a7a-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="85a7a-142">Una vez hecho, puede quitar la licencia del buzón de correo del usuario.</span><span class="sxs-lookup"><span data-stu-id="85a7a-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="85a7a-143">No elimine el buzón de correo antiguo del usuario.</span><span class="sxs-lookup"><span data-stu-id="85a7a-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="85a7a-144">El buzón compartido lo necesita como un delimitador.</span><span class="sxs-lookup"><span data-stu-id="85a7a-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="85a7a-145">Agregar miembros al buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="85a7a-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="85a7a-146">Volver a convertir un buzón de correo compartido en un buzón de correo (privado) de un usuario</span><span class="sxs-lookup"><span data-stu-id="85a7a-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="85a7a-147">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="85a7a-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="85a7a-148">Seleccione **destinatarios** \> **compartidos**.</span><span class="sxs-lookup"><span data-stu-id="85a7a-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="85a7a-149">Seleccione el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="85a7a-149">Select the shared mailbox.</span></span> <span data-ttu-id="85a7a-150">En **convertir a buzón normal**, seleccione **convertir**.</span><span class="sxs-lookup"><span data-stu-id="85a7a-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="85a7a-151">Vuelva al centro de administración.</span><span class="sxs-lookup"><span data-stu-id="85a7a-151">Go back to the admin center.</span></span> <span data-ttu-id="85a7a-152">En **usuarios**, seleccione la cuenta de usuario asociada con el buzón compartido antiguo.</span><span class="sxs-lookup"><span data-stu-id="85a7a-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="85a7a-153">Asigne una licencia a la cuenta y restablezca la contraseña.</span><span class="sxs-lookup"><span data-stu-id="85a7a-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="85a7a-154">El buzón tardará unos minutos en configurarse, pero, después de eso, la persona que va a usar esa cuenta está lista.</span><span class="sxs-lookup"><span data-stu-id="85a7a-154">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="85a7a-155">Cuando inicien sesión, verán los elementos de calendario y correo electrónico que solían estar en el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="85a7a-155">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="85a7a-156">Convertir el buzón de un usuario en un entorno híbrido</span><span class="sxs-lookup"><span data-stu-id="85a7a-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="85a7a-157">Si este buzón compartido se encuentra en un entorno híbrido, se recomienda **encarecidamente** (casi necesario) que mueva el buzón de usuario de nuevo a local, convierta el buzón de correo del usuario en un buzón de correo compartido y, a continuación, vuelva a mover el buzón compartido a la nube.</span><span class="sxs-lookup"><span data-stu-id="85a7a-157">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="85a7a-158">Este es el motivo: Si convierte el buzón de correo en la nube, se puede convertir, pero local todavía considera que el buzón de correo es el buzón del usuario, porque la nueva realidad no se sincroniza de nuevo en local.</span><span class="sxs-lookup"><span data-stu-id="85a7a-158">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="85a7a-159">Normalmente esto no es un problema, pero hay algunos escenarios en los que los atributos locales (que consideran que el buzón de correo del usuario) pueden sobrescribir las nuevas versiones en la nube de esos atributos y, como resultado, el buzón de correo puede volver a convertirse.</span><span class="sxs-lookup"><span data-stu-id="85a7a-159">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="85a7a-160">Se trata de un problema porque los buzones de usuario requieren licencias **o se eliminan de forma Soft transcurridos 30 días**.</span><span class="sxs-lookup"><span data-stu-id="85a7a-160">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="85a7a-161">Hemos tratado la mayoría de los motivos por los que esto ocurre pero sigue teniendo lugar, aunque no con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="85a7a-161">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="85a7a-162">Es mejor estar seguro y volver a mover el buzón de correo a local, convertirlo y, a continuación, volver a mover el buzón compartido a la nube.</span><span class="sxs-lookup"><span data-stu-id="85a7a-162">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="85a7a-163">Esta solución recomendada no infringe el contrato de licencia de entornos híbridos porque la existencia de buzón de usuario local es solo temporal.</span><span class="sxs-lookup"><span data-stu-id="85a7a-163">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="85a7a-164">Infringirá su licencia si mantuvo el buzón de correo del usuario o el buzón compartido en su organización local y no lo devolvió a la nube.</span><span class="sxs-lookup"><span data-stu-id="85a7a-164">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="85a7a-165">Si es miembro del grupo de funciones administración de la organización o administración de destinatarios, puede usar el shell de administración de Exchange para cambiar el buzón de un usuario a un buzón compartido local.</span><span class="sxs-lookup"><span data-stu-id="85a7a-165">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="85a7a-166">Por ejemplo, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="85a7a-166">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="85a7a-167">Vea la solución alternativa en esta solución de soporte para instancias cuando los [buzones compartidos se convierten de forma inesperada en buzones de usuario](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span><span class="sxs-lookup"><span data-stu-id="85a7a-167">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="85a7a-168">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="85a7a-168">Related articles</span></span>

[<span data-ttu-id="85a7a-169">Acerca de los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="85a7a-169">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="85a7a-170">Crear un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="85a7a-170">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="85a7a-171">Configurar un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="85a7a-171">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="85a7a-172">Quitar la licencia de un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="85a7a-172">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="85a7a-173">Resolver problemas con los buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="85a7a-173">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
