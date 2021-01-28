---
title: Ver informes de flujo de correo en el panel informes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre los informes de flujo de correo que están disponibles en el panel Informes del Centro de & cumplimiento.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e69085d1fad845ab519f2590b0527316463373a7
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029803"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="b5cbe-103">Ver informes de flujo de correo en el panel Informes del Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b5cbe-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b5cbe-104">Además de los informes de flujo [](mail-flow-insights-v2.md) de correo que están disponibles en el panel flujo de correo en el Centro de seguridad y cumplimiento de &, hay disponibles varios informes de flujo de correo adicionales en el panel informes para ayudarle a supervisar su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="b5cbe-105">Si tiene los permisos [necesarios,](#what-permissions-are-needed-to-view-these-reports)puede ver estos informes en el Centro de seguridad [& cumplimiento](https://protection.office.com) yendo al **Panel de** \> **informes.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="b5cbe-106">Para ir directamente al panel Informes, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="b5cbe-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Panel informes en el Centro de & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="b5cbe-108">Informe de conector</span><span class="sxs-lookup"><span data-stu-id="b5cbe-108">Connector report</span></span>

<span data-ttu-id="b5cbe-109">El **informe del conector** muestra la actividad de flujo de correo en los conectores entrantes y [salientes configurados](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para su organización.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="b5cbe-110">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Informe \>  de **conector.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="b5cbe-111">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="b5cbe-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget Informe de conectores en el panel informes](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="b5cbe-113">Vista de informe para el informe del conector</span><span class="sxs-lookup"><span data-stu-id="b5cbe-113">Report view for the Connector report</span></span>

<span data-ttu-id="b5cbe-114">Los siguientes gráficos están disponibles en la vista de informes:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="b5cbe-115">**Ver datos por: Flujo de correo:** este gráfico muestra el número de mensajes entrantes y salientes organizados por:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="b5cbe-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-116">**Total**</span></span>
  - <span data-ttu-id="b5cbe-117">**Desde Internet sin un conector**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="b5cbe-118">**A Internet sin un conector**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="b5cbe-119">Un conector específico que ha configurado.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="b5cbe-120">Para aislar los datos del gráfico, use la opción Mostrar **datos** para el control para seleccionar una de estas opciones o **Todo el flujo de correo.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Ver datos por flujo de correo en el informe del conector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="b5cbe-122">**Ver datos por: uso de TLS:** este gráfico muestra el porcentaje de uso de la versión seguridad de la capa de transporte (TLS) para el flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="b5cbe-123">Para aislar los datos del gráfico, use la opción Mostrar **datos para** el control para seleccionar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="b5cbe-124">**Todo el flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-124">**All mail flow**</span></span>
  - <span data-ttu-id="b5cbe-125">**Desde Internet sin un conector**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="b5cbe-126">**A Internet sin un conector**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="b5cbe-127">Un conector específico que ha configurado.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-127">A specific connector that you've configured.</span></span>

  ![Ver datos por uso de TLS en el informe del conector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="b5cbe-129">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con fecha **de inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="b5cbe-130">Vista de tabla de detalles para el informe del conector</span><span class="sxs-lookup"><span data-stu-id="b5cbe-130">Details table view for the Connector report</span></span>

<span data-ttu-id="b5cbe-131">Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="b5cbe-132">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-132">**Date**</span></span>
- <span data-ttu-id="b5cbe-133">**Nombre y dirección del conector**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-133">**Connector direction and name**</span></span>
- <span data-ttu-id="b5cbe-134">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-134">**Connector type**</span></span>
- <span data-ttu-id="b5cbe-135">**¿TLS forzada?**: El valor **True** o **False**.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="b5cbe-136">**Sin TLS** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="b5cbe-137">**TLS 1.0** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="b5cbe-138">**TLS 1.1** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="b5cbe-139">**TLS 1.2** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="b5cbe-140">**Volumen:** el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="b5cbe-141">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con fecha de **inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b5cbe-142">Para volver a la vista informe, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="b5cbe-143">Informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="b5cbe-143">Exchange transport rule report</span></span>

<span data-ttu-id="b5cbe-144">El **informe de reglas de transporte de Exchange** muestra el efecto de las reglas de flujo de correo (también conocidas como reglas de transporte) en los mensajes entrantes y salientes de la organización.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="b5cbe-145">Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione la regla de transporte \>  de **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="b5cbe-146">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="b5cbe-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget de regla de transporte de Exchange en el panel informes](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="b5cbe-148">Vista de informe para el informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="b5cbe-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="b5cbe-149">Los siguientes gráficos están disponibles en la vista de informes:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="b5cbe-150">**Ver datos por: reglas de transporte de** \> Exchange **Dividir por: Dirección:** este gráfico  muestra  el número de mensajes entrantes y salientes que se vieron afectados por las reglas de transporte.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="b5cbe-151">**Ver datos por: reglas de transporte de** \> Exchange **Dividir por: Gravedad: este** gráfico muestra  el número de mensajes de gravedad alta y media y **baja.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="b5cbe-152">El nivel de gravedad se establece como una acción en la regla (**Audite** esta regla con el nivel de gravedad o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="b5cbe-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="b5cbe-153">Para obtener más información, vea [Acciones de regla de flujo de correo en Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="b5cbe-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="b5cbe-154">**Ver datos por: reglas de transporte de Exchange DLP** \> **Dividir por: Dirección:** este gráfico  muestra  el número de mensajes entrantes y salientes que se vieron afectados por las reglas de transporte de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="b5cbe-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="b5cbe-155">Puede refinar aún más el gráfico seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="b5cbe-156">**Mostrar datos para: Todas las reglas de transporte DLP**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="b5cbe-157">**Mostrar datos para: usuarios comprometidos**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="b5cbe-158">**Mostrar datos para: Bajo volumen de contenido detectado por la Ley Patriota de Ee. UU.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="b5cbe-159">**Ver datos por: reglas de transporte de Exchange dlp** \> **Dividir por: Dirección:** esta vista muestra el número de mensajes  de gravedad alta y media, y de gravedad baja que se vieron afectados por las reglas de transporte DLP. </span><span class="sxs-lookup"><span data-stu-id="b5cbe-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="b5cbe-160">Puede refinar aún más el gráfico seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="b5cbe-161">**Mostrar datos para: Todas las reglas de transporte DLP**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="b5cbe-162">**Mostrar datos para: usuarios comprometidos**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="b5cbe-163">**Mostrar datos para: Bajo volumen de contenido detectado por la Ley Patriota de Ee. UU.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="b5cbe-164">Si hace clic **en Filtros** en una vista de informe, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="b5cbe-165">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="b5cbe-166">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="b5cbe-166">Direction values</span></span>
- <span data-ttu-id="b5cbe-167">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="b5cbe-167">Severity values</span></span>

![Vista de informe en el informe de reglas de transporte de Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="b5cbe-169">Vista de tabla de detalles para el informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="b5cbe-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="b5cbe-170">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b5cbe-171">**Ver datos por: Reglas de transporte de Exchange:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="b5cbe-172">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-172">**Date**</span></span>
  - <span data-ttu-id="b5cbe-173">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-173">**Transport rule**</span></span>
  - <span data-ttu-id="b5cbe-174">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-174">**Subject**</span></span>
  - <span data-ttu-id="b5cbe-175">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-175">**Sender address**</span></span>
  - <span data-ttu-id="b5cbe-176">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-176">**Recipient address**</span></span>
  - <span data-ttu-id="b5cbe-177">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-177">**Severity**</span></span>
  - <span data-ttu-id="b5cbe-178">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-178">**Direction**</span></span>

- <span data-ttu-id="b5cbe-179">**Ver datos por: reglas de transporte de Exchange DLP:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="b5cbe-180">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-180">**Date**</span></span>
  - <span data-ttu-id="b5cbe-181">**Directiva DLP**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-181">**DLP policy**</span></span>
  - <span data-ttu-id="b5cbe-182">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-182">**Transport rule**</span></span>
  - <span data-ttu-id="b5cbe-183">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-183">**Subject**</span></span>
  - <span data-ttu-id="b5cbe-184">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-184">**Sender address**</span></span>
  - <span data-ttu-id="b5cbe-185">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-185">**Recipient address**</span></span>
  - <span data-ttu-id="b5cbe-186">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-186">**Severity**</span></span>
  - <span data-ttu-id="b5cbe-187">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-187">**Direction**</span></span>

<span data-ttu-id="b5cbe-188">Si hace clic **en Filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b5cbe-189">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="b5cbe-190">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="b5cbe-190">Direction values</span></span>
- <span data-ttu-id="b5cbe-191">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="b5cbe-191">Severity values</span></span>

<span data-ttu-id="b5cbe-192">Para volver a la vista informe, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="b5cbe-193">Informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="b5cbe-193">Forwarding report</span></span>

<span data-ttu-id="b5cbe-194">El **informe de reenvío** muestra los mensajes reenviados automáticamente de su organización a dominios externos desde buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="b5cbe-195">Los mensajes reenviados pueden suponer un riesgo de seguridad o cumplimiento, y pueden indicar una cuenta en peligro.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="b5cbe-196">Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de \>  informes y seleccione Informe **de reenvío.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="b5cbe-197">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="b5cbe-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget Reenviar informe en el panel Informes](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="b5cbe-199">Vista de informe para el informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="b5cbe-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="b5cbe-200">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b5cbe-201">**Mostrar datos para: Métodos de reenvío:** se muestran los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="b5cbe-202">**Regla de transporte:** también conocida como reglas [de flujo de correo.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="b5cbe-203">**Regla de buzón:** también conocida como [reglas de bandeja de entrada.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vista de métodos de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="b5cbe-205">**Mostrar datos para: Dominios de reenvío:** esta vista muestra los dominios de destinatario que son los destinos para el reenvío.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vista de dominios de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="b5cbe-207">**Mostrar datos para: Reenviadores:** se muestran los siguientes reenviadores:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="b5cbe-208">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-208">**Transport rule**</span></span>
  - <span data-ttu-id="b5cbe-209">El buzón que contiene la regla de reenvío de la Bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vista Reenviadores en el informe de reenvío](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="b5cbe-211">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con fecha **de inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="b5cbe-212">Vista de tabla de detalles para el informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="b5cbe-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="b5cbe-213">Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="b5cbe-214">**Reenviadores:** la regla **de transporte de** valor o el buzón que contiene la regla de reenvío de la Bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="b5cbe-215">**Tipo de reenvío:** la regla de **buzón de valor** o la regla de **transporte**.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="b5cbe-216">**Nombre de destinatario**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-216">**Recipient name**</span></span>
- <span data-ttu-id="b5cbe-217">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-217">**Recipient domain**</span></span>
- <span data-ttu-id="b5cbe-218">**Detalles:** este es el valor GUID de la regla de flujo de correo o el valor RuleIdentity de la regla de bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="b5cbe-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-219">**Count**</span></span>
- <span data-ttu-id="b5cbe-220">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-220">**First forward date**</span></span>

<span data-ttu-id="b5cbe-221">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con fecha de **inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b5cbe-222">Para volver a la vista informes, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="b5cbe-223">Informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="b5cbe-223">Mailflow status report</span></span>

<span data-ttu-id="b5cbe-224">El **informe de estado de flujo de** correo es similar al informe de correo electrónico enviado y recibido, con información adicional sobre el correo electrónico permitido o bloqueado en el perímetro. [](#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="b5cbe-225">Este es el único informe que contiene información de protección perimetral y muestra cuánto correo electrónico se bloquea antes de que Exchange Online Protection (EOP) pueda entrar en el servicio para su evaluación.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="b5cbe-226">Es importante comprender que si se envía un mensaje a cinco destinatarios, lo contaremos como cinco mensajes diferentes y no como un mensaje.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="b5cbe-227">Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Informe de estado \>  de flujo **de correo.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="b5cbe-228">Para ir directamente al informe **de estado de flujo de correo**, abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="b5cbe-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget Informe de estado de flujo de correo en el panel Informes](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="b5cbe-230">Vista de tipo para el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="b5cbe-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="b5cbe-231">Al abrir el informe, la **pestaña** Tipo está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="b5cbe-232">De forma predeterminada, esta vista contiene un gráfico y una tabla de datos que se configura con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="b5cbe-233">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="b5cbe-234">**Dirección:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-234">**Direction**:</span></span>

  - <span data-ttu-id="b5cbe-235">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-235">**Inbound**</span></span>
  - <span data-ttu-id="b5cbe-236">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-236">**Outbound**</span></span>
  - <span data-ttu-id="b5cbe-237">**Dentro de la organización:** este recuento es para los mensajes dentro de un espacio empresarial, es decir,</span><span class="sxs-lookup"><span data-stu-id="b5cbe-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="b5cbe-238">remitente abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de **entrante** y **saliente)**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="b5cbe-239">**Tipo:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-239">**Type**:</span></span>

  - <span data-ttu-id="b5cbe-240">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-240">**Good mail**</span></span>
  - <span data-ttu-id="b5cbe-241">**Malware**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-241">**Malware**</span></span>
  - <span data-ttu-id="b5cbe-242">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-242">**Spam**</span></span>
  - <span data-ttu-id="b5cbe-243">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-243">**Edge protection**</span></span>
  - <span data-ttu-id="b5cbe-244">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-244">**Rule messages**</span></span>
  - <span data-ttu-id="b5cbe-245">**Correo de suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-245">**Phishing email**</span></span>

<span data-ttu-id="b5cbe-246">El gráfico está organizado por los valores **de** tipo.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="b5cbe-247">Puede cambiar estos filtros haciendo clic en **Filtro** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="b5cbe-248">La tabla de datos contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-248">The data table contains the following information:</span></span>

- <span data-ttu-id="b5cbe-249">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-249">**Direction**</span></span>
- <span data-ttu-id="b5cbe-250">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-250">**Type**</span></span>
- <span data-ttu-id="b5cbe-251">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-251">**24 hours**</span></span>
- <span data-ttu-id="b5cbe-252">**3 días**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-252">**3 days**</span></span>
- <span data-ttu-id="b5cbe-253">**7 días**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-253">**7 days**</span></span>
- <span data-ttu-id="b5cbe-254">**15 días**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-254">**15 days**</span></span>
- <span data-ttu-id="b5cbe-255">**30 días**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-255">**30 days**</span></span>

<span data-ttu-id="b5cbe-256">Si hace clic **en Elegir una categoría para obtener más** información, puede seleccionar entre los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="b5cbe-257">**Correo electrónico de suplantación** de identidad : esta selección le lleva al informe de estado [de protección contra amenazas.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="b5cbe-258">**Malware en el correo** electrónico: esta selección le lleva al informe de estado [de protección contra amenazas.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="b5cbe-259">**Detecciones de correo** no deseado: esta selección le lleva al informe de [detecciones de correo no deseado.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="b5cbe-260">**Correo no deseado bloqueado** perimetral: esta selección le lleva al informe de [detecciones de correo no deseado.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="b5cbe-261">**Exportar:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-261">**Export**:</span></span>

<span data-ttu-id="b5cbe-262">Para la vista de detalles, solo puede exportar datos de un día.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="b5cbe-263">Por lo tanto, si desea exportar datos durante 7 días, debe realizar 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="b5cbe-264">Cada archivo .csv exportado está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b5cbe-265">Si los datos de ese día contienen más de 150.000 filas, se crearán varios archivos .csv.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="b5cbe-266">Vista de tipo en el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="b5cbe-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="b5cbe-267">Vista de dirección del informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="b5cbe-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="b5cbe-268">Si hace clic en la **pestaña** Dirección, se usarán los mismos filtros predeterminados de la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="b5cbe-269">El gráfico se organiza por valores **de** dirección.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="b5cbe-270">Puede cambiar estos filtros haciendo clic en **Filtro** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="b5cbe-271">Se usan los mismos filtros de **la vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="b5cbe-272">La tabla de datos contiene la misma información de la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="b5cbe-273">La **categoría Elegir una categoría para obtener más detalles** sobre el comportamiento y las selecciones disponibles es la misma que la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="b5cbe-274">**Exportar:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-274">**Export**:</span></span>

<span data-ttu-id="b5cbe-275">Para la vista de detalles, solo puede exportar datos de un día.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="b5cbe-276">Por lo tanto, si desea exportar datos durante 7 días, debe realizar 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="b5cbe-277">Cada archivo .csv exportado está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b5cbe-278">Si los datos de ese día contienen más de 150.000 filas, se crearán varios archivos .csv.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="b5cbe-279">Vista de dirección en el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="b5cbe-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="b5cbe-280">Vista embudo para el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="b5cbe-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="b5cbe-281">La **vista Embudo** muestra cómo las características de protección contra amenazas de correo electrónico de Microsoft filtran el correo electrónico entrante y saliente en su organización.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="b5cbe-282">Proporciona detalles sobre el recuento total de correo electrónico y cómo afectan a este recuento las características configuradas de protección contra amenazas, incluida la protección perimetral, el antimalware, la protección contra suplantación de identidad, el correo no deseado y la protección contra la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="b5cbe-283">Si hace clic en la pestaña **Embudo,** de forma predeterminada, esta vista contiene un gráfico y una tabla de datos configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="b5cbe-284">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="b5cbe-285">**Dirección:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-285">**Direction**:</span></span>

  - <span data-ttu-id="b5cbe-286">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-286">**Inbound**</span></span>
  - <span data-ttu-id="b5cbe-287">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-287">**Outbound**</span></span>
  - <span data-ttu-id="b5cbe-288">**Dentro de la organización:** este recuento es para los mensajes enviados dentro de un inquilino; Es decir, el remitente abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de entrantes y salientes).</span><span class="sxs-lookup"><span data-stu-id="b5cbe-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="b5cbe-289">La vista de agregado y la vista de tabla de datos permiten un filtrado de 90 días.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="b5cbe-290">Si hace clic **en Filtrar,** puede filtrar tanto el gráfico como la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="b5cbe-291">En este gráfico se muestra el recuento de correo electrónico organizado por:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="b5cbe-292">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-292">**Total email**</span></span>
- <span data-ttu-id="b5cbe-293">**Correo electrónico después de la protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-293">**Email after edge protection**</span></span>
- <span data-ttu-id="b5cbe-294">**Correo electrónico después de antimalware, reputación del archivo, bloqueo de tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="b5cbe-295">**Correo electrónico después de la suplantación de identidad, reputación de la dirección URL, suplantación de marca, contra la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="b5cbe-296">**Correo electrónico después de correo no deseado, filtrado de correo masivo**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="b5cbe-297">**Correo electrónico después de la suplantación de usuario y dominio**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b5cbe-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="b5cbe-298">**Correo electrónico después de la detonación de archivos y direcciones URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b5cbe-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="b5cbe-299">**Correo electrónico detectado como benigno después de la protección posterior a la entrega (protección de tiempo de clic de url)**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="b5cbe-300"><sup>1 Defender</sup> solo para Office 365</span><span class="sxs-lookup"><span data-stu-id="b5cbe-300"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="b5cbe-301">Para ver el correo electrónico filtrado por EOP o Defender para Office 365 por separado, haga clic en el valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-301">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="b5cbe-302">La tabla de datos contiene la siguiente información, que se muestra en orden descendente de fecha:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="b5cbe-303">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-303">**Date**</span></span>
- <span data-ttu-id="b5cbe-304">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-304">**Total email**</span></span>
- <span data-ttu-id="b5cbe-305">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-305">**Edge protection**</span></span>
- <span data-ttu-id="b5cbe-306">**Antimalware, reputación del archivo, bloque de tipo de archivo:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="b5cbe-307">**Reputación del archivo:** mensajes filtrados debido a la identificación de un archivo adjunto por otros clientes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="b5cbe-308">**Bloque de tipo de archivo:** mensajes filtrados debido al tipo de archivo malintencionado identificado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="b5cbe-309">**Anti-phish, reputación de la dirección URL, suplantación de marca, anti-spoof**:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="b5cbe-310">**Reputación de la** dirección URL: mensajes filtrados debido a la identificación de la dirección URL por parte de otros clientes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="b5cbe-311">**Suplantación de marca:** mensajes filtrados debido al mensaje procedente de una marca conocida que suplanta a los remitentes.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="b5cbe-312">**Anti-spoof:** mensajes filtrados debido a que el mensaje intenta suplantar un dominio al que pertenece el destinatario o a un dominio que el remitente del mensaje no posee.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="b5cbe-313">**Contra correo no deseado, filtrado de correo masivo:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="b5cbe-314">**Filtrado de correo masivo:** mensajes filtrados debido a un intento de entregar correo masivo a sus destinatarios.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="b5cbe-315">**Suplantación de usuario y dominio (Defender para Office 365):**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-315">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="b5cbe-316">Suplantación de **usuario:** mensajes filtrados debido a un intento de suplantar a un usuario (remitente del mensaje) que se define en la configuración de protección de suplantación de una directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="b5cbe-317">**Suplantación** de dominio: mensajes filtrados debido a un intento de suplantar un dominio definido en la configuración de protección de suplantación de identidad de una directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="b5cbe-318">**Detonación de archivos y url (Defender para Office 365):**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-318">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="b5cbe-319">**Detonación de archivos:** mensajes filtrados por una directiva de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="b5cbe-320">**Detonación de dirección URL:** mensaje filtrado por una directiva de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="b5cbe-321">**Protección posterior a la entrega y ZAP (ATP) o ZAP (EOP):** ZAP indica purga automática de cero horas.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="b5cbe-322">Si selecciona una fila en la tabla de datos, en el menú desplegable se muestra un desglose adicional de los recuentos de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="b5cbe-323">**Exportar:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-323">**Export**:</span></span>

<span data-ttu-id="b5cbe-324">Después de hacer **clic en Exportar** en **Opciones,** puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="b5cbe-325">**Resumen (con datos de los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="b5cbe-326">**Detalles (con datos de los últimos 30 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="b5cbe-327">En **Fecha,** elija un intervalo y, a continuación, haga clic **en Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="b5cbe-328">Los datos de los filtros actuales se exportarán a un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="b5cbe-329">Cada archivo .csv exportado está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b5cbe-330">Si los datos contienen más de 150.000 filas, se crearán varios archivos .csv.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="b5cbe-331">Vista embudo en el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="b5cbe-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="b5cbe-332">Vista técnica del informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="b5cbe-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="b5cbe-333">La **vista Técnica es** similar a la vista **Embudo,** lo que proporciona detalles más granulares para las características configuradas de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="b5cbe-334">En el gráfico, puede ver cómo se clasifican los mensajes en las distintas etapas de la protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="b5cbe-335">Si hace clic en la pestaña **Vista** técnica, de forma predeterminada, esta vista contiene un gráfico y una tabla de datos configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="b5cbe-336">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="b5cbe-337">**Dirección:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-337">**Direction**:</span></span>

  - <span data-ttu-id="b5cbe-338">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-338">**Inbound**</span></span>
  - <span data-ttu-id="b5cbe-339">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-339">**Outbound**</span></span>
  - <span data-ttu-id="b5cbe-340">**Dentro de la organización:** este recuento es para los mensajes dentro de un espacio empresarial, es decir,</span><span class="sxs-lookup"><span data-stu-id="b5cbe-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="b5cbe-341">remitente abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de entrante y saliente)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="b5cbe-342">La vista de agregado y la vista de tabla de datos permiten un filtrado de 90 días.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="b5cbe-343">Si hace clic **en Filtrar,** puede filtrar tanto el gráfico como la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="b5cbe-344">En este gráfico se muestran los mensajes organizados en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="b5cbe-345">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-345">**Total email**</span></span>
- <span data-ttu-id="b5cbe-346">**Permitido perimetral y** **filtrado perimetral**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-346">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="b5cbe-347">**No es malware,** **detección de datos adjuntos seguros,** <sup>\*</sup> **detección del motor antimalware** y mensajes **de regla**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-347">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="b5cbe-348">**No suplantación** de identidad , **error de DMARC,** detección **de suplantación,** detección **de** suplantación de identidad y detección de **suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-348">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="b5cbe-349">**Sin detección con detonación de dirección URL** y **detonación de url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b5cbe-349">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="b5cbe-350">**Correo no deseado** y  **correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-350">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="b5cbe-351">**Correo electrónico no malintencionado,** **detección de vínculos seguros** <sup>\*</sup> y **ZAP**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-351">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="b5cbe-352"><sup>\*</sup> Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="b5cbe-352"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="b5cbe-353">Al mantener el puntero sobre una categoría del gráfico, puede ver el número de mensajes de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-353">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="b5cbe-354">La tabla de datos contiene la siguiente información, que se muestra en orden descendente:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-354">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="b5cbe-355">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-355">**Date**</span></span>
- <span data-ttu-id="b5cbe-356">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-356">**Total email**</span></span>
- <span data-ttu-id="b5cbe-357">**Edge filtrado**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-357">**Edge filtered**</span></span>
- <span data-ttu-id="b5cbe-358">**Motor antimalware, Datos adjuntos seguros, regla filtrada:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-358">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="b5cbe-359">**Regla filtrada:** mensajes filtrados debido a reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="b5cbe-359">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="b5cbe-360">**DMARC, suplantación, suplantación de identidad, phish filtered:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-360">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="b5cbe-361">**DMARC:** mensajes filtrados debido a que el mensaje no supera la comprobación de autenticación de DMARC.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-361">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="b5cbe-362">**Detección de detonación de url**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-362">**URL detonation detection**</span></span>
- <span data-ttu-id="b5cbe-363">**Filtrado contra correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-363">**Anti-spam filtered**</span></span>
- <span data-ttu-id="b5cbe-364">**ZAP quitado**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-364">**ZAP removed**</span></span>
- <span data-ttu-id="b5cbe-365">**Detección por vínculos seguros**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-365">**Detection by Safe Links**</span></span>

<span data-ttu-id="b5cbe-366">Si selecciona una fila en la tabla de datos, en el menú desplegable se muestra un desglose adicional de los recuentos de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-366">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="b5cbe-367">**Exportar:**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-367">**Export**:</span></span>

<span data-ttu-id="b5cbe-368">Al hacer **clic en** Exportar, **en Opciones** puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-368">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="b5cbe-369">**Resumen (con datos de los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-369">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="b5cbe-370">**Detalles (con datos de los últimos 30 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-370">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="b5cbe-371">En **Fecha,** elija un rango y, a continuación, haga clic **en Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-371">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="b5cbe-372">Los datos de los filtros actuales se exportarán a un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-372">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="b5cbe-373">Cada archivo .csv exportado está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-373">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b5cbe-374">Si los datos contienen más de 150.000 filas, se crearán varios archivos .csv.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-374">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="b5cbe-375">Vista técnica en el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="b5cbe-375">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="b5cbe-376">Informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="b5cbe-376">Sent and received email report</span></span>

<span data-ttu-id="b5cbe-377">El **informe de correo** electrónico enviado y recibido es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas las detecciones de correo no deseado, el malware y el correo electrónico identificado como "bueno".</span><span class="sxs-lookup"><span data-stu-id="b5cbe-377">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="b5cbe-378">La diferencia entre este informe y el [informe](#mailflow-status-report) de estado de flujo de correo es que este informe no incluye datos sobre los mensajes bloqueados por la protección perimetral. Es importante comprender que si se envía un mensaje a cinco destinatarios, lo contaremos como un mensaje.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-378">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="b5cbe-379">La vista de agregado y la vista de detalles del informe permiten un filtrado de 90 días.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-379">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="b5cbe-380">Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Correo electrónico \>  enviado **y recibido.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-380">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="b5cbe-381">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="b5cbe-381">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget Correo electrónico enviado y recibido en el panel informes](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="b5cbe-383">Vista de informe para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="b5cbe-383">Report view for the Sent and received email report</span></span>

<span data-ttu-id="b5cbe-384">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-384">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b5cbe-385">**Dividir por: Tipo**: El gráfico muestra todas las categorías disponibles:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-385">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="b5cbe-386">**Total**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-386">**Total**</span></span>
  - <span data-ttu-id="b5cbe-387">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-387">**Good mail**</span></span>
  - <span data-ttu-id="b5cbe-388">**Malware (antimalware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-388">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="b5cbe-389">**Detecciones de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-389">**Spam detections**</span></span>
  - <span data-ttu-id="b5cbe-390">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-390">**Rule messages**</span></span>
  - <span data-ttu-id="b5cbe-391">**Malware avanzado** (Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-391">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="b5cbe-392">Al mantener el puntero sobre un día (punto de datos) en el gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-392">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vista de tipo en el informe de correo electrónico enviado y recibido](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="b5cbe-394">**Dividir por: Dirección:** el gráfico muestra **datos totales,** **entrantes** **y salientes.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-394">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="b5cbe-395">Al mantener el puntero sobre un día (punto de datos) en el gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-395">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vista de dirección en el informe de correo electrónico enviado y recibido](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="b5cbe-397">**Explorar en profundidad** \> **Malware (antimalware):** esta selección le lleva a las detecciones [de malware en el informe de correo electrónico.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-397">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="b5cbe-398">**Explorar en profundidad** \> **Detecciones de correo** no deseado): esta selección le lleva al informe de [detecciones de correo no deseado.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-398">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="b5cbe-399">Si hace clic **en Filtros** en una vista de informe, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-399">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b5cbe-400">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-400">**Start date** and **End date**</span></span>
- <span data-ttu-id="b5cbe-401">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="b5cbe-401">Direction values</span></span>
- <span data-ttu-id="b5cbe-402">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="b5cbe-402">Type values</span></span>

<span data-ttu-id="b5cbe-403">Para volver a la vista informe, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-403">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="b5cbe-404">Vista de tabla de detalles para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="b5cbe-404">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="b5cbe-405">Si hace clic **en Ver tabla de detalles** en la vista Dividir **por:** Dirección o Dividir **por:** Vista Dirección, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-405">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="b5cbe-406">**Fecha (UTC)**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-406">**Date (UTC)**</span></span>
- <span data-ttu-id="b5cbe-407">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-407">**Type**</span></span>
- <span data-ttu-id="b5cbe-408">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-408">**Direction**</span></span>
- <span data-ttu-id="b5cbe-409">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-409">**Message count**</span></span>

<span data-ttu-id="b5cbe-410">Si hace clic **en Filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-410">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b5cbe-411">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-411">**Start date** and **End date**</span></span>
- <span data-ttu-id="b5cbe-412">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="b5cbe-412">Direction values</span></span>
- <span data-ttu-id="b5cbe-413">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="b5cbe-413">Type values</span></span>

<span data-ttu-id="b5cbe-414">Para volver a la vista informe, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-414">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="b5cbe-415">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="b5cbe-415">Top senders and recipients report</span></span>

<span data-ttu-id="b5cbe-416">El **informe de remitentes y destinatarios principales** es un gráfico circular que muestra los principales remitentes y destinatarios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="b5cbe-417">Para ver el informe, abra el Centro de  seguridad [& cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Principales \>  **remitentes y destinatarios.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-417">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="b5cbe-418">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="b5cbe-418">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget Remitentes y destinatarios principales en el panel informes](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="b5cbe-420">Vista de informe para el informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="b5cbe-420">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="b5cbe-421">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-421">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b5cbe-422">**Mostrar datos de \> remitentes principales de correo**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-422">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="b5cbe-423">**Mostrar datos para \> los destinatarios de correo principales**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-423">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="b5cbe-424">**Mostrar datos para los \> destinatarios principales de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-424">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="b5cbe-425">**Mostrar datos para \> Destinatarios principales de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-425">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="b5cbe-426">**Mostrar datos para \> los principales destinatarios de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-426">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="b5cbe-427">La composición del gráfico circular cambia en función de estas selecciones.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-427">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="b5cbe-428">Al pasar el puntero sobre una plataforma en el gráfico circular, puede ver un recuento de mensajes enviados o recibidos.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-428">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="b5cbe-429">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con fecha **de inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-429">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico circular en la vista Informe en el informe de remitentes y destinatarios principales](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="b5cbe-431">Vista de tabla de detalles para el informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="b5cbe-431">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="b5cbe-432">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-432">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b5cbe-433">**Mostrar datos de \> remitentes principales de correo**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-433">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="b5cbe-434">**Principales remitentes de correo**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-434">**Top mail senders**</span></span>
  - <span data-ttu-id="b5cbe-435">**Count**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-435">**Count**</span></span>

- <span data-ttu-id="b5cbe-436">**Mostrar datos para \> los destinatarios principales de correo**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-436">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="b5cbe-437">**Principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-437">**Top mail recipients**</span></span>
  - <span data-ttu-id="b5cbe-438">**Count**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-438">**Count**</span></span>

- <span data-ttu-id="b5cbe-439">**Mostrar datos para los \> destinatarios principales de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-439">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="b5cbe-440">**Principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-440">**Top spam recipients**</span></span>
  - <span data-ttu-id="b5cbe-441">**Count**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-441">**Count**</span></span>

- <span data-ttu-id="b5cbe-442">**Mostrar datos para \> Principales destinatarios de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="b5cbe-442">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="b5cbe-443">**Principales destinatarios de malware**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-443">**Top malware recipients**</span></span>
  - <span data-ttu-id="b5cbe-444">**Count**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-444">**Count**</span></span>

- <span data-ttu-id="b5cbe-445">**Mostrar datos para \> los principales destinatarios de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-445">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="b5cbe-446">**Principales destinatarios de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-446">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="b5cbe-447">**Count**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-447">**Count**</span></span>

<span data-ttu-id="b5cbe-448">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con fecha de **inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-448">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b5cbe-449">Para volver a la vista informe, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-449">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="b5cbe-450">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="b5cbe-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="b5cbe-451">Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="b5cbe-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b5cbe-452">**Administración de organizaciones**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-452">**Organization Management**</span></span>
- <span data-ttu-id="b5cbe-453">**Administrador de seguridad**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-453">**Security Administrator**</span></span>
- <span data-ttu-id="b5cbe-454">**Lector de seguridad**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-454">**Security Reader**</span></span>
- <span data-ttu-id="b5cbe-455">**Lector global**</span><span class="sxs-lookup"><span data-stu-id="b5cbe-455">**Global Reader**</span></span>

<span data-ttu-id="b5cbe-456">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b5cbe-456">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b5cbe-457">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5cbe-457">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b5cbe-458">Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="b5cbe-458">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b5cbe-459">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b5cbe-459">Related topics</span></span>

[<span data-ttu-id="b5cbe-460">Informes inteligentes y reportes en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b5cbe-460">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="b5cbe-461">Reportes de flujo de Correo en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b5cbe-461">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="b5cbe-462">Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b5cbe-462">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="b5cbe-463">Ver informes de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="b5cbe-463">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
