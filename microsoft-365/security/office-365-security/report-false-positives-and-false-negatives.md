---
title: Notificar falsos positivos y falsos negativos en Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo notificar falsos positivos y falsos negativos en Outlook y habilitar los complementos Report Message y Report Phishing.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065207"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="34769-103">Notificar falsos positivos y falsos negativos en Outlook</span><span class="sxs-lookup"><span data-stu-id="34769-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="34769-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="34769-104">**Applies to**</span></span>
- [<span data-ttu-id="34769-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="34769-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="34769-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="34769-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="34769-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34769-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="34769-108">Si es administrador de una organización de Microsoft 365 con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="34769-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="34769-109">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="34769-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="34769-110">En las organizaciones de Microsoft 365 con buzones en Exchange Online o buzones locales con autenticación moderna híbrida, puede enviar falsos positivos (correo electrónico bueno marcado como correo no deseado) y falsos negativos (correo electrónico no deseado y phish permitido) a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="34769-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email marked as spam) and false negatives (bad email and phish allowed) to Exchange Online Protection (EOP).</span></span>

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a><span data-ttu-id="34769-111">Cosas que debe recordar antes de usar la característica Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="34769-111">Things to remember before you use the Report Message feature</span></span>

- <span data-ttu-id="34769-112">Para obtener la mejor experiencia de envío de usuario, use el complemento Report Message o el complemento Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="34769-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="34769-113">Tenga en cuenta que este complemento funciona para Outlook en todas las plataformas: en la web, iOS, Android y Escritorio.</span><span class="sxs-lookup"><span data-stu-id="34769-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="34769-114">Si es administrador de una organización con buzones de Exchange Online, use el portal de envíos en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="34769-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="34769-115">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="34769-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="34769-116">Puede configurar para enviar mensajes directamente a Microsoft, un buzón que especifique o ambos.</span><span class="sxs-lookup"><span data-stu-id="34769-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="34769-117">Para obtener más información, vea [Directivas de envío de usuarios](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="34769-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="34769-118">Para obtener más información acerca de cómo notificar mensajes a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="34769-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="34769-119">Usar la característica Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="34769-119">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="34769-120">Notificar mensajes de correo no deseado y suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="34769-120">Report junk and phishing messages</span></span>

