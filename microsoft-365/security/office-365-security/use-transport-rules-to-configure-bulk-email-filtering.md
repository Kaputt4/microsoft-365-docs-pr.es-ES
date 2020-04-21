---
title: Usar reglas de flujo de correo para filtrar el correo electrónico masivo en Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar reglas de flujo de correo en Exchange Online Protection para el filtrado masivo de correo electrónico.
ms.openlocfilehash: 229a66658e041be737efbc4cbb7c36ba667d3aed
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631078"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a><span data-ttu-id="d03d9-103">Usar reglas de flujo de correo para filtrar el correo electrónico masivo en Office 365</span><span class="sxs-lookup"><span data-stu-id="d03d9-103">Use mail flow rules to filter bulk email in Office 365</span></span>

<span data-ttu-id="d03d9-104">Si es un cliente de Microsoft 365 con buzones en Exchange online o un cliente independiente de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP usa directivas contra correo no deseado (también conocidas como directivas de filtro de correo no deseado o directivas de filtro de contenido) para analizar los mensajes entrantes en busca de correo no deseado y correo masivo (también conocido como correo gris).</span><span class="sxs-lookup"><span data-stu-id="d03d9-104">If you're an Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="d03d9-105">Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d03d9-105">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="d03d9-106">Si desea más opciones para filtrar el correo masivo, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para buscar patrones de texto o frases que se encuentren con frecuencia en el correo masivo y marcar dichos mensajes como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="d03d9-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="d03d9-107">Para obtener más información sobre el correo masivo, vea [¿cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo? y el](what-s-the-difference-between-junk-email-and-bulk-email.md) [nivel de quejas masivas (BCL) en Office 365](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="d03d9-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="d03d9-108">En este tema se explica cómo crear estas reglas de flujo de correo en el centro de administración de Exchange (EAC) y PowerShell (Exchange Online PowerShell para los clientes de Microsoft 365; Exchange Online Protection PowerShell para clientes independientes de EOP).</span><span class="sxs-lookup"><span data-stu-id="d03d9-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d03d9-109">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="d03d9-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d03d9-110">Debe tener asignados permisos en Exchange Online para poder realizar estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="d03d9-110">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="d03d9-111">En concreto, debe tener asignado el rol **reglas de transporte** , que se asigna a las **funciones administración**de la organización, **Administración del cumplimiento**y administración de **registros** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d03d9-111">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="d03d9-112">Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="d03d9-112">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="d03d9-113">Para abrir el EAC en Exchange Online, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="d03d9-113">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="d03d9-114">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d03d9-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d03d9-115">Para conectarse a Exchange Online Protection PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="d03d9-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d03d9-116">Para obtener más información acerca de las reglas de flujo de correo en Exchange Online y EOP independiente, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="d03d9-116">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="d03d9-117">Reglas de flujo de correo (reglas de transporte) en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d03d9-117">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="d03d9-118">Excepciones (predicados) y condiciones de reglas de flujo de correo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d03d9-118">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="d03d9-119">Acciones de las reglas de flujo de correo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d03d9-119">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="d03d9-120">La lista de palabras y patrones de texto que se usan para identificar el correo masivo en los ejemplos no es exhaustivo; puede Agregar y quitar las entradas que considere necesario.</span><span class="sxs-lookup"><span data-stu-id="d03d9-120">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="d03d9-121">Sin embargo, son un buen punto de partida.</span><span class="sxs-lookup"><span data-stu-id="d03d9-121">However, they are a good starting point.</span></span>

