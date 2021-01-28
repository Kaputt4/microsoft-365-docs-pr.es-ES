---
title: Información sobre colas en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Los administradores pueden aprender a usar el widget Colas en el panel flujo de correo del Centro de seguridad & y cumplimiento para supervisar el flujo de correo fallido a las organizaciones locales o asociadas a través de conectores salientes.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 73e97cbbd05e298013e9e686053a969d587ad5cf
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029155"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="60a81-103">Información de colas en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="60a81-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="60a81-104">Cuando los mensajes no se pueden enviar desde su organización a los servidores de correo electrónico locales o asociados mediante conectores, los mensajes se ponen en cola en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60a81-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="60a81-105">Algunos ejemplos comunes que provocan esta condición son:</span><span class="sxs-lookup"><span data-stu-id="60a81-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="60a81-106">El conector no está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="60a81-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="60a81-107">Se han realizado cambios de red o firewall en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="60a81-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="60a81-108">Microsoft 365 seguirá reintentar la entrega durante 24 horas.</span><span class="sxs-lookup"><span data-stu-id="60a81-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="60a81-109">Después de 24 horas, los mensajes expirarán y se devolverán a los remitentes en informes de no entrega (también conocidos como NDRs o mensajes de devolución).</span><span class="sxs-lookup"><span data-stu-id="60a81-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="60a81-110">Si el volumen de correo electrónico en cola supera el umbral predefinido (el valor predeterminado es 200 mensajes), la información está disponible en las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="60a81-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="60a81-111">La **información de colas** en el panel flujo de [correo](mail-flow-insights-v2.md) en el Centro de [& cumplimiento.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="60a81-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="60a81-112">Para obtener más información, vea la información [sobre colas en la sección del](#queues-insight-in-the-mail-flow-dashboard) panel de flujo de correo de este artículo.</span><span class="sxs-lookup"><span data-stu-id="60a81-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="60a81-113">Se muestra una alerta en **alertas** recientes en el panel Alertas del Centro de [seguridad & cumplimiento](https://protection.office.com) (Panel **de** \> **alertas** o <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="60a81-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Alertas recientes en el panel Alertas del Centro de & cumplimiento](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="60a81-115">Los administradores recibirán una notificación por correo electrónico en función de la configuración de la directiva de alerta predeterminada denominada **Mensajes.**</span><span class="sxs-lookup"><span data-stu-id="60a81-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="60a81-116">Para configurar las opciones de notificación de esta alerta, consulta la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="60a81-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="60a81-117">Para obtener más información acerca de las directivas de alerta, vea [Directivas de alerta en el Centro de & cumplimiento.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="60a81-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="60a81-118">Personalizar alertas de cola</span><span class="sxs-lookup"><span data-stu-id="60a81-118">Customize queue alerts</span></span>

1. <span data-ttu-id="60a81-119">En el [Centro de & cumplimiento,](https://protection.office.com)vaya **a** Directivas \> **de alertas o** abra <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="60a81-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="60a81-120">En la **página Directivas de** alerta, busque y seleccione la directiva denominada Mensajes que se ha **retrasado.**</span><span class="sxs-lookup"><span data-stu-id="60a81-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="60a81-121">En el **menú desplegable Mensaje se ha** retrasado y se abre, puedes activar o desactivar la alerta y configurar las opciones de notificación.</span><span class="sxs-lookup"><span data-stu-id="60a81-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Se han retrasado los detalles de la directiva de alerta de mensajes en el Centro de & cumplimiento](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="60a81-123">**Estado:** puede activar o desactivar la alerta.</span><span class="sxs-lookup"><span data-stu-id="60a81-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="60a81-124">**Destinatarios de correo electrónico** y **límite de notificaciones diarias:** haga clic **en Editar** para configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="60a81-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="60a81-125">Para configurar las opciones de notificación, haga clic **en Editar**.</span><span class="sxs-lookup"><span data-stu-id="60a81-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="60a81-126">En el **control desplegable Editar** directiva que aparece, configura las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="60a81-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="60a81-127">**Enviar notificaciones por correo** electrónico: el valor predeterminado está en.</span><span class="sxs-lookup"><span data-stu-id="60a81-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="60a81-128">**Destinatarios de correo** electrónico: el valor predeterminado es **TenantAdmins**.</span><span class="sxs-lookup"><span data-stu-id="60a81-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="60a81-129">**Límite de notificación diario:** el valor predeterminado **es Sin límite.**</span><span class="sxs-lookup"><span data-stu-id="60a81-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="60a81-130">**Umbral:** el valor predeterminado es 200.</span><span class="sxs-lookup"><span data-stu-id="60a81-130">**Threshold**: The default value is 200.</span></span>

   ![La configuración de notificaciones en la directiva de alertas de mensajes se ha retrasado y el Centro de seguridad & cumplimiento](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="60a81-132">Cuando haya terminado, haga clic en **Guardar** y **cerrar.**</span><span class="sxs-lookup"><span data-stu-id="60a81-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="60a81-133">Información sobre colas en el panel de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="60a81-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="60a81-134">Incluso si el volumen de mensajes en cola no ha superado el  umbral y ha [](mail-flow-insights-v2.md) generado una alerta, puede seguir utilizando la información colas en el panel de flujo de correo para ver los mensajes que se han puesto en cola durante más de una hora y tomar medidas antes de que el número de mensajes en cola sea demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="60a81-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Widget Colas en el panel Flujo de correo del Centro de & cumplimiento](../../media/mfi-queues-widget.png)

<span data-ttu-id="60a81-136">Si hace clic en el número de mensajes del widget, aparecerá un **control** flotante Mensajes en cola con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="60a81-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="60a81-137">**Número de mensajes en cola**</span><span class="sxs-lookup"><span data-stu-id="60a81-137">**Number of queued messages**</span></span>
- <span data-ttu-id="60a81-138">**Nombre del conector:** haga clic en el nombre del conector para administrarlo en el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="60a81-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="60a81-139">**Hora de inicio de cola**</span><span class="sxs-lookup"><span data-stu-id="60a81-139">**Queue started time**</span></span>
- <span data-ttu-id="60a81-140">**Los mensajes más antiguos expiraron**</span><span class="sxs-lookup"><span data-stu-id="60a81-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="60a81-141">**Servidor de destino**</span><span class="sxs-lookup"><span data-stu-id="60a81-141">**Destination server**</span></span>
- <span data-ttu-id="60a81-142">**Última dirección IP**</span><span class="sxs-lookup"><span data-stu-id="60a81-142">**Last IP address**</span></span>
- <span data-ttu-id="60a81-143">**Último error**</span><span class="sxs-lookup"><span data-stu-id="60a81-143">**Last error**</span></span>
- <span data-ttu-id="60a81-144">**Cómo corregir:** hay problemas y soluciones comunes disponibles.</span><span class="sxs-lookup"><span data-stu-id="60a81-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="60a81-145">If is a **Fix it now** link is available, click it to fix the problem.</span><span class="sxs-lookup"><span data-stu-id="60a81-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="60a81-146">De lo contrario, haga clic en los vínculos disponibles para obtener más información sobre el error y las posibles soluciones.</span><span class="sxs-lookup"><span data-stu-id="60a81-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Detalles después de hacer clic en la información de colas en el panel de flujo de correo](../../media/mfi-queues-details.png)

<span data-ttu-id="60a81-148">Se muestra el mismo menú desplegable después de hacer clic en Ver **cola** en los detalles de una alerta de mensajes **retrasada.**</span><span class="sxs-lookup"><span data-stu-id="60a81-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Se han retrasado los detalles de las alertas en el Centro de & cumplimiento](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="60a81-150">Consulta también</span><span class="sxs-lookup"><span data-stu-id="60a81-150">See also</span></span>

<span data-ttu-id="60a81-151">Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="60a81-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
