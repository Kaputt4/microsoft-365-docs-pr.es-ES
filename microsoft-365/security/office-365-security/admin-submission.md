---
title: Envíos de administración en Office 365
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
description: Obtenga información sobre cómo enviar correos sospechosos, mensajes de suplantación de identidad (phishing), correo no deseado y otros mensajes potencialmente perjudiciales, direcciones URL y archivos de la empresa a Microsoft para su análisis.
ms.openlocfilehash: 79f200963655e5fb07a04b686c1dd8cc3bbd0873
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034205"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="c87ba-103">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="c87ba-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="c87ba-104">Si es administrador de una organización de Microsoft 365 con buzones en Exchange Online, puede usar el portal de envíos del centro de seguridad & cumplimiento para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="c87ba-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="c87ba-105">Al enviar un correo electrónico, recibirá información sobre las directivas que puedan haber permitido el correo entrante en su inquilino, así como el examen de las direcciones URL y los datos adjuntos del correo.</span><span class="sxs-lookup"><span data-stu-id="c87ba-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="c87ba-106">Las directivas que pueden haber permitido un correo incluyen la lista de remitentes seguros de un usuario individual, así como directivas de nivel de inquilino, como reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="c87ba-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="c87ba-107">Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c87ba-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c87ba-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="c87ba-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c87ba-109">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c87ba-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c87ba-110">Para ir directamente a la página de **envío** , <https://protection.office.com/reportsubmission>use.</span><span class="sxs-lookup"><span data-stu-id="c87ba-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="c87ba-111">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="c87ba-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="c87ba-112">Para agregar, modificar y eliminar directivas contra correo no deseado, debe ser miembro de los grupos de funciones **Administración**de la organización, **Administrador de seguridad**o **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-112">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="c87ba-113">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c87ba-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="c87ba-114">Para obtener más información sobre cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c87ba-114">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="c87ba-115">Informar sobre contenido sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="c87ba-115">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="c87ba-116">En el centro de seguridad & cumplimiento, vaya a **mensajes de envío**de administración de la **revisión** \> de **amenazas** \> .</span><span class="sxs-lookup"><span data-stu-id="c87ba-116">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="c87ba-117">En la página envíos que aparece, haga clic **en el botón** **nuevo envío** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-117">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="c87ba-118">Use el nuevo control flotante de **envío** que aparece para enviar el mensaje, la dirección URL o los datos adjuntos, tal como se describe en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="c87ba-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="c87ba-119">Enviar un correo electrónico cuestionable a Microsoft</span><span class="sxs-lookup"><span data-stu-id="c87ba-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="c87ba-120">En la sección **tipo de objeto** , seleccione **correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="c87ba-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="c87ba-121">En la sección **formato de envío** , use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c87ba-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="c87ba-122">**Identificador de mensaje de red**: es un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-ID** del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c87ba-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="c87ba-123">**Archivo**: haga clic en **elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="c87ba-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="c87ba-124">En el cuadro de diálogo que se abre, busque y seleccione el archivo. eml o. msg y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="c87ba-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="c87ba-125">En la sección **destinatarios** , especifique uno o más destinatarios con los que desee ejecutar una comprobación de directiva.</span><span class="sxs-lookup"><span data-stu-id="c87ba-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="c87ba-126">La comprobación de la Directiva determinará si se ha omitido el análisis del correo electrónico debido a las directivas del usuario o la organización.</span><span class="sxs-lookup"><span data-stu-id="c87ba-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="c87ba-127">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c87ba-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c87ba-128">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="c87ba-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c87ba-129">**Debe haberse bloqueado**: seleccione **correo no deseado**, **phishing**o **malware**.</span><span class="sxs-lookup"><span data-stu-id="c87ba-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="c87ba-130">Si no está seguro, use su mejor criterio.</span><span class="sxs-lookup"><span data-stu-id="c87ba-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="c87ba-131">Si se ha omitido el filtro debido a las directivas tras el envío, verá información sobre esa Directiva.</span><span class="sxs-lookup"><span data-stu-id="c87ba-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="c87ba-132">Si no se ha omitido el filtro debido a una o más directivas, el análisis se completará en varios minutos.</span><span class="sxs-lookup"><span data-stu-id="c87ba-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="c87ba-133">Para ver más información sobre el envío, haga clic en el vínculo estado.</span><span class="sxs-lookup"><span data-stu-id="c87ba-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="c87ba-134">Esto incluye los resultados de la comprobación de la Directiva y el veredicto de reescaneo.</span><span class="sxs-lookup"><span data-stu-id="c87ba-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="c87ba-135">Nota Esto no ejecuta el correo electrónico a través de la pila de filtrado completo de ATP de Office 365, sino que ejecuta un nuevo análisis parcial en función de determinados atributos del correo, la dirección URL o el archivo.</span><span class="sxs-lookup"><span data-stu-id="c87ba-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="c87ba-136">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-136">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de dirección URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="c87ba-138">Enviar una dirección URL sospechosa a Microsoft</span><span class="sxs-lookup"><span data-stu-id="c87ba-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="c87ba-139">En la sección **tipo de objeto** , seleccione **dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="c87ba-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="c87ba-140">En el cuadro que aparece, escriba la dirección URL completa (por ejemplo <https://www.fabrikam.com/marketing.html>,).</span><span class="sxs-lookup"><span data-stu-id="c87ba-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="c87ba-141">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c87ba-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c87ba-142">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="c87ba-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c87ba-143">**Debe haberse bloqueado**: seleccione **suplantación de identidad (phishing)** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="c87ba-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="c87ba-144">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-144">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de correo electrónico](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="c87ba-146">Enviar un archivo sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="c87ba-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="c87ba-147">En la sección **tipo de objeto** , seleccione **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="c87ba-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="c87ba-148">Haga clic en **elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="c87ba-148">Click **Choose File**.</span></span> <span data-ttu-id="c87ba-149">En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="c87ba-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="c87ba-150">En la sección **motivo de envío** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c87ba-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c87ba-151">**No se debe haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="c87ba-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c87ba-152">**Debe haberse bloqueado**: el **malware** es la única opción y se selecciona automáticamente..</span><span class="sxs-lookup"><span data-stu-id="c87ba-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="c87ba-153">Cuando haya terminado, haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-153">When you're finished, click the **Submit** button.</span></span>

