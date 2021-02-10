---
title: Habilitar el complemento Notificar mensajes
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: Obtenga información sobre cómo habilitar el complemento De mensaje de informe para Outlook y Outlook en la Web, para usuarios individuales o para toda la organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fe47bcb4db42514f3a5252a567421ad792967cd1
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167580"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="04862-103">Habilitar el complemento Notificar mensajes</span><span class="sxs-lookup"><span data-stu-id="04862-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="04862-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="04862-104">**Applies to**</span></span>
- [<span data-ttu-id="04862-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="04862-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="04862-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="04862-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="04862-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04862-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> <span data-ttu-id="04862-108">Si es administrador de una organización de Microsoft 365 con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="04862-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="04862-109">Para obtener más información, vea Usar envío de administrador para enviar correos sospechosos de correo no [deseado, phishing, direcciones URL y archivos a Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="04862-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="04862-110">Los complementos de notificación de suplantación de identidad (phishing) para Outlook y Outlook en la Web (anteriormente conocido como Outlook Web App) permiten a los usuarios notificar fácilmente falsos positivos (correo electrónico bueno marcado como negativo) o falsos negativos (correo electrónico no deseado permitido) a Microsoft y sus filiales para su análisis.</span><span class="sxs-lookup"><span data-stu-id="04862-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="04862-111">Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="04862-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="04862-112">Por ejemplo, si los usuarios informan de una gran cantidad de mensajes que se marcaron como correo no deseado mediante el complemento Mensaje de informe, es posible que el equipo de seguridad de su organización necesite ajustar las directivas contra correo no [deseado.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="04862-112">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="04862-113">Puede instalar el complemento Mensaje de informe o Informar de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="04862-113">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="04862-114">Si desea que los usuarios informen solo de mensajes de suplantación de identidad, implemente el complemento Detección de suplantación de identidad en su organización.</span><span class="sxs-lookup"><span data-stu-id="04862-114">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="04862-115">Para obtener más información, vea Habilitar el complemento [de suplantación de identidad de informes.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="04862-115">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="04862-116">El complemento Mensaje de informe ofrece la opción de notificar mensajes de correo no deseado y de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="04862-116">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="04862-117">Los administradores pueden habilitar el complemento Mensaje de informe para la organización y los usuarios individuales pueden instalarlo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="04862-117">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="04862-118">Si es un usuario individual, puede habilitar el complemento Mensaje [de informe para usted mismo.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="04862-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="04862-119">Si es un administrador global o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, puede habilitar el complemento Mensaje de [informe para su organización.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="04862-119">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="04862-120">El mensaje de informe Add-In ahora está disponible a través [de la implementación centralizada.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="04862-120">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="04862-121">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="04862-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="04862-122">El complemento Mensaje de informe funciona con la mayoría de las suscripciones de Microsoft 365 y los siguientes productos:</span><span class="sxs-lookup"><span data-stu-id="04862-122">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="04862-123">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="04862-123">Outlook on the web</span></span>
  - <span data-ttu-id="04862-124">Outlook 2013 SP1 o posterior</span><span class="sxs-lookup"><span data-stu-id="04862-124">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="04862-125">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="04862-125">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="04862-126">Outlook incluido con aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="04862-126">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="04862-127">Aplicación de Outlook para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="04862-127">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="04862-128">El complemento De mensaje de informe no está disponible para los buzones de las organizaciones de Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="04862-128">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="04862-129">Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique.</span><span class="sxs-lookup"><span data-stu-id="04862-129">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="04862-130">Para obtener más información, consulta [Directivas de envío de usuarios.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="04862-130">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="04862-131">El explorador web existente debe funcionar con el complemento Mensaje de informe.</span><span class="sxs-lookup"><span data-stu-id="04862-131">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="04862-132">Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe un explorador diferente.</span><span class="sxs-lookup"><span data-stu-id="04862-132">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="04862-133">Para las instalación de la organización, la organización debe configurarse para usar la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="04862-133">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="04862-134">Para obtener más información, vea Determinar si la implementación centralizada de complementos [funciona para su organización.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="04862-134">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="04862-135">Los administradores deben ser miembros del grupo de roles Administradores globales.</span><span class="sxs-lookup"><span data-stu-id="04862-135">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="04862-136">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="04862-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="04862-137">Obtener el complemento de mensaje de informe por sí mismo</span><span class="sxs-lookup"><span data-stu-id="04862-137">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="04862-138">Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento Mensaje de informe.</span><span class="sxs-lookup"><span data-stu-id="04862-138">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="04862-139">Para ir directamente al complemento Mensaje de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="04862-139">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="04862-140">Haga **clic en OBTENER AHORA.**</span><span class="sxs-lookup"><span data-stu-id="04862-140">Click **GET IT NOW**.</span></span>

   ![Mensaje de informe: obtenerlo ahora](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="04862-142">En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic en **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="04862-142">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="04862-143">Inicia sesión con tu cuenta de trabajo o escuela (para uso empresarial) o tu cuenta de Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="04862-143">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="04862-144">Después de instalar y habilitar el complemento, verá los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="04862-144">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="04862-145">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="04862-145">In Outlook, the icon looks like this:</span></span>

  ![Icono de complemento de mensaje de informe para Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="04862-147">En Outlook en la Web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="04862-147">In Outlook on the web, the icon looks like this:</span></span>

  ![Icono de complemento de mensaje de informe de Outlook en la web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="04862-149">Para obtener información sobre cómo usar el complemento, vea Usar el complemento De [mensaje de informe.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="04862-149">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="04862-150">Obtener y habilitar el complemento De mensaje de informe para su organización</span><span class="sxs-lookup"><span data-stu-id="04862-150">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="04862-151">El complemento puede tardar hasta 12 horas en aparecer en la organización.</span><span class="sxs-lookup"><span data-stu-id="04862-151">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="04862-152">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> , If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the Integrated **apps** page.</span><span class="sxs-lookup"><span data-stu-id="04862-152">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="04862-153">Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="04862-153">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Página servicios y complementos en el Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="04862-155">En el **menú desplegable Implementar** un nuevo complemento que aparece, revise la información y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="04862-155">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="04862-156">En la página siguiente, haga clic **en Elegir en la Tienda.**</span><span class="sxs-lookup"><span data-stu-id="04862-156">On the next page, click **Choose from the Store**.</span></span>

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="04862-158">En la **página Seleccionar complemento** que aparece, haga clic en el cuadro De búsqueda, escriba Mensaje de informe y, a continuación, haga clic en el icono    ![ Buscar. ](../../media/search-icon.png)</span><span class="sxs-lookup"><span data-stu-id="04862-158">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="04862-159">En la lista de resultados, busque **Mensaje de** informe y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="04862-159">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Seleccionar resultados de búsqueda de complementos](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="04862-161">En el cuadro de diálogo que aparece, revise la información de licencia y privacidad y, a continuación, haga clic **en Continuar.**</span><span class="sxs-lookup"><span data-stu-id="04862-161">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="04862-162">En la **página Configurar complemento que** aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="04862-162">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="04862-163">**Usuarios asignados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="04862-163">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="04862-164">**Todos** (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="04862-164">**Everyone** (default)</span></span>
     - <span data-ttu-id="04862-165">**Usuarios o grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="04862-165">**Specific users / groups**</span></span>
     - <span data-ttu-id="04862-166">**Sólo yo**</span><span class="sxs-lookup"><span data-stu-id="04862-166">**Just me**</span></span>

   - <span data-ttu-id="04862-167">**Método de implementación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="04862-167">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="04862-168">**Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="04862-168">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="04862-169">**Disponible:** los usuarios pueden instalar el complemento en **Inicio** \> **Obtener complementos** \> **administrados por el administrador.**</span><span class="sxs-lookup"><span data-stu-id="04862-169">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="04862-170">**Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="04862-170">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Configurar la página del complemento](../../media/configure-add-in.png)

   <span data-ttu-id="04862-172">Cuando haya terminado, haga clic **en Implementar.**</span><span class="sxs-lookup"><span data-stu-id="04862-172">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="04862-173">En la **página Implementar mensaje de** informe que aparece, verá un informe de progreso seguido de una confirmación de que se implementó el complemento.</span><span class="sxs-lookup"><span data-stu-id="04862-173">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="04862-174">Después de leer la información, haga clic **en Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="04862-174">After you read the information, click **Next**.</span></span>

   ![Página Implementar mensaje de informe](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="04862-176">En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="04862-176">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Página Anunciar complemento](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="04862-178">Obtenga información sobre cómo usar el complemento Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="04862-178">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="04862-179">Las personas que tengan asignado el complemento verán los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="04862-179">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="04862-180">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="04862-180">In Outlook, the icon looks like this:</span></span>

  ![Icono de complemento de mensaje de informe para Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="04862-182">En Outlook en la Web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="04862-182">In Outlook on the web, the icon looks like this:</span></span>

  ![Icono de complemento de mensaje de informe de Outlook en la Web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="04862-184">Cuando notifique a los usuarios sobre el complemento Mensaje de informe, incluya un vínculo para [Usar el complemento Mensaje de informe.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="04862-184">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="04862-185">Revisar o editar la configuración del complemento Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="04862-185">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="04862-186">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> , If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the Integrated **apps** page.</span><span class="sxs-lookup"><span data-stu-id="04862-186">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Servicios y Add-Ins página en el nuevo Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="04862-188">Busque y seleccione el **complemento Mensaje** de informe.</span><span class="sxs-lookup"><span data-stu-id="04862-188">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="04862-189">En el **control desplegable Editar mensaje** de informe que aparece, revise y edite la configuración según corresponda a su organización.</span><span class="sxs-lookup"><span data-stu-id="04862-189">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="04862-190">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="04862-190">When you're finished, click **Save**.</span></span>

   ![Configuración del complemento Mensaje de informe](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="04862-192">Ver y revisar los mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="04862-192">View and review reported messages</span></span>

<span data-ttu-id="04862-193">Para revisar los mensajes que los usuarios envían a Microsoft, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="04862-193">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="04862-194">Usa el portal de envíos de administrador.</span><span class="sxs-lookup"><span data-stu-id="04862-194">Use the Admin Submissions portal.</span></span> <span data-ttu-id="04862-195">Para obtener más información, vea [Ver envíos de usuarios a Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="04862-195">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="04862-196">Cree una regla de flujo de correo (también conocida como regla de transporte) para enviar copias de los mensajes notificados.</span><span class="sxs-lookup"><span data-stu-id="04862-196">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="04862-197">Para obtener instrucciones, consulte Usar reglas de flujo de correo para ver lo que los [usuarios están informando a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="04862-197">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
