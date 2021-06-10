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
ms.openlocfilehash: ff91cf4c99c9552ab5f5fecd7c6d2efee8d2d9a8
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789261"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="429b7-103">Habilitar el mensaje de informe o los complementos de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="429b7-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="429b7-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="429b7-104">**Applies to**</span></span>
- [<span data-ttu-id="429b7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="429b7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="429b7-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="429b7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="429b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="429b7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="429b7-108">Si es administrador de una organización Microsoft 365 con buzones de correo Exchange Online, se recomienda usar el portal de envíos en el Centro de seguridad y & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="429b7-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="429b7-109">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="429b7-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="429b7-110">Los complementos Report Message y Report Phishing para Outlook y Outlook en la web (anteriormente conocido como Outlook Web App) permiten a los usuarios notificar fácilmente falsos positivos (buen correo electrónico marcado como negativo) o falsos negativos (correo electrónico no permitido) a Microsoft y sus filiales para su análisis.</span><span class="sxs-lookup"><span data-stu-id="429b7-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="429b7-111">Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="429b7-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="429b7-112">Por ejemplo, supongamos que los usuarios están informando de muchos mensajes mediante el complemento Detección de suplantación de identidad de informes.</span><span class="sxs-lookup"><span data-stu-id="429b7-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="429b7-113">Esta información se muestra en el Panel de seguridad y otros informes.</span><span class="sxs-lookup"><span data-stu-id="429b7-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="429b7-114">El equipo de seguridad de la organización puede usar esta información como una indicación de que es posible que sea necesario actualizar las directivas contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="429b7-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="429b7-115">Puede instalar el complemento Report Message o Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="429b7-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="429b7-116">Si desea que los usuarios informen tanto de mensajes de correo no deseado como de suplantación de identidad( phishing), implemente el complemento Report Message en su organización.</span><span class="sxs-lookup"><span data-stu-id="429b7-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="429b7-117">Para obtener más información, vea Enable the Report Message add-in.</span><span class="sxs-lookup"><span data-stu-id="429b7-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="429b7-118">El complemento Mensaje de informe proporciona la opción de notificar mensajes de correo no deseado y de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="429b7-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="429b7-119">Los administradores pueden habilitar el complemento Mensaje de informe para la organización y los usuarios individuales pueden instalarlo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="429b7-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="429b7-120">El complemento Report Phishing proporciona la opción de notificar solo mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="429b7-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="429b7-121">Los administradores pueden habilitar el complemento Report Phishing para la organización y los usuarios individuales pueden instalarlo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="429b7-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="429b7-122">Si eres un usuario individual, puedes habilitar ambos complementos por ti mismo.</span><span class="sxs-lookup"><span data-stu-id="429b7-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="429b7-123">Si es un administrador global o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, puede habilitar el complemento Report Message y el complemento Report Phishing para su organización.</span><span class="sxs-lookup"><span data-stu-id="429b7-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="429b7-124">Ambos complementos ya están disponibles a través [de la implementación centralizada](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="429b7-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="429b7-125">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="429b7-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="429b7-126">Tanto el complemento Report Message como el complemento Report Phishing funcionan con la mayoría Microsoft 365 suscripciones y los siguientes productos:</span><span class="sxs-lookup"><span data-stu-id="429b7-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>
  - <span data-ttu-id="429b7-127">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="429b7-127">Outlook on the web</span></span>
  - <span data-ttu-id="429b7-128">Outlook 2013 SP1 o posterior</span><span class="sxs-lookup"><span data-stu-id="429b7-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="429b7-129">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="429b7-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="429b7-130">Outlook se incluye con Microsoft 365 aplicaciones para Enterprise</span><span class="sxs-lookup"><span data-stu-id="429b7-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="429b7-131">Outlook aplicación para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="429b7-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="429b7-132">Ambos complementos no están disponibles para buzones o buzones compartidos en organizaciones Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="429b7-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="429b7-133">El explorador web existente debe funcionar con los complementos Report Message y Report Phishing. Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe con un explorador diferente.</span><span class="sxs-lookup"><span data-stu-id="429b7-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="429b7-134">Para las instalaciones organizativas, la organización debe configurarse para usar la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="429b7-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="429b7-135">Para obtener más información, vea [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="429b7-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="429b7-136">Los administradores deben ser miembros del grupo de roles Administradores globales.</span><span class="sxs-lookup"><span data-stu-id="429b7-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="429b7-137">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="429b7-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="429b7-138">Para obtener más información sobre cómo notificar un mensaje mediante la característica Mensaje de informe, vea [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="429b7-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="429b7-139">No recomendamos la experiencia de informes integrada en Outlook porque no puede usar la directiva [de envío de usuario](./user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="429b7-139">We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="429b7-140">Se recomienda usar el complemento Report Message o el complemento Report Phishing en su lugar.</span><span class="sxs-lookup"><span data-stu-id="429b7-140">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="429b7-141">Obtener el complemento Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="429b7-141">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="429b7-142">Obtener el complemento por ti mismo</span><span class="sxs-lookup"><span data-stu-id="429b7-142">Get the add-in for yourself</span></span>

1. <span data-ttu-id="429b7-143">Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento Mensaje de informe.</span><span class="sxs-lookup"><span data-stu-id="429b7-143">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="429b7-144">Para ir directamente al complemento Mensaje de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="429b7-144">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="429b7-145">Haga **clic en OBTENER AHORA**.</span><span class="sxs-lookup"><span data-stu-id="429b7-145">Click **GET IT NOW**.</span></span>

   ![Mensaje de informe: obtenerlo ahora](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="429b7-147">En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="429b7-147">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="429b7-148">Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="429b7-148">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="429b7-149">Después de instalar y habilitar el complemento, verá los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="429b7-149">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="429b7-150">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="429b7-150">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="429b7-151">![Icono del complemento Mensaje de informe para Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="429b7-151">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="429b7-152">En Outlook web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="429b7-152">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="429b7-153">![Outlook en el icono del complemento Mensaje de informe web](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="429b7-153">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="429b7-154">Obtener el complemento para su organización</span><span class="sxs-lookup"><span data-stu-id="429b7-154">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="429b7-155">El complemento podría tardar hasta 12 horas en aparecer en la organización.</span><span class="sxs-lookup"><span data-stu-id="429b7-155">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="429b7-156">En el centro Microsoft 365 administración, vaya a  la página Configuración complementos en \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="429b7-156">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="429b7-157">Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="429b7-157">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="429b7-158">Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="429b7-158">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Servicios y complementos en el Centro de administración de Microsoft 365 administración](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="429b7-160">En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="429b7-160">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="429b7-161">En la página siguiente, haga clic **en Elegir en la Tienda**.</span><span class="sxs-lookup"><span data-stu-id="429b7-161">On the next page, click **Choose from the Store**.</span></span>

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="429b7-163">En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba **Mensaje** de informe y, a continuación, haga clic en **Buscar** en el icono Buscar  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="429b7-163">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="429b7-164">En la lista de resultados, busque **Mensaje de informe** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="429b7-164">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Seleccionar resultados de búsqueda de complementos](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="429b7-166">En el cuadro de diálogo que aparece, revise la información de privacidad y licencias y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="429b7-166">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="429b7-167">En la **página Configurar complemento que** aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="429b7-167">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="429b7-168">**Usuarios asignados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="429b7-168">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="429b7-169">**Todos** (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="429b7-169">**Everyone** (default)</span></span>
     - <span data-ttu-id="429b7-170">**Usuarios o grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="429b7-170">**Specific users / groups**</span></span>
     - <span data-ttu-id="429b7-171">**Sólo yo**</span><span class="sxs-lookup"><span data-stu-id="429b7-171">**Just me**</span></span>

   - <span data-ttu-id="429b7-172">**Método de implementación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="429b7-172">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="429b7-173">**Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="429b7-173">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="429b7-174">**Disponible:** los usuarios pueden instalar el complemento en **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="429b7-174">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="429b7-175">**Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="429b7-175">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Configurar página de complemento](../../media/configure-add-in.png)

   <span data-ttu-id="429b7-177">Cuando haya terminado, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="429b7-177">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="429b7-178">En la **página Implementar mensaje de** informe que aparece, verá un informe de progreso seguido de una confirmación de que se implementó el complemento.</span><span class="sxs-lookup"><span data-stu-id="429b7-178">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="429b7-179">Después de leer la información, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="429b7-179">After you read the information, click **Next**.</span></span>

   ![Página Implementar mensaje de informe](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="429b7-181">En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="429b7-181">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Anunciar página de complemento](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="429b7-183">Revisar o editar la configuración del complemento Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="429b7-183">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="429b7-184">En el centro Microsoft 365 administración, vaya a  la página Configuración complementos en \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="429b7-184">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="429b7-185">Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="429b7-185">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Servicios y Add-Ins en el nuevo Centro de administración Microsoft 365 administración](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="429b7-187">Busque y seleccione el **complemento Mensaje** de informe.</span><span class="sxs-lookup"><span data-stu-id="429b7-187">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="429b7-188">En el **control desplegable Editar mensaje** de informe que aparece, revise y edite la configuración según corresponda para su organización.</span><span class="sxs-lookup"><span data-stu-id="429b7-188">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="429b7-189">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="429b7-189">When you're finished, click **Save**.</span></span>

   ![Configuración para el complemento Mensaje de informe](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="429b7-191">Obtener el complemento de suplantación de identidad de informe</span><span class="sxs-lookup"><span data-stu-id="429b7-191">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="429b7-192">Obtener el complemento por ti mismo</span><span class="sxs-lookup"><span data-stu-id="429b7-192">Get the add-in for yourself</span></span>

1. <span data-ttu-id="429b7-193">Vaya a Microsoft AppSource en y busque el complemento <https://appsource.microsoft.com/marketplace/apps> Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="429b7-193">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="429b7-194">Haga **clic en OBTENER AHORA**.</span><span class="sxs-lookup"><span data-stu-id="429b7-194">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="429b7-195">En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="429b7-195">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="429b7-196">Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="429b7-196">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="429b7-197">Después de instalar y habilitar el complemento, verá los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="429b7-197">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="429b7-198">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="429b7-198">In Outlook, the icon looks like this:</span></span>

  ![Icono de complemento de phishing de informe para Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="429b7-200">En Outlook web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="429b7-200">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="429b7-201">![Outlook en el icono del complemento de phishing de informe web](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="429b7-201">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="429b7-202">Obtener el complemento para su organización</span><span class="sxs-lookup"><span data-stu-id="429b7-202">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="429b7-203">El complemento podría tardar hasta 12 horas en aparecer en la organización.</span><span class="sxs-lookup"><span data-stu-id="429b7-203">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="429b7-204">En el centro Microsoft 365 administración, vaya a  la página Configuración complementos en \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="429b7-204">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="429b7-205">Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="429b7-205">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="429b7-206">Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="429b7-206">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Servicios y complementos en el Centro de administración de Microsoft 365 administración](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="429b7-208">En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="429b7-208">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="429b7-209">En la página siguiente, haga clic **en Elegir en la Tienda**.</span><span class="sxs-lookup"><span data-stu-id="429b7-209">On the next page, click **Choose from the Store**.</span></span>

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="429b7-211">En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba Informe de **suplantación** de identidad y, a continuación, haga clic en **Buscar** icono  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="429b7-211">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="429b7-212">En la lista de resultados, busque **Report Phishing** y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="429b7-212">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="429b7-213">En el cuadro de diálogo que aparece, revise la información de privacidad y licencias y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="429b7-213">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="429b7-214">En la **página Configurar complemento que** aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="429b7-214">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="429b7-215">**Usuarios asignados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="429b7-215">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="429b7-216">**Todos** (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="429b7-216">**Everyone** (default)</span></span>
     - <span data-ttu-id="429b7-217">**Usuarios o grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="429b7-217">**Specific users / groups**</span></span>
     - <span data-ttu-id="429b7-218">**Sólo yo**</span><span class="sxs-lookup"><span data-stu-id="429b7-218">**Just me**</span></span>

   - <span data-ttu-id="429b7-219">**Método de implementación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="429b7-219">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="429b7-220">**Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="429b7-220">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="429b7-221">**Disponible:** los usuarios pueden instalar el complemento en **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="429b7-221">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="429b7-222">**Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="429b7-222">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="429b7-223">Cuando haya terminado, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="429b7-223">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="429b7-224">En la **página Implementar suplantación** de identidad de informes que aparece, verá un informe de progreso seguido de una confirmación de que el complemento se implementó.</span><span class="sxs-lookup"><span data-stu-id="429b7-224">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="429b7-225">Después de leer la información, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="429b7-225">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="429b7-226">En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="429b7-226">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="429b7-227">Revisar o editar la configuración del complemento de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="429b7-227">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="429b7-228">En el centro Microsoft 365 administración, vaya a  la página Configuración complementos en \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="429b7-228">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="429b7-229">Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="429b7-229">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="429b7-230">Busque y seleccione el **complemento Report Phishing.**</span><span class="sxs-lookup"><span data-stu-id="429b7-230">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="429b7-231">En el **control desplegable Editar suplantación** de identidad de informe que aparece, revise y edite la configuración según corresponda para su organización.</span><span class="sxs-lookup"><span data-stu-id="429b7-231">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="429b7-232">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="429b7-232">When you're finished, click **Save**.</span></span>
