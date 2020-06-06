---
title: Habilitar el complemento Notificar mensajes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo habilitar el complemento de mensajes de informe para Outlook y Outlook en la web, para usuarios individuales o para toda la organización.
ms.openlocfilehash: 0b900fe00dc590b69755b54f8103688042026df0
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588233"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="c6a65-103">Habilitar el complemento Notificar mensajes</span><span class="sxs-lookup"><span data-stu-id="c6a65-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="c6a65-104">Si es administrador de una organización de Microsoft 365 con buzones de correo de Exchange Online, le recomendamos que use el portal de envíos del centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c6a65-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c6a65-105">Para obtener más información, vea [usar el envío de administración para enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="c6a65-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="c6a65-106">El complemento de mensajes de informe para Outlook y Outlook en la web (anteriormente conocido como Outlook Web App) permite a los usuarios informar fácilmente de falsos positivos (correo electrónico bueno marcado como malo) o falsos negativos (se permite correo electrónico erróneo) para Microsoft y sus filiales para el análisis.</span><span class="sxs-lookup"><span data-stu-id="c6a65-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="c6a65-107">Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c6a65-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="c6a65-108">Por ejemplo, supongamos que las personas están notificando una gran cantidad de mensajes como suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="c6a65-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="c6a65-109">Esta información se Surfaces en el [Panel de seguridad](security-dashboard.md) y otros informes.</span><span class="sxs-lookup"><span data-stu-id="c6a65-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="c6a65-110">El equipo de seguridad de su organización puede usar esta información como indicación de que es posible que sea necesario actualizar las directivas antiphishing.</span><span class="sxs-lookup"><span data-stu-id="c6a65-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="c6a65-111">O bien, si los usuarios notifican un gran número de mensajes que se marcaron como correo no deseado mediante el complemento de mensajes de informe, es posible que el equipo de seguridad de la organización deba ajustar [las directivas contra correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c6a65-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="c6a65-112">Además, si su organización usa [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) o [plan 2](office-365-ti.md), el complemento de mensajes de informe proporciona al equipo de seguridad de su organización información útil que puede usar para revisar y actualizar las directivas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c6a65-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="c6a65-113">Los administradores pueden habilitar el complemento de mensajes de informe para la organización y los usuarios individuales pueden instalarlo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="c6a65-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="c6a65-114">Si es un usuario individual, puede [Habilitar el complemento de mensajes de informe para usted mismo](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="c6a65-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="c6a65-115">Si es administrador global o administrador de Exchange Online y Exchange está configurado para usar la autenticación OAuth, puede [Habilitar el complemento de mensajes de informe para su organización](#get-and-enable-the-report-message-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="c6a65-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="c6a65-116">El complemento de mensajes de informe ahora está disponible a través de la [implementación centralizada](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="c6a65-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c6a65-117">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="c6a65-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c6a65-118">El complemento de mensajes de informe funciona con la mayoría de las suscripciones de Microsoft 365 y los productos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c6a65-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="c6a65-119">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="c6a65-119">Outlook on the web</span></span>
  - <span data-ttu-id="c6a65-120">Outlook 2013 SP1 o posterior</span><span class="sxs-lookup"><span data-stu-id="c6a65-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="c6a65-121">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="c6a65-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="c6a65-122">Outlook incluido con las aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="c6a65-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="c6a65-123">El complemento de mensajes de informe no está disponible actualmente para:</span><span class="sxs-lookup"><span data-stu-id="c6a65-123">The Report Message add-in is currently not available for:</span></span>

  - <span data-ttu-id="c6a65-124">Buzones de correo en organizaciones locales de Exchange</span><span class="sxs-lookup"><span data-stu-id="c6a65-124">Mailboxes in on-premises Exchange organizations</span></span>
  - <span data-ttu-id="c6a65-125">Las suscripciones GCC, GCC HIGH o DoD</span><span class="sxs-lookup"><span data-stu-id="c6a65-125">GCC, GCC HIGH, or DoD subscriptions</span></span>

- <span data-ttu-id="c6a65-126">Puede configurar los mensajes notificados para que se copien o redirijan a un buzón de correo que especifique.</span><span class="sxs-lookup"><span data-stu-id="c6a65-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c6a65-127">Para obtener más información, vea [especificar un buzón para los envíos de usuarios de correo no deseado y mensajes de suplantación de identidad en Exchange Online](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="c6a65-127">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="c6a65-128">El explorador Web existente debe funcionar con el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="c6a65-128">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="c6a65-129">Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe con otro explorador.</span><span class="sxs-lookup"><span data-stu-id="c6a65-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="c6a65-130">Para las instalaciones organizativas, la organización debe estar configurada para usar la autenticación OAuth.</span><span class="sxs-lookup"><span data-stu-id="c6a65-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="c6a65-131">Para obtener más información, vea [determinar si la implementación centralizada de complementos funciona para su organización](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="c6a65-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="c6a65-132">Los administradores deben ser miembros del grupo de roles de administradores globales.</span><span class="sxs-lookup"><span data-stu-id="c6a65-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="c6a65-133">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c6a65-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="c6a65-134">Obtener el complemento de mensajes de informe para usted mismo</span><span class="sxs-lookup"><span data-stu-id="c6a65-134">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="c6a65-135">Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="c6a65-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="c6a65-136">Para ir directamente al complemento de mensajes de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="c6a65-136">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="c6a65-137">Haga clic en **obtener ahora**.</span><span class="sxs-lookup"><span data-stu-id="c6a65-137">Click **GET IT NOW**.</span></span>

   ![Mensaje de informe: obtenerlo ahora](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="c6a65-139">En el cuadro de diálogo que aparece, revise las condiciones de uso y la Directiva de privacidad y, a continuación, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="c6a65-139">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="c6a65-140">Inicie sesión con su cuenta profesional o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="c6a65-140">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="c6a65-141">Una vez instalado y habilitado el complemento, verá los iconos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c6a65-141">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="c6a65-142">En Outlook, el icono tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="c6a65-142">In Outlook, the icon looks like this:</span></span>

  ![Icono del complemento de mensajes de informe para Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="c6a65-144">En Outlook en la web, el icono tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="c6a65-144">In Outlook on the web, the icon looks like this:</span></span>

  ![Icono del complemento de mensaje de informe de Outlook en la web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="c6a65-146">Para obtener información sobre cómo usar el complemento, vea [usar el complemento de mensajes de informe](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="c6a65-146">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="c6a65-147">Obtener y habilitar el complemento de mensajes de informe para la organización</span><span class="sxs-lookup"><span data-stu-id="c6a65-147">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="c6a65-148">El complemento puede tardar hasta 12 horas en aparecer en la organización.</span><span class="sxs-lookup"><span data-stu-id="c6a65-148">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="c6a65-149">En el centro de administración de Microsoft 365, vaya a la página **servicios & complementos** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> y, a continuación, haga clic en **implementar complemento**.</span><span class="sxs-lookup"><span data-stu-id="c6a65-149">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Página servicios y complementos en el centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="c6a65-151">En el control flotante **implementar un nuevo complemento** que aparece, revise la información y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c6a65-151">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="c6a65-152">En la página siguiente, haga clic en **elegir en la tienda**.</span><span class="sxs-lookup"><span data-stu-id="c6a65-152">On the next page, click **Choose from the Store**.</span></span>

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="c6a65-154">En la página **seleccionar complemento** que aparece, haga clic en el cuadro de **búsqueda** , escriba **mensaje de informe**y, a continuación, haga clic en buscar en el icono de **Search** ![ búsqueda ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="c6a65-154">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="c6a65-155">En la lista de resultados, buscar **mensaje de informe** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c6a65-155">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Seleccionar resultados de la búsqueda de complementos](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="c6a65-157">En el cuadro de diálogo que aparece, revise la información de licencias y privacidad y, a continuación, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="c6a65-157">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="c6a65-158">En la página **configurar complemento** que aparece, configure las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c6a65-158">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c6a65-159">**Usuarios asignados**: Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c6a65-159">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="c6a65-160">**Todos** (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="c6a65-160">**Everyone** (default)</span></span>
     - <span data-ttu-id="c6a65-161">**Usuarios o grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="c6a65-161">**Specific users / groups**</span></span>
     - <span data-ttu-id="c6a65-162">**Sólo yo**</span><span class="sxs-lookup"><span data-stu-id="c6a65-162">**Just me**</span></span>

   - <span data-ttu-id="c6a65-163">**Método de implementación**: Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c6a65-163">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="c6a65-164">**Fijo (predeterminado)**: el complemento se implementa automáticamente en los usuarios especificados y no puede quitarlo.</span><span class="sxs-lookup"><span data-stu-id="c6a65-164">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="c6a65-165">**Disponible**: los usuarios pueden instalar el complemento en **casa** \> **obtener complementos** \> **administrados por el administrador**.</span><span class="sxs-lookup"><span data-stu-id="c6a65-165">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="c6a65-166">**Opcional**: el complemento se implementa automáticamente para los usuarios especificados, pero puede elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="c6a65-166">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Página de configuración del complemento](../../media/configure-add-in.png)

   <span data-ttu-id="c6a65-168">Cuando haya terminado, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="c6a65-168">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="c6a65-169">En la página **implementar mensaje de informe** que aparece, verá un informe de progreso seguido de una confirmación de que se ha implementado el complemento.</span><span class="sxs-lookup"><span data-stu-id="c6a65-169">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="c6a65-170">Una vez que haya leído la información, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c6a65-170">After you read the information, click **Next**.</span></span>

   ![Página implementar mensaje de informe](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="c6a65-172">En la página **anunciar complemento** que aparece, revise la información y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="c6a65-172">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Página de complementos de anuncio](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="c6a65-174">Obtener información sobre cómo usar el complemento de mensajes de informe</span><span class="sxs-lookup"><span data-stu-id="c6a65-174">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="c6a65-175">Los usuarios que tengan el complemento asignado verán los iconos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c6a65-175">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="c6a65-176">En Outlook, el icono tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="c6a65-176">In Outlook, the icon looks like this:</span></span>

  ![Icono del complemento de mensajes de informe para Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="c6a65-178">En Outlook en la web, el icono tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="c6a65-178">In Outlook on the web, the icon looks like this:</span></span>

  ![Icono del complemento de mensaje de informe de Outlook en la web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="c6a65-180">Cuando notifique a los usuarios sobre el complemento de mensajes de informe, incluya un vínculo para [usar el complemento de mensajes de informe](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="c6a65-180">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="c6a65-181">Revisión o edición de la configuración del complemento de mensajes de informe</span><span class="sxs-lookup"><span data-stu-id="c6a65-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="c6a65-182">En el centro de administración de Microsoft 365, vaya a la página **servicios & complementos** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .</span><span class="sxs-lookup"><span data-stu-id="c6a65-182">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![Página servicios y complementos en el nuevo centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="c6a65-184">Busque y seleccione el complemento de **mensajes de informe** .</span><span class="sxs-lookup"><span data-stu-id="c6a65-184">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="c6a65-185">En el control flotante de **mensaje de informe de edición** que aparece, revise y edite las opciones según corresponda para su organización.</span><span class="sxs-lookup"><span data-stu-id="c6a65-185">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="c6a65-186">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c6a65-186">When you're finished, click **Save**.</span></span>

   ![Configuración del complemento de mensajes de informe](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="c6a65-188">Ver y revisar los mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="c6a65-188">View and review reported messages</span></span>

<span data-ttu-id="c6a65-189">Para revisar los mensajes que los usuarios notifican a Microsoft, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="c6a65-189">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="c6a65-190">Usar el portal de envíos de administración.</span><span class="sxs-lookup"><span data-stu-id="c6a65-190">Use the Admin Submissions portal.</span></span> <span data-ttu-id="c6a65-191">Para obtener más información, vea [Ver envíos de usuarios a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c6a65-191">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="c6a65-192">Crear una regla de flujo de correo (también denominada regla de transporte) para enviar copias de mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="c6a65-192">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="c6a65-193">Para obtener instrucciones, vea [usar reglas de flujo de correo para ver qué están notificando los usuarios a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c6a65-193">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
