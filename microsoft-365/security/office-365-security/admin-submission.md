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
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el portal de envíos en el centro de seguridad & cumplimiento para enviar correos sospechosos, mensajes de suplantación de identidad (phishing), correo no deseado y otros mensajes potencialmente dañinos, direcciones URL y archivos a Microsoft para su análisis.
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845971"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="27a8c-103">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="27a8c-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="27a8c-104">En Microsoft 365 organizaciones con buzones de correo en Exchange Online, los administradores pueden usar el portal de envíos del centro de seguridad & cumplimiento para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="27a8c-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="27a8c-105">Al enviar un correo electrónico, recibirá información sobre las directivas que puedan haber permitido el correo entrante en su inquilino, así como el examen de las direcciones URL y los datos adjuntos del correo.</span><span class="sxs-lookup"><span data-stu-id="27a8c-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="27a8c-106">Las directivas que pueden haber permitido un correo incluyen la lista de remitentes seguros de un usuario individual, así como directivas de nivel de inquilino, como reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="27a8c-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="27a8c-107">Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="27a8c-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="27a8c-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="27a8c-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="27a8c-109">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="27a8c-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="27a8c-110">Para ir directamente a la página de **envío** , use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="27a8c-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="27a8c-111">Para poder realizar los procedimientos de este tema, deberá tener asignados los permisos necesarios:</span><span class="sxs-lookup"><span data-stu-id="27a8c-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="27a8c-112">Para enviar mensajes y archivos a Microsoft, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="27a8c-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="27a8c-113">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="27a8c-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="27a8c-114">**Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="27a8c-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="27a8c-115">Para obtener acceso de solo lectura al portal de envíos, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="27a8c-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="27a8c-116">**Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="27a8c-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="27a8c-117">**Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="27a8c-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="27a8c-118">Para obtener más información sobre cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="27a8c-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="27a8c-119">Informar sobre contenido sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="27a8c-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="27a8c-120">En el centro de seguridad & cumplimiento, vaya a envíos de **Administración de amenazas** \> **Submissions**, compruebe que se encuentran en la pestaña envíos **administrativos** y, a continuación, haga clic en **nuevo envío**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-120">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="27a8c-121">Use el nuevo control flotante de **envío** que aparece para enviar el mensaje, la dirección URL o los datos adjuntos, tal como se describe en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="27a8c-121">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="27a8c-122">Enviar un correo electrónico cuestionable a Microsoft</span><span class="sxs-lookup"><span data-stu-id="27a8c-122">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="27a8c-123">En la sección **tipo de objeto** , seleccione **correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-123">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="27a8c-124">En la sección **formato de envío** , use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="27a8c-124">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="27a8c-125">**Identificador de mensaje de red**: es un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-ID** del mensaje.</span><span class="sxs-lookup"><span data-stu-id="27a8c-125">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="27a8c-126">**Archivo**: haga clic en **elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-126">**File**: Click **Choose file**.</span></span> <span data-ttu-id="27a8c-127">En el cuadro de diálogo que se abre, busque y seleccione el archivo. eml o. msg y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-127">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="27a8c-128">En la sección **destinatarios** , especifique uno o más destinatarios con los que desee ejecutar una comprobación de directiva.</span><span class="sxs-lookup"><span data-stu-id="27a8c-128">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="27a8c-129">La comprobación de la Directiva determinará si se ha omitido el análisis del correo electrónico debido a las directivas del usuario o la organización.</span><span class="sxs-lookup"><span data-stu-id="27a8c-129">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="27a8c-130">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="27a8c-130">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="27a8c-131">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="27a8c-131">**Should not have been blocked**</span></span>

   - <span data-ttu-id="27a8c-132">**Debe haberse bloqueado**: seleccione **correo no deseado**, **phishing**o **malware**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-132">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="27a8c-133">Si no está seguro, use su mejor criterio.</span><span class="sxs-lookup"><span data-stu-id="27a8c-133">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="27a8c-134">Si se ha omitido el filtro debido a las directivas tras el envío, verá información sobre esa Directiva.</span><span class="sxs-lookup"><span data-stu-id="27a8c-134">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="27a8c-135">Si no se ha omitido el filtro debido a una o más directivas, el análisis se completará en varios minutos.</span><span class="sxs-lookup"><span data-stu-id="27a8c-135">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="27a8c-136">Para ver más información sobre el envío, haga clic en el vínculo estado.</span><span class="sxs-lookup"><span data-stu-id="27a8c-136">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="27a8c-137">Esto incluye los resultados de la comprobación de la Directiva y el veredicto de reescaneo.</span><span class="sxs-lookup"><span data-stu-id="27a8c-137">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="27a8c-138">Nota Esto no ejecuta el correo electrónico a través de la pila de filtrado completo de ATP de Office 365, sino que ejecuta un nuevo análisis parcial en función de determinados atributos del correo, la dirección URL o el archivo.</span><span class="sxs-lookup"><span data-stu-id="27a8c-138">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="27a8c-139">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="27a8c-139">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de dirección URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="27a8c-141">Enviar una dirección URL sospechosa a Microsoft</span><span class="sxs-lookup"><span data-stu-id="27a8c-141">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="27a8c-142">En la sección **tipo de objeto** , seleccione **dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-142">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="27a8c-143">En el cuadro que aparece, escriba la dirección URL completa (por ejemplo, <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="27a8c-143">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="27a8c-144">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="27a8c-144">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="27a8c-145">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="27a8c-145">**Should not have been blocked**</span></span>

   - <span data-ttu-id="27a8c-146">**Debe haberse bloqueado**: seleccione **suplantación de identidad (phishing)** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-146">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="27a8c-147">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="27a8c-147">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de correo electrónico](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="27a8c-149">Enviar un archivo sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="27a8c-149">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="27a8c-150">En la sección **tipo de objeto** , seleccione **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-150">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="27a8c-151">Haga clic en **elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-151">Click **Choose File**.</span></span> <span data-ttu-id="27a8c-152">En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-152">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="27a8c-153">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="27a8c-153">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="27a8c-154">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="27a8c-154">**Should not have been blocked**</span></span>

   - <span data-ttu-id="27a8c-155">**Debe haberse bloqueado**: el **malware** es la única opción y se selecciona automáticamente..</span><span class="sxs-lookup"><span data-stu-id="27a8c-155">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="27a8c-156">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="27a8c-156">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de datos adjuntos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="27a8c-158">Ver envíos de administración</span><span class="sxs-lookup"><span data-stu-id="27a8c-158">View admin submissions</span></span>

<span data-ttu-id="27a8c-159">En el centro de seguridad & cumplimiento, vaya a envíos de **Administración de amenazas** \> **Submissions**, compruebe que se encuentran en la pestaña envíos **administrativos** y, a continuación, haga clic en **nuevo envío**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-159">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="27a8c-160">Cerca de la parte superior de la página, puede especificar una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por **identificador de envío** (un valor de GUID asignado a cada envío) introduciendo un valor en el cuadro y haciendo clic en el ![ botón actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="27a8c-160">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="27a8c-161">Update</span><span class="sxs-lookup"><span data-stu-id="27a8c-161">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="27a8c-162">Para cambiar los criterios de filtro, haga clic en el botón **identificador de envío** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="27a8c-162">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="27a8c-163">**Sender**</span><span class="sxs-lookup"><span data-stu-id="27a8c-163">**Sender**</span></span>
- <span data-ttu-id="27a8c-164">**Asunto/URL/nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="27a8c-164">**Subject/URL/File name**</span></span>
- <span data-ttu-id="27a8c-165">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="27a8c-165">**Submitted by**</span></span>
- <span data-ttu-id="27a8c-166">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="27a8c-166">**Submission type**</span></span>
- <span data-ttu-id="27a8c-167">**Estado**</span><span class="sxs-lookup"><span data-stu-id="27a8c-167">**Status**</span></span>

![Opciones de filtro para envíos de administración](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="27a8c-169">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="27a8c-169">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="27a8c-170">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="27a8c-170">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="27a8c-171">Debajo del gráfico, hay tres pestañas: **correo electrónico** (predeterminado), **dirección URL**y **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-171">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="27a8c-172">Ver envíos de correo electrónico de administrador</span><span class="sxs-lookup"><span data-stu-id="27a8c-172">View admin email submissions</span></span>

<span data-ttu-id="27a8c-173">Haga clic en la pestaña **correo electrónico** .</span><span class="sxs-lookup"><span data-stu-id="27a8c-173">Click the **Email** tab.</span></span>

<span data-ttu-id="27a8c-174">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="27a8c-174">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="27a8c-175">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="27a8c-175">**Date**</span></span>
- <span data-ttu-id="27a8c-176">**Identificador de envío**: un valor de GUID que se asigna a cada envío.</span><span class="sxs-lookup"><span data-stu-id="27a8c-176">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="27a8c-177">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-177">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-178">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-178">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-179">**Sender**</span><span class="sxs-lookup"><span data-stu-id="27a8c-179">**Sender**</span></span>
- <span data-ttu-id="27a8c-180">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-180">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-181">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="27a8c-181">**Submission type**</span></span>
- <span data-ttu-id="27a8c-182">**Motivo de la entrega**</span><span class="sxs-lookup"><span data-stu-id="27a8c-182">**Delivery reason**</span></span>
- <span data-ttu-id="27a8c-183">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-183">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-184">**Tipo de control**</span><span class="sxs-lookup"><span data-stu-id="27a8c-184">**Control type**</span></span>
- <span data-ttu-id="27a8c-185">**Origen del control**</span><span class="sxs-lookup"><span data-stu-id="27a8c-185">**Control source**</span></span>

  <span data-ttu-id="27a8c-186"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="27a8c-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="27a8c-187">Ver envíos de direcciones URL de administración</span><span class="sxs-lookup"><span data-stu-id="27a8c-187">View admin URL submissions</span></span>

<span data-ttu-id="27a8c-188">Haga clic en la ficha **dirección URL** .</span><span class="sxs-lookup"><span data-stu-id="27a8c-188">Click the **URL** tab.</span></span>

<span data-ttu-id="27a8c-189">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="27a8c-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="27a8c-190">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="27a8c-190">**Date**</span></span>
- <span data-ttu-id="27a8c-191">**IDENTIFICADOR de envío**</span><span class="sxs-lookup"><span data-stu-id="27a8c-191">**Submission ID**</span></span>
- <span data-ttu-id="27a8c-192">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-194">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="27a8c-194">**Submission type**</span></span>
- <span data-ttu-id="27a8c-195">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="27a8c-196"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="27a8c-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="27a8c-197">Ver envíos de datos adjuntos de administración</span><span class="sxs-lookup"><span data-stu-id="27a8c-197">View admin attachment submissions</span></span>

<span data-ttu-id="27a8c-198">Haga clic en la pestaña **datos adjuntos** .</span><span class="sxs-lookup"><span data-stu-id="27a8c-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="27a8c-199">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="27a8c-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="27a8c-200">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="27a8c-200">**Date**</span></span>
- <span data-ttu-id="27a8c-201">**IDENTIFICADOR de envío**</span><span class="sxs-lookup"><span data-stu-id="27a8c-201">**Submission ID**</span></span>
- <span data-ttu-id="27a8c-202">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-203">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-204">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="27a8c-204">**Submission type**</span></span>
- <span data-ttu-id="27a8c-205">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="27a8c-206"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="27a8c-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="27a8c-207">Ver envíos de usuarios a Microsoft</span><span class="sxs-lookup"><span data-stu-id="27a8c-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="27a8c-208">Si ha implementado el [complemento de mensajes de informe](enable-the-report-message-add-in.md), o los usuarios usan la [creación de informes integrada en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), puede ver qué usuarios están notificando en la pestaña **envíos de usuarios** .</span><span class="sxs-lookup"><span data-stu-id="27a8c-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="27a8c-209">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **envíos**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="27a8c-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="27a8c-210">Seleccione la pestaña envíos de **usuarios** y, a continuación, haga clic en **nuevo envío**.</span><span class="sxs-lookup"><span data-stu-id="27a8c-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="27a8c-211">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="27a8c-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="27a8c-212">**Enviado el**</span><span class="sxs-lookup"><span data-stu-id="27a8c-212">**Submitted on**</span></span>
- <span data-ttu-id="27a8c-213">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-214">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="27a8c-215">**Sender**</span></span>
- <span data-ttu-id="27a8c-216">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-217">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="27a8c-217">**Submission type**</span></span>

<span data-ttu-id="27a8c-218"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="27a8c-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="27a8c-219">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por **remitente** introduciendo un valor en el cuadro y haciendo clic en el ![ botón actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="27a8c-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="27a8c-220">Update</span><span class="sxs-lookup"><span data-stu-id="27a8c-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="27a8c-221">Para cambiar los criterios de filtro, haga clic en el botón **remitente** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="27a8c-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="27a8c-222">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="27a8c-222">**Sender domain**</span></span>
- <span data-ttu-id="27a8c-223">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="27a8c-223">**Subject**</span></span>
- <span data-ttu-id="27a8c-224">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="27a8c-224">**Submitted by**</span></span>
- <span data-ttu-id="27a8c-225">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="27a8c-225">**Submission type**</span></span>
- <span data-ttu-id="27a8c-226">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="27a8c-226">**Sender IP**</span></span>

![Opciones de filtro para envíos de usuarios](../../media/user-submissions-filter-options.png)

<span data-ttu-id="27a8c-228">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="27a8c-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="27a8c-229">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="27a8c-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="27a8c-230">Ver los envíos de usuarios al buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="27a8c-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="27a8c-231">Si ha [configurado un buzón personalizado](user-submission.md) para recibir mensajes que el usuario ha notificado, puede ver y enviar también los mensajes que se entregaron al buzón de informes.</span><span class="sxs-lookup"><span data-stu-id="27a8c-231">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="27a8c-232">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **envíos**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="27a8c-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="27a8c-233">Seleccione la ficha **buzón personalizado** .</span><span class="sxs-lookup"><span data-stu-id="27a8c-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="27a8c-234">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="27a8c-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="27a8c-235">**Enviado el**</span><span class="sxs-lookup"><span data-stu-id="27a8c-235">**Submitted on**</span></span>
- <span data-ttu-id="27a8c-236">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-237">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="27a8c-238">**Sender**</span></span>
- <span data-ttu-id="27a8c-239">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="27a8c-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="27a8c-240">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="27a8c-240">**Submission type**</span></span>

<span data-ttu-id="27a8c-241">Cerca de la parte superior de la página, puede especificar una fecha de inicio, una fecha de finalización, y puede filtrar por **enviado** especificando un valor en el cuadro y haciendo clic en el ![ botón actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="27a8c-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="27a8c-242">Update</span><span class="sxs-lookup"><span data-stu-id="27a8c-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="27a8c-243">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="27a8c-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="27a8c-244">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="27a8c-244">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="27a8c-245">Enviar mensajes a Microsoft desde el buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="27a8c-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="27a8c-246">Si ha configurado el buzón personalizado para interceptar los mensajes detectados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="27a8c-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="27a8c-247">Esto mueve eficazmente un envío de usuario a un envío de administración.</span><span class="sxs-lookup"><span data-stu-id="27a8c-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="27a8c-248">En la ficha **buzón personalizado** , seleccione un mensaje de la lista, haga clic en el botón de **acción** y realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="27a8c-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="27a8c-249">**Limpiar informe**</span><span class="sxs-lookup"><span data-stu-id="27a8c-249">**Report clean**</span></span>
- <span data-ttu-id="27a8c-250">**Notificar phishing**</span><span class="sxs-lookup"><span data-stu-id="27a8c-250">**Report phishing**</span></span>
- <span data-ttu-id="27a8c-251">**Notificar malware**</span><span class="sxs-lookup"><span data-stu-id="27a8c-251">**Report malware**</span></span>
- <span data-ttu-id="27a8c-252">**Informar del correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="27a8c-252">**Report spam**</span></span>

![Opciones del botón de acción](../../media/user-submission-custom-mailbox-action-button.png)
