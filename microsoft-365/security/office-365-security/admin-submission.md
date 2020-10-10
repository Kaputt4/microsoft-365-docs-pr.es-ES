---
title: Envíos de administración
f1.keywords:
- NOCSH
ms.author: chrisda
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
- m365-initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el portal de envíos en el centro de seguridad & cumplimiento para enviar correos sospechosos, mensajes de suplantación de identidad (phishing), correo no deseado y otros mensajes potencialmente dañinos, direcciones URL y archivos a Microsoft para su análisis.
ms.openlocfilehash: 5165761b96eefe85437743968502dada51bc297f
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412027"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="91fcb-103">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="91fcb-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="91fcb-104">En Microsoft 365 organizaciones con buzones de correo en Exchange Online, los administradores pueden usar el portal de envíos del centro de seguridad & cumplimiento para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="91fcb-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="91fcb-105">Al enviar un correo electrónico, recibirá información sobre las directivas que puedan haber permitido el correo entrante en su inquilino, así como el examen de las direcciones URL y los datos adjuntos del correo.</span><span class="sxs-lookup"><span data-stu-id="91fcb-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="91fcb-106">Las directivas que pueden haber permitido un correo incluyen la lista de remitentes seguros de un usuario individual, así como directivas de nivel de inquilino, como reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="91fcb-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="91fcb-107">Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="91fcb-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="91fcb-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="91fcb-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="91fcb-109">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="91fcb-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="91fcb-110">Para ir directamente a la página de **envío** , use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="91fcb-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="91fcb-111">Para enviar mensajes y archivos a Microsoft, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="91fcb-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="91fcb-112">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="91fcb-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="91fcb-113">**Administración** de la organización en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="91fcb-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="91fcb-114">Tenga en cuenta que se requiere la pertenencia a este grupo de roles para [ver los envíos de usuarios al buzón de correo personalizado](#view-user-submissions-to-the-custom-mailbox) , tal como se describe más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="91fcb-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="91fcb-115">Para obtener más información sobre cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="91fcb-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="91fcb-116">Informar sobre contenido sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="91fcb-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="91fcb-117">En el centro de seguridad & cumplimiento, vaya a envíos de **Administración de amenazas** \> **Submissions**, compruebe que se encuentran en la pestaña envíos **administrativos** y, a continuación, haga clic en **nuevo envío**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="91fcb-118">Use el nuevo control flotante de **envío** que aparece para enviar el mensaje, la dirección URL o los datos adjuntos, tal como se describe en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="91fcb-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="91fcb-119">Enviar un correo electrónico cuestionable a Microsoft</span><span class="sxs-lookup"><span data-stu-id="91fcb-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="91fcb-120">En la sección **tipo de objeto** , seleccione **correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="91fcb-121">En la sección **formato de envío** , use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="91fcb-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="91fcb-122">**Identificador de mensaje de red**: es un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-ID** del mensaje.</span><span class="sxs-lookup"><span data-stu-id="91fcb-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="91fcb-123">**Archivo**: haga clic en **elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="91fcb-124">En el cuadro de diálogo que se abre, busque y seleccione el archivo. eml o. msg y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="91fcb-125">En la sección **destinatarios** , especifique uno o más destinatarios con los que desee ejecutar una comprobación de directiva.</span><span class="sxs-lookup"><span data-stu-id="91fcb-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="91fcb-126">La comprobación de la Directiva determinará si se ha omitido el análisis del correo electrónico debido a las directivas del usuario o la organización.</span><span class="sxs-lookup"><span data-stu-id="91fcb-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="91fcb-127">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="91fcb-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="91fcb-128">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="91fcb-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="91fcb-129">**Debe haberse bloqueado**: seleccione **correo no deseado**, **phishing**o **malware**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="91fcb-130">Si no está seguro, use su mejor criterio.</span><span class="sxs-lookup"><span data-stu-id="91fcb-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="91fcb-131">Si se ha omitido el filtro debido a las directivas tras el envío, verá información sobre esa Directiva.</span><span class="sxs-lookup"><span data-stu-id="91fcb-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="91fcb-132">Si no se ha omitido el filtro debido a una o más directivas, el análisis se completará en varios minutos.</span><span class="sxs-lookup"><span data-stu-id="91fcb-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="91fcb-133">Para ver más información sobre el envío, haga clic en el vínculo estado.</span><span class="sxs-lookup"><span data-stu-id="91fcb-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="91fcb-134">Esto incluye los resultados de la comprobación de la Directiva y el veredicto de reescaneo.</span><span class="sxs-lookup"><span data-stu-id="91fcb-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="91fcb-135">Nota Esto no ejecuta el correo electrónico a través de la pila de filtrado completo de ATP de Office 365, sino que ejecuta un nuevo análisis parcial en función de determinados atributos del correo, la dirección URL o el archivo.</span><span class="sxs-lookup"><span data-stu-id="91fcb-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="91fcb-136">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="91fcb-136">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de dirección URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="91fcb-138">Enviar una dirección URL sospechosa a Microsoft</span><span class="sxs-lookup"><span data-stu-id="91fcb-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="91fcb-139">En la sección **tipo de objeto** , seleccione **dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="91fcb-140">En el cuadro que aparece, escriba la dirección URL completa (por ejemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="91fcb-140">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="91fcb-141">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="91fcb-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="91fcb-142">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="91fcb-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="91fcb-143">**Debe haberse bloqueado**: seleccione **suplantación de identidad (phishing)** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="91fcb-144">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="91fcb-144">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de correo electrónico](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="91fcb-146">Enviar un archivo sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="91fcb-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="91fcb-147">En la sección **tipo de objeto** , seleccione **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="91fcb-148">Haga clic en **elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-148">Click **Choose File**.</span></span> <span data-ttu-id="91fcb-149">En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="91fcb-150">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="91fcb-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="91fcb-151">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="91fcb-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="91fcb-152">**Debe haberse bloqueado**: el **malware** es la única opción y se selecciona automáticamente..</span><span class="sxs-lookup"><span data-stu-id="91fcb-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="91fcb-153">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="91fcb-153">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de datos adjuntos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="91fcb-155">Ver envíos de administración</span><span class="sxs-lookup"><span data-stu-id="91fcb-155">View admin submissions</span></span>

