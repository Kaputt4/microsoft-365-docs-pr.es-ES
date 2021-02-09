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
description: Los administradores pueden aprender a usar los nuevos usuarios que reenvía información de correo electrónico en el Centro de seguridad & Cumplimiento para investigar cuándo los usuarios de su organización reenvía mensajes a nuevos dominios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7b86d726979991a55e7d4e43bf3581a4a664ee4f
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150260"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="bd702-103">Nuevos usuarios que reenvía información de correo electrónico en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bd702-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bd702-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="bd702-104">**Applies to**</span></span>
- [<span data-ttu-id="bd702-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bd702-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="bd702-106">Microsoft Defender para Office 365 plan 1 y plan 2</span><span class="sxs-lookup"><span data-stu-id="bd702-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="bd702-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd702-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="bd702-108">Es sospechoso cuando las nuevas cuentas de usuario de su organización comienzan de pronto a reenviar mensajes de correo electrónico a dominios externos.</span><span class="sxs-lookup"><span data-stu-id="bd702-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="bd702-109">La **información sobre nuevos** dominios que se reenvía de correo electrónico en el Centro de seguridad y cumplimiento de [&](https://protection.office.com) le notifica cuándo los usuarios recién creados de su organización están reenviando mensajes a dominios externos.</span><span class="sxs-lookup"><span data-stu-id="bd702-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="bd702-110">Esta condición podría indicar que se usaron cuentas de administrador comprometidas para crear los nuevos usuarios.</span><span class="sxs-lookup"><span data-stu-id="bd702-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="bd702-111">Si sospecha que las cuentas se han visto comprometidas, consulte [Responder a una cuenta de correo electrónico en peligro.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="bd702-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="bd702-112">Esta información solo aparece cuando se detecta el problema y aparece en la [página del informe de reenvío.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="bd702-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Información de nuevos usuarios que reenvían correo electrónico](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="bd702-114">Al hacer clic en el widget, aparece un control flotante donde puede encontrar más [](#forwarding-modifications-report) detalles sobre los mensajes reenviados, incluido un vínculo al informe de modificaciones de reenvío, tal como se describe más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="bd702-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Menú desplegable de detalles que aparece después de hacer clic en la información de reenvío de correo electrónico de nuevos usuarios](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="bd702-116">También puede acceder a esta página de detalles  cuando seleccione la información después de hacer clic en Ver todo en el área de información **superior &** recomendaciones **(** Panel de informes \>  o <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="bd702-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="bd702-117">Puede hacer clic en el **vínculo Ver informe asociado con** información para ir al informe de modificaciones **de** reenvío, tal como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="bd702-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="bd702-118">Informe de modificaciones de reenvío</span><span class="sxs-lookup"><span data-stu-id="bd702-118">Forwarding modifications report</span></span>

<span data-ttu-id="bd702-119">El **informe de modificaciones de reenvío** muestra detalles sobre los mensajes que se reenván automáticamente de los remitentes de su organización:</span><span class="sxs-lookup"><span data-stu-id="bd702-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="bd702-120">Cuentas recién creadas que reenvía mensajes a dominios externos.</span><span class="sxs-lookup"><span data-stu-id="bd702-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="bd702-121">Cuentas que reenvía mensajes a dominios externos que nunca han sido reenviados por otros remitentes de la organización.</span><span class="sxs-lookup"><span data-stu-id="bd702-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="bd702-122">Estos tipos de mensajes reenviados pueden suponer un riesgo de seguridad o cumplimiento, y pueden indicar cuentas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="bd702-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="bd702-123">El informe contiene datos de hasta 90 días.</span><span class="sxs-lookup"><span data-stu-id="bd702-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="bd702-124">De forma predeterminada, el informe muestra los datos de los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="bd702-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="bd702-125">Este informe no está disponible directamente en el [panel](mail-flow-insights-v2.md) flujo de correo o en el panel [informes.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="bd702-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="bd702-126">Además de hacer clic en el vínculo  Ver **informe asociado** a la información en la información de nuevos usuarios que reenvía correo electrónico, puede obtener acceso al informe mediante:</span><span class="sxs-lookup"><span data-stu-id="bd702-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="bd702-127">Haga clic **en el vínculo informe de notificaciones de** reenvío en los detalles de la información de correo electrónico de nuevos dominios que se [reenvía.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="bd702-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="bd702-128">Abrir <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="bd702-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="bd702-129">Vista de informe para el informe de modificaciones de reenvío</span><span class="sxs-lookup"><span data-stu-id="bd702-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="bd702-130">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="bd702-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="bd702-131">**Mostrar datos para: Nuevos usuarios de reenvío:**</span><span class="sxs-lookup"><span data-stu-id="bd702-131">**Show data for: New forwarding users**:</span></span>

  ![Nueva vista de usuarios de reenvío en el informe de modificaciones de reenvío](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="bd702-133">**Mostrar datos para: Nuevos dominios de reenvío:**</span><span class="sxs-lookup"><span data-stu-id="bd702-133">**Show data for: New forwarding domains**:</span></span>

  ![Nueva vista de dominios reenviados en el informe de modificaciones de reenvío](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="bd702-135">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con fecha **de inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="bd702-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="bd702-136">Vista de tabla de detalles para el informe de modificaciones de reenvío</span><span class="sxs-lookup"><span data-stu-id="bd702-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="bd702-137">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="bd702-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="bd702-138">**Mostrar datos para: Nuevos usuarios de reenvío:**</span><span class="sxs-lookup"><span data-stu-id="bd702-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="bd702-139">**Nombre:** la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="bd702-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="bd702-140">**Tipo de reenvío**</span><span class="sxs-lookup"><span data-stu-id="bd702-140">**Forwarding type**</span></span>
  - <span data-ttu-id="bd702-141">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="bd702-141">**Recipient address**</span></span>
  - <span data-ttu-id="bd702-142">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="bd702-142">**Details**</span></span>
  - <span data-ttu-id="bd702-143">**Count**</span><span class="sxs-lookup"><span data-stu-id="bd702-143">**Count**</span></span>
  - <span data-ttu-id="bd702-144">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="bd702-144">**First forward date**</span></span>

- <span data-ttu-id="bd702-145">**Mostrar datos para: Nuevos dominios de reenvío:**</span><span class="sxs-lookup"><span data-stu-id="bd702-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="bd702-146">**Nombre:** el dominio de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="bd702-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="bd702-147">**Tipo de reenvío**</span><span class="sxs-lookup"><span data-stu-id="bd702-147">**Forwarding type**</span></span>
  - <span data-ttu-id="bd702-148">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="bd702-148">**Recipient address**</span></span>
  - <span data-ttu-id="bd702-149">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="bd702-149">**Details**</span></span>
  - <span data-ttu-id="bd702-150">**Count**</span><span class="sxs-lookup"><span data-stu-id="bd702-150">**Count**</span></span>
  - <span data-ttu-id="bd702-151">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="bd702-151">**First forward date**</span></span>

<span data-ttu-id="bd702-152">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con fecha de **inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="bd702-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bd702-153">Si selecciona una fila de la tabla, **aparecerá** un menú desplegable Detalles con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="bd702-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="bd702-154">**Nombre:** esta es la dirección de correo electrónico del remitente (desde Mostrar datos **para:** vista Nuevos usuarios de reenvío) o el dominio de correo electrónico del remitente (desde Mostrar datos **para:** Vista Nuevos dominios de reenvío).</span><span class="sxs-lookup"><span data-stu-id="bd702-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="bd702-155">**Tipo de reenvío**</span><span class="sxs-lookup"><span data-stu-id="bd702-155">**Forwarding type**</span></span>
- <span data-ttu-id="bd702-156">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="bd702-156">**Recipient**</span></span>
- <span data-ttu-id="bd702-157">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="bd702-157">**Details**</span></span>
- <span data-ttu-id="bd702-158">**Count**</span><span class="sxs-lookup"><span data-stu-id="bd702-158">**Count**</span></span>
- <span data-ttu-id="bd702-159">**Fecha de comienzo**</span><span class="sxs-lookup"><span data-stu-id="bd702-159">**Start date**</span></span>
- <span data-ttu-id="bd702-160">**Recomendación:** desde aquí, puede hacer clic en el vínculo para administrar el usuario en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd702-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Menú desplegable de detalles de la tabla de detalles de la vista Nuevos usuarios de reenvío en el informe de modificaciones de reenvío](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="bd702-162">Para volver a la vista informes, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="bd702-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bd702-163">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bd702-163">Related topics</span></span>

<span data-ttu-id="bd702-164">Para obtener información sobre otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="bd702-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
