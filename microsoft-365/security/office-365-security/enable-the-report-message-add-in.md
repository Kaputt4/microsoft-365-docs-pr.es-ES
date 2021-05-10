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
ms.openlocfilehash: dc54c5b74697ac41a1d4ff0818467dba662b31f5
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52295824"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="78845-103">Habilitar el mensaje de informe o los complementos de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="78845-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="78845-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="78845-104">**Applies to**</span></span>
- [<span data-ttu-id="78845-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="78845-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="78845-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="78845-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="78845-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78845-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="78845-108">Si es administrador de una organización Microsoft 365 con buzones de correo Exchange Online, se recomienda usar el portal de envíos en el Centro de seguridad y & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="78845-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="78845-109">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="78845-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="78845-110">Los complementos Report Message y Report Phishing para Outlook y Outlook en la web (anteriormente conocido como Outlook Web App) permiten a los usuarios notificar fácilmente falsos positivos (buen correo electrónico marcado como negativo) o falsos negativos (correo electrónico no permitido) a Microsoft y sus filiales para su análisis.</span><span class="sxs-lookup"><span data-stu-id="78845-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="78845-111">Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="78845-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="78845-112">Por ejemplo, supongamos que los usuarios están informando de muchos mensajes mediante el complemento Detección de suplantación de identidad de informes.</span><span class="sxs-lookup"><span data-stu-id="78845-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="78845-113">Esta información se muestra en el Panel de seguridad y otros informes.</span><span class="sxs-lookup"><span data-stu-id="78845-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="78845-114">El equipo de seguridad de la organización puede usar esta información como una indicación de que es posible que sea necesario actualizar las directivas contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="78845-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="78845-115">Puede instalar el complemento Report Message o Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="78845-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="78845-116">Si desea que los usuarios informen tanto de mensajes de correo no deseado como de suplantación de identidad( phishing), implemente el complemento Report Message en su organización.</span><span class="sxs-lookup"><span data-stu-id="78845-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="78845-117">Para obtener más información, vea Enable the Report Message add-in.</span><span class="sxs-lookup"><span data-stu-id="78845-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="78845-118">El complemento Mensaje de informe proporciona la opción de notificar mensajes de correo no deseado y de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="78845-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="78845-119">Los administradores pueden habilitar el complemento Mensaje de informe para la organización y los usuarios individuales pueden instalarlo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="78845-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="78845-120">El complemento Report Phishing proporciona la opción de notificar solo mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="78845-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="78845-121">Los administradores pueden habilitar el complemento Report Phishing para la organización y los usuarios individuales pueden instalarlo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="78845-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="78845-122">Si eres un usuario individual, puedes habilitar ambos complementos por ti mismo.</span><span class="sxs-lookup"><span data-stu-id="78845-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="78845-123">si es un administrador global o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, puede habilitar el complemento Report Message y el complemento Report Phishing para su organización.</span><span class="sxs-lookup"><span data-stu-id="78845-123">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="78845-124">Ambos complementos ya están disponibles a través [de la implementación centralizada](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="78845-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="78845-125">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="78845-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="78845-126">Tanto el complemento Report Message como el complemento Report Phishing funcionan con la mayoría Microsoft 365 suscripciones y los siguientes productos:</span><span class="sxs-lookup"><span data-stu-id="78845-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="78845-127">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="78845-127">Outlook on the web</span></span>
  - <span data-ttu-id="78845-128">Outlook 2013 SP1 o posterior</span><span class="sxs-lookup"><span data-stu-id="78845-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="78845-129">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="78845-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="78845-130">Outlook se incluye con Microsoft 365 aplicaciones para Enterprise</span><span class="sxs-lookup"><span data-stu-id="78845-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="78845-131">Outlook aplicación para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="78845-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="78845-132">Ambos complementos no están disponibles para buzones o buzones compartidos en organizaciones Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="78845-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="78845-133">El explorador web existente debe funcionar con los complementos Report Message y Report Phishing. Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe con un explorador diferente.</span><span class="sxs-lookup"><span data-stu-id="78845-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="78845-134">Para las instalaciones organizativas, la organización debe configurarse para usar la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="78845-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="78845-135">Para obtener más información, vea [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="78845-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="78845-136">Los administradores deben ser miembros del grupo de roles Administradores globales.</span><span class="sxs-lookup"><span data-stu-id="78845-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="78845-137">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="78845-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="78845-138">Para obtener más información sobre cómo notificar un mensaje mediante la característica Mensaje de informe, vea [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="78845-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="78845-139">Obtener el complemento Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="78845-139">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="78845-140">Obtener el complemento por ti mismo</span><span class="sxs-lookup"><span data-stu-id="78845-140">Get the add-in for yourself</span></span>

1. <span data-ttu-id="78845-141">Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento Mensaje de informe.</span><span class="sxs-lookup"><span data-stu-id="78845-141">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="78845-142">Para ir directamente al complemento Mensaje de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="78845-142">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="78845-143">Haga **clic en OBTENER AHORA**.</span><span class="sxs-lookup"><span data-stu-id="78845-143">Click **GET IT NOW**.</span></span>

   ![Mensaje de informe: obtenerlo ahora](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="78845-145">En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="78845-145">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="78845-146">Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="78845-146">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="78845-147">Después de instalar y habilitar el complemento, verá los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="78845-147">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="78845-148">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="78845-148">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="78845-149">![Icono del complemento Mensaje de informe para Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="78845-149">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="78845-150">En Outlook web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="78845-150">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="78845-151">![Outlook en el icono del complemento Mensaje de informe web](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="78845-151">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="78845-152">Obtener el complemento para su organización</span><span class="sxs-lookup"><span data-stu-id="78845-152">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="78845-153">El complemento podría tardar hasta 12 horas en aparecer en la organización.</span><span class="sxs-lookup"><span data-stu-id="78845-153">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="78845-154">En el centro Microsoft 365 administración, vaya a  la página Configuración complementos en \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="78845-154">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="78845-155">Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="78845-155">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="78845-156">Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78845-156">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Servicios y complementos en el Centro de administración de Microsoft 365 administración](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="78845-158">En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78845-158">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="78845-159">En la página siguiente, haga clic **en Elegir en la Tienda**.</span><span class="sxs-lookup"><span data-stu-id="78845-159">On the next page, click **Choose from the Store**.</span></span>

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="78845-161">En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba **Mensaje** de informe y, a continuación, haga clic en **Buscar** en el icono Buscar  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="78845-161">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="78845-162">En la lista de resultados, busque **Mensaje de informe** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="78845-162">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Seleccionar resultados de búsqueda de complementos](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="78845-164">En el cuadro de diálogo que aparece, revise la información de privacidad y licencias y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="78845-164">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="78845-165">En la **página Configurar complemento que** aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="78845-165">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="78845-166">**Usuarios asignados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="78845-166">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="78845-167">**Todos** (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="78845-167">**Everyone** (default)</span></span>
     - <span data-ttu-id="78845-168">**Usuarios o grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="78845-168">**Specific users / groups**</span></span>
     - <span data-ttu-id="78845-169">**Sólo yo**</span><span class="sxs-lookup"><span data-stu-id="78845-169">**Just me**</span></span>

   - <span data-ttu-id="78845-170">**Método de implementación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="78845-170">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="78845-171">**Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="78845-171">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="78845-172">**Disponible:** los usuarios pueden instalar el complemento en **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="78845-172">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="78845-173">**Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="78845-173">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Configurar página de complemento](../../media/configure-add-in.png)

   <span data-ttu-id="78845-175">Cuando haya terminado, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="78845-175">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="78845-176">En la **página Implementar mensaje de** informe que aparece, verá un informe de progreso seguido de una confirmación de que se implementó el complemento.</span><span class="sxs-lookup"><span data-stu-id="78845-176">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="78845-177">Después de leer la información, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78845-177">After you read the information, click **Next**.</span></span>

   ![Página Implementar mensaje de informe](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="78845-179">En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="78845-179">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Anunciar página de complemento](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="78845-181">Revisar o editar la configuración del complemento Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="78845-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="78845-182">En el centro Microsoft 365 administración, vaya a  la página Configuración complementos en \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="78845-182">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="78845-183">Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="78845-183">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Servicios y Add-Ins en el nuevo Centro de administración Microsoft 365 administración](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="78845-185">Busque y seleccione el **complemento Mensaje** de informe.</span><span class="sxs-lookup"><span data-stu-id="78845-185">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="78845-186">En el **control desplegable Editar mensaje** de informe que aparece, revise y edite la configuración según corresponda para su organización.</span><span class="sxs-lookup"><span data-stu-id="78845-186">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="78845-187">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="78845-187">When you're finished, click **Save**.</span></span>

   ![Configuración para el complemento Mensaje de informe](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="78845-189">Obtener el complemento de suplantación de identidad de informe</span><span class="sxs-lookup"><span data-stu-id="78845-189">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="78845-190">Obtener el complemento por ti mismo</span><span class="sxs-lookup"><span data-stu-id="78845-190">Get the add-in for yourself</span></span>

1. <span data-ttu-id="78845-191">Vaya a Microsoft AppSource en y busque el complemento <https://appsource.microsoft.com/marketplace/apps> Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="78845-191">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="78845-192">Haga **clic en OBTENER AHORA**.</span><span class="sxs-lookup"><span data-stu-id="78845-192">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="78845-193">En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="78845-193">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="78845-194">Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="78845-194">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="78845-195">Después de instalar y habilitar el complemento, verá los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="78845-195">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="78845-196">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="78845-196">In Outlook, the icon looks like this:</span></span>

  ![Icono de complemento de phishing de informe para Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="78845-198">En Outlook web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="78845-198">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="78845-199">![Outlook en el icono del complemento de phishing de informe web](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="78845-199">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="78845-200">Obtener el complemento para su organización</span><span class="sxs-lookup"><span data-stu-id="78845-200">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="78845-201">El complemento podría tardar hasta 12 horas en aparecer en la organización.</span><span class="sxs-lookup"><span data-stu-id="78845-201">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="78845-202">En el centro Microsoft 365 administración, vaya a  la página Configuración complementos en \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="78845-202">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="78845-203">Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="78845-203">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="78845-204">Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78845-204">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Servicios y complementos en el Centro de administración de Microsoft 365 administración](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="78845-206">En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78845-206">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="78845-207">En la página siguiente, haga clic **en Elegir en la Tienda**.</span><span class="sxs-lookup"><span data-stu-id="78845-207">On the next page, click **Choose from the Store**.</span></span>

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="78845-209">En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba Informe de **suplantación** de identidad y, a continuación, haga clic en **Buscar** icono  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="78845-209">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="78845-210">En la lista de resultados, busque **Report Phishing** y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="78845-210">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="78845-211">En el cuadro de diálogo que aparece, revise la información de privacidad y licencias y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="78845-211">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="78845-212">En la **página Configurar complemento que** aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="78845-212">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="78845-213">**Usuarios asignados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="78845-213">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="78845-214">**Todos** (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="78845-214">**Everyone** (default)</span></span>
     - <span data-ttu-id="78845-215">**Usuarios o grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="78845-215">**Specific users / groups**</span></span>
     - <span data-ttu-id="78845-216">**Sólo yo**</span><span class="sxs-lookup"><span data-stu-id="78845-216">**Just me**</span></span>

   - <span data-ttu-id="78845-217">**Método de implementación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="78845-217">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="78845-218">**Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="78845-218">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="78845-219">**Disponible:** los usuarios pueden instalar el complemento en **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="78845-219">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="78845-220">**Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="78845-220">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="78845-221">Cuando haya terminado, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="78845-221">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="78845-222">En la **página Implementar suplantación** de identidad de informes que aparece, verá un informe de progreso seguido de una confirmación de que el complemento se implementó.</span><span class="sxs-lookup"><span data-stu-id="78845-222">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="78845-223">Después de leer la información, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78845-223">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="78845-224">En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="78845-224">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="78845-225">Revisar o editar la configuración del complemento de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="78845-225">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="78845-226">En el centro Microsoft 365 administración, vaya a  la página Configuración complementos en \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="78845-226">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="78845-227">Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**</span><span class="sxs-lookup"><span data-stu-id="78845-227">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="78845-228">Busque y seleccione el **complemento Report Phishing.**</span><span class="sxs-lookup"><span data-stu-id="78845-228">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="78845-229">En el **control desplegable Editar suplantación** de identidad de informe que aparece, revise y edite la configuración según corresponda para su organización.</span><span class="sxs-lookup"><span data-stu-id="78845-229">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="78845-230">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="78845-230">When you're finished, click **Save**.</span></span>