<span data-ttu-id="91fcb-156">En el centro de seguridad & cumplimiento, vaya a envíos de **Administración de amenazas** \> **Submissions**, compruebe que se encuentran en la pestaña envíos **administrativos** y, a continuación, haga clic en **nuevo envío**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="91fcb-157">Cerca de la parte superior de la página, puede especificar una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por **identificador de envío** (un valor de GUID asignado a cada envío) introduciendo un valor en el cuadro y haciendo clic en el ![ botón actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="91fcb-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="91fcb-158">Update</span><span class="sxs-lookup"><span data-stu-id="91fcb-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="91fcb-159">Para cambiar los criterios de filtro, haga clic en el botón **identificador de envío** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="91fcb-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="91fcb-160">**Sender**</span><span class="sxs-lookup"><span data-stu-id="91fcb-160">**Sender**</span></span>
- <span data-ttu-id="91fcb-161">**Asunto/URL/nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="91fcb-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="91fcb-162">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="91fcb-162">**Submitted by**</span></span>
- <span data-ttu-id="91fcb-163">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="91fcb-163">**Submission type**</span></span>
- <span data-ttu-id="91fcb-164">**Estado**</span><span class="sxs-lookup"><span data-stu-id="91fcb-164">**Status**</span></span>

![Opciones de filtro para envíos de administración](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="91fcb-166">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="91fcb-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="91fcb-167">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="91fcb-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="91fcb-168">Debajo del gráfico, hay tres pestañas: **correo electrónico** (predeterminado), **dirección URL**y **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-168">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="91fcb-169">Ver envíos de correo electrónico de administrador</span><span class="sxs-lookup"><span data-stu-id="91fcb-169">View admin email submissions</span></span>

<span data-ttu-id="91fcb-170">Haga clic en la pestaña **correo electrónico** .</span><span class="sxs-lookup"><span data-stu-id="91fcb-170">Click the **Email** tab.</span></span>

<span data-ttu-id="91fcb-171">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="91fcb-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="91fcb-172">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="91fcb-172">**Date**</span></span>
- <span data-ttu-id="91fcb-173">**Identificador de envío**: un valor de GUID que se asigna a cada envío.</span><span class="sxs-lookup"><span data-stu-id="91fcb-173">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="91fcb-174">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-175">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-176">**Sender**</span><span class="sxs-lookup"><span data-stu-id="91fcb-176">**Sender**</span></span>
- <span data-ttu-id="91fcb-177">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-178">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="91fcb-178">**Submission type**</span></span>
- <span data-ttu-id="91fcb-179">**Motivo de la entrega**</span><span class="sxs-lookup"><span data-stu-id="91fcb-179">**Delivery reason**</span></span>
- <span data-ttu-id="91fcb-180">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-181">**Tipo de control**</span><span class="sxs-lookup"><span data-stu-id="91fcb-181">**Control type**</span></span>
- <span data-ttu-id="91fcb-182">**Origen del control**</span><span class="sxs-lookup"><span data-stu-id="91fcb-182">**Control source**</span></span>

  <span data-ttu-id="91fcb-183"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="91fcb-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="91fcb-184">Ver envíos de direcciones URL de administración</span><span class="sxs-lookup"><span data-stu-id="91fcb-184">View admin URL submissions</span></span>

<span data-ttu-id="91fcb-185">Haga clic en la ficha **dirección URL** .</span><span class="sxs-lookup"><span data-stu-id="91fcb-185">Click the **URL** tab.</span></span>

<span data-ttu-id="91fcb-186">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="91fcb-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="91fcb-187">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="91fcb-187">**Date**</span></span>
- <span data-ttu-id="91fcb-188">**IDENTIFICADOR de envío**</span><span class="sxs-lookup"><span data-stu-id="91fcb-188">**Submission ID**</span></span>
- <span data-ttu-id="91fcb-189">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-190">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-191">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="91fcb-191">**Submission type**</span></span>
- <span data-ttu-id="91fcb-192">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="91fcb-193"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="91fcb-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="91fcb-194">Ver envíos de datos adjuntos de administración</span><span class="sxs-lookup"><span data-stu-id="91fcb-194">View admin attachment submissions</span></span>

<span data-ttu-id="91fcb-195">Haga clic en la pestaña **datos adjuntos** .</span><span class="sxs-lookup"><span data-stu-id="91fcb-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="91fcb-196">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="91fcb-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="91fcb-197">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="91fcb-197">**Date**</span></span>
- <span data-ttu-id="91fcb-198">**IDENTIFICADOR de envío**</span><span class="sxs-lookup"><span data-stu-id="91fcb-198">**Submission ID**</span></span>
- <span data-ttu-id="91fcb-199">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-200">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-201">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="91fcb-201">**Submission type**</span></span>
- <span data-ttu-id="91fcb-202">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="91fcb-203"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="91fcb-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="91fcb-204">Ver envíos de usuarios a Microsoft</span><span class="sxs-lookup"><span data-stu-id="91fcb-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="91fcb-205">Si ha implementado el [complemento de mensajes de informe](enable-the-report-message-add-in.md), o los usuarios usan la [creación de informes integrada en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), puede ver qué usuarios están notificando en la pestaña **envíos de usuarios** .</span><span class="sxs-lookup"><span data-stu-id="91fcb-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="91fcb-206">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **envíos**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="91fcb-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="91fcb-207">Seleccione la pestaña envíos de **usuarios** y, a continuación, haga clic en **nuevo envío**.</span><span class="sxs-lookup"><span data-stu-id="91fcb-207">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="91fcb-208">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="91fcb-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="91fcb-209">**Enviado el**</span><span class="sxs-lookup"><span data-stu-id="91fcb-209">**Submitted on**</span></span>
- <span data-ttu-id="91fcb-210">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-211">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-212">**Sender**</span><span class="sxs-lookup"><span data-stu-id="91fcb-212">**Sender**</span></span>
- <span data-ttu-id="91fcb-213">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-214">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="91fcb-214">**Submission type**</span></span>

<span data-ttu-id="91fcb-215"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="91fcb-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="91fcb-216">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por **remitente** introduciendo un valor en el cuadro y haciendo clic en el ![ botón actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="91fcb-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="91fcb-217">Update</span><span class="sxs-lookup"><span data-stu-id="91fcb-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="91fcb-218">Para cambiar los criterios de filtro, haga clic en el botón **remitente** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="91fcb-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="91fcb-219">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="91fcb-219">**Sender domain**</span></span>
- <span data-ttu-id="91fcb-220">**Subject**</span><span class="sxs-lookup"><span data-stu-id="91fcb-220">**Subject**</span></span>
- <span data-ttu-id="91fcb-221">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="91fcb-221">**Submitted by**</span></span>
- <span data-ttu-id="91fcb-222">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="91fcb-222">**Submission type**</span></span>
- <span data-ttu-id="91fcb-223">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="91fcb-223">**Sender IP**</span></span>

![Opciones de filtro para envíos de usuarios](../../media/user-submissions-filter-options.png)

<span data-ttu-id="91fcb-225">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="91fcb-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="91fcb-226">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="91fcb-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="91fcb-227">Ver los envíos de usuarios al buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="91fcb-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="91fcb-228">**Si** ha [configurado un buzón personalizado](user-submission.md) para recibir mensajes que el usuario ha notificado, puede ver y enviar también los mensajes que se entregaron al buzón de informes.</span><span class="sxs-lookup"><span data-stu-id="91fcb-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="91fcb-229">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **envíos**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="91fcb-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="91fcb-230">Seleccione la ficha **buzón personalizado** .</span><span class="sxs-lookup"><span data-stu-id="91fcb-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="91fcb-231">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="91fcb-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="91fcb-232">**Enviado el**</span><span class="sxs-lookup"><span data-stu-id="91fcb-232">**Submitted on**</span></span>
- <span data-ttu-id="91fcb-233">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-234">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-235">**Sender**</span><span class="sxs-lookup"><span data-stu-id="91fcb-235">**Sender**</span></span>
- <span data-ttu-id="91fcb-236">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="91fcb-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="91fcb-237">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="91fcb-237">**Submission type**</span></span>

<span data-ttu-id="91fcb-238">Cerca de la parte superior de la página, puede especificar una fecha de inicio, una fecha de finalización, y puede filtrar por **enviado** especificando un valor en el cuadro y haciendo clic en el ![ botón actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="91fcb-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="91fcb-239">Update</span><span class="sxs-lookup"><span data-stu-id="91fcb-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="91fcb-240">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="91fcb-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="91fcb-241">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="91fcb-241">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="91fcb-242">Enviar mensajes a Microsoft desde el buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="91fcb-242">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="91fcb-243">Si ha configurado el buzón personalizado para interceptar los mensajes detectados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="91fcb-243">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="91fcb-244">Esto mueve eficazmente un envío de usuario a un envío de administración.</span><span class="sxs-lookup"><span data-stu-id="91fcb-244">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="91fcb-245">En la ficha **buzón personalizado** , seleccione un mensaje de la lista, haga clic en el botón de **acción** y realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="91fcb-245">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="91fcb-246">**Limpiar informe**</span><span class="sxs-lookup"><span data-stu-id="91fcb-246">**Report clean**</span></span>
- <span data-ttu-id="91fcb-247">**Notificar phishing**</span><span class="sxs-lookup"><span data-stu-id="91fcb-247">**Report phishing**</span></span>
- <span data-ttu-id="91fcb-248">**Notificar malware**</span><span class="sxs-lookup"><span data-stu-id="91fcb-248">**Report malware**</span></span>
- <span data-ttu-id="91fcb-249">**Informar del correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="91fcb-249">**Report spam**</span></span>

![Opciones del botón de acción](../../media/user-submission-custom-mailbox-action-button.png)
