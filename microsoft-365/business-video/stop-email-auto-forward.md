---
title: Detener el reenvío automático de correos electrónicos
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Obtenga información sobre cómo detener el reenvío automático de correo electrónico.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702594"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="c1393-103">Detener el reenvío automático de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c1393-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="c1393-104">Si un pirata informático obtiene acceso al buzón de un usuario, puede reenviar automáticamente el correo electrónico del usuario a una dirección externa y robar información de propietario.</span><span class="sxs-lookup"><span data-stu-id="c1393-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="c1393-105">Para detener esto, cree una regla de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="c1393-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="c1393-106">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="c1393-106">Try it!</span></span>

1. <span data-ttu-id="c1393-107">En el centro de administración de 365 de Microsoft, seleccione **Exchange**, **flujo de correo** y, en la ficha **reglas** , seleccione el signo más y elija **crear una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="c1393-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="c1393-108">Seleccione **más opciones**.</span><span class="sxs-lookup"><span data-stu-id="c1393-108">Select **More options**.</span></span> <span data-ttu-id="c1393-109">Asigne un nombre a la nueva regla.</span><span class="sxs-lookup"><span data-stu-id="c1393-109">Name your new rule.</span></span>
1. <span data-ttu-id="c1393-110">A continuación, abra la lista desplegable para **aplicar esta regla si**, seleccione **el remitente** y, a continuación, **es interno externo**.</span><span class="sxs-lookup"><span data-stu-id="c1393-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="c1393-111">Seleccione **dentro de la organización** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1393-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="c1393-112">Elija **Agregar condición**, abra la lista desplegable, seleccione **las propiedades del mensaje** y, a continuación, **incluya el tipo de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="c1393-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="c1393-113">Abra la lista desplegable **Seleccionar tipo de mensaje** , elija **reenvío automático** y **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1393-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="c1393-114">Abra la lista desplegable **haga lo siguiente** , seleccione **bloquear el mensaje** y, a continuación, **rechazar el mensaje e incluir una explicación**.</span><span class="sxs-lookup"><span data-stu-id="c1393-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="c1393-115">Escriba el texto del mensaje para su explicación y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1393-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="c1393-116">Desplácese hasta la parte inferior y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c1393-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="c1393-117">Se ha creado la regla y los hackers ya no podrán reenviar mensajes automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c1393-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>