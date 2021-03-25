---
title: Información de nuevos usuarios que reenvían correo electrónico
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden aprender a usar la información sobre nuevos usuarios que reenvía correo electrónico en el Centro de seguridad & cumplimiento para investigar cuándo los usuarios de su organización reenvía mensajes a nuevos dominios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207242"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="89d8a-103">Nuevos usuarios reenviar información de correo electrónico en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="89d8a-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="89d8a-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="89d8a-104">**Applies to**</span></span>
- [<span data-ttu-id="89d8a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="89d8a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="89d8a-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="89d8a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="89d8a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89d8a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="89d8a-108">Es sospechoso cuando las nuevas cuentas de usuario de la organización comienzan de repente a reenviar mensajes de correo electrónico a dominios externos.</span><span class="sxs-lookup"><span data-stu-id="89d8a-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="89d8a-109">La **información sobre nuevos** dominios que se reenvía de correo electrónico en el Centro de seguridad y cumplimiento de [&](https://protection.office.com) le notifica cuándo los usuarios recién creados de su organización reenvía mensajes a dominios externos.</span><span class="sxs-lookup"><span data-stu-id="89d8a-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="89d8a-110">Esta condición podría indicar que se usaron cuentas de administrador comprometidas para crear los nuevos usuarios.</span><span class="sxs-lookup"><span data-stu-id="89d8a-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="89d8a-111">Si sospecha que las cuentas se han visto comprometidas, consulte [Responder a una cuenta de correo electrónico comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="89d8a-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="89d8a-112">Esta información solo aparece cuando se detecta el problema y aparece en la página [Informe de reenvío.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="89d8a-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Información de nuevos usuarios que reenvían correo electrónico](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="89d8a-114">Al hacer clic en el widget, aparece un control flotante donde puede encontrar más [](#forwarding-modifications-report) detalles sobre los mensajes reenviados, incluido un vínculo al informe de modificaciones de reenvío, tal como se describe más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="89d8a-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![El menú desplegable de detalles que aparece después de hacer clic en la información sobre el reenvío de correo electrónico de nuevos usuarios](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="89d8a-116">También puede acceder a esta página de detalles  al seleccionar la información después de hacer clic en Ver todo en el área Información **principal & recomendaciones** en (**Panel** de informes \>  o <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="89d8a-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="89d8a-117">Puede hacer clic en el **vínculo Ver informe asociado a insight** para ir al informe de modificaciones **de** reenvío, tal como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="89d8a-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="89d8a-118">Informe de modificaciones de reenvío</span><span class="sxs-lookup"><span data-stu-id="89d8a-118">Forwarding modifications report</span></span>

<span data-ttu-id="89d8a-119">El **informe de modificaciones de reenvío** muestra detalles sobre los mensajes que se reenvía automáticamente de remitentes de la organización:</span><span class="sxs-lookup"><span data-stu-id="89d8a-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="89d8a-120">Cuentas recién creadas que reenvía mensajes a dominios externos.</span><span class="sxs-lookup"><span data-stu-id="89d8a-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="89d8a-121">Cuentas que reenvía mensajes a dominios externos que nunca han sido reenviados por otros remitentes de la organización.</span><span class="sxs-lookup"><span data-stu-id="89d8a-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="89d8a-122">Estos tipos de mensajes reenviados pueden suponer un riesgo de seguridad o cumplimiento, y pueden indicar cuentas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="89d8a-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="89d8a-123">El informe contiene datos de hasta 90 días.</span><span class="sxs-lookup"><span data-stu-id="89d8a-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="89d8a-124">De forma predeterminada, el informe muestra los datos de los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="89d8a-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="89d8a-125">Este informe no está disponible directamente en el panel flujo de [correo](mail-flow-insights-v2.md) ni en el [panel Informes.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="89d8a-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="89d8a-126">Además de hacer clic en el vínculo **Ver informe asociado a insight** en el vínculo **Nuevos** usuarios que reenvía la información de correo electrónico, puede obtener acceso al informe mediante:</span><span class="sxs-lookup"><span data-stu-id="89d8a-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="89d8a-127">Haga clic **en el vínculo Informe de notificaciones de reenvío** en los detalles de los nuevos dominios que se [reenvía la](mfi-new-domains-being-forwarded-email.md)información de correo electrónico .</span><span class="sxs-lookup"><span data-stu-id="89d8a-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="89d8a-128">Abrir <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="89d8a-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="89d8a-129">Vista Informe para el informe de modificaciones de reenvío</span><span class="sxs-lookup"><span data-stu-id="89d8a-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="89d8a-130">Los gráficos siguientes están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="89d8a-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="89d8a-131">**Mostrar datos para: Nuevos usuarios de reenvío:**</span><span class="sxs-lookup"><span data-stu-id="89d8a-131">**Show data for: New forwarding users**:</span></span>

  ![Vista Nuevos usuarios de reenvío en el informe de modificaciones de reenvío](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="89d8a-133">**Mostrar datos para: Nuevos dominios de reenvío:**</span><span class="sxs-lookup"><span data-stu-id="89d8a-133">**Show data for: New forwarding domains**:</span></span>

  ![Vista Nuevos dominios reenviados en el informe de modificaciones de reenvío](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="89d8a-135">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con Fecha **de inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="89d8a-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="89d8a-136">Vista de tabla Detalles para el informe de modificaciones de reenvío</span><span class="sxs-lookup"><span data-stu-id="89d8a-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="89d8a-137">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba mirando:</span><span class="sxs-lookup"><span data-stu-id="89d8a-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="89d8a-138">**Mostrar datos para: Nuevos usuarios de reenvío:**</span><span class="sxs-lookup"><span data-stu-id="89d8a-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="89d8a-139">**Nombre:** la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="89d8a-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="89d8a-140">**Tipo de reenvío**</span><span class="sxs-lookup"><span data-stu-id="89d8a-140">**Forwarding type**</span></span>
  - <span data-ttu-id="89d8a-141">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="89d8a-141">**Recipient address**</span></span>
  - <span data-ttu-id="89d8a-142">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="89d8a-142">**Details**</span></span>
  - <span data-ttu-id="89d8a-143">**Count**</span><span class="sxs-lookup"><span data-stu-id="89d8a-143">**Count**</span></span>
  - <span data-ttu-id="89d8a-144">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="89d8a-144">**First forward date**</span></span>

- <span data-ttu-id="89d8a-145">**Mostrar datos para: Nuevos dominios de reenvío:**</span><span class="sxs-lookup"><span data-stu-id="89d8a-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="89d8a-146">**Nombre:** el dominio de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="89d8a-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="89d8a-147">**Tipo de reenvío**</span><span class="sxs-lookup"><span data-stu-id="89d8a-147">**Forwarding type**</span></span>
  - <span data-ttu-id="89d8a-148">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="89d8a-148">**Recipient address**</span></span>
  - <span data-ttu-id="89d8a-149">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="89d8a-149">**Details**</span></span>
  - <span data-ttu-id="89d8a-150">**Count**</span><span class="sxs-lookup"><span data-stu-id="89d8a-150">**Count**</span></span>
  - <span data-ttu-id="89d8a-151">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="89d8a-151">**First forward date**</span></span>

<span data-ttu-id="89d8a-152">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="89d8a-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="89d8a-153">Si selecciona una fila de la tabla, **aparecerá** un menú desplegable Detalles con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="89d8a-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="89d8a-154">**Nombre:** esta es la dirección de correo electrónico del remitente (desde Mostrar datos **para: Vista** Nuevos usuarios de reenvío) o el dominio de correo electrónico del remitente (desde Mostrar datos **para:** Vista Nuevos dominios de reenvío).</span><span class="sxs-lookup"><span data-stu-id="89d8a-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="89d8a-155">**Tipo de reenvío**</span><span class="sxs-lookup"><span data-stu-id="89d8a-155">**Forwarding type**</span></span>
- <span data-ttu-id="89d8a-156">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="89d8a-156">**Recipient**</span></span>
- <span data-ttu-id="89d8a-157">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="89d8a-157">**Details**</span></span>
- <span data-ttu-id="89d8a-158">**Count**</span><span class="sxs-lookup"><span data-stu-id="89d8a-158">**Count**</span></span>
- <span data-ttu-id="89d8a-159">**Fecha de comienzo**</span><span class="sxs-lookup"><span data-stu-id="89d8a-159">**Start date**</span></span>
- <span data-ttu-id="89d8a-160">**Recomendación:** Desde aquí, puede hacer clic en el vínculo para administrar el usuario en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="89d8a-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Los detalles se desván de la tabla de detalles de la vista Nuevos usuarios de reenvío en el informe Modificaciones de reenvío](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="89d8a-162">Para volver a la vista informes, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="89d8a-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="89d8a-163">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="89d8a-163">Related topics</span></span>

<span data-ttu-id="89d8a-164">Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="89d8a-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