![Ejemplo de envío de datos adjuntos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="c87ba-155">Ver envíos de administración</span><span class="sxs-lookup"><span data-stu-id="c87ba-155">View admin submissions</span></span>

1. <span data-ttu-id="c87ba-156">En el centro de seguridad & cumplimiento, vaya a **mensajes de envío**de administración de la **revisión** \> de **amenazas** \> .</span><span class="sxs-lookup"><span data-stu-id="c87ba-156">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="c87ba-157">En la página **envíos** que aparece, compruebe que la pestaña **envíos administrativos** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c87ba-157">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="c87ba-158">Cerca de la parte superior de la página, puede especificar una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por **identificador de envío** introduciendo un valor ![en el](../../media/scc-quarantine-refresh.png)cuadro y haciendo clic en el botón actualizar.</span><span class="sxs-lookup"><span data-stu-id="c87ba-158">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c87ba-159">Update</span><span class="sxs-lookup"><span data-stu-id="c87ba-159">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c87ba-160">Para cambiar los criterios de filtro, haga clic en el botón **identificador de envío** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c87ba-160">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="c87ba-161">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c87ba-161">**Sender**</span></span>
- <span data-ttu-id="c87ba-162">**Asunto/URL/nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="c87ba-162">**Subject/URL/File name**</span></span>
- <span data-ttu-id="c87ba-163">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="c87ba-163">**Submitted by**</span></span>
- <span data-ttu-id="c87ba-164">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="c87ba-164">**Submission type**</span></span>
- <span data-ttu-id="c87ba-165">**Estado**</span><span class="sxs-lookup"><span data-stu-id="c87ba-165">**Status**</span></span>

![Opciones de filtro para envíos de administración](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="c87ba-167">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-167">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c87ba-168">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="c87ba-168">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="c87ba-169">Debajo del gráfico, hay tres pestañas: **correo electrónico** (predeterminado), **dirección URL**y **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="c87ba-169">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="c87ba-170">Ver envíos de correo electrónico de administrador</span><span class="sxs-lookup"><span data-stu-id="c87ba-170">View admin email submissions</span></span>

<span data-ttu-id="c87ba-171">Haga clic en la pestaña **correo electrónico** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-171">Click the **Email** tab.</span></span>

<span data-ttu-id="c87ba-172">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="c87ba-172">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c87ba-173">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c87ba-173">**Date**</span></span>
- <span data-ttu-id="c87ba-174">**IDENTIFICADOR de envío**</span><span class="sxs-lookup"><span data-stu-id="c87ba-174">**Submission ID**</span></span>
- <span data-ttu-id="c87ba-175">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-175">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-176">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-176">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-177">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c87ba-177">**Sender**</span></span>
- <span data-ttu-id="c87ba-178">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-178">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-179">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="c87ba-179">**Submission type**</span></span>
- <span data-ttu-id="c87ba-180">**Motivo de la entrega**</span><span class="sxs-lookup"><span data-stu-id="c87ba-180">**Delivery reason**</span></span>
- <span data-ttu-id="c87ba-181">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-181">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-182">**Tipo de control**</span><span class="sxs-lookup"><span data-stu-id="c87ba-182">**Control type**</span></span>
- <span data-ttu-id="c87ba-183">**Origen del control**</span><span class="sxs-lookup"><span data-stu-id="c87ba-183">**Control source**</span></span>

  <span data-ttu-id="c87ba-184"><sup>\*</sup>Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="c87ba-184"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="c87ba-185">Ver envíos de direcciones URL de administración</span><span class="sxs-lookup"><span data-stu-id="c87ba-185">View admin URL submissions</span></span>

<span data-ttu-id="c87ba-186">Haga clic en la ficha **dirección URL** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-186">Click the **URL** tab.</span></span>

<span data-ttu-id="c87ba-187">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="c87ba-187">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c87ba-188">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c87ba-188">**Date**</span></span>
- <span data-ttu-id="c87ba-189">**IDENTIFICADOR de envío**</span><span class="sxs-lookup"><span data-stu-id="c87ba-189">**Submission ID**</span></span>
- <span data-ttu-id="c87ba-190">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-190">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-191">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-191">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-192">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="c87ba-192">**Submission type**</span></span>
- <span data-ttu-id="c87ba-193">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-193">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="c87ba-194"><sup>\*</sup>Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="c87ba-194"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="c87ba-195">Ver envíos de datos adjuntos de administración</span><span class="sxs-lookup"><span data-stu-id="c87ba-195">View admin attachment submissions</span></span>

<span data-ttu-id="c87ba-196">Haga clic en la pestaña **datos adjuntos** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-196">Click the **Attachments** tab.</span></span>

<span data-ttu-id="c87ba-197">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="c87ba-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c87ba-198">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c87ba-198">**Date**</span></span>
- <span data-ttu-id="c87ba-199">**IDENTIFICADOR de envío**</span><span class="sxs-lookup"><span data-stu-id="c87ba-199">**Submission ID**</span></span>
- <span data-ttu-id="c87ba-200">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-201">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-201">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-202">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="c87ba-202">**Submission type**</span></span>
- <span data-ttu-id="c87ba-203">**Estatus**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="c87ba-204"><sup>\*</sup>Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="c87ba-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="c87ba-205">Ver envíos de usuarios a Microsoft</span><span class="sxs-lookup"><span data-stu-id="c87ba-205">View user submissions to Microsoft</span></span>

<span data-ttu-id="c87ba-206">Si ha implementado el [complemento de mensajes de informe](enable-the-report-message-add-in.md), o los usuarios usan la [creación de informes integrada en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), puede ver qué usuarios están notificando en la pestaña **envíos de usuarios** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-206">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="c87ba-207">En el centro de seguridad & cumplimiento, vaya a **mensajes de envío**de administración de la **revisión** \> de **amenazas** \> .</span><span class="sxs-lookup"><span data-stu-id="c87ba-207">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="c87ba-208">En la página **envíos** que aparece, haga clic en la pestaña **envíos de usuarios** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-208">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="c87ba-209">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="c87ba-209">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c87ba-210">**Enviado el**</span><span class="sxs-lookup"><span data-stu-id="c87ba-210">**Submitted on**</span></span>
- <span data-ttu-id="c87ba-211">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-211">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-212">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-212">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-213">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c87ba-213">**Sender**</span></span>
- <span data-ttu-id="c87ba-214">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-214">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-215">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="c87ba-215">**Submission type**</span></span>

<span data-ttu-id="c87ba-216"><sup>\*</sup>Si hace clic en este valor, se muestra información detallada en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="c87ba-216"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="c87ba-217">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por **remitente** introduciendo un valor en el ![cuadro y](../../media/scc-quarantine-refresh.png)haciendo clic en el botón actualizar.</span><span class="sxs-lookup"><span data-stu-id="c87ba-217">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c87ba-218">Update</span><span class="sxs-lookup"><span data-stu-id="c87ba-218">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c87ba-219">Para cambiar los criterios de filtro, haga clic en el botón **remitente** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c87ba-219">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="c87ba-220">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="c87ba-220">**Sender domain**</span></span>
- <span data-ttu-id="c87ba-221">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="c87ba-221">**Subject**</span></span>
- <span data-ttu-id="c87ba-222">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="c87ba-222">**Submitted by**</span></span>
- <span data-ttu-id="c87ba-223">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="c87ba-223">**Submission type**</span></span>
- <span data-ttu-id="c87ba-224">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="c87ba-224">**Sender IP**</span></span>

![Opciones de filtro para envíos de usuarios](../../media/user-submissions-filter-options.png)

<span data-ttu-id="c87ba-226">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-226">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c87ba-227">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="c87ba-227">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="c87ba-228">Ver los envíos de usuarios al buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="c87ba-228">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="c87ba-229">Si ha [configurado un buzón personalizado](user-submission.md) para recibir mensajes que el usuario ha notificado, puede ver y enviar también los mensajes que se entregaron al buzón de informes.</span><span class="sxs-lookup"><span data-stu-id="c87ba-229">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="c87ba-230">En el centro de seguridad & cumplimiento, vaya a **mensajes de envío**de administración de la **revisión** \> de **amenazas** \> .</span><span class="sxs-lookup"><span data-stu-id="c87ba-230">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="c87ba-231">En la página **envíos** que aparece, haga clic en la ficha **buzón personalizado** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-231">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="c87ba-232">Puede hacer clic en el botón **Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="c87ba-232">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c87ba-233">**Enviado el**</span><span class="sxs-lookup"><span data-stu-id="c87ba-233">**Submitted on**</span></span>
- <span data-ttu-id="c87ba-234">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-234">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-235">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-235">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-236">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c87ba-236">**Sender**</span></span>
- <span data-ttu-id="c87ba-237">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c87ba-237">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c87ba-238">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="c87ba-238">**Submission type**</span></span>

<span data-ttu-id="c87ba-239">Cerca de la parte superior de la página, puede especificar una fecha de inicio, una fecha de finalización, y puede filtrar por **enviado** especificando un valor en el ![cuadro y](../../media/scc-quarantine-refresh.png)haciendo clic en el botón actualizar.</span><span class="sxs-lookup"><span data-stu-id="c87ba-239">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c87ba-240">Update</span><span class="sxs-lookup"><span data-stu-id="c87ba-240">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c87ba-241">Para exportar los resultados, haga clic en **exportar** cerca de la parte superior de la página y seleccione datos o **tabla**de **gráficos** .</span><span class="sxs-lookup"><span data-stu-id="c87ba-241">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c87ba-242">En el cuadro de diálogo que aparece, guarde el archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="c87ba-242">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="c87ba-243">Enviar mensajes a Microsoft desde el buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="c87ba-243">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="c87ba-244">Si ha configurado el buzón personalizado para interceptar los mensajes detectados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="c87ba-244">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="c87ba-245">Esto mueve eficazmente un envío de usuario a un envío de administración.</span><span class="sxs-lookup"><span data-stu-id="c87ba-245">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="c87ba-246">En la ficha **buzón personalizado** , seleccione un mensaje de la lista, haga clic en el botón de **acción** y realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="c87ba-246">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="c87ba-247">**Limpiar informe**</span><span class="sxs-lookup"><span data-stu-id="c87ba-247">**Report clean**</span></span>
- <span data-ttu-id="c87ba-248">**Notificar phishing**</span><span class="sxs-lookup"><span data-stu-id="c87ba-248">**Report phishing**</span></span>
- <span data-ttu-id="c87ba-249">**Notificar malware**</span><span class="sxs-lookup"><span data-stu-id="c87ba-249">**Report malware**</span></span>
- <span data-ttu-id="c87ba-250">**Informar del correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="c87ba-250">**Report spam**</span></span>

![Opciones del botón de acción](../../media/user-submission-custom-mailbox-action-button.png)
