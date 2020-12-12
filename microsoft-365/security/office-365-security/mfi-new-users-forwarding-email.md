---
title: Información de nuevos usuarios que reenvían correo electrónico
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden aprender a usar los nuevos usuarios que reenvían el conocimiento del correo electrónico en el centro de seguridad & cumplimiento para investigar Cuándo los usuarios de la organización reenvían mensajes a nuevos dominios.
ms.openlocfilehash: cf1852169279e19ac00e5e29dd1c26e155936039
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660022"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="94b7d-103">Nuevos usuarios que reenvían el conocimiento del correo electrónico en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="94b7d-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="94b7d-104">Es sospechoso cuando las nuevas cuentas de usuario de la organización inician repentinamente el reenvío de mensajes de correo electrónico a dominios externos.</span><span class="sxs-lookup"><span data-stu-id="94b7d-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="94b7d-105">Los **nuevos dominios que se reenvían** el conocimiento de correo electrónico del [centro de seguridad & cumplimiento](https://protection.office.com) le notifican cuando los usuarios recién creados en la organización reenvían mensajes a dominios externos.</span><span class="sxs-lookup"><span data-stu-id="94b7d-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="94b7d-106">Esta condición podría indicar que se usaron cuentas de administrador en peligro para crear los nuevos usuarios.</span><span class="sxs-lookup"><span data-stu-id="94b7d-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="94b7d-107">Si sospecha que las cuentas se han puesto en peligro, consulte [responder a una cuenta de correo electrónico en peligro](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="94b7d-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="94b7d-108">Esta información sólo aparece cuando se detecta el problema y aparece en la página de [reenvío del informe](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="94b7d-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Información de nuevos usuarios que reenvían correo electrónico](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="94b7d-110">Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al [Informe de modificaciones de reenvío](#forwarding-modifications-report) tal y como se describe más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="94b7d-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Control flotante de detalles que aparece después de hacer clic en los nuevos usuarios Reenviar información sobre el correo electrónico](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="94b7d-112">También puede obtener acceso a esta página de detalles si selecciona la información después de hacer clic en **ver todo** en el área de **recomendaciones &** información sobre ( \> **Panel** de informes o <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="94b7d-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="94b7d-113">Puede hacer clic en el vínculo **Ver informe asociado con conocimiento** para ir al **Informe de modificaciones de reenvío** , como se describe en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="94b7d-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="94b7d-114">Reenvío del informe de modificaciones</span><span class="sxs-lookup"><span data-stu-id="94b7d-114">Forwarding modifications report</span></span>

<span data-ttu-id="94b7d-115">El **Informe de modificaciones de reenvío** muestra detalles sobre los mensajes que se reenvían automáticamente a los remitentes de la organización:</span><span class="sxs-lookup"><span data-stu-id="94b7d-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="94b7d-116">Cuentas recién creadas que reenvían mensajes a dominios externos.</span><span class="sxs-lookup"><span data-stu-id="94b7d-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="94b7d-117">Cuentas que reenvían mensajes a dominios externos que nunca han sido reenviados por otros remitentes de la organización.</span><span class="sxs-lookup"><span data-stu-id="94b7d-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="94b7d-118">Estos tipos de mensajes reenviados pueden suponer un riesgo de seguridad o de cumplimiento, y pueden indicar cuentas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="94b7d-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="94b7d-119">El informe contiene datos de hasta 90 días.</span><span class="sxs-lookup"><span data-stu-id="94b7d-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="94b7d-120">De forma predeterminada, el informe muestra los datos de los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="94b7d-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="94b7d-121">Este informe no está directamente disponible en el [Panel de flujo de correo](mail-flow-insights-v2.md) ni en el panel de [informes](view-mail-flow-reports.md).</span><span class="sxs-lookup"><span data-stu-id="94b7d-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="94b7d-122">Además de hacer clic en el vínculo **vea el informe asociado con el conocimiento** en el **nuevo usuario Reenviar información sobre el correo electrónico de reenvío** , obtenga acceso al informe de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="94b7d-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="94b7d-123">Haga clic en el vínculo **reenviar notificaciones del informe** en los detalles de los [nuevos dominios que se reenviarán el conocimiento de correo electrónico](mfi-new-domains-being-forwarded-email.md).</span><span class="sxs-lookup"><span data-stu-id="94b7d-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="94b7d-124">Abrir <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="94b7d-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="94b7d-125">Vista informes para el informe de modificaciones de reenvío</span><span class="sxs-lookup"><span data-stu-id="94b7d-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="94b7d-126">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="94b7d-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="94b7d-127">**Mostrar datos para: nuevos usuarios de reenvío**:</span><span class="sxs-lookup"><span data-stu-id="94b7d-127">**Show data for: New forwarding users**:</span></span>

  ![Vista de nuevos usuarios de reenvío en el informe de modificaciones de reenvío](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="94b7d-129">**Mostrar datos para: nuevos dominios de reenvío**:</span><span class="sxs-lookup"><span data-stu-id="94b7d-129">**Show data for: New forwarding domains**:</span></span>

  ![Vista de nuevos dominios reenviados en el informe de modificaciones de reenvío](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="94b7d-131">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="94b7d-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="94b7d-132">Vista de tabla de detalles para el informe de modificaciones de reenvío</span><span class="sxs-lookup"><span data-stu-id="94b7d-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="94b7d-133">Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="94b7d-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="94b7d-134">**Mostrar datos para: nuevos usuarios de reenvío**:</span><span class="sxs-lookup"><span data-stu-id="94b7d-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="94b7d-135">**Name**: la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="94b7d-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="94b7d-136">**Tipo de reenvío**</span><span class="sxs-lookup"><span data-stu-id="94b7d-136">**Forwarding type**</span></span>
  - <span data-ttu-id="94b7d-137">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="94b7d-137">**Recipient address**</span></span>
  - <span data-ttu-id="94b7d-138">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="94b7d-138">**Details**</span></span>
  - <span data-ttu-id="94b7d-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="94b7d-139">**Count**</span></span>
  - <span data-ttu-id="94b7d-140">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="94b7d-140">**First forward date**</span></span>

- <span data-ttu-id="94b7d-141">**Mostrar datos para: nuevos dominios de reenvío**:</span><span class="sxs-lookup"><span data-stu-id="94b7d-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="94b7d-142">**Name**: el dominio de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="94b7d-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="94b7d-143">**Tipo de reenvío**</span><span class="sxs-lookup"><span data-stu-id="94b7d-143">**Forwarding type**</span></span>
  - <span data-ttu-id="94b7d-144">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="94b7d-144">**Recipient address**</span></span>
  - <span data-ttu-id="94b7d-145">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="94b7d-145">**Details**</span></span>
  - <span data-ttu-id="94b7d-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="94b7d-146">**Count**</span></span>
  - <span data-ttu-id="94b7d-147">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="94b7d-147">**First forward date**</span></span>

<span data-ttu-id="94b7d-148">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="94b7d-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="94b7d-149">Si selecciona una fila de la tabla, aparece un flotante de **detalles** con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="94b7d-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="94b7d-150">**Name**: esta es la dirección de correo electrónico del remitente (de **Mostrar datos para: nuevos usuarios de reenvío** ) o el dominio de correo electrónico del remitente (de la vista **Mostrar datos para: nuevos dominios de reenvío** ).</span><span class="sxs-lookup"><span data-stu-id="94b7d-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="94b7d-151">**Tipo de reenvío**</span><span class="sxs-lookup"><span data-stu-id="94b7d-151">**Forwarding type**</span></span>
- <span data-ttu-id="94b7d-152">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="94b7d-152">**Recipient**</span></span>
- <span data-ttu-id="94b7d-153">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="94b7d-153">**Details**</span></span>
- <span data-ttu-id="94b7d-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="94b7d-154">**Count**</span></span>
- <span data-ttu-id="94b7d-155">**Fecha de comienzo**</span><span class="sxs-lookup"><span data-stu-id="94b7d-155">**Start date**</span></span>
- <span data-ttu-id="94b7d-156">**Recomendación**: desde aquí, puede hacer clic en el vínculo para administrar el usuario en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94b7d-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Control flotante de la tabla detalles de la vista nuevos usuarios de reenvío en el informe de reenvío de modificaciones](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="94b7d-158">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="94b7d-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="94b7d-159">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="94b7d-159">Related topics</span></span>

<span data-ttu-id="94b7d-160">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="94b7d-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
