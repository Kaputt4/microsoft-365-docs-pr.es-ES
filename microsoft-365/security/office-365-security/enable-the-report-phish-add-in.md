---
title: Habilitar el complemento de suplantación de identidad de informe
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo habilitar el complemento report phishing para Outlook y Outlook en la web, para usuarios individuales o para toda la organización.
ms.openlocfilehash: 44fa55a82462de336982d3af2e3996c14699fd7c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625394"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="c451c-103">Habilitar el complemento Informe de suplantación de identidad (phishing)</span><span class="sxs-lookup"><span data-stu-id="c451c-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="c451c-104">Si es administrador de una organización Microsoft 365 con buzones de correo Exchange Online, se recomienda usar el portal de envíos en el Centro de seguridad y & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c451c-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c451c-105">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="c451c-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="c451c-106">Los complementos Report Message y Report Phishing para Outlook y Outlook en la web (anteriormente conocido como Outlook Web App) permiten a los usuarios notificar fácilmente falsos positivos (buen correo electrónico marcado como negativo) o falsos negativos (correo electrónico no permitido) a Microsoft y sus filiales para su análisis.</span><span class="sxs-lookup"><span data-stu-id="c451c-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="c451c-107">Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c451c-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="c451c-108">Por ejemplo, supongamos que los usuarios están informando de muchos mensajes mediante el complemento Detección de suplantación de identidad de informes.</span><span class="sxs-lookup"><span data-stu-id="c451c-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="c451c-109">Esta información se muestra en el Panel [de seguridad](security-dashboard.md) y otros informes.</span><span class="sxs-lookup"><span data-stu-id="c451c-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="c451c-110">El equipo de seguridad de la organización puede usar esta información como una indicación de que es posible que sea necesario actualizar las directivas contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="c451c-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="c451c-111">Puede instalar el complemento Report Message o Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="c451c-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="c451c-112">Si desea que los usuarios informen tanto de mensajes de correo no deseado como de suplantación de identidad( phishing), implemente el complemento Report Message en su organización.</span><span class="sxs-lookup"><span data-stu-id="c451c-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="c451c-113">Para obtener más información, vea [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="c451c-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="c451c-114">El complemento Report Phishing proporciona la opción de notificar solo mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="c451c-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="c451c-115">Los administradores pueden habilitar el complemento Report Phishing para la organización y los usuarios individuales pueden instalarlo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="c451c-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="c451c-116">Si es un usuario individual, puede habilitar el complemento Detección de suplantación de identidad [por su cuenta.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="c451c-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="c451c-117">Si es un administrador global o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, puede habilitar el complemento Report Phishing para [su organización.](#get-and-enable-the-report-phishing-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="c451c-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="c451c-118">El informe de phishing Add-In está disponible a través [de la implementación centralizada.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="c451c-118">The Report Phishing Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c451c-119">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="c451c-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c451c-120">El complemento Report Phishing funciona con la mayoría Microsoft 365 suscripciones y los siguientes productos:</span><span class="sxs-lookup"><span data-stu-id="c451c-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="c451c-121">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="c451c-121">Outlook on the web</span></span>
  - <span data-ttu-id="c451c-122">Outlook 2013 SP1 o posterior</span><span class="sxs-lookup"><span data-stu-id="c451c-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="c451c-123">Outlook 2016 para Mac o posterior</span><span class="sxs-lookup"><span data-stu-id="c451c-123">Outlook 2016 for Mac or later</span></span>
  - <span data-ttu-id="c451c-124">Outlook se incluye con Microsoft 365 aplicaciones para Enterprise</span><span class="sxs-lookup"><span data-stu-id="c451c-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="c451c-125">Outlook aplicación para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="c451c-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="c451c-126">El complemento Report Phishing no está disponible para buzones o buzones compartidos en organizaciones Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="c451c-126">The Report Phishing add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="c451c-127">Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique.</span><span class="sxs-lookup"><span data-stu-id="c451c-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c451c-128">Para obtener más información, vea [Directivas de envío de usuarios](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="c451c-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="c451c-129">El explorador web existente debe funcionar con el complemento Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="c451c-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="c451c-130">Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe con un explorador diferente.</span><span class="sxs-lookup"><span data-stu-id="c451c-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="c451c-131">Para las instalaciones organizativas, la organización debe configurarse para usar la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="c451c-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="c451c-132">Para obtener más información, vea [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="c451c-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="c451c-133">Los administradores deben ser miembros del grupo de roles Administradores globales.</span><span class="sxs-lookup"><span data-stu-id="c451c-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="c451c-134">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c451c-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="c451c-135">Obtener el complemento de suplantación de identidad de informe por sí mismo</span><span class="sxs-lookup"><span data-stu-id="c451c-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="c451c-136">Vaya a Microsoft AppSource en y busque el complemento <https://appsource.microsoft.com/marketplace/apps> Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="c451c-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="c451c-137">Haga **clic en OBTENER AHORA**.</span><span class="sxs-lookup"><span data-stu-id="c451c-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="c451c-138">En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="c451c-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="c451c-139">Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="c451c-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="c451c-140">Después de instalar y habilitar el complemento, verá los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="c451c-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="c451c-141">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="c451c-141">In Outlook, the icon looks like this:</span></span>

  ![Icono de complemento de phishing de informe para Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="c451c-143">En Outlook web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="c451c-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook en el icono del complemento de phishing de informe web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="c451c-145">Obtener y habilitar el complemento de suplantación de identidad de informes para su organización</span><span class="sxs-lookup"><span data-stu-id="c451c-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="c451c-146">El complemento podría tardar hasta 12 horas en aparecer en la organización.</span><span class="sxs-lookup"><span data-stu-id="c451c-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="c451c-147">En el Centro de administración de **Microsoft 365,** vaya a la página Complementos de Configuración en , Si no ve la página Complementos, vaya al vínculo Complementos de aplicaciones integradas de Configuración en la parte superior de la página Aplicaciones \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **integradas.** </span><span class="sxs-lookup"><span data-stu-id="c451c-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c451c-148">Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c451c-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Servicios y complementos en el Centro de administración de Microsoft 365 administración](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="c451c-150">En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c451c-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="c451c-151">En la página siguiente, haga clic **en Elegir en la Tienda**.</span><span class="sxs-lookup"><span data-stu-id="c451c-151">On the next page, click **Choose from the Store**.</span></span>

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="c451c-153">En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba Informe de **suplantación** de identidad y, a continuación, haga clic en **Buscar** icono  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="c451c-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="c451c-154">En la lista de resultados, busque **Report Phishing** y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c451c-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="c451c-155">En el cuadro de diálogo que aparece, revise la información de privacidad y licencias y, a continuación, haga clic **en Continuar**.</span><span class="sxs-lookup"><span data-stu-id="c451c-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="c451c-156">En la **página Configurar complemento que** aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c451c-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c451c-157">**Usuarios asignados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c451c-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="c451c-158">**Todos** (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="c451c-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="c451c-159">**Usuarios o grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="c451c-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="c451c-160">**Sólo yo**</span><span class="sxs-lookup"><span data-stu-id="c451c-160">**Just me**</span></span>

   - <span data-ttu-id="c451c-161">**Método de implementación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c451c-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="c451c-162">**Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="c451c-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="c451c-163">**Disponible:** los usuarios pueden instalar el complemento en **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="c451c-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="c451c-164">**Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="c451c-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="c451c-165">Cuando haya terminado, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="c451c-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="c451c-166">En la **página Implementar suplantación** de identidad de informes que aparece, verá un informe de progreso seguido de una confirmación de que el complemento se implementó.</span><span class="sxs-lookup"><span data-stu-id="c451c-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="c451c-167">Después de leer la información, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c451c-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="c451c-168">En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="c451c-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="c451c-169">Obtenga información sobre cómo usar el complemento de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="c451c-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="c451c-170">Las personas que tengan asignado el complemento verán los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="c451c-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="c451c-171">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="c451c-171">In Outlook, the icon looks like this:</span></span>

  ![Icono de complemento de phishing de informe para Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="c451c-173">En Outlook web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="c451c-173">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook en el icono del complemento de suplantación de identidad de informes web](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="c451c-175">Revisar o editar la configuración del complemento de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="c451c-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="c451c-176">En el Centro de administración de **Microsoft 365,** vaya a la página Complementos de Configuración en , Si no ve la página Complementos, vaya al vínculo Complementos de aplicaciones integradas de Configuración en la parte superior de la página Aplicaciones \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **integradas.** </span><span class="sxs-lookup"><span data-stu-id="c451c-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c451c-177">Busque y seleccione el **complemento Report Phishing.**</span><span class="sxs-lookup"><span data-stu-id="c451c-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="c451c-178">En el **control desplegable Editar suplantación** de identidad de informe que aparece, revise y edite la configuración según corresponda para su organización.</span><span class="sxs-lookup"><span data-stu-id="c451c-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="c451c-179">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c451c-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="c451c-180">Ver y revisar los mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="c451c-180">View and review reported messages</span></span>

<span data-ttu-id="c451c-181">Para revisar los mensajes que los usuarios informan a Microsoft, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="c451c-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="c451c-182">Use el portal de envíos de administrador.</span><span class="sxs-lookup"><span data-stu-id="c451c-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="c451c-183">Para obtener más información, vea [Ver envíos de usuarios a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c451c-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="c451c-184">Cree una regla de flujo de correo (también conocida como regla de transporte) para enviar copias de los mensajes notificados.</span><span class="sxs-lookup"><span data-stu-id="c451c-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="c451c-185">Para obtener instrucciones, vea [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c451c-185">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
