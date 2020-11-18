---
title: Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo buscar y usar informes de seguridad de correo electrónico para su organización. Los informes de seguridad de correo electrónico están disponibles en el centro de seguridad & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1b2fd7a18589932d56ea39722b48462d2a6eac2f
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131206"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="cf250-104">Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cf250-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cf250-105">Hay disponibles varios informes en el centro de [seguridad & cumplimiento](https://protection.office.com) para ayudarle a ver cómo las características de seguridad del correo electrónico, como las características contra correo electrónico no deseado, antimalware y de cifrado de Microsoft 365 están protegiendo su organización.</span><span class="sxs-lookup"><span data-stu-id="cf250-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="cf250-106">Si dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en el centro de seguridad & cumplimiento desde el panel de **informes** \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="cf250-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="cf250-107">Para ir directamente al panel informes, Abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="cf250-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Panel de informes en el centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="cf250-109">Informe de usuarios comprometidos</span><span class="sxs-lookup"><span data-stu-id="cf250-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="cf250-110">Este informe está disponible en Microsoft 365 organizaciones con buzones de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cf250-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="cf250-111">No está disponible en organizaciones independientes de Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="cf250-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="cf250-112">El informe de **usuarios comprometedos** muestra el número de cuentas de usuario que se marcaron como **sospechosas** o **restringidas** en los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="cf250-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="cf250-113">Las cuentas en cualquiera de estos Estados son problemáticas o incluso comprometidas.</span><span class="sxs-lookup"><span data-stu-id="cf250-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="cf250-114">Con el uso frecuente, puede usar el informe para identificar picos e incluso tendencias, en cuentas sospechosas o restringidas.</span><span class="sxs-lookup"><span data-stu-id="cf250-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="cf250-115">Para obtener más información acerca de los usuarios comprometidos, consulte [responder a una cuenta de correo electrónico en peligro](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget usuarios comprometidos en el panel informes](../../media/compromised-users-report-widget.png)

<span data-ttu-id="cf250-117">La vista agregada muestra los datos de los últimos 90 días y la vista de detalles muestra los datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="cf250-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="cf250-118">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **usuarios comprometidos**.</span><span class="sxs-lookup"><span data-stu-id="cf250-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="cf250-119">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="cf250-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="cf250-120">Puede filtrar tanto el gráfico como la tabla de detalles haciendo clic en **filtros** y seleccionando uno o más de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="cf250-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="cf250-121">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cf250-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="cf250-122">**Sospechoso**: la cuenta de usuario ha enviado un mensaje de correo electrónico sospechoso y corre el riesgo de que se restrinja el envío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="cf250-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="cf250-123">**Restringido**: se ha restringido el envío de correo electrónico a la cuenta de usuario debido a patrones muy sospechosos.</span><span class="sxs-lookup"><span data-stu-id="cf250-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Vista de informe en el informe de usuarios comprometedos](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="cf250-125">Si hace clic en **ver tabla de detalles**, puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="cf250-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="cf250-126">**Hora de creación**</span><span class="sxs-lookup"><span data-stu-id="cf250-126">**Creation time**</span></span>
- <span data-ttu-id="cf250-127">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="cf250-127">**User ID**</span></span>
- <span data-ttu-id="cf250-128">**Action**</span><span class="sxs-lookup"><span data-stu-id="cf250-128">**Action**</span></span>

<span data-ttu-id="cf250-129">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="cf250-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="cf250-130">Informe de cifrado</span><span class="sxs-lookup"><span data-stu-id="cf250-130">Encryption report</span></span>

<span data-ttu-id="cf250-131">El **Informe de cifrado** está disponible en EOP (suscripciones con buzones en Exchange online o EOP independiente sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="cf250-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="cf250-132">El equipo de seguridad de la organización puede usar la información de este informe para identificar patrones y aplicar de forma proactiva o ajustar las directivas de los mensajes de correo electrónico confidenciales.</span><span class="sxs-lookup"><span data-stu-id="cf250-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="cf250-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf250-133">For example:</span></span>

- <span data-ttu-id="cf250-134">Si ve un gran número de mensajes de correo electrónico cifrados por los usuarios, es posible que desee agregar una directiva de cifrado para automatizar el cifrado para determinados casos de uso.</span><span class="sxs-lookup"><span data-stu-id="cf250-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="cf250-135">Para obtener más información, vea [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="cf250-136">Si tiene varias plantillas de cifrado disponibles pero nadie las está usando, puede explorar si los usuarios necesitan formación de características.</span><span class="sxs-lookup"><span data-stu-id="cf250-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="cf250-137">La vista agregada permite filtrar los últimos 90 días, mientras que la vista de detalles permite el filtrado durante 10 días.</span><span class="sxs-lookup"><span data-stu-id="cf250-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="cf250-138">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **Informe de cifrado**.</span><span class="sxs-lookup"><span data-stu-id="cf250-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="cf250-139">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="cf250-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="cf250-140">Para obtener más información sobre el cifrado, consulte [cifrado de correo electrónico en Microsoft 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="cf250-141">Vista informes para el informe de cifrado</span><span class="sxs-lookup"><span data-stu-id="cf250-141">Report view for the Encryption report</span></span>

<span data-ttu-id="cf250-142">Puede usar los siguientes filtros en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="cf250-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="cf250-143">**Ver datos por: informe de cifrado de mensajes** y **desglose descendente por: método de cifrado**: están disponibles los siguientes métodos de cifrado:</span><span class="sxs-lookup"><span data-stu-id="cf250-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="cf250-144">**Cifrado por usuario**</span><span class="sxs-lookup"><span data-stu-id="cf250-144">**Encryption by user**</span></span>
  - <span data-ttu-id="cf250-145">**Cifrado por directiva**</span><span class="sxs-lookup"><span data-stu-id="cf250-145">**Encryption by policy**</span></span>

  <span data-ttu-id="cf250-146">Si hace clic en **filtros**, puede modificar el gráfico con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="cf250-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="cf250-147">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cf250-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cf250-148">Método de cifrado.</span><span class="sxs-lookup"><span data-stu-id="cf250-148">Encryption method.</span></span>
  - <span data-ttu-id="cf250-149">Plantilla de cifrado.</span><span class="sxs-lookup"><span data-stu-id="cf250-149">Encryption template.</span></span>

- <span data-ttu-id="cf250-150">**Ver datos por: informe de cifrado de mensajes** y **desglosar por: plantilla de cifrado**: están disponibles los siguientes métodos de cifrado:</span><span class="sxs-lookup"><span data-stu-id="cf250-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="cf250-151">**No reenviar**</span><span class="sxs-lookup"><span data-stu-id="cf250-151">**Do not forward**</span></span>
  - <span data-ttu-id="cf250-152">**Cifrar solo**</span><span class="sxs-lookup"><span data-stu-id="cf250-152">**Encrypt only**</span></span>
  - <span data-ttu-id="cf250-153">**OME anterior**</span><span class="sxs-lookup"><span data-stu-id="cf250-153">**OME previous**</span></span>
  - <span data-ttu-id="cf250-154">**Personalizados**</span><span class="sxs-lookup"><span data-stu-id="cf250-154">**Custom**</span></span>

  <span data-ttu-id="cf250-155">Si hace clic en **filtros**, puede modificar el gráfico con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="cf250-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="cf250-156">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cf250-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cf250-157">Método de cifrado</span><span class="sxs-lookup"><span data-stu-id="cf250-157">Encryption method</span></span>
  - <span data-ttu-id="cf250-158">Plantilla de cifrado</span><span class="sxs-lookup"><span data-stu-id="cf250-158">Encryption template</span></span>

- <span data-ttu-id="cf250-159">**Ver datos por: los 5 dominios de destinatarios principales**: esta vista muestra un gráfico circular con recuentos de mensajes enviados para los 5 principales dominios de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="cf250-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="cf250-160">Si hace clic en **filtros**, puede seleccionar una **fecha de inicio** y una fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="cf250-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="cf250-161">Vista de tabla de detalles para el informe de cifrado</span><span class="sxs-lookup"><span data-stu-id="cf250-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="cf250-162">Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="cf250-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cf250-163">**Dividir por: método de cifrado** o **desglosar por: plantilla de cifrado**: se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cf250-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="cf250-164">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cf250-164">**Date**</span></span>
  - <span data-ttu-id="cf250-165">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="cf250-165">**Sender address**</span></span>
  - <span data-ttu-id="cf250-166">**Plantilla de cifrado**</span><span class="sxs-lookup"><span data-stu-id="cf250-166">**Encryption template**</span></span>
  - <span data-ttu-id="cf250-167">**Método de cifrado**</span><span class="sxs-lookup"><span data-stu-id="cf250-167">**Encryption method**</span></span>
  - <span data-ttu-id="cf250-168">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="cf250-168">**Recipient address**</span></span>
  - <span data-ttu-id="cf250-169">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="cf250-169">**Subject**</span></span>

- <span data-ttu-id="cf250-170">**Ver datos por: los 5 dominios de destinatarios principales**:</span><span class="sxs-lookup"><span data-stu-id="cf250-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="cf250-171">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cf250-171">**Date**</span></span>
  - <span data-ttu-id="cf250-172">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="cf250-172">**Recipient domain**</span></span>
  - <span data-ttu-id="cf250-173">**Número de mensajes**</span><span class="sxs-lookup"><span data-stu-id="cf250-173">**Message count**</span></span>

<span data-ttu-id="cf250-174">Si hace clic en **filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="cf250-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cf250-175">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cf250-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="cf250-176">Método de cifrado</span><span class="sxs-lookup"><span data-stu-id="cf250-176">Encryption method</span></span>
- <span data-ttu-id="cf250-177">Plantilla de cifrado</span><span class="sxs-lookup"><span data-stu-id="cf250-177">Encryption template</span></span>

<span data-ttu-id="cf250-178">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="cf250-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="cf250-179">Informe de estado de flujo de notificación</span><span class="sxs-lookup"><span data-stu-id="cf250-179">Mailflow status report</span></span>

<span data-ttu-id="cf250-180">El **Informe de estado de flujo** de correo contiene información sobre malware, correo no deseado, phishing y mensajes bloqueados del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="cf250-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="cf250-181">Para obtener más información, consulte [Informe de estado de flujo](view-mail-flow-reports.md#mailflow-status-report)de datos.</span><span class="sxs-lookup"><span data-stu-id="cf250-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="cf250-182">Informe de detecciones de malware en correo electrónico</span><span class="sxs-lookup"><span data-stu-id="cf250-182">Malware detections in email report</span></span>

<span data-ttu-id="cf250-183">El informe **de detecciones de malware en el informe de correo electrónico** muestra información sobre las detecciones de malware en los mensajes entrantes y salientes (malware detectado por Exchange Online Protection o EOP).</span><span class="sxs-lookup"><span data-stu-id="cf250-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="cf250-184">Para obtener más información acerca de la protección contra malware en EOP, vea [Anti-Malware Protection in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="cf250-185">El filtro de vista agregado permite 90 días, mientras que el filtro de tabla de detalles sólo permite 10 días.</span><span class="sxs-lookup"><span data-stu-id="cf250-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="cf250-186">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **detecciones de malware en correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="cf250-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="cf250-187">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="cf250-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Detecciones de malware en el widget de correo electrónico en el panel informes](../../media/malware-detections-widget.png)

<span data-ttu-id="cf250-189">Puede filtrar tanto el gráfico como la tabla de detalles haciendo clic en **filtros** y seleccionando:</span><span class="sxs-lookup"><span data-stu-id="cf250-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="cf250-190">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cf250-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="cf250-191">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="cf250-191">**Inbound**</span></span>
- <span data-ttu-id="cf250-192">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="cf250-192">**Outbound**</span></span>

![Vista de informe en el informe de detección de malware en correo electrónico](../../media/malware-detections-report-view.png)

<span data-ttu-id="cf250-194">Si hace clic en **ver tabla de detalles**, puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="cf250-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="cf250-195">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cf250-195">**Date**</span></span>
- <span data-ttu-id="cf250-196">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="cf250-196">**Sender address**</span></span>
- <span data-ttu-id="cf250-197">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="cf250-197">**Recipient address**</span></span>
- <span data-ttu-id="cf250-198">**Identificador del mensaje**: disponible en el campo de encabezado del **identificador del mensaje** en el encabezado del mensaje y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="cf250-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="cf250-199">Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observe los corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="cf250-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="cf250-200">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="cf250-200">**Subject**</span></span>
- <span data-ttu-id="cf250-201">**Filename**</span><span class="sxs-lookup"><span data-stu-id="cf250-201">**Filename**</span></span>
- <span data-ttu-id="cf250-202">**Nombre del malware**</span><span class="sxs-lookup"><span data-stu-id="cf250-202">**Malware name**</span></span>

<span data-ttu-id="cf250-203">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="cf250-203">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="cf250-204">Informe de latencia de correo</span><span class="sxs-lookup"><span data-stu-id="cf250-204">Mail latency report</span></span>

<span data-ttu-id="cf250-205">El **Informe de latencia de correo** contiene información sobre la entrega de correo y la latencia de detonaciones experimentadas en la organización.</span><span class="sxs-lookup"><span data-stu-id="cf250-205">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="cf250-206">Para obtener más información, vea [Informe de latencia de correo](view-reports-for-atp.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="cf250-206">For more information, see [Mail latency report](view-reports-for-atp.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="cf250-207">Informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="cf250-207">Sent and received email report</span></span>

<span data-ttu-id="cf250-208">El informe de **correo electrónico enviado y recibido** contiene información sobre malware, correo no deseado, reglas de flujo de correo (también conocidos como reglas de transporte) y detecciones de malware avanzadas una vez que el correo electrónico entra en el servicio.</span><span class="sxs-lookup"><span data-stu-id="cf250-208">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="cf250-209">Para obtener más información, consulte [Informe de correo electrónico enviado y recibido](view-mail-flow-reports.md#sent-and-received-email-report).</span><span class="sxs-lookup"><span data-stu-id="cf250-209">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="cf250-210">Informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="cf250-210">Spam detections report</span></span>

<span data-ttu-id="cf250-211">El informe de **detecciones de correo no deseado** muestra mensajes de correo electrónico no deseado bloqueados por EOP.</span><span class="sxs-lookup"><span data-stu-id="cf250-211">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="cf250-212">Los mensajes se cuentan de forma individual, no por destinatario.</span><span class="sxs-lookup"><span data-stu-id="cf250-212">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="cf250-213">Por ejemplo, si se envió el mismo mensaje de correo no deseado a 100 destinatarios de la organización, se cuenta como un mensaje.</span><span class="sxs-lookup"><span data-stu-id="cf250-213">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="cf250-214">La vista agregada permite el filtrado de 90 días, mientras que la tabla de detalles permite el filtrado de 10 días.</span><span class="sxs-lookup"><span data-stu-id="cf250-214">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="cf250-215">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **detecciones de correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="cf250-215">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="cf250-216">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="cf250-216">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Widget de detecciones de correo no deseado en el panel informes](../../media/spam-detections-report-widget.png)

<span data-ttu-id="cf250-218">Para obtener más información acerca de la protección contra correo no deseado, vea [protección contra correo no deseado en EOP](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-218">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="cf250-219">Vista informes para el informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="cf250-219">Report view for the Spam detections report</span></span>

<span data-ttu-id="cf250-220">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="cf250-220">The following charts are available in the report view:</span></span>

- <span data-ttu-id="cf250-221">**Dividir por: acción**: se muestran los siguientes tipos de eventos:</span><span class="sxs-lookup"><span data-stu-id="cf250-221">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="cf250-222">**Contenido de correo no deseado filtrado**</span><span class="sxs-lookup"><span data-stu-id="cf250-222">**Spam content filtered**</span></span>
  - <span data-ttu-id="cf250-223">**Bloqueo de IP de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="cf250-223">**Spam IP block**</span></span>
  - <span data-ttu-id="cf250-224">**Bloque de sobre de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="cf250-224">**Spam envelope block**</span></span>
  - <span data-ttu-id="cf250-225">**Filtro de DBEB de correo no deseado**: bloqueo perimetral basado en directorios (DBEB)</span><span class="sxs-lookup"><span data-stu-id="cf250-225">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="cf250-226">Al pasar el mouse por encima de un día (punto de datos) en el gráfico, puede ver cuántos elementos se bloquearon ese día, así como la forma en que se clasifican dichos elementos.</span><span class="sxs-lookup"><span data-stu-id="cf250-226">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Vista de acción en el informe de detecciones de correo no deseado](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="cf250-228">**Desglose por: dirección**: se muestran las siguientes direcciones:</span><span class="sxs-lookup"><span data-stu-id="cf250-228">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="cf250-229">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="cf250-229">**Inbound**</span></span>
  - <span data-ttu-id="cf250-230">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="cf250-230">**Outbound**</span></span>

  ![Vista de dirección en en el informe de detecciones de correo no deseado](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="cf250-232">Si hace clic en **filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="cf250-232">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cf250-233">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cf250-233">**Start date** and **End date**</span></span>
- <span data-ttu-id="cf250-234">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="cf250-234">Direction values</span></span>
- <span data-ttu-id="cf250-235">Valores de tipo de evento</span><span class="sxs-lookup"><span data-stu-id="cf250-235">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="cf250-236">Vista de tabla de detalles para el informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="cf250-236">Details table view for the Spam detections report</span></span>

<span data-ttu-id="cf250-237">Si hace clic en **ver tabla de detalles** en cualquier vista de informe, se mostrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cf250-237">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="cf250-238">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cf250-238">**Date**</span></span>
- <span data-ttu-id="cf250-239">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="cf250-239">**Sender address**</span></span>
- <span data-ttu-id="cf250-240">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="cf250-240">**Recipient address**</span></span>
- <span data-ttu-id="cf250-241">**Tipo de evento**</span><span class="sxs-lookup"><span data-stu-id="cf250-241">**Event type**</span></span>
- <span data-ttu-id="cf250-242">**Action**</span><span class="sxs-lookup"><span data-stu-id="cf250-242">**Action**</span></span>
- <span data-ttu-id="cf250-243">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="cf250-243">**Subject**</span></span>

<span data-ttu-id="cf250-244">Si hace clic en **filtros** en una tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="cf250-244">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cf250-245">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cf250-245">**Start date** and **End date**</span></span>
- <span data-ttu-id="cf250-246">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="cf250-246">Direction values</span></span>
- <span data-ttu-id="cf250-247">Valores de tipo de evento</span><span class="sxs-lookup"><span data-stu-id="cf250-247">Event type values</span></span>

<span data-ttu-id="cf250-248">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="cf250-248">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="cf250-249">Informe de detecciones de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="cf250-249">Spoof detections report</span></span>

<span data-ttu-id="cf250-250">El informe de **detecciones de suplantación de identidad** muestra el número de mensajes de correo falsificados que se han detectado y de aquellos que se consideran "buenos" (correo falsificado realizado por razones empresariales legítimas).</span><span class="sxs-lookup"><span data-stu-id="cf250-250">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="cf250-251">Para obtener más información sobre la suplantación de identidad, vea [anti-spoofing Protection in EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-251">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="cf250-252">La vista agregada del informe permite 90 días de filtrado, mientras que la vista de detalles sólo permite diez días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="cf250-252">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="cf250-253">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **detecciones de suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="cf250-253">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="cf250-254">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="cf250-254">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Widget detecciones de suplantación en el panel de informes](../../media/spoof-detections-widget.png)

<span data-ttu-id="cf250-256">Al pasar el mouse por encima de un día (punto de datos) en el gráfico, puede ver cuántos mensajes de correo electrónico de falsificación llegaron.</span><span class="sxs-lookup"><span data-stu-id="cf250-256">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="cf250-257">Puede filtrar tanto el gráfico como la tabla de detalles haciendo clic en **filtros** y seleccionando uno o más de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="cf250-257">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="cf250-258">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cf250-258">**Start date** and **End date**</span></span>

- <span data-ttu-id="cf250-259">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="cf250-259">**Good mail**</span></span>

- <span data-ttu-id="cf250-260">**Detectado como correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="cf250-260">**Caught as spam**</span></span>

![Vista informes en el informe de detecciones de suplantación de identidad](../../media/spoof-detections-report-view.png)

<span data-ttu-id="cf250-262">Si hace clic en **ver tabla de detalles**, puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="cf250-262">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="cf250-263">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cf250-263">**Date**</span></span>
- <span data-ttu-id="cf250-264">**Remitente falsificado**</span><span class="sxs-lookup"><span data-stu-id="cf250-264">**Spoofed sender**</span></span>
- <span data-ttu-id="cf250-265">**Auténtico remitente**</span><span class="sxs-lookup"><span data-stu-id="cf250-265">**True sender**</span></span>
- <span data-ttu-id="cf250-266">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="cf250-266">**Sender IP**</span></span>
- <span data-ttu-id="cf250-267">**Action**</span><span class="sxs-lookup"><span data-stu-id="cf250-267">**Action**</span></span>
- <span data-ttu-id="cf250-268">**Número de mensajes**</span><span class="sxs-lookup"><span data-stu-id="cf250-268">**Message count**</span></span>

<span data-ttu-id="cf250-269">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="cf250-269">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="cf250-270">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="cf250-270">Threat protection status report</span></span>

<span data-ttu-id="cf250-271">El informe de **Estado de protección contra amenazas** está disponible en EOP y en Microsoft defender para Office 365; sin embargo, los informes contienen datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="cf250-271">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="cf250-272">Por ejemplo, los clientes de EOP pueden ver información sobre malware detectado en el correo electrónico, pero no información sobre los archivos malintencionados detectados por [ATP para SharePoint, OneDrive o Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-272">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [ATP for SharePoint, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="cf250-273">El informe proporciona el número de mensajes de correo electrónico con contenido malintencionado, como archivos o direcciones de sitios web (URL) bloqueados por el motor antimalware, [purgado automático de cero horas (ZAP)](zero-hour-auto-purge.md)y defender para Office 365 características como [vínculos seguros](atp-safe-links.md), [datos adjuntos seguros](atp-safe-attachments.md)y [anti-phishing](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-273">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="cf250-274">Puede usar esta información para identificar tendencias o determinar si es necesario ajustar las directivas de la organización.</span><span class="sxs-lookup"><span data-stu-id="cf250-274">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="cf250-275">**Nota**: es importante comprender que si un mensaje se envía a cinco destinatarios, se cuenta como cinco mensajes diferentes y no un mensaje.</span><span class="sxs-lookup"><span data-stu-id="cf250-275">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="cf250-276">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione estado de **protección contra amenazas**.</span><span class="sxs-lookup"><span data-stu-id="cf250-276">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="cf250-277">Para ir directamente al informe, abra una de las siguientes direcciones URL:</span><span class="sxs-lookup"><span data-stu-id="cf250-277">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="cf250-278">Microsoft defender para Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="cf250-278">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="cf250-279">EOP <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="cf250-279">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Widget de estado de protección contra amenazas en el panel de informes](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="cf250-281">De forma predeterminada, el gráfico muestra los datos de los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="cf250-281">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="cf250-282">Si hace clic en **filtros**, puede seleccionar un intervalo de fechas de 90 días (las suscripciones de prueba pueden estar limitadas a 30 días).</span><span class="sxs-lookup"><span data-stu-id="cf250-282">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="cf250-283">La vista de tabla de detalles permite filtrar durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="cf250-283">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="cf250-284">Vista informes para el informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="cf250-284">Report view for the Threat protection status report</span></span>

<span data-ttu-id="cf250-285">Están disponibles las siguientes vistas:</span><span class="sxs-lookup"><span data-stu-id="cf250-285">The following views are available:</span></span>

- <span data-ttu-id="cf250-286">**Ver datos por: información general**: se muestra la siguiente información de detección:</span><span class="sxs-lookup"><span data-stu-id="cf250-286">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="cf250-287">**Malware de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="cf250-287">**Email malware**</span></span>
  - <span data-ttu-id="cf250-288">**Phishing de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="cf250-288">**Email phish**</span></span>
  - <span data-ttu-id="cf250-289">**Malware de contenido**</span><span class="sxs-lookup"><span data-stu-id="cf250-289">**Content malware**</span></span>

  ![Vista de información general en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="cf250-291">**Ver datos por: contenido \> Malware**<sup>1</sup>: se muestra la siguiente información para las organizaciones de Microsoft Defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="cf250-291">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="cf250-292">**Motor antimalware**: archivos malintencionados detectados en SharePoint, OneDrive y Microsoft Teams mediante la [detección de virus integrada en Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-292">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="cf250-293">**Detonación de archivo**: archivos malintencionados detectados por [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-293">**File detonation**: Malicious files detected by [ATP for Sharepoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

  ![Vista de malware de contenido en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="cf250-295">**Ver datos por: reemplazo de mensaje**: se muestra la siguiente información sobre el motivo de invalidación:</span><span class="sxs-lookup"><span data-stu-id="cf250-295">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="cf250-296">**Omisión local**</span><span class="sxs-lookup"><span data-stu-id="cf250-296">**On-premises skip**</span></span>
  - <span data-ttu-id="cf250-297">**IP allow**</span><span class="sxs-lookup"><span data-stu-id="cf250-297">**IP Allow**</span></span>
  - <span data-ttu-id="cf250-298">**Regla de flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="cf250-298">**Mail flow rule**</span></span>
  - <span data-ttu-id="cf250-299">**Permitir remitente**</span><span class="sxs-lookup"><span data-stu-id="cf250-299">**Sender allow**</span></span>
  - <span data-ttu-id="cf250-300">**Permitir dominio**</span><span class="sxs-lookup"><span data-stu-id="cf250-300">**Domain allow**</span></span>
  - <span data-ttu-id="cf250-301">**ZAP no habilitado**</span><span class="sxs-lookup"><span data-stu-id="cf250-301">**ZAP not enabled**</span></span>
  - <span data-ttu-id="cf250-302">**Carpeta de correo no deseado no habilitada**</span><span class="sxs-lookup"><span data-stu-id="cf250-302">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="cf250-303">**Remitente seguro del usuario**</span><span class="sxs-lookup"><span data-stu-id="cf250-303">**User Safe Sender**</span></span>
  - <span data-ttu-id="cf250-304">**Dominio seguro del usuario**</span><span class="sxs-lookup"><span data-stu-id="cf250-304">**User Safe Domain**</span></span>

  ![Vista de invalidación de mensajes en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="cf250-306">**Desglose por: tecnología de detección** y **ver datos por: \> phishing email**: se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cf250-306">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="cf250-307">**Reputación de dirección URL generada por ATP**<sup>1</sup>: reputación de dirección URL malintencionada generada desde defender para Office 365 detonaciones en otros clientes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf250-307">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="cf250-308">**Filtro de phish avanzado**: señales de suplantación de identidad basadas en aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="cf250-308">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="cf250-309">**Anti-spoofing-error de dMarc**: error de autenticación de dMarc en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="cf250-309">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="cf250-310">**Anti-spoofing-intra-org**: el remitente está intentando imitar el dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="cf250-310">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="cf250-311">**Anti-falseamiento-dominio externo**: el remitente está intentando suplantar algún otro dominio.</span><span class="sxs-lookup"><span data-stu-id="cf250-311">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="cf250-312">**Suplantación de marca**: suplantación de marcas conocidas basadas en remitentes.</span><span class="sxs-lookup"><span data-stu-id="cf250-312">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="cf250-313">**Suplantación de dominio**<sup>1</sup>: suplantación de dominios que el cliente posee o define.</span><span class="sxs-lookup"><span data-stu-id="cf250-313">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="cf250-314">**Reputación de dirección URL de EOP**: reputación de dirección URL malintencionada.</span><span class="sxs-lookup"><span data-stu-id="cf250-314">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="cf250-315">**Filtro de phish general**: señales de suplantación de identidad basadas en reglas de analista.</span><span class="sxs-lookup"><span data-stu-id="cf250-315">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="cf250-316">**Otros**</span><span class="sxs-lookup"><span data-stu-id="cf250-316">**Others**</span></span>
  - <span data-ttu-id="cf250-317">**Zap de phish**<sup>2</sup>: purga automática de cero horas de mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="cf250-317">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="cf250-318">**Detonación de dirección URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cf250-318">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="cf250-319">**Suplantación de usuario**<sup>1</sup>: suplantación de usuarios definida por el administrador o aprendida a través de la inteligencia de buzones.</span><span class="sxs-lookup"><span data-stu-id="cf250-319">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Vista de la tecnología de detección de correo phishing en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="cf250-321">**Desglose por: tecnología de detección** y **ver datos por: \> malware de correo electrónico**: se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cf250-321">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="cf250-322">**Reputación de archivo generada por ATP**<sup>1</sup>: toda la reputación de archivos malintencionados generada por defender para Office 365 detonaciones.</span><span class="sxs-lookup"><span data-stu-id="cf250-322">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="cf250-323">**Motor de antimalware**<sup>1</sup>: detección de motores antimalware.</span><span class="sxs-lookup"><span data-stu-id="cf250-323">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="cf250-324">**Bloqueo de tipo de archivo de directiva antimalware**: son mensajes de correo electrónico filtrados debido al tipo de archivo malintencionado identificado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cf250-324">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="cf250-325">**Detonación de archivo**<sup>1</sup>: detección por datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="cf250-325">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="cf250-326">**Reputación de archivos malintencionados**</span><span class="sxs-lookup"><span data-stu-id="cf250-326">**Malicious file reputation**</span></span>
  - <span data-ttu-id="cf250-327">**Zap de malware**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cf250-327">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="cf250-328">**Otros**</span><span class="sxs-lookup"><span data-stu-id="cf250-328">**Others**</span></span>

  ![Vista de la tecnología de detección de malware en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="cf250-330">**Desglose por: tipo de directiva** y **ver datos por: \> phishing de correo electrónico** o **ver datos por: \> malware de correo electrónico**: se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cf250-330">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="cf250-331">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="cf250-331">**Anti-malware**</span></span>
  - <span data-ttu-id="cf250-332">**Datos adjuntos seguros**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cf250-332">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="cf250-333">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="cf250-333">**Anti-phish**</span></span>
  - <span data-ttu-id="cf250-334">**Contra correo electrónico no deseado**</span><span class="sxs-lookup"><span data-stu-id="cf250-334">**Anti-spam**</span></span>
  - <span data-ttu-id="cf250-335">**Regla de flujo de correo** (también denominada regla de transporte)</span><span class="sxs-lookup"><span data-stu-id="cf250-335">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="cf250-336">**Otros**</span><span class="sxs-lookup"><span data-stu-id="cf250-336">**Others**</span></span>

  ![Vista de tipo de directiva de correo de suplantación de identidad en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="cf250-338">**Desglose por: estado de entrega** y **ver datos por: \> phishing de correo electrónico** o **ver datos por: \> malware de correo electrónico**: se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cf250-338">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="cf250-339">**Error en la entrega**</span><span class="sxs-lookup"><span data-stu-id="cf250-339">**Delivery failed**</span></span>
  - <span data-ttu-id="cf250-340">**Sombra**</span><span class="sxs-lookup"><span data-stu-id="cf250-340">**Dropped**</span></span>
  - <span data-ttu-id="cf250-341">**Reenviado**</span><span class="sxs-lookup"><span data-stu-id="cf250-341">**Forwarded**</span></span>
  - <span data-ttu-id="cf250-342">**Buzón de correo hospedado: carpeta personalizada**</span><span class="sxs-lookup"><span data-stu-id="cf250-342">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="cf250-343">**Buzón de correo hospedado: elementos eliminados**</span><span class="sxs-lookup"><span data-stu-id="cf250-343">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="cf250-344">**Buzón de correo hospedado: bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="cf250-344">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="cf250-345">**Buzón hospedado: correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="cf250-345">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="cf250-346">**Servidor local: entregado**</span><span class="sxs-lookup"><span data-stu-id="cf250-346">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="cf250-347">**Cuarentena**</span><span class="sxs-lookup"><span data-stu-id="cf250-347">**Quarantine**</span></span>

  ![Vista de estado de entrega de correo de suplantación de identidad en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="cf250-349"><sup>1</sup> defender solo para Office 365</span><span class="sxs-lookup"><span data-stu-id="cf250-349"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="cf250-350"><sup>2</sup> la depuración automática de cero horas (ZAP) no está disponible en EOP independiente (solo funciona en buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="cf250-350"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="cf250-351">Si hace clic en **filtros**, los filtros disponibles dependen del gráfico que esté consultando:</span><span class="sxs-lookup"><span data-stu-id="cf250-351">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cf250-352">Para **ver los datos por: \> malware de contenido**, puede modificar el informe por la **fecha de inicio** y la **fecha de finalización**, y por el valor de **detección** .</span><span class="sxs-lookup"><span data-stu-id="cf250-352">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="cf250-353">Para **ver los datos por: reemplazo de mensaje**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="cf250-353">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cf250-354">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cf250-354">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cf250-355">**Motivo de la invalidación**</span><span class="sxs-lookup"><span data-stu-id="cf250-355">**Override Reason**</span></span>
  - <span data-ttu-id="cf250-356">**Tag**: filtrar los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="cf250-356">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="cf250-357">Para obtener más información acerca de las etiquetas de usuario, vea [etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-357">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="cf250-358">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="cf250-358">**Domain**</span></span>

- <span data-ttu-id="cf250-359">Para todas las demás vistas, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="cf250-359">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cf250-360">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cf250-360">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cf250-361">**Detección**</span><span class="sxs-lookup"><span data-stu-id="cf250-361">**Detection**</span></span>
  - <span data-ttu-id="cf250-362">**Protegido por**: **ATP** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="cf250-362">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="cf250-363">**Tag**: filtrar los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="cf250-363">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="cf250-364">Para obtener más información acerca de las etiquetas de usuario, vea [etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-364">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="cf250-365">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="cf250-365">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="cf250-366">Vista de tabla de detalles para el informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="cf250-366">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="cf250-367">Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="cf250-367">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cf250-368">**Ver datos por: información general**: no hay disponible ningún botón **tabla de detalles** de la vista.</span><span class="sxs-lookup"><span data-stu-id="cf250-368">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="cf250-369">**Ver datos por: contenido \> Malware**:</span><span class="sxs-lookup"><span data-stu-id="cf250-369">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="cf250-370">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cf250-370">**Date**</span></span>
  - <span data-ttu-id="cf250-371">**Location**</span><span class="sxs-lookup"><span data-stu-id="cf250-371">**Location**</span></span>
  - <span data-ttu-id="cf250-372">**Dirigida por**</span><span class="sxs-lookup"><span data-stu-id="cf250-372">**Directed by**</span></span>
  - <span data-ttu-id="cf250-373">**Nombre del malware**</span><span class="sxs-lookup"><span data-stu-id="cf250-373">**Malware name**</span></span>

  <span data-ttu-id="cf250-374">Si hace clic en **filtros** en esta vista, puede modificar el informe por **fecha de inicio** y **fecha de finalización**, y por el valor de **detección** .</span><span class="sxs-lookup"><span data-stu-id="cf250-374">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="cf250-375">**Ver datos por: invalidación de mensaje**:</span><span class="sxs-lookup"><span data-stu-id="cf250-375">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="cf250-376">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cf250-376">**Date**</span></span>
  - <span data-ttu-id="cf250-377">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="cf250-377">**Subject**</span></span>
  - <span data-ttu-id="cf250-378">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="cf250-378">**Sender**</span></span>
  - <span data-ttu-id="cf250-379">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="cf250-379">**Recipients**</span></span>
  - <span data-ttu-id="cf250-380">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="cf250-380">**Detected by**</span></span>
  - <span data-ttu-id="cf250-381">**Motivo de la invalidación**</span><span class="sxs-lookup"><span data-stu-id="cf250-381">**Override Reason**</span></span>
  - <span data-ttu-id="cf250-382">**Origen de la intromisión**</span><span class="sxs-lookup"><span data-stu-id="cf250-382">**Source of Compromise**</span></span>
  - <span data-ttu-id="cf250-383">**Tags**</span><span class="sxs-lookup"><span data-stu-id="cf250-383">**Tags**</span></span>

  <span data-ttu-id="cf250-384">Si hace clic en **filtros** en esta vista, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="cf250-384">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cf250-385">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cf250-385">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cf250-386">**Motivo de la invalidación**</span><span class="sxs-lookup"><span data-stu-id="cf250-386">**Override Reason**</span></span>
  - <span data-ttu-id="cf250-387">**Tag**: filtrar los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="cf250-387">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="cf250-388">Para obtener más información acerca de las etiquetas de usuario, vea [etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-388">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="cf250-389">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="cf250-389">**Domain**</span></span>
  - <span data-ttu-id="cf250-390">**Destinatarios** (tenga en cuenta que esta propiedad filterable solo está disponible en la vista de tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="cf250-390">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="cf250-391">Todos los demás gráficos:</span><span class="sxs-lookup"><span data-stu-id="cf250-391">All other charts:</span></span>

  - <span data-ttu-id="cf250-392">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cf250-392">**Date**</span></span>
  - <span data-ttu-id="cf250-393">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="cf250-393">**Subject**</span></span>
  - <span data-ttu-id="cf250-394">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="cf250-394">**Sender**</span></span>
  - <span data-ttu-id="cf250-395">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="cf250-395">**Recipients**</span></span>
  - <span data-ttu-id="cf250-396">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="cf250-396">**Detected by**</span></span>
  - <span data-ttu-id="cf250-397">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="cf250-397">**Delivery Status**</span></span>
  - <span data-ttu-id="cf250-398">**Origen de la intromisión**</span><span class="sxs-lookup"><span data-stu-id="cf250-398">**Source of Compromise**</span></span>
  - <span data-ttu-id="cf250-399">**Tags**</span><span class="sxs-lookup"><span data-stu-id="cf250-399">**Tags**</span></span>

  <span data-ttu-id="cf250-400">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="cf250-400">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cf250-401">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cf250-401">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cf250-402">**Detección**</span><span class="sxs-lookup"><span data-stu-id="cf250-402">**Detection**</span></span>
  - <span data-ttu-id="cf250-403">**Protegido por**: **Defender para Office 365** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="cf250-403">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="cf250-404">**Tag**: filtrar los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="cf250-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="cf250-405">Para obtener más información acerca de las etiquetas de usuario, vea [etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="cf250-406">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="cf250-406">**Domain**</span></span>
  - <span data-ttu-id="cf250-407">**Destinatarios** (tenga en cuenta que esta propiedad filterable solo está disponible en la vista de tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="cf250-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="cf250-408">Informe de malware principal</span><span class="sxs-lookup"><span data-stu-id="cf250-408">Top malware report</span></span>

<span data-ttu-id="cf250-409">El informe de **malware más alto** muestra los distintos tipos de malware detectados por la [protección antimalware en EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-409">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="cf250-410">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **malware principal**.</span><span class="sxs-lookup"><span data-stu-id="cf250-410">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="cf250-411">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="cf250-411">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Widget de malware principal en el panel de informes](../../media/top-malware-report-widget.png)

<span data-ttu-id="cf250-413">Cuando desplaza el puntero sobre una cuña del gráfico circular, puede ver el nombre de un tipo de malware y el número de mensajes que se detectaron como si tuvieran ese malware.</span><span class="sxs-lookup"><span data-stu-id="cf250-413">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Vista de informe de malware superior](../../media/top-malware-report-view.png)

<span data-ttu-id="cf250-415">Si hace clic en **ver tabla de detalles**, puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="cf250-415">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="cf250-416">**Malware principal**</span><span class="sxs-lookup"><span data-stu-id="cf250-416">**Top malware**</span></span>
- <span data-ttu-id="cf250-417">**Count**</span><span class="sxs-lookup"><span data-stu-id="cf250-417">**Count**</span></span>

<span data-ttu-id="cf250-418">Si hace clic en **filtros** en la vista de informe o en la vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="cf250-418">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="cf250-419">Informe de protección contra amenazas de URL</span><span class="sxs-lookup"><span data-stu-id="cf250-419">URL threat protection report</span></span>

<span data-ttu-id="cf250-420">El **Informe de protección contra amenazas de URL** está disponible en Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf250-420">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="cf250-421">Para obtener más información, consulte [Informe de protección contra amenazas de direcciones URL](view-reports-for-atp.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="cf250-421">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="cf250-422">Informe de mensajes notificados por el usuario</span><span class="sxs-lookup"><span data-stu-id="cf250-422">User-reported messages report</span></span>

<span data-ttu-id="cf250-423">El informe de **mensajes de** informes de usuario muestra información sobre los mensajes de correo electrónico que los usuarios han notificado como correo no deseado, intentos de suplantación de identidad (phishing) o correo correcto mediante el [complemento de mensajes de informe](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span><span class="sxs-lookup"><span data-stu-id="cf250-423">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="cf250-424">Hay más detalles disponibles para cada mensaje, incluidos el motivo de la entrega, la excepción de la Directiva de correo no deseado o la regla de flujo de correo configurada para la organización.</span><span class="sxs-lookup"><span data-stu-id="cf250-424">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="cf250-425">Para ver los detalles, seleccione un elemento de la lista de informes de usuarios y, a continuación, vea la información en las pestañas **Resumen** y **detalles** .</span><span class="sxs-lookup"><span data-stu-id="cf250-425">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![El informe mensajes de User-Reported muestra los usuarios que han sido identificados como correo no deseado, no deseados o de suplantación de identidad.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="cf250-427">Para ver este informe, en el [centro de seguridad & cumplimiento](https://protection.office.com), realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cf250-427">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="cf250-428">Vaya a **Threat management** \> **Dashboard** \> **mensajes de los que ha informado el usuario del panel de administración de** amenazas.</span><span class="sxs-lookup"><span data-stu-id="cf250-428">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="cf250-429">Vaya a **Threat management** \> **Review** \> **los mensajes de revisión de administración de amenazas que ha informado el usuario**.</span><span class="sxs-lookup"><span data-stu-id="cf250-429">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![En el centro de seguridad & cumplimiento, seleccione \> \> mensajes notificados por el usuario de revisión de administración de amenazas](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="cf250-431">Para que el informe de mensajes notificados por el usuario funcione correctamente, el **registro de auditoría debe estar activado** para su entorno de Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf250-431">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="cf250-432">Normalmente lo hace alguien que tiene el rol registros de auditoría asignado en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cf250-432">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="cf250-433">Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="cf250-433">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="cf250-434">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="cf250-434">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="cf250-435">Para ver y usar los informes, debe ser miembro del grupo de roles especificado en el centro de seguridad & cumplimiento **y** en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cf250-435">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="cf250-436">En el centro de seguridad & cumplimiento, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="cf250-436">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="cf250-437">-Organization Management-administrador de seguridad (también puede hacerlo en el [centro de administración de Azure Active Directory](https://aad.portal.azure.com) -lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="cf250-437">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="cf250-438">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="cf250-438">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="cf250-439">En Exchange Online, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="cf250-439">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="cf250-440">-Administración de la organización: administración de la organización de solo vista-destinatarios de solo vista-administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cf250-440">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="cf250-441">Para obtener más información, consulte [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) y [Manage role Groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="cf250-441">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="cf250-442">¿Qué ocurre si los informes no muestran datos?</span><span class="sxs-lookup"><span data-stu-id="cf250-442">What if the reports aren't showing data?</span></span>

<span data-ttu-id="cf250-443">Si no ve datos en los informes, compruebe que las directivas estén correctamente configuradas.</span><span class="sxs-lookup"><span data-stu-id="cf250-443">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="cf250-444">Para obtener más información, consulte [proteger contra amenazas](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="cf250-444">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf250-445">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cf250-445">Related topics</span></span>

[<span data-ttu-id="cf250-446">Protección contra correo electrónico no deseado y antimalware en EOP</span><span class="sxs-lookup"><span data-stu-id="cf250-446">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="cf250-447">Informes inteligentes y reportes en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cf250-447">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="cf250-448">Ver informes de flujo de correo en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cf250-448">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="cf250-449">Ver informes para defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="cf250-449">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
