---
title: Establecer la configuración de buzón compartido
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Cree un buzón compartido y configure algunas opciones para sus usuarios, como el reenvío de correo electrónico y las respuestas automáticas.
ms.openlocfilehash: ab23353f07a24f06d43172e8087819dd915ab720
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582673"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="cbc52-103">Establecer la configuración de buzón compartido</span><span class="sxs-lookup"><span data-stu-id="cbc52-103">Configure shared mailbox settings</span></span>

<span data-ttu-id="cbc52-104">Después de crear [un buzón](create-a-shared-mailbox.md)compartido, querrá configurar algunas opciones para los usuarios del buzón, como el reenvío de correo electrónico y las respuestas automáticas.</span><span class="sxs-lookup"><span data-stu-id="cbc52-104">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="cbc52-105">Más adelante, es posible que desee cambiar otras opciones de configuración, como el nombre del buzón, los miembros o los permisos de miembro.</span><span class="sxs-lookup"><span data-stu-id="cbc52-105">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="cbc52-106">Cambiar el nombre o el alias de correo electrónico de un buzón compartido o cambiar la dirección de correo electrónico principal</span><span class="sxs-lookup"><span data-stu-id="cbc52-106">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="cbc52-107">En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.</span><span class="sxs-lookup"><span data-stu-id="cbc52-107">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="cbc52-108">Seleccione el buzón compartido que desea editar y, a continuación, **seleccione Editar** junto a **Nombre, Correo electrónico, Alias de correo electrónico.**</span><span class="sxs-lookup"><span data-stu-id="cbc52-108">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="cbc52-109">Escriba un nuevo nombre o agregue otro alias.</span><span class="sxs-lookup"><span data-stu-id="cbc52-109">Enter a new name, or add another alias.</span></span> <span data-ttu-id="cbc52-110">Si desea cambiar la dirección de correo electrónico principal, el buzón debe tener más de un alias de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="cbc52-110">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="cbc52-111">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-111">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="cbc52-112">Reenviar mensajes de correo electrónico que se envían a un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="cbc52-112">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="cbc52-113">No es necesario asignar una licencia al buzón compartido para reenviar el correo electrónico que se le ha enviado.</span><span class="sxs-lookup"><span data-stu-id="cbc52-113">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="cbc52-114">Puede reenviar los mensajes a cualquier dirección de correo electrónico o lista de distribución válida.</span><span class="sxs-lookup"><span data-stu-id="cbc52-114">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="cbc52-115">En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.</span><span class="sxs-lookup"><span data-stu-id="cbc52-115">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="cbc52-116">Seleccione el buzón compartido que desea editar y, a continuación, **seleccione Reenvío de correo electrónico** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-116">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="cbc52-117">Establezca la alternancia en **On** y escriba una dirección de correo electrónico a la que reenviar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="cbc52-117">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="cbc52-118">Puede ser cualquier dirección de correo electrónico válida.</span><span class="sxs-lookup"><span data-stu-id="cbc52-118">It can be any valid email address.</span></span> <span data-ttu-id="cbc52-119">Para reenviar a varias direcciones, debe crear un grupo de distribución para las direcciones y, [a](/office365/admin/setup/create-distribution-lists) continuación, escriba el nombre del grupo en este cuadro.</span><span class="sxs-lookup"><span data-stu-id="cbc52-119">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="cbc52-120">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-120">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="cbc52-121">Enviar respuestas automáticas desde un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="cbc52-121">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="cbc52-122">En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.</span><span class="sxs-lookup"><span data-stu-id="cbc52-122">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="cbc52-123">Seleccione el buzón compartido que desea editar y, a continuación, **seleccione Respuestas automáticas** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-123">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="cbc52-124">Establezca el botón de alternancia en **Activado** y elija si desea enviar la respuesta a las personas de su organización o de fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="cbc52-124">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="cbc52-p105">Escriba la respuesta que desee enviar a personas dentro de su organización. No puede agregar imágenes, solo texto.</span><span class="sxs-lookup"><span data-stu-id="cbc52-p105">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="cbc52-127">Si también desea enviar *una* respuesta a personas fuera de su organización, active la casilla, quién desea obtener la respuesta y escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="cbc52-127">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="cbc52-128">No hay forma de enviar solo a las personas de fuera de la organización pero no a las personas de dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="cbc52-128">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="cbc52-129">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-129">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="cbc52-130">Permitir que cualquier usuario vea el correo enviado (las respuestas)</span><span class="sxs-lookup"><span data-stu-id="cbc52-130">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="cbc52-p107">De forma predeterminada, los mensajes enviados al buzón compartido no se guardan en la carpeta Elementos enviados del buzón compartido. En su lugar, se guardan en la carpeta Elementos enviados de la persona que envió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cbc52-p107">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="cbc52-133">Si desea permitir que todos los usuarios vean el correo electrónico enviado, en el Centro de administración, edite la configuración del buzón compartido y seleccione **Elementos enviados** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-133">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="cbc52-134">Elegir las aplicaciones que un buzón compartido puede usar para tener acceso al correo electrónico de Microsoft</span><span class="sxs-lookup"><span data-stu-id="cbc52-134">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="cbc52-135">En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.</span><span class="sxs-lookup"><span data-stu-id="cbc52-135">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="cbc52-136">Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Editar aplicaciones de correo** \> **electrónico.**</span><span class="sxs-lookup"><span data-stu-id="cbc52-136">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="cbc52-137">Establece la alternancia en **Activar** para todas las aplicaciones que quieres que los miembros puedan usar para tener acceso al buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="cbc52-137">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="cbc52-138">Establece el botón de **alternancia en Desactivado** para las aplicaciones que no quieras que usen.</span><span class="sxs-lookup"><span data-stu-id="cbc52-138">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="cbc52-139">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-139">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="cbc52-140">Poner un buzón compartido en retención por juicio</span><span class="sxs-lookup"><span data-stu-id="cbc52-140">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="cbc52-141">Para obtener más información acerca de la retención por juicio, [vea Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span><span class="sxs-lookup"><span data-stu-id="cbc52-141">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="cbc52-142">En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.</span><span class="sxs-lookup"><span data-stu-id="cbc52-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="cbc52-143">Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Retención por juicio** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-143">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="cbc52-144">Establece la alternancia en **On**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-144">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="cbc52-145">Opcionalmente, escriba una duración, una nota sobre la retención y una dirección URL con más información.</span><span class="sxs-lookup"><span data-stu-id="cbc52-145">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="cbc52-146">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-146">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="cbc52-147">Agregar o quitar miembros</span><span class="sxs-lookup"><span data-stu-id="cbc52-147">Add or remove members</span></span>

1. <span data-ttu-id="cbc52-148">En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.</span><span class="sxs-lookup"><span data-stu-id="cbc52-148">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="cbc52-149">Seleccione el buzón compartido que desea editar y, a continuación, seleccione **Miembros** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-149">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="cbc52-150">Realiza una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cbc52-150">Do one of the following:</span></span>
   - <span data-ttu-id="cbc52-151">Para agregar miembros, seleccione **Agregar miembros,** buscar o seleccionar un miembro para agregar y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-151">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="cbc52-152">Para quitar miembros, use el cuadro Buscar para buscar el miembro si es necesario, seleccione **la X** junto al nombre del miembro y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-152">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="cbc52-153">Seleccione **Guardar de** nuevo.</span><span class="sxs-lookup"><span data-stu-id="cbc52-153">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="cbc52-154">Agregar o quitar permisos de miembros</span><span class="sxs-lookup"><span data-stu-id="cbc52-154">Add or remove permissions of members</span></span>

1. <span data-ttu-id="cbc52-155">En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.</span><span class="sxs-lookup"><span data-stu-id="cbc52-155">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="cbc52-156">Seleccione el buzón compartido que desea editar y, a continuación, **seleccione Miembros** \> **Personalizar permisos**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-156">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="cbc52-157">Seleccione **Editar** junto al permiso que desea cambiar para un miembro.</span><span class="sxs-lookup"><span data-stu-id="cbc52-157">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="cbc52-158">Realiza una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cbc52-158">Do one of the following:</span></span>
   - <span data-ttu-id="cbc52-159">Para conceder ese permiso a un miembro adicional, seleccione **Agregar** permisos, busque o seleccione un miembro para agregar y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-159">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="cbc52-160">Para quitar el permiso de un miembro, use el cuadro Buscar para buscar el miembro si es necesario, seleccione la **X** junto al nombre del miembro y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-160">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="cbc52-161">Seleccione **Guardar de** nuevo.</span><span class="sxs-lookup"><span data-stu-id="cbc52-161">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="cbc52-162">Mostrar u ocultar un buzón compartido en la lista global de direcciones</span><span class="sxs-lookup"><span data-stu-id="cbc52-162">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="cbc52-163">Si decide no mostrar el buzón compartido en la lista global de direcciones, el buzón no aparecerá en la lista de direcciones de su organización, pero seguirá recibiendo correo electrónico enviado.</span><span class="sxs-lookup"><span data-stu-id="cbc52-163">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="cbc52-164">En el centro de administración, vaya a la página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Buzones compartidos</a>.</span><span class="sxs-lookup"><span data-stu-id="cbc52-164">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="cbc52-165">Seleccione el buzón compartido que desea editar y, a continuación, **seleccione Mostrar en la lista global de direcciones** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-165">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="cbc52-166">Establece la alternancia en **Activar**  o **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-166">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="cbc52-167">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cbc52-167">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="cbc52-168">Ocultar un buzón compartido de la lista de direcciones hará imposible que los nuevos miembros del buzón compartido agreguen el buzón oculto a su perfil de Outlook hasta que el buzón compartido se vuelva a mostrar en la lista de direcciones.</span><span class="sxs-lookup"><span data-stu-id="cbc52-168">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="cbc52-169">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="cbc52-169">Related content</span></span>

<span data-ttu-id="cbc52-170">[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="cbc52-170">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>

<span data-ttu-id="cbc52-171">[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="cbc52-171">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="cbc52-172">[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="cbc52-172">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="cbc52-173">[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="cbc52-173">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="cbc52-174">[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="cbc52-174">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>