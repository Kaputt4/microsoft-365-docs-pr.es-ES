---
title: Ver informes de seguridad de correo electrónico
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
description: Los administradores pueden aprender a buscar y usar los informes de seguridad de correo electrónico que están disponibles en el portal Microsoft 365 Defender correo electrónico.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ad90038ac818f9759768d0d00019393205b03f3
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083529"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="c5d13-103">Ver informes de seguridad de correo electrónico en el portal Microsoft 365 Defender correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c5d13-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c5d13-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="c5d13-104">**Applies to**</span></span>
- [<span data-ttu-id="c5d13-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c5d13-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c5d13-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c5d13-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c5d13-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5d13-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c5d13-108">Hay una variedad de informes disponibles en el portal de Microsoft 365 Defender para ayudarle a ver cómo las características de seguridad del correo electrónico, como el correo no deseado, antimalware y las características de cifrado en Microsoft 365 protegen su <https://security.microsoft.com> organización.</span><span class="sxs-lookup"><span data-stu-id="c5d13-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="c5d13-109">Si tiene los [permisos](#what-permissions-are-needed-to-view-these-reports)necesarios, puede ver estos informes en el  portal de Microsoft 365 Defender yendo a Informes de correo electrónico & colaboración Correo electrónico & informes \>  \> **de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c5d13-110">Para ir directamente a la página **Informes de colaboración & correo** electrónico, abra <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="c5d13-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Página & informes de colaboración de correo electrónico en el portal de Microsoft 365 Defender web](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="c5d13-112">Algunos de los informes de la página Informes de **colaboración & correo** electrónico requieren Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="c5d13-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="c5d13-113">Para obtener información acerca de estos informes, vea [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="c5d13-114">Los informes relacionados con el flujo de correo se encuentran ahora en el Centro Exchange administración (EAC).</span><span class="sxs-lookup"><span data-stu-id="c5d13-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="c5d13-115">Para obtener más información acerca de estos informes, vea Informes de flujo de correo [en el nuevo centro Exchange administración.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="c5d13-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="c5d13-116">Informe de usuarios comprometidos</span><span class="sxs-lookup"><span data-stu-id="c5d13-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="c5d13-117">Este informe está disponible en Microsoft 365 organizaciones con Exchange Online buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="c5d13-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="c5d13-118">No está disponible en organizaciones independientes Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="c5d13-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="c5d13-119">El **informe Usuarios comprometidos** muestra el número de  cuentas  de usuario que se marcaron como Sospechosas o Restringidas en los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="c5d13-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="c5d13-120">Las cuentas en cualquiera de estos estados son problemáticas o incluso están en peligro.</span><span class="sxs-lookup"><span data-stu-id="c5d13-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="c5d13-121">Con el uso frecuente, puede usar el informe para detectar picos e incluso tendencias en cuentas sospechosas o restringidas.</span><span class="sxs-lookup"><span data-stu-id="c5d13-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="c5d13-122">Para obtener más información acerca de los usuarios en peligro, vea [Responder a una cuenta de correo electrónico comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="c5d13-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Usuarios comprometidos en la página Informes de colaboración & correo electrónico](../../media/compromised-users-report-widget.png)

<span data-ttu-id="c5d13-124">La vista de agregado muestra los datos de los últimos 90 días y la vista de detalles muestra los datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="c5d13-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="c5d13-125">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c5d13-126">En la página **Informes de colaboración &** correo electrónico, busque **Usuarios** en peligro y, a continuación, haga clic en **Ver detalles.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="c5d13-127">Para ir directamente al informe, abra <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="c5d13-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="c5d13-128">En la **página Usuarios** en peligro, puede filtrar tanto  el gráfico como la tabla de detalles haciendo clic en Filtrar y seleccionando uno o varios de los siguientes valores en el menú desplegable que aparece:</span><span class="sxs-lookup"><span data-stu-id="c5d13-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="c5d13-129">**Date (UTC):** **Fecha de inicio y** fecha de **finalización.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="c5d13-130">**Actividad**:</span><span class="sxs-lookup"><span data-stu-id="c5d13-130">**Activity**:</span></span>
  - <span data-ttu-id="c5d13-131">**Sospechoso:** la cuenta de usuario ha enviado un correo electrónico sospechoso y corre el riesgo de que se le restringa el envío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c5d13-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="c5d13-132">**Restringido:** la cuenta de usuario se ha restringido para enviar correo electrónico debido a patrones altamente sospechosos.</span><span class="sxs-lookup"><span data-stu-id="c5d13-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="c5d13-133">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![Vista Informe en el informe usuarios comprometidos](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="c5d13-135">En la tabla de detalles debajo del gráfico, puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="c5d13-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="c5d13-136">**Tiempo de creación**</span><span class="sxs-lookup"><span data-stu-id="c5d13-136">**Creation time**</span></span>
- <span data-ttu-id="c5d13-137">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="c5d13-137">**User ID**</span></span>
- <span data-ttu-id="c5d13-138">**Action**</span><span class="sxs-lookup"><span data-stu-id="c5d13-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="c5d13-139">Exchange de regla de transporte</span><span class="sxs-lookup"><span data-stu-id="c5d13-139">Exchange transport rule report</span></span>

<span data-ttu-id="c5d13-140">El **Exchange de regla de** transporte muestra el efecto de las reglas de flujo de correo (también conocidas como reglas de transporte) en los mensajes entrantes y salientes de la organización.</span><span class="sxs-lookup"><span data-stu-id="c5d13-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="c5d13-141">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c5d13-142">En la página **Informes de colaboración &** correo electrónico, busque Exchange de transporte **y, a** continuación, haga clic en Ver **detalles.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="c5d13-143">Para ir directamente al informe, abra <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="c5d13-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Exchange de regla de transporte en la página Informes de colaboración & correo electrónico](../../media/transport-rule-report-widget.png)

<span data-ttu-id="c5d13-145">En la página Exchange informe de reglas de **transporte,** los gráficos y datos disponibles se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="c5d13-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="c5d13-146">Desglose del gráfico por dirección</span><span class="sxs-lookup"><span data-stu-id="c5d13-146">Chart breakdown by Direction</span></span>

![Vista Dirección para las Exchange de transporte en el informe Exchange regla de transporte](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="c5d13-148">Si selecciona Desglose **de gráficos por dirección,** los siguientes gráficos estarán disponibles:</span><span class="sxs-lookup"><span data-stu-id="c5d13-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="c5d13-149">**Ver datos por Exchange de transporte:** el  número **de** mensajes entrantes y salientes que se vieron afectados por las reglas de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="c5d13-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="c5d13-150">**Ver datos por DLP Exchange** de transporte:  el  número de mensajes entrantes y salientes que se vieron afectados por las reglas de flujo de correo de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="c5d13-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="c5d13-151">La siguiente información se muestra en la tabla de detalles debajo del gráfico:</span><span class="sxs-lookup"><span data-stu-id="c5d13-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="c5d13-152">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c5d13-152">**Date**</span></span>
- <span data-ttu-id="c5d13-153">**Directiva DLP** (**Ver datos por DLP Exchange reglas de transporte)**</span><span class="sxs-lookup"><span data-stu-id="c5d13-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="c5d13-154">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="c5d13-154">**Transport rule**</span></span>
- <span data-ttu-id="c5d13-155">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="c5d13-155">**Subject**</span></span>
- <span data-ttu-id="c5d13-156">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-156">**Sender address**</span></span>
- <span data-ttu-id="c5d13-157">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="c5d13-157">**Recipient address**</span></span>
- <span data-ttu-id="c5d13-158">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="c5d13-158">**Severity**</span></span>
- <span data-ttu-id="c5d13-159">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-159">**Direction**</span></span>

<span data-ttu-id="c5d13-160">Puede filtrar tanto el gráfico como  la tabla de detalles haciendo clic en Filtrar y seleccionando uno o varios de los siguientes valores en el menú desplegable que aparece:</span><span class="sxs-lookup"><span data-stu-id="c5d13-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="c5d13-161">**Fecha (UTC) Fecha** **de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="c5d13-162">**Dirección:** **saliente** y **entrante**</span><span class="sxs-lookup"><span data-stu-id="c5d13-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="c5d13-163">**Gravedad:** **gravedad alta,** **gravedad media** y **gravedad baja**</span><span class="sxs-lookup"><span data-stu-id="c5d13-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="c5d13-164">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="c5d13-165">Desglose del gráfico por gravedad</span><span class="sxs-lookup"><span data-stu-id="c5d13-165">Chart breakdown by Severity</span></span>

![Vista gravedad de las Exchange de transporte en el informe Exchange regla de transporte](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="c5d13-167">Si selecciona Desglose **de gráficos por gravedad,** los siguientes gráficos están disponibles:</span><span class="sxs-lookup"><span data-stu-id="c5d13-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="c5d13-168">**Ver datos por Exchange de transporte:** el número de mensajes de gravedad **alta,** gravedad media y **gravedad** baja.</span><span class="sxs-lookup"><span data-stu-id="c5d13-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="c5d13-169">El nivel de gravedad se establece como una acción en la regla (**Auditar** esta regla con el nivel de gravedad o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="c5d13-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="c5d13-170">Para obtener más información, vea [Acciones de regla de flujo de correo en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="c5d13-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="c5d13-171">**Ver datos por DLP Exchange** de transporte: el número de mensajes  de gravedad **alta,** media y de gravedad baja que se vieron afectados por las reglas de flujo de correo DLP.</span><span class="sxs-lookup"><span data-stu-id="c5d13-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="c5d13-172">La siguiente información se muestra en la tabla de detalles debajo del gráfico:</span><span class="sxs-lookup"><span data-stu-id="c5d13-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="c5d13-173">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c5d13-173">**Date**</span></span>
- <span data-ttu-id="c5d13-174">**Directiva DLP** (**Ver datos por DLP Exchange reglas de transporte)**</span><span class="sxs-lookup"><span data-stu-id="c5d13-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="c5d13-175">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="c5d13-175">**Transport rule**</span></span>
- <span data-ttu-id="c5d13-176">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="c5d13-176">**Subject**</span></span>
- <span data-ttu-id="c5d13-177">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-177">**Sender address**</span></span>
- <span data-ttu-id="c5d13-178">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="c5d13-178">**Recipient address**</span></span>
- <span data-ttu-id="c5d13-179">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="c5d13-179">**Severity**</span></span>
- <span data-ttu-id="c5d13-180">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-180">**Direction**</span></span>

<span data-ttu-id="c5d13-181">Puede filtrar tanto el gráfico como  la tabla de detalles haciendo clic en Filtrar y seleccionando uno o varios de los siguientes valores en el menú desplegable que aparece:</span><span class="sxs-lookup"><span data-stu-id="c5d13-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="c5d13-182">**Fecha (UTC) Fecha** **de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="c5d13-183">**Dirección:** **saliente** y **entrante**</span><span class="sxs-lookup"><span data-stu-id="c5d13-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="c5d13-184">**Gravedad:** **gravedad alta,** **gravedad media** y **gravedad baja**</span><span class="sxs-lookup"><span data-stu-id="c5d13-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="c5d13-185">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="c5d13-186">Informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="c5d13-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="c5d13-187">El **informe de reenvío** ya está disponible en el EAC.</span><span class="sxs-lookup"><span data-stu-id="c5d13-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="c5d13-188">Para obtener más información, vea Informe de mensajes reenviados [automáticamente en el nuevo EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span><span class="sxs-lookup"><span data-stu-id="c5d13-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="c5d13-189">Informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="c5d13-189">Mailflow status report</span></span>

<span data-ttu-id="c5d13-190">El **informe de** estado de flujo de correo es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, las detecciones de correo no deseado, el malware, el correo electrónico identificado como "bueno" y la información sobre el correo electrónico permitido o bloqueado en el perímetro.</span><span class="sxs-lookup"><span data-stu-id="c5d13-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="c5d13-191">Este es el único informe que contiene información de protección perimetral y muestra cuánto correo electrónico se bloquea antes de que se le permita entrar en el servicio para su evaluación por parte de Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="c5d13-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="c5d13-192">Es importante comprender que si un mensaje se envía a cinco destinatarios, lo contamos como cinco mensajes diferentes y no un mensaje.</span><span class="sxs-lookup"><span data-stu-id="c5d13-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="c5d13-193">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c5d13-194">En la página **Informes de colaboración &** correo electrónico, busque Resumen de estado de **flujo** de correo y, a continuación, haga clic en **Ver detalles.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="c5d13-195">Para ir directamente al informe, abra <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="c5d13-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Widget de resumen de estado de flujo de correo en la página Informes de colaboración & correo electrónico](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="c5d13-197">Vista de tipo para el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="c5d13-197">Type view for the Mailflow status report</span></span>

![Vista De tipo en el informe de estado de flujo de correo](../../media/mail-flow-status-report-type-view.png)

<span data-ttu-id="c5d13-199">En la **página Informe de estado de flujo de** correo, la **pestaña** Tipo está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c5d13-199">On the **Mailflow status report** page, the **Type** tab is selected by default.</span></span> <span data-ttu-id="c5d13-200">De forma predeterminada, esta vista contiene un gráfico y una tabla de detalles que está configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5d13-200">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="c5d13-201">**Fecha (UTC)** Los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="c5d13-201">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="c5d13-202">**Dirección del correo**:</span><span class="sxs-lookup"><span data-stu-id="c5d13-202">**Mail direction**:</span></span>
  - <span data-ttu-id="c5d13-203">**Entrante**</span><span class="sxs-lookup"><span data-stu-id="c5d13-203">**Inbound**</span></span>
  - <span data-ttu-id="c5d13-204">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-204">**Outbound**</span></span>
  - <span data-ttu-id="c5d13-205">**Intra-org:** este recuento es para mensajes dentro de un espacio empresarial, es decir,</span><span class="sxs-lookup"><span data-stu-id="c5d13-205">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="c5d13-206">sender abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de **Entrante** y **Saliente**)</span><span class="sxs-lookup"><span data-stu-id="c5d13-206">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="c5d13-207">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="c5d13-207">**Type**:</span></span>
  - <span data-ttu-id="c5d13-208">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="c5d13-208">**Good mail**</span></span>
  - <span data-ttu-id="c5d13-209">**Malware**</span><span class="sxs-lookup"><span data-stu-id="c5d13-209">**Malware**</span></span>
  - <span data-ttu-id="c5d13-210">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-210">**Spam**</span></span>
  - <span data-ttu-id="c5d13-211">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="c5d13-211">**Edge protection**</span></span>
  - <span data-ttu-id="c5d13-212">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="c5d13-212">**Rule messages**</span></span>
  - <span data-ttu-id="c5d13-213">**Correo de suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="c5d13-213">**Phishing email**</span></span>
- <span data-ttu-id="c5d13-214">**Dominio**: **Todos**</span><span class="sxs-lookup"><span data-stu-id="c5d13-214">**Domain**: **All**</span></span>

<span data-ttu-id="c5d13-215">El gráfico está organizado por los **valores Type.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-215">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="c5d13-216">Puede cambiar estos filtros haciendo clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-216">You can change these filters by clicking **Filter**.</span></span>

<span data-ttu-id="c5d13-217">La siguiente información se muestra en la tabla de detalles debajo del gráfico:</span><span class="sxs-lookup"><span data-stu-id="c5d13-217">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="c5d13-218">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-218">**Direction**</span></span>
- <span data-ttu-id="c5d13-219">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c5d13-219">**Type**</span></span>
- <span data-ttu-id="c5d13-220">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="c5d13-220">**24 hours**</span></span>
- <span data-ttu-id="c5d13-221">**3 días**</span><span class="sxs-lookup"><span data-stu-id="c5d13-221">**3 days**</span></span>
- <span data-ttu-id="c5d13-222">**7 días**</span><span class="sxs-lookup"><span data-stu-id="c5d13-222">**7 days**</span></span>
- <span data-ttu-id="c5d13-223">**15 días**</span><span class="sxs-lookup"><span data-stu-id="c5d13-223">**15 days**</span></span>
- <span data-ttu-id="c5d13-224">**30 días**</span><span class="sxs-lookup"><span data-stu-id="c5d13-224">**30 days**</span></span>

<span data-ttu-id="c5d13-225">Si hace clic **en Elegir una categoría para obtener más información,** puede seleccionar entre los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c5d13-225">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="c5d13-226">**Correo electrónico de suplantación** de identidad : esta selección le lleva al informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="c5d13-226">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="c5d13-227">**Malware en el correo** electrónico: esta selección le lleva al informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="c5d13-227">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="c5d13-228">**Detecciones de correo** no deseado: esta selección le lleva al informe [Detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="c5d13-228">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="c5d13-229">**Correo no deseado bloqueado** perimetral: esta selección le lleva al informe [Detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="c5d13-229">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="c5d13-230">Exportar desde la vista Tipo</span><span class="sxs-lookup"><span data-stu-id="c5d13-230">Export from Type view</span></span>

<span data-ttu-id="c5d13-231">Para la vista de detalles, solo puede exportar datos durante un día.</span><span class="sxs-lookup"><span data-stu-id="c5d13-231">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="c5d13-232">Por lo tanto, si desea exportar datos durante 7 días, debe realizar 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="c5d13-232">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="c5d13-233">Cada archivo .csv exportada está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="c5d13-233">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="c5d13-234">Si los datos de ese día contienen más de 150.000 filas, se crearán varios .csv archivos.</span><span class="sxs-lookup"><span data-stu-id="c5d13-234">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="c5d13-235">Vista Dirección del informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="c5d13-235">Direction view for the Mailflow status report</span></span>

![Vista Dirección en el informe de estado de flujo de correo](../../media/mail-flow-status-report-direction-view.png)

<span data-ttu-id="c5d13-237">Si hace clic en la **pestaña Dirección,** se usan los mismos filtros predeterminados de la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="c5d13-237">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="c5d13-238">El gráfico está organizado por valores **direction.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-238">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="c5d13-239">Puede cambiar estos filtros haciendo clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-239">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="c5d13-240">Se usan los mismos filtros de **la vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="c5d13-240">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="c5d13-241">La tabla de detalles contiene la misma información de la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="c5d13-241">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="c5d13-242">La **categoría Elegir una categoría para obtener más detalles** sobre las selecciones y el comportamiento disponibles son los mismos que la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="c5d13-242">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="c5d13-243">Exportar desde la vista Dirección</span><span class="sxs-lookup"><span data-stu-id="c5d13-243">Export from Direction view</span></span>

<span data-ttu-id="c5d13-244">Para la vista de detalles, solo puede exportar datos durante un día.</span><span class="sxs-lookup"><span data-stu-id="c5d13-244">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="c5d13-245">Por lo tanto, si desea exportar datos durante 7 días, debe realizar 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="c5d13-245">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="c5d13-246">Cada archivo .csv exportada está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="c5d13-246">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="c5d13-247">Si los datos de ese día contienen más de 150.000 filas, se crearán varios .csv archivos.</span><span class="sxs-lookup"><span data-stu-id="c5d13-247">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="c5d13-248">Vista embudo para el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="c5d13-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="c5d13-249">La **vista Embudo** muestra cómo las características de protección contra amenazas de correo electrónico de Microsoft filtran el correo electrónico entrante y saliente en su organización.</span><span class="sxs-lookup"><span data-stu-id="c5d13-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="c5d13-250">Proporciona detalles sobre el recuento total de correo electrónico y cómo afectan a este recuento las características de protección contra amenazas configuradas, como la protección perimetral, el antimalware, la suplantación de identidad (phishing), el correo no deseado y la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="c5d13-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

![Vista embudo en el informe de estado de flujo de correo](../../media/mail-flow-status-report-funnel-view.png)

<span data-ttu-id="c5d13-252">Si hace clic en la pestaña **Embudo,** de forma predeterminada, esta vista contiene un gráfico y una tabla de detalles configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5d13-252">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="c5d13-253">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="c5d13-253">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="c5d13-254">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="c5d13-254">**Direction**:</span></span>
  - <span data-ttu-id="c5d13-255">**Entrante**</span><span class="sxs-lookup"><span data-stu-id="c5d13-255">**Inbound**</span></span>
  - <span data-ttu-id="c5d13-256">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-256">**Outbound**</span></span>
  - <span data-ttu-id="c5d13-257">**Intra-org:** este recuento es para los mensajes enviados dentro de un espacio empresarial; Es decir, el remitente abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de Entrante y Saliente).</span><span class="sxs-lookup"><span data-stu-id="c5d13-257">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="c5d13-258">La vista de agregado y la vista de tabla de detalles permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="c5d13-258">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="c5d13-259">Puede cambiar estos filtros haciendo clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-259">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="c5d13-260">Se usan los mismos filtros de **la vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="c5d13-260">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="c5d13-261">Este gráfico muestra el recuento de correo electrónico organizado por:</span><span class="sxs-lookup"><span data-stu-id="c5d13-261">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="c5d13-262">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="c5d13-262">**Total email**</span></span>
- <span data-ttu-id="c5d13-263">**Correo electrónico después de la protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="c5d13-263">**Email after edge protection**</span></span>
- <span data-ttu-id="c5d13-264">**Correo electrónico después de la regla de transporte** (regla de flujo de correo)</span><span class="sxs-lookup"><span data-stu-id="c5d13-264">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="c5d13-265">**Correo electrónico después de antimalware, reputación de archivo, bloqueo de tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="c5d13-265">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="c5d13-266">**Correo electrónico después de anti phish, reputación url, suplantación de marca, anti suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="c5d13-266">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="c5d13-267">**Correo electrónico después de correo no deseado, filtrado masivo de correo**</span><span class="sxs-lookup"><span data-stu-id="c5d13-267">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="c5d13-268">**Correo electrónico después de la suplantación de usuario y dominio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c5d13-268">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="c5d13-269">**Email after file and URL detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c5d13-269">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="c5d13-270">**Correo electrónico detectado como benigno después de la protección posterior a la entrega (url click time protection)**</span><span class="sxs-lookup"><span data-stu-id="c5d13-270">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="c5d13-271"><sup>\*</sup>Solo defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c5d13-271"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="c5d13-272">Para ver el correo electrónico filtrado por EOP o Defender Office 365 por separado, haga clic en el valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="c5d13-272">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="c5d13-273">La tabla de detalles contiene la siguiente información, que se muestra en orden de fecha descendente:</span><span class="sxs-lookup"><span data-stu-id="c5d13-273">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="c5d13-274">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c5d13-274">**Date**</span></span>
- <span data-ttu-id="c5d13-275">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="c5d13-275">**Total email**</span></span>
- <span data-ttu-id="c5d13-276">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="c5d13-276">**Edge protection**</span></span>
- <span data-ttu-id="c5d13-277">**Antimalware, reputación de archivo, bloque de tipo de archivo:**</span><span class="sxs-lookup"><span data-stu-id="c5d13-277">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="c5d13-278">**Reputación del archivo:** mensajes filtrados debido a la identificación de un archivo adjunto por otros clientes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5d13-278">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="c5d13-279">**Bloque de tipo de** archivo: mensajes filtrados debido al tipo de archivo malintencionado identificado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c5d13-279">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="c5d13-280">**Anti-phish, reputación url, suplantación de marca, suplantación de identidad:**</span><span class="sxs-lookup"><span data-stu-id="c5d13-280">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="c5d13-281">**Reputación de la dirección URL:** mensajes filtrados debido a la identificación de la dirección URL por otros clientes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5d13-281">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="c5d13-282">**Suplantación de marca:** mensajes filtrados debido al mensaje procedente de remitentes de suplantación de marca conocidos.</span><span class="sxs-lookup"><span data-stu-id="c5d13-282">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="c5d13-283">**Anti-spoof:** mensajes filtrados debido a que el mensaje intenta suplantar un dominio al que pertenece el destinatario o un dominio que el remitente del mensaje no posee.</span><span class="sxs-lookup"><span data-stu-id="c5d13-283">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="c5d13-284">**Antispam, filtrado masivo de correo:**</span><span class="sxs-lookup"><span data-stu-id="c5d13-284">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="c5d13-285">**Filtrado masivo de correo:** mensajes filtrados según el umbral de nivel de queja masiva (BCL) en una directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c5d13-285">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="c5d13-286">**Suplantación de usuario y dominio (Defender para Office 365):**</span><span class="sxs-lookup"><span data-stu-id="c5d13-286">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="c5d13-287">Suplantación de **usuario:** mensajes filtrados debido a un intento de suplantar a un usuario (remitente de mensajes) que se define en la configuración de protección de suplantación de una directiva contra suplantación.</span><span class="sxs-lookup"><span data-stu-id="c5d13-287">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="c5d13-288">**Suplantación** de dominio: mensajes filtrados debido a un intento de suplantar un dominio definido en la configuración de protección de suplantación de una directiva contra suplantación.</span><span class="sxs-lookup"><span data-stu-id="c5d13-288">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="c5d13-289">**Detonación de archivos y direcciones URL (Defender para Office 365):**</span><span class="sxs-lookup"><span data-stu-id="c5d13-289">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="c5d13-290">**Detonación de archivos:** mensajes filtrados por una directiva Caja fuerte datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="c5d13-290">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="c5d13-291">**Detonación de dirección URL:** mensaje filtrado por una directiva Caja fuerte vínculos.</span><span class="sxs-lookup"><span data-stu-id="c5d13-291">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="c5d13-292">Protección posterior a la entrega y **ZAP (ATP) o ZAP (EOP):** purga automática de hora cero (ZAP) para malware, correo no deseado y phishing.</span><span class="sxs-lookup"><span data-stu-id="c5d13-292">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="c5d13-293">Si selecciona una fila en la tabla de detalles, se muestra un desglose adicional de los recuentos de correo electrónico en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="c5d13-293">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="c5d13-294">Exportar desde la vista Embudo</span><span class="sxs-lookup"><span data-stu-id="c5d13-294">Export from Funnel view</span></span>

<span data-ttu-id="c5d13-295">Después de hacer **clic en Exportar** en **Opciones,** puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c5d13-295">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="c5d13-296">**Resumen (con datos de los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="c5d13-296">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="c5d13-297">**Detalles (con datos de los últimos 30 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="c5d13-297">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="c5d13-298">En **Fecha**, elija un rango y, a continuación, haga clic **en Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-298">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="c5d13-299">Los datos de los filtros actuales se exportarán a un .csv archivo.</span><span class="sxs-lookup"><span data-stu-id="c5d13-299">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="c5d13-300">Cada archivo .csv exportada está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="c5d13-300">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="c5d13-301">Si los datos contienen más de 150 000 filas, se crearán varios .csv archivos.</span><span class="sxs-lookup"><span data-stu-id="c5d13-301">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="c5d13-302">Vista técnica del informe de estado del flujo de correo</span><span class="sxs-lookup"><span data-stu-id="c5d13-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="c5d13-303">La **vista Tech es** similar a la vista **Embudo,** lo que proporciona más detalles pormenorizados para las características de protección contra amenazas configuradas.</span><span class="sxs-lookup"><span data-stu-id="c5d13-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="c5d13-304">En el gráfico, puede ver cómo se clasifican los mensajes en las distintas etapas de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="c5d13-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="c5d13-305">Si hace clic en la **pestaña Vista técnica,** de forma predeterminada, esta vista contiene un gráfico y una tabla de detalles configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5d13-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="c5d13-306">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="c5d13-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="c5d13-307">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="c5d13-307">**Direction**:</span></span>
  - <span data-ttu-id="c5d13-308">**Entrante**</span><span class="sxs-lookup"><span data-stu-id="c5d13-308">**Inbound**</span></span>
  - <span data-ttu-id="c5d13-309">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-309">**Outbound**</span></span>
  - <span data-ttu-id="c5d13-310">**Intra-org:** este recuento es para mensajes dentro de un espacio empresarial, es decir,</span><span class="sxs-lookup"><span data-stu-id="c5d13-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="c5d13-311">remitente abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de Entrante y Saliente)</span><span class="sxs-lookup"><span data-stu-id="c5d13-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="c5d13-312">La vista de agregado y la vista de tabla de detalles permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="c5d13-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="c5d13-313">Puede cambiar estos filtros haciendo clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="c5d13-314">Se usan los mismos filtros de **la vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="c5d13-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="c5d13-315">En este gráfico se muestran los mensajes organizados en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="c5d13-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="c5d13-316">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="c5d13-316">**Total email**</span></span>
- <span data-ttu-id="c5d13-317">**Edge allow** y **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="c5d13-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="c5d13-318">**Regla de transporte permitido** y **regla de transporte filtrada** (reglas de flujo de correo)</span><span class="sxs-lookup"><span data-stu-id="c5d13-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="c5d13-319">**No malware,** **detección Caja fuerte datos adjuntos** y detección de motores <sup>\*</sup> **antimalware**</span><span class="sxs-lookup"><span data-stu-id="c5d13-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="c5d13-320">**No phish**, **error DMARC,** **detección de suplantación,** detección <sup>\*</sup> de **suplantación** y detección **de suplantación** de identidad</span><span class="sxs-lookup"><span data-stu-id="c5d13-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="c5d13-321">**No hay detección con detonación de dirección URL** y **detonación de url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c5d13-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="c5d13-322">**No correo no** deseado y  **correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="c5d13-323">**Correo electrónico no malintencionado,** **Caja fuerte de detección de vínculos y** <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="c5d13-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="c5d13-324"><sup>\*</sup>Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c5d13-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="c5d13-325">Al pasar el mouse sobre una categoría del gráfico, puede ver el número de mensajes de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="c5d13-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="c5d13-326">La tabla de detalles contiene la siguiente información, que se muestra en orden de fecha descendente:</span><span class="sxs-lookup"><span data-stu-id="c5d13-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="c5d13-327">**Fecha (UTC)**</span><span class="sxs-lookup"><span data-stu-id="c5d13-327">**Date (UTC)**</span></span>
- <span data-ttu-id="c5d13-328">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="c5d13-328">**Total email**</span></span>
- <span data-ttu-id="c5d13-329">**Perímetro filtrado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-329">**Edge filtered**</span></span>
- <span data-ttu-id="c5d13-330">**Mensajes de regla:** mensajes filtrados debido a reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="c5d13-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="c5d13-331">**Motor antimalware**, **Caja fuerte datos adjuntos** <sup>\*</sup> :</span><span class="sxs-lookup"><span data-stu-id="c5d13-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="c5d13-332">**DMARC, suplantación,** <sup>\*</sup> **suplantación, suplantación** de **identidad filtrada**:</span><span class="sxs-lookup"><span data-stu-id="c5d13-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="c5d13-333">**DMARC:** mensajes filtrados debido a que el mensaje no ha fallado en la comprobación de autenticación de DMARC.</span><span class="sxs-lookup"><span data-stu-id="c5d13-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="c5d13-334">**Detección de detonación de url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c5d13-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="c5d13-335">**Filtrado contra correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="c5d13-336">**ZAP quitado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-336">**ZAP removed**</span></span>
- <span data-ttu-id="c5d13-337">**Detección por Caja fuerte vínculos**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c5d13-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="c5d13-338"><sup>\*</sup>Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c5d13-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="c5d13-339">Si selecciona una fila en la tabla de detalles, se muestra un desglose adicional de los recuentos de correo electrónico en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="c5d13-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="c5d13-340">Exportar desde la vista Tech</span><span class="sxs-lookup"><span data-stu-id="c5d13-340">Export from Tech view</span></span>

<span data-ttu-id="c5d13-341">Al hacer **clic en** Exportar , en **Opciones,** puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c5d13-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="c5d13-342">**Resumen (con datos de los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="c5d13-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="c5d13-343">**Detalles (con datos de los últimos 30 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="c5d13-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="c5d13-344">En **Fecha**, elija un rango y, a continuación, haga clic **en Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="c5d13-345">Los datos de los filtros actuales se exportarán a un .csv archivo.</span><span class="sxs-lookup"><span data-stu-id="c5d13-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="c5d13-346">Cada archivo .csv exportada está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="c5d13-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="c5d13-347">Si los datos contienen más de 150 000 filas, se crearán varios .csv archivos.</span><span class="sxs-lookup"><span data-stu-id="c5d13-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Vista técnica en el informe de estado del flujo de correo](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="c5d13-349">Informe de detecciones de malware</span><span class="sxs-lookup"><span data-stu-id="c5d13-349">Malware detections report</span></span>

<span data-ttu-id="c5d13-350">El **informe de detecciones** de malware muestra información sobre detecciones de malware en mensajes de correo electrónico entrantes y salientes (malware detectado por Exchange Online Protection o EOP).</span><span class="sxs-lookup"><span data-stu-id="c5d13-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="c5d13-351">Para obtener más información acerca de la protección contra malware en EOP, vea [Protección contra malware en EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="c5d13-352">El filtro de vista agregado permite 90 días, mientras que el filtro de tabla de detalles solo permite 10 días.</span><span class="sxs-lookup"><span data-stu-id="c5d13-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="c5d13-353">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c5d13-354">En la **página Informes de colaboración &** correo electrónico, busque Malware detectado en el correo **electrónico** y, a continuación, haga clic en **Ver detalles.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="c5d13-355">Para ir directamente al informe, abra <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="c5d13-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Detecciones de malware en el widget de correo electrónico en la página Informes de & de colaboración](../../media/malware-detections-widget.png)

<span data-ttu-id="c5d13-357">En la **página Informe de detecciones de** malware, puede filtrar tanto el gráfico como la tabla de detalles haciendo clic en **Filtrar** y seleccionando uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c5d13-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="c5d13-358">**Fecha (UTC) Fecha** **de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="c5d13-359">**Dirección:** **entrante** y **saliente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-359">**Direction**: **Inbound** and **Outbound**</span></span>

![Vista Informe en el informe de detección de malware en el correo electrónico](../../media/malware-detections-report-view.png)

<span data-ttu-id="c5d13-361">En la tabla de detalles debajo del gráfico, puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="c5d13-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="c5d13-362">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c5d13-362">**Date**</span></span>
- <span data-ttu-id="c5d13-363">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-363">**Sender address**</span></span>
- <span data-ttu-id="c5d13-364">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="c5d13-364">**Recipient address**</span></span>
- <span data-ttu-id="c5d13-365">**Id. de** mensaje: disponible en el **campo de encabezado Id. de** mensaje en el encabezado del mensaje y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="c5d13-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="c5d13-366">Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (tenga en cuenta los corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="c5d13-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="c5d13-367">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="c5d13-367">**Subject**</span></span>
- <span data-ttu-id="c5d13-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="c5d13-368">**Filename**</span></span>
- <span data-ttu-id="c5d13-369">**Nombre de malware**</span><span class="sxs-lookup"><span data-stu-id="c5d13-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="c5d13-370">Informe de latencia de correo</span><span class="sxs-lookup"><span data-stu-id="c5d13-370">Mail latency report</span></span>

<span data-ttu-id="c5d13-371">El **informe de latencia de** correo en Defender para Office 365 contiene información sobre la latencia de entrega y detonación de correo experimentada en su organización.</span><span class="sxs-lookup"><span data-stu-id="c5d13-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="c5d13-372">Para obtener más información, vea [Informe de latencia de correo](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="c5d13-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="c5d13-373">Informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="c5d13-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="c5d13-374">El **informe de detecciones de correo** no deseado desaparecerá finalmente.</span><span class="sxs-lookup"><span data-stu-id="c5d13-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="c5d13-375">La misma información está disponible en el informe [de estado de protección contra amenazas](#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="c5d13-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="c5d13-376">Informe de detecciones de suplantación</span><span class="sxs-lookup"><span data-stu-id="c5d13-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="c5d13-377">El informe de detecciones de suplantación mejoradas, tal como se describe en este artículo, está en versión preliminar, está sujeto a cambios y no está disponible en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="c5d13-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="c5d13-378">La versión anterior del informe muestra solo **Correo bueno** y Capturado como correo **no deseado.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="c5d13-379">El **informe Detecciones** de suplantación muestra información sobre los mensajes bloqueados o permitidos debido a la suplantación.</span><span class="sxs-lookup"><span data-stu-id="c5d13-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="c5d13-380">Para obtener más información acerca de la suplantación, vea Protección contra la suplantación [en EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="c5d13-381">La vista de agregado del informe permite 45 días de filtrado, mientras que la vista de detalles solo permite <sup>\*</sup> diez días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="c5d13-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="c5d13-382"><sup>\*</sup> Con el tiempo, podrás usar hasta 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="c5d13-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="c5d13-383">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c5d13-384">En la página **Informes de colaboración &** correo electrónico, busque **Detecciones** de suplantación de suplantación y, a continuación, haga clic **en Ver detalles.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="c5d13-385">Para ir directamente al informe, abra <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="c5d13-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Widget Detecciones de suplantación en la página Informes de colaboración & correo electrónico](../../media/spoof-detections-widget.png)

<span data-ttu-id="c5d13-387">El gráfico muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c5d13-387">The chart shows the following information:</span></span>

- <span data-ttu-id="c5d13-388">**Pasar**</span><span class="sxs-lookup"><span data-stu-id="c5d13-388">**Pass**</span></span>
- <span data-ttu-id="c5d13-389">**Error**</span><span class="sxs-lookup"><span data-stu-id="c5d13-389">**Fail**</span></span>
- <span data-ttu-id="c5d13-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="c5d13-390">**SoftPass**</span></span>
- <span data-ttu-id="c5d13-391">**Ninguna**</span><span class="sxs-lookup"><span data-stu-id="c5d13-391">**None**</span></span>
- <span data-ttu-id="c5d13-392">**Otros**</span><span class="sxs-lookup"><span data-stu-id="c5d13-392">**Other**</span></span>

<span data-ttu-id="c5d13-393">Al pasar el mouse sobre un día (punto de datos) en el gráfico, puede ver cuántos mensajes suplantados se detectaron y por qué.</span><span class="sxs-lookup"><span data-stu-id="c5d13-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="c5d13-394">En la **página Informe** de correo suplantado, puede filtrar tanto el gráfico como la tabla de detalles haciendo clic en **Filtrar** y seleccionando uno o varios de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c5d13-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="c5d13-395">**Fecha (UTC) Fecha** **de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="c5d13-396">**Resultado**:</span><span class="sxs-lookup"><span data-stu-id="c5d13-396">**Result**:</span></span>
  - <span data-ttu-id="c5d13-397">**Pasar**</span><span class="sxs-lookup"><span data-stu-id="c5d13-397">**Pass**</span></span>
  - <span data-ttu-id="c5d13-398">**Error**</span><span class="sxs-lookup"><span data-stu-id="c5d13-398">**Fail**</span></span>
  - <span data-ttu-id="c5d13-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="c5d13-399">**SoftPass**</span></span>
  - <span data-ttu-id="c5d13-400">**Ninguna**</span><span class="sxs-lookup"><span data-stu-id="c5d13-400">**None**</span></span>
  - <span data-ttu-id="c5d13-401">**Otros**</span><span class="sxs-lookup"><span data-stu-id="c5d13-401">**Other**</span></span>
- <span data-ttu-id="c5d13-402">**Tipo de suplantación:** **Interno** y **Externo**</span><span class="sxs-lookup"><span data-stu-id="c5d13-402">**Spoof type**: **Internal** and **External**</span></span>

![Página de informe de correo suplantación en el portal Microsoft 365 Defender correo](../../media/spoof-detections-report-page.png)

<span data-ttu-id="c5d13-404">En la tabla de detalles debajo del gráfico, puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="c5d13-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="c5d13-405">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c5d13-405">**Date**</span></span>
- <span data-ttu-id="c5d13-406">**Usuario suplantado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-406">**Spoofed user**</span></span>
- <span data-ttu-id="c5d13-407">**Infraestructura de envío**</span><span class="sxs-lookup"><span data-stu-id="c5d13-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="c5d13-408">**Tipo de suplantación**</span><span class="sxs-lookup"><span data-stu-id="c5d13-408">**Spoof type**</span></span>
- <span data-ttu-id="c5d13-409">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-409">**Result**</span></span>
- <span data-ttu-id="c5d13-410">**Código de resultados**</span><span class="sxs-lookup"><span data-stu-id="c5d13-410">**Result code**</span></span>
- <span data-ttu-id="c5d13-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="c5d13-411">**SPF**</span></span>
- <span data-ttu-id="c5d13-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="c5d13-412">**DKIM**</span></span>
- <span data-ttu-id="c5d13-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="c5d13-413">**DMARC**</span></span>
- <span data-ttu-id="c5d13-414">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="c5d13-414">**Message count**</span></span>

<span data-ttu-id="c5d13-415">Para obtener más información acerca de los códigos de resultados de autenticación compuesta, vea [Encabezados de mensajes](anti-spam-message-headers.md)contra correo no deseado en Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="c5d13-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="c5d13-416">Informe de envíos</span><span class="sxs-lookup"><span data-stu-id="c5d13-416">Submissions report</span></span>

<span data-ttu-id="c5d13-417">El **informe Envíos** muestra información sobre los elementos que los administradores han notificado a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="c5d13-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="c5d13-418">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="c5d13-419">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c5d13-420">En la página **Informes de colaboración &** correo electrónico, busque **Envíos** y, a continuación, haga clic **en Ver detalles.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="c5d13-421">Para ir directamente al informe, abra <https://security.microsoft.com/adminSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="c5d13-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="c5d13-422">Para ir a [envíos de administrador en el portal de Microsoft 365 Defender,](admin-submission.md)haga clic **en Ir a Envíos**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget Envíos en la página Informes de colaboración & correo electrónico](../../media/submissions-report-widget.png)

<span data-ttu-id="c5d13-424">El gráfico muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c5d13-424">The chart shows the following information:</span></span>

- <span data-ttu-id="c5d13-425">**Pending**</span><span class="sxs-lookup"><span data-stu-id="c5d13-425">**Pending**</span></span>
- <span data-ttu-id="c5d13-426">**Completed**</span><span class="sxs-lookup"><span data-stu-id="c5d13-426">**Completed**</span></span>

<span data-ttu-id="c5d13-427">En la **página Envíos,** puede filtrar tanto el gráfico como la tabla de detalles haciendo clic en **Filtrar** y seleccionando uno o varios de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c5d13-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="c5d13-428">**Fecha notificada:** **Hora de inicio** y hora de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="c5d13-429">**Tipo de envío**:</span><span class="sxs-lookup"><span data-stu-id="c5d13-429">**Submission type**:</span></span>
  - <span data-ttu-id="c5d13-430">**Correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="c5d13-430">**Email**</span></span>
  - <span data-ttu-id="c5d13-431">**URL**</span><span class="sxs-lookup"><span data-stu-id="c5d13-431">**URL**</span></span>
  - <span data-ttu-id="c5d13-432">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="c5d13-432">**File**</span></span>
- <span data-ttu-id="c5d13-433">**Identificador de envío**</span><span class="sxs-lookup"><span data-stu-id="c5d13-433">**Submission ID**</span></span>
- <span data-ttu-id="c5d13-434">**Id. de mensaje de red**</span><span class="sxs-lookup"><span data-stu-id="c5d13-434">**Network Message ID**</span></span>
- <span data-ttu-id="c5d13-435">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c5d13-435">**Sender**</span></span>
- <span data-ttu-id="c5d13-436">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="c5d13-436">**Name**</span></span>
- <span data-ttu-id="c5d13-437">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="c5d13-437">**Submitted by**</span></span>
- <span data-ttu-id="c5d13-438">**Motivo para enviar**:</span><span class="sxs-lookup"><span data-stu-id="c5d13-438">**Reason for submitting**:</span></span>
  - <span data-ttu-id="c5d13-439">**No es correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-439">**Not junk**</span></span>
  - <span data-ttu-id="c5d13-440">**Suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="c5d13-440">**Phish**</span></span>
  - <span data-ttu-id="c5d13-441">**Malware**</span><span class="sxs-lookup"><span data-stu-id="c5d13-441">**Malware**</span></span>
  - <span data-ttu-id="c5d13-442">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-442">**Spam**</span></span>
- <span data-ttu-id="c5d13-443">**Estado de volver a examinar:**</span><span class="sxs-lookup"><span data-stu-id="c5d13-443">**Rescan status**:</span></span>
  - <span data-ttu-id="c5d13-444">**Pending**</span><span class="sxs-lookup"><span data-stu-id="c5d13-444">**Pending**</span></span>
  - <span data-ttu-id="c5d13-445">**Completed**</span><span class="sxs-lookup"><span data-stu-id="c5d13-445">**Completed**</span></span>

<span data-ttu-id="c5d13-446">La tabla de detalles debajo del gráfico  muestra la misma información  y tiene las mismas opciones de grupo o personalizar columnas que en la pestaña Enviado para el análisis en Correo electrónico **& envíos** de  \> **colaboración.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-446">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="c5d13-447">Para obtener más información, vea [Ver envíos de administrador a Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c5d13-447">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Página de informe de envíos en el portal Microsoft 365 Defender envío](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="c5d13-449">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="c5d13-449">Threat protection status report</span></span>

<span data-ttu-id="c5d13-450">El **informe de estado de** protección contra amenazas está disponible en EOP y Defender para Office 365; sin embargo, los informes contienen datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="c5d13-450">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="c5d13-451">Por ejemplo, los clientes de EOP pueden ver información sobre malware detectado en el correo electrónico, pero no información sobre archivos malintencionados detectados por [Caja fuerte Attachments for SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)y Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="c5d13-451">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="c5d13-452">El informe proporciona el recuento de mensajes de correo electrónico con contenido malintencionado, como archivos o direcciones de sitios web (DIRECCIONES URL) bloqueadas por el motor antimalware, purga automática de hora cero [(ZAP)](zero-hour-auto-purge.md)y Defender para características de Office 365 como vínculos [de Caja fuerte,](safe-links.md)datos adjuntos de [Caja fuerte](safe-attachments.md)y características de protección de suplantación en directivas [contra suplantación.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="c5d13-452">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="c5d13-453">Puede usar esta información para identificar tendencias o determinar si las directivas de la organización necesitan ajustes.</span><span class="sxs-lookup"><span data-stu-id="c5d13-453">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="c5d13-454">**Nota:** Es importante comprender que si un mensaje se envía a cinco destinatarios, lo contamos como cinco mensajes diferentes y no un mensaje.</span><span class="sxs-lookup"><span data-stu-id="c5d13-454">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="c5d13-455">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-455">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c5d13-456">En la página **Informes de colaboración &** correo electrónico, busque Estado de protección contra **amenazas** y, a continuación, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-456">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="c5d13-457">Para ir directamente al informe, abra una de las siguientes direcciones URL:</span><span class="sxs-lookup"><span data-stu-id="c5d13-457">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="c5d13-458">Defender para Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="c5d13-458">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="c5d13-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="c5d13-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Widget de estado de protección contra amenazas en la página Informes de colaboración & correo electrónico](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="c5d13-461">De forma predeterminada, el gráfico muestra los datos de los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="c5d13-461">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="c5d13-462">Si hace clic **en Filtrar** en la página **Informe** de estado de protección contra amenazas, puede seleccionar un intervalo de fechas de 90 días (las suscripciones de prueba podrían limitarse a 30 días).</span><span class="sxs-lookup"><span data-stu-id="c5d13-462">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="c5d13-463">La tabla de detalles permite filtrar durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="c5d13-463">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="c5d13-464">Las vistas disponibles se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="c5d13-464">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="c5d13-465">Ver datos por información general</span><span class="sxs-lookup"><span data-stu-id="c5d13-465">View data by Overview</span></span>

![Vista general en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="c5d13-467">En la **vista Ver datos por información** general, se muestra la siguiente información de detección en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="c5d13-467">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="c5d13-468">**Malware de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="c5d13-468">**Email malware**</span></span>
- <span data-ttu-id="c5d13-469">**Phish de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="c5d13-469">**Email phish**</span></span>
- <span data-ttu-id="c5d13-470">**Malware de contenido**</span><span class="sxs-lookup"><span data-stu-id="c5d13-470">**Content malware**</span></span>

<span data-ttu-id="c5d13-471">No hay ninguna tabla de detalles disponible debajo del gráfico.</span><span class="sxs-lookup"><span data-stu-id="c5d13-471">No details table is available below the chart.</span></span>

<span data-ttu-id="c5d13-472">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="c5d13-472">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="c5d13-473">**Fecha (UTC) Fecha** **de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-473">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="c5d13-474">**Detección:** **malware de correo** electrónico, **suplantación** de identidad de correo electrónico o **malware de contenido**</span><span class="sxs-lookup"><span data-stu-id="c5d13-474">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="c5d13-475">**Protegido por**: **MDO** (Defender para Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="c5d13-475">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="c5d13-476">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="c5d13-476">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="c5d13-477">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-477">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="c5d13-478">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-478">**Direction**</span></span>
- <span data-ttu-id="c5d13-479">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="c5d13-479">**Domain**</span></span>
- <span data-ttu-id="c5d13-480">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="c5d13-480">**Policy type**</span></span>

<span data-ttu-id="c5d13-481">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-481">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="c5d13-482">Ver datos por phishing de \> correo electrónico y desglose de gráficos por tecnología de detección</span><span class="sxs-lookup"><span data-stu-id="c5d13-482">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Vista de tecnología de detección para correo electrónico de suplantación de identidad (phishing) en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="c5d13-484">En la vista Ver  **datos por \> phishing** de correo electrónico y desglose de gráficos por tecnología de detección, se muestra la siguiente información en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="c5d13-484">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="c5d13-485">**Reputación malintencionada** de la dirección URL: reputación de url malintencionada generada desde <sup>\*</sup> Defender para Office 365 detonaciones en otros Microsoft 365 cliente.</span><span class="sxs-lookup"><span data-stu-id="c5d13-485">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="c5d13-486">**Filtro avanzado:** señales de suplantación de identidad basadas en el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="c5d13-486">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="c5d13-487">**Filtro general:** señales de suplantación de identidad basadas en reglas de analista.</span><span class="sxs-lookup"><span data-stu-id="c5d13-487">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="c5d13-488">**Suplantación de** identidad dentro de la organización: el remitente está intentando suplantación del dominio de destinatario.</span><span class="sxs-lookup"><span data-stu-id="c5d13-488">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="c5d13-489">**Suplantación de dominio externo:** el remitente está intentando suplantación de identidad de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="c5d13-489">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="c5d13-490">**Spoof DMARC:** error de autenticación DMARC en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c5d13-490">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="c5d13-491">**Marca de suplantación:** suplantación de marcas conocidas basadas en remitentes.</span><span class="sxs-lookup"><span data-stu-id="c5d13-491">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="c5d13-492">**Detección de análisis mixto**</span><span class="sxs-lookup"><span data-stu-id="c5d13-492">**Mixed analysis detection**</span></span>
- <span data-ttu-id="c5d13-493">**Reputación de los archivos**</span><span class="sxs-lookup"><span data-stu-id="c5d13-493">**File reputation**</span></span>
- <span data-ttu-id="c5d13-494">**Coincidencia de huella digital**</span><span class="sxs-lookup"><span data-stu-id="c5d13-494">**Fingerprint matching**</span></span>
- <span data-ttu-id="c5d13-495">**Reputación de detonación de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c5d13-495">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="c5d13-496">**Detonación de dirección URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c5d13-496">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="c5d13-497">**Usuario de suplantación**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c5d13-497">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="c5d13-498">**Dominio de suplantación:** <sup>\*</sup> suplantación de dominios que el cliente posee o define.</span><span class="sxs-lookup"><span data-stu-id="c5d13-498">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="c5d13-499">**Suplantación de inteligencia de buzones:** suplantación de usuarios definida por el administrador o aprendida a través <sup>\*</sup> de la inteligencia de buzones.</span><span class="sxs-lookup"><span data-stu-id="c5d13-499">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="c5d13-500">**Detonación de archivos**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c5d13-500">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="c5d13-501">**Campaña**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c5d13-501">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="c5d13-502">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c5d13-502">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="c5d13-503">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c5d13-503">**Date**</span></span>
- <span data-ttu-id="c5d13-504">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="c5d13-504">**Subject**</span></span>
- <span data-ttu-id="c5d13-505">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-505">**Sender**</span></span>
- <span data-ttu-id="c5d13-506">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="c5d13-506">**Recipients**</span></span>
- <span data-ttu-id="c5d13-507">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="c5d13-507">**Detected by**</span></span>
- <span data-ttu-id="c5d13-508">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="c5d13-508">**Delivery Status**</span></span>
- <span data-ttu-id="c5d13-509">**Origen de la transacción**</span><span class="sxs-lookup"><span data-stu-id="c5d13-509">**Source of Compromise**</span></span>
- <span data-ttu-id="c5d13-510">**Tags**</span><span class="sxs-lookup"><span data-stu-id="c5d13-510">**Tags**</span></span>

<span data-ttu-id="c5d13-511">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="c5d13-511">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="c5d13-512">**Fecha (UTC) Fecha** **de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-512">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="c5d13-513">**Detección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-513">**Detection**</span></span>
- <span data-ttu-id="c5d13-514">**Protegido por**: **MDO** (Defender para Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="c5d13-514">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="c5d13-515">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-515">**Direction**</span></span>
- <span data-ttu-id="c5d13-516">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="c5d13-516">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="c5d13-517">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-517">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="c5d13-518">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="c5d13-518">**Domain**</span></span>
- <span data-ttu-id="c5d13-519">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="c5d13-519">**Policy type**</span></span>
- <span data-ttu-id="c5d13-520">**Nombre de directiva** (solo tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="c5d13-520">**Policy name** (details table only)</span></span>
- <span data-ttu-id="c5d13-521">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="c5d13-521">**Recipients**</span></span>

<span data-ttu-id="c5d13-522">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-522">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="c5d13-523">Ver datos por malware de \> correo electrónico y desglose de gráficos por tecnología de detección</span><span class="sxs-lookup"><span data-stu-id="c5d13-523">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Vista de tecnología de detección de malware en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="c5d13-525">En la vista Ver  **datos por malware de \> correo** electrónico y desglose de gráficos por tecnología de detección, se muestra la siguiente información en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="c5d13-525">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="c5d13-526">**Detonación de archivos:** <sup>\*</sup> detección por Caja fuerte datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="c5d13-526">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="c5d13-527">**Reputación de detonación de archivos:** toda la reputación de archivos malintencionados generada por <sup>\*</sup> Defender para Office 365 detonaciones.</span><span class="sxs-lookup"><span data-stu-id="c5d13-527">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="c5d13-528">**Reputación de los archivos**</span><span class="sxs-lookup"><span data-stu-id="c5d13-528">**File reputation**</span></span>
- <span data-ttu-id="c5d13-529">**Motor antimalware: detección** <sup>\*</sup> de motores antimalware.</span><span class="sxs-lookup"><span data-stu-id="c5d13-529">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="c5d13-530">Bloque de tipo de archivo de directiva **antimalware:** se trata de mensajes de correo electrónico filtrados debido al tipo de archivo malintencionado identificado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c5d13-530">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="c5d13-531">**Reputación malintencionada de URL**</span><span class="sxs-lookup"><span data-stu-id="c5d13-531">**URL malicious reputation**</span></span>
- <span data-ttu-id="c5d13-532">**Detonación de URL**</span><span class="sxs-lookup"><span data-stu-id="c5d13-532">**URL detonation**</span></span>
- <span data-ttu-id="c5d13-533">**Reputación de detonación de URL**</span><span class="sxs-lookup"><span data-stu-id="c5d13-533">**URL detonation reputation**</span></span>
- <span data-ttu-id="c5d13-534">**Campaña**</span><span class="sxs-lookup"><span data-stu-id="c5d13-534">**Campaign**</span></span>

<span data-ttu-id="c5d13-535">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c5d13-535">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="c5d13-536">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c5d13-536">**Date**</span></span>
- <span data-ttu-id="c5d13-537">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="c5d13-537">**Subject**</span></span>
- <span data-ttu-id="c5d13-538">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-538">**Sender**</span></span>
- <span data-ttu-id="c5d13-539">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="c5d13-539">**Recipients**</span></span>
- <span data-ttu-id="c5d13-540">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="c5d13-540">**Detected by**</span></span>
- <span data-ttu-id="c5d13-541">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="c5d13-541">**Delivery Status**</span></span>
- <span data-ttu-id="c5d13-542">**Origen de la transacción**</span><span class="sxs-lookup"><span data-stu-id="c5d13-542">**Source of Compromise**</span></span>
- <span data-ttu-id="c5d13-543">**Tags**</span><span class="sxs-lookup"><span data-stu-id="c5d13-543">**Tags**</span></span>

<span data-ttu-id="c5d13-544">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="c5d13-544">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="c5d13-545">**Fecha (UTC) Fecha** **de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-545">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="c5d13-546">**Detección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-546">**Detection**</span></span>
- <span data-ttu-id="c5d13-547">**Protegido por**: **MDO** (Defender para Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="c5d13-547">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="c5d13-548">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-548">**Direction**</span></span>
- <span data-ttu-id="c5d13-549">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="c5d13-549">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="c5d13-550">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-550">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="c5d13-551">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="c5d13-551">**Domain**</span></span>
- <span data-ttu-id="c5d13-552">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="c5d13-552">**Policy type**</span></span>
- <span data-ttu-id="c5d13-553">**Nombre de directiva** (solo tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="c5d13-553">**Policy name** (details table only)</span></span>
- <span data-ttu-id="c5d13-554">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="c5d13-554">**Recipients**</span></span>

<span data-ttu-id="c5d13-555">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-555">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="c5d13-556">Desglose de gráficos por tipo de directiva y Ver datos por \> correo electrónico Phish o Ver datos por malware de correo \> electrónico</span><span class="sxs-lookup"><span data-stu-id="c5d13-556">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Vista de tipo de directiva para correo electrónico de suplantación de identidad (phishing) o correo electrónico de malware en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="c5d13-558">En las **vistas Desglose** de gráficos por tipo de directiva y Ver datos por correo electrónico **\> phish** o Ver datos por **\> correo** electrónico malintencionado, se muestra la siguiente información en los gráficos:</span><span class="sxs-lookup"><span data-stu-id="c5d13-558">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="c5d13-559">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="c5d13-559">**Anti-malware**</span></span>
- <span data-ttu-id="c5d13-560">**Caja fuerte Datos adjuntos**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c5d13-560">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="c5d13-561">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="c5d13-561">**Anti-phish**</span></span>
- <span data-ttu-id="c5d13-562">**Contra correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-562">**Anti-spam**</span></span>
- <span data-ttu-id="c5d13-563">**Regla de flujo de** correo (también conocida como regla de transporte)</span><span class="sxs-lookup"><span data-stu-id="c5d13-563">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="c5d13-564">**Otros**</span><span class="sxs-lookup"><span data-stu-id="c5d13-564">**Others**</span></span>

<span data-ttu-id="c5d13-565">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c5d13-565">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="c5d13-566">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c5d13-566">**Date**</span></span>
- <span data-ttu-id="c5d13-567">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="c5d13-567">**Subject**</span></span>
- <span data-ttu-id="c5d13-568">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-568">**Sender**</span></span>
- <span data-ttu-id="c5d13-569">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="c5d13-569">**Recipients**</span></span>
- <span data-ttu-id="c5d13-570">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="c5d13-570">**Detected by**</span></span>
- <span data-ttu-id="c5d13-571">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="c5d13-571">**Delivery Status**</span></span>
- <span data-ttu-id="c5d13-572">**Origen de la transacción**</span><span class="sxs-lookup"><span data-stu-id="c5d13-572">**Source of Compromise**</span></span>
- <span data-ttu-id="c5d13-573">**Tags**</span><span class="sxs-lookup"><span data-stu-id="c5d13-573">**Tags**</span></span>

<span data-ttu-id="c5d13-574">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="c5d13-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="c5d13-575">**Fecha (UTC) Fecha** **de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-575">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="c5d13-576">**Detección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-576">**Detection**</span></span>
- <span data-ttu-id="c5d13-577">**Protegido por**: **MDO** (Defender para Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="c5d13-577">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="c5d13-578">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-578">**Direction**</span></span>
- <span data-ttu-id="c5d13-579">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="c5d13-579">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="c5d13-580">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-580">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="c5d13-581">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="c5d13-581">**Domain**</span></span>
- <span data-ttu-id="c5d13-582">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="c5d13-582">**Policy type**</span></span>
- <span data-ttu-id="c5d13-583">**Nombre de directiva** (solo tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="c5d13-583">**Policy name** (details table only)</span></span>
- <span data-ttu-id="c5d13-584">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="c5d13-584">**Recipients**</span></span>

<span data-ttu-id="c5d13-585">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-585">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="c5d13-586">Desglose del gráfico por estado de entrega y Ver datos por correo electrónico \> phish o ver datos por malware de correo \> electrónico</span><span class="sxs-lookup"><span data-stu-id="c5d13-586">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Vista Estado de entrega para correo electrónico de suplantación de identidad (phishing) y correo electrónico de malware en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="c5d13-588">En las **vistas Desglose** del gráfico por estado de entrega y Ver datos por correo electrónico **\> phish** o **Ver \>** datos por correo electrónico malintencionado, se muestra la siguiente información en los gráficos:</span><span class="sxs-lookup"><span data-stu-id="c5d13-588">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="c5d13-589">**Buzón hospedado: Bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="c5d13-589">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="c5d13-590">**Buzón hospedado: correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-590">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="c5d13-591">**Buzón hospedado: carpeta personalizada**</span><span class="sxs-lookup"><span data-stu-id="c5d13-591">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="c5d13-592">**Buzón hospedado: elementos eliminados**</span><span class="sxs-lookup"><span data-stu-id="c5d13-592">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="c5d13-593">**Reenviado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-593">**Forwarded**</span></span>
- <span data-ttu-id="c5d13-594">**Servidor local: entregado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-594">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="c5d13-595">**Cuarentena**</span><span class="sxs-lookup"><span data-stu-id="c5d13-595">**Quarantine**</span></span>
- <span data-ttu-id="c5d13-596">**Error en la entrega**</span><span class="sxs-lookup"><span data-stu-id="c5d13-596">**Delivery failed**</span></span>
- <span data-ttu-id="c5d13-597">**Se ha descartado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-597">**Dropped**</span></span>

<span data-ttu-id="c5d13-598">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c5d13-598">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="c5d13-599">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c5d13-599">**Date**</span></span>
- <span data-ttu-id="c5d13-600">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="c5d13-600">**Subject**</span></span>
- <span data-ttu-id="c5d13-601">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-601">**Sender**</span></span>
- <span data-ttu-id="c5d13-602">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="c5d13-602">**Recipients**</span></span>
- <span data-ttu-id="c5d13-603">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="c5d13-603">**Detected by**</span></span>
- <span data-ttu-id="c5d13-604">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="c5d13-604">**Delivery Status**</span></span>
- <span data-ttu-id="c5d13-605">**Origen de la transacción**</span><span class="sxs-lookup"><span data-stu-id="c5d13-605">**Source of Compromise**</span></span>
- <span data-ttu-id="c5d13-606">**Tags**</span><span class="sxs-lookup"><span data-stu-id="c5d13-606">**Tags**</span></span>

<span data-ttu-id="c5d13-607">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="c5d13-607">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="c5d13-608">**Fecha (UTC) Fecha** **de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-608">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="c5d13-609">**Detección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-609">**Detection**</span></span>
- <span data-ttu-id="c5d13-610">**Protegido por**: **MDO** (Defender para Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="c5d13-610">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="c5d13-611">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-611">**Direction**</span></span>
- <span data-ttu-id="c5d13-612">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="c5d13-612">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="c5d13-613">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-613">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="c5d13-614">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="c5d13-614">**Domain**</span></span>
- <span data-ttu-id="c5d13-615">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="c5d13-615">**Policy type**</span></span>
- <span data-ttu-id="c5d13-616">**Nombre de directiva** (solo tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="c5d13-616">**Policy name** (details table only)</span></span>
- <span data-ttu-id="c5d13-617">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="c5d13-617">**Recipients**</span></span>

<span data-ttu-id="c5d13-618">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-618">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="c5d13-619">Ver datos por malware \> de contenido</span><span class="sxs-lookup"><span data-stu-id="c5d13-619">View data by Content \> Malware</span></span>

![Vista de malware de contenido en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="c5d13-621">En la **vista Ver datos por \> malware** de contenido, la siguiente información se muestra en el gráfico de Microsoft Defender para Office 365 organizaciones:</span><span class="sxs-lookup"><span data-stu-id="c5d13-621">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="c5d13-622">**Motor antimalware:** archivos malintencionados detectados en Sharepoint, OneDrive y Microsoft Teams por la detección de virus integrada en [Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-622">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="c5d13-623">**Detonación de archivos:** archivos malintencionados detectados por Caja fuerte datos adjuntos para [SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-623">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="c5d13-624">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c5d13-624">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="c5d13-625">**Fecha (UTC) Fecha** **de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-625">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="c5d13-626">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="c5d13-626">**Location**</span></span>
- <span data-ttu-id="c5d13-627">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="c5d13-627">**Detected by**</span></span>
- <span data-ttu-id="c5d13-628">**Nombre de malware**</span><span class="sxs-lookup"><span data-stu-id="c5d13-628">**Malware name**</span></span>

<span data-ttu-id="c5d13-629">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="c5d13-629">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="c5d13-630">**Fecha (UTC) Fecha** **de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-630">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="c5d13-631">**Detección:** **motor antimalware o** **detonación de archivos**</span><span class="sxs-lookup"><span data-stu-id="c5d13-631">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="c5d13-632">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-632">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="c5d13-633">Ver datos por invalidación del sistema</span><span class="sxs-lookup"><span data-stu-id="c5d13-633">View data by System override</span></span>

![Vista De invalidación de mensajes en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="c5d13-635">En la **vista Ver datos por invalidación** del sistema, se muestra la siguiente información de motivo de invalidación en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="c5d13-635">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="c5d13-636">**Omitir localmente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-636">**On-premises skip**</span></span>
- <span data-ttu-id="c5d13-637">**Ip allow**</span><span class="sxs-lookup"><span data-stu-id="c5d13-637">**IP allow**</span></span>
- <span data-ttu-id="c5d13-638">**Exchange de transporte de correo** (regla de flujo de correo)</span><span class="sxs-lookup"><span data-stu-id="c5d13-638">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="c5d13-639">**Remitentes permitidos por la organización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-639">**Organization allowed senders**</span></span>
- <span data-ttu-id="c5d13-640">**Dominios permitidos por la organización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-640">**Organization allowed domains**</span></span>
- <span data-ttu-id="c5d13-641">**ZAP no habilitado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-641">**ZAP not enabled**</span></span>
- <span data-ttu-id="c5d13-642">**Carpeta de correo no deseado no habilitada**</span><span class="sxs-lookup"><span data-stu-id="c5d13-642">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="c5d13-643">**Remitente Caja fuerte usuario**</span><span class="sxs-lookup"><span data-stu-id="c5d13-643">**User Safe Sender**</span></span>
- <span data-ttu-id="c5d13-644">**Dominio Caja fuerte usuario**</span><span class="sxs-lookup"><span data-stu-id="c5d13-644">**User Safe Domain**</span></span>

<span data-ttu-id="c5d13-645">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c5d13-645">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="c5d13-646">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c5d13-646">**Date**</span></span>
- <span data-ttu-id="c5d13-647">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="c5d13-647">**Subject**</span></span>
- <span data-ttu-id="c5d13-648">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="c5d13-648">**Sender**</span></span>
- <span data-ttu-id="c5d13-649">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="c5d13-649">**Recipients**</span></span>
- <span data-ttu-id="c5d13-650">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="c5d13-650">**Detected by**</span></span>
- <span data-ttu-id="c5d13-651">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="c5d13-651">**Delivery Status**</span></span>
- <span data-ttu-id="c5d13-652">**Origen de la transacción**</span><span class="sxs-lookup"><span data-stu-id="c5d13-652">**Source of Compromise**</span></span>
- <span data-ttu-id="c5d13-653">**Tags**</span><span class="sxs-lookup"><span data-stu-id="c5d13-653">**Tags**</span></span>

<span data-ttu-id="c5d13-654">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="c5d13-654">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="c5d13-655">**Fecha (UTC) Fecha** **de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-655">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="c5d13-656">**Detección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-656">**Detection**</span></span>
- <span data-ttu-id="c5d13-657">**Protegido por**: **MDO** (Defender para Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="c5d13-657">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="c5d13-658">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="c5d13-658">**Direction**</span></span>
- <span data-ttu-id="c5d13-659">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="c5d13-659">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="c5d13-660">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-660">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="c5d13-661">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="c5d13-661">**Domain**</span></span>
- <span data-ttu-id="c5d13-662">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="c5d13-662">**Policy type**</span></span>
- <span data-ttu-id="c5d13-663">**Nombre de directiva** (solo tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="c5d13-663">**Policy name** (details table only)</span></span>
- <span data-ttu-id="c5d13-664">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="c5d13-664">**Recipients**</span></span>

<span data-ttu-id="c5d13-665">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-665">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="c5d13-666"><sup>\*</sup>Solo defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c5d13-666"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="c5d13-667">Informe de malware superior</span><span class="sxs-lookup"><span data-stu-id="c5d13-667">Top malware report</span></span>

<span data-ttu-id="c5d13-668">El **informe de malware** top muestra los distintos tipos de malware detectados por la protección [antimalware en EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-668">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="c5d13-669">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-669">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c5d13-670">En la página **Informes de colaboración &** correo electrónico, busque Top **malware** y, a continuación, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-670">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="c5d13-671">Para ir directamente al informe, abra <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="c5d13-671">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Widget de malware superior en la página Informes de colaboración & correo electrónico](../../media/top-malware-report-widget.png)

<span data-ttu-id="c5d13-673">Al pasar el mouse sobre una cuña en el gráfico circular, puede ver el nombre de un tipo de malware y cuántos mensajes se detectaron como que tienen ese malware.</span><span class="sxs-lookup"><span data-stu-id="c5d13-673">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="c5d13-674">En la **página Informe de malware superior,** se muestra una versión más grande del gráfico circular en la página del informe. La tabla de detalles debajo del gráfico muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c5d13-674">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="c5d13-675">**Malware superior**</span><span class="sxs-lookup"><span data-stu-id="c5d13-675">**Top malware**</span></span>
- <span data-ttu-id="c5d13-676">**Count**</span><span class="sxs-lookup"><span data-stu-id="c5d13-676">**Count**</span></span>

<span data-ttu-id="c5d13-677">Si hace clic **en Filtrar**, puede especificar un intervalo de fechas con Fecha de **inicio y** Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-677">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Vista de informe de malware superior](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="c5d13-679">Informe de protección contra amenazas de url</span><span class="sxs-lookup"><span data-stu-id="c5d13-679">URL threat protection report</span></span>

<span data-ttu-id="c5d13-680">El **informe de protección contra amenazas de url** solo está disponible en Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="c5d13-680">The **URL threat protection report** is available only in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="c5d13-681">Para obtener más información, vea [Informe de protección contra amenazas de url](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="c5d13-681">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="c5d13-682">Informe de mensajes notificados por el usuario</span><span class="sxs-lookup"><span data-stu-id="c5d13-682">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5d13-683">Para que el informe **de** mensajes notificados por el usuario funcione correctamente,  el registro de auditoría debe estar activado para el Microsoft 365 usuario.</span><span class="sxs-lookup"><span data-stu-id="c5d13-683">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="c5d13-684">Esto lo suele hacer alguien que tenga el rol Registros de auditoría asignado en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c5d13-684">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="c5d13-685">Para obtener más información, vea Activar Microsoft 365 o desactivar la búsqueda del [registro de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="c5d13-685">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="c5d13-686">El  informe de mensajes notificados por el usuario muestra información acerca de los mensajes de correo electrónico que los usuarios han notificado como correo no deseado, intentos de suplantación de identidad o correo bueno mediante el complemento Report [Message o](enable-the-report-message-add-in.md) el complemento [Report Phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-686">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="c5d13-687">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-687">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c5d13-688">En la página **Informes de colaboración &** correo electrónico, busque **Mensajes** notificados por el usuario y, a continuación, haga clic en **Ver detalles.**</span><span class="sxs-lookup"><span data-stu-id="c5d13-688">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="c5d13-689">Para ir directamente al informe, abra <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="c5d13-689">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="c5d13-690">Para ir a [envíos de administrador en el portal de Microsoft 365 Defender,](admin-submission.md)haga clic **en Ir a Envíos**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-690">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget Mensajes notificados por el usuario en la página Informes de & de colaboración](../../media/user-reported-messages-widget.png)

<span data-ttu-id="c5d13-692">En **la página Mensajes** notificados por el usuario, puede  filtrar tanto el gráfico como la tabla de detalles haciendo clic en Filtrar y seleccionando uno o varios de los siguientes valores en el control desplegable que aparece:</span><span class="sxs-lookup"><span data-stu-id="c5d13-692">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="c5d13-693">**Fecha notificada:** **Hora de inicio** y hora de **finalización**</span><span class="sxs-lookup"><span data-stu-id="c5d13-693">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="c5d13-694">**Informe realizado por**</span><span class="sxs-lookup"><span data-stu-id="c5d13-694">**Reported by**</span></span>
- <span data-ttu-id="c5d13-695">**Asunto del correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="c5d13-695">**Email subject**</span></span>
- <span data-ttu-id="c5d13-696">**Id. de mensaje notificado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-696">**Message reported ID**</span></span>
- <span data-ttu-id="c5d13-697">**Id. de mensaje de red**</span><span class="sxs-lookup"><span data-stu-id="c5d13-697">**Network Message ID**</span></span>
- <span data-ttu-id="c5d13-698">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c5d13-698">**Sender**</span></span>
- <span data-ttu-id="c5d13-699">**Motivo notificado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-699">**Reported reason**</span></span>
  - <span data-ttu-id="c5d13-700">**No es correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-700">**Not junk**</span></span>
  - <span data-ttu-id="c5d13-701">**Suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="c5d13-701">**Phish**</span></span>
  - <span data-ttu-id="c5d13-702">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-702">**Spam**</span></span>
- <span data-ttu-id="c5d13-703">**Simulación de phish:** **Sí** o **No**</span><span class="sxs-lookup"><span data-stu-id="c5d13-703">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="c5d13-704">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c5d13-704">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="c5d13-705">Para agrupar las entradas, haga clic **en Agrupar** y seleccione uno de los siguientes valores de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="c5d13-705">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="c5d13-706">**Ninguna**</span><span class="sxs-lookup"><span data-stu-id="c5d13-706">**None**</span></span>
- <span data-ttu-id="c5d13-707">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="c5d13-707">**Reason**</span></span>
- <span data-ttu-id="c5d13-708">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c5d13-708">**Sender**</span></span>
- <span data-ttu-id="c5d13-709">**Informe realizado por**</span><span class="sxs-lookup"><span data-stu-id="c5d13-709">**Reported by**</span></span>
- <span data-ttu-id="c5d13-710">**Volver a examinar el resultado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-710">**Rescan result**</span></span>
- <span data-ttu-id="c5d13-711">**Simulación de phishing**</span><span class="sxs-lookup"><span data-stu-id="c5d13-711">**Phish simulation**</span></span>

![Informe de mensajes notificados por el usuario](../../media/user-reported-messages-report.png)

<span data-ttu-id="c5d13-713">En la tabla de detalles debajo del gráfico, puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="c5d13-713">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="c5d13-714">**Asunto del correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="c5d13-714">**Email subject**</span></span>
- <span data-ttu-id="c5d13-715">**Informe realizado por**</span><span class="sxs-lookup"><span data-stu-id="c5d13-715">**Reported by**</span></span>
- <span data-ttu-id="c5d13-716">**Fecha notificada**</span><span class="sxs-lookup"><span data-stu-id="c5d13-716">**Date reported**</span></span>
- <span data-ttu-id="c5d13-717">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c5d13-717">**Sender**</span></span>
- <span data-ttu-id="c5d13-718">**Motivo notificado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-718">**Reported reason**</span></span>
- <span data-ttu-id="c5d13-719">**Volver a examinar el resultado**</span><span class="sxs-lookup"><span data-stu-id="c5d13-719">**Rescan result**</span></span>
- <span data-ttu-id="c5d13-720">**Tags**</span><span class="sxs-lookup"><span data-stu-id="c5d13-720">**Tags**</span></span>

<span data-ttu-id="c5d13-721">Para enviar un mensaje a Microsoft para su análisis, seleccione la entrada de mensaje de la tabla, haga clic en Enviar a **Microsoft** para su análisis y, a continuación, seleccione uno de los siguientes valores de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="c5d13-721">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="c5d13-722">**Informe limpio**</span><span class="sxs-lookup"><span data-stu-id="c5d13-722">**Report clean**</span></span>
- <span data-ttu-id="c5d13-723">**Report phishing**</span><span class="sxs-lookup"><span data-stu-id="c5d13-723">**Report phishing**</span></span>
- <span data-ttu-id="c5d13-724">**Informar de malware**</span><span class="sxs-lookup"><span data-stu-id="c5d13-724">**Report malware**</span></span>
- <span data-ttu-id="c5d13-725">**Notificar correo no deseado**'</span><span class="sxs-lookup"><span data-stu-id="c5d13-725">**Report spam**'</span></span>
- <span data-ttu-id="c5d13-726">**Investigación de desencadenador** (Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="c5d13-726">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="c5d13-727">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="c5d13-727">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="c5d13-728">Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el portal de Microsoft 365 Defender web:</span><span class="sxs-lookup"><span data-stu-id="c5d13-728">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="c5d13-729">**Administración de organizaciones**</span><span class="sxs-lookup"><span data-stu-id="c5d13-729">**Organization Management**</span></span>
- <span data-ttu-id="c5d13-730">**Administrador de seguridad**</span><span class="sxs-lookup"><span data-stu-id="c5d13-730">**Security Administrator**</span></span>
- <span data-ttu-id="c5d13-731">**Lector de seguridad**</span><span class="sxs-lookup"><span data-stu-id="c5d13-731">**Security Reader**</span></span>
- <span data-ttu-id="c5d13-732">**Lector global**</span><span class="sxs-lookup"><span data-stu-id="c5d13-732">**Global Reader**</span></span>

<span data-ttu-id="c5d13-733">Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-733">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

<span data-ttu-id="c5d13-734">**Nota:** Agregar usuarios al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c5d13-734">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c5d13-735">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-735">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="c5d13-736">¿Qué ocurre si los informes no muestran datos?</span><span class="sxs-lookup"><span data-stu-id="c5d13-736">What if the reports aren't showing data?</span></span>

<span data-ttu-id="c5d13-737">Si no ve datos en los informes, compruebe que las directivas están configuradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="c5d13-737">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="c5d13-738">Para obtener más información, vea [Protect against threats](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="c5d13-738">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c5d13-739">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c5d13-739">Related topics</span></span>

[<span data-ttu-id="c5d13-740">Protección contra correo no deseado y antimalware en EOP</span><span class="sxs-lookup"><span data-stu-id="c5d13-740">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="c5d13-741">Informes e información inteligentes en el portal Microsoft 365 Defender web</span><span class="sxs-lookup"><span data-stu-id="c5d13-741">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="c5d13-742">Ver informes de flujo de correo en el portal Microsoft 365 Defender correo</span><span class="sxs-lookup"><span data-stu-id="c5d13-742">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="c5d13-743">Ver informes de Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c5d13-743">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
