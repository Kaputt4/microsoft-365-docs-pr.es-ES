---
title: Ver informes de flujo de correo en el panel de informes
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
description: Los administradores pueden obtener información sobre los informes de flujo de correo que están disponibles en el panel informes del centro de seguridad & cumplimiento.
ms.custom: ''
ms.openlocfilehash: 98b27497b758a202ccbb741f6cb10e4ec65570e9
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814519"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="125e0-103">Ver informes de flujo de correo en el panel informes del centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="125e0-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="125e0-104">Además de los informes de flujo de correo que están disponibles en el [panel del flujo de correo](mail-flow-insights-v2.md) en el centro de seguridad & cumplimiento, hay disponible una variedad de informes de flujo de correo adicionales en el panel de informes para ayudarle a supervisar su organización de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="125e0-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="125e0-105">Si dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en el [centro de seguridad & cumplimiento](https://office.protection.com) desde el panel de **informes** \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="125e0-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="125e0-106">Para ir directamente al panel informes, Abra <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="125e0-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Panel de informes en el centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="125e0-108">Informe de conector</span><span class="sxs-lookup"><span data-stu-id="125e0-108">Connector report</span></span>

<span data-ttu-id="125e0-109">El **Informe de conectores** muestra la actividad de flujo de correo en los [conectores entrantes y](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) salientes que están configurados para su organización.</span><span class="sxs-lookup"><span data-stu-id="125e0-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="125e0-110">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **Informe de conector**.</span><span class="sxs-lookup"><span data-stu-id="125e0-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="125e0-111">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="125e0-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget de informe de conectores en el panel de informes](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="125e0-113">Vista informes para el informe de conector</span><span class="sxs-lookup"><span data-stu-id="125e0-113">Report view for the Connector report</span></span>

