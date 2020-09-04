---
title: Pone en cola información en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Los administradores pueden aprender a usar el widget colas del panel de flujo de correo en el centro de seguridad & cumplimiento para supervisar el flujo de correo incorrecto hacia sus organizaciones locales o de asociados a través de los conectores de salida.
ms.openlocfilehash: bcd78a50f017aae65e82185bf167ea7a227656fa
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357393"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="e3d45-103">Pone en cola información en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e3d45-103">Queues insight in the Security & Compliance Center</span></span>

<span data-ttu-id="e3d45-104">Cuando los mensajes no se pueden enviar desde la organización a los servidores de correo electrónico locales o asociados mediante conectores, los mensajes se colocan en la cola de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3d45-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="e3d45-105">Algunos ejemplos comunes que causan esta condición son:</span><span class="sxs-lookup"><span data-stu-id="e3d45-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="e3d45-106">El conector está configurado incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="e3d45-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="e3d45-107">Ha habido cambios en la red o en el firewall en su entorno local.</span><span class="sxs-lookup"><span data-stu-id="e3d45-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="e3d45-108">Microsoft 365 seguirá reintentando la entrega durante 24 horas.</span><span class="sxs-lookup"><span data-stu-id="e3d45-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="e3d45-109">Transcurridas las 24 horas, los mensajes expirarán y se devolverán a los remitentes en informes de no entrega (también conocidos como NDR o mensajes de devolución).</span><span class="sxs-lookup"><span data-stu-id="e3d45-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="e3d45-110">Si el volumen de correo electrónico en cola supera el umbral predefinido (el valor predeterminado es de 200 mensajes), la información está disponible en las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="e3d45-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="e3d45-111">Las **colas** profundizan en el [panel del flujo de correo](mail-flow-insights-v2.md) en el [centro de seguridad & cumplimiento](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="e3d45-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="e3d45-112">Para obtener más información, vea la información [sobre las colas en la sección panel de flujo de correo](#queues-insight-in-the-mail-flow-dashboard) de este tema.</span><span class="sxs-lookup"><span data-stu-id="e3d45-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>
  
- <span data-ttu-id="e3d45-113">Se muestra una alerta en el panel de alertas del centro de [seguridad & cumplimiento](https://protection.office.com) (panel de**alertas** o) en **Alerts recents** \> **Dashboard** <https://protection.office.com/alertsdashboard> .</span><span class="sxs-lookup"><span data-stu-id="e3d45-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Alertas recientes en el panel de alertas del centro de seguridad & cumplimiento](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="e3d45-115">Los administradores recibirán una notificación de correo electrónico basada en la configuración de la Directiva de alertas predeterminada denominada **mensajes que se han retrasado**.</span><span class="sxs-lookup"><span data-stu-id="e3d45-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="e3d45-116">Para establecer la configuración de las notificaciones para esta alerta, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="e3d45-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="e3d45-117">Para obtener más información acerca de las directivas de alertas, consulte [directivas de alerta en el centro de seguridad & cumplimiento](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e3d45-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="e3d45-118">Personalizar alertas de cola</span><span class="sxs-lookup"><span data-stu-id="e3d45-118">Customize queue alerts</span></span>

1. <span data-ttu-id="e3d45-119">En el [centro de seguridad & cumplimiento](https://protection.office.com), vaya a directivas de alerta de **alertas** \> **Alert policies** o abrir <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="e3d45-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="e3d45-120">En la página **directivas de alerta** , busque y seleccione la Directiva denominada **mensajes que se han retrasado**.</span><span class="sxs-lookup"><span data-stu-id="e3d45-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="e3d45-121">En el **mensaje se ha retrasado** el control flotante que se abre, puede activar o desactivar la alerta y configurar las opciones de notificación.</span><span class="sxs-lookup"><span data-stu-id="e3d45-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Los mensajes se han retrasado de la Directiva de alerta detalles del centro de seguridad & cumplimiento](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="e3d45-123">**Estado**: puede activar o desactivar la alerta.</span><span class="sxs-lookup"><span data-stu-id="e3d45-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="e3d45-124">**Destinatarios de correo electrónico** y **límite de notificaciones diarias**: haga clic en **Editar** para configurar las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e3d45-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="e3d45-125">Para establecer la configuración de las notificaciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e3d45-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="e3d45-126">En el control flotante **Editar Directiva** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e3d45-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e3d45-127">**Enviar notificaciones por correo electrónico**: el valor predeterminado es activado.</span><span class="sxs-lookup"><span data-stu-id="e3d45-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="e3d45-128">**Destinatarios de correo electrónico**: el valor predeterminado es **TenantAdmins**.</span><span class="sxs-lookup"><span data-stu-id="e3d45-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="e3d45-129">**Límite de notificación diario**: el valor predeterminado es **sin límite**.</span><span class="sxs-lookup"><span data-stu-id="e3d45-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="e3d45-130">**Umbral**: el valor predeterminado es 200.</span><span class="sxs-lookup"><span data-stu-id="e3d45-130">**Threshold**: The default value is 200.</span></span>

   ![La configuración de notificaciones en los mensajes se ha retrasado detalles de la Directiva de alerta el centro de seguridad & cumplimiento](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="e3d45-132">Cuando haya terminado, haga clic en **Guardar** y **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e3d45-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="e3d45-133">Pone en cola información en el panel de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="e3d45-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="e3d45-134">Incluso si el volumen de mensajes en cola no ha superado el umbral y ha generado una alerta, puede usar la información de las **colas** del [panel del flujo de correo](mail-flow-insights-v2.md) para ver los mensajes que se han puesto en cola durante más de una hora y emprender acciones antes de que el número de mensajes en cola sea demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="e3d45-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Widget colas del panel flujo de correo en el centro de seguridad & cumplimiento](../../media/mfi-queues-widget.png)

<span data-ttu-id="e3d45-136">Si hace clic en el número de mensajes del widget, aparece un control flotante **en cola de mensajes** con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="e3d45-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="e3d45-137">**Número de mensajes en cola**</span><span class="sxs-lookup"><span data-stu-id="e3d45-137">**Number of queued messages**</span></span>
- <span data-ttu-id="e3d45-138">**Nombre del conector**: haga clic en el nombre del conector para administrar el conector en el centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="e3d45-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="e3d45-139">**Tiempo de inicio de la cola**</span><span class="sxs-lookup"><span data-stu-id="e3d45-139">**Queue started time**</span></span>
- <span data-ttu-id="e3d45-140">**Los mensajes más antiguos expiraron**</span><span class="sxs-lookup"><span data-stu-id="e3d45-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="e3d45-141">**Servidor de destino**</span><span class="sxs-lookup"><span data-stu-id="e3d45-141">**Destination server**</span></span>
- <span data-ttu-id="e3d45-142">**Última dirección IP**</span><span class="sxs-lookup"><span data-stu-id="e3d45-142">**Last IP address**</span></span>
- <span data-ttu-id="e3d45-143">**Último error**</span><span class="sxs-lookup"><span data-stu-id="e3d45-143">**Last error**</span></span>
- <span data-ttu-id="e3d45-144">**Procedimiento para la corrección**: hay disponibles problemas y soluciones comunes.</span><span class="sxs-lookup"><span data-stu-id="e3d45-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="e3d45-145">Si es un vínculo **arreglar ahora** está disponible, haga clic en él para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="e3d45-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="e3d45-146">De lo contrario, haga clic en los vínculos disponibles para obtener más información sobre el error y las posibles soluciones.</span><span class="sxs-lookup"><span data-stu-id="e3d45-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Detalles después de hacer clic en la información sobre las colas del panel flujo de correo](../../media/mfi-queues-details.png)

<span data-ttu-id="e3d45-148">Se muestra el mismo control flotante después de hacer clic en **Ver cola** en los detalles de los **mensajes se han retrasado** la alerta.</span><span class="sxs-lookup"><span data-stu-id="e3d45-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Se han retrasado los detalles de la alerta en el centro de seguridad & cumplimiento](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="e3d45-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e3d45-150">See also</span></span>

<span data-ttu-id="e3d45-151">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="e3d45-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
