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
description: Obtenga información sobre cómo detener el reenvío automático de mensajes de correo electrónico.
ms.openlocfilehash: b6715cfdf8622521d977e0746cb9a340a8f70a5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578608"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="c8655-103">Detener el reenvío automático de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c8655-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="c8655-104">Si un hacker obtiene acceso al buzón de un usuario, puede reenviar automáticamente el correo electrónico del usuario a una dirección externa y robar información de propiedad.</span><span class="sxs-lookup"><span data-stu-id="c8655-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="c8655-105">Puede detener esto creando una regla de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="c8655-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="c8655-106">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="c8655-106">Try it!</span></span>

1. <span data-ttu-id="c8655-107">En el Centro de administración de Microsoft 365,  seleccione **Exchange** **,** flujo de correo y, en la pestaña reglas, seleccione el signo más y elija crear una **nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="c8655-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="c8655-108">Seleccione **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="c8655-108">Select **More options**.</span></span> <span data-ttu-id="c8655-109">Asigne un nombre a la nueva regla.</span><span class="sxs-lookup"><span data-stu-id="c8655-109">Name your new rule.</span></span>
1. <span data-ttu-id="c8655-110">A continuación, abra la lista desplegable para **aplicar esta regla** si , seleccione el **remitente** y, a continuación, sea **interno externo**.</span><span class="sxs-lookup"><span data-stu-id="c8655-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="c8655-111">Seleccione **Dentro de la organización** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c8655-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="c8655-112">Elija **agregar condición,** abra la lista desplegable, seleccione **Las propiedades del mensaje** y, a continuación, incluya el tipo de **mensaje**.</span><span class="sxs-lookup"><span data-stu-id="c8655-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="c8655-113">Abra la **lista desplegable Seleccionar tipo** de mensaje, elija Reenvío **automático** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c8655-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="c8655-114">Abra la lista desplegable **Hacer** lo siguiente, seleccione **Bloquear el** mensaje y, a continuación, **rechace** el mensaje e incluya una explicación .</span><span class="sxs-lookup"><span data-stu-id="c8655-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="c8655-115">Escriba el texto del mensaje para su explicación y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c8655-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="c8655-116">Desplácese hasta la parte inferior y **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c8655-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="c8655-117">La regla se ha creado y los hackers ya no podrán reenviar mensajes automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c8655-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>