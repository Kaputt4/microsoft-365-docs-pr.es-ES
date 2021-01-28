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
description: Los administradores pueden aprender a usar el portal de envíos del Centro de seguridad y cumplimiento de & para enviar correos electrónicos sospechosos, correos sospechosos de suplantación de identidad, correo no deseado y otros mensajes potencialmente peligrosos, direcciones URL y archivos a Microsoft para su análisis.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed417db93bc2f3efa6b85b0ef97c10b5941cd8eb
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029519"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="402c3-103">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="402c3-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="402c3-104">En organizaciones de Microsoft 365 con buzones en Exchange Online, los administradores pueden usar el portal de envíos del Centro de seguridad & y cumplimiento para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="402c3-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="402c3-105">Cuando envíe un mensaje de correo electrónico, recibirá:</span><span class="sxs-lookup"><span data-stu-id="402c3-105">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="402c3-106">**Comprobación de autenticación de** correo electrónico: detalles sobre si la autenticación de correo electrónico se ha superado o no cuando se entregó.</span><span class="sxs-lookup"><span data-stu-id="402c3-106">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="402c3-107">**Aciertos de** directiva: información sobre las directivas que pueden haber permitido o bloqueado el correo electrónico entrante en su espacio empresarial, invalidando nuestros veredictos de filtro de servicio.</span><span class="sxs-lookup"><span data-stu-id="402c3-107">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="402c3-108">**Reputación/detonación de carga:** examen de las direcciones URL y los datos adjuntos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="402c3-108">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="402c3-109">**Análisis de calificador:** revisión realizada por los calificadores para confirmar si los mensajes son malintencionados o no.</span><span class="sxs-lookup"><span data-stu-id="402c3-109">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="402c3-110">La reputación/detonación de carga útil y el análisis de calificador no se realizan en todos los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="402c3-110">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="402c3-111">Se bloquea la información para que no salga de la organización cuando se supone que los datos no deben salir del límite del espacio empresarial por motivos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="402c3-111">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="402c3-112">Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea Notificar mensajes y [archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="402c3-112">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="402c3-113">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="402c3-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="402c3-114">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="402c3-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="402c3-115">Para ir directamente a la **página Envío,** use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="402c3-115">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="402c3-116">Para enviar mensajes y archivos a Microsoft, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="402c3-116">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="402c3-117">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="402c3-117">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="402c3-118">**Administración de la** organización [en Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="402c3-118">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="402c3-119">Tenga en cuenta que es necesario pertenecer a este grupo de roles para ver los [envíos](#view-user-submissions-to-the-custom-mailbox) de usuarios al buzón personalizado, tal como se describe más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="402c3-119">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="402c3-120">Para obtener más información acerca de cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea Notificar mensajes y [archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="402c3-120">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="402c3-121">Notificar contenido sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="402c3-121">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="402c3-122">En el Centro de & cumplimiento,  vaya a Envíos de administración de amenazas, compruebe que está en la pestaña Envíos de administración y, a continuación, haga clic en \>  **Nuevo envío.** </span><span class="sxs-lookup"><span data-stu-id="402c3-122">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="402c3-123">Use **el menú desplegable Nuevo** envío que parece enviar el mensaje, la dirección URL o los datos adjuntos, tal como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="402c3-123">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="402c3-124">Enviar un correo electrónico cuestionable a Microsoft</span><span class="sxs-lookup"><span data-stu-id="402c3-124">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="402c3-125">En la **sección Tipo de** objeto, seleccione Correo **electrónico.**</span><span class="sxs-lookup"><span data-stu-id="402c3-125">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="402c3-126">En la **sección Formato de** envío, usa una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="402c3-126">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="402c3-127">**Id.** de mensaje de red: es un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-Id** del mensaje, o en el encabezado **X-MS-Office365-Filtering-Correlation-Id** en mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="402c3-127">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="402c3-128">**Archivo:** haga clic **en Elegir archivo.**</span><span class="sxs-lookup"><span data-stu-id="402c3-128">**File**: Click **Choose file**.</span></span> <span data-ttu-id="402c3-129">En el cuadro de diálogo que se abre, busque y seleccione el archivo .eml o .msg y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="402c3-129">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="402c3-130">Los administradores con Defender para Office 365 Plan 1 o Plan 2 pueden enviar mensajes tan antiguos como 30 días.</span><span class="sxs-lookup"><span data-stu-id="402c3-130">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="402c3-131">Otros administradores solo podrán volver 7 días atrás.</span><span class="sxs-lookup"><span data-stu-id="402c3-131">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="402c3-132">En la **sección** Destinatarios, especifique uno o más destinatarios con los que desea ejecutar una comprobación de directiva.</span><span class="sxs-lookup"><span data-stu-id="402c3-132">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="402c3-133">La comprobación de directivas determinará si el correo electrónico omitió el examen debido a directivas de usuario u organización.</span><span class="sxs-lookup"><span data-stu-id="402c3-133">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="402c3-134">En la **sección Motivo del** envío, selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="402c3-134">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="402c3-135">**No debería haber sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="402c3-135">**Should not have been blocked**</span></span>

   - <span data-ttu-id="402c3-136">**Debería haber sido bloqueado:** Seleccionar **correo no** deseado, **suplantación** de identidad o **malware.**</span><span class="sxs-lookup"><span data-stu-id="402c3-136">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="402c3-137">Si no está seguro, use su mejor criterio.</span><span class="sxs-lookup"><span data-stu-id="402c3-137">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="402c3-138">Cuando haya terminado, haga clic en **el botón** Enviar.</span><span class="sxs-lookup"><span data-stu-id="402c3-138">When you're finished, click the **Submit** button.</span></span>

   ![Ejemplo de envío de dirección URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="402c3-140">Enviar una dirección URL sospechosa a Microsoft</span><span class="sxs-lookup"><span data-stu-id="402c3-140">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="402c3-141">En la **sección Tipo de** objeto, seleccione Dirección **URL**.</span><span class="sxs-lookup"><span data-stu-id="402c3-141">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="402c3-142">En el cuadro que aparece, escriba la dirección URL completa (por ejemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="402c3-142">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="402c3-143">En la **sección Motivo del envío,** selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="402c3-143">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="402c3-144">**No debería haber sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="402c3-144">**Should not have been blocked**</span></span>

   - <span data-ttu-id="402c3-145">**Debería haber sido bloqueado:** Seleccione **Suplantación de identidad** o **malware.**</span><span class="sxs-lookup"><span data-stu-id="402c3-145">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="402c3-146">Cuando haya terminado, haga clic en **el botón** Enviar.</span><span class="sxs-lookup"><span data-stu-id="402c3-146">When you're finished, click the **Submit** button.</span></span>

   ![Ejemplo de envío de correo electrónico](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="402c3-148">Enviar un archivo sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="402c3-148">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="402c3-149">En la **sección Tipo de** objeto, seleccione Datos **adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="402c3-149">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="402c3-150">Haga clic **en Elegir archivo.**</span><span class="sxs-lookup"><span data-stu-id="402c3-150">Click **Choose File**.</span></span> <span data-ttu-id="402c3-151">En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="402c3-151">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="402c3-152">En la **sección Motivo del** envío, selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="402c3-152">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="402c3-153">**No debería haber sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="402c3-153">**Should not have been blocked**</span></span>

   - <span data-ttu-id="402c3-154">**Debería haber sido bloqueado:** **el malware** es la única opción y se selecciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="402c3-154">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="402c3-155">Cuando haya terminado, haga clic en **el botón** Enviar.</span><span class="sxs-lookup"><span data-stu-id="402c3-155">When you're finished, click the **Submit** button.</span></span>

   ![Ejemplo de envío de datos adjuntos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="402c3-157">Ver envíos de administrador</span><span class="sxs-lookup"><span data-stu-id="402c3-157">View admin submissions</span></span>

<span data-ttu-id="402c3-158">En el Centro de & cumplimiento,  vaya a Envíos de administración de amenazas, compruebe que está en la pestaña Envíos de administración y, a continuación, haga clic en \>  **Nuevo envío.** </span><span class="sxs-lookup"><span data-stu-id="402c3-158">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="402c3-159">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por identificador de envío **(un** valor GUID asignado a cada envío) especificando un valor en el cuadro y haciendo clic en el botón Actualizar ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="402c3-159">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="402c3-160">Update</span><span class="sxs-lookup"><span data-stu-id="402c3-160">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="402c3-161">Para cambiar los criterios de filtro, haz clic en el botón **Id. de** envío y elige uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="402c3-161">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="402c3-162">**Sender**</span><span class="sxs-lookup"><span data-stu-id="402c3-162">**Sender**</span></span>
- <span data-ttu-id="402c3-163">**Asunto/DIRECCIÓN URL/Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="402c3-163">**Subject/URL/File name**</span></span>
- <span data-ttu-id="402c3-164">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="402c3-164">**Submitted by**</span></span>
- <span data-ttu-id="402c3-165">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="402c3-165">**Submission type**</span></span>
- <span data-ttu-id="402c3-166">**Estado**</span><span class="sxs-lookup"><span data-stu-id="402c3-166">**Status**</span></span>

![Opciones de filtro para envíos de administrador](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="402c3-168">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="402c3-168">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="402c3-169">En el cuadro de diálogo que aparece, guarde el archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="402c3-169">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="402c3-170">Debajo del gráfico, hay tres pestañas: **Correo** electrónico (predeterminado), **Dirección URL** y **Datos adjuntos.**</span><span class="sxs-lookup"><span data-stu-id="402c3-170">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="402c3-171">Ver envíos de correo electrónico de administrador</span><span class="sxs-lookup"><span data-stu-id="402c3-171">View admin email submissions</span></span>

<span data-ttu-id="402c3-172">Haga clic en **la pestaña** Correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="402c3-172">Click the **Email** tab.</span></span>

<span data-ttu-id="402c3-173">Puede hacer clic en el **botón Opciones de columna** situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="402c3-173">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="402c3-174">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="402c3-174">**Date**</span></span>
- <span data-ttu-id="402c3-175">**Identificador de** envío: un valor GUID que se asigna a cada envío.</span><span class="sxs-lookup"><span data-stu-id="402c3-175">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="402c3-176">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-176">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-177">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-177">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-178">**Sender**</span><span class="sxs-lookup"><span data-stu-id="402c3-178">**Sender**</span></span>
- <span data-ttu-id="402c3-179">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-179">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-180">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="402c3-180">**Submission type**</span></span>
- <span data-ttu-id="402c3-181">**Motivo de la entrega**</span><span class="sxs-lookup"><span data-stu-id="402c3-181">**Delivery reason**</span></span>
- <span data-ttu-id="402c3-182">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-182">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="402c3-183"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="402c3-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="402c3-184">Detalles del nuevo análisis del envío de administrador</span><span class="sxs-lookup"><span data-stu-id="402c3-184">Admin submission rescan details</span></span>

<span data-ttu-id="402c3-185">Los mensajes que se envían en envíos de administrador se examinan de nuevo y los resultados se muestran en el menú desplegable de detalles:</span><span class="sxs-lookup"><span data-stu-id="402c3-185">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="402c3-186">Si se ha produce un error en la autenticación de correo electrónico del remitente en el momento de la entrega.</span><span class="sxs-lookup"><span data-stu-id="402c3-186">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="402c3-187">Información sobre los aciertos de directiva que podrían haber afectado o invalidado el veredicto de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="402c3-187">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="402c3-188">Resultados de detonación actuales para ver si las direcciones URL o los archivos contenidos en el mensaje eran malintencionados o no.</span><span class="sxs-lookup"><span data-stu-id="402c3-188">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="402c3-189">Comentarios de los alumnos.</span><span class="sxs-lookup"><span data-stu-id="402c3-189">Feedback from graders.</span></span>

<span data-ttu-id="402c3-190">Si se encontró una invalidación, el nuevo análisis debe completarse en varios minutos.</span><span class="sxs-lookup"><span data-stu-id="402c3-190">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="402c3-191">Si no hubo un problema en la autenticación o entrega de correo electrónico no se vio afectado por una invalidación, los comentarios de los calificadores podrían tardar hasta un día.</span><span class="sxs-lookup"><span data-stu-id="402c3-191">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="402c3-192">Ver envíos de url de administrador</span><span class="sxs-lookup"><span data-stu-id="402c3-192">View admin URL submissions</span></span>

<span data-ttu-id="402c3-193">Haga clic en la **pestaña Dirección** URL.</span><span class="sxs-lookup"><span data-stu-id="402c3-193">Click the **URL** tab.</span></span>

<span data-ttu-id="402c3-194">Puede hacer clic en el **botón Opciones de columna** situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="402c3-194">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="402c3-195">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="402c3-195">**Date**</span></span>
- <span data-ttu-id="402c3-196">**Id. de envío**</span><span class="sxs-lookup"><span data-stu-id="402c3-196">**Submission ID**</span></span>
- <span data-ttu-id="402c3-197">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-197">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-198">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-198">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-199">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="402c3-199">**Submission type**</span></span>
- <span data-ttu-id="402c3-200">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-200">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="402c3-201"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="402c3-201"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="402c3-202">Ver envíos de datos adjuntos de administrador</span><span class="sxs-lookup"><span data-stu-id="402c3-202">View admin attachment submissions</span></span>

<span data-ttu-id="402c3-203">Haga clic en **la pestaña Datos** adjuntos.</span><span class="sxs-lookup"><span data-stu-id="402c3-203">Click the **Attachments** tab.</span></span>

<span data-ttu-id="402c3-204">Puede hacer clic en el **botón Opciones de** columna situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="402c3-204">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="402c3-205">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="402c3-205">**Date**</span></span>
- <span data-ttu-id="402c3-206">**Id. de envío**</span><span class="sxs-lookup"><span data-stu-id="402c3-206">**Submission ID**</span></span>
- <span data-ttu-id="402c3-207">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-207">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-208">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-208">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-209">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="402c3-209">**Submission type**</span></span>
- <span data-ttu-id="402c3-210">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-210">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="402c3-211"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="402c3-211"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="402c3-212">Ver envíos de usuarios a Microsoft</span><span class="sxs-lookup"><span data-stu-id="402c3-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="402c3-213">Si ha implementado el complemento Mensaje de [](enable-the-report-phish-add-in.md) [informe,](enable-the-report-message-add-in.md)el complemento de suplantación de identidad de informes o los usuarios usan los informes integrados en Outlook en [la Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)puede ver qué usuarios están informando en la pestaña **Envíos** de usuarios.</span><span class="sxs-lookup"><span data-stu-id="402c3-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="402c3-214">En el Centro de & cumplimiento, vaya a **Envíos de administración** \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="402c3-214">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="402c3-215">Selecciona la **pestaña Envíos de** usuario y, a continuación, haz clic **en Nuevo envío.**</span><span class="sxs-lookup"><span data-stu-id="402c3-215">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="402c3-216">Puede hacer clic en el **botón Opciones de columna** situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="402c3-216">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="402c3-217">**Enviado en**</span><span class="sxs-lookup"><span data-stu-id="402c3-217">**Submitted on**</span></span>
- <span data-ttu-id="402c3-218">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-218">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-219">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-219">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-220">**Sender**</span><span class="sxs-lookup"><span data-stu-id="402c3-220">**Sender**</span></span>
- <span data-ttu-id="402c3-221">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-221">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-222">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="402c3-222">**Submission type**</span></span>

<span data-ttu-id="402c3-223"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="402c3-223"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="402c3-224">Cerca de la parte superior de la página, puede escribir una fecha de  inicio, una fecha de finalización y , de forma predeterminada, puede filtrar por remitente especificando un valor en el cuadro y haciendo clic en el botón ![ Actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="402c3-224">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="402c3-225">Update</span><span class="sxs-lookup"><span data-stu-id="402c3-225">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="402c3-226">Para cambiar los criterios de filtro, haga clic en el **botón Remitente** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="402c3-226">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="402c3-227">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="402c3-227">**Sender domain**</span></span>
- <span data-ttu-id="402c3-228">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="402c3-228">**Subject**</span></span>
- <span data-ttu-id="402c3-229">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="402c3-229">**Submitted by**</span></span>
- <span data-ttu-id="402c3-230">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="402c3-230">**Submission type**</span></span>
- <span data-ttu-id="402c3-231">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="402c3-231">**Sender IP**</span></span>

![Opciones de filtro para envíos de usuarios](../../media/user-submissions-filter-options.png)

<span data-ttu-id="402c3-233">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="402c3-233">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="402c3-234">En el cuadro de diálogo que aparece, guarde el archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="402c3-234">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="402c3-235">Ver envíos de usuario al buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="402c3-235">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="402c3-236">**Si** ha configurado un [buzón personalizado](user-submission.md) para recibir mensajes notificados por el usuario, puede ver y enviar también los mensajes que se entregaron al buzón de informes.</span><span class="sxs-lookup"><span data-stu-id="402c3-236">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="402c3-237">En el Centro de & cumplimiento, vaya a **Envíos de administración** \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="402c3-237">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="402c3-238">Seleccione la **pestaña Buzón personalizado.**</span><span class="sxs-lookup"><span data-stu-id="402c3-238">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="402c3-239">Puede hacer clic en el **botón Opciones de** columna situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="402c3-239">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="402c3-240">**Enviado en**</span><span class="sxs-lookup"><span data-stu-id="402c3-240">**Submitted on**</span></span>
- <span data-ttu-id="402c3-241">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-241">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-242">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-242">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-243">**Sender**</span><span class="sxs-lookup"><span data-stu-id="402c3-243">**Sender**</span></span>
- <span data-ttu-id="402c3-244">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="402c3-244">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="402c3-245">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="402c3-245">**Submission type**</span></span>

<span data-ttu-id="402c3-246">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y puede filtrar por **Enviado** especificando un valor en el cuadro y haciendo clic en el botón ![ Actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="402c3-246">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="402c3-247">Update</span><span class="sxs-lookup"><span data-stu-id="402c3-247">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="402c3-248">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="402c3-248">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="402c3-249">En el cuadro de diálogo que aparece, guarde el archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="402c3-249">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="402c3-250">Deshacer envíos de usuarios</span><span class="sxs-lookup"><span data-stu-id="402c3-250">Undo user submissions</span></span>

<span data-ttu-id="402c3-251">Una vez que un usuario envía un correo electrónico sospechoso al buzón personalizado, el usuario y el administrador no tienen la opción de deshacer el envío.</span><span class="sxs-lookup"><span data-stu-id="402c3-251">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="402c3-252">Si el usuario desea recuperar el correo electrónico, estará disponible para su recuperación en las carpetas Elementos eliminados o Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="402c3-252">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="402c3-253">Enviar mensajes a Microsoft desde el buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="402c3-253">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="402c3-254">Si ha configurado el buzón personalizado para interceptar mensajes notificados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="402c3-254">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="402c3-255">Esto mueve de forma eficaz un envío de usuario a un envío de administrador.</span><span class="sxs-lookup"><span data-stu-id="402c3-255">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="402c3-256">En la **pestaña Buzón personalizado,** seleccione un  mensaje en la lista, haga clic en el botón Acción y realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="402c3-256">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="402c3-257">**Informe limpio**</span><span class="sxs-lookup"><span data-stu-id="402c3-257">**Report clean**</span></span>
- <span data-ttu-id="402c3-258">**Informar sobre la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="402c3-258">**Report phishing**</span></span>
- <span data-ttu-id="402c3-259">**Notificar malware**</span><span class="sxs-lookup"><span data-stu-id="402c3-259">**Report malware**</span></span>
- <span data-ttu-id="402c3-260">**Notificar correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="402c3-260">**Report spam**</span></span>

![Opciones del botón Acción](../../media/user-submission-custom-mailbox-action-button.png)
