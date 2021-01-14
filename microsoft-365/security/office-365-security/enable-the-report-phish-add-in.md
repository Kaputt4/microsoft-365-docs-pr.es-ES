---
title: Habilitar el complemento de suplantación de identidad de informe
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
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
description: Obtenga información sobre cómo habilitar el complemento de suplantación de identidad de informes para Outlook y Outlook en la Web, para usuarios individuales o toda la organización.
ms.openlocfilehash: 2ea6a9bf9b00fc844aede6daeb9fc11f23c81e4a
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865287"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="cdf0b-103">Habilitar el complemento de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="cdf0b-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="cdf0b-104">Si es administrador de una organización de Microsoft 365 con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="cdf0b-105">Para obtener más información, vea Usar envío de administrador para enviar correos sospechosos de correo no [deseado, phishing, direcciones URL y archivos a Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="cdf0b-106">Los complementos de notificación de suplantación de identidad (phishing) para Outlook y Outlook en la Web (anteriormente conocido como Outlook Web App) permiten a los usuarios notificar fácilmente falsos positivos (correo electrónico bueno marcado como negativo) o falsos negativos (correo electrónico no deseado permitido) a Microsoft y sus filiales para su análisis.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="cdf0b-107">Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="cdf0b-108">Por ejemplo, supongamos que los usuarios están informando de muchos mensajes mediante el complemento de suplantación de identidad de informes.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="cdf0b-109">Esta información se muestra en el Panel [de seguridad](security-dashboard.md) y otros informes.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="cdf0b-110">El equipo de seguridad de su organización puede usar esta información como una indicación de que es posible que sea necesario actualizar las directivas contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="cdf0b-111">Puede instalar el complemento Mensaje de informe o Informar de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="cdf0b-112">Si desea que los usuarios informen tanto de mensajes de correo no deseado como de suplantación de identidad, implemente el complemento Informar de mensaje en su organización.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="cdf0b-113">Para obtener más información, vea Habilitar el complemento Mensaje [de informe.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="cdf0b-114">El complemento Report Phishing ofrece la opción de notificar solo mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="cdf0b-115">Los administradores pueden habilitar el complemento de suplantación de identidad de informes para la organización y los usuarios individuales pueden instalarlo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="cdf0b-116">Si es un usuario individual, puede habilitar el complemento de suplantación de identidad [de informes para usted mismo.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="cdf0b-117">Si es un administrador global o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, puede habilitar el complemento de suplantación de identidad de informes para [su organización.](#get-and-enable-the-report-phishing-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="cdf0b-118">El informe de suplantación de Add-In ya está disponible a través [de la implementación centralizada.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-118">The Report Phishing Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cdf0b-119">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="cdf0b-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cdf0b-120">El complemento de suplantación de identidad de informes funciona con la mayoría de las suscripciones de Microsoft 365 y los siguientes productos:</span><span class="sxs-lookup"><span data-stu-id="cdf0b-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="cdf0b-121">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="cdf0b-121">Outlook on the web</span></span>
  - <span data-ttu-id="cdf0b-122">Outlook 2013 SP1 o posterior</span><span class="sxs-lookup"><span data-stu-id="cdf0b-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="cdf0b-123">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="cdf0b-123">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="cdf0b-124">Outlook incluido con aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="cdf0b-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="cdf0b-125">El complemento de suplantación de identidad de informes no está disponible para buzones en organizaciones de Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-125">The Report Phishing add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="cdf0b-126">Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="cdf0b-127">Para obtener más información, consulta [Directivas de envío de usuarios.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-127">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="cdf0b-128">El explorador web existente debe funcionar con el complemento de suplantación de identidad de informes.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-128">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="cdf0b-129">Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe un explorador diferente.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="cdf0b-130">Para las instalación de la organización, la organización debe configurarse para usar la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="cdf0b-131">Para obtener más información, vea Determinar si la implementación centralizada de complementos [funciona para su organización.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="cdf0b-132">Los administradores deben ser miembros del grupo de roles Administradores globales.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="cdf0b-133">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="cdf0b-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="cdf0b-134">Obtener el complemento de suplantación de identidad de informes por su cuenta</span><span class="sxs-lookup"><span data-stu-id="cdf0b-134">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="cdf0b-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="cdf0b-136">Haga **clic en OBTENER AHORA.**</span><span class="sxs-lookup"><span data-stu-id="cdf0b-136">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="cdf0b-137">En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic en **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="cdf0b-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="cdf0b-138">Inicia sesión con tu cuenta de trabajo o escuela (para uso empresarial) o tu cuenta de Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="cdf0b-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="cdf0b-139">Después de instalar y habilitar el complemento, verá los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="cdf0b-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="cdf0b-140">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="cdf0b-140">In Outlook, the icon looks like this:</span></span>

  ![Icono de complemento de suplantación de identidad de informes para Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="cdf0b-142">En Outlook en la Web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="cdf0b-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Icono de complemento de suplantación de identidad de informes de Outlook en la web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="cdf0b-144">Obtener y habilitar el complemento de suplantación de identidad de informes para su organización</span><span class="sxs-lookup"><span data-stu-id="cdf0b-144">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="cdf0b-145">El complemento puede tardar hasta 12 horas en aparecer en la organización.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-145">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="cdf0b-146">En el Centro de administración de Microsoft 365, vaya a Configuración, en la página Aplicaciones **integradas & Complementos** y, a continuación, haga clic en Implementar <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **complemento.**</span><span class="sxs-lookup"><span data-stu-id="cdf0b-146">In the Microsoft 365 admin center, go to the **Settings, integrated Apps & Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, and then click **Deploy Add-In**.</span></span>

   ![Página servicios y complementos en el Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="cdf0b-148">En el **menú desplegable Implementar** un nuevo complemento que aparece, revise la información y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="cdf0b-148">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="cdf0b-149">En la página siguiente, haga clic **en Elegir en la Tienda.**</span><span class="sxs-lookup"><span data-stu-id="cdf0b-149">On the next page, click **Choose from the Store**.</span></span>

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="cdf0b-151">En la página **Seleccionar complemento** que aparece, haga clic en el cuadro De búsqueda, escriba Suplantación de identidad de informe y, a continuación, haga clic **en** el icono  ![ Buscar. ](../../media/search-icon.png)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-151">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="cdf0b-152">En la lista de resultados, busque **La suplantación** de identidad de informes y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-152">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

5. <span data-ttu-id="cdf0b-153">En el cuadro de diálogo que aparece, revise la información de licencia y privacidad y, a continuación, haga clic **en Continuar.**</span><span class="sxs-lookup"><span data-stu-id="cdf0b-153">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="cdf0b-154">En la **página Configurar complemento que** aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="cdf0b-154">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="cdf0b-155">**Usuarios asignados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="cdf0b-155">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="cdf0b-156">**Todos** (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-156">**Everyone** (default)</span></span>
     - <span data-ttu-id="cdf0b-157">**Usuarios o grupos específicos**</span><span class="sxs-lookup"><span data-stu-id="cdf0b-157">**Specific users / groups**</span></span>
     - <span data-ttu-id="cdf0b-158">**Sólo yo**</span><span class="sxs-lookup"><span data-stu-id="cdf0b-158">**Just me**</span></span>

   - <span data-ttu-id="cdf0b-159">**Método de implementación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="cdf0b-159">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="cdf0b-160">**Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-160">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="cdf0b-161">**Disponible:** los usuarios pueden instalar el complemento en **Inicio** \> **Obtener complementos** \> **administrados por el administrador.**</span><span class="sxs-lookup"><span data-stu-id="cdf0b-161">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="cdf0b-162">**Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-162">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="cdf0b-163">Cuando haya terminado, haga clic **en Implementar.**</span><span class="sxs-lookup"><span data-stu-id="cdf0b-163">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="cdf0b-164">En la **página Implementar suplantación** de identidad de informes que aparece, verá un informe de progreso seguido de una confirmación de que el complemento se implementó.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-164">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="cdf0b-165">Después de leer la información, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-165">After you read the information, click **Next**.</span></span>

8. <span data-ttu-id="cdf0b-166">En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-166">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="cdf0b-167">Obtenga información sobre cómo usar el complemento de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="cdf0b-167">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="cdf0b-168">Las personas que tengan asignado el complemento verán los siguientes iconos:</span><span class="sxs-lookup"><span data-stu-id="cdf0b-168">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="cdf0b-169">En Outlook, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="cdf0b-169">In Outlook, the icon looks like this:</span></span>

  ![Icono de complemento de suplantación de identidad de informes para Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="cdf0b-171">En Outlook en la Web, el icono tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="cdf0b-171">In Outlook on the web, the icon looks like this:</span></span>

  ![Icono de complemento de suplantación de identidad de informes web de Outlook en la Web](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="cdf0b-173">Revisar o editar la configuración del complemento de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="cdf0b-173">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="cdf0b-174">En el Centro de administración de Microsoft 365, vaya a la página servicios **& complementos** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .</span><span class="sxs-lookup"><span data-stu-id="cdf0b-174">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

2. <span data-ttu-id="cdf0b-175">Busque y seleccione el **complemento Detección de suplantación** de identidad (Phishing) de informes.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-175">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="cdf0b-176">En el **control desplegable Editar suplantación** de identidad de informes que aparece, revisa y edita la configuración según corresponda a tu organización.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-176">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="cdf0b-177">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-177">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="cdf0b-178">Ver y revisar los mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="cdf0b-178">View and review reported messages</span></span>

<span data-ttu-id="cdf0b-179">Para revisar los mensajes que los usuarios envían a Microsoft, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="cdf0b-179">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="cdf0b-180">Usa el portal de envíos de administrador.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-180">Use the Admin Submissions portal.</span></span> <span data-ttu-id="cdf0b-181">Para obtener más información, vea [Ver envíos de usuarios a Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-181">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="cdf0b-182">Cree una regla de flujo de correo (también conocida como regla de transporte) para enviar copias de los mensajes notificados.</span><span class="sxs-lookup"><span data-stu-id="cdf0b-182">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="cdf0b-183">Para obtener instrucciones, consulte Usar reglas de flujo de correo para ver lo que los [usuarios están informando a Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="cdf0b-183">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>