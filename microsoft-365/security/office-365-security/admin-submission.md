---
title: Envíos de administración
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el portal de envíos en el centro de seguridad & cumplimiento para enviar correos sospechosos, mensajes de suplantación de identidad (phishing), correo no deseado y otros mensajes potencialmente dañinos, direcciones URL y archivos a Microsoft para su análisis.
ms.openlocfilehash: 0c01afff2e9e5a656099192f3867bb3a6f1cee23
ms.sourcegitcommit: 7e003ee0a06f61bfb9f80441c3479fa3148afafe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "49568595"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="f534a-103">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f534a-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f534a-104">En Microsoft 365 organizaciones con buzones de correo en Exchange Online, los administradores pueden usar el portal de envíos del centro de seguridad & cumplimiento para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="f534a-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="f534a-105">Al enviar un correo electrónico, recibirá información sobre las directivas que puedan haber permitido el correo entrante en su inquilino, así como el examen de las direcciones URL y los datos adjuntos del correo.</span><span class="sxs-lookup"><span data-stu-id="f534a-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="f534a-106">Las directivas que pueden haber permitido un correo incluyen la lista de remitentes seguros de un usuario individual, así como directivas de nivel de inquilino, como reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="f534a-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="f534a-107">Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f534a-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f534a-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="f534a-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f534a-109">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f534a-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f534a-110">Para ir directamente a la página de **envío** , use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="f534a-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="f534a-111">Para enviar mensajes y archivos a Microsoft, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="f534a-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="f534a-112">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f534a-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="f534a-113">**Administración** de la organización en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f534a-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="f534a-114">Tenga en cuenta que se requiere la pertenencia a este grupo de roles para [ver los envíos de usuarios al buzón de correo personalizado](#view-user-submissions-to-the-custom-mailbox) , tal como se describe más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="f534a-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="f534a-115">Para obtener más información sobre cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f534a-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="f534a-116">Informar sobre contenido sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f534a-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="f534a-117">En el centro de seguridad & cumplimiento, vaya a envíos de **Administración de amenazas** \> **Submissions**, compruebe que se encuentran en la pestaña envíos **administrativos** y, a continuación, haga clic en **nuevo envío**.</span><span class="sxs-lookup"><span data-stu-id="f534a-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="f534a-118">Use el nuevo control flotante de **envío** que aparece para enviar el mensaje, la dirección URL o los datos adjuntos, tal como se describe en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="f534a-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="f534a-119">Enviar un correo electrónico cuestionable a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f534a-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="f534a-120">En la sección **tipo de objeto** , seleccione **correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="f534a-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="f534a-121">En la sección **formato de envío** , use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f534a-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="f534a-122">**Identificador de mensaje de red**: es un valor GUID que está disponible en el encabezado **x-MS-Exchange-Organization-Network-Message-ID** del mensaje, o en el encabezado **x-MS-Office365-Filtering-Correlation-ID** en los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="f534a-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="f534a-123">**Archivo**: haga clic en **elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="f534a-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="f534a-124">En el cuadro de diálogo que se abre, busque y seleccione el archivo. eml o. msg y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="f534a-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f534a-125">Los administradores con defender para Office 365 plan 1 o plan 2 pueden enviar mensajes con una antigüedad de 30 días.</span><span class="sxs-lookup"><span data-stu-id="f534a-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="f534a-126">Otros administradores solo podrán retroceder 7 días.</span><span class="sxs-lookup"><span data-stu-id="f534a-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="f534a-127">En la sección **destinatarios** , especifique uno o más destinatarios con los que desee ejecutar una comprobación de directiva.</span><span class="sxs-lookup"><span data-stu-id="f534a-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="f534a-128">La comprobación de la Directiva determinará si se ha omitido el análisis del correo electrónico debido a las directivas del usuario o la organización.</span><span class="sxs-lookup"><span data-stu-id="f534a-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="f534a-129">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f534a-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="f534a-130">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="f534a-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="f534a-131">**Debe haberse bloqueado**: seleccione **correo no deseado**, **phishing** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="f534a-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="f534a-132">Si no está seguro, use su mejor criterio.</span><span class="sxs-lookup"><span data-stu-id="f534a-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="f534a-133">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="f534a-133">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de dirección URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="f534a-135">Enviar una dirección URL sospechosa a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f534a-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="f534a-136">En la sección **tipo de objeto** , seleccione **dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="f534a-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="f534a-137">En el cuadro que aparece, escriba la dirección URL completa (por ejemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="f534a-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="f534a-138">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f534a-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="f534a-139">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="f534a-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="f534a-140">**Debe haberse bloqueado**: seleccione **suplantación de identidad (phishing)** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="f534a-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="f534a-141">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="f534a-141">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de correo electrónico](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="f534a-143">Enviar un archivo sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f534a-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="f534a-144">En la sección **tipo de objeto** , seleccione **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="f534a-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="f534a-145">Haga clic en **elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="f534a-145">Click **Choose File**.</span></span> <span data-ttu-id="f534a-146">En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="f534a-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="f534a-147">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f534a-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="f534a-148">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="f534a-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="f534a-149">**Debe haberse bloqueado**: el **malware** es la única opción y se selecciona automáticamente..</span><span class="sxs-lookup"><span data-stu-id="f534a-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="f534a-150">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="f534a-150">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de datos adjuntos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="f534a-152">Ver envíos de administración</span><span class="sxs-lookup"><span data-stu-id="f534a-152">View admin submissions</span></span>

<span data-ttu-id="f534a-153">En el centro de seguridad & cumplimiento, vaya a envíos de **Administración de amenazas** \> **Submissions**, compruebe que se encuentran en la pestaña envíos **administrativos** y, a continuación, haga clic en **nuevo envío**.</span><span class="sxs-lookup"><span data-stu-id="f534a-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="f534a-154">Cerca de la parte superior de la página, puede especificar una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por **identificador de envío** (un valor de GUID asignado a cada envío) introduciendo un valor en el cuadro y haciendo clic en el ![ botón actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="f534a-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="f534a-155">Update</span><span class="sxs-lookup"><span data-stu-id="f534a-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="f534a-156">Para cambiar los criterios de filtro, haga clic en el botón **identificador de envío** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="f534a-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="f534a-157">**Sender**</span><span class="sxs-lookup"><span data-stu-id="f534a-157">**Sender**</span></span>
- <span data-ttu-id="f534a-158">**Asunto/URL/nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="f534a-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="f534a-159">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="f534a-159">**Submitted by**</span></span>
- <span data-ttu-id="f534a-160">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f534a-160">**Submission type**</span></span>
- <span data-ttu-id="f534a-161">**Estado**</span><span class="sxs-lookup"><span data-stu-id="f534a-161">**Status**</span></span>

![Opciones de filtro para envíos de administración](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="f534a-163">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla** de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="f534a-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="f534a-164">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="f534a-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="f534a-165">Debajo del gráfico, hay tres pestañas: **correo electrónico** (predeterminado), **dirección URL** y **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="f534a-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="f534a-166">Ver envíos de correo electrónico de administrador</span><span class="sxs-lookup"><span data-stu-id="f534a-166">View admin email submissions</span></span>

<span data-ttu-id="f534a-167">Haga clic en la pestaña **correo electrónico** .</span><span class="sxs-lookup"><span data-stu-id="f534a-167">Click the **Email** tab.</span></span>

<span data-ttu-id="f534a-168">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="f534a-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f534a-169">**Date**</span><span class="sxs-lookup"><span data-stu-id="f534a-169">**Date**</span></span>
- <span data-ttu-id="f534a-170">**Identificador de envío**: un valor de GUID que se asigna a cada envío.</span><span class="sxs-lookup"><span data-stu-id="f534a-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="f534a-171">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-172">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-173">**Sender**</span><span class="sxs-lookup"><span data-stu-id="f534a-173">**Sender**</span></span>
- <span data-ttu-id="f534a-174">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-175">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f534a-175">**Submission type**</span></span>
- <span data-ttu-id="f534a-176">**Motivo de la entrega**</span><span class="sxs-lookup"><span data-stu-id="f534a-176">**Delivery reason**</span></span>
- <span data-ttu-id="f534a-177">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="f534a-178"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="f534a-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="f534a-179">Detalles de reexamen de envío de administración</span><span class="sxs-lookup"><span data-stu-id="f534a-179">Admin submission rescan details</span></span>

<span data-ttu-id="f534a-180">Los mensajes que se envían en los envíos de administración se vuelven a examinar y los resultados que se muestran en el flotante de detalles:</span><span class="sxs-lookup"><span data-stu-id="f534a-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="f534a-181">Si se produjo un error en la autenticación de correo electrónico del remitente en el momento de la entrega.</span><span class="sxs-lookup"><span data-stu-id="f534a-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="f534a-182">Información sobre las visitas de directivas que podrían haber afectado o invalidar el veredicto de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f534a-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="f534a-183">Detonaciones actuales resultados para ver si las direcciones URL o los archivos contenidos en el mensaje eran malintencionados o no.</span><span class="sxs-lookup"><span data-stu-id="f534a-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="f534a-184">Comentarios de los evaluadores.</span><span class="sxs-lookup"><span data-stu-id="f534a-184">Feedback from graders.</span></span>

<span data-ttu-id="f534a-185">Si se encontró una invalidación, el nuevo examen debe completarse en varios minutos.</span><span class="sxs-lookup"><span data-stu-id="f534a-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="f534a-186">Si no ha habido un problema en la autenticación de correo electrónico o la entrega no se ve afectada por un reemplazo, los comentarios de los evaluadores podrían tardar hasta un día.</span><span class="sxs-lookup"><span data-stu-id="f534a-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="f534a-187">Ver envíos de direcciones URL de administración</span><span class="sxs-lookup"><span data-stu-id="f534a-187">View admin URL submissions</span></span>

<span data-ttu-id="f534a-188">Haga clic en la ficha **dirección URL** .</span><span class="sxs-lookup"><span data-stu-id="f534a-188">Click the **URL** tab.</span></span>

<span data-ttu-id="f534a-189">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="f534a-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f534a-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="f534a-190">**Date**</span></span>
- <span data-ttu-id="f534a-191">**IDENTIFICADOR de envío**</span><span class="sxs-lookup"><span data-stu-id="f534a-191">**Submission ID**</span></span>
- <span data-ttu-id="f534a-192">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-194">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f534a-194">**Submission type**</span></span>
- <span data-ttu-id="f534a-195">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="f534a-196"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="f534a-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="f534a-197">Ver envíos de datos adjuntos de administración</span><span class="sxs-lookup"><span data-stu-id="f534a-197">View admin attachment submissions</span></span>

<span data-ttu-id="f534a-198">Haga clic en la pestaña **datos adjuntos** .</span><span class="sxs-lookup"><span data-stu-id="f534a-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="f534a-199">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="f534a-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f534a-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="f534a-200">**Date**</span></span>
- <span data-ttu-id="f534a-201">**IDENTIFICADOR de envío**</span><span class="sxs-lookup"><span data-stu-id="f534a-201">**Submission ID**</span></span>
- <span data-ttu-id="f534a-202">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-203">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-204">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f534a-204">**Submission type**</span></span>
- <span data-ttu-id="f534a-205">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="f534a-206"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="f534a-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="f534a-207">Ver envíos de usuarios a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f534a-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="f534a-208">Si ha implementado el [complemento de mensajes de informe](enable-the-report-message-add-in.md), o los usuarios usan la [creación de informes integrada en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), puede ver qué usuarios están notificando en la pestaña **envíos de usuarios** .</span><span class="sxs-lookup"><span data-stu-id="f534a-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="f534a-209">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **envíos** de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f534a-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="f534a-210">Seleccione la pestaña envíos de **usuarios** y, a continuación, haga clic en **nuevo envío**.</span><span class="sxs-lookup"><span data-stu-id="f534a-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="f534a-211">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="f534a-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f534a-212">**Enviado el**</span><span class="sxs-lookup"><span data-stu-id="f534a-212">**Submitted on**</span></span>
- <span data-ttu-id="f534a-213">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-214">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="f534a-215">**Sender**</span></span>
- <span data-ttu-id="f534a-216">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-217">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f534a-217">**Submission type**</span></span>

<span data-ttu-id="f534a-218"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="f534a-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="f534a-219">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por **remitente** introduciendo un valor en el cuadro y haciendo clic en el ![ botón actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="f534a-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="f534a-220">Update</span><span class="sxs-lookup"><span data-stu-id="f534a-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="f534a-221">Para cambiar los criterios de filtro, haga clic en el botón **remitente** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="f534a-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="f534a-222">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="f534a-222">**Sender domain**</span></span>
- <span data-ttu-id="f534a-223">**Subject**</span><span class="sxs-lookup"><span data-stu-id="f534a-223">**Subject**</span></span>
- <span data-ttu-id="f534a-224">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="f534a-224">**Submitted by**</span></span>
- <span data-ttu-id="f534a-225">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f534a-225">**Submission type**</span></span>
- <span data-ttu-id="f534a-226">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="f534a-226">**Sender IP**</span></span>

![Opciones de filtro para envíos de usuarios](../../media/user-submissions-filter-options.png)

<span data-ttu-id="f534a-228">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla** de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="f534a-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="f534a-229">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="f534a-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="f534a-230">Ver los envíos de usuarios al buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="f534a-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="f534a-231">**Si** ha [configurado un buzón personalizado](user-submission.md) para recibir mensajes que el usuario ha notificado, puede ver y enviar también los mensajes que se entregaron al buzón de informes.</span><span class="sxs-lookup"><span data-stu-id="f534a-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="f534a-232">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **envíos** de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f534a-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="f534a-233">Seleccione la ficha **buzón personalizado** .</span><span class="sxs-lookup"><span data-stu-id="f534a-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="f534a-234">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="f534a-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f534a-235">**Enviado el**</span><span class="sxs-lookup"><span data-stu-id="f534a-235">**Submitted on**</span></span>
- <span data-ttu-id="f534a-236">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-237">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="f534a-238">**Sender**</span></span>
- <span data-ttu-id="f534a-239">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f534a-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="f534a-240">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f534a-240">**Submission type**</span></span>

<span data-ttu-id="f534a-241">Cerca de la parte superior de la página, puede especificar una fecha de inicio, una fecha de finalización, y puede filtrar por **enviado** especificando un valor en el cuadro y haciendo clic en el ![ botón actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="f534a-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="f534a-242">Update</span><span class="sxs-lookup"><span data-stu-id="f534a-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="f534a-243">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla** de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="f534a-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="f534a-244">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="f534a-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="f534a-245">Deshacer envíos de usuario</span><span class="sxs-lookup"><span data-stu-id="f534a-245">Undo user submissions</span></span>

<span data-ttu-id="f534a-246">Una vez que un usuario envía un correo electrónico sospechoso al buzón personalizado, el usuario y el administrador no tienen la opción de deshacer el envío.</span><span class="sxs-lookup"><span data-stu-id="f534a-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="f534a-247">Si el usuario desea recuperar el correo electrónico, estará disponible para su recuperación en las carpetas elementos eliminados o correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="f534a-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="f534a-248">Enviar mensajes a Microsoft desde el buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="f534a-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="f534a-249">Si ha configurado el buzón personalizado para interceptar los mensajes detectados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="f534a-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="f534a-250">Esto mueve eficazmente un envío de usuario a un envío de administración.</span><span class="sxs-lookup"><span data-stu-id="f534a-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="f534a-251">En la ficha **buzón personalizado** , seleccione un mensaje de la lista, haga clic en el botón de **acción** y realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="f534a-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="f534a-252">**Limpiar informe**</span><span class="sxs-lookup"><span data-stu-id="f534a-252">**Report clean**</span></span>
- <span data-ttu-id="f534a-253">**Notificar phishing**</span><span class="sxs-lookup"><span data-stu-id="f534a-253">**Report phishing**</span></span>
- <span data-ttu-id="f534a-254">**Notificar malware**</span><span class="sxs-lookup"><span data-stu-id="f534a-254">**Report malware**</span></span>
- <span data-ttu-id="f534a-255">**Informar del correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="f534a-255">**Report spam**</span></span>

![Opciones del botón de acción](../../media/user-submission-custom-mailbox-action-button.png)