<span data-ttu-id="125e0-114">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="125e0-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="125e0-115">**Ver datos por: flujo del correo**: en este gráfico se muestra el número de mensajes entrantes y salientes organizados por:</span><span class="sxs-lookup"><span data-stu-id="125e0-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="125e0-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="125e0-116">**Total**</span></span>
  - <span data-ttu-id="125e0-117">**De Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="125e0-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="125e0-118">**A Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="125e0-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="125e0-119">Un conector específico que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="125e0-119">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="125e0-120">Para aislar los datos del gráfico, use el control **Mostrar datos para** para seleccionar una de estas opciones o **todo el flujo de correo**.</span><span class="sxs-lookup"><span data-stu-id="125e0-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Ver los datos por flujo de correo en el informe de conectores](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="125e0-122">**Ver datos por: uso de TLS**: en este gráfico se muestra el porcentaje de uso de la versión de seguridad de la capa de transporte (TLS) para el flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="125e0-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="125e0-123">Para aislar los datos del gráfico, use el control **Mostrar datos para** para seleccionar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="125e0-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="125e0-124">**Todo el flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="125e0-124">**All mail flow**</span></span>
  - <span data-ttu-id="125e0-125">**De Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="125e0-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="125e0-126">**A Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="125e0-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="125e0-127">Un conector específico que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="125e0-127">A specific connector that you've configured.</span></span>

  ![Ver datos por uso de TLS en el informe de conectores](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="125e0-129">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="125e0-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="125e0-130">Vista de tabla de detalles para el informe de conector</span><span class="sxs-lookup"><span data-stu-id="125e0-130">Details table view for the Connector report</span></span>

<span data-ttu-id="125e0-131">Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="125e0-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="125e0-132">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="125e0-132">**Date**</span></span>
- <span data-ttu-id="125e0-133">**Dirección y nombre del conector**</span><span class="sxs-lookup"><span data-stu-id="125e0-133">**Connector direction and name**</span></span>
- <span data-ttu-id="125e0-134">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="125e0-134">**Connector type**</span></span>
- <span data-ttu-id="125e0-135">**¿TLS forzado?**: el valor **true** o **false**.</span><span class="sxs-lookup"><span data-stu-id="125e0-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="125e0-136">**Sin TLS** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="125e0-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="125e0-137">**TLS 1,0** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="125e0-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="125e0-138">**TLS 1,1** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="125e0-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="125e0-139">**TLS 1,2** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="125e0-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="125e0-140">**Volumen**: el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="125e0-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="125e0-141">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="125e0-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="125e0-142">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="125e0-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="125e0-143">Informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="125e0-143">Exchange transport rule report</span></span>

<span data-ttu-id="125e0-144">El **Informe de reglas de transporte de Exchange** muestra el efecto de las reglas de flujo de correo (también conocidas como reglas de transporte) en los mensajes entrantes y salientes de la organización.</span><span class="sxs-lookup"><span data-stu-id="125e0-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="125e0-145">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione regla de **transporte de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="125e0-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="125e0-146">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="125e0-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget de regla de transporte de Exchange en el panel informes](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="125e0-148">Vista informes para el informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="125e0-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="125e0-149">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="125e0-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="125e0-150">**Ver datos por: reglas** \> de transporte de Exchange **Desglose por: Dirección: en**este gráfico se muestra el número de mensajes **entrantes** y **salientes** que se vieron afectados por las reglas de transporte.</span><span class="sxs-lookup"><span data-stu-id="125e0-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="125e0-151">**Ver datos por: reglas** \> de transporte de Exchange **Desglose por: gravedad: en**este gráfico se muestra el número de gravedad **alta** y **mediana**y los mensajes de **gravedad baja** .</span><span class="sxs-lookup"><span data-stu-id="125e0-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="125e0-152">El nivel de gravedad se establece como una acción en la regla (**auditar esta regla con el nivel de gravedad** o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="125e0-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="125e0-153">Para obtener más información, vea [acciones de las reglas de flujo de correo en Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="125e0-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="125e0-154">**Ver datos por: reglas de transporte de Exchange de DLP** \> **Desglose por: Dirección: en**este gráfico se muestra el número de mensajes **entrantes** y **salientes** que se vieron afectados por las reglas de transporte de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="125e0-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="125e0-155">Puede refinar aún más el gráfico si selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="125e0-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="125e0-156">**Mostrar datos para: todas las reglas de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="125e0-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="125e0-157">**Mostrar datos para: usuarios comprometidos**</span><span class="sxs-lookup"><span data-stu-id="125e0-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="125e0-158">**Mostrar datos para: bajo volumen de contenido detectado Patriot Act de Estados Unidos**</span><span class="sxs-lookup"><span data-stu-id="125e0-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="125e0-159">**Ver datos por: reglas de transporte de Exchange de DLP** \> **Dividir por: dirección**: esta vista muestra el número de gravedad **alta** y **mediana**y los mensajes de **gravedad baja** que se vieron afectados por las reglas de transporte de DLP.</span><span class="sxs-lookup"><span data-stu-id="125e0-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="125e0-160">Puede refinar aún más el gráfico si selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="125e0-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="125e0-161">**Mostrar datos para: todas las reglas de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="125e0-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="125e0-162">**Mostrar datos para: usuarios comprometidos**</span><span class="sxs-lookup"><span data-stu-id="125e0-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="125e0-163">**Mostrar datos para: bajo volumen de contenido detectado Patriot Act de Estados Unidos**</span><span class="sxs-lookup"><span data-stu-id="125e0-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="125e0-164">Si hace clic en **filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros::</span><span class="sxs-lookup"><span data-stu-id="125e0-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="125e0-165">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="125e0-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="125e0-166">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="125e0-166">Direction values</span></span>
- <span data-ttu-id="125e0-167">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="125e0-167">Severity values</span></span>

![Vista de informe en el informe de reglas de transporte de Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="125e0-169">Vista de tabla de detalles para el informe de regla de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="125e0-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="125e0-170">Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="125e0-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="125e0-171">**Ver datos por: reglas de transporte de Exchange**:</span><span class="sxs-lookup"><span data-stu-id="125e0-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="125e0-172">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="125e0-172">**Date**</span></span>
  - <span data-ttu-id="125e0-173">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="125e0-173">**Transport rule**</span></span>
  - <span data-ttu-id="125e0-174">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="125e0-174">**Subject**</span></span>
  - <span data-ttu-id="125e0-175">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="125e0-175">**Sender address**</span></span>
  - <span data-ttu-id="125e0-176">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="125e0-176">**Recipient address**</span></span>
  - <span data-ttu-id="125e0-177">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="125e0-177">**Severity**</span></span>
  - <span data-ttu-id="125e0-178">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="125e0-178">**Direction**</span></span>

- <span data-ttu-id="125e0-179">**Ver datos por: reglas de transporte de DLP de Exchange**:</span><span class="sxs-lookup"><span data-stu-id="125e0-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="125e0-180">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="125e0-180">**Date**</span></span>
  - <span data-ttu-id="125e0-181">**Directiva DLP**</span><span class="sxs-lookup"><span data-stu-id="125e0-181">**DLP policy**</span></span>
  - <span data-ttu-id="125e0-182">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="125e0-182">**Transport rule**</span></span>
  - <span data-ttu-id="125e0-183">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="125e0-183">**Subject**</span></span>
  - <span data-ttu-id="125e0-184">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="125e0-184">**Sender address**</span></span>
  - <span data-ttu-id="125e0-185">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="125e0-185">**Recipient address**</span></span>
  - <span data-ttu-id="125e0-186">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="125e0-186">**Severity**</span></span>
  - <span data-ttu-id="125e0-187">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="125e0-187">**Direction**</span></span>

<span data-ttu-id="125e0-188">Si hace clic en **filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="125e0-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="125e0-189">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="125e0-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="125e0-190">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="125e0-190">Direction values</span></span>
- <span data-ttu-id="125e0-191">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="125e0-191">Severity values</span></span>

<span data-ttu-id="125e0-192">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="125e0-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="125e0-193">Reenvío de informes</span><span class="sxs-lookup"><span data-stu-id="125e0-193">Forwarding report</span></span>

<span data-ttu-id="125e0-194">El **Informe de reenvío** muestra los mensajes reenviados automáticamente de la organización a dominios externos de los buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="125e0-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="125e0-195">Los mensajes reenviados pueden suponer un riesgo de seguridad o de cumplimiento, y pueden indicar una cuenta en peligro.</span><span class="sxs-lookup"><span data-stu-id="125e0-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="125e0-196">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **reenviar Informe**.</span><span class="sxs-lookup"><span data-stu-id="125e0-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="125e0-197">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="125e0-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Reenvío del widget de informe en el panel informes](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="125e0-199">Vista informes para el informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="125e0-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="125e0-200">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="125e0-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="125e0-201">**Mostrar datos para: métodos de reenvío**: se muestran los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="125e0-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="125e0-202">**Regla de transporte**: también conocida como [reglas de flujo de correo](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="125e0-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="125e0-203">**Regla de buzón de correo**: también conocida como reglas de la [bandeja de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="125e0-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vista de métodos de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="125e0-205">**Mostrar datos de: dominios de reenvío**: esta vista muestra los dominios de destinatario que son los destinos para el reenvío.</span><span class="sxs-lookup"><span data-stu-id="125e0-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vista de dominios de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="125e0-207">**Mostrar datos para: reenviadores**: se muestran los siguientes reenviadores:</span><span class="sxs-lookup"><span data-stu-id="125e0-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="125e0-208">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="125e0-208">**Transport rule**</span></span>
  - <span data-ttu-id="125e0-209">El buzón de correo que contiene la regla de reenvío de la bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="125e0-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vista de reenvíos en el informe de reenvío](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="125e0-211">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="125e0-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="125e0-212">Vista de tabla de detalles para el informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="125e0-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="125e0-213">Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="125e0-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="125e0-214">**Reenviadores**: la **regla de transporte** de valor o el buzón que contiene la regla de reenvío de la bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="125e0-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="125e0-215">**Tipo de reenvío**: regla de **buzón de correo** de valor o regla de **transporte**.</span><span class="sxs-lookup"><span data-stu-id="125e0-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="125e0-216">**Nombre de destinatario**</span><span class="sxs-lookup"><span data-stu-id="125e0-216">**Recipient name**</span></span>
- <span data-ttu-id="125e0-217">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="125e0-217">**Recipient domain**</span></span>
- <span data-ttu-id="125e0-218">**Detalles**: este es el valor de GUID de la regla de flujo de correo o el valor RuleIdentity de la regla de bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="125e0-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="125e0-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="125e0-219">**Count**</span></span>
- <span data-ttu-id="125e0-220">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="125e0-220">**First forward date**</span></span>

<span data-ttu-id="125e0-221">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="125e0-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="125e0-222">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="125e0-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="125e0-223">Informe de estado de flujo de notificación</span><span class="sxs-lookup"><span data-stu-id="125e0-223">Mailflow status report</span></span>

<span data-ttu-id="125e0-224">El **Informe de estado de flujo** de correo es similar al [Informe de correo electrónico enviado y recibido](#sent-and-received-email-report), con información adicional sobre el correo electrónico permitido o bloqueado en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="125e0-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="125e0-225">Este es el único informe que contiene información sobre la protección perimetral y muestra la cantidad de correo electrónico que se bloquea antes de que se permita el servicio para su evaluación por parte de Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="125e0-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="125e0-226">Es importante comprender que si un mensaje se envía a cinco destinatarios, se cuenta como cinco mensajes diferentes y no un mensaje.</span><span class="sxs-lookup"><span data-stu-id="125e0-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>  
<span data-ttu-id="125e0-227">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione informe de **Estado de flujo**de información.</span><span class="sxs-lookup"><span data-stu-id="125e0-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="125e0-228">Para ir directamente al **Informe de estado del flujo de correo**, Abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="125e0-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget de informe de estado de flujo de registros en el panel informes](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="125e0-230">Tipo de vista para el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="125e0-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="125e0-231">Al abrir el informe, la ficha **tipo** se selecciona de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="125e0-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="125e0-232">De forma predeterminada, esta vista contiene un gráfico y una tabla de datos que se configura con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="125e0-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="125e0-233">**Fecha**: los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="125e0-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="125e0-234">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="125e0-234">**Direction**:</span></span>

  - <span data-ttu-id="125e0-235">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="125e0-235">**Inbound**</span></span>
  - <span data-ttu-id="125e0-236">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="125e0-236">**Outbound**</span></span>
  - <span data-ttu-id="125e0-237">**Dentro de la organización**: este recuento es para los mensajes dentro de un espacio empresarial es decir</span><span class="sxs-lookup"><span data-stu-id="125e0-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="125e0-238">el remitente abc@domain.com envía al destinatario xyz@domain.com (cuenta por separado de **entrada** y de **salida**)</span><span class="sxs-lookup"><span data-stu-id="125e0-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="125e0-239">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="125e0-239">**Type**:</span></span>

  - <span data-ttu-id="125e0-240">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="125e0-240">**Good mail**</span></span>
  - <span data-ttu-id="125e0-241">**Malware**</span><span class="sxs-lookup"><span data-stu-id="125e0-241">**Malware**</span></span>
  - <span data-ttu-id="125e0-242">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="125e0-242">**Spam**</span></span>
  - <span data-ttu-id="125e0-243">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="125e0-243">**Edge protection**</span></span>
  - <span data-ttu-id="125e0-244">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="125e0-244">**Rule messages**</span></span>
  - <span data-ttu-id="125e0-245">**Correo de suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="125e0-245">**Phishing email**</span></span>

<span data-ttu-id="125e0-246">El gráfico se organiza por los valores de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="125e0-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="125e0-247">Puede cambiar estos filtros haciendo clic en **filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="125e0-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="125e0-248">La tabla de datos contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="125e0-248">The data table contains the following information:</span></span>

- <span data-ttu-id="125e0-249">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="125e0-249">**Direction**</span></span>
- <span data-ttu-id="125e0-250">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="125e0-250">**Type**</span></span>
- <span data-ttu-id="125e0-251">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="125e0-251">**24 hours**</span></span>
- <span data-ttu-id="125e0-252">**3 días**</span><span class="sxs-lookup"><span data-stu-id="125e0-252">**3 days**</span></span>
- <span data-ttu-id="125e0-253">**7 días**</span><span class="sxs-lookup"><span data-stu-id="125e0-253">**7 days**</span></span>
- <span data-ttu-id="125e0-254">**15 días**</span><span class="sxs-lookup"><span data-stu-id="125e0-254">**15 days**</span></span>
- <span data-ttu-id="125e0-255">**30 días**</span><span class="sxs-lookup"><span data-stu-id="125e0-255">**30 days**</span></span>

<span data-ttu-id="125e0-256">Si hace clic en **elegir una categoría para obtener más información**, puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="125e0-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="125e0-257">**Correo electrónico de suplantación de identidad**: esta selección le lleva al [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="125e0-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="125e0-258">**Malware en correo electrónico**: esta selección le lleva al [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="125e0-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="125e0-259">**Detecciones de correo no deseado**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="125e0-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="125e0-260">**Correo no deseado de Edge bloqueado**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="125e0-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="125e0-261">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="125e0-261">**Export**:</span></span>

<span data-ttu-id="125e0-262">Para la vista de detalles, solo puede exportar datos de un día.</span><span class="sxs-lookup"><span data-stu-id="125e0-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="125e0-263">Por lo tanto, si desea exportar datos durante 7 días, necesitará hacer 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="125e0-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="125e0-264">Cada archivo. csv exportado está limitado a 150.000 filas.</span><span class="sxs-lookup"><span data-stu-id="125e0-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="125e0-265">Si los datos de ese día contienen más de 150.000 filas, se crearán varios archivos. csv.</span><span class="sxs-lookup"><span data-stu-id="125e0-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="125e0-266">Tipo ver en el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="125e0-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="125e0-267">Vista de dirección para el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="125e0-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="125e0-268">Si hace clic en la ficha **Dirección** , se usarán los mismos filtros predeterminados de la vista de **tipos** .</span><span class="sxs-lookup"><span data-stu-id="125e0-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="125e0-269">El gráfico está organizado por valores de **Dirección** .</span><span class="sxs-lookup"><span data-stu-id="125e0-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="125e0-270">Puede cambiar estos filtros haciendo clic en **filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="125e0-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="125e0-271">Se usan los mismos filtros de la vista **tipo** .</span><span class="sxs-lookup"><span data-stu-id="125e0-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="125e0-272">La tabla de datos contiene la misma información de la vista de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="125e0-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="125e0-273">El comportamiento seleccionar **una categoría para obtener más información sobre** las selecciones disponibles y el comportamiento es el mismo que el de la vista **tipo** .</span><span class="sxs-lookup"><span data-stu-id="125e0-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="125e0-274">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="125e0-274">**Export**:</span></span>

<span data-ttu-id="125e0-275">Para la vista de detalles, solo puede exportar datos de un día.</span><span class="sxs-lookup"><span data-stu-id="125e0-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="125e0-276">Por lo tanto, si desea exportar datos durante 7 días, necesitará hacer 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="125e0-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="125e0-277">Cada archivo. csv exportado está limitado a 150.000 filas.</span><span class="sxs-lookup"><span data-stu-id="125e0-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="125e0-278">Si los datos de ese día contienen más de 150.000 filas, se crearán varios archivos. csv.</span><span class="sxs-lookup"><span data-stu-id="125e0-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="125e0-279">Vista de dirección en el informe de estado de flujo de notificación</span><span class="sxs-lookup"><span data-stu-id="125e0-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="125e0-280">Vista de embudo para el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="125e0-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="125e0-281">La vista de **embudo** muestra cómo las características de protección contra amenazas de correo electrónico de Microsoft filtran el correo entrante y saliente de su organización.</span><span class="sxs-lookup"><span data-stu-id="125e0-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="125e0-282">Proporciona detalles sobre el recuento de correo electrónico total y cómo las características de protección contra amenazas configuradas, incluida la protección perimetral, anti-malware, antiphishing, contra correo no deseado y contra la suplantación de identidad afectan a este recuento.</span><span class="sxs-lookup"><span data-stu-id="125e0-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="125e0-283">Si hace clic en la ficha **embudo** , de forma predeterminada, esta vista contendrá un gráfico y una tabla de datos configurada con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="125e0-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="125e0-284">**Fecha**: los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="125e0-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="125e0-285">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="125e0-285">**Direction**:</span></span>

  - <span data-ttu-id="125e0-286">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="125e0-286">**Inbound**</span></span>
  - <span data-ttu-id="125e0-287">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="125e0-287">**Outbound**</span></span>
  - <span data-ttu-id="125e0-288">**Dentro de la organización**: este recuento es para los mensajes enviados en un espacio empresarial; es decir, el abc@domain.com del remitente envía al destinatario xyz@domain.com (contado por separado de entrante y saliente).</span><span class="sxs-lookup"><span data-stu-id="125e0-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="125e0-289">La vista agregada y la vista de tabla de datos permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="125e0-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="125e0-290">Si hace clic en **filtrar**, puede filtrar tanto el gráfico como la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="125e0-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="125e0-291">Este gráfico muestra el número de correos electrónicos organizados por:</span><span class="sxs-lookup"><span data-stu-id="125e0-291">This chart shows the email count organized by:</span></span>

  - <span data-ttu-id="125e0-292">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="125e0-292">**Total email**</span></span>
  - <span data-ttu-id="125e0-293">**Correo electrónico tras la protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="125e0-293">**Email after edge protection**</span></span>
  - <span data-ttu-id="125e0-294">**Correo electrónico después de anti-malware, reputación de archivo, bloque de tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="125e0-294">**Email after anti-malware, file reputation, file type block**</span></span>
  - <span data-ttu-id="125e0-295">**Correo electrónico después de antiphishing, reputación de dirección URL, suplantación de marca, anti-falseamiento**</span><span class="sxs-lookup"><span data-stu-id="125e0-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
  - <span data-ttu-id="125e0-296">**Correo electrónico después de la protección contra correo no deseado, filtrado de correo masivo**</span><span class="sxs-lookup"><span data-stu-id="125e0-296">**Email after anti-spam, bulk mail filtering**</span></span>
  - <span data-ttu-id="125e0-297">**Correo electrónico después de suplantación de usuario y dominio**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="125e0-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
  - <span data-ttu-id="125e0-298">**Correo electrónico después de detonación de archivo y URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="125e0-298">**Email after file and URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="125e0-299">**Correo electrónico detectado como benigno después de la protección tras la entrega (dirección URL, clic en protección del tiempo)**</span><span class="sxs-lookup"><span data-stu-id="125e0-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="125e0-300"><sup>1</sup> solo para ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="125e0-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="125e0-301">Para ver el correo electrónico filtrado por EOP o ATP por separado, haga clic en el valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="125e0-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="125e0-302">La tabla de datos contiene la siguiente información, que se muestra en orden de fecha descendente:</span><span class="sxs-lookup"><span data-stu-id="125e0-302">The data table contains the following information, shown in descending date order:</span></span>

 - <span data-ttu-id="125e0-303">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="125e0-303">**Date**</span></span>
 - <span data-ttu-id="125e0-304">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="125e0-304">**Total email**</span></span>
 - <span data-ttu-id="125e0-305">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="125e0-305">**Edge protection**</span></span>
 - <span data-ttu-id="125e0-306">**Anti-malware, reputación de archivos, bloque de tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="125e0-306">**Anti-malware, file reputation, file type block**</span></span>
 - <span data-ttu-id="125e0-307">**Anti-phish, reputación de dirección URL, suplantación de marca, antifalsificación**</span><span class="sxs-lookup"><span data-stu-id="125e0-307">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**</span></span>
 - <span data-ttu-id="125e0-308">**Contra correo electrónico no deseado, filtrado de correo masivo**</span><span class="sxs-lookup"><span data-stu-id="125e0-308">**Anti-spam, bulk mail filtering**</span></span>
 - <span data-ttu-id="125e0-309">**Suplantación de usuario y dominio (ATP)**</span><span class="sxs-lookup"><span data-stu-id="125e0-309">**User and domain impersonation (ATP)**</span></span>
 - <span data-ttu-id="125e0-310">**Detonación de archivo y dirección URL (ATP)**</span><span class="sxs-lookup"><span data-stu-id="125e0-310">**File and URL detonation (ATP)**</span></span>
 - <span data-ttu-id="125e0-311">**Protección tras entrega y ZAP (ATP) o ZAP (EOP)**</span><span class="sxs-lookup"><span data-stu-id="125e0-311">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**</span></span>

<span data-ttu-id="125e0-312">Si selecciona una fila en la tabla de datos, se muestra un desglose de los recuentos de correo electrónico en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="125e0-312">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="125e0-313">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="125e0-313">**Export**:</span></span>

<span data-ttu-id="125e0-314">Después de hacer clic en **exportar** en **Opciones**, puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="125e0-314">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="125e0-315">**Resumen (con datos para los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="125e0-315">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="125e0-316">**Detalles (con datos de 30 últimos días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="125e0-316">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="125e0-317">En **fecha**, elija un rango y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="125e0-317">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="125e0-318">Los datos de los filtros actuales se exportarán a un archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="125e0-318">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="125e0-319">Cada archivo. csv exportado está limitado a 150.000 filas.</span><span class="sxs-lookup"><span data-stu-id="125e0-319">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="125e0-320">Si los datos contienen más de 150.000 filas, se crearán varios archivos. csv.</span><span class="sxs-lookup"><span data-stu-id="125e0-320">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="125e0-321">Vista de embudo en el informe de estado de flujo de notificación</span><span class="sxs-lookup"><span data-stu-id="125e0-321">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

 ### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="125e0-322">Vista técnica del informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="125e0-322">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="125e0-323">La **vista técnica** es similar a la vista de **embudo** y proporciona detalles más granulares para las características de protección contra amenazas configuradas.</span><span class="sxs-lookup"><span data-stu-id="125e0-323">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="125e0-324">Desde el gráfico, puede ver cómo se clasifican los mensajes en las diferentes etapas de la protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="125e0-324">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="125e0-325">Si hace clic en la pestaña **vista técnica** , de forma predeterminada, esta vista contendrá un gráfico y una tabla de datos configurada con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="125e0-325">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="125e0-326">**Fecha**: los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="125e0-326">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="125e0-327">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="125e0-327">**Direction**:</span></span>

  - <span data-ttu-id="125e0-328">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="125e0-328">**Inbound**</span></span>
  - <span data-ttu-id="125e0-329">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="125e0-329">**Outbound**</span></span>
  - <span data-ttu-id="125e0-330">**Dentro de la organización**: este recuento es para los mensajes dentro de un espacio empresarial es decir</span><span class="sxs-lookup"><span data-stu-id="125e0-330">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="125e0-331">el remitente abc@domain.com envía al destinatario xyz@domain.com (cuenta por separado de entrada y de salida)</span><span class="sxs-lookup"><span data-stu-id="125e0-331">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="125e0-332">La vista agregada y la vista de tabla de datos permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="125e0-332">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="125e0-333">Si hace clic en **filtrar**, puede filtrar tanto el gráfico como la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="125e0-333">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="125e0-334">Este gráfico muestra los mensajes organizados en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="125e0-334">This chart shows messages organized into the following categories:</span></span>

  - <span data-ttu-id="125e0-335">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="125e0-335">**Total email**</span></span>
  - <span data-ttu-id="125e0-336">**Límite permitido, perimetral filtrado**</span><span class="sxs-lookup"><span data-stu-id="125e0-336">**Edge allow, edge filtered**</span></span>
  - <span data-ttu-id="125e0-337">**No es malware, detección de datos adjuntos seguros (ATP), detección del motor antimalware, bloqueo de reglas**</span><span class="sxs-lookup"><span data-stu-id="125e0-337">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
  - <span data-ttu-id="125e0-338">**No phish, error de DMARC, detección de suplantación, detección de suplantación de identidad, detección de phish**</span><span class="sxs-lookup"><span data-stu-id="125e0-338">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
  - <span data-ttu-id="125e0-339">**Sin detección con detonación de dirección URL, detección de detonación de dirección URL (ATP)**</span><span class="sxs-lookup"><span data-stu-id="125e0-339">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
  - <span data-ttu-id="125e0-340">**No es correo no deseado, correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="125e0-340">**Not spam, spam**</span></span>
  - <span data-ttu-id="125e0-341">**Correo electrónico no malintencionado, detección de vínculos seguros (ATP), ZAP**</span><span class="sxs-lookup"><span data-stu-id="125e0-341">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="125e0-342">Cuando desplaza el puntero sobre una categoría del gráfico, puede ver el número de mensajes que hay en esa categoría.</span><span class="sxs-lookup"><span data-stu-id="125e0-342">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="125e0-343">La tabla de datos contiene la siguiente información, que se muestra en orden de fecha descendente:</span><span class="sxs-lookup"><span data-stu-id="125e0-343">The data table contains the following information, shown in descending date order:</span></span>

  - <span data-ttu-id="125e0-344">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="125e0-344">**Date**</span></span>  
  - <span data-ttu-id="125e0-345">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="125e0-345">**Total email**</span></span>
  - <span data-ttu-id="125e0-346">**Borde filtrado**</span><span class="sxs-lookup"><span data-stu-id="125e0-346">**Edge filtered**</span></span>
  - <span data-ttu-id="125e0-347">**Motor antimalware, datos adjuntos seguros, regla filtrado**</span><span class="sxs-lookup"><span data-stu-id="125e0-347">**Anti-malware engine, safe attachments, rule filtered**</span></span>
  - <span data-ttu-id="125e0-348">**DMARC, suplantación, falsificación, phish filtrado**</span><span class="sxs-lookup"><span data-stu-id="125e0-348">**DMARC, impersonation, spoof, phish filtered**</span></span>
  - <span data-ttu-id="125e0-349">**Detección de detonación de dirección URL**</span><span class="sxs-lookup"><span data-stu-id="125e0-349">**URL detonation detection**</span></span>
  - <span data-ttu-id="125e0-350">**Filtrado contra correo electrónico no deseado**</span><span class="sxs-lookup"><span data-stu-id="125e0-350">**Anti-spam filtered**</span></span>
  - <span data-ttu-id="125e0-351">**ZAP quitado**</span><span class="sxs-lookup"><span data-stu-id="125e0-351">**ZAP removed**</span></span>
  - <span data-ttu-id="125e0-352">**Detección por vínculos seguros**</span><span class="sxs-lookup"><span data-stu-id="125e0-352">**Detection by safe links**</span></span>

<span data-ttu-id="125e0-353">Si selecciona una fila en la tabla de datos, se muestra un desglose de los recuentos de correo electrónico en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="125e0-353">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="125e0-354">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="125e0-354">**Export**:</span></span>

<span data-ttu-id="125e0-355">Al hacer clic en **exportar**, en **Opciones** , puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="125e0-355">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="125e0-356">**Resumen (con datos para los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="125e0-356">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="125e0-357">**Detalles (con datos de 30 últimos días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="125e0-357">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="125e0-358">En **fecha**, elija un rango y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="125e0-358">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="125e0-359">Los datos de los filtros actuales se exportarán a un archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="125e0-359">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="125e0-360">Cada archivo. csv exportado está limitado a 150.000 filas.</span><span class="sxs-lookup"><span data-stu-id="125e0-360">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="125e0-361">Si los datos contienen más de 150.000 filas, se crearán varios archivos. csv.</span><span class="sxs-lookup"><span data-stu-id="125e0-361">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="125e0-362">Vista de Tech en el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="125e0-362">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="125e0-363">Informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="125e0-363">Sent and received email report</span></span>

<span data-ttu-id="125e0-364">El informe de **correo electrónico enviado y recibido** es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas las detecciones de correo no deseado, malware y el correo electrónico identificado como "bueno".</span><span class="sxs-lookup"><span data-stu-id="125e0-364">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="125e0-365">La diferencia entre este informe y el [Informe de estado de flujo](#mailflow-status-report) de correos es la siguiente: este informe no incluye datos sobre los mensajes bloqueados por la protección perimetral.</span><span class="sxs-lookup"><span data-stu-id="125e0-365">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="125e0-366">La vista agregada y la vista de detalles del informe permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="125e0-366">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="125e0-367">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **correo electrónico enviado y recibido**.</span><span class="sxs-lookup"><span data-stu-id="125e0-367">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="125e0-368">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="125e0-368">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget de correo electrónico enviado y recibido en el panel de informes](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="125e0-370">Vista informes para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="125e0-370">Report view for the Sent and received email report</span></span>

<span data-ttu-id="125e0-371">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="125e0-371">The following charts are available in the report view:</span></span>

- <span data-ttu-id="125e0-372">**Dividir por: escriba**: el gráfico muestra todas las categorías disponibles:</span><span class="sxs-lookup"><span data-stu-id="125e0-372">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="125e0-373">**Total**</span><span class="sxs-lookup"><span data-stu-id="125e0-373">**Total**</span></span>
  - <span data-ttu-id="125e0-374">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="125e0-374">**Good mail**</span></span>
  - <span data-ttu-id="125e0-375">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="125e0-375">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="125e0-376">**Detecciones de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="125e0-376">**Spam detections**</span></span>
  - <span data-ttu-id="125e0-377">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="125e0-377">**Rule messages**</span></span>
  - <span data-ttu-id="125e0-378">**Malware avanzado** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="125e0-378">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="125e0-379">Al pasar el mouse sobre un día (punto de datos) del gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="125e0-379">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Tipo ver en el informe de correo electrónico enviado y recibido](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="125e0-381">**Desglose por: dirección**: el gráfico muestra los datos **totales**, **entrantes**y **salientes** .</span><span class="sxs-lookup"><span data-stu-id="125e0-381">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="125e0-382">Al pasar el mouse sobre un día (punto de datos) del gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="125e0-382">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vista de dirección en el informe de correo electrónico enviados y recibidos](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="125e0-384">**Explorar en profundidad por** \> **Malware (anti-malware)**: esta selección le lleva a las [detecciones de malware en el informe de correo electrónico](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="125e0-384">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="125e0-385">**Explorar en profundidad por** \> **Detecciones de correo no deseado)**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="125e0-385">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="125e0-386">Si hace clic en **filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="125e0-386">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="125e0-387">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="125e0-387">**Start date** and **End date**</span></span>
- <span data-ttu-id="125e0-388">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="125e0-388">Direction values</span></span>
- <span data-ttu-id="125e0-389">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="125e0-389">Type values</span></span>

<span data-ttu-id="125e0-390">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="125e0-390">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="125e0-391">Vista de tabla de detalles para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="125e0-391">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="125e0-392">Si hace clic en **ver tabla de detalles** en el cuadro **desglosar por: dirección** o **dividir por:** vista de dirección, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="125e0-392">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="125e0-393">**Fecha (UTC)**</span><span class="sxs-lookup"><span data-stu-id="125e0-393">**Date (UTC)**</span></span>
- <span data-ttu-id="125e0-394">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="125e0-394">**Type**</span></span>
- <span data-ttu-id="125e0-395">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="125e0-395">**Direction**</span></span>
- <span data-ttu-id="125e0-396">**Número de mensajes**</span><span class="sxs-lookup"><span data-stu-id="125e0-396">**Message count**</span></span>

<span data-ttu-id="125e0-397">Si hace clic en **filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="125e0-397">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="125e0-398">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="125e0-398">**Start date** and **End date**</span></span>
- <span data-ttu-id="125e0-399">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="125e0-399">Direction values</span></span>
- <span data-ttu-id="125e0-400">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="125e0-400">Type values</span></span>

<span data-ttu-id="125e0-401">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="125e0-401">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="125e0-402">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="125e0-402">Top senders and recipients report</span></span>

<span data-ttu-id="125e0-403">El informe de **remitentes y destinatarios principales** es un gráfico circular que muestra los principales remitentes y destinatarios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="125e0-403">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="125e0-404">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **principales remitentes y destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="125e0-404">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="125e0-405">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="125e0-405">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widgets principales remitentes y destinatarios en el panel informes](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="125e0-407">Vista informes para los principales informes de remitentes y destinatarios</span><span class="sxs-lookup"><span data-stu-id="125e0-407">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="125e0-408">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="125e0-408">The following charts are available in the report view:</span></span>

- <span data-ttu-id="125e0-409">**Mostrar datos para los \> remitentes de correo principales**</span><span class="sxs-lookup"><span data-stu-id="125e0-409">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="125e0-410">**Mostrar datos para los \> principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="125e0-410">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="125e0-411">**Mostrar datos para los \> principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="125e0-411">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="125e0-412">**Mostrar datos para \> Destinatarios principales de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="125e0-412">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="125e0-413">**Mostrar datos para \> Principales destinatarios de malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="125e0-413">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="125e0-414">La composición del gráfico circular cambia en función de estas selecciones.</span><span class="sxs-lookup"><span data-stu-id="125e0-414">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="125e0-415">Cuando desplaza el puntero sobre una cuña del gráfico circular, puede ver un recuento de los mensajes enviados o recibidos.</span><span class="sxs-lookup"><span data-stu-id="125e0-415">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="125e0-416">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="125e0-416">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico circular en la vista de informe en el informe de remitentes y destinatarios principales](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="125e0-418">Vista de tabla de detalles para el informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="125e0-418">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="125e0-419">Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="125e0-419">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="125e0-420">**Mostrar datos para los \> remitentes de correo principales**</span><span class="sxs-lookup"><span data-stu-id="125e0-420">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="125e0-421">**Principales remitentes de correo**</span><span class="sxs-lookup"><span data-stu-id="125e0-421">**Top mail senders**</span></span>
  - <span data-ttu-id="125e0-422">**Count**</span><span class="sxs-lookup"><span data-stu-id="125e0-422">**Count**</span></span>

- <span data-ttu-id="125e0-423">**Mostrar datos para los \> principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="125e0-423">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="125e0-424">**Destinatarios principales de correo**</span><span class="sxs-lookup"><span data-stu-id="125e0-424">**Top mail recipients**</span></span>
  - <span data-ttu-id="125e0-425">**Count**</span><span class="sxs-lookup"><span data-stu-id="125e0-425">**Count**</span></span>

- <span data-ttu-id="125e0-426">**Mostrar datos para los \> principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="125e0-426">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="125e0-427">**Principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="125e0-427">**Top spam recipients**</span></span>
  - <span data-ttu-id="125e0-428">**Count**</span><span class="sxs-lookup"><span data-stu-id="125e0-428">**Count**</span></span>

- <span data-ttu-id="125e0-429">**Mostrar datos para \> Destinatarios principales de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="125e0-429">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="125e0-430">**Destinatarios principales de malware**</span><span class="sxs-lookup"><span data-stu-id="125e0-430">**Top malware recipients**</span></span>
  - <span data-ttu-id="125e0-431">**Count**</span><span class="sxs-lookup"><span data-stu-id="125e0-431">**Count**</span></span>

- <span data-ttu-id="125e0-432">**Mostrar datos para \> Principales destinatarios de malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="125e0-432">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="125e0-433">**Destinatarios principales de malware (ATP)**</span><span class="sxs-lookup"><span data-stu-id="125e0-433">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="125e0-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="125e0-434">**Count**</span></span>

<span data-ttu-id="125e0-435">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="125e0-435">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="125e0-436">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="125e0-436">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="125e0-437">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="125e0-437">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="125e0-438">Para ver y usar los informes, debe ser miembro del grupo de roles especificado en el centro de seguridad & cumplimiento **y** en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="125e0-438">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="125e0-439">En el centro de seguridad & cumplimiento, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="125e0-439">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="125e0-440">-Organization Management-administrador de seguridad (también puede hacerlo en el [centro de administración de Azure Active Directory](https://aad.portal.azure.com) -lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="125e0-440">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="125e0-441">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="125e0-441">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="125e0-442">En Exchange Online, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="125e0-442">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="125e0-443">-Administración de la organización: administración de la organización de solo vista-destinatarios de solo vista-administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="125e0-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="125e0-444">Para obtener más información, consulte [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) y [Manage role Groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="125e0-444">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="125e0-445">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="125e0-445">Related topics</span></span>

[<span data-ttu-id="125e0-446">Informes inteligentes y reportes en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="125e0-446">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="125e0-447">Reportes de flujo de Correo en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="125e0-447">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="125e0-448">Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="125e0-448">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="125e0-449">Ver informes para la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="125e0-449">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
