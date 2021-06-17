---
title: Ver informes de seguridad de correo electrónico en el portal de Microsoft 365 Defender
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
description: Obtenga información sobre cómo buscar y usar informes de seguridad de correo electrónico para su organización. Los informes de seguridad de correo electrónico están disponibles en el portal de Microsoft 365 Defender.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d46aec8601d19234eed8682955ffef27b7e9b467
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985308"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="7f628-104">Ver informes de seguridad de correo electrónico en el portal de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f628-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7f628-105">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="7f628-105">**Applies to**</span></span>
- [<span data-ttu-id="7f628-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7f628-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7f628-107">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7f628-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7f628-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f628-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="7f628-109">Hay varios informes disponibles en el portal de Microsoft 365 Defender para ayudarle a ver cómo las características de seguridad de correo electrónico, como el correo no deseado, antimalware y las características de cifrado en Microsoft 365 protegen su <https://security.microsoft.com> organización.</span><span class="sxs-lookup"><span data-stu-id="7f628-109">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="7f628-110">Si tiene los permisos [necesarios,](#what-permissions-are-needed-to-view-these-reports)puede ver estos informes en el portal  de Microsoft 365 Defender yendo a Informes de correo electrónico & colaboración Correo electrónico & informes de \>  \> **colaboración**.</span><span class="sxs-lookup"><span data-stu-id="7f628-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="7f628-111">Para ir directamente a la página **Informes de colaboración & correo** electrónico, abra <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="7f628-111">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Página & informes de colaboración en el portal de Microsoft 365 Defender](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="7f628-113">Algunos de los informes de la página Informes de **colaboración & correo** electrónico requieren Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f628-113">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="7f628-114">Para obtener información acerca de estos informes, vea Ver informes de [Defender para Office 365 en el portal de Microsoft 365 Defender](view-reports-for-mdo.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-114">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="7f628-115">Los informes relacionados con el flujo de correo están ahora en el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="7f628-115">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="7f628-116">Para obtener más información acerca de estos informes, vea [Informes de flujo de correo en el nuevo Centro de administración de Exchange](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span><span class="sxs-lookup"><span data-stu-id="7f628-116">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="7f628-117">Informe de usuarios comprometidos</span><span class="sxs-lookup"><span data-stu-id="7f628-117">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="7f628-118">Este informe está disponible en organizaciones de Microsoft 365 con buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7f628-118">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="7f628-119">No está disponible en organizaciones independientes de Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="7f628-119">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="7f628-120">El **informe Usuarios comprometidos** muestra el número de  cuentas  de usuario que se marcaron como Sospechosas o Restringidas en los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="7f628-120">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="7f628-121">Las cuentas en cualquiera de estos estados son problemáticas o incluso están en peligro.</span><span class="sxs-lookup"><span data-stu-id="7f628-121">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="7f628-122">Con el uso frecuente, puede usar el informe para detectar picos e incluso tendencias en cuentas sospechosas o restringidas.</span><span class="sxs-lookup"><span data-stu-id="7f628-122">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="7f628-123">Para obtener más información acerca de los usuarios en peligro, vea [Responder a una cuenta de correo electrónico comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="7f628-123">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Usuarios comprometidos en la página Informes de colaboración & correo electrónico](../../media/compromised-users-report-widget.png)

<span data-ttu-id="7f628-125">La vista de agregado muestra los datos de los últimos 90 días y la vista de detalles muestra los datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="7f628-125">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="7f628-126">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & colaboración Correo electrónico \>  \> **& informes de colaboración.**</span><span class="sxs-lookup"><span data-stu-id="7f628-126">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="7f628-127">En **Usuarios en peligro,** haga clic **en Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="7f628-127">On **Compromised users**, click **View details**.</span></span> <span data-ttu-id="7f628-128">Para ir directamente al informe, abra <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="7f628-128">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="7f628-129">Después de **hacer** clic en Ver detalles, puede filtrar  tanto el gráfico como la tabla de detalles haciendo clic en Filtrar y seleccionando uno o varios de los siguientes valores en el menú desplegable que aparece:</span><span class="sxs-lookup"><span data-stu-id="7f628-129">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="7f628-130">**Date (UTC):** **Fecha de inicio y** fecha de **finalización.**</span><span class="sxs-lookup"><span data-stu-id="7f628-130">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="7f628-131">**Actividad**:</span><span class="sxs-lookup"><span data-stu-id="7f628-131">**Activity**:</span></span>
  - <span data-ttu-id="7f628-132">**Sospechoso:** la cuenta de usuario ha enviado un correo electrónico sospechoso y corre el riesgo de que se le restringa el envío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7f628-132">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="7f628-133">**Restringido:** la cuenta de usuario se ha restringido para enviar correo electrónico debido a patrones altamente sospechosos.</span><span class="sxs-lookup"><span data-stu-id="7f628-133">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="7f628-134">Cuando haya terminado de filtrar, haga clic **en Aplicar** o **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="7f628-134">When you're finished filtering, click **Apply** or **Cancel**.</span></span>

![Vista Informe en el informe usuarios comprometidos](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="7f628-136">En la tabla debajo del gráfico, puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="7f628-136">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="7f628-137">**Tiempo de creación**</span><span class="sxs-lookup"><span data-stu-id="7f628-137">**Creation time**</span></span>
- <span data-ttu-id="7f628-138">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="7f628-138">**User ID**</span></span>
- <span data-ttu-id="7f628-139">**Action**</span><span class="sxs-lookup"><span data-stu-id="7f628-139">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="7f628-140">Informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="7f628-140">Exchange transport rule report</span></span>

<span data-ttu-id="7f628-141">El **informe de reglas de transporte de Exchange** muestra el efecto de las reglas de flujo de correo (también conocidas como reglas de transporte) en los mensajes entrantes y salientes de la organización.</span><span class="sxs-lookup"><span data-stu-id="7f628-141">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="7f628-142">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & colaboración Correo electrónico \>  \> **& informes de colaboración.**</span><span class="sxs-lookup"><span data-stu-id="7f628-142">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="7f628-143">En la **regla de transporte de Exchange,** haga clic en Ver **detalles**.</span><span class="sxs-lookup"><span data-stu-id="7f628-143">On **Exchange transport rule**, click **View details**.</span></span> <span data-ttu-id="7f628-144">Para ir directamente al informe, abra <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="7f628-144">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Widget de regla de transporte de Exchange en la página Informes de colaboración & correo electrónico](../../media/transport-rule-report-widget.png)

<span data-ttu-id="7f628-146">Después de hacer clic **en Ver detalles,** están disponibles los siguientes gráficos y datos:</span><span class="sxs-lookup"><span data-stu-id="7f628-146">After you click **View details**, the following charts and data are available:</span></span>

- <span data-ttu-id="7f628-147">**Ver datos por reglas de transporte de Exchange** \> **Desglose del gráfico por dirección:**  este  gráfico muestra el número de mensajes entrantes y salientes que se vieron afectados por las reglas de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="7f628-147">**View data by Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>

- <span data-ttu-id="7f628-148">**Ver datos por reglas de transporte de Exchange** \> **Desglose del gráfico por gravedad:** este gráfico muestra el número de mensajes de gravedad **alta,** gravedad media y **gravedad** baja.</span><span class="sxs-lookup"><span data-stu-id="7f628-148">**View data by Exchange transport rules** \> **Chart breakdown by Severity**: This chart shows the number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="7f628-149">El nivel de gravedad se establece como una acción en la regla (**Auditar** esta regla con el nivel de gravedad o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="7f628-149">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="7f628-150">Para obtener más información, vea [Acciones de regla de flujo de correo en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="7f628-150">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="7f628-151">**Ver datos por reglas de transporte** \> de Dlp Exchange **Desglose del gráfico por dirección:**  este  gráfico muestra el número de mensajes entrantes y salientes que se vieron afectados por las reglas de flujo de correo de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="7f628-151">**View data by DLP Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

- <span data-ttu-id="7f628-152">**Ver datos por reglas de transporte** \> de Dlp Exchange **Desglose del gráfico por gravedad:** esta vista muestra el número  de mensajes de gravedad **alta,** gravedad media y gravedad baja que se vieron afectados por las reglas de flujo de correo DLP.</span><span class="sxs-lookup"><span data-stu-id="7f628-152">**View data by DLP Exchange transport rules** \> **Chart breakdown by Severity**: This view shows the number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="7f628-153">Para **ver los datos por selecciones** de reglas de transporte de Exchange, la siguiente información se muestra en la tabla de detalles debajo del gráfico:</span><span class="sxs-lookup"><span data-stu-id="7f628-153">For **View data by Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="7f628-154">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="7f628-154">**Date**</span></span>
- <span data-ttu-id="7f628-155">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="7f628-155">**Transport rule**</span></span>
- <span data-ttu-id="7f628-156">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="7f628-156">**Subject**</span></span>
- <span data-ttu-id="7f628-157">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="7f628-157">**Sender address**</span></span>
- <span data-ttu-id="7f628-158">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="7f628-158">**Recipient address**</span></span>
- <span data-ttu-id="7f628-159">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="7f628-159">**Severity**</span></span>
- <span data-ttu-id="7f628-160">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="7f628-160">**Direction**</span></span>

<span data-ttu-id="7f628-161">Para **ver datos por selecciones de** reglas de transporte de DLP Exchange, la siguiente información se muestra en la tabla de detalles debajo del gráfico:</span><span class="sxs-lookup"><span data-stu-id="7f628-161">For **View data by DLP Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="7f628-162">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="7f628-162">**Date**</span></span>
- <span data-ttu-id="7f628-163">**Directiva DLP**</span><span class="sxs-lookup"><span data-stu-id="7f628-163">**DLP policy**</span></span>
- <span data-ttu-id="7f628-164">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="7f628-164">**Transport rule**</span></span>
- <span data-ttu-id="7f628-165">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="7f628-165">**Subject**</span></span>
- <span data-ttu-id="7f628-166">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="7f628-166">**Sender address**</span></span>
- <span data-ttu-id="7f628-167">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="7f628-167">**Recipient address**</span></span>
- <span data-ttu-id="7f628-168">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="7f628-168">**Severity**</span></span>
- <span data-ttu-id="7f628-169">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="7f628-169">**Direction**</span></span>

<span data-ttu-id="7f628-170">Puede filtrar tanto el gráfico como  la tabla de detalles haciendo clic en Filtrar y seleccionando uno o varios de los siguientes valores en el menú desplegable que aparece:</span><span class="sxs-lookup"><span data-stu-id="7f628-170">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="7f628-171">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="7f628-171">**Start date** and **End date**</span></span>
- <span data-ttu-id="7f628-172">**Dirección:** **saliente** y **entrante**</span><span class="sxs-lookup"><span data-stu-id="7f628-172">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="7f628-173">**Gravedad:** **gravedad alta,** **gravedad media** y **gravedad baja**</span><span class="sxs-lookup"><span data-stu-id="7f628-173">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

![Vista Informe en el informe de reglas de transporte de Exchange](../../media/transport-rule-report-report-view.png)

## <a name="mailflow-status-report"></a><span data-ttu-id="7f628-175">Informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="7f628-175">Mailflow status report</span></span>

<span data-ttu-id="7f628-176">El **informe de** estado de flujo de correo es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, las detecciones de correo no deseado, el malware, el correo electrónico identificado como "bueno" y la información sobre el correo electrónico permitido o bloqueado en el perímetro.</span><span class="sxs-lookup"><span data-stu-id="7f628-176">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="7f628-177">Este es el único informe que contiene información de protección perimetral y muestra cuánto correo electrónico se bloquea antes de que exchange Online Protection (EOP) pueda evaluarlo.</span><span class="sxs-lookup"><span data-stu-id="7f628-177">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="7f628-178">Es importante comprender que si un mensaje se envía a cinco destinatarios, lo contamos como cinco mensajes diferentes y no un mensaje.</span><span class="sxs-lookup"><span data-stu-id="7f628-178">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="7f628-179">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & colaboración Correo electrónico \>  \> **& informes de colaboración.**</span><span class="sxs-lookup"><span data-stu-id="7f628-179">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="7f628-180">En **Resumen de estado de flujo de correo,** haga clic en Ver **detalles**.</span><span class="sxs-lookup"><span data-stu-id="7f628-180">On **Mailflow status summary**, click **View details**.</span></span> <span data-ttu-id="7f628-181">Para ir directamente al informe, abra <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="7f628-181">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Widget de resumen de estado de flujo de correo en la página Informes de colaboración & correo electrónico](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="7f628-183">Vista de tipo para el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="7f628-183">Type view for the Mailflow status report</span></span>

<span data-ttu-id="7f628-184">Al abrir el informe, la **pestaña Tipo** está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7f628-184">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="7f628-185">De forma predeterminada, esta vista contiene un gráfico y una tabla de datos configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f628-185">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="7f628-186">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="7f628-186">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="7f628-187">**Dirección del correo**:</span><span class="sxs-lookup"><span data-stu-id="7f628-187">**Mail direction**:</span></span>
  - <span data-ttu-id="7f628-188">**Entrante**</span><span class="sxs-lookup"><span data-stu-id="7f628-188">**Inbound**</span></span>
  - <span data-ttu-id="7f628-189">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="7f628-189">**Outbound**</span></span>
  - <span data-ttu-id="7f628-190">**Intra-org:** este recuento es para mensajes dentro de un espacio empresarial, es decir,</span><span class="sxs-lookup"><span data-stu-id="7f628-190">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="7f628-191">sender abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de **Entrante** y **Saliente**)</span><span class="sxs-lookup"><span data-stu-id="7f628-191">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="7f628-192">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="7f628-192">**Type**:</span></span>
  - <span data-ttu-id="7f628-193">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="7f628-193">**Good mail**</span></span>
  - <span data-ttu-id="7f628-194">**Malware**</span><span class="sxs-lookup"><span data-stu-id="7f628-194">**Malware**</span></span>
  - <span data-ttu-id="7f628-195">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="7f628-195">**Spam**</span></span>
  - <span data-ttu-id="7f628-196">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="7f628-196">**Edge protection**</span></span>
  - <span data-ttu-id="7f628-197">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="7f628-197">**Rule messages**</span></span>
  - <span data-ttu-id="7f628-198">**Correo de suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="7f628-198">**Phishing email**</span></span>
- <span data-ttu-id="7f628-199">**Dominio**: **Todos**</span><span class="sxs-lookup"><span data-stu-id="7f628-199">**Domain**: **All**</span></span>

<span data-ttu-id="7f628-200">El gráfico está organizado por los **valores Type.**</span><span class="sxs-lookup"><span data-stu-id="7f628-200">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="7f628-201">Puede cambiar estos filtros haciendo clic en **Filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="7f628-201">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="7f628-202">La tabla de datos contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7f628-202">The data table contains the following information:</span></span>

- <span data-ttu-id="7f628-203">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="7f628-203">**Direction**</span></span>
- <span data-ttu-id="7f628-204">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7f628-204">**Type**</span></span>
- <span data-ttu-id="7f628-205">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="7f628-205">**24 hours**</span></span>
- <span data-ttu-id="7f628-206">**3 días**</span><span class="sxs-lookup"><span data-stu-id="7f628-206">**3 days**</span></span>
- <span data-ttu-id="7f628-207">**7 días**</span><span class="sxs-lookup"><span data-stu-id="7f628-207">**7 days**</span></span>
- <span data-ttu-id="7f628-208">**15 días**</span><span class="sxs-lookup"><span data-stu-id="7f628-208">**15 days**</span></span>
- <span data-ttu-id="7f628-209">**30 días**</span><span class="sxs-lookup"><span data-stu-id="7f628-209">**30 days**</span></span>

<span data-ttu-id="7f628-210">Si hace clic **en Elegir una categoría para obtener más información,** puede seleccionar entre los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="7f628-210">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="7f628-211">**Correo electrónico de suplantación** de identidad : esta selección le lleva al informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="7f628-211">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="7f628-212">**Malware en el correo** electrónico: esta selección le lleva al informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="7f628-212">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="7f628-213">**Detecciones de correo** no deseado: esta selección le lleva al informe [Detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="7f628-213">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="7f628-214">**Correo no deseado bloqueado** perimetral: esta selección le lleva al informe [Detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="7f628-214">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="7f628-215">Exportar desde la vista Tipo</span><span class="sxs-lookup"><span data-stu-id="7f628-215">Export from Type view</span></span>

<span data-ttu-id="7f628-216">Para la vista de detalles, solo puede exportar datos durante un día.</span><span class="sxs-lookup"><span data-stu-id="7f628-216">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="7f628-217">Por lo tanto, si desea exportar datos durante 7 días, debe realizar 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="7f628-217">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="7f628-218">Cada archivo .csv exportada está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="7f628-218">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="7f628-219">Si los datos de ese día contienen más de 150.000 filas, se crearán varios .csv archivos.</span><span class="sxs-lookup"><span data-stu-id="7f628-219">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Vista De tipo en el informe de estado de flujo de correo](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="7f628-221">Vista Dirección del informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="7f628-221">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="7f628-222">Si hace clic en la **pestaña Dirección,** se usan los mismos filtros predeterminados de la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="7f628-222">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="7f628-223">El gráfico está organizado por valores **direction.**</span><span class="sxs-lookup"><span data-stu-id="7f628-223">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="7f628-224">Puede cambiar estos filtros haciendo clic en **Filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="7f628-224">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="7f628-225">Se usan los mismos filtros de **la vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="7f628-225">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="7f628-226">La tabla de datos contiene la misma información de la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="7f628-226">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="7f628-227">La **categoría Elegir una categoría para obtener más detalles** sobre las selecciones y el comportamiento disponibles son los mismos que la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="7f628-227">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="7f628-228">Exportar desde la vista Dirección</span><span class="sxs-lookup"><span data-stu-id="7f628-228">Export from Direction view</span></span>

<span data-ttu-id="7f628-229">Para la vista de detalles, solo puede exportar datos durante un día.</span><span class="sxs-lookup"><span data-stu-id="7f628-229">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="7f628-230">Por lo tanto, si desea exportar datos durante 7 días, debe realizar 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="7f628-230">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="7f628-231">Cada archivo .csv exportada está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="7f628-231">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="7f628-232">Si los datos de ese día contienen más de 150.000 filas, se crearán varios .csv archivos.</span><span class="sxs-lookup"><span data-stu-id="7f628-232">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Vista Dirección en el informe de estado de flujo de correo](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="7f628-234">Vista embudo para el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="7f628-234">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="7f628-235">La **vista Embudo** muestra cómo las características de protección contra amenazas de correo electrónico de Microsoft filtran el correo electrónico entrante y saliente en su organización.</span><span class="sxs-lookup"><span data-stu-id="7f628-235">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="7f628-236">Proporciona detalles sobre el recuento total de correo electrónico y cómo afectan a este recuento las características de protección contra amenazas configuradas, como la protección perimetral, el antimalware, la suplantación de identidad (phishing), el correo no deseado y la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="7f628-236">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="7f628-237">Si hace clic en la **pestaña Embudo,** de forma predeterminada, esta vista contiene un gráfico y una tabla de datos configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f628-237">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="7f628-238">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="7f628-238">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="7f628-239">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="7f628-239">**Direction**:</span></span>

  - <span data-ttu-id="7f628-240">**Entrante**</span><span class="sxs-lookup"><span data-stu-id="7f628-240">**Inbound**</span></span>
  - <span data-ttu-id="7f628-241">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="7f628-241">**Outbound**</span></span>
  - <span data-ttu-id="7f628-242">**Intra-org:** este recuento es para los mensajes enviados dentro de un espacio empresarial; Es decir, el remitente abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de Entrante y Saliente).</span><span class="sxs-lookup"><span data-stu-id="7f628-242">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="7f628-243">La vista de agregado y la vista de tabla de datos permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="7f628-243">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="7f628-244">Si hace clic **en Filtrar,** puede filtrar tanto el gráfico como la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="7f628-244">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="7f628-245">Este gráfico muestra el recuento de correo electrónico organizado por:</span><span class="sxs-lookup"><span data-stu-id="7f628-245">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="7f628-246">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="7f628-246">**Total email**</span></span>
- <span data-ttu-id="7f628-247">**Correo electrónico después de la protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="7f628-247">**Email after edge protection**</span></span>
- <span data-ttu-id="7f628-248">**Correo electrónico después de la regla de transporte** (regla de flujo de correo)</span><span class="sxs-lookup"><span data-stu-id="7f628-248">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="7f628-249">**Correo electrónico después de antimalware, reputación de archivo, bloqueo de tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="7f628-249">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="7f628-250">**Correo electrónico después de anti phish, reputación url, suplantación de marca, anti suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="7f628-250">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="7f628-251">**Correo electrónico después de correo no deseado, filtrado masivo de correo**</span><span class="sxs-lookup"><span data-stu-id="7f628-251">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="7f628-252">**Correo electrónico después de la suplantación de usuario y dominio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f628-252">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="7f628-253">**Email after file and URL detonation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f628-253">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="7f628-254">**Correo electrónico detectado como benigno después de la protección posterior a la entrega (url click time protection)**</span><span class="sxs-lookup"><span data-stu-id="7f628-254">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="7f628-255"><sup>\*</sup>Solo defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7f628-255"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="7f628-256">Para ver el correo electrónico filtrado por EOP o Defender Office 365 por separado, haga clic en el valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="7f628-256">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="7f628-257">La tabla de datos contiene la siguiente información, que se muestra en orden de fecha descendente:</span><span class="sxs-lookup"><span data-stu-id="7f628-257">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="7f628-258">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="7f628-258">**Date**</span></span>
- <span data-ttu-id="7f628-259">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="7f628-259">**Total email**</span></span>
- <span data-ttu-id="7f628-260">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="7f628-260">**Edge protection**</span></span>
- <span data-ttu-id="7f628-261">**Antimalware, reputación de archivo, bloque de tipo de archivo:**</span><span class="sxs-lookup"><span data-stu-id="7f628-261">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="7f628-262">**Reputación del archivo:** mensajes filtrados debido a la identificación de un archivo adjunto por otros clientes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f628-262">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="7f628-263">**Bloque de tipo de** archivo: mensajes filtrados debido al tipo de archivo malintencionado identificado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="7f628-263">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="7f628-264">**Anti-phish, reputación url, suplantación de marca, suplantación de identidad:**</span><span class="sxs-lookup"><span data-stu-id="7f628-264">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="7f628-265">**Reputación de la dirección URL:** mensajes filtrados debido a la identificación de la dirección URL por otros clientes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f628-265">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="7f628-266">**Suplantación de marca:** mensajes filtrados debido al mensaje procedente de remitentes de suplantación de marca conocidos.</span><span class="sxs-lookup"><span data-stu-id="7f628-266">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="7f628-267">**Anti-spoof:** mensajes filtrados debido a que el mensaje intenta suplantar un dominio al que pertenece el destinatario o un dominio que el remitente del mensaje no posee.</span><span class="sxs-lookup"><span data-stu-id="7f628-267">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="7f628-268">**Antispam, filtrado masivo de correo:**</span><span class="sxs-lookup"><span data-stu-id="7f628-268">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="7f628-269">**Filtrado masivo de correo:** mensajes filtrados según el umbral de nivel de queja masiva (BCL) en una directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="7f628-269">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="7f628-270">**Suplantación de usuario y dominio (Defender para Office 365):**</span><span class="sxs-lookup"><span data-stu-id="7f628-270">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="7f628-271">Suplantación de **usuario:** mensajes filtrados debido a un intento de suplantar a un usuario (remitente de mensajes) que se define en la configuración de protección de suplantación de una directiva contra suplantación.</span><span class="sxs-lookup"><span data-stu-id="7f628-271">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="7f628-272">**Suplantación** de dominio: mensajes filtrados debido a un intento de suplantar un dominio definido en la configuración de protección de suplantación de una directiva contra suplantación.</span><span class="sxs-lookup"><span data-stu-id="7f628-272">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="7f628-273">**Detonación de archivos y direcciones URL (Defender para Office 365):**</span><span class="sxs-lookup"><span data-stu-id="7f628-273">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="7f628-274">**Detonación de archivos:** mensajes filtrados por una directiva Caja fuerte datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="7f628-274">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="7f628-275">**Detonación de dirección URL:** mensaje filtrado por una directiva Caja fuerte vínculos.</span><span class="sxs-lookup"><span data-stu-id="7f628-275">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="7f628-276">Protección posterior a la entrega y **ZAP (ATP) o ZAP (EOP):** purga automática de hora cero (ZAP) para malware, correo no deseado y phishing.</span><span class="sxs-lookup"><span data-stu-id="7f628-276">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="7f628-277">Si selecciona una fila en la tabla de datos, se muestra un desglose adicional de los recuentos de correo electrónico en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="7f628-277">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="7f628-278">Exportar desde la vista Embudo</span><span class="sxs-lookup"><span data-stu-id="7f628-278">Export from Funnel view</span></span>

<span data-ttu-id="7f628-279">Después de hacer **clic en Exportar** en **Opciones,** puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="7f628-279">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="7f628-280">**Resumen (con datos de los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="7f628-280">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="7f628-281">**Detalles (con datos de los últimos 30 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="7f628-281">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="7f628-282">En **Fecha**, elija un rango y, a continuación, haga clic **en Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="7f628-282">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="7f628-283">Los datos de los filtros actuales se exportarán a un .csv archivo.</span><span class="sxs-lookup"><span data-stu-id="7f628-283">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="7f628-284">Cada archivo .csv exportada está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="7f628-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="7f628-285">Si los datos contienen más de 150 000 filas, se crearán varios .csv archivos.</span><span class="sxs-lookup"><span data-stu-id="7f628-285">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Vista embudo en el informe de estado de flujo de correo](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="7f628-287">Vista técnica del informe de estado del flujo de correo</span><span class="sxs-lookup"><span data-stu-id="7f628-287">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="7f628-288">La **vista Tech es** similar a la vista **Embudo,** lo que proporciona más detalles pormenorizados para las características de protección contra amenazas configuradas.</span><span class="sxs-lookup"><span data-stu-id="7f628-288">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="7f628-289">En el gráfico, puede ver cómo se clasifican los mensajes en las distintas etapas de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="7f628-289">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="7f628-290">Si hace clic en la **pestaña Vista técnica,** de forma predeterminada, esta vista contiene un gráfico y una tabla de datos configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f628-290">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="7f628-291">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="7f628-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="7f628-292">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="7f628-292">**Direction**:</span></span>

  - <span data-ttu-id="7f628-293">**Entrante**</span><span class="sxs-lookup"><span data-stu-id="7f628-293">**Inbound**</span></span>
  - <span data-ttu-id="7f628-294">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="7f628-294">**Outbound**</span></span>
  - <span data-ttu-id="7f628-295">**Intra-org:** este recuento es para mensajes dentro de un espacio empresarial, es decir,</span><span class="sxs-lookup"><span data-stu-id="7f628-295">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="7f628-296">remitente abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de Entrante y Saliente)</span><span class="sxs-lookup"><span data-stu-id="7f628-296">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="7f628-297">La vista de agregado y la vista de tabla de datos permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="7f628-297">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="7f628-298">Si hace clic **en Filtrar,** puede filtrar tanto el gráfico como la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="7f628-298">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="7f628-299">En este gráfico se muestran los mensajes organizados en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="7f628-299">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="7f628-300">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="7f628-300">**Total email**</span></span>
- <span data-ttu-id="7f628-301">**Edge allow** y **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="7f628-301">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="7f628-302">**Regla de transporte permitido** y **regla de transporte filtrada** (reglas de flujo de correo)</span><span class="sxs-lookup"><span data-stu-id="7f628-302">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="7f628-303">**No malware,** **detección Caja fuerte datos adjuntos** y detección de motores <sup>\*</sup> **antimalware**</span><span class="sxs-lookup"><span data-stu-id="7f628-303">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="7f628-304">**No phish**, **error DMARC,** **detección de suplantación,** detección <sup>\*</sup> de **suplantación** y detección **de suplantación** de identidad</span><span class="sxs-lookup"><span data-stu-id="7f628-304">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="7f628-305">**No hay detección con detonación de dirección URL** y **detonación de url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f628-305">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="7f628-306">**No correo no** deseado y  **correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="7f628-306">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="7f628-307">**Correo electrónico no malintencionado,** **Caja fuerte de detección de vínculos y** <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="7f628-307">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="7f628-308"><sup>\*</sup>Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7f628-308"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="7f628-309">Al pasar el mouse sobre una categoría del gráfico, puede ver el número de mensajes de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="7f628-309">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="7f628-310">La tabla de datos contiene la siguiente información, que se muestra en orden de fecha descendente:</span><span class="sxs-lookup"><span data-stu-id="7f628-310">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="7f628-311">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="7f628-311">**Date**</span></span>
- <span data-ttu-id="7f628-312">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="7f628-312">**Total email**</span></span>
- <span data-ttu-id="7f628-313">**Perímetro filtrado**</span><span class="sxs-lookup"><span data-stu-id="7f628-313">**Edge filtered**</span></span>
- <span data-ttu-id="7f628-314">**Mensajes de regla:** mensajes filtrados debido a reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="7f628-314">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="7f628-315">**Motor antimalware**, **Caja fuerte datos adjuntos** <sup>\*</sup> :</span><span class="sxs-lookup"><span data-stu-id="7f628-315">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="7f628-316">**DMARC, suplantación,** <sup>\*</sup> **suplantación, suplantación** de **identidad filtrada**:</span><span class="sxs-lookup"><span data-stu-id="7f628-316">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="7f628-317">**DMARC:** mensajes filtrados debido a que el mensaje no ha fallado en la comprobación de autenticación de DMARC.</span><span class="sxs-lookup"><span data-stu-id="7f628-317">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="7f628-318">**Detección de detonación de url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f628-318">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="7f628-319">**Filtrado contra correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="7f628-319">**Anti-spam filtered**</span></span>
- <span data-ttu-id="7f628-320">**ZAP quitado**</span><span class="sxs-lookup"><span data-stu-id="7f628-320">**ZAP removed**</span></span>
- <span data-ttu-id="7f628-321">**Detección por Caja fuerte vínculos**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f628-321">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="7f628-322"><sup>\*</sup>Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7f628-322"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="7f628-323">Si selecciona una fila en la tabla de datos, se muestra un desglose adicional de los recuentos de correo electrónico en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="7f628-323">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="7f628-324">Exportar desde la vista Tech</span><span class="sxs-lookup"><span data-stu-id="7f628-324">Export from Tech view</span></span>

<span data-ttu-id="7f628-325">Al hacer **clic en** Exportar , en **Opciones,** puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="7f628-325">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="7f628-326">**Resumen (con datos de los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="7f628-326">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="7f628-327">**Detalles (con datos de los últimos 30 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="7f628-327">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="7f628-328">En **Fecha**, elija un rango y, a continuación, haga clic **en Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="7f628-328">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="7f628-329">Los datos de los filtros actuales se exportarán a un .csv archivo.</span><span class="sxs-lookup"><span data-stu-id="7f628-329">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="7f628-330">Cada archivo .csv exportada está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="7f628-330">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="7f628-331">Si los datos contienen más de 150 000 filas, se crearán varios .csv archivos.</span><span class="sxs-lookup"><span data-stu-id="7f628-331">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Vista técnica en el informe de estado del flujo de correo](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="7f628-333">Informe de detecciones de malware</span><span class="sxs-lookup"><span data-stu-id="7f628-333">Malware detections report</span></span>

<span data-ttu-id="7f628-334">El **informe de detecciones** de malware muestra información sobre detecciones de malware en mensajes de correo electrónico entrantes y salientes (malware detectado por Exchange Online Protection o EOP).</span><span class="sxs-lookup"><span data-stu-id="7f628-334">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="7f628-335">Para obtener más información acerca de la protección contra malware en EOP, vea [Protección contra malware en EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-335">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="7f628-336">El filtro de vista agregado permite 90 días, mientras que el filtro de tabla de detalles solo permite 10 días.</span><span class="sxs-lookup"><span data-stu-id="7f628-336">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="7f628-337">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="7f628-337">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="7f628-338">En **Malware detectado en el correo electrónico,** haga clic en Ver **detalles**.</span><span class="sxs-lookup"><span data-stu-id="7f628-338">On **Malware detected in email**, click **View details**.</span></span> <span data-ttu-id="7f628-339">Para ir directamente al informe, abra <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="7f628-339">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Detecciones de malware en el widget de correo electrónico en la página Informes de & de colaboración](../../media/malware-detections-widget.png)

<span data-ttu-id="7f628-341">Después de hacer clic **en Ver detalles,** puede filtrar tanto el gráfico como la tabla de detalles haciendo clic **en Filtrar** y seleccionando:</span><span class="sxs-lookup"><span data-stu-id="7f628-341">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting:</span></span>

- <span data-ttu-id="7f628-342">**Fecha:** **Fecha de inicio** y fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="7f628-342">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="7f628-343">**Dirección:** **entrante** y **saliente**</span><span class="sxs-lookup"><span data-stu-id="7f628-343">**Direction**: **Inbound** and **Outbound**</span></span>

![Vista Informe en el informe de detección de malware en el correo electrónico](../../media/malware-detections-report-view.png)

<span data-ttu-id="7f628-345">En la tabla de detalles debajo del gráfico, puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="7f628-345">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="7f628-346">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="7f628-346">**Date**</span></span>
- <span data-ttu-id="7f628-347">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="7f628-347">**Sender address**</span></span>
- <span data-ttu-id="7f628-348">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="7f628-348">**Recipient address**</span></span>
- <span data-ttu-id="7f628-349">**Id. de** mensaje: disponible en el **campo de encabezado Id. de** mensaje en el encabezado del mensaje y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="7f628-349">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="7f628-350">Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (tenga en cuenta los corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="7f628-350">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="7f628-351">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="7f628-351">**Subject**</span></span>
- <span data-ttu-id="7f628-352">**Filename**</span><span class="sxs-lookup"><span data-stu-id="7f628-352">**Filename**</span></span>
- <span data-ttu-id="7f628-353">**Nombre de malware**</span><span class="sxs-lookup"><span data-stu-id="7f628-353">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="7f628-354">Informe de latencia de correo</span><span class="sxs-lookup"><span data-stu-id="7f628-354">Mail latency report</span></span>

<span data-ttu-id="7f628-355">El **informe de latencia de** correo en Defender para Office 365 contiene información sobre la latencia de entrega y detonación de correo experimentada en su organización.</span><span class="sxs-lookup"><span data-stu-id="7f628-355">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="7f628-356">Para obtener más información, vea [Informe de latencia de correo](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="7f628-356">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="7f628-357">Informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="7f628-357">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="7f628-358">El **informe de detecciones de correo** no deseado desaparecerá el 30 de junio de 2021.</span><span class="sxs-lookup"><span data-stu-id="7f628-358">The **Spam detections report** will go away on June 30, 2021.</span></span> <span data-ttu-id="7f628-359">La misma información está disponible en el informe [de estado de protección contra amenazas](#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="7f628-359">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="7f628-360">Informe de detecciones de suplantación</span><span class="sxs-lookup"><span data-stu-id="7f628-360">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="7f628-361">El informe de detecciones de suplantación mejoradas, tal como se describe en este artículo, está en versión preliminar, está sujeto a cambios y no está disponible en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="7f628-361">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="7f628-362">La versión anterior del informe muestra solo **Correo bueno** y Capturado como correo **no deseado.**</span><span class="sxs-lookup"><span data-stu-id="7f628-362">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="7f628-363">El **informe Detecciones** de suplantación muestra información sobre los mensajes bloqueados o permitidos debido a la suplantación.</span><span class="sxs-lookup"><span data-stu-id="7f628-363">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="7f628-364">Para obtener más información acerca de la suplantación, vea Protección contra la suplantación [en EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-364">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="7f628-365">La vista de agregado del informe permite 45 días de filtrado, mientras que la vista de detalles solo permite <sup>\*</sup> diez días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="7f628-365">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="7f628-366"><sup>\*</sup> Con el tiempo, podrás usar hasta 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="7f628-366"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="7f628-367">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="7f628-367">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="7f628-368">En **Detecciones de suplantación,** haga clic **en Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="7f628-368">On **Spoof detections**, click **View details**.</span></span> <span data-ttu-id="7f628-369">Para ir directamente al informe, abra <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="7f628-369">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Widget Detecciones de suplantación en la página Informes de colaboración & correo electrónico](../../media/spoof-detections-widget.png)

<span data-ttu-id="7f628-371">Al pasar el mouse sobre un día (punto de datos) en el gráfico, puede ver cuántos mensajes suplantados se detectaron y por qué.</span><span class="sxs-lookup"><span data-stu-id="7f628-371">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="7f628-372">Después de hacer clic **en Ver** detalles, puede filtrar tanto el gráfico como la tabla de detalles haciendo clic en **Filtrar** y seleccionando uno o varios de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="7f628-372">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="7f628-373">**Fecha:** **Fecha de inicio** y fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="7f628-373">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="7f628-374">**Resultado**:</span><span class="sxs-lookup"><span data-stu-id="7f628-374">**Result**:</span></span>
  - <span data-ttu-id="7f628-375">**Pasar**</span><span class="sxs-lookup"><span data-stu-id="7f628-375">**Pass**</span></span>
  - <span data-ttu-id="7f628-376">**Error**</span><span class="sxs-lookup"><span data-stu-id="7f628-376">**Fail**</span></span>
  - <span data-ttu-id="7f628-377">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="7f628-377">**SoftPass**</span></span>
  - <span data-ttu-id="7f628-378">**Ninguna**</span><span class="sxs-lookup"><span data-stu-id="7f628-378">**None**</span></span>
  - <span data-ttu-id="7f628-379">**Otros**</span><span class="sxs-lookup"><span data-stu-id="7f628-379">**Other**</span></span>
- <span data-ttu-id="7f628-380">**Tipo de suplantación:** **Interno** y **Externo**</span><span class="sxs-lookup"><span data-stu-id="7f628-380">**Spoof type**: **Internal** and **External**</span></span>

![Página de informe de correo suplantación en el portal Microsoft 365 Defender correo](../../media/spoof-detections-report-page.png)

<span data-ttu-id="7f628-382">En la tabla debajo del gráfico, puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="7f628-382">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="7f628-383">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="7f628-383">**Date**</span></span>
- <span data-ttu-id="7f628-384">**Usuario suplantado**</span><span class="sxs-lookup"><span data-stu-id="7f628-384">**Spoofed user**</span></span>
- <span data-ttu-id="7f628-385">**Infraestructura de envío**</span><span class="sxs-lookup"><span data-stu-id="7f628-385">**Sending infrastructure**</span></span>
- <span data-ttu-id="7f628-386">**Tipo de suplantación**</span><span class="sxs-lookup"><span data-stu-id="7f628-386">**Spoof type**</span></span>
- <span data-ttu-id="7f628-387">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="7f628-387">**Result**</span></span>
- <span data-ttu-id="7f628-388">**Código de resultados**</span><span class="sxs-lookup"><span data-stu-id="7f628-388">**Result code**</span></span>
- <span data-ttu-id="7f628-389">**SPF**</span><span class="sxs-lookup"><span data-stu-id="7f628-389">**SPF**</span></span>
- <span data-ttu-id="7f628-390">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="7f628-390">**DKIM**</span></span>
- <span data-ttu-id="7f628-391">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="7f628-391">**DMARC**</span></span>
- <span data-ttu-id="7f628-392">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="7f628-392">**Message count**</span></span>

<span data-ttu-id="7f628-393">Para obtener más información acerca de los códigos de resultados de autenticación compuesta, vea [Encabezados de mensajes](anti-spam-message-headers.md)contra correo no deseado en Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="7f628-393">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="7f628-394">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="7f628-394">Threat protection status report</span></span>

<span data-ttu-id="7f628-395">El **informe de estado de** protección contra amenazas está disponible en EOP y Defender para Office 365; sin embargo, los informes contienen datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="7f628-395">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="7f628-396">Por ejemplo, los clientes de EOP pueden ver información sobre malware detectado en el correo electrónico, pero no información sobre archivos malintencionados detectados por [Caja fuerte Attachments for SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)y Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="7f628-396">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="7f628-397">El informe proporciona el recuento de mensajes de correo electrónico con contenido malintencionado, como archivos o direcciones de sitios web (DIRECCIONES URL) bloqueadas por el motor antimalware, purga automática de hora cero [(ZAP)](zero-hour-auto-purge.md)y Defender para características de Office 365 como vínculos [de Caja fuerte,](safe-links.md)datos adjuntos de [Caja fuerte](safe-attachments.md)y características de protección de suplantación en directivas [contra suplantación.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="7f628-397">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="7f628-398">Puede usar esta información para identificar tendencias o determinar si las directivas de la organización necesitan ajustes.</span><span class="sxs-lookup"><span data-stu-id="7f628-398">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="7f628-399">**Nota:** Es importante comprender que si un mensaje se envía a cinco destinatarios, lo contamos como cinco mensajes diferentes y no un mensaje.</span><span class="sxs-lookup"><span data-stu-id="7f628-399">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="7f628-400">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="7f628-400">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="7f628-401">En **Estado de protección contra amenazas,** haga clic en Ver **detalles**.</span><span class="sxs-lookup"><span data-stu-id="7f628-401">On **Threat protection status**, click **View details**.</span></span> <span data-ttu-id="7f628-402">Para ir directamente al informe, abra una de las siguientes direcciones URL:</span><span class="sxs-lookup"><span data-stu-id="7f628-402">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="7f628-403">Defender para Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="7f628-403">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="7f628-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="7f628-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Widget de estado de protección contra amenazas en la página Informes de colaboración & correo electrónico](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="7f628-406">De forma predeterminada, después de hacer clic en **Ver detalles,** el gráfico muestra los datos de los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="7f628-406">By default, after you click **View details**, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="7f628-407">Si hace clic **en Filtrar,** puede seleccionar un intervalo de fechas de 90 días (las suscripciones de prueba podrían estar limitadas a 30 días).</span><span class="sxs-lookup"><span data-stu-id="7f628-407">If you click **Filter**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="7f628-408">La tabla de detalles permite filtrar durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="7f628-408">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="7f628-409">Las vistas disponibles se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="7f628-409">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="7f628-410">Ver datos por información general</span><span class="sxs-lookup"><span data-stu-id="7f628-410">View data by Overview</span></span>

![Vista general en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="7f628-412">En la **vista Ver datos por información** general, se muestra la siguiente información de detección en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="7f628-412">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="7f628-413">**Malware de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="7f628-413">**Email malware**</span></span>
- <span data-ttu-id="7f628-414">**Phish de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="7f628-414">**Email phish**</span></span>
- <span data-ttu-id="7f628-415">**Malware de contenido**</span><span class="sxs-lookup"><span data-stu-id="7f628-415">**Content malware**</span></span>

<span data-ttu-id="7f628-416">No hay ninguna tabla de detalles disponible debajo del gráfico.</span><span class="sxs-lookup"><span data-stu-id="7f628-416">No details table is available below the chart.</span></span>

<span data-ttu-id="7f628-417">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="7f628-417">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="7f628-418">**Fecha:** **Fecha de inicio** y fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="7f628-418">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="7f628-419">**Detección:** **malware de correo** electrónico, **suplantación** de identidad de correo electrónico o **malware de contenido**</span><span class="sxs-lookup"><span data-stu-id="7f628-419">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="7f628-420">**Protegido por**: **MDO** (Defender para Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="7f628-420">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="7f628-421">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="7f628-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="7f628-422">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="7f628-423">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="7f628-423">**Direction**</span></span>
- <span data-ttu-id="7f628-424">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="7f628-424">**Domain**</span></span>
- <span data-ttu-id="7f628-425">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="7f628-425">**Policy type**</span></span>

<span data-ttu-id="7f628-426">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="7f628-426">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="7f628-427">Ver datos por phishing de \> correo electrónico y desglose de gráficos por tecnología de detección</span><span class="sxs-lookup"><span data-stu-id="7f628-427">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Vista de tecnología de detección para correo electrónico de suplantación de identidad (phishing) en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="7f628-429">En la vista Ver  **datos por \> phishing** de correo electrónico y desglose de gráficos por tecnología de detección, se muestra la siguiente información en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="7f628-429">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="7f628-430">**Reputación malintencionada** de la dirección URL: reputación de url malintencionada generada desde <sup>\*</sup> Defender para Office 365 detonaciones en otros Microsoft 365 cliente.</span><span class="sxs-lookup"><span data-stu-id="7f628-430">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="7f628-431">**Filtro avanzado:** señales de suplantación de identidad basadas en el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="7f628-431">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="7f628-432">**Filtro general:** señales de suplantación de identidad basadas en reglas de analista.</span><span class="sxs-lookup"><span data-stu-id="7f628-432">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="7f628-433">**Suplantación de** identidad dentro de la organización: el remitente está intentando suplantación del dominio de destinatario.</span><span class="sxs-lookup"><span data-stu-id="7f628-433">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="7f628-434">**Suplantación de dominio externo:** el remitente está intentando suplantación de identidad de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="7f628-434">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="7f628-435">**Spoof DMARC:** error de autenticación DMARC en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="7f628-435">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="7f628-436">**Marca de suplantación:** suplantación de marcas conocidas basadas en remitentes.</span><span class="sxs-lookup"><span data-stu-id="7f628-436">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="7f628-437">**Detección de análisis mixto**</span><span class="sxs-lookup"><span data-stu-id="7f628-437">**Mixed analysis detection**</span></span>
- <span data-ttu-id="7f628-438">**Reputación de los archivos**</span><span class="sxs-lookup"><span data-stu-id="7f628-438">**File reputation**</span></span>
- <span data-ttu-id="7f628-439">**Coincidencia de huella digital**</span><span class="sxs-lookup"><span data-stu-id="7f628-439">**Fingerprint matching**</span></span>
- <span data-ttu-id="7f628-440">**Reputación de detonación de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f628-440">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="7f628-441">**Detonación de dirección URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f628-441">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="7f628-442">**Usuario de suplantación**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f628-442">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="7f628-443">**Dominio de suplantación:** <sup>\*</sup> suplantación de dominios que el cliente posee o define.</span><span class="sxs-lookup"><span data-stu-id="7f628-443">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="7f628-444">**Suplantación de inteligencia de buzones:** suplantación de usuarios definida por el administrador o aprendida a través <sup>\*</sup> de la inteligencia de buzones.</span><span class="sxs-lookup"><span data-stu-id="7f628-444">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="7f628-445">**Detonación de archivos**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f628-445">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="7f628-446">**Campaña**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f628-446">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="7f628-447">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7f628-447">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="7f628-448">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="7f628-448">**Date**</span></span>
- <span data-ttu-id="7f628-449">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="7f628-449">**Subject**</span></span>
- <span data-ttu-id="7f628-450">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="7f628-450">**Sender**</span></span>
- <span data-ttu-id="7f628-451">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="7f628-451">**Recipients**</span></span>
- <span data-ttu-id="7f628-452">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="7f628-452">**Detected by**</span></span>
- <span data-ttu-id="7f628-453">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="7f628-453">**Delivery Status**</span></span>
- <span data-ttu-id="7f628-454">**Origen de la transacción**</span><span class="sxs-lookup"><span data-stu-id="7f628-454">**Source of Compromise**</span></span>
- <span data-ttu-id="7f628-455">**Tags**</span><span class="sxs-lookup"><span data-stu-id="7f628-455">**Tags**</span></span>

<span data-ttu-id="7f628-456">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="7f628-456">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="7f628-457">**Fecha:** **Fecha de inicio** y fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="7f628-457">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="7f628-458">**Detección**</span><span class="sxs-lookup"><span data-stu-id="7f628-458">**Detection**</span></span>
- <span data-ttu-id="7f628-459">**Protegido por**: **MDO** (Defender para Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="7f628-459">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="7f628-460">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="7f628-460">**Direction**</span></span>
- <span data-ttu-id="7f628-461">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="7f628-461">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="7f628-462">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-462">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="7f628-463">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="7f628-463">**Domain**</span></span>
- <span data-ttu-id="7f628-464">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="7f628-464">**Policy type**</span></span>
- <span data-ttu-id="7f628-465">**Nombre de directiva** (solo tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="7f628-465">**Policy name** (details table only)</span></span>
- <span data-ttu-id="7f628-466">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="7f628-466">**Recipients**</span></span>

<span data-ttu-id="7f628-467">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="7f628-467">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="7f628-468">Ver datos por malware de \> correo electrónico y desglose de gráficos por tecnología de detección</span><span class="sxs-lookup"><span data-stu-id="7f628-468">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Vista de tecnología de detección de malware en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="7f628-470">En la vista Ver  **datos por malware de \> correo** electrónico y desglose de gráficos por tecnología de detección, se muestra la siguiente información en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="7f628-470">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="7f628-471">**Detonación de archivos:** <sup>\*</sup> detección por Caja fuerte datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="7f628-471">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="7f628-472">**Reputación de detonación de archivos:** toda la reputación de archivos malintencionados generada por <sup>\*</sup> Defender para Office 365 detonaciones.</span><span class="sxs-lookup"><span data-stu-id="7f628-472">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="7f628-473">**Reputación de los archivos**</span><span class="sxs-lookup"><span data-stu-id="7f628-473">**File reputation**</span></span>
- <span data-ttu-id="7f628-474">**Motor antimalware: detección** <sup>\*</sup> de motores antimalware.</span><span class="sxs-lookup"><span data-stu-id="7f628-474">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="7f628-475">Bloque de tipo de archivo de directiva **antimalware:** se trata de mensajes de correo electrónico filtrados debido al tipo de archivo malintencionado identificado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="7f628-475">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="7f628-476">**Reputación malintencionada de URL**</span><span class="sxs-lookup"><span data-stu-id="7f628-476">**URL malicious reputation**</span></span>
- <span data-ttu-id="7f628-477">**Detonación de URL**</span><span class="sxs-lookup"><span data-stu-id="7f628-477">**URL detonation**</span></span>
- <span data-ttu-id="7f628-478">**Reputación de detonación de URL**</span><span class="sxs-lookup"><span data-stu-id="7f628-478">**URL detonation reputation**</span></span>
- <span data-ttu-id="7f628-479">**Campaña**</span><span class="sxs-lookup"><span data-stu-id="7f628-479">**Campaign**</span></span>

<span data-ttu-id="7f628-480">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7f628-480">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="7f628-481">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="7f628-481">**Date**</span></span>
- <span data-ttu-id="7f628-482">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="7f628-482">**Subject**</span></span>
- <span data-ttu-id="7f628-483">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="7f628-483">**Sender**</span></span>
- <span data-ttu-id="7f628-484">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="7f628-484">**Recipients**</span></span>
- <span data-ttu-id="7f628-485">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="7f628-485">**Detected by**</span></span>
- <span data-ttu-id="7f628-486">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="7f628-486">**Delivery Status**</span></span>
- <span data-ttu-id="7f628-487">**Origen de la transacción**</span><span class="sxs-lookup"><span data-stu-id="7f628-487">**Source of Compromise**</span></span>
- <span data-ttu-id="7f628-488">**Tags**</span><span class="sxs-lookup"><span data-stu-id="7f628-488">**Tags**</span></span>

<span data-ttu-id="7f628-489">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="7f628-489">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="7f628-490">**Fecha:** **Fecha de inicio** y fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="7f628-490">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="7f628-491">**Detección**</span><span class="sxs-lookup"><span data-stu-id="7f628-491">**Detection**</span></span>
- <span data-ttu-id="7f628-492">**Protegido por**: **MDO** (Defender para Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="7f628-492">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="7f628-493">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="7f628-493">**Direction**</span></span>
- <span data-ttu-id="7f628-494">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="7f628-494">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="7f628-495">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-495">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="7f628-496">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="7f628-496">**Domain**</span></span>
- <span data-ttu-id="7f628-497">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="7f628-497">**Policy type**</span></span>
- <span data-ttu-id="7f628-498">**Nombre de directiva** (solo tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="7f628-498">**Policy name** (details table only)</span></span>
- <span data-ttu-id="7f628-499">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="7f628-499">**Recipients**</span></span>

<span data-ttu-id="7f628-500">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="7f628-500">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="7f628-501">Desglose de gráficos por tipo de directiva y Ver datos por \> correo electrónico Phish o Ver datos por malware de correo \> electrónico</span><span class="sxs-lookup"><span data-stu-id="7f628-501">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Vista de tipo de directiva para correo electrónico de suplantación de identidad (phishing) o correo electrónico de malware en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="7f628-503">En las **vistas Desglose** de gráficos por tipo de directiva y Ver datos por correo electrónico **\> phish** o Ver datos por **\> correo** electrónico malintencionado, se muestra la siguiente información en los gráficos:</span><span class="sxs-lookup"><span data-stu-id="7f628-503">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="7f628-504">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="7f628-504">**Anti-malware**</span></span>
- <span data-ttu-id="7f628-505">**Caja fuerte Datos adjuntos**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f628-505">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="7f628-506">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="7f628-506">**Anti-phish**</span></span>
- <span data-ttu-id="7f628-507">**Contra correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="7f628-507">**Anti-spam**</span></span>
- <span data-ttu-id="7f628-508">**Regla de flujo de** correo (también conocida como regla de transporte)</span><span class="sxs-lookup"><span data-stu-id="7f628-508">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="7f628-509">**Otros**</span><span class="sxs-lookup"><span data-stu-id="7f628-509">**Others**</span></span>

<span data-ttu-id="7f628-510">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7f628-510">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="7f628-511">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="7f628-511">**Date**</span></span>
- <span data-ttu-id="7f628-512">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="7f628-512">**Subject**</span></span>
- <span data-ttu-id="7f628-513">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="7f628-513">**Sender**</span></span>
- <span data-ttu-id="7f628-514">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="7f628-514">**Recipients**</span></span>
- <span data-ttu-id="7f628-515">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="7f628-515">**Detected by**</span></span>
- <span data-ttu-id="7f628-516">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="7f628-516">**Delivery Status**</span></span>
- <span data-ttu-id="7f628-517">**Origen de la transacción**</span><span class="sxs-lookup"><span data-stu-id="7f628-517">**Source of Compromise**</span></span>
- <span data-ttu-id="7f628-518">**Tags**</span><span class="sxs-lookup"><span data-stu-id="7f628-518">**Tags**</span></span>

<span data-ttu-id="7f628-519">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="7f628-519">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="7f628-520">**Fecha:** **Fecha de inicio** y fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="7f628-520">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="7f628-521">**Detección**</span><span class="sxs-lookup"><span data-stu-id="7f628-521">**Detection**</span></span>
- <span data-ttu-id="7f628-522">**Protegido por**: **MDO** (Defender para Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="7f628-522">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="7f628-523">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="7f628-523">**Direction**</span></span>
- <span data-ttu-id="7f628-524">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="7f628-524">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="7f628-525">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-525">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="7f628-526">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="7f628-526">**Domain**</span></span>
- <span data-ttu-id="7f628-527">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="7f628-527">**Policy type**</span></span>
- <span data-ttu-id="7f628-528">**Nombre de directiva** (solo tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="7f628-528">**Policy name** (details table only)</span></span>
- <span data-ttu-id="7f628-529">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="7f628-529">**Recipients**</span></span>

<span data-ttu-id="7f628-530">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="7f628-530">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="7f628-531">Desglose del gráfico por estado de entrega y Ver datos por correo electrónico \> phish o ver datos por malware de correo \> electrónico</span><span class="sxs-lookup"><span data-stu-id="7f628-531">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Vista Estado de entrega para correo electrónico de suplantación de identidad (phishing) y correo electrónico de malware en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="7f628-533">En las **vistas Desglose** del gráfico por estado de entrega y Ver datos por correo electrónico **\> phish** o **Ver \>** datos por correo electrónico malintencionado, se muestra la siguiente información en los gráficos:</span><span class="sxs-lookup"><span data-stu-id="7f628-533">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="7f628-534">**Buzón hospedado: Bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="7f628-534">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="7f628-535">**Buzón hospedado: correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="7f628-535">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="7f628-536">**Buzón hospedado: carpeta personalizada**</span><span class="sxs-lookup"><span data-stu-id="7f628-536">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="7f628-537">**Buzón hospedado: elementos eliminados**</span><span class="sxs-lookup"><span data-stu-id="7f628-537">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="7f628-538">**Reenviado**</span><span class="sxs-lookup"><span data-stu-id="7f628-538">**Forwarded**</span></span>
- <span data-ttu-id="7f628-539">**Servidor local: entregado**</span><span class="sxs-lookup"><span data-stu-id="7f628-539">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="7f628-540">**Cuarentena**</span><span class="sxs-lookup"><span data-stu-id="7f628-540">**Quarantine**</span></span>
- <span data-ttu-id="7f628-541">**Error en la entrega**</span><span class="sxs-lookup"><span data-stu-id="7f628-541">**Delivery failed**</span></span>
- <span data-ttu-id="7f628-542">**Se ha descartado**</span><span class="sxs-lookup"><span data-stu-id="7f628-542">**Dropped**</span></span>

<span data-ttu-id="7f628-543">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7f628-543">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="7f628-544">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="7f628-544">**Date**</span></span>
- <span data-ttu-id="7f628-545">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="7f628-545">**Subject**</span></span>
- <span data-ttu-id="7f628-546">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="7f628-546">**Sender**</span></span>
- <span data-ttu-id="7f628-547">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="7f628-547">**Recipients**</span></span>
- <span data-ttu-id="7f628-548">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="7f628-548">**Detected by**</span></span>
- <span data-ttu-id="7f628-549">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="7f628-549">**Delivery Status**</span></span>
- <span data-ttu-id="7f628-550">**Origen de la transacción**</span><span class="sxs-lookup"><span data-stu-id="7f628-550">**Source of Compromise**</span></span>
- <span data-ttu-id="7f628-551">**Tags**</span><span class="sxs-lookup"><span data-stu-id="7f628-551">**Tags**</span></span>

<span data-ttu-id="7f628-552">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="7f628-552">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="7f628-553">**Fecha:** **Fecha de inicio** y fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="7f628-553">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="7f628-554">**Detección**</span><span class="sxs-lookup"><span data-stu-id="7f628-554">**Detection**</span></span>
- <span data-ttu-id="7f628-555">**Protegido por**: **MDO** (Defender para Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="7f628-555">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="7f628-556">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="7f628-556">**Direction**</span></span>
- <span data-ttu-id="7f628-557">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="7f628-557">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="7f628-558">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-558">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="7f628-559">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="7f628-559">**Domain**</span></span>
- <span data-ttu-id="7f628-560">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="7f628-560">**Policy type**</span></span>
- <span data-ttu-id="7f628-561">**Nombre de directiva** (solo tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="7f628-561">**Policy name** (details table only)</span></span>
- <span data-ttu-id="7f628-562">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="7f628-562">**Recipients**</span></span>

<span data-ttu-id="7f628-563">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="7f628-563">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="7f628-564">Ver datos por malware \> de contenido</span><span class="sxs-lookup"><span data-stu-id="7f628-564">View data by Content \> Malware</span></span>

![Vista de malware de contenido en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="7f628-566">En la **vista Ver datos por \> malware** de contenido, la siguiente información se muestra en el gráfico de Microsoft Defender para Office 365 organizaciones:</span><span class="sxs-lookup"><span data-stu-id="7f628-566">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="7f628-567">**Motor antimalware:** archivos malintencionados detectados en Sharepoint, OneDrive y Microsoft Teams por la detección de virus integrada en [Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-567">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="7f628-568">**Detonación de archivos:** archivos malintencionados detectados por Caja fuerte datos adjuntos para [SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-568">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="7f628-569">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7f628-569">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="7f628-570">**Fecha:** **Fecha de inicio** y fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="7f628-570">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="7f628-571">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="7f628-571">**Location**</span></span>
- <span data-ttu-id="7f628-572">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="7f628-572">**Detected by**</span></span>
- <span data-ttu-id="7f628-573">**Nombre de malware**</span><span class="sxs-lookup"><span data-stu-id="7f628-573">**Malware name**</span></span>

<span data-ttu-id="7f628-574">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="7f628-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="7f628-575">**Fecha:** **Fecha de inicio** y fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="7f628-575">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="7f628-576">**Detección:** **motor antimalware o** **detonación de archivos**</span><span class="sxs-lookup"><span data-stu-id="7f628-576">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="7f628-577">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="7f628-577">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="7f628-578">Ver datos por invalidación del sistema</span><span class="sxs-lookup"><span data-stu-id="7f628-578">View data by System override</span></span>

![Vista De invalidación de mensajes en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="7f628-580">En la **vista Ver datos por invalidación** del sistema, se muestra la siguiente información de motivo de invalidación en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="7f628-580">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="7f628-581">**Omitir localmente**</span><span class="sxs-lookup"><span data-stu-id="7f628-581">**On-premises skip**</span></span>
- <span data-ttu-id="7f628-582">**Ip allow**</span><span class="sxs-lookup"><span data-stu-id="7f628-582">**IP allow**</span></span>
- <span data-ttu-id="7f628-583">**Exchange de transporte de correo** (regla de flujo de correo)</span><span class="sxs-lookup"><span data-stu-id="7f628-583">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="7f628-584">**Remitentes permitidos por la organización**</span><span class="sxs-lookup"><span data-stu-id="7f628-584">**Organization allowed senders**</span></span>
- <span data-ttu-id="7f628-585">**Dominios permitidos por la organización**</span><span class="sxs-lookup"><span data-stu-id="7f628-585">**Organization allowed domains**</span></span>
- <span data-ttu-id="7f628-586">**ZAP no habilitado**</span><span class="sxs-lookup"><span data-stu-id="7f628-586">**ZAP not enabled**</span></span>
- <span data-ttu-id="7f628-587">**Carpeta de correo no deseado no habilitada**</span><span class="sxs-lookup"><span data-stu-id="7f628-587">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="7f628-588">**Remitente Caja fuerte usuario**</span><span class="sxs-lookup"><span data-stu-id="7f628-588">**User Safe Sender**</span></span>
- <span data-ttu-id="7f628-589">**Dominio Caja fuerte usuario**</span><span class="sxs-lookup"><span data-stu-id="7f628-589">**User Safe Domain**</span></span>

<span data-ttu-id="7f628-590">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7f628-590">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="7f628-591">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="7f628-591">**Date**</span></span>
- <span data-ttu-id="7f628-592">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="7f628-592">**Subject**</span></span>
- <span data-ttu-id="7f628-593">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="7f628-593">**Sender**</span></span>
- <span data-ttu-id="7f628-594">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="7f628-594">**Recipients**</span></span>
- <span data-ttu-id="7f628-595">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="7f628-595">**Detected by**</span></span>
- <span data-ttu-id="7f628-596">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="7f628-596">**Delivery Status**</span></span>
- <span data-ttu-id="7f628-597">**Origen de la transacción**</span><span class="sxs-lookup"><span data-stu-id="7f628-597">**Source of Compromise**</span></span>
- <span data-ttu-id="7f628-598">**Tags**</span><span class="sxs-lookup"><span data-stu-id="7f628-598">**Tags**</span></span>

<span data-ttu-id="7f628-599">Si hace clic **en Filtrar,** estarán disponibles los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="7f628-599">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="7f628-600">**Fecha:** **Fecha de inicio** y fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="7f628-600">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="7f628-601">**Detección**</span><span class="sxs-lookup"><span data-stu-id="7f628-601">**Detection**</span></span>
- <span data-ttu-id="7f628-602">**Protegido por**: **MDO** (Defender para Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="7f628-602">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="7f628-603">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="7f628-603">**Direction**</span></span>
- <span data-ttu-id="7f628-604">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="7f628-604">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="7f628-605">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-605">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="7f628-606">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="7f628-606">**Domain**</span></span>
- <span data-ttu-id="7f628-607">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="7f628-607">**Policy type**</span></span>
- <span data-ttu-id="7f628-608">**Nombre de directiva** (solo tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="7f628-608">**Policy name** (details table only)</span></span>
- <span data-ttu-id="7f628-609">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="7f628-609">**Recipients**</span></span>

<span data-ttu-id="7f628-610">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="7f628-610">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="7f628-611"><sup>\*</sup>Solo defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7f628-611"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="7f628-612">Informe de malware superior</span><span class="sxs-lookup"><span data-stu-id="7f628-612">Top malware report</span></span>

<span data-ttu-id="7f628-613">El **informe de malware** top muestra los distintos tipos de malware detectados por la protección [antimalware en EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-613">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="7f628-614">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="7f628-614">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="7f628-615">En **Malware superior,** haga clic **en Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="7f628-615">On **Top malware**, click **View details**.</span></span> <span data-ttu-id="7f628-616">Para ir directamente al informe, abra <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="7f628-616">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Widget de malware superior en la página Informes de colaboración & correo electrónico](../../media/top-malware-report-widget.png)

<span data-ttu-id="7f628-618">Al pasar el mouse sobre una cuña en el gráfico circular, puede ver el nombre de un tipo de malware y cuántos mensajes se detectaron como que tienen ese malware.</span><span class="sxs-lookup"><span data-stu-id="7f628-618">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="7f628-619">Después de hacer clic **en Ver detalles,** se muestra una versión más grande del gráfico circular en la página del informe. La tabla de detalles debajo del gráfico muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7f628-619">After you click **View details**, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="7f628-620">**Malware superior**</span><span class="sxs-lookup"><span data-stu-id="7f628-620">**Top malware**</span></span>
- <span data-ttu-id="7f628-621">**Count**</span><span class="sxs-lookup"><span data-stu-id="7f628-621">**Count**</span></span>

<span data-ttu-id="7f628-622">Si hace clic **en Filtrar**, puede especificar un intervalo de fechas con Fecha de **inicio y** Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="7f628-622">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Vista de informe de malware superior](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="7f628-624">Informe de protección contra amenazas de url</span><span class="sxs-lookup"><span data-stu-id="7f628-624">URL threat protection report</span></span>

<span data-ttu-id="7f628-625">El **informe de protección contra amenazas de url** está disponible en Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f628-625">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="7f628-626">Para obtener más información, vea [Informe de protección contra amenazas de url](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="7f628-626">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="7f628-627">Informe de mensajes notificados por el usuario</span><span class="sxs-lookup"><span data-stu-id="7f628-627">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f628-628">Para que el informe **de** mensajes notificados por el usuario funcione correctamente,  el registro de auditoría debe estar activado para el Microsoft 365 usuario.</span><span class="sxs-lookup"><span data-stu-id="7f628-628">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="7f628-629">Esto lo suele hacer alguien que tenga el rol Registros de auditoría asignado en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7f628-629">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="7f628-630">Para obtener más información, vea Activar Microsoft 365 o desactivar la búsqueda del [registro de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="7f628-630">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="7f628-631">El  informe de mensajes notificados por el usuario muestra información acerca de los mensajes de correo electrónico que los usuarios han notificado como correo no deseado, intentos de suplantación de identidad o correo bueno mediante el complemento Report [Message o](enable-the-report-message-add-in.md) el complemento [Report Phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-631">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="7f628-632">Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** de correo electrónico & colaboración Correo electrónico & informes de colaboración \>  \> **Mensajes** \> **notificados por el usuario.**</span><span class="sxs-lookup"><span data-stu-id="7f628-632">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span> <span data-ttu-id="7f628-633">En **Mensajes notificados por el usuario,** haga clic **en Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="7f628-633">On **User reported messages**, click **View details**.</span></span> <span data-ttu-id="7f628-634">Para ir directamente al informe, abra <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="7f628-634">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="7f628-635">Para ir a [envíos de administrador en el portal de Microsoft 365 Defender,](admin-submission.md)haga clic **en Ir a Envíos**.</span><span class="sxs-lookup"><span data-stu-id="7f628-635">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget Mensajes notificados por el usuario en la página Informes de & de colaboración](../../media/user-reported-messages-widget.png)

<span data-ttu-id="7f628-637">Después de **hacer** clic en Ver detalles, puede filtrar  tanto el gráfico como la tabla de detalles haciendo clic en Filtrar y seleccionando uno o varios de los siguientes valores en el menú desplegable que aparece:</span><span class="sxs-lookup"><span data-stu-id="7f628-637">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="7f628-638">**Fecha notificada:** **Hora de inicio** y hora de **finalización**</span><span class="sxs-lookup"><span data-stu-id="7f628-638">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="7f628-639">**Informe realizado por**</span><span class="sxs-lookup"><span data-stu-id="7f628-639">**Reported by**</span></span>
- <span data-ttu-id="7f628-640">**Asunto del correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="7f628-640">**Email subject**</span></span>
- <span data-ttu-id="7f628-641">**Id. de mensaje notificado**</span><span class="sxs-lookup"><span data-stu-id="7f628-641">**Message reported ID**</span></span>
- <span data-ttu-id="7f628-642">**Id. de mensaje de red**</span><span class="sxs-lookup"><span data-stu-id="7f628-642">**Network Message ID**</span></span>
- <span data-ttu-id="7f628-643">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7f628-643">**Sender**</span></span>
- <span data-ttu-id="7f628-644">**Motivo notificado**</span><span class="sxs-lookup"><span data-stu-id="7f628-644">**Reported reason**</span></span>
  - <span data-ttu-id="7f628-645">**No es correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="7f628-645">**Not junk**</span></span>
  - <span data-ttu-id="7f628-646">**Suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="7f628-646">**Phish**</span></span>
  - <span data-ttu-id="7f628-647">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="7f628-647">**Spam**</span></span>
- <span data-ttu-id="7f628-648">**Simulación de phish:** **Sí** o **No**</span><span class="sxs-lookup"><span data-stu-id="7f628-648">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="7f628-649">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="7f628-649">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="7f628-650">Para agrupar las entradas, haga clic **en Agrupar** y seleccione uno de los siguientes valores de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="7f628-650">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="7f628-651">**Ninguna**</span><span class="sxs-lookup"><span data-stu-id="7f628-651">**None**</span></span>
- <span data-ttu-id="7f628-652">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="7f628-652">**Reason**</span></span>
- <span data-ttu-id="7f628-653">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7f628-653">**Sender**</span></span>
- <span data-ttu-id="7f628-654">**Informe realizado por**</span><span class="sxs-lookup"><span data-stu-id="7f628-654">**Reported by**</span></span>
- <span data-ttu-id="7f628-655">**Volver a examinar el resultado**</span><span class="sxs-lookup"><span data-stu-id="7f628-655">**Rescan result**</span></span>
- <span data-ttu-id="7f628-656">**Simulación de phishing**</span><span class="sxs-lookup"><span data-stu-id="7f628-656">**Phish simulation**</span></span>

![Informe de mensajes notificados por el usuario](../../media/user-reported-messages-report.png)

<span data-ttu-id="7f628-658">En la tabla debajo del gráfico, puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="7f628-658">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="7f628-659">**Asunto del correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="7f628-659">**Email subject**</span></span>
- <span data-ttu-id="7f628-660">**Informe realizado por**</span><span class="sxs-lookup"><span data-stu-id="7f628-660">**Reported by**</span></span>
- <span data-ttu-id="7f628-661">**Fecha notificada**</span><span class="sxs-lookup"><span data-stu-id="7f628-661">**Date reported**</span></span>
- <span data-ttu-id="7f628-662">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7f628-662">**Sender**</span></span>
- <span data-ttu-id="7f628-663">**Motivo notificado**</span><span class="sxs-lookup"><span data-stu-id="7f628-663">**Reported reason**</span></span>
- <span data-ttu-id="7f628-664">**Volver a examinar el resultado**</span><span class="sxs-lookup"><span data-stu-id="7f628-664">**Rescan result**</span></span>
- <span data-ttu-id="7f628-665">**Tags**</span><span class="sxs-lookup"><span data-stu-id="7f628-665">**Tags**</span></span>

<span data-ttu-id="7f628-666">Para enviar un mensaje a Microsoft para su análisis, seleccione la entrada de mensaje de la tabla, haga clic en Enviar a **Microsoft** para su análisis y, a continuación, seleccione uno de los siguientes valores de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="7f628-666">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="7f628-667">**Informe limpio**</span><span class="sxs-lookup"><span data-stu-id="7f628-667">**Report clean**</span></span>
- <span data-ttu-id="7f628-668">**Report phishing**</span><span class="sxs-lookup"><span data-stu-id="7f628-668">**Report phishing**</span></span>
- <span data-ttu-id="7f628-669">**Informar de malware**</span><span class="sxs-lookup"><span data-stu-id="7f628-669">**Report malware**</span></span>
- <span data-ttu-id="7f628-670">**Notificar correo no deseado**'</span><span class="sxs-lookup"><span data-stu-id="7f628-670">**Report spam**'</span></span>
- <span data-ttu-id="7f628-671">**Investigación de desencadenador** (Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="7f628-671">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="7f628-672">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="7f628-672">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="7f628-673">Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el portal de Microsoft 365 Defender web:</span><span class="sxs-lookup"><span data-stu-id="7f628-673">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="7f628-674">**Administración de organizaciones**</span><span class="sxs-lookup"><span data-stu-id="7f628-674">**Organization Management**</span></span>
- <span data-ttu-id="7f628-675">**Administrador de seguridad**</span><span class="sxs-lookup"><span data-stu-id="7f628-675">**Security Administrator**</span></span>
- <span data-ttu-id="7f628-676">**Lector de seguridad**</span><span class="sxs-lookup"><span data-stu-id="7f628-676">**Security Reader**</span></span>
- <span data-ttu-id="7f628-677">**Lector global**</span><span class="sxs-lookup"><span data-stu-id="7f628-677">**Global Reader**</span></span>

<span data-ttu-id="7f628-678">Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-678">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="7f628-679">**Nota:** Agregar usuarios al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f628-679">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="7f628-680">Para más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-680">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="7f628-681">¿Qué ocurre si los informes no muestran datos?</span><span class="sxs-lookup"><span data-stu-id="7f628-681">What if the reports aren't showing data?</span></span>

<span data-ttu-id="7f628-682">Si no ve datos en los informes, compruebe que las directivas están configuradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="7f628-682">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="7f628-683">Para obtener más información, vea [Protect against threats](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-683">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7f628-684">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7f628-684">Related topics</span></span>

[<span data-ttu-id="7f628-685">Protección contra correo no deseado y antimalware en EOP</span><span class="sxs-lookup"><span data-stu-id="7f628-685">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="7f628-686">Informes e información inteligentes en el portal Microsoft 365 Defender web</span><span class="sxs-lookup"><span data-stu-id="7f628-686">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="7f628-687">Ver informes de flujo de correo en el portal Microsoft 365 Defender correo</span><span class="sxs-lookup"><span data-stu-id="7f628-687">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="7f628-688">Ver informes de Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7f628-688">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
