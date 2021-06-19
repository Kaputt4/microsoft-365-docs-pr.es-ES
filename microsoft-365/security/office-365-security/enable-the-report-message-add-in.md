---
title: Habilitar el mensaje de informe o los complementos de suplantación de identidad de informes
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo habilitar el mensaje de informe o los complementos de suplantación de identidad de informes para Outlook y Outlook en la web, para usuarios individuales o para toda la organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7e5136e6d1a118df2e0e91f09a79a9a63e88052
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028588"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="e721c-103">Habilitar el mensaje de informe o los complementos de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="e721c-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e721c-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="e721c-104">**Applies to**</span></span>
- [<span data-ttu-id="e721c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e721c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e721c-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e721c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e721c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e721c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="e721c-108">Si es administrador de una organización de Microsoft 365 con buzones de Exchange Online, le recomendamos que use el portal de envíos en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e721c-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in Microsoft 365 Defender.</span></span> <span data-ttu-id="e721c-109">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e721c-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="e721c-110">Los complementos Report Message y Report Phishing para Outlook y Outlook en la web (anteriormente conocidos como Outlook Web App) permiten a los usuarios notificar fácilmente falsos positivos (correo electrónico bueno marcado como negativo) o falsos negativos (correo electrónico no permitido) a Microsoft y sus filiales para su análisis.</span><span class="sxs-lookup"><span data-stu-id="e721c-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="e721c-111">Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e721c-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="e721c-112">Por ejemplo, supongamos que los usuarios están informando de muchos mensajes mediante el complemento Detección de suplantación de identidad de informes.</span><span class="sxs-lookup"><span data-stu-id="e721c-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="e721c-113">Esta información se muestra en el Panel de seguridad y otros informes.</span><span class="sxs-lookup"><span data-stu-id="e721c-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="e721c-114">El equipo de seguridad de la organización puede usar esta información como una indicación de que es posible que sea necesario actualizar las directivas contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="e721c-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="e721c-115">Puede instalar el complemento Report Message o Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="e721c-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="e721c-116">Si desea que los usuarios informen tanto de mensajes de correo no deseado como de suplantación de identidad( phishing), implemente el complemento Report Message en su organización.</span><span class="sxs-lookup"><span data-stu-id="e721c-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="e721c-117">Para obtener más información, vea Enable the Report Message add-in.</span><span class="sxs-lookup"><span data-stu-id="e721c-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="e721c-118">El complemento Mensaje de informe proporciona la opción de notificar mensajes de correo no deseado y de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="e721c-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="e721c-119">Los administradores pueden habilitar el complemento Mensaje de informe para la organización y los usuarios individuales pueden instalarlo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="e721c-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="e721c-120">El complemento Report Phishing proporciona la opción de notificar solo mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="e721c-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="e721c-121">Los administradores pueden habilitar el complemento Report Phishing para la organización y los usuarios individuales pueden instalarlo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="e721c-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="e721c-122">Si eres un usuario individual, puedes habilitar ambos complementos por ti mismo.</span><span class="sxs-lookup"><span data-stu-id="e721c-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="e721c-123">Si es un administrador global o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, puede habilitar el complemento Report Message y el complemento Report Phishing para su organización.</span><span class="sxs-lookup"><span data-stu-id="e721c-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="e721c-124">Ambos complementos ya están disponibles a través [de la implementación centralizada](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="e721c-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e721c-125">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="e721c-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e721c-126">Tanto el complemento Mensaje de informe como el complemento Report Phishing funcionan con la mayoría de las suscripciones de Microsoft 365 y los siguientes productos:</span><span class="sxs-lookup"><span data-stu-id="e721c-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>
  - <span data-ttu-id="e721c-127">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="e721c-127">Outlook on the web</span></span>
  - <span data-ttu-id="e721c-128">Outlook 2013 SP1 o posterior</span><span class="sxs-lookup"><span data-stu-id="e721c-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="e721c-129">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="e721c-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="e721c-130">Outlook incluido con aplicaciones de Microsoft 365 para Empresas</span><span class="sxs-lookup"><span data-stu-id="e721c-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="e721c-131">Aplicación de Outlook para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="e721c-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="e721c-132">Ambos complementos no están disponibles para buzones o buzones compartidos en organizaciones locales de Exchange.</span><span class="sxs-lookup"><span data-stu-id="e721c-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="e721c-133">El explorador web existente debe funcionar con los complementos Report Message y Report Phishing. Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe con un explorador diferente.</span><span class="sxs-lookup"><span data-stu-id="e721c-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="e721c-134">Para las instalaciones organizativas, la organización debe configurarse para usar la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="e721c-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="e721c-135">Para obtener más información, vea [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="e721c-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="e721c-136">Los administradores deben ser miembros del grupo de roles Administradores globales.</span><span class="sxs-lookup"><span data-stu-id="e721c-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="e721c-137">Para obtener más información, vea [Permissions in the Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e721c-137">For more information, see [Permissions in the Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="e721c-138">Para obtener más información sobre cómo informar de un mensaje mediante la característica Mensaje de informe, vea [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="e721c-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e721c-139">No recomendamos la experiencia de informes integrada en Outlook porque no puede usar la directiva [de envío de usuarios](./user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e721c-139">We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="e721c-140">Se recomienda usar el complemento Report Message o el complemento Report Phishing en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e721c-140">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="e721c-141">Obtener el complemento Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="e721c-141">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="e721c-142">Obtener el complemento por ti mismo</span><span class="sxs-lookup"><span data-stu-id="e721c-142">Get the add-in for yourself</span></span>

1. <span data-ttu-id="e721c-143">Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento Mensaje de informe.</span><span class="sxs-lookup"><span data-stu-id="e721c-143">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="e721c-144">Para ir directamente al complemento Mensaje de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="e721c-144">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="e721c-145">Haga **clic en OBTENER AHORA**.</span><span class="sxs-lookup"><span data-stu-id="e721c-145">Click **GET IT NOW**.</span></span>

   ![Mensaje de informe: obtenerlo ahora](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="e721c-147">En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="e721c-147">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="e721c-148">Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="e721c-148">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="e721c-149">Después de instalar y habilitar el complemento, verá los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="e721c-149">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="e721c-150">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="e721c-150">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e721c-151">![Icono del complemento Mensaje de informe para Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="e721c-151">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="e721c-152">En Outlook en la web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="e721c-152">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e721c-153">![Icono del complemento Mensaje de informe de Outlook en la web](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="e721c-153">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="e721c-154">Obtener el complemento para su organización</span><span class="sxs-lookup"><span data-stu-id="e721c-154">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="e721c-155">El complemento podría tardar hasta 12 horas en aparecer en la organización.</span><span class="sxs-lookup"><span data-stu-id="e721c-155">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="e721c-156">En el Centro de administración de Microsoft  365, vaya a la página \> **Complementos de configuración** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="e721c-156">In the Microsoft 365 admin center, go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="e721c-157">Si no ves  la página Complemento, ve  al vínculo Configuración Complementos de aplicaciones integradas en la parte \>  \>  superior de la **página Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="e721c-157">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="e721c-158">Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e721c-158">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Página Servicios y complementos en el Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="e721c-160">En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e721c-160">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="e721c-161">En la página siguiente, haga clic **en Elegir en la Tienda**.</span><span class="sxs-lookup"><span data-stu-id="e721c-161">On the next page, click **Choose from the Store**.</span></span>

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="e721c-163">En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba **Mensaje** de informe y, a continuación, haga clic en **Buscar** en el icono Buscar  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="e721c-163">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="e721c-164">En la lista de resultados, busque **Mensaje de informe** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e721c-164">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Seleccionar resultados de búsqueda de complementos](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="e721c-166">En el cuadro de diálogo que aparece, revise la información de privacidad y licencias y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="e721c-166">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="e721c-167">En la **página Configurar complemento que** aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e721c-167">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e721c-168">**Usuarios asignados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e721c-168">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="e721c-169">**Todos** (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="e721c-169">**Everyone** (default)</span></span>
     - <span data-ttu-id="e721c-170">**Usuarios o grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="e721c-170">**Specific users / groups**</span></span>
     - <span data-ttu-id="e721c-171">**Sólo yo**</span><span class="sxs-lookup"><span data-stu-id="e721c-171">**Just me**</span></span>

   - <span data-ttu-id="e721c-172">**Método de implementación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e721c-172">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="e721c-173">**Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="e721c-173">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="e721c-174">**Disponible:** los usuarios pueden instalar el complemento en **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="e721c-174">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="e721c-175">**Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="e721c-175">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Configurar página de complemento](../../media/configure-add-in.png)

   <span data-ttu-id="e721c-177">Cuando haya terminado, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="e721c-177">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="e721c-178">En la **página Implementar mensaje de** informe que aparece, verá un informe de progreso seguido de una confirmación de que se implementó el complemento.</span><span class="sxs-lookup"><span data-stu-id="e721c-178">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="e721c-179">Después de leer la información, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e721c-179">After you read the information, click **Next**.</span></span>

   ![Página Implementar mensaje de informe](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="e721c-181">En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e721c-181">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Anunciar página de complemento](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="e721c-183">Revisar o editar la configuración del complemento Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="e721c-183">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="e721c-184">En el Centro de administración de Microsoft 365, vaya a la página Complementos  \> **de configuración** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="e721c-184">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="e721c-185">Si no ves  la página Complemento, ve  al vínculo Configuración Complementos de aplicaciones integradas en la parte \>  \>  superior de la **página Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="e721c-185">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Servicios y Add-Ins en el nuevo Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="e721c-187">Busque y seleccione el **complemento Mensaje** de informe.</span><span class="sxs-lookup"><span data-stu-id="e721c-187">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="e721c-188">En el **control desplegable Editar mensaje** de informe que aparece, revise y edite la configuración según corresponda para su organización.</span><span class="sxs-lookup"><span data-stu-id="e721c-188">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="e721c-189">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e721c-189">When you're finished, click **Save**.</span></span>

   ![Configuración del complemento Mensaje de informe](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="e721c-191">Obtener el complemento de suplantación de identidad de informe</span><span class="sxs-lookup"><span data-stu-id="e721c-191">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="e721c-192">Obtener el complemento por ti mismo</span><span class="sxs-lookup"><span data-stu-id="e721c-192">Get the add-in for yourself</span></span>

1. <span data-ttu-id="e721c-193">Vaya a Microsoft AppSource en y busque el complemento <https://appsource.microsoft.com/marketplace/apps> Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="e721c-193">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="e721c-194">Haga **clic en OBTENER AHORA**.</span><span class="sxs-lookup"><span data-stu-id="e721c-194">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="e721c-195">En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="e721c-195">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="e721c-196">Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="e721c-196">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="e721c-197">Después de instalar y habilitar el complemento, verá los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="e721c-197">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="e721c-198">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="e721c-198">In Outlook, the icon looks like this:</span></span>

  ![Icono de complemento de suplantación de identidad de informes para Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="e721c-200">En Outlook en la web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="e721c-200">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e721c-201">![Icono del complemento de suplantación de identidad de informes de Outlook en la web](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="e721c-201">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="e721c-202">Obtener el complemento para su organización</span><span class="sxs-lookup"><span data-stu-id="e721c-202">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="e721c-203">El complemento podría tardar hasta 12 horas en aparecer en la organización.</span><span class="sxs-lookup"><span data-stu-id="e721c-203">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="e721c-204">En el Centro de administración de Microsoft 365, vaya a la página Complementos  \> **de configuración** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="e721c-204">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="e721c-205">Si no ves  la página Complemento, ve  al vínculo Configuración Complementos de aplicaciones integradas en la parte \>  \>  superior de la **página Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="e721c-205">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="e721c-206">Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e721c-206">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Página Servicios y complementos en el Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="e721c-208">En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e721c-208">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="e721c-209">En la página siguiente, haga clic **en Elegir en la Tienda**.</span><span class="sxs-lookup"><span data-stu-id="e721c-209">On the next page, click **Choose from the Store**.</span></span>

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="e721c-211">En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba Informe de **suplantación** de identidad y, a continuación, haga clic en **Buscar** icono  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="e721c-211">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="e721c-212">En la lista de resultados, busque **Report Phishing** y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e721c-212">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="e721c-213">En el cuadro de diálogo que aparece, revise la información de privacidad y licencias y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="e721c-213">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="e721c-214">En la **página Configurar complemento que** aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e721c-214">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e721c-215">**Usuarios asignados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e721c-215">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="e721c-216">**Todos** (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="e721c-216">**Everyone** (default)</span></span>
     - <span data-ttu-id="e721c-217">**Usuarios o grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="e721c-217">**Specific users / groups**</span></span>
     - <span data-ttu-id="e721c-218">**Sólo yo**</span><span class="sxs-lookup"><span data-stu-id="e721c-218">**Just me**</span></span>

   - <span data-ttu-id="e721c-219">**Método de implementación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e721c-219">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="e721c-220">**Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="e721c-220">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="e721c-221">**Disponible:** los usuarios pueden instalar el complemento en **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="e721c-221">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="e721c-222">**Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="e721c-222">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="e721c-223">Cuando haya terminado, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="e721c-223">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="e721c-224">En la **página Implementar suplantación** de identidad de informes que aparece, verá un informe de progreso seguido de una confirmación de que el complemento se implementó.</span><span class="sxs-lookup"><span data-stu-id="e721c-224">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="e721c-225">Después de leer la información, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e721c-225">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="e721c-226">En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e721c-226">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="e721c-227">Revisar o editar la configuración del complemento de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="e721c-227">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="e721c-228">En el Centro de administración de Microsoft 365, vaya a la página Complementos  \> **de configuración** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="e721c-228">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="e721c-229">Si no ves  la página Complemento, ve  al vínculo Configuración Complementos de aplicaciones integradas en la parte \>  \>  superior de la **página Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="e721c-229">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="e721c-230">Busque y seleccione el **complemento Report Phishing.**</span><span class="sxs-lookup"><span data-stu-id="e721c-230">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="e721c-231">En el **control desplegable Editar suplantación** de identidad de informe que aparece, revise y edite la configuración según corresponda para su organización.</span><span class="sxs-lookup"><span data-stu-id="e721c-231">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="e721c-232">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e721c-232">When you're finished, click **Save**.</span></span>
