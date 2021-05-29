---
title: Detener el reenvío automático de mensajes de correo electrónico
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Aprende a detener el reenvío automático de mensajes de correo mediante la creación de una regla de flujo de correo para evitar el robo de información propietaria.
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706479"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="1bfb5-103">Detener el reenvío automático de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="1bfb5-103">Stop email auto-forward</span></span>

## <a name="watch-stop-auto-forwarding-emails"></a><span data-ttu-id="1bfb5-104">Watch: Stop auto-forwarding emails</span><span class="sxs-lookup"><span data-stu-id="1bfb5-104">Watch: Stop auto-forwarding emails</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="1bfb5-105">Si un hacker obtiene acceso al buzón de un usuario, puede reenviar automáticamente el correo electrónico del usuario a una dirección externa y robar información de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1bfb5-105">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="1bfb5-106">Puede detener esto creando una regla de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="1bfb5-106">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="1bfb5-107">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="1bfb5-107">Try it!</span></span>

1. <span data-ttu-id="1bfb5-108">En el Microsoft 365 de administración, seleccione **Exchange** **,** flujo de  correo y, en la pestaña reglas, seleccione el signo más y elija crear **una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="1bfb5-108">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="1bfb5-109">Seleccione **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="1bfb5-109">Select **More options**.</span></span> <span data-ttu-id="1bfb5-110">Asigne un nombre a la nueva regla.</span><span class="sxs-lookup"><span data-stu-id="1bfb5-110">Name your new rule.</span></span>
1. <span data-ttu-id="1bfb5-111">A continuación, abra la lista desplegable para **aplicar esta regla** si , seleccione el **remitente** y, a continuación, sea **interno externo**.</span><span class="sxs-lookup"><span data-stu-id="1bfb5-111">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="1bfb5-112">Seleccione **Dentro de la organización** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1bfb5-112">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="1bfb5-113">Elija **agregar condición,** abra la lista desplegable, seleccione **Las propiedades del mensaje** y, a continuación, incluya el tipo de **mensaje**.</span><span class="sxs-lookup"><span data-stu-id="1bfb5-113">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="1bfb5-114">Abra la **lista desplegable Seleccionar tipo** de mensaje, elija Reenvío **automático** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1bfb5-114">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="1bfb5-115">Abra la lista desplegable **Hacer** lo siguiente, seleccione **Bloquear el** mensaje y, a continuación, **rechace** el mensaje e incluya una explicación .</span><span class="sxs-lookup"><span data-stu-id="1bfb5-115">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="1bfb5-116">Escriba el texto del mensaje para su explicación y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1bfb5-116">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="1bfb5-117">Desplácese hasta la parte inferior y **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1bfb5-117">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="1bfb5-118">La regla se ha creado y los hackers ya no podrán reenviar mensajes automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1bfb5-118">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="1bfb5-119">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="1bfb5-119">Related content</span></span>

<span data-ttu-id="1bfb5-120">[Agregar otro alias de correo electrónico para un usuario](../admin/email/add-another-email-alias-for-a-user.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="1bfb5-120">[Add another email alias for a user](../admin/email/add-another-email-alias-for-a-user.md) (article)</span></span>\
<span data-ttu-id="1bfb5-121">[Configurar el reenvío de correo electrónico en Microsoft 365](../admin/email/configure-email-forwarding.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="1bfb5-121">[Configure email forwarding in Microsoft 365](../admin/email/configure-email-forwarding.md) (article)</span></span>\
<span data-ttu-id="1bfb5-122">[Buscar y corregir problemas de entrega de correo electrónico](/exchange/troubleshoot/email-delivery/email-delivery-issues) como un Office 365 administración para empresas (artículo)</span><span class="sxs-lookup"><span data-stu-id="1bfb5-122">[Find and fix email delivery issues as an Office 365 for business admin](/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>