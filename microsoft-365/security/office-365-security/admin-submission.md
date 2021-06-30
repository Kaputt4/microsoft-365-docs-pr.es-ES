---
title: Envíos de administrador
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el portal de envíos en el portal de Microsoft 365 Defender para enviar correos electrónicos sospechosos, correos de suplantación de identidad sospechosos, correo no deseado y otros mensajes potencialmente dañinos, direcciones URL y datos adjuntos de correo electrónico a Microsoft para volver a examinarlos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eecb635972be85e1a1a4f95c2786f209ee249745
ms.sourcegitcommit: 99e67bfe1d677c2f51712b05dcc54908b343cf6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53203285"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="33c66-103">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="33c66-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="33c66-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="33c66-104">**Applies to**</span></span>
- [<span data-ttu-id="33c66-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="33c66-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="33c66-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="33c66-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="33c66-107">En Microsoft 365 organizaciones con buzones de correo Exchange Online, los administradores pueden usar el portal de envíos en el portal de Microsoft 365 Defender para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para examinarlos.</span><span class="sxs-lookup"><span data-stu-id="33c66-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="33c66-108">Cuando envíe un mensaje de correo electrónico, recibirá:</span><span class="sxs-lookup"><span data-stu-id="33c66-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="33c66-109">**Comprobación de autenticación de** correo electrónico: detalles sobre si la autenticación de correo electrónico se ha pasado o no cuando se entregó.</span><span class="sxs-lookup"><span data-stu-id="33c66-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="33c66-110">**Aciertos de** directiva: información sobre las directivas que pueden haber permitido o bloqueado el correo electrónico entrante en su inquilino, invalidando nuestros veredictos de filtro de servicio.</span><span class="sxs-lookup"><span data-stu-id="33c66-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="33c66-111">**Reputación/detonación de carga:** examen de las direcciones URL y los datos adjuntos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="33c66-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="33c66-112">**Análisis del calificador:** revisión realizada por calificadores humanos para confirmar si los mensajes son malintencionados o no.</span><span class="sxs-lookup"><span data-stu-id="33c66-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33c66-113">El análisis de reputación/detonación y calificador de carga no se realiza en todos los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="33c66-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="33c66-114">La información se bloquea para que no salga de la organización cuando los datos no deben salir del límite del espacio empresarial con fines de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="33c66-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="33c66-115">Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="33c66-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="33c66-116">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="33c66-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="33c66-117">Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="33c66-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="33c66-118">Para ir directamente a la **página Envíos,** use <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="33c66-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="33c66-119">Para enviar mensajes y archivos a Microsoft, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="33c66-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="33c66-120">**Administración de** la organización **o Lector de** seguridad en Microsoft 365 Defender [portal](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="33c66-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  
    <span data-ttu-id="33c66-121">Tenga en cuenta que la pertenencia a este grupo de roles es necesaria para ver los [envíos](#view-user-submissions-to-microsoft) de usuarios al buzón personalizado, tal como se describe más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="33c66-121">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="33c66-122">Para obtener más información acerca de cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="33c66-122">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="33c66-123">Informar de contenido sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="33c66-123">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="33c66-124">En el portal Microsoft 365 Defender, vaya a **Correo electrónico &** \> **envíos de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="33c66-124">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="33c66-125">En la **página Envíos,** compruebe que la pestaña **Enviado** para el análisis está seleccionada y, a continuación, haga clic en Icono de anuncio ![ Enviar a Microsoft para su ](../../media/m365-cc-sc-create-icon.png) **análisis.**</span><span class="sxs-lookup"><span data-stu-id="33c66-125">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="33c66-126">Use el menú desplegable Enviar a **Microsoft** para revisión que parece enviar el mensaje, la dirección URL o los datos adjuntos de correo electrónico, tal como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="33c66-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="33c66-127">Enviar un correo electrónico cuestionable a Microsoft</span><span class="sxs-lookup"><span data-stu-id="33c66-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="33c66-128">En el **cuadro Seleccionar el tipo de envío,** compruebe que **el** correo electrónico está seleccionado en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="33c66-128">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="33c66-129">En la **sección Agregar el identificador de mensaje de red o cargar** el archivo de correo electrónico, use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="33c66-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="33c66-130">Agregar el identificador de mensaje de red de correo **electrónico:** se trata de un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-Id** en el mensaje o en el encabezado **X-MS-Office365-Filtering-Correlation-Id** en mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="33c66-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="33c66-131">**Upload el archivo de correo electrónico (.msg o .eml):** haga clic **en Examinar archivos**.</span><span class="sxs-lookup"><span data-stu-id="33c66-131">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="33c66-132">En el cuadro de diálogo que se abre, busque y seleccione el archivo .eml o .msg y, a continuación, haga clic **en Abrir**.</span><span class="sxs-lookup"><span data-stu-id="33c66-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="33c66-133">La capacidad de enviar mensajes tan antiguos como 30 días se ha suspendido temporalmente para Defender para Office 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="33c66-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="33c66-134">Los administradores solo podrán volver 7 días atrás.</span><span class="sxs-lookup"><span data-stu-id="33c66-134">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="33c66-135">En el **cuadro Elegir un destinatario con un** problema, especifique el destinatario con el que desea ejecutar una comprobación de directiva.</span><span class="sxs-lookup"><span data-stu-id="33c66-135">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="33c66-136">La comprobación de directivas determinará si el correo electrónico omitió el examen debido a directivas de usuario u organización.</span><span class="sxs-lookup"><span data-stu-id="33c66-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="33c66-137">En la **sección Seleccionar un motivo para enviar a Microsoft,** seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="33c66-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="33c66-138">**No se debería haber bloqueado (falso positivo)**</span><span class="sxs-lookup"><span data-stu-id="33c66-138">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="33c66-139">**Debería haber sido** bloqueado: en la sección El correo electrónico debería haber sido categorizado como sección que aparece, seleccione uno de los siguientes valores (si no está seguro, use su mejor criterio): </span><span class="sxs-lookup"><span data-stu-id="33c66-139">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="33c66-140">**Suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="33c66-140">**Phish**</span></span>
     - <span data-ttu-id="33c66-141">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="33c66-141">**Spam**</span></span>
     - <span data-ttu-id="33c66-142">**Malware**</span><span class="sxs-lookup"><span data-stu-id="33c66-142">**Malware**</span></span>

5. <span data-ttu-id="33c66-143">Cuando haya terminado, haga clic en el **botón Enviar.**</span><span class="sxs-lookup"><span data-stu-id="33c66-143">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="33c66-144">![Ejemplo de envío de nueva dirección URL](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="33c66-144">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="33c66-145">Enviar una dirección URL sospechosa a Microsoft</span><span class="sxs-lookup"><span data-stu-id="33c66-145">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="33c66-146">En el **cuadro Seleccionar el tipo de envío,** seleccione DIRECCIÓN **URL** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="33c66-146">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="33c66-147">En el **cuadro Dirección URL** que aparece, escriba la dirección URL completa (por ejemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="33c66-147">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="33c66-148">En la **sección Seleccionar un motivo para enviar a Microsoft,** seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="33c66-148">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="33c66-149">**No se debería haber bloqueado (falso positivo)**</span><span class="sxs-lookup"><span data-stu-id="33c66-149">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="33c66-150">**Debería haber sido bloqueado:** en esta **dirección URL debería haber sido** categorizada como sección que aparece, seleccione **Phish** o **Malware**.</span><span class="sxs-lookup"><span data-stu-id="33c66-150">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="33c66-151">Cuando haya terminado, haga clic en el **botón Enviar.**</span><span class="sxs-lookup"><span data-stu-id="33c66-151">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="33c66-152">![Ejemplo de nuevo envío de correo electrónico](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="33c66-152">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="33c66-153">Enviar datos adjuntos de correo electrónico sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="33c66-153">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="33c66-154">En el **cuadro Seleccionar el tipo de envío,** seleccione **Archivo** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="33c66-154">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="33c66-155">En la **sección Archivo** que aparece, haga clic en **Examinar archivos**.</span><span class="sxs-lookup"><span data-stu-id="33c66-155">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="33c66-156">En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="33c66-156">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="33c66-157">En la **sección Seleccionar un motivo para enviar a Microsoft,** seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="33c66-157">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="33c66-158">**No se debería haber bloqueado (falso positivo)**</span><span class="sxs-lookup"><span data-stu-id="33c66-158">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="33c66-159">**Debería haber sido bloqueado:** en esta **dirección URL** debería haber sido categorizada como sección que aparece, **Malware** es la única opción y se selecciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="33c66-159">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="33c66-160">Cuando haya terminado, haga clic en el **botón Enviar.**</span><span class="sxs-lookup"><span data-stu-id="33c66-160">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="33c66-161">![Ejemplo de nuevo envío de datos adjuntos](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="33c66-161">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="33c66-162">Ver envíos de administrador a Microsoft</span><span class="sxs-lookup"><span data-stu-id="33c66-162">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="33c66-163">En el portal Microsoft 365 Defender, vaya a **Correo electrónico &** \> **envíos de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="33c66-163">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="33c66-164">En la **página Envíos,** compruebe que la pestaña **Enviado** para el análisis está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="33c66-164">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="33c66-165">Puede ordenar las entradas haciendo clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="33c66-165">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="33c66-166">Haga **clic en** Personalizar columnas para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="33c66-166">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="33c66-167">Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="33c66-167">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="33c66-168">**Nombre del envío**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-168">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-169">**Remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-169">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-170">**Fecha enviada**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-170">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-171">**Tipo de envío**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-171">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-172">**Motivo para enviar**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-172">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-173">**Estado de reescaneo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-173">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-174">**Volver a examinar el resultado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-174">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-175">**Veredicto de filtro**</span><span class="sxs-lookup"><span data-stu-id="33c66-175">**Filter verdict**</span></span>
     - <span data-ttu-id="33c66-176">**Motivo de entrega/bloqueo**</span><span class="sxs-lookup"><span data-stu-id="33c66-176">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="33c66-177">**Identificador de envío**</span><span class="sxs-lookup"><span data-stu-id="33c66-177">**Submission ID**</span></span>
     - <span data-ttu-id="33c66-178">**Id. de mensaje de red/id. de objeto**</span><span class="sxs-lookup"><span data-stu-id="33c66-178">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="33c66-179">**Direction**</span><span class="sxs-lookup"><span data-stu-id="33c66-179">**Direction**</span></span>
     - <span data-ttu-id="33c66-180">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="33c66-180">**Sender IP**</span></span>
     - <span data-ttu-id="33c66-181">**Nivel de cumplimiento masivo (BCL)**</span><span class="sxs-lookup"><span data-stu-id="33c66-181">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="33c66-182">**Destino**</span><span class="sxs-lookup"><span data-stu-id="33c66-182">**Destination**</span></span>
     - <span data-ttu-id="33c66-183">**Acción de directiva**</span><span class="sxs-lookup"><span data-stu-id="33c66-183">**Policy action**</span></span>
     - <span data-ttu-id="33c66-184">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="33c66-184">**Submitted by**</span></span>

     <span data-ttu-id="33c66-185">Cuando haya terminado, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="33c66-185">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="33c66-186">Para filtrar las entradas, haga clic **en Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="33c66-186">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="33c66-187">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="33c66-187">The available filters are:</span></span>
     - <span data-ttu-id="33c66-188">**Fecha enviada:** **Fecha de inicio** y Fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="33c66-188">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="33c66-189">**Tipo de envío:** **Correo** **electrónico, dirección URL** o **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="33c66-189">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="33c66-190">**Identificador de envío:** valor GUID que se asigna a cada envío.</span><span class="sxs-lookup"><span data-stu-id="33c66-190">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="33c66-191">**Id. de mensaje de red**</span><span class="sxs-lookup"><span data-stu-id="33c66-191">**Network Message ID**</span></span>
     - <span data-ttu-id="33c66-192">**Sender**</span><span class="sxs-lookup"><span data-stu-id="33c66-192">**Sender**</span></span>

     <span data-ttu-id="33c66-193">Cuando haya terminado, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="33c66-193">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="33c66-194">![Nuevas opciones de filtro para envíos de administrador](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="33c66-194">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="33c66-195">Para agrupar las entradas, haga clic **en Agrupar** y seleccione uno de los siguientes valores de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="33c66-195">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="33c66-196">**Ninguna**</span><span class="sxs-lookup"><span data-stu-id="33c66-196">**None**</span></span>
     - <span data-ttu-id="33c66-197">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="33c66-197">**Type**</span></span>
     - <span data-ttu-id="33c66-198">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="33c66-198">**Reason**</span></span>
     - <span data-ttu-id="33c66-199">**Estado**</span><span class="sxs-lookup"><span data-stu-id="33c66-199">**Status**</span></span>
     - <span data-ttu-id="33c66-200">**Volver a examinar el resultado**</span><span class="sxs-lookup"><span data-stu-id="33c66-200">**Rescan result**</span></span>

   - <span data-ttu-id="33c66-201">Para exportar las entradas, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="33c66-201">To export the entries, click **Export**.</span></span> <span data-ttu-id="33c66-202">En el cuadro de diálogo que aparece, guarde el .csv archivo.</span><span class="sxs-lookup"><span data-stu-id="33c66-202">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="33c66-203">Detalles de reescaneo de envío de administrador</span><span class="sxs-lookup"><span data-stu-id="33c66-203">Admin submission rescan details</span></span>

<span data-ttu-id="33c66-204">Los mensajes que se envían en envíos de administrador se revisan y los resultados se muestran en el menú desplegable de detalles de envíos:</span><span class="sxs-lookup"><span data-stu-id="33c66-204">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="33c66-205">Si hubo un error en la autenticación de correo electrónico del remitente en el momento de la entrega.</span><span class="sxs-lookup"><span data-stu-id="33c66-205">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="33c66-206">Información sobre los aciertos de directiva que puedan haber afectado o invalidado el veredicto de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="33c66-206">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="33c66-207">Actualice los resultados de cancelación para ver si las direcciones URL o los archivos contenidos en el mensaje son malintencionados o no.</span><span class="sxs-lookup"><span data-stu-id="33c66-207">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="33c66-208">Comentarios de los calificadores.</span><span class="sxs-lookup"><span data-stu-id="33c66-208">Feedback from graders.</span></span>

<span data-ttu-id="33c66-209">Si se encontró una invalidación, se volverá a ejecutar una detección que se completará en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="33c66-209">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="33c66-210">Si no hubo un problema en la autenticación o entrega de correo electrónico no se vio afectado por una invalidación, los comentarios de los calificadores podrían tardar hasta un día.</span><span class="sxs-lookup"><span data-stu-id="33c66-210">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="33c66-211">Ver envíos de usuario a Microsoft</span><span class="sxs-lookup"><span data-stu-id="33c66-211">View user submissions to Microsoft</span></span>

<span data-ttu-id="33c66-212">Si ha implementado el complemento Report  [Message](enable-the-report-message-add-in.md), el complemento Report [Phishing](enable-the-report-phish-add-in.md)o los usuarios usan los informes integrados en [Outlook en la Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)puede ver qué usuarios están informando en la pestaña Mensaje notificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="33c66-212">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="33c66-213">En el portal Microsoft 365 Defender, vaya a **Correo electrónico &** \> **envíos de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="33c66-213">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="33c66-214">En la **página Envíos,** seleccione la **pestaña Mensajes notificados por el** usuario.</span><span class="sxs-lookup"><span data-stu-id="33c66-214">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="33c66-215">Puede ordenar las entradas haciendo clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="33c66-215">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="33c66-216">Haga **clic en** Personalizar columnas para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="33c66-216">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="33c66-217">Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="33c66-217">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="33c66-218">**Asunto del correo electrónico**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-218">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-219">**Notificado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-219">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-220">**Fecha notificada**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-220">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-221">**Remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-221">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-222">**Motivo notificado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-222">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-223">**Volver a examinar el resultado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33c66-223">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="33c66-224">**Id. de mensaje notificado**</span><span class="sxs-lookup"><span data-stu-id="33c66-224">**Message reported ID**</span></span>
     - <span data-ttu-id="33c66-225">**Id. de mensaje de red**</span><span class="sxs-lookup"><span data-stu-id="33c66-225">**Network Message ID**</span></span>
     - <span data-ttu-id="33c66-226">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="33c66-226">**Sender IP**</span></span>
     - <span data-ttu-id="33c66-227">**Simulación de phishing**</span><span class="sxs-lookup"><span data-stu-id="33c66-227">**Phish simulation**</span></span>

     <span data-ttu-id="33c66-228">Cuando haya terminado, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="33c66-228">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="33c66-229">Para filtrar las entradas, haga clic **en Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="33c66-229">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="33c66-230">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="33c66-230">The available filters are:</span></span>
     - <span data-ttu-id="33c66-231">**Fecha notificada**: **Fecha de inicio** y Fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="33c66-231">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="33c66-232">**Informe realizado por**</span><span class="sxs-lookup"><span data-stu-id="33c66-232">**Reported by**</span></span>
     - <span data-ttu-id="33c66-233">**Asunto del correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="33c66-233">**Email subject**</span></span>
     - <span data-ttu-id="33c66-234">**Id. de mensaje notificado**</span><span class="sxs-lookup"><span data-stu-id="33c66-234">**Message reported ID**</span></span>
     - <span data-ttu-id="33c66-235">**Id. de mensaje de red**</span><span class="sxs-lookup"><span data-stu-id="33c66-235">**Network Message ID**</span></span>
     - <span data-ttu-id="33c66-236">**Sender**</span><span class="sxs-lookup"><span data-stu-id="33c66-236">**Sender**</span></span>
     - <span data-ttu-id="33c66-237">**Motivo notificado:** **No es correo no** deseado, **phish** o correo **no deseado.**</span><span class="sxs-lookup"><span data-stu-id="33c66-237">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="33c66-238">**Simulación de phish:** **Sí** o **No**</span><span class="sxs-lookup"><span data-stu-id="33c66-238">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="33c66-239">Cuando haya terminado, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="33c66-239">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="33c66-240">![Nuevas opciones de filtro para envíos de usuarios](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="33c66-240">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="33c66-241">Para agrupar las entradas, haga clic **en Agrupar** y seleccione uno de los siguientes valores de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="33c66-241">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="33c66-242">**Ninguna**</span><span class="sxs-lookup"><span data-stu-id="33c66-242">**None**</span></span>
     - <span data-ttu-id="33c66-243">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="33c66-243">**Reason**</span></span>
     - <span data-ttu-id="33c66-244">**Sender**</span><span class="sxs-lookup"><span data-stu-id="33c66-244">**Sender**</span></span>
     - <span data-ttu-id="33c66-245">**Informe realizado por**</span><span class="sxs-lookup"><span data-stu-id="33c66-245">**Reported by**</span></span>
     - <span data-ttu-id="33c66-246">**Volver a examinar el resultado**</span><span class="sxs-lookup"><span data-stu-id="33c66-246">**Rescan result**</span></span>
     - <span data-ttu-id="33c66-247">**Simulación de phishing**</span><span class="sxs-lookup"><span data-stu-id="33c66-247">**Phish simulation**</span></span>

   - <span data-ttu-id="33c66-248">Para exportar las entradas, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="33c66-248">To export the entries, click **Export**.</span></span> <span data-ttu-id="33c66-249">En el cuadro de diálogo que aparece, guarde el .csv archivo.</span><span class="sxs-lookup"><span data-stu-id="33c66-249">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="33c66-250">Si las organizaciones están configuradas para enviar mensajes notificados por el usuario solo  al buzón personalizado, los mensajes notificados no se enviarán para volver a examinarse y los resultados de los mensajes notificados por el usuario siempre estarán vacíos.</span><span class="sxs-lookup"><span data-stu-id="33c66-250">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="33c66-251">Deshacer envíos de usuarios</span><span class="sxs-lookup"><span data-stu-id="33c66-251">Undo user submissions</span></span>

<span data-ttu-id="33c66-252">Una vez que un usuario envía un correo electrónico sospechoso al buzón personalizado, el usuario y el administrador no tienen ninguna opción para deshacer el envío.</span><span class="sxs-lookup"><span data-stu-id="33c66-252">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="33c66-253">Si el usuario desea recuperar el correo electrónico, estará disponible para su recuperación en las carpetas Elementos eliminados o Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="33c66-253">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="33c66-254">Enviar mensajes a Microsoft desde el buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="33c66-254">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="33c66-255">Si ha configurado el buzón personalizado para interceptar mensajes notificados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="33c66-255">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="33c66-256">Esto mueve de forma eficaz un envío de usuario a un envío de administrador.</span><span class="sxs-lookup"><span data-stu-id="33c66-256">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="33c66-257">En la **pestaña Mensajes** notificados por el usuario, seleccione un mensaje en la lista, haga clic en Enviar a **Microsoft** para su análisis y, a continuación, seleccione uno de los siguientes valores de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="33c66-257">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="33c66-258">**Informe limpio**</span><span class="sxs-lookup"><span data-stu-id="33c66-258">**Report clean**</span></span>
- <span data-ttu-id="33c66-259">**Report phishing**</span><span class="sxs-lookup"><span data-stu-id="33c66-259">**Report phishing**</span></span>
- <span data-ttu-id="33c66-260">**Informar de malware**</span><span class="sxs-lookup"><span data-stu-id="33c66-260">**Report malware**</span></span>
- <span data-ttu-id="33c66-261">**Notificar correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="33c66-261">**Report spam**</span></span>
- <span data-ttu-id="33c66-262">**Investigación de desencadenadores**</span><span class="sxs-lookup"><span data-stu-id="33c66-262">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="33c66-263">![Nuevas opciones en el botón Acción](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="33c66-263">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>
