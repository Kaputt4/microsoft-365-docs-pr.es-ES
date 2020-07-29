---
title: Ver informes de flujo de correos en el Centro de seguridad y cumplimiento.
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
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo buscar y usar informes de seguridad de flujo de correo para su organización. Los informes de flujo de correo están disponibles en el centro de seguridad & cumplimiento.
ms.custom: ''
ms.openlocfilehash: e891d9373b169dc01cfd89f114e31b23e1bd8480
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434184"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a><span data-ttu-id="68a0c-104">Ver informes de flujo de correos en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="68a0c-104">View mail flow reports in the Security & Compliance Center</span></span>

<span data-ttu-id="68a0c-105">Además de la [información del flujo de correo](mail-flow-insights-v2.md) que está disponible en el centro de seguridad & cumplimiento, hay disponible una variedad de informes de flujo de correo que le ayudarán a supervisar su organización de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68a0c-105">In addition to the [Mail flow insights](mail-flow-insights-v2.md) that are available in the Security & Compliance Center, a variety of mail flow reports are also available to help you monitor your Microsoft 365 organization.</span></span> <span data-ttu-id="68a0c-106">Si dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en el centro de seguridad & cumplimiento en <https://office.protection.com> visitando el panel de **informes** \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center at <https://office.protection.com> by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="68a0c-107">Para ir directamente al panel informes, Abra <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="68a0c-107">To go directly to the reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Panel de informes en el centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="68a0c-109">Informe de conector</span><span class="sxs-lookup"><span data-stu-id="68a0c-109">Connector report</span></span>

<span data-ttu-id="68a0c-110">El **Informe de conectores** muestra la actividad de flujo de correo en los [conectores entrantes y](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) salientes que están configurados para su organización.</span><span class="sxs-lookup"><span data-stu-id="68a0c-110">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="68a0c-111">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **Informe de conector**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="68a0c-112">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="68a0c-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget de informe de conectores en el panel de informes](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="68a0c-114">Vista informes para el informe de conector</span><span class="sxs-lookup"><span data-stu-id="68a0c-114">Report view for the Connector report</span></span>

<span data-ttu-id="68a0c-115">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="68a0c-115">The following charts are available in report view:</span></span>

