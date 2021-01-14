---
title: Envíos de administrador
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
description: Los administradores pueden aprender a usar el portal de envíos del Centro de seguridad y cumplimiento de & para enviar correos electrónicos sospechosos, correos sospechosos de suplantación de identidad, correo no deseado y otros mensajes potencialmente perjudiciales, direcciones URL y archivos a Microsoft para su análisis.
ms.openlocfilehash: 432a245530d7906ae8babbc54176480d36315351
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864953"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="fdc6a-103">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="fdc6a-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fdc6a-104">En organizaciones de Microsoft 365 con buzones en Exchange Online, los administradores pueden usar el portal de envíos del Centro de seguridad & y cumplimiento para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="fdc6a-105">Cuando envíe un correo electrónico, recibirá información sobre las directivas que pueden haber permitido el correo electrónico entrante en su espacio empresarial, así como el examen de las direcciones URL y los datos adjuntos del correo.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="fdc6a-106">Las directivas que pueden haber permitido un correo incluyen la lista de remitentes seguros de un usuario individual, así como directivas de nivel de inquilino como reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="fdc6a-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="fdc6a-107">Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea Notificar mensajes y [archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="fdc6a-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fdc6a-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="fdc6a-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fdc6a-109">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fdc6a-110">Para ir directamente a la **página Envío,** use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="fdc6a-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="fdc6a-111">Para enviar mensajes y archivos a Microsoft, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="fdc6a-112">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fdc6a-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="fdc6a-113">**Administración de la** organización [en Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="fdc6a-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="fdc6a-114">Tenga en cuenta que es necesario pertenecer a este grupo de roles para ver los [envíos](#view-user-submissions-to-the-custom-mailbox) de usuarios al buzón personalizado, tal como se describe más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="fdc6a-115">Para obtener más información acerca de cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea Notificar mensajes y [archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="fdc6a-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="fdc6a-116">Notificar contenido sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="fdc6a-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="fdc6a-117">En el Centro de seguridad &  cumplimiento, vaya a Envíos de administración de amenazas, compruebe que está en la pestaña Envíos de administración y, a continuación, haga clic en \>  **Nuevo envío.** </span><span class="sxs-lookup"><span data-stu-id="fdc6a-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="fdc6a-118">Use **el menú desplegable Nuevo** envío que parece enviar el mensaje, la dirección URL o los datos adjuntos, tal como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="fdc6a-119">Enviar un correo electrónico cuestionable a Microsoft</span><span class="sxs-lookup"><span data-stu-id="fdc6a-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="fdc6a-120">En la **sección Tipo de** objeto, seleccione Correo **electrónico.**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="fdc6a-121">En la **sección Formato de** envío, usa una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="fdc6a-122">**Id.** de mensaje de red: es un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-Id** del mensaje o en el encabezado **X-MS-Office365-Filtering-Correlation-Id** en mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="fdc6a-123">**Archivo:** haga clic **en Elegir archivo.**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="fdc6a-124">En el cuadro de diálogo que se abre, busque y seleccione el archivo .eml o .msg y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fdc6a-125">Los administradores con Defender para Office 365 Plan 1 o Plan 2 pueden enviar mensajes con una antigüedad de 30 días.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="fdc6a-126">Otros administradores solo podrán volver 7 días atrás.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="fdc6a-127">En la **sección** Destinatarios, especifique uno o más destinatarios con los que desea ejecutar una comprobación de directiva.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="fdc6a-128">La comprobación de directivas determinará si el correo electrónico omitió el examen debido a directivas de usuario u organización.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="fdc6a-129">En la **sección Motivo del** envío, selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="fdc6a-130">**No debería haber sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="fdc6a-131">**Debería haber sido bloqueado:** Seleccionar **correo no** deseado, **suplantación** de identidad o **malware.**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="fdc6a-132">Si no está seguro, use su mejor criterio.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="fdc6a-133">Cuando haya terminado, haga clic en **el botón** Enviar.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-133">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de dirección URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="fdc6a-135">Enviar una dirección URL sospechosa a Microsoft</span><span class="sxs-lookup"><span data-stu-id="fdc6a-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="fdc6a-136">En la **sección Tipo de** objeto, seleccione Dirección **URL**.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="fdc6a-137">En el cuadro que aparece, escriba la dirección URL completa (por ejemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="fdc6a-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="fdc6a-138">En la **sección Motivo del** envío, selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="fdc6a-139">**No debería haber sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="fdc6a-140">**Debería haber sido bloqueado:** Seleccione **Suplantación de identidad** o **malware.**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="fdc6a-141">Cuando haya terminado, haga clic en **el botón** Enviar.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-141">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de correo electrónico](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="fdc6a-143">Enviar un archivo sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="fdc6a-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="fdc6a-144">En la **sección Tipo de** objeto, seleccione Datos **adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="fdc6a-145">Haga clic **en Elegir archivo.**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-145">Click **Choose File**.</span></span> <span data-ttu-id="fdc6a-146">En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="fdc6a-147">En la **sección Motivo del** envío, selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="fdc6a-148">**No debería haber sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="fdc6a-149">**Debería haber sido bloqueado:** **el malware** es la única opción y se selecciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="fdc6a-150">Cuando haya terminado, haga clic en **el botón** Enviar.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-150">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de datos adjuntos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="fdc6a-152">Ver envíos de administrador</span><span class="sxs-lookup"><span data-stu-id="fdc6a-152">View admin submissions</span></span>

<span data-ttu-id="fdc6a-153">En el Centro de seguridad &  cumplimiento, vaya a Envíos de administración de amenazas, compruebe que está en la pestaña Envíos de administración y, a continuación, haga clic en \>  **Nuevo envío.** </span><span class="sxs-lookup"><span data-stu-id="fdc6a-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="fdc6a-154">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por identificador de envío **(un** valor GUID asignado a cada envío) especificando un valor en el cuadro y haciendo clic en el botón Actualizar ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="fdc6a-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="fdc6a-155">Update</span><span class="sxs-lookup"><span data-stu-id="fdc6a-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="fdc6a-156">Para cambiar los criterios de filtro, haz clic en el botón **Id. de** envío y elige uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="fdc6a-157">**Sender**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-157">**Sender**</span></span>
- <span data-ttu-id="fdc6a-158">**Asunto/DIRECCIÓN URL/Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="fdc6a-159">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-159">**Submitted by**</span></span>
- <span data-ttu-id="fdc6a-160">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-160">**Submission type**</span></span>
- <span data-ttu-id="fdc6a-161">**Estado**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-161">**Status**</span></span>

![Opciones de filtro para envíos de administrador](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="fdc6a-163">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="fdc6a-164">En el cuadro de diálogo que aparece, guarde el archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="fdc6a-165">Debajo del gráfico, hay tres pestañas: **Correo** electrónico (predeterminado), **Dirección URL** y **Datos adjuntos.**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="fdc6a-166">Ver envíos de correo electrónico de administrador</span><span class="sxs-lookup"><span data-stu-id="fdc6a-166">View admin email submissions</span></span>

<span data-ttu-id="fdc6a-167">Haga clic en la **pestaña** Correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-167">Click the **Email** tab.</span></span>

<span data-ttu-id="fdc6a-168">Puede hacer clic en el **botón Opciones de** columna situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fdc6a-169">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-169">**Date**</span></span>
- <span data-ttu-id="fdc6a-170">**Identificador de** envío: un valor GUID que se asigna a cada envío.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="fdc6a-171">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-172">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-173">**Sender**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-173">**Sender**</span></span>
- <span data-ttu-id="fdc6a-174">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-175">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-175">**Submission type**</span></span>
- <span data-ttu-id="fdc6a-176">**Motivo de la entrega**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-176">**Delivery reason**</span></span>
- <span data-ttu-id="fdc6a-177">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="fdc6a-178"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="fdc6a-179">Detalles del nuevo análisis del envío de administrador</span><span class="sxs-lookup"><span data-stu-id="fdc6a-179">Admin submission rescan details</span></span>

<span data-ttu-id="fdc6a-180">Los mensajes que se envían en envíos de administrador se examinan de nuevo y los resultados se muestran en el menú desplegable de detalles:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="fdc6a-181">Si se ha produce un error en la autenticación de correo electrónico del remitente en el momento de la entrega.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="fdc6a-182">Información sobre los aciertos de directiva que podrían haber afectado o invalidado el veredicto de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="fdc6a-183">Resultados de detonación actuales para ver si las direcciones URL o los archivos contenidos en el mensaje eran malintencionados o no.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="fdc6a-184">Comentarios de los alumnos.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-184">Feedback from graders.</span></span>

<span data-ttu-id="fdc6a-185">Si se encontró una invalidación, el nuevo análisis debe completarse en varios minutos.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="fdc6a-186">Si no hubo un problema en la autenticación o entrega de correo electrónico no se vio afectado por una invalidación, los comentarios de los calificadores podrían tardar hasta un día.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="fdc6a-187">Ver envíos de url de administrador</span><span class="sxs-lookup"><span data-stu-id="fdc6a-187">View admin URL submissions</span></span>

<span data-ttu-id="fdc6a-188">Haga clic en la **pestaña Dirección** URL.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-188">Click the **URL** tab.</span></span>

<span data-ttu-id="fdc6a-189">Puede hacer clic en el **botón Opciones de** columna situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fdc6a-190">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-190">**Date**</span></span>
- <span data-ttu-id="fdc6a-191">**Id. de envío**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-191">**Submission ID**</span></span>
- <span data-ttu-id="fdc6a-192">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-194">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-194">**Submission type**</span></span>
- <span data-ttu-id="fdc6a-195">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="fdc6a-196"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="fdc6a-197">Ver envíos de datos adjuntos de administrador</span><span class="sxs-lookup"><span data-stu-id="fdc6a-197">View admin attachment submissions</span></span>

<span data-ttu-id="fdc6a-198">Haga clic en **la pestaña Datos** adjuntos.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="fdc6a-199">Puede hacer clic en el **botón Opciones de** columna situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fdc6a-200">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-200">**Date**</span></span>
- <span data-ttu-id="fdc6a-201">**Id. de envío**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-201">**Submission ID**</span></span>
- <span data-ttu-id="fdc6a-202">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-203">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-204">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-204">**Submission type**</span></span>
- <span data-ttu-id="fdc6a-205">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="fdc6a-206"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="fdc6a-207">Ver envíos de usuario a Microsoft</span><span class="sxs-lookup"><span data-stu-id="fdc6a-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="fdc6a-208">Si ha implementado el complemento Mensaje de [](enable-the-report-phish-add-in.md) [informe,](enable-the-report-message-add-in.md)el complemento de suplantación de identidad de informes o los usuarios usan los informes integrados en Outlook en [la Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)puede ver qué usuarios están informando en la pestaña **Envíos** de usuarios.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="fdc6a-209">En el Centro de & cumplimiento, vaya a **Envíos de administración** \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="fdc6a-210">Selecciona la **pestaña Envíos de** usuario y, a continuación, haz clic **en Nuevo envío.**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="fdc6a-211">Puede hacer clic en el **botón Opciones de** columna situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fdc6a-212">**Enviado en**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-212">**Submitted on**</span></span>
- <span data-ttu-id="fdc6a-213">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-214">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-215">**Sender**</span></span>
- <span data-ttu-id="fdc6a-216">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-217">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-217">**Submission type**</span></span>

<span data-ttu-id="fdc6a-218"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="fdc6a-219">Cerca de la parte superior de la página, puede escribir una fecha de  inicio, una fecha de finalización y , de forma predeterminada, puede filtrar por remitente especificando un valor en el cuadro y haciendo clic en el botón ![ Actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="fdc6a-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="fdc6a-220">Update</span><span class="sxs-lookup"><span data-stu-id="fdc6a-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="fdc6a-221">Para cambiar los criterios de filtro, haga clic en el **botón Remitente** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="fdc6a-222">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-222">**Sender domain**</span></span>
- <span data-ttu-id="fdc6a-223">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-223">**Subject**</span></span>
- <span data-ttu-id="fdc6a-224">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-224">**Submitted by**</span></span>
- <span data-ttu-id="fdc6a-225">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-225">**Submission type**</span></span>
- <span data-ttu-id="fdc6a-226">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-226">**Sender IP**</span></span>

![Opciones de filtro para envíos de usuarios](../../media/user-submissions-filter-options.png)

<span data-ttu-id="fdc6a-228">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="fdc6a-229">En el cuadro de diálogo que aparece, guarde el archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="fdc6a-230">Ver envíos de usuario al buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="fdc6a-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="fdc6a-231">**Si** ha configurado un [buzón personalizado](user-submission.md) para recibir mensajes notificados por el usuario, puede ver y enviar también los mensajes que se entregaron al buzón de informes.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="fdc6a-232">En el Centro de & cumplimiento, vaya a **Envíos de administración** \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="fdc6a-233">Seleccione la **pestaña Buzón personalizado.**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="fdc6a-234">Puede hacer clic en el **botón Opciones de** columna situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fdc6a-235">**Enviado en**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-235">**Submitted on**</span></span>
- <span data-ttu-id="fdc6a-236">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-237">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-238">**Sender**</span></span>
- <span data-ttu-id="fdc6a-239">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fdc6a-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="fdc6a-240">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-240">**Submission type**</span></span>

<span data-ttu-id="fdc6a-241">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y puede filtrar por **Enviado** especificando un valor en el cuadro y haciendo clic en el botón ![ Actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="fdc6a-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="fdc6a-242">Update</span><span class="sxs-lookup"><span data-stu-id="fdc6a-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="fdc6a-243">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="fdc6a-244">En el cuadro de diálogo que aparece, guarde el archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="fdc6a-245">Deshacer envíos de usuarios</span><span class="sxs-lookup"><span data-stu-id="fdc6a-245">Undo user submissions</span></span>

<span data-ttu-id="fdc6a-246">Una vez que un usuario envía un correo electrónico sospechoso al buzón personalizado, el usuario y el administrador no tienen la opción de deshacer el envío.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="fdc6a-247">Si el usuario desea recuperar el correo electrónico, estará disponible para su recuperación en las carpetas Elementos eliminados o Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="fdc6a-248">Enviar mensajes a Microsoft desde el buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="fdc6a-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="fdc6a-249">Si ha configurado el buzón personalizado para interceptar mensajes notificados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="fdc6a-250">Esto mueve de forma eficaz un envío de usuario a un envío de administrador.</span><span class="sxs-lookup"><span data-stu-id="fdc6a-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="fdc6a-251">En la **pestaña Buzón personalizado,** seleccione un  mensaje en la lista, haga clic en el botón Acción y realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="fdc6a-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="fdc6a-252">**Informe limpio**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-252">**Report clean**</span></span>
- <span data-ttu-id="fdc6a-253">**Informar sobre la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-253">**Report phishing**</span></span>
- <span data-ttu-id="fdc6a-254">**Notificar malware**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-254">**Report malware**</span></span>
- <span data-ttu-id="fdc6a-255">**Notificar correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="fdc6a-255">**Report spam**</span></span>

![Opciones del botón Acción](../../media/user-submission-custom-mailbox-action-button.png)
