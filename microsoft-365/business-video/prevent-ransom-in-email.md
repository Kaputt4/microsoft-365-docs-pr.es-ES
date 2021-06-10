---
title: Crear reglas de correo electrónico para protegerse contra ransomware
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
description: Aprenda a crear reglas de correo electrónico para evitar ransomware.
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580503"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="260e8-103">Crear reglas de correo electrónico para evitar ransomware</span><span class="sxs-lookup"><span data-stu-id="260e8-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="260e8-104">Microsoft 365 ayuda a proteger su negocio contra ransomware al impedir que los archivos potencialmente peligrosos, como JavaScript, por lotes y ejecutables, se abran en Outlook.</span><span class="sxs-lookup"><span data-stu-id="260e8-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="260e8-105">Para aumentar este nivel de protección mediante la adición de reglas que bloquean o advierten de tipos de archivos adicionales, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="260e8-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="260e8-106">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="260e8-106">Try it!</span></span>

1. <span data-ttu-id="260e8-107">En el Centro de administración de [https://admin.microsoft.com](https://admin.microsoft.com) , elija **Exchange** en Centros **de administración**.</span><span class="sxs-lookup"><span data-stu-id="260e8-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="260e8-108">En el menú de la izquierda, elija **flujo de correo**.</span><span class="sxs-lookup"><span data-stu-id="260e8-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="260e8-109">En la pestaña reglas, elija la flecha situada junto al símbolo más (+) y, a continuación, **elija Crear una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="260e8-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="260e8-110">En la **página nueva regla,** escriba un nombre para la regla, desplácese hasta la parte inferior y, a continuación, elija **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="260e8-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="260e8-111">En **Aplicar esta regla si**, seleccione Cualquier dato **adjunto** y, a continuación, seleccione extensión de archivo incluye estas **palabras**.</span><span class="sxs-lookup"><span data-stu-id="260e8-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="260e8-112">En el cuadro de especificar **palabras** o frases, escriba las extensiones de archivo a las que desea que se aplique la regla, como las extensiones de archivo que pueden contener macros.</span><span class="sxs-lookup"><span data-stu-id="260e8-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="260e8-113">Usa el símbolo más (+) para agregarlos uno a la vez.</span><span class="sxs-lookup"><span data-stu-id="260e8-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="260e8-114">Para obtener más información acerca de los tipos de archivo, [lea Proteger contra ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span><span class="sxs-lookup"><span data-stu-id="260e8-114">Learn more about file types by reading [Protect against ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span></span>

1. <span data-ttu-id="260e8-115">Desplácese hacia abajo para revisar la lista y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="260e8-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="260e8-116">En la **página nueva regla,** elija **agregar condición** y, a continuación, elija una condición en Hacer **lo siguiente.**</span><span class="sxs-lookup"><span data-stu-id="260e8-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="260e8-117">Tiene muchas opciones de regla entre las que elegir, pero en este ejemplo elegiremos notificar al **destinatario con un mensaje**.</span><span class="sxs-lookup"><span data-stu-id="260e8-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="260e8-118">Escriba el texto del mensaje para la notificación y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="260e8-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="260e8-119">Opcional: en la página  **nueva regla,** elija Agregar excepción y escriba los detalles de las excepciones a la regla, como los mensajes de remitentes de confianza.</span><span class="sxs-lookup"><span data-stu-id="260e8-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="260e8-120">En la página nueva regla, elija **Guardar** y revise la información de resumen de regla proporcionada.</span><span class="sxs-lookup"><span data-stu-id="260e8-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>