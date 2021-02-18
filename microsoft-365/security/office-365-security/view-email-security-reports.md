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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo buscar y usar informes de seguridad de correo electrónico para su organización. Los informes de seguridad de correo electrónico están disponibles en el Centro de & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f6d9f149c9e1c71532018e6b43a6e9e31eb04607
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290804"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="cd49c-104">Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cd49c-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cd49c-105">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="cd49c-105">**Applies to**</span></span>
- [<span data-ttu-id="cd49c-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cd49c-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cd49c-107">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="cd49c-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="cd49c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd49c-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="cd49c-109">Hay varios informes disponibles en el Centro de seguridad y cumplimiento de [&](https://protection.office.com) para ayudarle a ver cómo protegen su organización las características de seguridad de correo electrónico, como el correo no deseado, el malware y las características de cifrado de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cd49c-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="cd49c-110">Si tiene los permisos [necesarios,](#what-permissions-are-needed-to-view-these-reports)puede ver estos informes en el Centro  de seguridad & Cumplimiento yendo al Panel \> **de informes.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="cd49c-111">Para ir directamente al panel Informes, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="cd49c-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Panel informes en el Centro de & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="cd49c-113">Informe de usuarios comprometidos</span><span class="sxs-lookup"><span data-stu-id="cd49c-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="cd49c-114">Este informe está disponible en organizaciones de Microsoft 365 con buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cd49c-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="cd49c-115">No está disponible en organizaciones independientes de Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="cd49c-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="cd49c-116">El **informe de usuarios comprometidos** muestra el número  de  cuentas de usuario que se marcaron como sospechosas o restringidas en los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="cd49c-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="cd49c-117">Las cuentas de cualquiera de estos estados son problemáticas o incluso están en peligro.</span><span class="sxs-lookup"><span data-stu-id="cd49c-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="cd49c-118">Con el uso frecuente, puede usar el informe para detectar picos e incluso tendencias en cuentas sospechosas o restringidas.</span><span class="sxs-lookup"><span data-stu-id="cd49c-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="cd49c-119">Para obtener más información acerca de los usuarios comprometidos, consulte [Responder a una cuenta de correo electrónico en peligro.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Usuarios comprometidos en el panel informes](../../media/compromised-users-report-widget.png)

<span data-ttu-id="cd49c-121">La vista de agregado muestra los datos de los últimos 90 días y la vista de detalles muestra los datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="cd49c-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="cd49c-122">Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de \>  informes y seleccione **Usuarios comprometidos.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="cd49c-123">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="cd49c-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="cd49c-124">Puede filtrar el gráfico y la  tabla de detalles haciendo clic en Filtros y seleccionando uno o varios de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="cd49c-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="cd49c-125">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cd49c-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="cd49c-126">**Sospechoso:** la cuenta de usuario ha enviado un correo electrónico sospechoso y corre el riesgo de que se le restringa el envío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="cd49c-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="cd49c-127">**Restringido:** se ha restringido el envío de correo electrónico a la cuenta de usuario debido a patrones altamente sospechosos.</span><span class="sxs-lookup"><span data-stu-id="cd49c-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Vista de informe en el informe de usuarios comprometidos](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="cd49c-129">Si hace clic **en Ver tabla de detalles,** puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="cd49c-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="cd49c-130">**Hora de creación**</span><span class="sxs-lookup"><span data-stu-id="cd49c-130">**Creation time**</span></span>
- <span data-ttu-id="cd49c-131">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="cd49c-131">**User ID**</span></span>
- <span data-ttu-id="cd49c-132">**Acción**</span><span class="sxs-lookup"><span data-stu-id="cd49c-132">**Action**</span></span>

<span data-ttu-id="cd49c-133">Para volver a la vista informe, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="cd49c-134">Informe de cifrado</span><span class="sxs-lookup"><span data-stu-id="cd49c-134">Encryption report</span></span>

<span data-ttu-id="cd49c-135">El **informe de cifrado** está disponible en EOP (suscripciones con buzones en Exchange Online o EOP independiente sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="cd49c-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="cd49c-136">El equipo de seguridad de su organización puede usar la información de este informe para identificar patrones y aplicar o ajustar directivas de forma proactiva para mensajes de correo electrónico confidenciales.</span><span class="sxs-lookup"><span data-stu-id="cd49c-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="cd49c-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cd49c-137">For example:</span></span>

- <span data-ttu-id="cd49c-138">Si ve un gran número de mensajes de correo electrónico cifrados por los usuarios, es posible que desee agregar una directiva de cifrado para automatizar el cifrado en determinados casos de uso.</span><span class="sxs-lookup"><span data-stu-id="cd49c-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="cd49c-139">Para obtener más información, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Microsoft 365.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="cd49c-140">Si tiene varias plantillas de cifrado disponibles, pero nadie las usa, puede explorar si los usuarios necesitan formación de características.</span><span class="sxs-lookup"><span data-stu-id="cd49c-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="cd49c-141">La vista de agregado permite el filtrado de los últimos 90 días, mientras que la vista de detalles permite el filtrado durante 10 días.</span><span class="sxs-lookup"><span data-stu-id="cd49c-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="cd49c-142">Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de \>  informes y seleccione Informe **de cifrado.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="cd49c-143">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="cd49c-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="cd49c-144">Para obtener más información sobre el cifrado, consulte [Cifrado de correo electrónico en Microsoft 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="cd49c-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="cd49c-145">Vista de informe para el informe de cifrado</span><span class="sxs-lookup"><span data-stu-id="cd49c-145">Report view for the Encryption report</span></span>

<span data-ttu-id="cd49c-146">Puede usar los siguientes filtros en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="cd49c-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="cd49c-147">**Ver datos por: Informe de cifrado de mensajes** y Dividir **por: Método de cifrado**: Están disponibles los siguientes métodos de cifrado:</span><span class="sxs-lookup"><span data-stu-id="cd49c-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="cd49c-148">**Cifrado por usuario**</span><span class="sxs-lookup"><span data-stu-id="cd49c-148">**Encryption by user**</span></span>
  - <span data-ttu-id="cd49c-149">**Cifrado por directiva**</span><span class="sxs-lookup"><span data-stu-id="cd49c-149">**Encryption by policy**</span></span>

  <span data-ttu-id="cd49c-150">Si hace clic **en Filtros,** puede modificar el gráfico con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd49c-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="cd49c-151">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cd49c-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cd49c-152">Método de cifrado.</span><span class="sxs-lookup"><span data-stu-id="cd49c-152">Encryption method.</span></span>
  - <span data-ttu-id="cd49c-153">Plantilla de cifrado.</span><span class="sxs-lookup"><span data-stu-id="cd49c-153">Encryption template.</span></span>

- <span data-ttu-id="cd49c-154">**Ver datos por: Informe de cifrado de mensajes** y Dividir **por: Plantilla de cifrado:** Están disponibles los siguientes métodos de cifrado:</span><span class="sxs-lookup"><span data-stu-id="cd49c-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="cd49c-155">**No reenviar**</span><span class="sxs-lookup"><span data-stu-id="cd49c-155">**Do not forward**</span></span>
  - <span data-ttu-id="cd49c-156">**Cifrar solo**</span><span class="sxs-lookup"><span data-stu-id="cd49c-156">**Encrypt only**</span></span>
  - <span data-ttu-id="cd49c-157">**OME anterior**</span><span class="sxs-lookup"><span data-stu-id="cd49c-157">**OME previous**</span></span>
  - <span data-ttu-id="cd49c-158">**Personalizados**</span><span class="sxs-lookup"><span data-stu-id="cd49c-158">**Custom**</span></span>

  <span data-ttu-id="cd49c-159">Si hace clic **en Filtros,** puede modificar el gráfico con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd49c-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="cd49c-160">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cd49c-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cd49c-161">Método de cifrado</span><span class="sxs-lookup"><span data-stu-id="cd49c-161">Encryption method</span></span>
  - <span data-ttu-id="cd49c-162">Plantilla de cifrado</span><span class="sxs-lookup"><span data-stu-id="cd49c-162">Encryption template</span></span>

- <span data-ttu-id="cd49c-163">**Ver datos por: principales 5** dominios de destinatarios: esta vista muestra un gráfico circular con recuentos de mensajes enviados para los 5 dominios de destinatarios principales.</span><span class="sxs-lookup"><span data-stu-id="cd49c-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="cd49c-164">Si hace clic **en Filtros,** puede seleccionar una **fecha de inicio y** una fecha de **finalización.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="cd49c-165">Vista de tabla de detalles para el informe de cifrado</span><span class="sxs-lookup"><span data-stu-id="cd49c-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="cd49c-166">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="cd49c-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cd49c-167">**Dividir por: Método de cifrado o** Dividir **por: Plantilla de cifrado**: Se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cd49c-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="cd49c-168">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cd49c-168">**Date**</span></span>
  - <span data-ttu-id="cd49c-169">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="cd49c-169">**Sender address**</span></span>
  - <span data-ttu-id="cd49c-170">**Plantilla de cifrado**</span><span class="sxs-lookup"><span data-stu-id="cd49c-170">**Encryption template**</span></span>
  - <span data-ttu-id="cd49c-171">**Método de cifrado**</span><span class="sxs-lookup"><span data-stu-id="cd49c-171">**Encryption method**</span></span>
  - <span data-ttu-id="cd49c-172">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="cd49c-172">**Recipient address**</span></span>
  - <span data-ttu-id="cd49c-173">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="cd49c-173">**Subject**</span></span>

- <span data-ttu-id="cd49c-174">**Ver datos por: los 5 dominios de destinatarios principales:**</span><span class="sxs-lookup"><span data-stu-id="cd49c-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="cd49c-175">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cd49c-175">**Date**</span></span>
  - <span data-ttu-id="cd49c-176">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="cd49c-176">**Recipient domain**</span></span>
  - <span data-ttu-id="cd49c-177">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="cd49c-177">**Message count**</span></span>

<span data-ttu-id="cd49c-178">Si hace clic **en Filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd49c-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cd49c-179">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cd49c-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="cd49c-180">Método de cifrado</span><span class="sxs-lookup"><span data-stu-id="cd49c-180">Encryption method</span></span>
- <span data-ttu-id="cd49c-181">Plantilla de cifrado</span><span class="sxs-lookup"><span data-stu-id="cd49c-181">Encryption template</span></span>

<span data-ttu-id="cd49c-182">Para volver a la vista informe, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="cd49c-183">Informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="cd49c-183">Mailflow status report</span></span>

<span data-ttu-id="cd49c-184">El **informe de estado de flujo de** correo contiene información sobre malware, correo no deseado, suplantación de identidad y mensajes bloqueados perimetrales.</span><span class="sxs-lookup"><span data-stu-id="cd49c-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="cd49c-185">Para obtener más información, vea [el informe de estado de flujo de correo.](view-mail-flow-reports.md#mailflow-status-report)</span><span class="sxs-lookup"><span data-stu-id="cd49c-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="cd49c-186">Detecciones de malware en el informe de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="cd49c-186">Malware detections in email report</span></span>

<span data-ttu-id="cd49c-187">Las detecciones de malware en el informe de correo electrónico muestran información sobre las detecciones de malware en los mensajes de correo electrónico entrantes y **salientes** (malware detectado por Exchange Online Protection o EOP).</span><span class="sxs-lookup"><span data-stu-id="cd49c-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="cd49c-188">Para obtener más información acerca de la protección contra malware en EOP, vea [Protección antimalware en EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="cd49c-189">El filtro de vista agregado permite 90 días, mientras que el filtro de tabla de detalles solo permite 10 días.</span><span class="sxs-lookup"><span data-stu-id="cd49c-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="cd49c-190">Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione \>  Detecciones de malware por correo **electrónico.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="cd49c-191">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="cd49c-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Detecciones de malware en el widget correo electrónico en el panel informes](../../media/malware-detections-widget.png)

<span data-ttu-id="cd49c-193">Puede filtrar el gráfico y la tabla de detalles haciendo clic en **Filtros** y seleccionando:</span><span class="sxs-lookup"><span data-stu-id="cd49c-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="cd49c-194">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cd49c-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="cd49c-195">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="cd49c-195">**Inbound**</span></span>
- <span data-ttu-id="cd49c-196">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="cd49c-196">**Outbound**</span></span>

![Vista de informe en el informe de detección de malware en el correo electrónico](../../media/malware-detections-report-view.png)

<span data-ttu-id="cd49c-198">Si hace clic **en Ver tabla de detalles,** puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="cd49c-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="cd49c-199">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cd49c-199">**Date**</span></span>
- <span data-ttu-id="cd49c-200">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="cd49c-200">**Sender address**</span></span>
- <span data-ttu-id="cd49c-201">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="cd49c-201">**Recipient address**</span></span>
- <span data-ttu-id="cd49c-202">**Id. de** mensaje: disponible en el **campo de encabezado Id.** de mensaje en el encabezado del mensaje y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="cd49c-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="cd49c-203">Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (tenga en cuenta los corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="cd49c-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="cd49c-204">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="cd49c-204">**Subject**</span></span>
- <span data-ttu-id="cd49c-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="cd49c-205">**Filename**</span></span>
- <span data-ttu-id="cd49c-206">**Nombre de malware**</span><span class="sxs-lookup"><span data-stu-id="cd49c-206">**Malware name**</span></span>

<span data-ttu-id="cd49c-207">Para volver a la vista informe, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="cd49c-208">Informe de latencia de correo</span><span class="sxs-lookup"><span data-stu-id="cd49c-208">Mail latency report</span></span>

<span data-ttu-id="cd49c-209">El **informe de latencia de correo** contiene información sobre la latencia de entrega y detonación de correo experimentada en la organización.</span><span class="sxs-lookup"><span data-stu-id="cd49c-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="cd49c-210">Para obtener más información, vea [el informe de latencia de correo.](view-reports-for-atp.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="cd49c-210">For more information, see [Mail latency report](view-reports-for-atp.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="cd49c-211">Informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="cd49c-211">Sent and received email report</span></span>

<span data-ttu-id="cd49c-212">El **informe de correo electrónico enviado** y recibido contiene información sobre malware, correo no deseado, reglas de flujo de correo (también conocidas como reglas de transporte) y detecciones avanzadas de malware después de que el correo electrónico entre en el servicio.</span><span class="sxs-lookup"><span data-stu-id="cd49c-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="cd49c-213">Para obtener más información, vea [El informe de correo electrónico enviado y recibido.](view-mail-flow-reports.md#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="cd49c-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="cd49c-214">Informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="cd49c-214">Spam detections report</span></span>

<span data-ttu-id="cd49c-215">El **informe de detecciones de** correo no deseado muestra los mensajes de correo no deseado bloqueados por EOP.</span><span class="sxs-lookup"><span data-stu-id="cd49c-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="cd49c-216">Los mensajes se cuentan individualmente, no por destinatario.</span><span class="sxs-lookup"><span data-stu-id="cd49c-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="cd49c-217">Por ejemplo, si el mismo mensaje de correo no deseado se envió a 100 destinatarios de su organización, cuenta como un mensaje.</span><span class="sxs-lookup"><span data-stu-id="cd49c-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="cd49c-218">La vista de agregado permite el filtrado de 90 días, mientras que la tabla de detalles permite el filtrado de 10 días.</span><span class="sxs-lookup"><span data-stu-id="cd49c-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="cd49c-219">Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Detecciones \>  de correo **no deseado.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="cd49c-220">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="cd49c-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Widget Detecciones de correo no deseado en el panel Informes](../../media/spam-detections-report-widget.png)

<span data-ttu-id="cd49c-222">Para obtener más información acerca de la protección contra correo no deseado, vea [Protección contra correo no deseado en EOP.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="cd49c-223">Vista de informe del informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="cd49c-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="cd49c-224">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="cd49c-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="cd49c-225">**Dividir por: Acción:** se muestran los siguientes tipos de evento:</span><span class="sxs-lookup"><span data-stu-id="cd49c-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="cd49c-226">**Contenido de correo no deseado filtrado**</span><span class="sxs-lookup"><span data-stu-id="cd49c-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="cd49c-227">**Bloqueo de IP de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="cd49c-227">**Spam IP block**</span></span>
  - <span data-ttu-id="cd49c-228">**Bloqueo de sobre de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="cd49c-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="cd49c-229">**Filtro DBEB de correo no deseado:** bloqueo perimetral basado en directorios (DBEB)</span><span class="sxs-lookup"><span data-stu-id="cd49c-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="cd49c-230">Al mantener el puntero sobre un día (punto de datos) en el gráfico, puede ver cuántos elementos se bloquearon ese día, así como cómo se clasifican esos elementos.</span><span class="sxs-lookup"><span data-stu-id="cd49c-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Vista de acción en el informe de detecciones de correo no deseado](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="cd49c-232">**Dividir por: Dirección:** se muestran las siguientes direcciones:</span><span class="sxs-lookup"><span data-stu-id="cd49c-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="cd49c-233">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="cd49c-233">**Inbound**</span></span>
  - <span data-ttu-id="cd49c-234">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="cd49c-234">**Outbound**</span></span>

  ![Vista de dirección en el informe de detecciones de correo no deseado](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="cd49c-236">Si hace clic **en Filtros** en una vista de informe, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd49c-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cd49c-237">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cd49c-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="cd49c-238">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="cd49c-238">Direction values</span></span>
- <span data-ttu-id="cd49c-239">Valores de tipo de evento</span><span class="sxs-lookup"><span data-stu-id="cd49c-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="cd49c-240">Vista de tabla de detalles del informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="cd49c-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="cd49c-241">Si hace clic **en Ver tabla de detalles en** cualquier vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cd49c-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="cd49c-242">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cd49c-242">**Date**</span></span>
- <span data-ttu-id="cd49c-243">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="cd49c-243">**Sender address**</span></span>
- <span data-ttu-id="cd49c-244">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="cd49c-244">**Recipient address**</span></span>
- <span data-ttu-id="cd49c-245">**Tipo de evento**</span><span class="sxs-lookup"><span data-stu-id="cd49c-245">**Event type**</span></span>
- <span data-ttu-id="cd49c-246">**Acción**</span><span class="sxs-lookup"><span data-stu-id="cd49c-246">**Action**</span></span>
- <span data-ttu-id="cd49c-247">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="cd49c-247">**Subject**</span></span>

<span data-ttu-id="cd49c-248">Si hace clic **en Filtros** en una tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd49c-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cd49c-249">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cd49c-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="cd49c-250">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="cd49c-250">Direction values</span></span>
- <span data-ttu-id="cd49c-251">Valores de tipo de evento</span><span class="sxs-lookup"><span data-stu-id="cd49c-251">Event type values</span></span>

<span data-ttu-id="cd49c-252">Para volver a la vista informe, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="cd49c-253">Informe de detecciones de suplantación de seguridad</span><span class="sxs-lookup"><span data-stu-id="cd49c-253">Spoof detections report</span></span>

<span data-ttu-id="cd49c-254">El **informe de** detecciones de suplantación muestra cuántos mensajes de correo de suplantación de seguridad se detectaron y cuáles se consideraron "buenos" (correo de suplantación de seguridad realizado por motivos comerciales legítimos).</span><span class="sxs-lookup"><span data-stu-id="cd49c-254">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="cd49c-255">Para obtener más información acerca de la suplantación de nombre, vea Protección contra la suplantación [en EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-255">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="cd49c-256">La vista de agregado del informe permite 90 días de filtrado, mientras que la vista de detalles solo permite diez días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="cd49c-256">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="cd49c-257">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y \>  seleccione **Detecciones de suplantación de seguridad.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-257">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="cd49c-258">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="cd49c-258">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Widget Detecciones de suplantación de seguridad en el panel informes](../../media/spoof-detections-widget.png)

<span data-ttu-id="cd49c-260">Al pasar el puntero sobre un día (punto de datos) en el gráfico, puede ver cuántos mensajes de correo de suplantación de voz se enviaron.</span><span class="sxs-lookup"><span data-stu-id="cd49c-260">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="cd49c-261">Puede filtrar el gráfico y la  tabla de detalles haciendo clic en Filtros y seleccionando uno o varios de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="cd49c-261">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="cd49c-262">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cd49c-262">**Start date** and **End date**</span></span>

- <span data-ttu-id="cd49c-263">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="cd49c-263">**Good mail**</span></span>

- <span data-ttu-id="cd49c-264">**Detectado como correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="cd49c-264">**Caught as spam**</span></span>

![Vista de informe en el informe de detecciones de suplantación de seguridad](../../media/spoof-detections-report-view.png)

<span data-ttu-id="cd49c-266">Si hace clic **en Ver tabla de detalles,** puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="cd49c-266">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="cd49c-267">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cd49c-267">**Date**</span></span>
- <span data-ttu-id="cd49c-268">**Remitente suplantado**</span><span class="sxs-lookup"><span data-stu-id="cd49c-268">**Spoofed sender**</span></span>
- <span data-ttu-id="cd49c-269">**Remitente verdadero**</span><span class="sxs-lookup"><span data-stu-id="cd49c-269">**True sender**</span></span>
- <span data-ttu-id="cd49c-270">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="cd49c-270">**Sender IP**</span></span>
- <span data-ttu-id="cd49c-271">**Acción**</span><span class="sxs-lookup"><span data-stu-id="cd49c-271">**Action**</span></span>
- <span data-ttu-id="cd49c-272">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="cd49c-272">**Message count**</span></span>

<span data-ttu-id="cd49c-273">Para volver a la vista informe, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-273">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="cd49c-274">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="cd49c-274">Threat protection status report</span></span>

<span data-ttu-id="cd49c-275">El **informe de estado de** protección contra amenazas está disponible en EOP y Microsoft Defender para Office 365; sin embargo, los informes contienen datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="cd49c-275">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="cd49c-276">Por ejemplo, los clientes de EOP pueden ver información sobre el malware detectado en el correo electrónico, pero no información sobre archivos malintencionados detectados por datos adjuntos seguros para [SharePoint, OneDrive](atp-for-spo-odb-and-teams.md)y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd49c-276">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="cd49c-277">El informe proporciona el recuento de mensajes de correo electrónico con contenido malintencionado, como archivos o direcciones de sitio web (DIRECCIONES URL) bloqueadas por el [](atp-safe-attachments.md)motor antimalware, purga automática de cero horas [(ZAP)](zero-hour-auto-purge.md)y características de Defender para Office 365 como vínculos [seguros,](atp-safe-links.md)datos adjuntos seguros y [antiphishing.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-277">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="cd49c-278">Puede usar esta información para identificar tendencias o determinar si las directivas de la organización necesitan ajustes.</span><span class="sxs-lookup"><span data-stu-id="cd49c-278">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="cd49c-279">**Nota:** Es importante comprender que si se envía un mensaje a cinco destinatarios, lo contamos como cinco mensajes diferentes y no un mensaje.</span><span class="sxs-lookup"><span data-stu-id="cd49c-279">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="cd49c-280">Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Estado de protección \>  contra **amenazas.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-280">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="cd49c-281">Para ir directamente al informe, abra una de las siguientes direcciones URL:</span><span class="sxs-lookup"><span data-stu-id="cd49c-281">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="cd49c-282">Microsoft Defender para Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="cd49c-282">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="cd49c-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="cd49c-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Widget Estado de protección contra amenazas en el panel informes](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="cd49c-285">De forma predeterminada, el gráfico muestra los datos de los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="cd49c-285">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="cd49c-286">Si hace clic **en Filtros,** puede seleccionar un intervalo de fechas de 90 días (las suscripciones de prueba podrían estar limitadas a 30 días).</span><span class="sxs-lookup"><span data-stu-id="cd49c-286">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="cd49c-287">La vista de tabla de detalles permite filtrar durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="cd49c-287">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="cd49c-288">Vista de informe del informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="cd49c-288">Report view for the Threat protection status report</span></span>

<span data-ttu-id="cd49c-289">Están disponibles las siguientes vistas:</span><span class="sxs-lookup"><span data-stu-id="cd49c-289">The following views are available:</span></span>

- <span data-ttu-id="cd49c-290">**Ver datos por: Información general:** se muestra la siguiente información de detección:</span><span class="sxs-lookup"><span data-stu-id="cd49c-290">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="cd49c-291">**Malware de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="cd49c-291">**Email malware**</span></span>
  - <span data-ttu-id="cd49c-292">**Suplantación de identidad de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="cd49c-292">**Email phish**</span></span>
  - <span data-ttu-id="cd49c-293">**Malware de contenido**</span><span class="sxs-lookup"><span data-stu-id="cd49c-293">**Content malware**</span></span>

  ![Vista general en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="cd49c-295">**Ver datos por: Contenido \> Malware**<sup>1:</sup>se muestra la siguiente información para organizaciones de Microsoft Defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="cd49c-295">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="cd49c-296">**Motor antimalware:** archivos malintencionados detectados en SharePoint, OneDrive y Microsoft Teams mediante la detección de virus integrada [en Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="cd49c-296">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="cd49c-297">**Detonación de archivos:** archivos malintencionados detectados por datos adjuntos seguros [para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cd49c-297">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

  ![Vista de malware de contenido en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="cd49c-299">**Ver datos por: Invalidación de** mensaje: se muestra la siguiente información de motivo de invalidación:</span><span class="sxs-lookup"><span data-stu-id="cd49c-299">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="cd49c-300">**Skip local**</span><span class="sxs-lookup"><span data-stu-id="cd49c-300">**On-premises skip**</span></span>
  - <span data-ttu-id="cd49c-301">**Ip permitido**</span><span class="sxs-lookup"><span data-stu-id="cd49c-301">**IP Allow**</span></span>
  - <span data-ttu-id="cd49c-302">**Regla de flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="cd49c-302">**Mail flow rule**</span></span>
  - <span data-ttu-id="cd49c-303">**Remitente permitido**</span><span class="sxs-lookup"><span data-stu-id="cd49c-303">**Sender allow**</span></span>
  - <span data-ttu-id="cd49c-304">**Dominios permitidos**</span><span class="sxs-lookup"><span data-stu-id="cd49c-304">**Domain allow**</span></span>
  - <span data-ttu-id="cd49c-305">**ZAP no habilitado**</span><span class="sxs-lookup"><span data-stu-id="cd49c-305">**ZAP not enabled**</span></span>
  - <span data-ttu-id="cd49c-306">**Carpeta de correo no deseado no habilitada**</span><span class="sxs-lookup"><span data-stu-id="cd49c-306">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="cd49c-307">**Remitente seguro de usuario**</span><span class="sxs-lookup"><span data-stu-id="cd49c-307">**User Safe Sender**</span></span>
  - <span data-ttu-id="cd49c-308">**Dominio seguro de usuario**</span><span class="sxs-lookup"><span data-stu-id="cd49c-308">**User Safe Domain**</span></span>

  ![Vista de invalidación de mensajes en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="cd49c-310">**Dividir por: Tecnología de detección** y **Ver datos por: Correo \> electrónico suplantación** de identidad : Se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cd49c-310">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="cd49c-311">**Reputación** de la dirección URL generada por ATP <sup>1:</sup>reputación de url malintencionada generada desde Defender para detonaciones de Office 365 en otros clientes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cd49c-311">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="cd49c-312">**Filtro de suplantación de** identidad avanzado: señales de suplantación de identidad basadas en el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="cd49c-312">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="cd49c-313">**Anti-spoof - Error de DMARC:** error de autenticación de DMARC en mensajes.</span><span class="sxs-lookup"><span data-stu-id="cd49c-313">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="cd49c-314">**Anti-spoof - dentro de la organización:** el remitente está intentando suplantación de identidad del dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="cd49c-314">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="cd49c-315">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span><span class="sxs-lookup"><span data-stu-id="cd49c-315">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="cd49c-316">**Suplantación de marca:** suplantación de marcas conocidas basada en remitentes.</span><span class="sxs-lookup"><span data-stu-id="cd49c-316">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="cd49c-317">**Suplantación de dominio**<sup>1:</sup>suplantación de dominios que el cliente posee o define.</span><span class="sxs-lookup"><span data-stu-id="cd49c-317">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="cd49c-318">**Reputación de la dirección URL de EOP:** reputación de la dirección URL malintencionada.</span><span class="sxs-lookup"><span data-stu-id="cd49c-318">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="cd49c-319">**Filtro de suplantación de** identidad general: señales de suplantación de identidad basadas en reglas de analista.</span><span class="sxs-lookup"><span data-stu-id="cd49c-319">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="cd49c-320">**Otros**</span><span class="sxs-lookup"><span data-stu-id="cd49c-320">**Others**</span></span>
  - <span data-ttu-id="cd49c-321">**Phish ZAP**<sup>2</sup>: Purga automática de cero horas de mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="cd49c-321">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="cd49c-322">**Detonación de dirección URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cd49c-322">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="cd49c-323">**Suplantación de usuario**<sup>1:</sup>suplantación de usuarios definida por el administrador o aprendida a través de la inteligencia de buzones.</span><span class="sxs-lookup"><span data-stu-id="cd49c-323">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Vista de tecnología de detección para correo electrónico de suplantación de identidad en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="cd49c-325">**Dividir por: Tecnología de detección** y **Ver datos por: Malware de \> correo** electrónico: se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cd49c-325">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="cd49c-326">**Reputación de archivo generada por ATP**<sup>1:</sup>toda la reputación de archivos malintencionados generada por Defender para detonaciones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd49c-326">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="cd49c-327">**Motor antimalware**<sup>1:</sup>Detección de motores antimalware.</span><span class="sxs-lookup"><span data-stu-id="cd49c-327">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="cd49c-328">Bloque de tipo de archivo de directiva **antimalware:** se trata de mensajes de correo electrónico filtrados debido al tipo de archivo malintencionado identificado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cd49c-328">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="cd49c-329">**Detonación de archivos**<sup>1:</sup>Detección por datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="cd49c-329">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="cd49c-330">**Reputación de archivos malintencionados**</span><span class="sxs-lookup"><span data-stu-id="cd49c-330">**Malicious file reputation**</span></span>
  - <span data-ttu-id="cd49c-331">**Malware ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cd49c-331">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="cd49c-332">**Otros**</span><span class="sxs-lookup"><span data-stu-id="cd49c-332">**Others**</span></span>

  ![Vista de tecnología de detección de malware en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="cd49c-334">**Dividir por: Tipo de directiva** y Ver datos por: Correo electrónico **\> Phish** o Ver datos **por: \> Malware** de correo electrónico: Se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cd49c-334">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="cd49c-335">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="cd49c-335">**Anti-malware**</span></span>
  - <span data-ttu-id="cd49c-336">**Datos adjuntos**<sup>seguros 1</sup></span><span class="sxs-lookup"><span data-stu-id="cd49c-336">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="cd49c-337">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="cd49c-337">**Anti-phish**</span></span>
  - <span data-ttu-id="cd49c-338">**Contra correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="cd49c-338">**Anti-spam**</span></span>
  - <span data-ttu-id="cd49c-339">**Regla de flujo de** correo (también conocida como regla de transporte)</span><span class="sxs-lookup"><span data-stu-id="cd49c-339">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="cd49c-340">**Otros**</span><span class="sxs-lookup"><span data-stu-id="cd49c-340">**Others**</span></span>

  ![Vista de tipo de directiva para correo electrónico de suplantación de identidad en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="cd49c-342">**Dividir por: Estado de** entrega y Ver datos por: Correo electrónico **\> suplantación** de identidad o ver datos **por: \> Malware** de correo electrónico : Se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cd49c-342">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="cd49c-343">**Error en la entrega**</span><span class="sxs-lookup"><span data-stu-id="cd49c-343">**Delivery failed**</span></span>
  - <span data-ttu-id="cd49c-344">**Dropped**</span><span class="sxs-lookup"><span data-stu-id="cd49c-344">**Dropped**</span></span>
  - <span data-ttu-id="cd49c-345">**Reenviado**</span><span class="sxs-lookup"><span data-stu-id="cd49c-345">**Forwarded**</span></span>
  - <span data-ttu-id="cd49c-346">**Buzón hospedado: carpeta personalizada**</span><span class="sxs-lookup"><span data-stu-id="cd49c-346">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="cd49c-347">**Buzón hospedado: elementos eliminados**</span><span class="sxs-lookup"><span data-stu-id="cd49c-347">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="cd49c-348">**Buzón hospedado: Bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="cd49c-348">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="cd49c-349">**Buzón hospedado: correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="cd49c-349">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="cd49c-350">**Servidor local: entregado**</span><span class="sxs-lookup"><span data-stu-id="cd49c-350">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="cd49c-351">**Cuarentena**</span><span class="sxs-lookup"><span data-stu-id="cd49c-351">**Quarantine**</span></span>

  ![Vista de estado de entrega para correo electrónico de suplantación de identidad en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="cd49c-353"><sup>1 Defender</sup> solo para Office 365</span><span class="sxs-lookup"><span data-stu-id="cd49c-353"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="cd49c-354"><sup>2</sup> Purga automática de cero horas (ZAP) no está disponible en EOP independiente (solo funciona en buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="cd49c-354"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="cd49c-355">Si hace clic **en Filtros,** los filtros disponibles dependen del gráfico que estuviera viendo:</span><span class="sxs-lookup"><span data-stu-id="cd49c-355">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cd49c-356">Para **ver datos por: Malware de \>** contenido, puede modificar el informe por fecha **de** inicio **y** fecha de finalización, y el valor **de** detección.</span><span class="sxs-lookup"><span data-stu-id="cd49c-356">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="cd49c-357">Para **ver datos mediante: Invalidación de** mensaje, puede modificar el informe con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd49c-357">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cd49c-358">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cd49c-358">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cd49c-359">**Motivo de invalidación**</span><span class="sxs-lookup"><span data-stu-id="cd49c-359">**Override Reason**</span></span>
  - <span data-ttu-id="cd49c-360">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se haya aplicado la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="cd49c-360">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="cd49c-361">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-361">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="cd49c-362">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="cd49c-362">**Domain**</span></span>

- <span data-ttu-id="cd49c-363">Para todas las demás vistas, puede modificar el informe con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd49c-363">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cd49c-364">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cd49c-364">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cd49c-365">**Detección**</span><span class="sxs-lookup"><span data-stu-id="cd49c-365">**Detection**</span></span>
  - <span data-ttu-id="cd49c-366">**Protegido por:** **ATP** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="cd49c-366">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="cd49c-367">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se haya aplicado la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="cd49c-367">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="cd49c-368">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-368">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="cd49c-369">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="cd49c-369">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="cd49c-370">Vista de tabla de detalles del informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="cd49c-370">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="cd49c-371">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="cd49c-371">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cd49c-372">**Ver datos por: Información general:** no hay ningún botón **de tabla de detalles** de vista disponible.</span><span class="sxs-lookup"><span data-stu-id="cd49c-372">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="cd49c-373">**Ver datos por: Contenido \> Malware:**</span><span class="sxs-lookup"><span data-stu-id="cd49c-373">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="cd49c-374">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cd49c-374">**Date**</span></span>
  - <span data-ttu-id="cd49c-375">**Location**</span><span class="sxs-lookup"><span data-stu-id="cd49c-375">**Location**</span></span>
  - <span data-ttu-id="cd49c-376">**Dirigida por**</span><span class="sxs-lookup"><span data-stu-id="cd49c-376">**Directed by**</span></span>
  - <span data-ttu-id="cd49c-377">**Nombre de malware**</span><span class="sxs-lookup"><span data-stu-id="cd49c-377">**Malware name**</span></span>

  <span data-ttu-id="cd49c-378">Si hace clic **en Filtros** en esta vista, puede modificar el informe por fecha de inicio **y** **fecha** de finalización, y el valor **Detección.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-378">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="cd49c-379">**Ver datos por: Invalidación de mensaje:**</span><span class="sxs-lookup"><span data-stu-id="cd49c-379">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="cd49c-380">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cd49c-380">**Date**</span></span>
  - <span data-ttu-id="cd49c-381">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="cd49c-381">**Subject**</span></span>
  - <span data-ttu-id="cd49c-382">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="cd49c-382">**Sender**</span></span>
  - <span data-ttu-id="cd49c-383">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="cd49c-383">**Recipients**</span></span>
  - <span data-ttu-id="cd49c-384">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="cd49c-384">**Detected by**</span></span>
  - <span data-ttu-id="cd49c-385">**Motivo de invalidación**</span><span class="sxs-lookup"><span data-stu-id="cd49c-385">**Override Reason**</span></span>
  - <span data-ttu-id="cd49c-386">**Origen de peligro**</span><span class="sxs-lookup"><span data-stu-id="cd49c-386">**Source of Compromise**</span></span>
  - <span data-ttu-id="cd49c-387">**Tags**</span><span class="sxs-lookup"><span data-stu-id="cd49c-387">**Tags**</span></span>

  <span data-ttu-id="cd49c-388">Si hace clic **en Filtros** en esta vista, puede modificar el informe con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd49c-388">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cd49c-389">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cd49c-389">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cd49c-390">**Motivo de invalidación**</span><span class="sxs-lookup"><span data-stu-id="cd49c-390">**Override Reason**</span></span>
  - <span data-ttu-id="cd49c-391">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se haya aplicado la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="cd49c-391">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="cd49c-392">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-392">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="cd49c-393">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="cd49c-393">**Domain**</span></span>
  - <span data-ttu-id="cd49c-394">**Destinatarios** (Tenga en cuenta que esta propiedad que se puede filtrar solo está disponible en la vista de tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="cd49c-394">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="cd49c-395">Todos los demás gráficos:</span><span class="sxs-lookup"><span data-stu-id="cd49c-395">All other charts:</span></span>

  - <span data-ttu-id="cd49c-396">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="cd49c-396">**Date**</span></span>
  - <span data-ttu-id="cd49c-397">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="cd49c-397">**Subject**</span></span>
  - <span data-ttu-id="cd49c-398">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="cd49c-398">**Sender**</span></span>
  - <span data-ttu-id="cd49c-399">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="cd49c-399">**Recipients**</span></span>
  - <span data-ttu-id="cd49c-400">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="cd49c-400">**Detected by**</span></span>
  - <span data-ttu-id="cd49c-401">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="cd49c-401">**Delivery Status**</span></span>
  - <span data-ttu-id="cd49c-402">**Origen de peligro**</span><span class="sxs-lookup"><span data-stu-id="cd49c-402">**Source of Compromise**</span></span>
  - <span data-ttu-id="cd49c-403">**Tags**</span><span class="sxs-lookup"><span data-stu-id="cd49c-403">**Tags**</span></span>

  <span data-ttu-id="cd49c-404">Si hace clic **en Filtros,** puede modificar el informe con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd49c-404">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cd49c-405">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="cd49c-405">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cd49c-406">**Detección**</span><span class="sxs-lookup"><span data-stu-id="cd49c-406">**Detection**</span></span>
  - <span data-ttu-id="cd49c-407">**Protegido por**: **Defender para Office 365** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="cd49c-407">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="cd49c-408">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se haya aplicado la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="cd49c-408">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="cd49c-409">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-409">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="cd49c-410">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="cd49c-410">**Domain**</span></span>
  - <span data-ttu-id="cd49c-411">**Destinatarios** (Tenga en cuenta que esta propiedad que se puede filtrar solo está disponible en la vista de tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="cd49c-411">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="cd49c-412">Informe de malware principal</span><span class="sxs-lookup"><span data-stu-id="cd49c-412">Top malware report</span></span>

<span data-ttu-id="cd49c-413">El **informe de malware** superior muestra los distintos tipos de malware detectados por la protección [antimalware en EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-413">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="cd49c-414">Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de \>  informes y seleccione **Malware superior.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-414">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="cd49c-415">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="cd49c-415">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Widget De malware superior en el panel informes](../../media/top-malware-report-widget.png)

<span data-ttu-id="cd49c-417">Al pasar el puntero sobre una malla en el gráfico circular, puede ver el nombre de un tipo de malware y cuántos mensajes se detectaron como malware.</span><span class="sxs-lookup"><span data-stu-id="cd49c-417">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Vista de informe de malware superior](../../media/top-malware-report-view.png)

<span data-ttu-id="cd49c-419">Si hace clic **en Ver tabla de detalles,** puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="cd49c-419">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="cd49c-420">**Malware principal**</span><span class="sxs-lookup"><span data-stu-id="cd49c-420">**Top malware**</span></span>
- <span data-ttu-id="cd49c-421">**Count**</span><span class="sxs-lookup"><span data-stu-id="cd49c-421">**Count**</span></span>

<span data-ttu-id="cd49c-422">Si hace clic **en Filtros en** la vista informe o en la vista tabla de detalles, puede especificar un intervalo de fechas con fecha **de** inicio y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-422">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="cd49c-423">Informe de protección contra amenazas de URL</span><span class="sxs-lookup"><span data-stu-id="cd49c-423">URL threat protection report</span></span>

<span data-ttu-id="cd49c-424">El **informe de protección contra amenazas de** url está disponible en Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd49c-424">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="cd49c-425">Para obtener más información, vea el [informe de protección contra amenazas de url.](view-reports-for-atp.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="cd49c-425">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="cd49c-426">Informe de mensajes notificados por el usuario</span><span class="sxs-lookup"><span data-stu-id="cd49c-426">User-reported messages report</span></span>

<span data-ttu-id="cd49c-427">El  informe de mensajes notificados por el usuario muestra información sobre los mensajes de [](enable-the-report-message-add-in.md) correo electrónico que los usuarios han notificado como correo no deseado, intentos de suplantación de identidad o correo electrónico bueno mediante el complemento Informar de mensaje o El complemento de suplantación de identidad de [informe.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-427">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="cd49c-428">Los detalles están disponibles para cada mensaje, incluido el motivo de la entrega, como una excepción de directiva de correo no deseado o una regla de flujo de correo configurada para su organización.</span><span class="sxs-lookup"><span data-stu-id="cd49c-428">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="cd49c-429">Para ver detalles, seleccione un elemento en la lista de  informes de usuario y, a continuación, vea la información en las pestañas **Resumen** y Detalles.</span><span class="sxs-lookup"><span data-stu-id="cd49c-429">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![El User-Reported mensajes de correo electrónico muestra los mensajes que los usuarios etiquetan como correo no deseado, no como correo no deseado o intentos de suplantación de identidad.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="cd49c-431">Para ver este informe, en el Centro de & [cumplimiento,](https://protection.office.com)realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cd49c-431">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="cd49c-432">Vaya a Mensajes **del panel de administración** \> **de** \> **amenazas notificados por el usuario.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-432">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="cd49c-433">Vaya a **Administración de amenazas** \> **Revisar** \> **mensajes notificados por el usuario.**</span><span class="sxs-lookup"><span data-stu-id="cd49c-433">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![En el Centro de seguridad & cumplimiento, elija Administración de amenazas \> Revisar \> mensajes notificados por el usuario](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="cd49c-435">Para que el informe de mensajes notificados  por el usuario funcione correctamente, el registro de auditoría debe estar activado para su entorno de Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd49c-435">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="cd49c-436">Esto lo suele hacer alguien que tiene el rol Registros de auditoría asignado en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cd49c-436">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="cd49c-437">Para obtener más información, vea Activar o desactivar la búsqueda del registro de auditoría [de Microsoft 365.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-437">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="cd49c-438">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="cd49c-438">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="cd49c-439">Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="cd49c-439">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="cd49c-440">**Administración de organizaciones**</span><span class="sxs-lookup"><span data-stu-id="cd49c-440">**Organization Management**</span></span>
- <span data-ttu-id="cd49c-441">**Administrador de seguridad**</span><span class="sxs-lookup"><span data-stu-id="cd49c-441">**Security Administrator**</span></span>
- <span data-ttu-id="cd49c-442">**Lector de seguridad**</span><span class="sxs-lookup"><span data-stu-id="cd49c-442">**Security Reader**</span></span>
- <span data-ttu-id="cd49c-443">**Lector global**</span><span class="sxs-lookup"><span data-stu-id="cd49c-443">**Global Reader**</span></span>

<span data-ttu-id="cd49c-444">Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="cd49c-444">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="cd49c-445">**Nota:** agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft  365 proporciona a los usuarios los permisos necesarios en el Centro de seguridad & Cumplimiento y permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cd49c-445">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cd49c-446">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cd49c-446">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="cd49c-447">¿Qué ocurre si los informes no muestran datos?</span><span class="sxs-lookup"><span data-stu-id="cd49c-447">What if the reports aren't showing data?</span></span>

<span data-ttu-id="cd49c-448">Si no ve datos en los informes, compruebe que las directivas están configuradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="cd49c-448">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="cd49c-449">Para obtener más información, vea [Proteger contra amenazas.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="cd49c-449">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cd49c-450">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cd49c-450">Related topics</span></span>

[<span data-ttu-id="cd49c-451">Protección contra correo electrónico no deseado y antimalware en EOP</span><span class="sxs-lookup"><span data-stu-id="cd49c-451">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="cd49c-452">Informes inteligentes y reportes en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cd49c-452">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="cd49c-453">Ver informes de flujo de correo en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cd49c-453">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="cd49c-454">Ver informes de Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="cd49c-454">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