- <span data-ttu-id="d03d9-p106">La búsqueda de palabras o patrones de texto en el asunto u otros campos del encabezado del mensaje ocurre *después* de que el mensaje se haya decodificado desde el método de codificación de transferencia de contenido MIME que se usó para transmitir el mensaje binario entre los servidores SMTP en texto ASCII. No puede usar condiciones ni excepciones para buscar los valores codificados sin formato (normalmente, Base64) del asunto o de otros campos del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d03d9-p106">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="d03d9-124">Los siguientes procedimientos marcan un mensaje masivo como correo no deseado para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="d03d9-124">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="d03d9-125">Sin embargo, puede agregar otra condición para aplicar estas reglas solo a destinatarios específicos, de modo que pueda usar un filtrado agresivo en algunos usuarios muy dirigidos, mientras que el resto de los usuarios (que obtienen el correo electrónico en masa en el que se suscribiron) no se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="d03d9-125">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="d03d9-126">Usar el EAC para crear reglas de flujo de correo que filtren el correo electrónico masivo</span><span class="sxs-lookup"><span data-stu-id="d03d9-126">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="d03d9-127">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="d03d9-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="d03d9-128">Haga **Add** ![clic en agregar](../../media/ITPro-EAC-AddIcon.png) icono Agregar y, a continuación, seleccione **crear una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="d03d9-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="d03d9-129">En la ventana **Nueva regla** que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d03d9-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d03d9-130">**Name**: escriba un nombre único y descriptivo para la regla.</span><span class="sxs-lookup"><span data-stu-id="d03d9-130">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="d03d9-131">Haga clic en **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="d03d9-131">Click **More Options**.</span></span>

   - <span data-ttu-id="d03d9-132">**Aplicar esta regla si**: configure una de las siguientes opciones para buscar contenido en los mensajes mediante expresiones regulares (regex) o palabras o frases:</span><span class="sxs-lookup"><span data-stu-id="d03d9-132">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="d03d9-133">**El asunto o el** \> **cuerpo o el asunto del cuerpo coinciden con estos patrones de texto**: en el cuadro de diálogo **especificar palabras o frases** que aparece, escriba uno de](../../media/ITPro-EAC-AddIcon.png)los siguientes valores, haga clic en **Agregar** ![icono y repita el procedimiento hasta que haya introducido todos los valores.</span><span class="sxs-lookup"><span data-stu-id="d03d9-133">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`

       - `\>(safe )?unsubscribe( here)?\</a\>`

       - `If you do not wish to receive further communications like this\, please`

       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

       - `To stop receiving these+emails\:http\://`

       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

       - `no longer (wish )?(to )?(be sent|receive) w+ email`

       - `If you are unable to view the content of this email\, please click here`

       - `To ensure you receive (your daily deals|our e-?mails)\, add`

       - `If you no longer wish to receive these emails`

       - `to change your (subscription preferences|preferences or unsubscribe)`

       - `click (here to|the) unsubscribe`

      <span data-ttu-id="d03d9-134">Para editar una entrada, selecciónela y haga clic en **Editar** ![icono](../../media/ITPro-EAC-EditIcon.png)de edición.</span><span class="sxs-lookup"><span data-stu-id="d03d9-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="d03d9-135">Para quitar una entrada, selecciónela y haga clic en **quitar** ![icono](../../media/ITPro-EAC-DeleteIcon.png)quitar.</span><span class="sxs-lookup"><span data-stu-id="d03d9-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="d03d9-136">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d03d9-136">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="d03d9-137">**El asunto o** \> el asunto o el cuerpo del mensaje **incluye alguna de estas palabras**: en el cuadro de diálogo **especificar palabras o frases** que aparece, escriba uno de los siguientes valores](../../media/ITPro-EAC-AddIcon.png), haga clic en **Agregar** ![icono y repita el procedimiento hasta que haya introducido todos los valores.</span><span class="sxs-lookup"><span data-stu-id="d03d9-137">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `to change your preferences or unsubscribe`

       - `Modify email preferences or unsubscribe`

       - `This is a promotional email`

       - `You are receiving this email because you requested a subscription`

       - `click here to unsubscribe`

       - `You have received this email because you are subscribed`

       - `If you no longer wish to receive our email newsletter`

       - `to unsubscribe from this newsletter`

       - `If you have trouble viewing this email`

       - `This is an advertisement`

       - `you would like to unsubscribe or change your`

       - `view this email as a webpage`

       - `You are receiving this email because you are subscribed`

      <span data-ttu-id="d03d9-138">Para editar una entrada, selecciónela y haga clic en **Editar** ![icono](../../media/ITPro-EAC-EditIcon.png)de edición.</span><span class="sxs-lookup"><span data-stu-id="d03d9-138">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="d03d9-139">Para quitar una entrada, selecciónela y haga clic en **quitar** ![icono](../../media/ITPro-EAC-DeleteIcon.png)quitar.</span><span class="sxs-lookup"><span data-stu-id="d03d9-139">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="d03d9-140">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d03d9-140">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="d03d9-141">**Haga lo siguiente**: seleccione **modificar las propiedades** \> del mensaje **establecer el nivel de confianza contra correo no deseado (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="d03d9-141">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="d03d9-142">En el cuadro de diálogo **especificar SCL** que aparece, configure una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d03d9-142">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="d03d9-143">Para marcar los mensajes como **correo no deseado**, selecciona **6**.</span><span class="sxs-lookup"><span data-stu-id="d03d9-143">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="d03d9-144">La acción que ha configurado para los veredictos de filtrado de **correo no deseado** en las directivas contra correo no deseado se aplica a los mensajes (el valor predeterminado es **mover mensaje a la carpeta de correo electrónico no deseado**).</span><span class="sxs-lookup"><span data-stu-id="d03d9-144">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="d03d9-145">Para marcar mensajes como **correo no deseado de alta confianza** , seleccione **9**.</span><span class="sxs-lookup"><span data-stu-id="d03d9-145">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="d03d9-146">La acción que ha configurado para los veredictos de filtrado de **correo no deseado de confianza alta** en las directivas contra correo no deseado se aplica a los mensajes (el valor predeterminado es **mover mensaje a la carpeta correo electrónico no deseado**).</span><span class="sxs-lookup"><span data-stu-id="d03d9-146">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="d03d9-147">Para obtener más información acerca de los valores de SCL, vea [nivel de confianza contra correo no deseado (SCL) en Office 365](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d03d9-147">For more information about SCL values, see [Spam confidence level (SCL) in Office 365](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="d03d9-148">Cuando haya terminado, haga clic en **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="d03d9-148">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="d03d9-149">Usar PowerShell para crear reglas de flujo de correo que filtren el correo electrónico masivo</span><span class="sxs-lookup"><span data-stu-id="d03d9-149">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="d03d9-150">Use la siguiente sintaxis para crear una o ambas reglas de flujo de correo (expresiones regulares frente a palabras):</span><span class="sxs-lookup"><span data-stu-id="d03d9-150">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="d03d9-151">En este ejemplo se crea una nueva regla denominada "Bulk Email Filtering-RegEx" que usa la misma lista de expresiones regulares de la sección anterior en el tema para establecer mensajes como **correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="d03d9-151">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="d03d9-152">En este ejemplo se crea una nueva regla denominada "Bulk Email Filtering-Words" que usa la misma lista de palabras descritas anteriormente en el tema para establecer los mensajes como **correo no deseado de confianza alta**.</span><span class="sxs-lookup"><span data-stu-id="d03d9-152">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="d03d9-153">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="d03d9-153">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d03d9-154">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="d03d9-154">How do you know this worked?</span></span>

<span data-ttu-id="d03d9-155">Para comprobar que ha configurado reglas de flujo de correo para filtrar el correo masivo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d03d9-155">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="d03d9-156">En el EAC, vaya a **Mail flow** \> **reglas** \> de flujo de correo Seleccione \> la regla haga clic](../../media/ITPro-EAC-EditIcon.png)en **Editar** ![icono de edición y Compruebe la configuración.</span><span class="sxs-lookup"><span data-stu-id="d03d9-156">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="d03d9-157">En PowerShell, reemplace \<el nombre\> de la regla por el nombre de la regla y ejecute el siguiente comando para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="d03d9-157">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="d03d9-158">Desde una cuenta externa, envíe mensajes de prueba a un destinatario afectado que contenga una de las frases o patrones de texto y compruebe los resultados.</span><span class="sxs-lookup"><span data-stu-id="d03d9-158">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
