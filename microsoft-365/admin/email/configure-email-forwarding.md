---
title: Configurar el reenvío de correo electrónico
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Configurar el reenvío de correo electrónico a una o más cuentas de correo electrónico con Office 365.
ms.openlocfilehash: b5612a915fce21e9e9865fca6cb2275d8af17bd2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242413"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="316a3-103">Configurar el reenvío de correo electrónico en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="316a3-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="316a3-104">Como administrador de una organización, es posible que tenga requisitos de la compañía para configurar el reenvío de correo electrónico para el buzón de un usuario.</span><span class="sxs-lookup"><span data-stu-id="316a3-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="316a3-105">El reenvío de correo electrónico le permite reenviar los mensajes del buzón de correo enviados al buzón de un usuario dentro o fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="316a3-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="316a3-106">Puede usar las directivas del filtro de correo no deseado saliente para controlar el reenvío automático a destinatarios externos.</span><span class="sxs-lookup"><span data-stu-id="316a3-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="316a3-107">Para obtener más información, consulte [Controlar el reenvío automático de correo electrónico externo en Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="316a3-107">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="316a3-108">Configurar el reenvío de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="316a3-108">Configure email forwarding</span></span>

<span data-ttu-id="316a3-109">Antes de configurar el reenvío de correo electrónico, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="316a3-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="316a3-110">Una vez configurado el reenvío de correo electrónico, solo se reenviarán los correos electrónicos **nuevos** enviados al buzón de  correo electrónico de *origen*.</span><span class="sxs-lookup"><span data-stu-id="316a3-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="316a3-111">El reenvío de correo electrónico requiere que la cuenta de *origen*  tenga una licencia.</span><span class="sxs-lookup"><span data-stu-id="316a3-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="316a3-112">Si está configurando el reenvío de correo electrónico porque el usuario ha dejado la organización, otra opción es [convertir su buzón en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="316a3-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="316a3-113">De esta forma, varias personas podrán acceder a él.</span><span class="sxs-lookup"><span data-stu-id="316a3-113">This way several people can access it.</span></span> <span data-ttu-id="316a3-114">Sin embargo, un buzón compartido no puede superar los 50 GB.</span><span class="sxs-lookup"><span data-stu-id="316a3-114">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="316a3-115">Debe ser Administrador de Exchange o Administrador global en Microsoft 365 para poder realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="316a3-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="316a3-116">Para obtener más información, consulte el tema [Acerca de los roles de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="316a3-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="316a3-117">En el Centro de administración, vaya a la página **Usuarios** \> **[Usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=834822)**.</span><span class="sxs-lookup"><span data-stu-id="316a3-117">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="316a3-118">Seleccione el nombre del usuario cuyo correo electrónico quiere reenviar para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="316a3-118">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="316a3-119">En la pestaña **Correo**, seleccione **Administrar el reenvío de correos**.</span><span class="sxs-lookup"><span data-stu-id="316a3-119">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="316a3-120">En la página de reenvío de correo electrónico, seleccione **Reenviar todos los mensajes enviados a este buzón**, escriba la dirección de reenvío y elija si desea conservar una copia de los correos electrónicos reenviados.</span><span class="sxs-lookup"><span data-stu-id="316a3-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="316a3-121">Si no ve esta opción, asegúrese de tener asignada una licencia asignada a la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="316a3-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="316a3-122">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="316a3-122">Select **Save changes**.</span></span>

    <span data-ttu-id="316a3-123">**Para reenviar a varias direcciones de correo**, puede pedir al usuario que configure una regla en Outlook para que se reenvía a las direcciones.</span><span class="sxs-lookup"><span data-stu-id="316a3-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="316a3-124">Para obtener más información, consulte [Usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="316a3-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="316a3-125">O bien, en el Centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [agregue las direcciones](add-user-or-contact-to-distribution-list.md) y luego, configure el reenvío para que apunte a la DL con las instrucciones de este artículo.</span><span class="sxs-lookup"><span data-stu-id="316a3-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="316a3-126">No elimine la cuenta del usuario cuyo correo electrónico está reenviando ni le quite su licencia.</span><span class="sxs-lookup"><span data-stu-id="316a3-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="316a3-127">Si lo hace, se detendrá el reenvío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="316a3-127">If you do, email forwarding will stop.</span></span>