- <span data-ttu-id="68a0c-116">**Ver datos por: flujo del correo**: en este gráfico se muestra el número de mensajes entrantes y salientes organizados por:</span><span class="sxs-lookup"><span data-stu-id="68a0c-116">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="68a0c-117">**Total**</span><span class="sxs-lookup"><span data-stu-id="68a0c-117">**Total**</span></span>
  - <span data-ttu-id="68a0c-118">**De Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="68a0c-118">**From the internet without a connector**</span></span>
  - <span data-ttu-id="68a0c-119">**A Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="68a0c-119">**To the internet without a connector**</span></span>
  - <span data-ttu-id="68a0c-120">Un conector específico que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="68a0c-120">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="68a0c-121">Para aislar los datos del gráfico, use el control **Mostrar datos para** para seleccionar una de estas opciones o **todo el flujo de correo**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-121">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Ver los datos por flujo de correo en el informe de conectores](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="68a0c-123">**Ver datos por: uso de TLS**: en este gráfico se muestra el porcentaje de uso de la versión de seguridad de la capa de transporte (TLS) para el flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="68a0c-123">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="68a0c-124">Para aislar los datos del gráfico, use el control **Mostrar datos para** para seleccionar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="68a0c-124">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="68a0c-125">**Todo el flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="68a0c-125">**All mail flow**</span></span>
  - <span data-ttu-id="68a0c-126">**De Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="68a0c-126">**From the internet without a connector**</span></span>
  - <span data-ttu-id="68a0c-127">**A Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="68a0c-127">**To the internet without a connector**</span></span>
  - <span data-ttu-id="68a0c-128">Un conector específico que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="68a0c-128">A specific connector that you've configured.</span></span>

  ![Ver datos por uso de TLS en el informe de conectores](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="68a0c-130">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-130">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="68a0c-131">Vista de tabla de detalles para el informe de conector</span><span class="sxs-lookup"><span data-stu-id="68a0c-131">Details table view for the Connector report</span></span>

<span data-ttu-id="68a0c-132">Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="68a0c-132">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="68a0c-133">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="68a0c-133">**Date**</span></span>
- <span data-ttu-id="68a0c-134">**Dirección y nombre del conector**</span><span class="sxs-lookup"><span data-stu-id="68a0c-134">**Connector direction and name**</span></span>
- <span data-ttu-id="68a0c-135">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="68a0c-135">**Connector type**</span></span>
- <span data-ttu-id="68a0c-136">**¿TLS forzado?**: el valor **true** o **false**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-136">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="68a0c-137">**Sin TLS** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="68a0c-137">**No TLS** (percentage)</span></span>
- <span data-ttu-id="68a0c-138">**TLS 1,0** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="68a0c-138">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="68a0c-139">**TLS 1,1** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="68a0c-139">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="68a0c-140">**TLS 1,2** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="68a0c-140">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="68a0c-141">**Volumen**: el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="68a0c-141">**Volume**: The number of messages.</span></span>

<span data-ttu-id="68a0c-142">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-142">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="68a0c-143">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-143">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="68a0c-144">Informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="68a0c-144">Exchange transport rule report</span></span>

<span data-ttu-id="68a0c-145">El **Informe de reglas de transporte de Exchange** muestra el efecto de las reglas de flujo de correo (también conocidas como reglas de transporte) en los mensajes entrantes y salientes de la organización.</span><span class="sxs-lookup"><span data-stu-id="68a0c-145">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="68a0c-146">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione regla de **transporte de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-146">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="68a0c-147">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="68a0c-147">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget de regla de transporte de Exchange en el panel informes](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="68a0c-149">Vista informes para el informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="68a0c-149">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="68a0c-150">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="68a0c-150">The following charts are available in report view:</span></span>

- <span data-ttu-id="68a0c-151">**Ver datos por: reglas** \> de transporte de Exchange **Desglose por: Dirección: en**este gráfico se muestra el número de mensajes **entrantes** y **salientes** que se vieron afectados por las reglas de transporte.</span><span class="sxs-lookup"><span data-stu-id="68a0c-151">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="68a0c-152">**Ver datos por: reglas** \> de transporte de Exchange **Desglose por: gravedad: en**este gráfico se muestra el número de gravedad **alta** y **mediana**y los mensajes de **gravedad baja** .</span><span class="sxs-lookup"><span data-stu-id="68a0c-152">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="68a0c-153">El nivel de gravedad se establece como una acción en la regla (**auditar esta regla con el nivel de gravedad** o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="68a0c-153">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="68a0c-154">Para obtener más información, vea [acciones de las reglas de flujo de correo en Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="68a0c-154">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="68a0c-155">**Ver datos por: reglas de transporte de Exchange de DLP** \> **Desglose por: Dirección: en**este gráfico se muestra el número de mensajes **entrantes** y **salientes** que se vieron afectados por las reglas de transporte de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="68a0c-155">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="68a0c-156">Puede refinar aún más el gráfico si selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="68a0c-156">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="68a0c-157">**Mostrar datos para: todas las reglas de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="68a0c-157">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="68a0c-158">**Mostrar datos para: usuarios comprometidos**</span><span class="sxs-lookup"><span data-stu-id="68a0c-158">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="68a0c-159">**Mostrar datos para: bajo volumen de contenido detectado Patriot Act de Estados Unidos**</span><span class="sxs-lookup"><span data-stu-id="68a0c-159">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="68a0c-160">**Ver datos por: reglas de transporte de Exchange de DLP** \> **Dividir por: dirección**: esta vista muestra el número de gravedad **alta** y **mediana**y los mensajes de **gravedad baja** que se vieron afectados por las reglas de transporte de DLP.</span><span class="sxs-lookup"><span data-stu-id="68a0c-160">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="68a0c-161">Puede refinar aún más el gráfico si selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="68a0c-161">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="68a0c-162">**Mostrar datos para: todas las reglas de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="68a0c-162">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="68a0c-163">**Mostrar datos para: usuarios comprometidos**</span><span class="sxs-lookup"><span data-stu-id="68a0c-163">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="68a0c-164">**Mostrar datos para: bajo volumen de contenido detectado Patriot Act de Estados Unidos**</span><span class="sxs-lookup"><span data-stu-id="68a0c-164">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="68a0c-165">Si hace clic en **filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros::</span><span class="sxs-lookup"><span data-stu-id="68a0c-165">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="68a0c-166">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="68a0c-166">**Start date** and **End date**</span></span>
- <span data-ttu-id="68a0c-167">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="68a0c-167">Direction values</span></span>
- <span data-ttu-id="68a0c-168">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="68a0c-168">Severity values</span></span>

![Vista de informe en el informe de reglas de transporte de Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="68a0c-170">Vista de tabla de detalles para el informe de regla de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="68a0c-170">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="68a0c-171">Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="68a0c-171">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="68a0c-172">**Ver datos por: reglas de transporte de Exchange**:</span><span class="sxs-lookup"><span data-stu-id="68a0c-172">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="68a0c-173">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="68a0c-173">**Date**</span></span>
  - <span data-ttu-id="68a0c-174">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="68a0c-174">**Transport rule**</span></span>
  - <span data-ttu-id="68a0c-175">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="68a0c-175">**Subject**</span></span>
  - <span data-ttu-id="68a0c-176">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="68a0c-176">**Sender address**</span></span>
  - <span data-ttu-id="68a0c-177">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="68a0c-177">**Recipient address**</span></span>
  - <span data-ttu-id="68a0c-178">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="68a0c-178">**Severity**</span></span>
  - <span data-ttu-id="68a0c-179">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="68a0c-179">**Direction**</span></span>

- <span data-ttu-id="68a0c-180">**Ver datos por: reglas de transporte de DLP de Exchange**:</span><span class="sxs-lookup"><span data-stu-id="68a0c-180">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="68a0c-181">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="68a0c-181">**Date**</span></span>
  - <span data-ttu-id="68a0c-182">**Directiva DLP**</span><span class="sxs-lookup"><span data-stu-id="68a0c-182">**DLP policy**</span></span>
  - <span data-ttu-id="68a0c-183">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="68a0c-183">**Transport rule**</span></span>
  - <span data-ttu-id="68a0c-184">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="68a0c-184">**Subject**</span></span>
  - <span data-ttu-id="68a0c-185">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="68a0c-185">**Sender address**</span></span>
  - <span data-ttu-id="68a0c-186">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="68a0c-186">**Recipient address**</span></span>
  - <span data-ttu-id="68a0c-187">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="68a0c-187">**Severity**</span></span>
  - <span data-ttu-id="68a0c-188">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="68a0c-188">**Direction**</span></span>

<span data-ttu-id="68a0c-189">Si hace clic en **filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="68a0c-189">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="68a0c-190">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="68a0c-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="68a0c-191">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="68a0c-191">Direction values</span></span>
- <span data-ttu-id="68a0c-192">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="68a0c-192">Severity values</span></span>

<span data-ttu-id="68a0c-193">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-193">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="68a0c-194">Reenvío de informes</span><span class="sxs-lookup"><span data-stu-id="68a0c-194">Forwarding report</span></span>

<span data-ttu-id="68a0c-195">El **Informe de reenvío** muestra los mensajes reenviados automáticamente de la organización a dominios externos de los buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="68a0c-195">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="68a0c-196">Los mensajes reenviados pueden suponer un riesgo de seguridad o de cumplimiento, y pueden indicar una cuenta en peligro.</span><span class="sxs-lookup"><span data-stu-id="68a0c-196">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="68a0c-197">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **reenviar Informe**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-197">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="68a0c-198">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="68a0c-198">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Reenvío del widget de informe en el panel informes](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="68a0c-200">Vista informes para el informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="68a0c-200">Report view for the Forwarding report</span></span>

<span data-ttu-id="68a0c-201">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="68a0c-201">The following charts are available in the report view:</span></span>

- <span data-ttu-id="68a0c-202">**Mostrar datos para: métodos de reenvío**: se muestran los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="68a0c-202">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="68a0c-203">**Regla de transporte**: también conocida como [reglas de flujo de correo](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="68a0c-203">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="68a0c-204">**Regla de buzón de correo**: también conocida como reglas de la [bandeja de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="68a0c-204">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vista de métodos de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="68a0c-206">**Mostrar datos de: dominios de reenvío**: esta vista muestra los dominios de destinatario que son los destinos para el reenvío.</span><span class="sxs-lookup"><span data-stu-id="68a0c-206">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vista de dominios de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="68a0c-208">**Mostrar datos para: reenviadores**: se muestran los siguientes reenviadores:</span><span class="sxs-lookup"><span data-stu-id="68a0c-208">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="68a0c-209">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="68a0c-209">**Transport rule**</span></span>
  - <span data-ttu-id="68a0c-210">El buzón de correo que contiene la regla de reenvío de la bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="68a0c-210">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vista de reenvíos en el informe de reenvío](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="68a0c-212">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-212">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="68a0c-213">Vista de tabla de detalles para el informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="68a0c-213">Details table view for the Forwarding report</span></span>

<span data-ttu-id="68a0c-214">Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="68a0c-214">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="68a0c-215">**Reenviadores**: la **regla de transporte** de valor o el buzón que contiene la regla de reenvío de la bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="68a0c-215">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="68a0c-216">**Tipo de reenvío**: regla de **buzón de correo** de valor o regla de **transporte**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-216">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="68a0c-217">**Nombre de destinatario**</span><span class="sxs-lookup"><span data-stu-id="68a0c-217">**Recipient name**</span></span>
- <span data-ttu-id="68a0c-218">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="68a0c-218">**Recipient domain**</span></span>
- <span data-ttu-id="68a0c-219">**Detalles**: este es el valor de GUID de la regla de flujo de correo o el valor RuleIdentity de la regla de bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="68a0c-219">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="68a0c-220">**Count**</span><span class="sxs-lookup"><span data-stu-id="68a0c-220">**Count**</span></span>
- <span data-ttu-id="68a0c-221">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="68a0c-221">**First forward date**</span></span>

<span data-ttu-id="68a0c-222">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-222">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="68a0c-223">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-223">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="68a0c-224">Informe de estado de flujo de notificación</span><span class="sxs-lookup"><span data-stu-id="68a0c-224">Mailflow status report</span></span>

<span data-ttu-id="68a0c-225">El **Informe de estado de flujo** de correo es similar al [Informe de correo electrónico enviado y recibido](#sent-and-received-email-report), con información adicional sobre el correo electrónico permitido o bloqueado en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="68a0c-225">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="68a0c-226">Este es el único informe que contiene información sobre la protección perimetral y muestra la cantidad de correo electrónico que se bloquea antes de que se permita el servicio para su evaluación por parte de Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="68a0c-226">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="68a0c-227">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione informe de **Estado de flujo**de información.</span><span class="sxs-lookup"><span data-stu-id="68a0c-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="68a0c-228">Para ir directamente al **Informe de estado del flujo de correo**, Abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="68a0c-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget de informe de estado de flujo de registros en el panel informes](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="68a0c-230">Tipo de vista para el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="68a0c-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="68a0c-231">Al abrir el informe, la ficha **tipo** se selecciona de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="68a0c-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="68a0c-232">De forma predeterminada, esta vista contiene un gráfico y una tabla de datos que se configura con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="68a0c-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="68a0c-233">**Fecha**: los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="68a0c-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="68a0c-234">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="68a0c-234">**Direction**:</span></span>

  - <span data-ttu-id="68a0c-235">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="68a0c-235">**Inbound**</span></span>
  - <span data-ttu-id="68a0c-236">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="68a0c-236">**Outbound**</span></span>
  - <span data-ttu-id="68a0c-237">**Dentro de la organización** (cuenta por separado de **entrada** y de **salida**)</span><span class="sxs-lookup"><span data-stu-id="68a0c-237">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="68a0c-238">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="68a0c-238">**Type**:</span></span>

  - <span data-ttu-id="68a0c-239">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="68a0c-239">**Good mail**</span></span>
  - <span data-ttu-id="68a0c-240">**Malware**</span><span class="sxs-lookup"><span data-stu-id="68a0c-240">**Malware**</span></span>
  - <span data-ttu-id="68a0c-241">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="68a0c-241">**Spam**</span></span>
  - <span data-ttu-id="68a0c-242">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="68a0c-242">**Edge protection**</span></span>
  - <span data-ttu-id="68a0c-243">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="68a0c-243">**Rule messages**</span></span>
  - <span data-ttu-id="68a0c-244">**Correo de suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="68a0c-244">**Phishing email**</span></span>

<span data-ttu-id="68a0c-245">El gráfico se organiza por los valores de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="68a0c-245">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="68a0c-246">Puede cambiar estos filtros haciendo clic en **filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="68a0c-246">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="68a0c-247">La tabla de datos contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="68a0c-247">The data table contains the following information:</span></span>

- <span data-ttu-id="68a0c-248">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="68a0c-248">**Direction**</span></span>
- <span data-ttu-id="68a0c-249">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="68a0c-249">**Type**</span></span>
- <span data-ttu-id="68a0c-250">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="68a0c-250">**24 hours**</span></span>
- <span data-ttu-id="68a0c-251">**3 días**</span><span class="sxs-lookup"><span data-stu-id="68a0c-251">**3 days**</span></span>
- <span data-ttu-id="68a0c-252">**7 días**</span><span class="sxs-lookup"><span data-stu-id="68a0c-252">**7 days**</span></span>
- <span data-ttu-id="68a0c-253">**15 días**</span><span class="sxs-lookup"><span data-stu-id="68a0c-253">**15 days**</span></span>
- <span data-ttu-id="68a0c-254">**30 días**</span><span class="sxs-lookup"><span data-stu-id="68a0c-254">**30 days**</span></span>

<span data-ttu-id="68a0c-255">Si hace clic en **elegir una categoría para obtener más información**, puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="68a0c-255">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="68a0c-256">**Correo electrónico de suplantación de identidad**: esta selección le lleva al [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="68a0c-256">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="68a0c-257">**Malware en correo electrónico**: esta selección le lleva al [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="68a0c-257">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="68a0c-258">**Detecciones de correo no deseado**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="68a0c-258">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="68a0c-259">**Correo no deseado de Edge bloqueado**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="68a0c-259">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="68a0c-260">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="68a0c-260">**Export**:</span></span>

<span data-ttu-id="68a0c-261">Para la vista de detalles, solo puede exportar datos de un día.</span><span class="sxs-lookup"><span data-stu-id="68a0c-261">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="68a0c-262">Por lo tanto, si desea exportar datos durante 7 días, necesitará hacer 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="68a0c-262">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="68a0c-263">Cada archivo. csv exportado está limitado a 150.000 filas.</span><span class="sxs-lookup"><span data-stu-id="68a0c-263">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="68a0c-264">Si los datos de ese día contienen más de 150.000 filas, se crearán varios archivos. csv.</span><span class="sxs-lookup"><span data-stu-id="68a0c-264">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="68a0c-265">Tipo ver en el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="68a0c-265">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="68a0c-266">Vista de dirección para el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="68a0c-266">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="68a0c-267">Si hace clic en la ficha **Dirección** , se usarán los mismos filtros predeterminados de la vista de **tipos** .</span><span class="sxs-lookup"><span data-stu-id="68a0c-267">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="68a0c-268">El gráfico está organizado por valores de **Dirección** .</span><span class="sxs-lookup"><span data-stu-id="68a0c-268">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="68a0c-269">Puede cambiar estos filtros haciendo clic en **filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="68a0c-269">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="68a0c-270">Se usan los mismos filtros de la vista **tipo** .</span><span class="sxs-lookup"><span data-stu-id="68a0c-270">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="68a0c-271">La tabla de datos contiene la misma información de la vista de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="68a0c-271">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="68a0c-272">El comportamiento seleccionar **una categoría para obtener más información sobre** las selecciones disponibles y el comportamiento es el mismo que el de la vista **tipo** .</span><span class="sxs-lookup"><span data-stu-id="68a0c-272">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="68a0c-273">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="68a0c-273">**Export**:</span></span>

<span data-ttu-id="68a0c-274">Para la vista de detalles, solo puede exportar datos de un día.</span><span class="sxs-lookup"><span data-stu-id="68a0c-274">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="68a0c-275">Por lo tanto, si desea exportar datos durante 7 días, necesitará hacer 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="68a0c-275">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="68a0c-276">Cada archivo. csv exportado está limitado a 150.000 filas.</span><span class="sxs-lookup"><span data-stu-id="68a0c-276">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="68a0c-277">Si los datos de ese día contienen más de 150.000 filas, se crearán varios archivos. csv.</span><span class="sxs-lookup"><span data-stu-id="68a0c-277">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="68a0c-278">Vista de dirección en el informe de estado de flujo de notificación</span><span class="sxs-lookup"><span data-stu-id="68a0c-278">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="68a0c-279">Informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="68a0c-279">Sent and received email report</span></span>

<span data-ttu-id="68a0c-280">El informe de **correo electrónico enviado y recibido** es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas las detecciones de correo no deseado, malware y el correo electrónico identificado como "bueno".</span><span class="sxs-lookup"><span data-stu-id="68a0c-280">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="68a0c-281">La diferencia entre este informe y el [Informe de estado de flujo](#mailflow-status-report) de correos es la siguiente: este informe no incluye datos sobre los mensajes bloqueados por la protección perimetral.</span><span class="sxs-lookup"><span data-stu-id="68a0c-281">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="68a0c-282">La vista agregada y la vista de detalles del informe permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="68a0c-282">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="68a0c-283">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **correo electrónico enviado y recibido**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-283">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="68a0c-284">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="68a0c-284">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget de correo electrónico enviado y recibido en el panel de informes](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="68a0c-286">Vista informes para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="68a0c-286">Report view for the Sent and received email report</span></span>

<span data-ttu-id="68a0c-287">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="68a0c-287">The following charts are available in the report view:</span></span>

- <span data-ttu-id="68a0c-288">**Dividir por: escriba**: el gráfico muestra todas las categorías disponibles:</span><span class="sxs-lookup"><span data-stu-id="68a0c-288">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="68a0c-289">**Total**</span><span class="sxs-lookup"><span data-stu-id="68a0c-289">**Total**</span></span>
  - <span data-ttu-id="68a0c-290">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="68a0c-290">**Good mail**</span></span>
  - <span data-ttu-id="68a0c-291">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="68a0c-291">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="68a0c-292">**Detecciones de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="68a0c-292">**Spam detections**</span></span>
  - <span data-ttu-id="68a0c-293">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="68a0c-293">**Rule messages**</span></span>
  - <span data-ttu-id="68a0c-294">**Malware avanzado** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="68a0c-294">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="68a0c-295">Al pasar el mouse sobre un día (punto de datos) del gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="68a0c-295">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Tipo ver en el informe de correo electrónico enviado y recibido](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="68a0c-297">**Desglose por: dirección**: el gráfico muestra los datos **totales**, **entrantes**y **salientes** .</span><span class="sxs-lookup"><span data-stu-id="68a0c-297">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="68a0c-298">Al pasar el mouse sobre un día (punto de datos) del gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="68a0c-298">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vista de dirección en el informe de correo electrónico enviados y recibidos](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="68a0c-300">**Explorar en profundidad por** \> **Malware (anti-malware)**: esta selección le lleva a las [detecciones de malware en el informe de correo electrónico](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="68a0c-300">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="68a0c-301">**Explorar en profundidad por** \> **Detecciones de correo no deseado)**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="68a0c-301">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="68a0c-302">Si hace clic en **filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="68a0c-302">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="68a0c-303">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="68a0c-303">**Start date** and **End date**</span></span>
- <span data-ttu-id="68a0c-304">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="68a0c-304">Direction values</span></span>
- <span data-ttu-id="68a0c-305">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="68a0c-305">Type values</span></span>

<span data-ttu-id="68a0c-306">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-306">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="68a0c-307">Vista de tabla de detalles para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="68a0c-307">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="68a0c-308">Si hace clic en **ver tabla de detalles** en el cuadro **desglosar por: dirección** o **dividir por:** vista de dirección, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="68a0c-308">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="68a0c-309">**Fecha (UTC)**</span><span class="sxs-lookup"><span data-stu-id="68a0c-309">**Date (UTC)**</span></span>
- <span data-ttu-id="68a0c-310">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="68a0c-310">**Type**</span></span>
- <span data-ttu-id="68a0c-311">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="68a0c-311">**Direction**</span></span>
- <span data-ttu-id="68a0c-312">**Número de mensajes**</span><span class="sxs-lookup"><span data-stu-id="68a0c-312">**Message count**</span></span>

<span data-ttu-id="68a0c-313">Si hace clic en **filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="68a0c-313">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="68a0c-314">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="68a0c-314">**Start date** and **End date**</span></span>
- <span data-ttu-id="68a0c-315">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="68a0c-315">Direction values</span></span>
- <span data-ttu-id="68a0c-316">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="68a0c-316">Type values</span></span>

<span data-ttu-id="68a0c-317">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-317">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="68a0c-318">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="68a0c-318">Top senders and recipients report</span></span>

<span data-ttu-id="68a0c-319">El informe de **remitentes y destinatarios principales** es un gráfico circular que muestra los principales remitentes y destinatarios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="68a0c-319">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="68a0c-320">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **principales remitentes y destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-320">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="68a0c-321">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="68a0c-321">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widgets principales remitentes y destinatarios en el panel informes](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="68a0c-323">Vista informes para los principales informes de remitentes y destinatarios</span><span class="sxs-lookup"><span data-stu-id="68a0c-323">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="68a0c-324">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="68a0c-324">The following charts are available in the report view:</span></span>

- <span data-ttu-id="68a0c-325">**Mostrar datos para los \> remitentes de correo principales**</span><span class="sxs-lookup"><span data-stu-id="68a0c-325">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="68a0c-326">**Mostrar datos para los \> principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="68a0c-326">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="68a0c-327">**Mostrar datos para los \> principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="68a0c-327">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="68a0c-328">**Mostrar datos para \> Destinatarios principales de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="68a0c-328">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="68a0c-329">**Mostrar datos para \> Principales destinatarios de malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="68a0c-329">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="68a0c-330">La composición del gráfico circular cambia en función de estas selecciones.</span><span class="sxs-lookup"><span data-stu-id="68a0c-330">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="68a0c-331">Cuando desplaza el puntero sobre una cuña del gráfico circular, puede ver un recuento de los mensajes enviados o recibidos.</span><span class="sxs-lookup"><span data-stu-id="68a0c-331">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="68a0c-332">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-332">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico circular en la vista de informe en el informe de remitentes y destinatarios principales](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="68a0c-334">Vista de tabla de detalles para el informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="68a0c-334">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="68a0c-335">Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="68a0c-335">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="68a0c-336">**Mostrar datos para los \> remitentes de correo principales**</span><span class="sxs-lookup"><span data-stu-id="68a0c-336">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="68a0c-337">**Principales remitentes de correo**</span><span class="sxs-lookup"><span data-stu-id="68a0c-337">**Top mail senders**</span></span>
  - <span data-ttu-id="68a0c-338">**Count**</span><span class="sxs-lookup"><span data-stu-id="68a0c-338">**Count**</span></span>

- <span data-ttu-id="68a0c-339">**Mostrar datos para los \> principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="68a0c-339">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="68a0c-340">**Destinatarios principales de correo**</span><span class="sxs-lookup"><span data-stu-id="68a0c-340">**Top mail recipients**</span></span>
  - <span data-ttu-id="68a0c-341">**Count**</span><span class="sxs-lookup"><span data-stu-id="68a0c-341">**Count**</span></span>

- <span data-ttu-id="68a0c-342">**Mostrar datos para los \> principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="68a0c-342">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="68a0c-343">**Principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="68a0c-343">**Top spam recipients**</span></span>
  - <span data-ttu-id="68a0c-344">**Count**</span><span class="sxs-lookup"><span data-stu-id="68a0c-344">**Count**</span></span>

- <span data-ttu-id="68a0c-345">**Mostrar datos para \> Destinatarios principales de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="68a0c-345">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="68a0c-346">**Destinatarios principales de malware**</span><span class="sxs-lookup"><span data-stu-id="68a0c-346">**Top malware recipients**</span></span>
  - <span data-ttu-id="68a0c-347">**Count**</span><span class="sxs-lookup"><span data-stu-id="68a0c-347">**Count**</span></span>

- <span data-ttu-id="68a0c-348">**Mostrar datos para \> Principales destinatarios de malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="68a0c-348">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="68a0c-349">**Destinatarios principales de malware (ATP)**</span><span class="sxs-lookup"><span data-stu-id="68a0c-349">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="68a0c-350">**Count**</span><span class="sxs-lookup"><span data-stu-id="68a0c-350">**Count**</span></span>

<span data-ttu-id="68a0c-351">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-351">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="68a0c-352">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="68a0c-352">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="68a0c-353">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="68a0c-353">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="68a0c-354">Para ver y usar los informes, debe ser miembro del grupo de roles especificado en el centro de seguridad & cumplimiento **y** en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="68a0c-354">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="68a0c-355">En el centro de seguridad & cumplimiento, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="68a0c-355">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="68a0c-356">-Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="68a0c-356">-Organization Management</span></span>

  <span data-ttu-id="68a0c-357">-Administrador de seguridad (también puede hacerlo en el [centro de administración de Azure Active Directory](https://aad.portal.azure.com) : lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="68a0c-357">-Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="68a0c-358">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="68a0c-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="68a0c-359">En Exchange Online, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="68a0c-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="68a0c-360">-Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="68a0c-360">-Organization Management</span></span>

  <span data-ttu-id="68a0c-361">-View-Only administración de la organización</span><span class="sxs-lookup"><span data-stu-id="68a0c-361">-View-only Organization Management</span></span>

  <span data-ttu-id="68a0c-362">: Ver solo los destinatarios</span><span class="sxs-lookup"><span data-stu-id="68a0c-362">-View-Only Recipients</span></span>

  <span data-ttu-id="68a0c-363">-Administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="68a0c-363">-Compliance Management</span></span>

<span data-ttu-id="68a0c-364">Para obtener más información, consulte [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) y [Manage role Groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="68a0c-364">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="68a0c-365">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="68a0c-365">Related topics</span></span>

[<span data-ttu-id="68a0c-366">Informes inteligentes y reportes en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="68a0c-366">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="68a0c-367">Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="68a0c-367">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)
