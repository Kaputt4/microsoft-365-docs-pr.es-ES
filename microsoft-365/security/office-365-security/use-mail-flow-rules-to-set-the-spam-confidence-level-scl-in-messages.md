---
title: Usar reglas de flujo de correo para el SCL en los mensajes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo crear reglas de flujo de correo (reglas de transporte) para identificar mensajes y establecer el nivel de confianza contra correo no deseado (SCL) de los mensajes en Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 791e6747e1ffa92d54e7d4f4a6c257c3aad4c0d9
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195860"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="21c43-103">Usar reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL) en los mensajes en EOP</span><span class="sxs-lookup"><span data-stu-id="21c43-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="21c43-104">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP usa directivas contra correo no deseado (también conocidas como directivas de filtro de correo no deseado o directivas de filtro de contenido) para analizar los mensajes entrantes en busca de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="21c43-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="21c43-105">Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="21c43-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="21c43-106">Si desea marcar determinados mensajes como correo no deseado antes de que se analicen mediante el filtrado de correo no deseado o marcar mensajes para que omitan el filtrado de correo no deseado, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para identificar los mensajes y establecer el nivel de confianza contra correo no deseado (SCL).</span><span class="sxs-lookup"><span data-stu-id="21c43-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="21c43-107">Para obtener más información sobre el SCL, vea [nivel de confianza de correo no deseado (SCL) en EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="21c43-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="21c43-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="21c43-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="21c43-109">Debe tener asignados permisos en Exchange Online para poder realizar estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="21c43-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="21c43-110">En concreto, debe tener asignado el rol **reglas de transporte** , que se asigna a las **funciones administración**de la organización, **Administración del cumplimiento**y administración de **registros** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="21c43-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="21c43-111">Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="21c43-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="21c43-112">Para abrir el EAC en Exchange Online, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="21c43-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="21c43-113">Para obtener más información acerca de las reglas de flujo de correo en Exchange Online, consulte [reglas de flujo de correo (reglas de transporte) en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) .</span><span class="sxs-lookup"><span data-stu-id="21c43-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="21c43-114">Usar el EAC para crear una regla de flujo de correo que establezca el SCL de un mensaje</span><span class="sxs-lookup"><span data-stu-id="21c43-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="21c43-115">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="21c43-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="21c43-116">Haga clic en **Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) y, a continuación, seleccione **crear una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="21c43-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="21c43-117">En la ventana **Nueva regla** que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="21c43-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="21c43-118">**Name**: escriba un nombre único y descriptivo para la regla.</span><span class="sxs-lookup"><span data-stu-id="21c43-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="21c43-119">Haga clic en **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="21c43-119">Click **More Options**.</span></span>

   - <span data-ttu-id="21c43-120">**Aplicar esta regla si**: Seleccione una o más condiciones para identificar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="21c43-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="21c43-121">Para obtener más información, consulte [mail Flow Rule conditions and Exceptions (Predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="21c43-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="21c43-122">**Haga lo siguiente**: seleccione **modificar las propiedades del mensaje** \> **establecer el nivel de confianza contra correo no deseado (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="21c43-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="21c43-123">En el cuadro de diálogo **especificar SCL** que aparece, configure uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="21c43-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="21c43-124">**Omitir el filtrado de correo no deseado**: los mensajes omitirán el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="21c43-124">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="21c43-125">Tenga cuidado con la autorización de mensajes para omitir el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="21c43-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="21c43-126">Los atacantes pueden usar esta vulnerabilidad para enviar mensajes de suplantación de identidad (phishing) y otros mensajes malintencionados a la organización.</span><span class="sxs-lookup"><span data-stu-id="21c43-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="21c43-127">Las reglas de flujo de correo requieren más que solo la dirección de correo electrónico o el dominio del remitente.</span><span class="sxs-lookup"><span data-stu-id="21c43-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="21c43-128">Para obtener más información, vea [crear listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="21c43-128">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="21c43-129">de **0 a 4**: el mensaje se envía a través del filtrado de correo no deseado para su procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="21c43-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="21c43-130">**5 o 6**: el mensaje se marca como **correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="21c43-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="21c43-131">La acción que ha configurado para los veredictos de filtrado de **correo no deseado** en las directivas contra correo no deseado se aplica al mensaje (el valor predeterminado es **mover mensaje a la carpeta de correo electrónico no deseado**).</span><span class="sxs-lookup"><span data-stu-id="21c43-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="21c43-132">de **7 a 9**: el mensaje se marca como **correo no deseado de confianza alta**.</span><span class="sxs-lookup"><span data-stu-id="21c43-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="21c43-133">La acción que ha configurado para los veredictos de filtrado de **correo no deseado de confianza alta** en las directivas contra correo no deseado se aplica al mensaje (el valor predeterminado es **mover mensaje a la carpeta correo electrónico no deseado**).</span><span class="sxs-lookup"><span data-stu-id="21c43-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="21c43-134">Especifique las propiedades adicionales que desee para la regla.</span><span class="sxs-lookup"><span data-stu-id="21c43-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="21c43-135">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="21c43-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="21c43-136">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="21c43-136">How do you know this worked?</span></span>

<span data-ttu-id="21c43-137">Para comprobar que este procedimiento funciona correctamente, envíe un mensaje de correo electrónico a una persona de su organización y compruebe que la acción que se realiza en el mensaje sea como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="21c43-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="21c43-138">Por ejemplo, si **establece el nivel de confianza de correo no deseado (SCL)** en **Omitir el filtrado de correo no deseado**, el mensaje debe enviarse a la bandeja de entrada del destinatario especificado.</span><span class="sxs-lookup"><span data-stu-id="21c43-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="21c43-139">Sin embargo, si **establece el nivel de confianza contra correo no deseado (SCL)** en **9**y la acción de **correo no deseado de confianza alta** para las directivas contra correo no deseado aplicable es mover el mensaje a la carpeta de correo electrónico no deseado, el mensaje debe enviarse a la carpeta de correo electrónico no deseado del destinatario especificado.</span><span class="sxs-lookup"><span data-stu-id="21c43-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
