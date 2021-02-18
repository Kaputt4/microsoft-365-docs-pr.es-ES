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
ms.openlocfilehash: 7b4e6dfcb5900ed41ad3ab0b44fada93599f0b4b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288794"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="3ef5b-103">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ef5b-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3ef5b-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-104">**Applies to**</span></span>
- [<span data-ttu-id="3ef5b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3ef5b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3ef5b-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3ef5b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)


<span data-ttu-id="3ef5b-107">En organizaciones de Microsoft 365 con buzones en Exchange Online, los administradores pueden usar el portal de envíos del Centro de seguridad & y cumplimiento para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="3ef5b-108">Cuando envíe un mensaje de correo electrónico, recibirá:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="3ef5b-109">**Comprobación de autenticación de** correo electrónico: detalles sobre si la autenticación de correo electrónico se ha superado o no cuando se entregó.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="3ef5b-110">**Aciertos de** directiva: información sobre las directivas que pueden haber permitido o bloqueado el correo electrónico entrante en su espacio empresarial, invalidando nuestros veredictos de filtro de servicio.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="3ef5b-111">**Reputación/detonación de carga:** examen de las direcciones URL y los datos adjuntos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="3ef5b-112">**Análisis de calificador:** revisión realizada por los calificadores para confirmar si los mensajes son malintencionados o no.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ef5b-113">La reputación/detonación de carga útil y el análisis de calificador no se realizan en todos los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="3ef5b-114">Se bloquea la información para que no salga de la organización cuando se supone que los datos no deben salir del límite del espacio empresarial por motivos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="3ef5b-115">Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea Notificar mensajes y [archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="3ef5b-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3ef5b-116">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="3ef5b-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3ef5b-117">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3ef5b-118">Para ir directamente a la **página Envío,** use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="3ef5b-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="3ef5b-119">Para enviar mensajes y archivos a Microsoft, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="3ef5b-120">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3ef5b-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="3ef5b-121">**Administración de la** organización [en Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="3ef5b-121">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="3ef5b-122">Tenga en cuenta que es necesario pertenecer a este grupo de roles para ver los [envíos](#view-user-submissions-to-the-custom-mailbox) de usuarios al buzón personalizado, tal como se describe más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="3ef5b-123">Para obtener más información acerca de cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea Notificar mensajes y [archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="3ef5b-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="3ef5b-124">Notificar contenido sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ef5b-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="3ef5b-125">En el Centro de & cumplimiento,  vaya a Envíos de administración de amenazas, compruebe que está en la pestaña Envíos de administración y, a continuación, haga clic en \>  **Nuevo envío.** </span><span class="sxs-lookup"><span data-stu-id="3ef5b-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="3ef5b-126">Use **el menú desplegable Nuevo** envío que parece enviar el mensaje, la dirección URL o los datos adjuntos, tal como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="3ef5b-127">Enviar un correo electrónico cuestionable a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ef5b-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="3ef5b-128">En la **sección Tipo de** objeto, seleccione Correo **electrónico.**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="3ef5b-129">En la **sección Formato de** envío, usa una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="3ef5b-130">**Id.** de mensaje de red: es un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-Id** del mensaje o en el encabezado **X-MS-Office365-Filtering-Correlation-Id** en mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="3ef5b-131">**Archivo:** haga clic **en Elegir archivo.**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="3ef5b-132">En el cuadro de diálogo que se abre, busque y seleccione el archivo .eml o .msg y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3ef5b-133">Los administradores con Defender para Office 365 Plan 1 o Plan 2 pueden enviar mensajes tan antiguos como 30 días.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="3ef5b-134">Otros administradores solo podrán volver 7 días atrás.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="3ef5b-135">En la **sección** Destinatarios, especifique uno o más destinatarios con los que desea ejecutar una comprobación de directiva.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="3ef5b-136">La comprobación de directivas determinará si el correo electrónico omitió el examen debido a directivas de usuario u organización.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="3ef5b-137">En la **sección Motivo del envío,** selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3ef5b-138">**No debería haber sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3ef5b-139">**Debería haber sido bloqueado:** Seleccionar **correo no** deseado, **suplantación** de identidad o **malware.**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="3ef5b-140">Si no está seguro, use su mejor criterio.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="3ef5b-141">Cuando haya terminado, haga clic en **el botón** Enviar.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-141">When you're finished, click the **Submit** button.</span></span>

   ![Ejemplo de envío de dirección URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="3ef5b-143">Enviar una dirección URL sospechosa a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ef5b-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="3ef5b-144">En la **sección Tipo de** objeto, seleccione Dirección **URL**.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="3ef5b-145">En el cuadro que aparece, escriba la dirección URL completa (por ejemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="3ef5b-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="3ef5b-146">En la **sección Motivo del envío,** selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3ef5b-147">**No debería haber sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3ef5b-148">**Debería haber sido bloqueado:** Seleccione **Suplantación de identidad** o **malware.**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="3ef5b-149">Cuando haya terminado, haga clic en **el botón** Enviar.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-149">When you're finished, click the **Submit** button.</span></span>

   ![Ejemplo de envío de correo electrónico](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="3ef5b-151">Enviar un archivo sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ef5b-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="3ef5b-152">En la **sección Tipo de** objeto, seleccione Datos **adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="3ef5b-153">Haga clic **en Elegir archivo.**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-153">Click **Choose File**.</span></span> <span data-ttu-id="3ef5b-154">En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="3ef5b-155">En la **sección Motivo del envío,** selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3ef5b-156">**No debería haber sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3ef5b-157">**Debería haber sido bloqueado:** **el malware** es la única opción y se selecciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="3ef5b-158">Cuando haya terminado, haga clic en **el botón** Enviar.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-158">When you're finished, click the **Submit** button.</span></span>

   ![Ejemplo de envío de datos adjuntos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="3ef5b-160">Ver envíos de administrador</span><span class="sxs-lookup"><span data-stu-id="3ef5b-160">View admin submissions</span></span>

<span data-ttu-id="3ef5b-161">En el Centro de & cumplimiento,  vaya a Envíos de administración de amenazas, compruebe que está en la pestaña Envíos de administración y, a continuación, haga clic en \>  **Nuevo envío.** </span><span class="sxs-lookup"><span data-stu-id="3ef5b-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="3ef5b-162">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por identificador de envío **(un** valor GUID asignado a cada envío) especificando un valor en el cuadro y haciendo clic en el botón Actualizar ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3ef5b-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3ef5b-163">Update</span><span class="sxs-lookup"><span data-stu-id="3ef5b-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3ef5b-164">Para cambiar los criterios de filtro, haz clic en el botón **Id. de** envío y elige uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="3ef5b-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-165">**Sender**</span></span>
- <span data-ttu-id="3ef5b-166">**Asunto/DIRECCIÓN URL/Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="3ef5b-167">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-167">**Submitted by**</span></span>
- <span data-ttu-id="3ef5b-168">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-168">**Submission type**</span></span>
- <span data-ttu-id="3ef5b-169">**Estado**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-169">**Status**</span></span>

![Opciones de filtro para envíos de administrador](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="3ef5b-171">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3ef5b-172">En el cuadro de diálogo que aparece, guarde el archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="3ef5b-173">Debajo del gráfico, hay tres pestañas: **Correo** electrónico (predeterminado), **Dirección URL** y **Datos adjuntos.**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="3ef5b-174">Ver envíos de correo electrónico de administrador</span><span class="sxs-lookup"><span data-stu-id="3ef5b-174">View admin email submissions</span></span>

<span data-ttu-id="3ef5b-175">Haga clic en la **pestaña** Correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-175">Click the **Email** tab.</span></span>

<span data-ttu-id="3ef5b-176">Puede hacer clic en el **botón Opciones de** columna situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3ef5b-177">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-177">**Date**</span></span>
- <span data-ttu-id="3ef5b-178">**Identificador de** envío: un valor GUID que se asigna a cada envío.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="3ef5b-179">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-180">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-181">**Sender**</span></span>
- <span data-ttu-id="3ef5b-182">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-183">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-183">**Submission type**</span></span>
- <span data-ttu-id="3ef5b-184">**Motivo de la entrega**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-184">**Delivery reason**</span></span>
- <span data-ttu-id="3ef5b-185">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3ef5b-186"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="3ef5b-187">Detalles del nuevo análisis del envío de administrador</span><span class="sxs-lookup"><span data-stu-id="3ef5b-187">Admin submission rescan details</span></span>

<span data-ttu-id="3ef5b-188">Los mensajes que se envían en envíos de administrador se examinan de nuevo y los resultados se muestran en el menú desplegable de detalles:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="3ef5b-189">Si se ha produce un error en la autenticación de correo electrónico del remitente en el momento de la entrega.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="3ef5b-190">Información sobre los aciertos de directiva que podrían haber afectado o invalidado el veredicto de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="3ef5b-191">Resultados de detonación actuales para ver si las direcciones URL o los archivos contenidos en el mensaje eran malintencionados o no.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="3ef5b-192">Comentarios de los alumnos.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-192">Feedback from graders.</span></span>

<span data-ttu-id="3ef5b-193">Si se encontró una invalidación, el nuevo análisis debe completarse en varios minutos.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="3ef5b-194">Si no hubo un problema en la autenticación o entrega de correo electrónico no se vio afectado por una invalidación, los comentarios de los calificadores podrían tardar hasta un día.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="3ef5b-195">Ver envíos de url de administrador</span><span class="sxs-lookup"><span data-stu-id="3ef5b-195">View admin URL submissions</span></span>

<span data-ttu-id="3ef5b-196">Haga clic en la **pestaña Dirección** URL.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-196">Click the **URL** tab.</span></span>

<span data-ttu-id="3ef5b-197">Puede hacer clic en el **botón Opciones de** columna situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3ef5b-198">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-198">**Date**</span></span>
- <span data-ttu-id="3ef5b-199">**Id. de envío**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-199">**Submission ID**</span></span>
- <span data-ttu-id="3ef5b-200">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-202">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-202">**Submission type**</span></span>
- <span data-ttu-id="3ef5b-203">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3ef5b-204"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="3ef5b-205">Ver envíos de datos adjuntos de administrador</span><span class="sxs-lookup"><span data-stu-id="3ef5b-205">View admin attachment submissions</span></span>

<span data-ttu-id="3ef5b-206">Haga clic en **la pestaña Datos** adjuntos.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="3ef5b-207">Puede hacer clic en el **botón Opciones de** columna situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3ef5b-208">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-208">**Date**</span></span>
- <span data-ttu-id="3ef5b-209">**Id. de envío**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-209">**Submission ID**</span></span>
- <span data-ttu-id="3ef5b-210">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-211">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-212">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-212">**Submission type**</span></span>
- <span data-ttu-id="3ef5b-213">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3ef5b-214"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="3ef5b-215">Ver envíos de usuarios a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ef5b-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="3ef5b-216">Si ha implementado el complemento Mensaje de [](enable-the-report-phish-add-in.md) [informe,](enable-the-report-message-add-in.md)el complemento de suplantación de identidad de informes o los usuarios usan los informes integrados en Outlook en [la Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)puede ver qué usuarios están informando en la pestaña **Envíos** de usuarios.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="3ef5b-217">En el Centro de & cumplimiento, vaya a **Envíos de administración** \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="3ef5b-218">Selecciona la **pestaña Envíos de** usuario y, a continuación, haz clic **en Nuevo envío.**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="3ef5b-219">Puede hacer clic en el **botón Opciones de** columna situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3ef5b-220">**Enviado en**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-220">**Submitted on**</span></span>
- <span data-ttu-id="3ef5b-221">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-222">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-223">**Sender**</span></span>
- <span data-ttu-id="3ef5b-224">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-225">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-225">**Submission type**</span></span>

<span data-ttu-id="3ef5b-226"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="3ef5b-227">Cerca de la parte superior de la página, puede escribir una fecha de  inicio, una fecha de finalización y, de forma predeterminada, puede filtrar por remitente especificando un valor en el cuadro y haciendo clic en el botón ![ Actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3ef5b-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3ef5b-228">Update</span><span class="sxs-lookup"><span data-stu-id="3ef5b-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3ef5b-229">Para cambiar los criterios de filtro, haga clic en el **botón Remitente** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="3ef5b-230">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-230">**Sender domain**</span></span>
- <span data-ttu-id="3ef5b-231">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-231">**Subject**</span></span>
- <span data-ttu-id="3ef5b-232">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-232">**Submitted by**</span></span>
- <span data-ttu-id="3ef5b-233">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-233">**Submission type**</span></span>
- <span data-ttu-id="3ef5b-234">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-234">**Sender IP**</span></span>

![Opciones de filtro para envíos de usuarios](../../media/user-submissions-filter-options.png)

<span data-ttu-id="3ef5b-236">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3ef5b-237">En el cuadro de diálogo que aparece, guarde el archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="3ef5b-238">Ver envíos de usuario al buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="3ef5b-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="3ef5b-239">**Si** ha configurado un [buzón personalizado](user-submission.md) para recibir mensajes notificados por el usuario, puede ver y enviar también los mensajes que se entregaron al buzón de informes.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="3ef5b-240">En el Centro de & cumplimiento, vaya a **Envíos de administración** \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="3ef5b-241">Seleccione la **pestaña Buzón personalizado.**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="3ef5b-242">Puede hacer clic en el **botón Opciones de** columna situado cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3ef5b-243">**Enviado en**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-243">**Submitted on**</span></span>
- <span data-ttu-id="3ef5b-244">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-245">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-246">**Sender**</span></span>
- <span data-ttu-id="3ef5b-247">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ef5b-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3ef5b-248">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-248">**Submission type**</span></span>

<span data-ttu-id="3ef5b-249">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y puede filtrar por **Enviado** especificando un valor en el cuadro y haciendo clic en el botón ![ Actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3ef5b-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3ef5b-250">Update</span><span class="sxs-lookup"><span data-stu-id="3ef5b-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3ef5b-251">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3ef5b-252">En el cuadro de diálogo que aparece, guarde el archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-252">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="3ef5b-253">Deshacer envíos de usuarios</span><span class="sxs-lookup"><span data-stu-id="3ef5b-253">Undo user submissions</span></span>

<span data-ttu-id="3ef5b-254">Una vez que un usuario envía un correo electrónico sospechoso al buzón personalizado, el usuario y el administrador no tienen la opción de deshacer el envío.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="3ef5b-255">Si el usuario desea recuperar el correo electrónico, estará disponible para su recuperación en las carpetas Elementos eliminados o Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="3ef5b-256">Enviar mensajes a Microsoft desde el buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="3ef5b-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="3ef5b-257">Si ha configurado el buzón personalizado para interceptar mensajes notificados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="3ef5b-258">Esto mueve de forma eficaz un envío de usuario a un envío de administrador.</span><span class="sxs-lookup"><span data-stu-id="3ef5b-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="3ef5b-259">En la **pestaña Buzón personalizado,** seleccione un  mensaje en la lista, haga clic en el botón Acción y realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="3ef5b-259">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="3ef5b-260">**Informe limpio**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-260">**Report clean**</span></span>
- <span data-ttu-id="3ef5b-261">**Informar sobre la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-261">**Report phishing**</span></span>
- <span data-ttu-id="3ef5b-262">**Notificar malware**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-262">**Report malware**</span></span>
- <span data-ttu-id="3ef5b-263">**Notificar correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="3ef5b-263">**Report spam**</span></span>

![Opciones en el botón Acción](../../media/user-submission-custom-mailbox-action-button.png)
