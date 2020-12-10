---
title: Ver los informes de defender para Office 365 en el panel de informes
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Busque y use informes de Microsoft defender para Office 365 en el centro de seguridad & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2818362eea4071430bb2c784ceb0ce0eeb970a79
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615581"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a><span data-ttu-id="1505c-103">Ver los informes de defender para Office 365 en el panel de informes del centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="1505c-103">View Defender for Office 365 reports in the Reports dashboard in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1505c-104">Microsoft defender para Office 365 organizaciones (por ejemplo, suscripciones a Microsoft 365 E5 o Microsoft defender para Office 365 plan 1 o Microsoft defender para Office 365 plan 2 complementos) contienen una variedad de informes relacionados con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="1505c-104">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="1505c-105">Si dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), puede ver estos informes en el centro de seguridad & cumplimiento desde el panel de **informes** \> .</span><span class="sxs-lookup"><span data-stu-id="1505c-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="1505c-106">Para ir directamente al panel informes, Abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="1505c-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Panel informes en el centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="1505c-108">Informe de tipos de archivo de defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1505c-108">Defender for Office 365 file types report</span></span>

<span data-ttu-id="1505c-109">El informe **de la defender para Office 365 del informe de tipos de archivo** muestra el tipo de archivos detectados como malintencionados por [datos adjuntos seguros](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="1505c-109">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="1505c-110">La vista agregada del informe permite 90 días de filtrado, mientras que la vista de detalles solo permite 10 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="1505c-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="1505c-111">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya  al \> **Panel** informes y seleccione **defender para Office 365 tipos de archivo**.</span><span class="sxs-lookup"><span data-stu-id="1505c-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="1505c-112">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="1505c-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Defender para Office 365 widget tipos de archivo en el panel de informes](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="1505c-114">La información de este informe también está disponible en el [Informe de disposición del mensaje de defender para Office 365](#defender-for-office-365-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="1505c-114">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="1505c-115">Vista informes para el informe de tipos de archivo de defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1505c-115">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="1505c-116">Están disponibles las siguientes vistas:</span><span class="sxs-lookup"><span data-stu-id="1505c-116">The following views are available:</span></span>

- <span data-ttu-id="1505c-117">**Ver datos por: archivo**: el gráfico contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="1505c-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="1505c-118">**Datos adjuntos de Excel malintencionados**</span><span class="sxs-lookup"><span data-stu-id="1505c-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="1505c-119">**Datos adjuntos de Flash malintencionados**</span><span class="sxs-lookup"><span data-stu-id="1505c-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="1505c-120">**Datos adjuntos de PDF malintencionados**</span><span class="sxs-lookup"><span data-stu-id="1505c-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="1505c-121">**Datos adjuntos de PowerPoint malintencionados**</span><span class="sxs-lookup"><span data-stu-id="1505c-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="1505c-122">**Direcciones URL malintencionadas**</span><span class="sxs-lookup"><span data-stu-id="1505c-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="1505c-123">**Datos adjuntos de Word malintencionado**</span><span class="sxs-lookup"><span data-stu-id="1505c-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="1505c-124">**Datos adjuntos ejecutables malintencionados**</span><span class="sxs-lookup"><span data-stu-id="1505c-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="1505c-125">**Otros**</span><span class="sxs-lookup"><span data-stu-id="1505c-125">**Others**</span></span>

  <span data-ttu-id="1505c-126">Cuando desplaza el puntero sobre un día concreto (punto de datos), puede ver el desglose de los tipos de archivos malintencionados que se detectaron con [datos adjuntos seguros](atp-safe-attachments.md) y la [protección antimalware en EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="1505c-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Vista de archivo en el informe de tipos de archivo de defender para Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="1505c-128">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="1505c-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1505c-129">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="1505c-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1505c-130">Los mismos valores de tipo de archivo que están visibles en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="1505c-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="1505c-131">**Ver datos por: mensaje**: el gráfico contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="1505c-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="1505c-132">**Bloquear acceso**</span><span class="sxs-lookup"><span data-stu-id="1505c-132">**Block access**</span></span>
  - <span data-ttu-id="1505c-133">**Mensajes reemplazados**</span><span class="sxs-lookup"><span data-stu-id="1505c-133">**Messages replaced**</span></span>
  - <span data-ttu-id="1505c-134">**Mensajes supervisados**</span><span class="sxs-lookup"><span data-stu-id="1505c-134">**Messages monitored**</span></span>
  - <span data-ttu-id="1505c-135">**Reemplazado por la entrega de correo electrónico dinámica**: para obtener más información, consulte [entrega dinámica en las directivas de datos adjuntos seguros](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="1505c-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Vista de mensaje en el informe de tipos de archivo de defender para Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="1505c-137">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="1505c-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1505c-138">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="1505c-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1505c-139">Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor de mensajes adicionales que se **pasan** .</span><span class="sxs-lookup"><span data-stu-id="1505c-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="1505c-140">Vista de tabla de detalles del informe de tipos de archivo de defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1505c-140">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="1505c-141">Si hace clic en **ver tabla de detalles**, el informe proporciona una vista casi en tiempo real de todos los clics que ocurren dentro de la organización durante los últimos 10 días.</span><span class="sxs-lookup"><span data-stu-id="1505c-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="1505c-142">La información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="1505c-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1505c-143">**Ver datos por: archivo**:</span><span class="sxs-lookup"><span data-stu-id="1505c-143">**View data by: File**:</span></span>

  - <span data-ttu-id="1505c-144">**Date**</span><span class="sxs-lookup"><span data-stu-id="1505c-144">**Date**</span></span>
  - <span data-ttu-id="1505c-145">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="1505c-145">**Recipient address**</span></span>
  - <span data-ttu-id="1505c-146">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="1505c-146">**Sender address**</span></span>
  - <span data-ttu-id="1505c-147">**Identificador del mensaje**: disponible en el campo de encabezado del **identificador del mensaje** en el encabezado del mensaje y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="1505c-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="1505c-148">Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observe los corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="1505c-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="1505c-149">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="1505c-149">**File**</span></span>

  <span data-ttu-id="1505c-150">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="1505c-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1505c-151">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="1505c-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1505c-152">Los mismos valores de tipo de archivo que están visibles en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="1505c-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="1505c-153">**Ver datos por: mensaje**:</span><span class="sxs-lookup"><span data-stu-id="1505c-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="1505c-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="1505c-154">**Date**</span></span>
  - <span data-ttu-id="1505c-155">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="1505c-155">**Recipient address**</span></span>
  - <span data-ttu-id="1505c-156">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="1505c-156">**Sender address**</span></span>
  - <span data-ttu-id="1505c-157">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="1505c-157">**Message ID**</span></span>
  - <span data-ttu-id="1505c-158">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="1505c-158">**File**</span></span>
  - <span data-ttu-id="1505c-159">**Subject**</span><span class="sxs-lookup"><span data-stu-id="1505c-159">**Subject**</span></span>

  <span data-ttu-id="1505c-160">Si hace clic en **filtros**, puede modificar los resultados con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="1505c-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="1505c-161">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="1505c-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1505c-162">Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor de mensajes adicionales que se **pasan** .</span><span class="sxs-lookup"><span data-stu-id="1505c-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="1505c-163">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="1505c-163">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="1505c-164">Informe de disposición de mensajes de defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1505c-164">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="1505c-165">El informe de **disposición de mensajes de ATP** muestra las acciones que se tomaron para los mensajes de correo electrónico que se detectaron con contenido malintencionado.</span><span class="sxs-lookup"><span data-stu-id="1505c-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="1505c-166">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya  al \> **Panel** informes y seleccione **defender para Office 365 disposición de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="1505c-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="1505c-167">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="1505c-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Widget de disposición del mensaje de defender para Office 365 en el panel de informes](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="1505c-169">La información de este informe también está disponible en el [Informe de tipos de archivo de defender para Office 365](#defender-for-office-365-file-types-report).</span><span class="sxs-lookup"><span data-stu-id="1505c-169">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="1505c-170">Vista informes del informe de disposición de los mensajes de defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1505c-170">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="1505c-171">Están disponibles las siguientes vistas:</span><span class="sxs-lookup"><span data-stu-id="1505c-171">The following views are available:</span></span>

- <span data-ttu-id="1505c-172">**Ver datos por: mensaje**: el gráfico contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="1505c-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="1505c-173">**Bloquear acceso**</span><span class="sxs-lookup"><span data-stu-id="1505c-173">**Block access**</span></span>
  - <span data-ttu-id="1505c-174">**Mensajes reemplazados**</span><span class="sxs-lookup"><span data-stu-id="1505c-174">**Messages replaced**</span></span>
  - <span data-ttu-id="1505c-175">**Mensajes supervisados**</span><span class="sxs-lookup"><span data-stu-id="1505c-175">**Messages monitored**</span></span>
  - <span data-ttu-id="1505c-176">**Reemplazado por la entrega de correo electrónico dinámica**: para obtener más información, consulte [entrega dinámica en las directivas de datos adjuntos seguros](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="1505c-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Vista de mensaje en el informe de tipos de archivo de defender para Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="1505c-178">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="1505c-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1505c-179">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="1505c-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1505c-180">Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor de mensajes adicionales que se **pasan** .</span><span class="sxs-lookup"><span data-stu-id="1505c-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="1505c-181">**Ver datos por: archivo**: el gráfico contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="1505c-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="1505c-182">**Datos adjuntos de Excel malintencionados**</span><span class="sxs-lookup"><span data-stu-id="1505c-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="1505c-183">**Datos adjuntos de Flash malintencionados**</span><span class="sxs-lookup"><span data-stu-id="1505c-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="1505c-184">**Datos adjuntos de PDF malintencionados**</span><span class="sxs-lookup"><span data-stu-id="1505c-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="1505c-185">**Datos adjuntos de PowerPoint malintencionados**</span><span class="sxs-lookup"><span data-stu-id="1505c-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="1505c-186">**Direcciones URL malintencionadas**</span><span class="sxs-lookup"><span data-stu-id="1505c-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="1505c-187">**Datos adjuntos de Word malintencionado**</span><span class="sxs-lookup"><span data-stu-id="1505c-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="1505c-188">**Datos adjuntos ejecutables malintencionados**</span><span class="sxs-lookup"><span data-stu-id="1505c-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="1505c-189">**Otros**</span><span class="sxs-lookup"><span data-stu-id="1505c-189">**Others**</span></span>

  <span data-ttu-id="1505c-190">Cuando desplaza el puntero sobre un día concreto (punto de datos), puede ver el desglose de los tipos de archivos malintencionados que se detectaron con [datos adjuntos seguros](atp-safe-attachments.md) y la [protección antimalware en EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="1505c-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Vista de archivo en el informe de tipos de archivo de defender para Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="1505c-192">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="1505c-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1505c-193">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="1505c-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1505c-194">Los mismos valores de tipo de archivo que están visibles en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="1505c-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="1505c-195">Vista de tabla de detalles del informe de disposición de los mensajes de defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1505c-195">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="1505c-196">Si hace clic en **ver tabla de detalles**, el informe proporciona una vista casi en tiempo real de todos los clics que ocurren dentro de la organización durante los últimos 10 días.</span><span class="sxs-lookup"><span data-stu-id="1505c-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="1505c-197">La información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="1505c-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1505c-198">**Ver datos por: mensaje**:</span><span class="sxs-lookup"><span data-stu-id="1505c-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="1505c-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="1505c-199">**Date**</span></span>
  - <span data-ttu-id="1505c-200">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="1505c-200">**Recipient address**</span></span>
  - <span data-ttu-id="1505c-201">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="1505c-201">**Sender address**</span></span>
  - <span data-ttu-id="1505c-202">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="1505c-202">**Message ID**</span></span>
  - <span data-ttu-id="1505c-203">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="1505c-203">**File**</span></span>
  - <span data-ttu-id="1505c-204">**Subject**</span><span class="sxs-lookup"><span data-stu-id="1505c-204">**Subject**</span></span>

  <span data-ttu-id="1505c-205">Si hace clic en **filtros**, puede modificar los resultados con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="1505c-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="1505c-206">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="1505c-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1505c-207">Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor de mensajes adicionales que se **pasan** .</span><span class="sxs-lookup"><span data-stu-id="1505c-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="1505c-208">**Ver datos por: archivo**:</span><span class="sxs-lookup"><span data-stu-id="1505c-208">**View data by: File**:</span></span>

  - <span data-ttu-id="1505c-209">**Date**</span><span class="sxs-lookup"><span data-stu-id="1505c-209">**Date**</span></span>
  - <span data-ttu-id="1505c-210">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="1505c-210">**Recipient address**</span></span>
  - <span data-ttu-id="1505c-211">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="1505c-211">**Sender address**</span></span>
  - <span data-ttu-id="1505c-212">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="1505c-212">**Message ID**</span></span>
  - <span data-ttu-id="1505c-213">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="1505c-213">**File**</span></span>

  <span data-ttu-id="1505c-214">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="1505c-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1505c-215">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="1505c-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1505c-216">Los mismos valores de tipo de archivo que están visibles en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="1505c-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="1505c-217">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="1505c-217">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="1505c-218">Informe de latencia de correo</span><span class="sxs-lookup"><span data-stu-id="1505c-218">Mail latency report</span></span>

<span data-ttu-id="1505c-219">El **Informe de latencia de correo** muestra una vista agregada de la entrega de correo y la latencia de detonación experimentada en la organización.</span><span class="sxs-lookup"><span data-stu-id="1505c-219">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="1505c-220">Los tiempos de entrega de correo en el servicio se ven afectados por una serie de factores, y el tiempo de entrega absoluto en segundos no suele ser un buen indicador de éxito o problema.</span><span class="sxs-lookup"><span data-stu-id="1505c-220">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="1505c-221">Una hora de entrega lenta en un día puede considerarse un promedio de tiempo de entrega en otro día o viceversa.</span><span class="sxs-lookup"><span data-stu-id="1505c-221">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="1505c-222">El **Informe de latencia de correo** intenta calificar la entrega de mensajes en función de los datos estadísticos sobre los tiempos de entrega observados de otros mensajes:</span><span class="sxs-lookup"><span data-stu-id="1505c-222">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="1505c-223">**percentil 50**: es la mitad de los tiempos de entrega de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1505c-223">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="1505c-224">Este valor se puede considerar como tiempo medio de entrega.</span><span class="sxs-lookup"><span data-stu-id="1505c-224">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="1505c-225">**nonagésimo percentil**: Esto indica una latencia alta para la entrega de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1505c-225">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="1505c-226">Solo el 10% de los mensajes tardó más que este valor para entregar.</span><span class="sxs-lookup"><span data-stu-id="1505c-226">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="1505c-227">**percentil 99th**: indica la latencia más alta para la entrega de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1505c-227">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="1505c-228">No se incluye la latencia de la red y del cliente.</span><span class="sxs-lookup"><span data-stu-id="1505c-228">Client side and network latency are not included.</span></span>

<span data-ttu-id="1505c-229">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya  al \> **Panel** informes y seleccione informe de **latencia de correo**.</span><span class="sxs-lookup"><span data-stu-id="1505c-229">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mail latency report**.</span></span> <span data-ttu-id="1505c-230">Para ir directamente al informe, Abra <https://protection.office.com/mailLatencyReport?viewid=P50> .</span><span class="sxs-lookup"><span data-stu-id="1505c-230">To go directly to the report, open <https://protection.office.com/mailLatencyReport?viewid=P50>.</span></span>

![Widget de informe de latencia de correo en el panel informes](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="1505c-232">Vista informes para el informe de latencia de correo</span><span class="sxs-lookup"><span data-stu-id="1505c-232">Report view for the Mail latency report</span></span>

<span data-ttu-id="1505c-233">Al abrir el informe, la ficha **percentiles 50** está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1505c-233">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="1505c-234">De forma predeterminada, esta vista contiene un gráfico que está configurado con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="1505c-234">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="1505c-235">**Fecha**: los últimos 7 días</span><span class="sxs-lookup"><span data-stu-id="1505c-235">**Date**: The last 7 days</span></span>
- <span data-ttu-id="1505c-236">**Vista de mensajes**:</span><span class="sxs-lookup"><span data-stu-id="1505c-236">**Message View**:</span></span>
  - <span data-ttu-id="1505c-237">Mensajes detonados</span><span class="sxs-lookup"><span data-stu-id="1505c-237">Detonated messages</span></span>

<span data-ttu-id="1505c-238">Este gráfico muestra los mensajes organizados en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="1505c-238">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="1505c-239">**Latencia de entrega de correo**</span><span class="sxs-lookup"><span data-stu-id="1505c-239">**Mail delivery latency**</span></span>
- <span data-ttu-id="1505c-240">**Latencia de detonación**</span><span class="sxs-lookup"><span data-stu-id="1505c-240">**Detonation latency**</span></span>

<span data-ttu-id="1505c-241">Cuando desplaza el puntero sobre una categoría del gráfico, puede ver un desglose de la latencia en cada categoría.</span><span class="sxs-lookup"><span data-stu-id="1505c-241">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![Informe de latencia de correo](../../media/mail-latency-report.png)

<span data-ttu-id="1505c-243">Si hace clic en **filtrar** en la vista de informe, puede modificar los resultados con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="1505c-243">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1505c-244">Todos los mensajes</span><span class="sxs-lookup"><span data-stu-id="1505c-244">All messages</span></span>
- <span data-ttu-id="1505c-245">Mensajes que contienen datos adjuntos o direcciones URL</span><span class="sxs-lookup"><span data-stu-id="1505c-245">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="1505c-246">Si hace clic en la pestaña **90 percentiles** o la ficha **percentiles de 99th** , se usan los mismos filtros predeterminados de la vista **percentil 50** .</span><span class="sxs-lookup"><span data-stu-id="1505c-246">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="1505c-247">Vista de tabla de detalles para el informe de latencia de correo</span><span class="sxs-lookup"><span data-stu-id="1505c-247">Details table view for the Mail latency report</span></span>

<span data-ttu-id="1505c-248">La siguiente información se muestra en la vista de tabla de detalles:</span><span class="sxs-lookup"><span data-stu-id="1505c-248">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="1505c-249">**Date**</span><span class="sxs-lookup"><span data-stu-id="1505c-249">**Date**</span></span>
- <span data-ttu-id="1505c-250">**Percentiles**</span><span class="sxs-lookup"><span data-stu-id="1505c-250">**Percentiles**</span></span>
- <span data-ttu-id="1505c-251">**Número de mensajes**</span><span class="sxs-lookup"><span data-stu-id="1505c-251">**Message count**</span></span>
- <span data-ttu-id="1505c-252">**Latencia general**</span><span class="sxs-lookup"><span data-stu-id="1505c-252">**Overall latency**</span></span>

![Detalles del informe de latencia de correo](../../media/mail-latency-report-details.png)

<span data-ttu-id="1505c-254">El anterior muestra que el 14 de noviembre la latencia media experimentada para todos los mensajes entregados y detonaciones fue de **108,033** segundos.</span><span class="sxs-lookup"><span data-stu-id="1505c-254">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="1505c-255">La tabla de detalles contiene la misma información en cada pestaña.</span><span class="sxs-lookup"><span data-stu-id="1505c-255">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="1505c-256">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="1505c-256">Threat protection status report</span></span>

<span data-ttu-id="1505c-257">El informe de **Estado de protección contra amenazas** es una vista única que reúne información sobre contenido malintencionado y correo electrónico malintencionado detectado y bloqueado por [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) y Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="1505c-257">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="1505c-258">Para obtener más información, consulte [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="1505c-258">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="1505c-259">Informe de protección contra amenazas de URL</span><span class="sxs-lookup"><span data-stu-id="1505c-259">URL threat protection report</span></span>

<span data-ttu-id="1505c-260">El **Informe de protección contra amenazas de direcciones URL** proporciona vistas de Resumen y tendencias para las amenazas detectadas y las acciones tomadas en los clics de direcciones URL como parte de los [vínculos seguros](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="1505c-260">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="1505c-261">Este informe no tendrá hacer clic en datos de usuarios en los que la Directiva de vínculos seguros aplicada tiene seleccionada la opción no hacer **un seguimiento de los clics del usuario** .</span><span class="sxs-lookup"><span data-stu-id="1505c-261">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="1505c-262">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya a **informes** de \> **Panel** y seleccione **Informe de protección de URL**.</span><span class="sxs-lookup"><span data-stu-id="1505c-262">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="1505c-263">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="1505c-263">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widget de informe de protección de URL en el panel informes](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="1505c-265">Se trata de un *Informe de tendencias de protección*, lo que significa que los datos representan tendencias en un conjunto de datos más grande.</span><span class="sxs-lookup"><span data-stu-id="1505c-265">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="1505c-266">Como resultado, los datos de la vista de agregado no están disponibles en tiempo real aquí, pero los datos de la vista de tabla de detalles son, por lo que es posible que vea una ligera diferencia entre las dos vistas.</span><span class="sxs-lookup"><span data-stu-id="1505c-266">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="1505c-267">Vista informes para el informe de protección contra amenazas de direcciones URL</span><span class="sxs-lookup"><span data-stu-id="1505c-267">Report view for the URL threat protection report</span></span>

<span data-ttu-id="1505c-268">El informe de **protección contra amenazas de direcciones URL** tiene dos vistas agregadas que se actualizan una vez cada cuatro horas que muestra datos para los últimos 90 días:</span><span class="sxs-lookup"><span data-stu-id="1505c-268">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="1505c-269">**Hacer clic en dirección URL acción de protección**: muestra el número de clics de direcciones URL por parte de los usuarios de la organización y los resultados del clic:</span><span class="sxs-lookup"><span data-stu-id="1505c-269">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="1505c-270">**Bloqueado** (se ha bloqueado al usuario para que navegue a la dirección URL)</span><span class="sxs-lookup"><span data-stu-id="1505c-270">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="1505c-271">**Bloqueado y clic en**</span><span class="sxs-lookup"><span data-stu-id="1505c-271">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="1505c-272">**Clic durante el examen**</span><span class="sxs-lookup"><span data-stu-id="1505c-272">**Clicked through during scan**</span></span>

  <span data-ttu-id="1505c-273">Un clic indica que el usuario ha acpulsado a través de la página de bloque al sitio Web malintencionado (los administradores pueden deshabilitar el clic en las directivas de vínculos a prueba de errores).</span><span class="sxs-lookup"><span data-stu-id="1505c-273">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="1505c-274">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="1505c-274">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1505c-275">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="1505c-275">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1505c-276">Las acciones de clic en protección disponibles, más el valor **permitido** (el usuario tuvo permiso para navegar a la dirección URL).</span><span class="sxs-lookup"><span data-stu-id="1505c-276">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![Vista de dirección URL haga clic en acción de protección en el informe de protección contra amenazas URL](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="1505c-278">**Dirección URL haga clic en por aplicación**: muestra el número de clics de direcciones URL por aplicaciones que admiten vínculos seguros:</span><span class="sxs-lookup"><span data-stu-id="1505c-278">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="1505c-279">**Cliente de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="1505c-279">**Email client**</span></span>
  - <span data-ttu-id="1505c-280">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="1505c-280">**PowerPoint**</span></span>
  - <span data-ttu-id="1505c-281">**Word**</span><span class="sxs-lookup"><span data-stu-id="1505c-281">**Word**</span></span>
  - <span data-ttu-id="1505c-282">**Excel**</span><span class="sxs-lookup"><span data-stu-id="1505c-282">**Excel**</span></span>
  - <span data-ttu-id="1505c-283">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="1505c-283">**OneNote**</span></span>
  - <span data-ttu-id="1505c-284">**Visio**</span><span class="sxs-lookup"><span data-stu-id="1505c-284">**Visio**</span></span>
  - <span data-ttu-id="1505c-285">**Teams**</span><span class="sxs-lookup"><span data-stu-id="1505c-285">**Teams**</span></span>
  - <span data-ttu-id="1505c-286">**Otros**</span><span class="sxs-lookup"><span data-stu-id="1505c-286">**Other**</span></span>

  <span data-ttu-id="1505c-287">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="1505c-287">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1505c-288">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="1505c-288">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1505c-289">Las aplicaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="1505c-289">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="1505c-290">Vista de tabla de detalles para el informe de protección contra amenazas de direcciones URL</span><span class="sxs-lookup"><span data-stu-id="1505c-290">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="1505c-291">Si hace clic en **ver tabla de detalles**, el informe proporciona una vista casi en tiempo real de todos los clics que ocurren dentro de la organización en los últimos 7 días con los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="1505c-291">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="1505c-292">**Haga clic en hora**</span><span class="sxs-lookup"><span data-stu-id="1505c-292">**Click time**</span></span>
- <span data-ttu-id="1505c-293">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="1505c-293">**User**</span></span>
- <span data-ttu-id="1505c-294">**URL**</span><span class="sxs-lookup"><span data-stu-id="1505c-294">**URL**</span></span>
- <span data-ttu-id="1505c-295">**Action**</span><span class="sxs-lookup"><span data-stu-id="1505c-295">**Action**</span></span>
- <span data-ttu-id="1505c-296">**App**</span><span class="sxs-lookup"><span data-stu-id="1505c-296">**App**</span></span>

<span data-ttu-id="1505c-297">Si hace clic en **filtros** en la vista de tabla de detalles, puede filtrar por los mismos criterios que en la vista de informe y también por **dominios** o **destinatarios** separados por comas.</span><span class="sxs-lookup"><span data-stu-id="1505c-297">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="1505c-298">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="1505c-298">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="1505c-299">Informes adicionales para ver</span><span class="sxs-lookup"><span data-stu-id="1505c-299">Additional reports to view</span></span>

<span data-ttu-id="1505c-300">Además de los informes descritos en este tema, hay varios otros informes disponibles, tal como se describe en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="1505c-300">In addition to the reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="1505c-301">Informe</span><span class="sxs-lookup"><span data-stu-id="1505c-301">Report</span></span>|<span data-ttu-id="1505c-302">Tema</span><span class="sxs-lookup"><span data-stu-id="1505c-302">Topic</span></span>|
|---|---|
|<span data-ttu-id="1505c-303">**Explorer** (Microsoft defender para Office 365 plan 2) o **detecciones en tiempo real** (microsoft defender para Office 365 plan 1)</span><span class="sxs-lookup"><span data-stu-id="1505c-303">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="1505c-304">Explorador de amenazas (y detecciones en tiempo real)</span><span class="sxs-lookup"><span data-stu-id="1505c-304">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="1505c-305">**Informes de seguridad de correo electrónico**, como el informe de remitentes y destinatarios principales, el informe de correo falsificado y el informe de detecciones de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="1505c-305">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="1505c-306">Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="1505c-306">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="1505c-307">**Informes de flujo de correo**, como el informe de reenvío, el informe de estado de flujo de correo y el informe de remitentes y destinatarios principales.</span><span class="sxs-lookup"><span data-stu-id="1505c-307">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="1505c-308">Ver informes de flujo de correo en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="1505c-308">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="1505c-309">**Seguimiento de dirección URL para vínculos seguros** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="1505c-309">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="1505c-310">El resultado de este cmdlet muestra los resultados de las acciones de vínculos a prueba de errores en los últimos siete días.</span><span class="sxs-lookup"><span data-stu-id="1505c-310">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="1505c-311">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="1505c-311">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="1505c-312">**Resultados del tráfico de correo para EOP y Microsoft defender para Office 365** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="1505c-312">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="1505c-313">El resultado de este cmdlet contiene información sobre el dominio, la fecha, el tipo de evento, la dirección, la acción y el recuento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1505c-313">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="1505c-314">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="1505c-314">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="1505c-315">**Informes de detalles de correo para EOP y defender para Office 365 DETECTIONS** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="1505c-315">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="1505c-316">El resultado de este cmdlet contiene detalles sobre archivos malintencionados o direcciones URL, intentos de suplantación de identidad (phishing), suplantación y otras amenazas potenciales en el correo electrónico o los archivos.</span><span class="sxs-lookup"><span data-stu-id="1505c-316">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="1505c-317">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="1505c-317">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="1505c-318">¿Qué permisos se necesitan para ver los informes de defender para Office 365?</span><span class="sxs-lookup"><span data-stu-id="1505c-318">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="1505c-319">Para poder ver y usar los informes descritos en este tema, debe pertenecer a uno de los siguientes grupos de roles en el centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="1505c-319">In order to view and use the reports described in this topic, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="1505c-320">**Administración de organizaciones**</span><span class="sxs-lookup"><span data-stu-id="1505c-320">**Organization Management**</span></span>
- <span data-ttu-id="1505c-321">**Administrador de seguridad**</span><span class="sxs-lookup"><span data-stu-id="1505c-321">**Security Administrator**</span></span>
- <span data-ttu-id="1505c-322">**Lector de seguridad**</span><span class="sxs-lookup"><span data-stu-id="1505c-322">**Security Reader**</span></span>
- <span data-ttu-id="1505c-323">**Lector global**</span><span class="sxs-lookup"><span data-stu-id="1505c-323">**Global Reader**</span></span>

<span data-ttu-id="1505c-324">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1505c-324">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="1505c-325">**Nota**: agregar usuarios al rol correspondiente de Azure Active Directory en el centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el centro de seguridad & cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1505c-325">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1505c-326">Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="1505c-326">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="1505c-327">¿Qué ocurre si los informes no muestran datos?</span><span class="sxs-lookup"><span data-stu-id="1505c-327">What if the reports aren't showing data?</span></span>

<span data-ttu-id="1505c-328">Si no ve datos en sus informes de defender para Office 365, compruebe que las directivas están configuradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="1505c-328">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="1505c-329">La organización debe tener directivas de [vínculos seguros](set-up-atp-safe-links-policies.md) y [las directivas de datos adjuntos seguros](set-up-atp-safe-attachments-policies.md) definidas para que defender para Office 365 esté en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1505c-329">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="1505c-330">Consulte también [protección contra correo no deseado y antimalware](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="1505c-330">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1505c-331">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1505c-331">Related topics</span></span>

[<span data-ttu-id="1505c-332">Informes inteligentes y reportes en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="1505c-332">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="1505c-333">Permisos de funciones (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1505c-333">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
