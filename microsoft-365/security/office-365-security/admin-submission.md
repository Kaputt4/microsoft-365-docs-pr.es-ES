---
title: Envíos de administración
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el portal de envíos en el centro de seguridad & cumplimiento para enviar correos sospechosos, mensajes de suplantación de identidad (phishing), correo no deseado y otros mensajes potencialmente dañinos, direcciones URL y archivos a Microsoft para su análisis.
ms.openlocfilehash: 4d0737d881334db9cc4aeda43037ab89d7444618
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577875"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="55fce-103">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="55fce-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="55fce-104">En Microsoft 365 organizaciones con buzones de correo en Exchange Online, los administradores pueden usar el portal de envíos del centro de seguridad & cumplimiento para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="55fce-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="55fce-105">Al enviar un correo electrónico, recibirá información sobre las directivas que puedan haber permitido el correo entrante en su inquilino, así como el examen de las direcciones URL y los datos adjuntos del correo.</span><span class="sxs-lookup"><span data-stu-id="55fce-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="55fce-106">Las directivas que pueden haber permitido un correo incluyen la lista de remitentes seguros de un usuario individual, así como directivas de nivel de inquilino, como reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="55fce-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="55fce-107">Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="55fce-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="55fce-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="55fce-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="55fce-109">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="55fce-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="55fce-110">Para ir directamente a la página de **envío** , use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="55fce-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="55fce-111">Para poder realizar los procedimientos de este tema, deberá tener asignados los permisos necesarios:</span><span class="sxs-lookup"><span data-stu-id="55fce-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="55fce-112">Para enviar mensajes y archivos a Microsoft, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="55fce-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="55fce-113">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="55fce-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="55fce-114">**Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="55fce-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="55fce-115">Para obtener acceso de solo lectura al portal de envíos, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="55fce-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="55fce-116">**Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="55fce-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="55fce-117">**Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="55fce-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="55fce-118">Para obtener más información sobre cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="55fce-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="55fce-119">Informar sobre contenido sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="55fce-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="55fce-120">En el centro de seguridad & cumplimiento, vaya a mensajes de envío de administración de la revisión de **amenazas** \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="55fce-120">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="55fce-121">En la página envíos que aparece, haga clic **en el botón** **nuevo envío** .</span><span class="sxs-lookup"><span data-stu-id="55fce-121">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="55fce-122">Use el nuevo control flotante de **envío** que aparece para enviar el mensaje, la dirección URL o los datos adjuntos, tal como se describe en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="55fce-122">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="55fce-123">Enviar un correo electrónico cuestionable a Microsoft</span><span class="sxs-lookup"><span data-stu-id="55fce-123">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="55fce-124">En la sección **tipo de objeto** , seleccione **correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="55fce-124">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="55fce-125">En la sección **formato de envío** , use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="55fce-125">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="55fce-126">**Identificador de mensaje de red**: es un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-ID** del mensaje.</span><span class="sxs-lookup"><span data-stu-id="55fce-126">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="55fce-127">**Archivo**: haga clic en **elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="55fce-127">**File**: Click **Choose file**.</span></span> <span data-ttu-id="55fce-128">En el cuadro de diálogo que se abre, busque y seleccione el archivo. eml o. msg y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="55fce-128">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="55fce-129">En la sección **destinatarios** , especifique uno o más destinatarios con los que desee ejecutar una comprobación de directiva.</span><span class="sxs-lookup"><span data-stu-id="55fce-129">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="55fce-130">La comprobación de la Directiva determinará si se ha omitido el análisis del correo electrónico debido a las directivas del usuario o la organización.</span><span class="sxs-lookup"><span data-stu-id="55fce-130">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="55fce-131">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="55fce-131">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="55fce-132">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="55fce-132">**Should not have been blocked**</span></span>

   - <span data-ttu-id="55fce-133">**Debe haberse bloqueado**: seleccione **correo no deseado**, **phishing**o **malware**.</span><span class="sxs-lookup"><span data-stu-id="55fce-133">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="55fce-134">Si no está seguro, use su mejor criterio.</span><span class="sxs-lookup"><span data-stu-id="55fce-134">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="55fce-135">Si se ha omitido el filtro debido a las directivas tras el envío, verá información sobre esa Directiva.</span><span class="sxs-lookup"><span data-stu-id="55fce-135">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="55fce-136">Si no se ha omitido el filtro debido a una o más directivas, el análisis se completará en varios minutos.</span><span class="sxs-lookup"><span data-stu-id="55fce-136">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="55fce-137">Para ver más información sobre el envío, haga clic en el vínculo estado.</span><span class="sxs-lookup"><span data-stu-id="55fce-137">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="55fce-138">Esto incluye los resultados de la comprobación de la Directiva y el veredicto de reescaneo.</span><span class="sxs-lookup"><span data-stu-id="55fce-138">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="55fce-139">Nota Esto no ejecuta el correo electrónico a través de la pila de filtrado completo de ATP de Office 365, sino que ejecuta un nuevo análisis parcial en función de determinados atributos del correo, la dirección URL o el archivo.</span><span class="sxs-lookup"><span data-stu-id="55fce-139">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="55fce-140">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="55fce-140">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de dirección URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="55fce-142">Enviar una dirección URL sospechosa a Microsoft</span><span class="sxs-lookup"><span data-stu-id="55fce-142">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="55fce-143">En la sección **tipo de objeto** , seleccione **dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="55fce-143">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="55fce-144">En el cuadro que aparece, escriba la dirección URL completa (por ejemplo, <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="55fce-144">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="55fce-145">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="55fce-145">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="55fce-146">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="55fce-146">**Should not have been blocked**</span></span>

   - <span data-ttu-id="55fce-147">**Debe haberse bloqueado**: seleccione **suplantación de identidad (phishing)** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="55fce-147">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="55fce-148">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="55fce-148">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de correo electrónico](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="55fce-150">Enviar un archivo sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="55fce-150">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="55fce-151">En la sección **tipo de objeto** , seleccione **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="55fce-151">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="55fce-152">Haga clic en **elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="55fce-152">Click **Choose File**.</span></span> <span data-ttu-id="55fce-153">En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="55fce-153">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="55fce-154">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="55fce-154">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="55fce-155">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="55fce-155">**Should not have been blocked**</span></span>

   - <span data-ttu-id="55fce-156">**Debe haberse bloqueado**: el **malware** es la única opción y se selecciona automáticamente..</span><span class="sxs-lookup"><span data-stu-id="55fce-156">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="55fce-157">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="55fce-157">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de datos adjuntos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="55fce-159">Ver envíos de administración</span><span class="sxs-lookup"><span data-stu-id="55fce-159">View admin submissions</span></span>

1. <span data-ttu-id="55fce-160">En el centro de seguridad & cumplimiento, vaya a mensajes de envío de administración de la revisión de **amenazas** \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="55fce-160">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="55fce-161">En la página **envíos** que aparece, compruebe que la pestaña **envíos administrativos** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="55fce-161">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="55fce-162">Cerca de la parte superior de la página, puede especificar una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por **identificador de envío** (un valor de GUID asignado a cada envío) introduciendo un valor en el cuadro y haciendo clic en el ![ botón actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="55fce-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="55fce-163">Update</span><span class="sxs-lookup"><span data-stu-id="55fce-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="55fce-164">Para cambiar los criterios de filtro, haga clic en el botón **identificador de envío** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="55fce-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="55fce-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="55fce-165">**Sender**</span></span>
- <span data-ttu-id="55fce-166">**Asunto/URL/nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="55fce-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="55fce-167">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="55fce-167">**Submitted by**</span></span>
- <span data-ttu-id="55fce-168">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="55fce-168">**Submission type**</span></span>
- <span data-ttu-id="55fce-169">**Estado**</span><span class="sxs-lookup"><span data-stu-id="55fce-169">**Status**</span></span>

![Opciones de filtro para envíos de administración](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="55fce-171">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="55fce-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="55fce-172">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="55fce-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="55fce-173">Debajo del gráfico, hay tres pestañas: **correo electrónico** (predeterminado), **dirección URL**y **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="55fce-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="55fce-174">Ver envíos de correo electrónico de administrador</span><span class="sxs-lookup"><span data-stu-id="55fce-174">View admin email submissions</span></span>

<span data-ttu-id="55fce-175">Haga clic en la pestaña **correo electrónico** .</span><span class="sxs-lookup"><span data-stu-id="55fce-175">Click the **Email** tab.</span></span>

<span data-ttu-id="55fce-176">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="55fce-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="55fce-177">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="55fce-177">**Date**</span></span>
- <span data-ttu-id="55fce-178">**Identificador de envío**: un valor de GUID que se asigna a cada envío.</span><span class="sxs-lookup"><span data-stu-id="55fce-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="55fce-179">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-180">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="55fce-181">**Sender**</span></span>
- <span data-ttu-id="55fce-182">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-183">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="55fce-183">**Submission type**</span></span>
- <span data-ttu-id="55fce-184">**Motivo de la entrega**</span><span class="sxs-lookup"><span data-stu-id="55fce-184">**Delivery reason**</span></span>
- <span data-ttu-id="55fce-185">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-185">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-186">**Tipo de control**</span><span class="sxs-lookup"><span data-stu-id="55fce-186">**Control type**</span></span>
- <span data-ttu-id="55fce-187">**Origen del control**</span><span class="sxs-lookup"><span data-stu-id="55fce-187">**Control source**</span></span>

  <span data-ttu-id="55fce-188"><sup>\*</sup>Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="55fce-188"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="55fce-189">Ver envíos de direcciones URL de administración</span><span class="sxs-lookup"><span data-stu-id="55fce-189">View admin URL submissions</span></span>

<span data-ttu-id="55fce-190">Haga clic en la ficha **dirección URL** .</span><span class="sxs-lookup"><span data-stu-id="55fce-190">Click the **URL** tab.</span></span>

<span data-ttu-id="55fce-191">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="55fce-191">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="55fce-192">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="55fce-192">**Date**</span></span>
- <span data-ttu-id="55fce-193">**IDENTIFICADOR de envío**</span><span class="sxs-lookup"><span data-stu-id="55fce-193">**Submission ID**</span></span>
- <span data-ttu-id="55fce-194">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-194">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-195">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-195">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-196">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="55fce-196">**Submission type**</span></span>
- <span data-ttu-id="55fce-197">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-197">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="55fce-198"><sup>\*</sup>Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="55fce-198"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="55fce-199">Ver envíos de datos adjuntos de administración</span><span class="sxs-lookup"><span data-stu-id="55fce-199">View admin attachment submissions</span></span>

<span data-ttu-id="55fce-200">Haga clic en la pestaña **datos adjuntos** .</span><span class="sxs-lookup"><span data-stu-id="55fce-200">Click the **Attachments** tab.</span></span>

<span data-ttu-id="55fce-201">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="55fce-201">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="55fce-202">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="55fce-202">**Date**</span></span>
- <span data-ttu-id="55fce-203">**IDENTIFICADOR de envío**</span><span class="sxs-lookup"><span data-stu-id="55fce-203">**Submission ID**</span></span>
- <span data-ttu-id="55fce-204">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-204">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-205">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-205">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-206">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="55fce-206">**Submission type**</span></span>
- <span data-ttu-id="55fce-207">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-207">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="55fce-208"><sup>\*</sup>Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="55fce-208"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="55fce-209">Ver envíos de usuarios a Microsoft</span><span class="sxs-lookup"><span data-stu-id="55fce-209">View user submissions to Microsoft</span></span>

<span data-ttu-id="55fce-210">Si ha implementado el [complemento de mensajes de informe](enable-the-report-message-add-in.md), o los usuarios usan la [creación de informes integrada en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), puede ver qué usuarios están notificando en la pestaña **envíos de usuarios** .</span><span class="sxs-lookup"><span data-stu-id="55fce-210">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="55fce-211">En el centro de seguridad & cumplimiento, vaya a mensajes de envío de administración de la revisión de **amenazas** \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="55fce-211">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="55fce-212">En la página **envíos** que aparece, haga clic en la pestaña **envíos de usuarios** .</span><span class="sxs-lookup"><span data-stu-id="55fce-212">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="55fce-213">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="55fce-213">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="55fce-214">**Enviado el**</span><span class="sxs-lookup"><span data-stu-id="55fce-214">**Submitted on**</span></span>
- <span data-ttu-id="55fce-215">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-215">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-216">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-216">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-217">**Sender**</span><span class="sxs-lookup"><span data-stu-id="55fce-217">**Sender**</span></span>
- <span data-ttu-id="55fce-218">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-218">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-219">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="55fce-219">**Submission type**</span></span>

<span data-ttu-id="55fce-220"><sup>\*</sup>Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="55fce-220"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="55fce-221">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por **remitente** introduciendo un valor en el cuadro y haciendo clic en el ![ botón actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="55fce-221">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="55fce-222">Update</span><span class="sxs-lookup"><span data-stu-id="55fce-222">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="55fce-223">Para cambiar los criterios de filtro, haga clic en el botón **remitente** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="55fce-223">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="55fce-224">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="55fce-224">**Sender domain**</span></span>
- <span data-ttu-id="55fce-225">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="55fce-225">**Subject**</span></span>
- <span data-ttu-id="55fce-226">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="55fce-226">**Submitted by**</span></span>
- <span data-ttu-id="55fce-227">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="55fce-227">**Submission type**</span></span>
- <span data-ttu-id="55fce-228">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="55fce-228">**Sender IP**</span></span>

![Opciones de filtro para envíos de usuarios](../../media/user-submissions-filter-options.png)

<span data-ttu-id="55fce-230">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="55fce-230">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="55fce-231">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="55fce-231">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="55fce-232">Ver los envíos de usuarios al buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="55fce-232">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="55fce-233">Si ha [configurado un buzón personalizado](user-submission.md) para recibir mensajes que el usuario ha notificado, puede ver y enviar también los mensajes que se entregaron al buzón de informes.</span><span class="sxs-lookup"><span data-stu-id="55fce-233">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="55fce-234">En el centro de seguridad & cumplimiento, vaya a mensajes de envío de administración de la revisión de **amenazas** \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="55fce-234">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="55fce-235">En la página **envíos** que aparece, haga clic en la ficha **buzón personalizado** .</span><span class="sxs-lookup"><span data-stu-id="55fce-235">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="55fce-236">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="55fce-236">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="55fce-237">**Enviado el**</span><span class="sxs-lookup"><span data-stu-id="55fce-237">**Submitted on**</span></span>
- <span data-ttu-id="55fce-238">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-238">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-239">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-239">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-240">**Sender**</span><span class="sxs-lookup"><span data-stu-id="55fce-240">**Sender**</span></span>
- <span data-ttu-id="55fce-241">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="55fce-241">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="55fce-242">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="55fce-242">**Submission type**</span></span>

<span data-ttu-id="55fce-243">Cerca de la parte superior de la página, puede especificar una fecha de inicio, una fecha de finalización, y puede filtrar por **enviado** especificando un valor en el cuadro y haciendo clic en el ![ botón actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="55fce-243">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="55fce-244">Update</span><span class="sxs-lookup"><span data-stu-id="55fce-244">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="55fce-245">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="55fce-245">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="55fce-246">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="55fce-246">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="55fce-247">Enviar mensajes a Microsoft desde el buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="55fce-247">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="55fce-248">Si ha configurado el buzón personalizado para interceptar los mensajes detectados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="55fce-248">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="55fce-249">Esto mueve eficazmente un envío de usuario a un envío de administración.</span><span class="sxs-lookup"><span data-stu-id="55fce-249">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="55fce-250">En la ficha **buzón personalizado** , seleccione un mensaje de la lista, haga clic en el botón de **acción** y realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="55fce-250">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="55fce-251">**Limpiar informe**</span><span class="sxs-lookup"><span data-stu-id="55fce-251">**Report clean**</span></span>
- <span data-ttu-id="55fce-252">**Notificar phishing**</span><span class="sxs-lookup"><span data-stu-id="55fce-252">**Report phishing**</span></span>
- <span data-ttu-id="55fce-253">**Notificar malware**</span><span class="sxs-lookup"><span data-stu-id="55fce-253">**Report malware**</span></span>
- <span data-ttu-id="55fce-254">**Informar del correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="55fce-254">**Report spam**</span></span>

![Opciones del botón de acción](../../media/user-submission-custom-mailbox-action-button.png)