<span data-ttu-id="34769-121">Para los mensajes de la Bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo no deseado, use el siguiente método para notificar mensajes de correo no deseado y suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="34769-121">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="34769-122">Haga clic en **los** puntos suspensivos Más acciones  de la esquina superior derecha  del mensaje seleccionado, haga clic en Informar mensaje en el menú desplegable y, a continuación, seleccione Correo no deseado o **Suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="34769-122">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="34769-123">![Mensaje de informe: más acciones](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="34769-123">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="34769-124">![Mensaje de informe: correo no deseado y suplantación de identidad](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="34769-124">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="34769-125">Los mensajes seleccionados se enviarán a Microsoft para su análisis y:</span><span class="sxs-lookup"><span data-stu-id="34769-125">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="34769-126">Se ha movido a la carpeta correo no deseado si se ha notificado como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="34769-126">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="34769-127">Se elimina si se ha notificado como suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="34769-127">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="34769-128">Informar de mensajes que no son correo no deseado</span><span class="sxs-lookup"><span data-stu-id="34769-128">Report messages that are not junk</span></span>

1. <span data-ttu-id="34769-129">Haga clic **en los** puntos suspensivos Más acciones  de la esquina superior derecha del mensaje seleccionado, haga clic en Informar mensaje en el menú desplegable y, a continuación, haga clic en **No deseado**.</span><span class="sxs-lookup"><span data-stu-id="34769-129">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="34769-130">![Mensaje de informe: más acciones](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="34769-130">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="34769-131">![Mensaje de informe: no deseado](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="34769-131">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="34769-132">El mensaje seleccionado se enviará a Microsoft para su análisis y se trasladará a la Bandeja de entrada o a cualquier otra carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="34769-132">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a><span data-ttu-id="34769-133">Habilitar los complementos Detección de informes y Mensajes de informe</span><span class="sxs-lookup"><span data-stu-id="34769-133">Enable the Report Message and Report Phishing add-ins</span></span>

<span data-ttu-id="34769-134">Los complementos Report Message y Report Phishing para Outlook y Outlook en la web (anteriormente conocidos como Outlook Web App) permiten a los usuarios notificar fácilmente falsos positivos (correo electrónico bueno marcado como negativo) o falsos negativos (correo electrónico no permitido) a Microsoft y sus filiales para su análisis.</span><span class="sxs-lookup"><span data-stu-id="34769-134">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="34769-135">Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="34769-135">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="34769-136">Por ejemplo, supongamos que los usuarios están informando de muchos mensajes mediante el complemento Detección de suplantación de identidad de informes.</span><span class="sxs-lookup"><span data-stu-id="34769-136">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="34769-137">Esta información se muestra en el Panel de seguridad y otros informes.</span><span class="sxs-lookup"><span data-stu-id="34769-137">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="34769-138">El equipo de seguridad de la organización puede usar esta información como una indicación de que es posible que sea necesario actualizar las directivas contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="34769-138">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="34769-139">Puede instalar el complemento Report Message o Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="34769-139">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="34769-140">Si desea que los usuarios informen tanto de mensajes de correo no deseado como de suplantación de identidad( phishing), implemente el complemento Report Message en su organización.</span><span class="sxs-lookup"><span data-stu-id="34769-140">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="34769-141">Para obtener más información, vea Enable the Report Message add-in.</span><span class="sxs-lookup"><span data-stu-id="34769-141">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="34769-142">El complemento Mensaje de informe proporciona la opción de notificar mensajes de correo no deseado y de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="34769-142">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="34769-143">Los administradores pueden habilitar el complemento Mensaje de informe para la organización y los usuarios individuales pueden instalarlo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="34769-143">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="34769-144">El complemento Report Phishing proporciona la opción de notificar solo mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="34769-144">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="34769-145">Los administradores pueden habilitar el complemento Report Phishing para la organización y los usuarios individuales pueden instalarlo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="34769-145">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="34769-146">Si eres un usuario individual, puedes habilitar ambos complementos por ti mismo.</span><span class="sxs-lookup"><span data-stu-id="34769-146">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="34769-147">si es un administrador global o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, puede habilitar el complemento Report Message y el complemento Report Phishing para su organización.</span><span class="sxs-lookup"><span data-stu-id="34769-147">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="34769-148">Ambos complementos ya están disponibles a través [de la implementación centralizada](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="34769-148">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="34769-149">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="34769-149">What do you need to know before you begin?</span></span>

- <span data-ttu-id="34769-150">Tanto el complemento Mensaje de informe como el complemento Report Phishing funcionan con la mayoría de las suscripciones de Microsoft 365 y los siguientes productos:</span><span class="sxs-lookup"><span data-stu-id="34769-150">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="34769-151">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="34769-151">Outlook on the web</span></span>
  - <span data-ttu-id="34769-152">Outlook 2013 SP1 o posterior</span><span class="sxs-lookup"><span data-stu-id="34769-152">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="34769-153">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="34769-153">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="34769-154">Outlook incluido con aplicaciones de Microsoft 365 para Empresas</span><span class="sxs-lookup"><span data-stu-id="34769-154">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="34769-155">Aplicación de Outlook para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="34769-155">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="34769-156">Ambos complementos no están disponibles para buzones o buzones compartidos en organizaciones locales de Exchange.</span><span class="sxs-lookup"><span data-stu-id="34769-156">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="34769-157">El explorador web existente debe funcionar con los complementos Report Message y Report Phishing. Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe con un explorador diferente.</span><span class="sxs-lookup"><span data-stu-id="34769-157">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="34769-158">Para las instalaciones organizativas, la organización debe configurarse para usar la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="34769-158">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="34769-159">Para obtener más información, vea [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="34769-159">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="34769-160">Los administradores deben ser miembros del grupo de roles Administradores globales.</span><span class="sxs-lookup"><span data-stu-id="34769-160">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="34769-161">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="34769-161">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="34769-162">Obtener el complemento Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="34769-162">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="34769-163">Obtener el complemento por ti mismo</span><span class="sxs-lookup"><span data-stu-id="34769-163">Get the add-in for yourself</span></span>

1. <span data-ttu-id="34769-164">Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento Mensaje de informe.</span><span class="sxs-lookup"><span data-stu-id="34769-164">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="34769-165">Para ir directamente al complemento Mensaje de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="34769-165">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="34769-166">Haga **clic en OBTENER AHORA**.</span><span class="sxs-lookup"><span data-stu-id="34769-166">Click **GET IT NOW**.</span></span>

   ![Mensaje de informe: obtenerlo ahora](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="34769-168">En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="34769-168">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="34769-169">Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="34769-169">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="34769-170">Después de instalar y habilitar el complemento, verá los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="34769-170">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="34769-171">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="34769-171">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="34769-172">![Icono del complemento Mensaje de informe para Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="34769-172">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="34769-173">En Outlook en la web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="34769-173">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="34769-174">![Icono del complemento Mensaje de informe de Outlook en la web](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="34769-174">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="34769-175">Obtener el complemento para su organización</span><span class="sxs-lookup"><span data-stu-id="34769-175">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="34769-176">El complemento podría tardar hasta 12 horas en aparecer en la organización.</span><span class="sxs-lookup"><span data-stu-id="34769-176">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="34769-177">En el Centro de administración de Microsoft 365, vaya a la página Complementos  \> **de configuración** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="34769-177">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="34769-178">Si no ves  la página Complemento, ve  al vínculo Configuración Complementos de aplicaciones integradas en la parte \>  \>  superior de la **página Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="34769-178">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="34769-179">Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="34769-179">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Página Servicios y complementos en el Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="34769-181">En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="34769-181">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="34769-182">En la página siguiente, haga clic **en Elegir en la Tienda**.</span><span class="sxs-lookup"><span data-stu-id="34769-182">On the next page, click **Choose from the Store**.</span></span>

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="34769-184">En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba **Mensaje** de informe y, a continuación, haga clic en **Buscar** en el icono Buscar  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="34769-184">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="34769-185">En la lista de resultados, busque **Mensaje de informe** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="34769-185">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Seleccionar resultados de búsqueda de complementos](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="34769-187">En el cuadro de diálogo que aparece, revise la información de privacidad y licencias y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="34769-187">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="34769-188">En la **página Configurar complemento que** aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="34769-188">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="34769-189">**Usuarios asignados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="34769-189">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="34769-190">**Todos** (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="34769-190">**Everyone** (default)</span></span>
     - <span data-ttu-id="34769-191">**Usuarios o grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="34769-191">**Specific users / groups**</span></span>
     - <span data-ttu-id="34769-192">**Sólo yo**</span><span class="sxs-lookup"><span data-stu-id="34769-192">**Just me**</span></span>

   - <span data-ttu-id="34769-193">**Método de implementación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="34769-193">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="34769-194">**Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="34769-194">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="34769-195">**Disponible:** los usuarios pueden instalar el complemento en **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="34769-195">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="34769-196">**Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="34769-196">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Configurar página de complemento](../../media/configure-add-in.png)

   <span data-ttu-id="34769-198">Cuando haya terminado, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="34769-198">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="34769-199">En la **página Implementar mensaje de** informe que aparece, verá un informe de progreso seguido de una confirmación de que se implementó el complemento.</span><span class="sxs-lookup"><span data-stu-id="34769-199">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="34769-200">Después de leer la información, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="34769-200">After you read the information, click **Next**.</span></span>

   ![Página Implementar mensaje de informe](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="34769-202">En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="34769-202">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Anunciar página de complemento](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="34769-204">Revisar o editar la configuración del complemento Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="34769-204">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="34769-205">En el Centro de administración de Microsoft 365, vaya a la página Complementos  \> **de configuración** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="34769-205">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="34769-206">Si no ves  la página Complemento, ve  al vínculo Configuración Complementos de aplicaciones integradas en la parte \>  \>  superior de la **página Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="34769-206">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Servicios y Add-Ins en el nuevo Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="34769-208">Busque y seleccione el **complemento Mensaje** de informe.</span><span class="sxs-lookup"><span data-stu-id="34769-208">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="34769-209">En el **control desplegable Editar mensaje** de informe que aparece, revise y edite la configuración según corresponda para su organización.</span><span class="sxs-lookup"><span data-stu-id="34769-209">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="34769-210">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="34769-210">When you're finished, click **Save**.</span></span>

   ![Configuración del complemento Mensaje de informe](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="34769-212">Obtener el complemento de suplantación de identidad de informe</span><span class="sxs-lookup"><span data-stu-id="34769-212">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="34769-213">Obtener el complemento por ti mismo</span><span class="sxs-lookup"><span data-stu-id="34769-213">Get the add-in for yourself</span></span>

1. <span data-ttu-id="34769-214">Vaya a Microsoft AppSource en y busque el complemento <https://appsource.microsoft.com/marketplace/apps> Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="34769-214">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="34769-215">Haga **clic en OBTENER AHORA**.</span><span class="sxs-lookup"><span data-stu-id="34769-215">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="34769-216">En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="34769-216">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="34769-217">Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="34769-217">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="34769-218">Después de instalar y habilitar el complemento, verá los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="34769-218">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="34769-219">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="34769-219">In Outlook, the icon looks like this:</span></span>

  ![Icono de complemento de suplantación de identidad de informes para Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="34769-221">En Outlook en la web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="34769-221">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="34769-222">![Icono del complemento de suplantación de identidad de informes de Outlook en la web](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="34769-222">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="34769-223">Obtener el complemento para su organización</span><span class="sxs-lookup"><span data-stu-id="34769-223">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="34769-224">El complemento podría tardar hasta 12 horas en aparecer en la organización.</span><span class="sxs-lookup"><span data-stu-id="34769-224">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="34769-225">En el Centro de administración de Microsoft 365, vaya a la página Complementos  \> **de configuración** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="34769-225">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="34769-226">Si no ves  la página Complemento, ve  al vínculo Configuración Complementos de aplicaciones integradas en la parte \>  \>  superior de la **página Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="34769-226">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="34769-227">Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="34769-227">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Página Servicios y complementos en el Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="34769-229">En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="34769-229">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="34769-230">En la página siguiente, haga clic **en Elegir en la Tienda**.</span><span class="sxs-lookup"><span data-stu-id="34769-230">On the next page, click **Choose from the Store**.</span></span>

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="34769-232">En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba Informe de **suplantación** de identidad y, a continuación, haga clic en **Buscar** icono  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="34769-232">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="34769-233">En la lista de resultados, busque **Report Phishing** y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="34769-233">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="34769-234">En el cuadro de diálogo que aparece, revise la información de privacidad y licencias y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="34769-234">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="34769-235">En la **página Configurar complemento que** aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="34769-235">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="34769-236">**Usuarios asignados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="34769-236">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="34769-237">**Todos** (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="34769-237">**Everyone** (default)</span></span>
     - <span data-ttu-id="34769-238">**Usuarios o grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="34769-238">**Specific users / groups**</span></span>
     - <span data-ttu-id="34769-239">**Sólo yo**</span><span class="sxs-lookup"><span data-stu-id="34769-239">**Just me**</span></span>

   - <span data-ttu-id="34769-240">**Método de implementación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="34769-240">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="34769-241">**Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="34769-241">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="34769-242">**Disponible:** los usuarios pueden instalar el complemento en **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="34769-242">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="34769-243">**Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="34769-243">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="34769-244">Cuando haya terminado, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="34769-244">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="34769-245">En la **página Implementar suplantación** de identidad de informes que aparece, verá un informe de progreso seguido de una confirmación de que el complemento se implementó.</span><span class="sxs-lookup"><span data-stu-id="34769-245">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="34769-246">Después de leer la información, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="34769-246">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="34769-247">En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="34769-247">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="34769-248">Revisar o editar la configuración del complemento de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="34769-248">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="34769-249">En el Centro de administración de Microsoft 365, vaya a la página Complementos  \> **de configuración** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="34769-249">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="34769-250">Si no ves  la página Complemento, ve  al vínculo Configuración Complementos de aplicaciones integradas en la parte \>  \>  superior de la **página Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="34769-250">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="34769-251">Busque y seleccione el **complemento Report Phishing.**</span><span class="sxs-lookup"><span data-stu-id="34769-251">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="34769-252">En el **control desplegable Editar suplantación** de identidad de informe que aparece, revise y edite la configuración según corresponda para su organización.</span><span class="sxs-lookup"><span data-stu-id="34769-252">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="34769-253">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="34769-253">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="34769-254">Ver y revisar los mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="34769-254">View and review reported messages</span></span>

<span data-ttu-id="34769-255">Para revisar los mensajes que los usuarios informan a Microsoft, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="34769-255">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="34769-256">Use el portal de envíos de administrador.</span><span class="sxs-lookup"><span data-stu-id="34769-256">Use the Admin Submissions portal.</span></span> <span data-ttu-id="34769-257">Para obtener más información, vea [Ver envíos de usuarios a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="34769-257">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="34769-258">Cree una regla de flujo de correo (también conocida como regla de transporte) para enviar copias de los mensajes notificados.</span><span class="sxs-lookup"><span data-stu-id="34769-258">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="34769-259">Para obtener instrucciones, consulte [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="34769-259">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>