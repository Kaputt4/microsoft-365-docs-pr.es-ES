---
title: Ver y liberar mensajes en cuarentena de buzones compartidos
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Los usuarios pueden aprender a ver y actuar en mensajes en cuarentena que se enviaron a buzones compartidos para los que tienen permisos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3efccca375745b0850c91039165b72a7d6f0bcb3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931451"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="6237c-103">Ver y liberar mensajes en cuarentena de buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="6237c-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="6237c-104">Las características que se describen en este artículo están actualmente en versión preliminar, no están disponibles para todos los usuarios y están sujetas a cambios.</span><span class="sxs-lookup"><span data-stu-id="6237c-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="6237c-105">Los usuarios pueden administrar mensajes en cuarentena donde son uno de los destinatarios, tal como se describe en Buscar y liberar mensajes en cuarentena como un usuario [en EOP.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="6237c-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="6237c-106">Pero, ¿qué sucede con los buzones compartidos en los que el usuario tiene permisos acceso total y Enviar como o Enviar en nombre del buzón, tal como se describe en Buzones compartidos [en Exchange Online?](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="6237c-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="6237c-107">Anteriormente, la capacidad de los usuarios para administrar los mensajes en cuarentena enviados a un buzón compartido requería que los administradores dejara habilitada la automapping para el buzón compartido (está habilitada de forma predeterminada cuando un administrador proporciona a un usuario acceso a otro buzón).</span><span class="sxs-lookup"><span data-stu-id="6237c-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="6237c-108">Sin embargo, según el tamaño y el número de buzones a los que  tenga acceso el usuario, el rendimiento puede sufrir cuando Outlook intenta abrir todos los buzones a los que el usuario tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="6237c-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="6237c-109">Por este motivo, muchos administradores eligen [quitar la autoapping para buzones compartidos.](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="6237c-109">For this reason, many admins choose to [remove automapping for shared mailboxes](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="6237c-110">Ahora, ya no es necesaria la autoapping para que los usuarios administren los mensajes en cuarentena que se enviaron a buzones compartidos.</span><span class="sxs-lookup"><span data-stu-id="6237c-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="6237c-111">Simplemente funciona.</span><span class="sxs-lookup"><span data-stu-id="6237c-111">It just works.</span></span> <span data-ttu-id="6237c-112">Existen dos métodos diferentes para obtener acceso a los mensajes en cuarentena que se enviaron a un buzón compartido:</span><span class="sxs-lookup"><span data-stu-id="6237c-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="6237c-113">Si el [](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) administrador ha habilitado notificaciones de correo no deseado para el usuario final en directivas contra correo no  deseado, cualquier usuario que tenga acceso a las notificaciones de correo no deseado del usuario final en el buzón compartido puede hacer clic en el botón Revisar de la notificación para pasar a cuarentena en el Centro de seguridad & Cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6237c-113">If the admin has [enabled end-user spam notifications](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="6237c-114">Tenga en cuenta que este método solo permite a los usuarios administrar los mensajes en cuarentena que se enviaron al buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="6237c-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="6237c-115">Los usuarios no pueden administrar sus propios mensajes de cuarentena en este contexto.</span><span class="sxs-lookup"><span data-stu-id="6237c-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="6237c-116">El usuario puede ir a la cuarentena en el Centro de [& cumplimiento.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="6237c-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="6237c-117">De forma predeterminada, solo se muestran los mensajes que se enviaron al usuario.</span><span class="sxs-lookup"><span data-stu-id="6237c-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="6237c-118">Sin embargo, el usuario puede  cambiar los resultados de la ordenación **(el** botón Id.  de mensaje de forma predeterminada) a la dirección de correo electrónico del **destinatario,** escribir la dirección de correo electrónico del buzón compartido y, a continuación, hacer clic en Actualizar para ver los mensajes en cuarentena que se enviaron al buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="6237c-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![Ordenar los mensajes en cuarentena por dirección de correo electrónico del destinatario.](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="6237c-120">Independientemente del método, los usuarios pueden evitar confusiones si incluyen la **columna Recipient** para los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="6237c-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="6237c-121">El número máximo de columnas para mostrar es 7, por lo que el usuario tendrá que hacer clic  en Modificar **columnas,** quitar una columna existente (por **ejemplo,** Tipo de directiva), seleccionar Destinatario y, a continuación, hacer clic en Guardar o Guardar como **predeterminado.**</span><span class="sxs-lookup"><span data-stu-id="6237c-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![Quite la columna Tipo de directiva y agregue la columna Destinatario a la cuarentena.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="6237c-123">Aspectos importantes</span><span class="sxs-lookup"><span data-stu-id="6237c-123">Things to keep in mind</span></span>

- <span data-ttu-id="6237c-124">El primer usuario que actúa en el mensaje en cuarentena decide el destino del mensaje para todos los usuarios que usan el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="6237c-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="6237c-125">Por ejemplo, si 10 usuarios acceden a un buzón compartido y un usuario decide eliminar el mensaje en cuarentena, el mensaje se elimina para los 10 usuarios.</span><span class="sxs-lookup"><span data-stu-id="6237c-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="6237c-126">Del mismo modo, si un usuario decide liberar el mensaje, se libera en el buzón compartido y es accesible para todos los demás usuarios del buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="6237c-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="6237c-127">Actualmente, el **botón Bloquear remitente** no está disponible en el control desplegable Detalles para los mensajes en cuarentena que se enviaron al buzón compartido. </span><span class="sxs-lookup"><span data-stu-id="6237c-127">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="6237c-128">Para administrar los mensajes en cuarentena para el buzón compartido en [Exchange Online PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)el usuario final tendrá que usar el cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) con la dirección de correo electrónico del buzón compartido para el valor del parámetro _RecipientAddress_ para identificar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="6237c-128">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="6237c-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6237c-129">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="6237c-130">A continuación, el usuario final puede seleccionar un mensaje en cuarentena de la lista para ver o tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="6237c-130">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="6237c-131">En este ejemplo se muestran todos los mensajes en cuarentena que se enviaron al buzón compartido y, a continuación, se libera el primer mensaje de la lista de cuarentena (el primer mensaje de la lista es 0, el segundo es 1, y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="6237c-131">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="6237c-132">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="6237c-132">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="6237c-133">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6237c-133">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="6237c-134">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="6237c-134">Get-QuarantineMessageHeader</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="6237c-135">Preview-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6237c-135">Preview-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="6237c-136">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6237c-136">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
