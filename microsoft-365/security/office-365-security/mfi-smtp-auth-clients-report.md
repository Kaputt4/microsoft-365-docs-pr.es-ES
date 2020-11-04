---
title: Informes y información sobre los clientes de autenticación SMTP en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el informe de conocimiento de autenticación de SMTP en el panel de flujo de correo en el centro de seguridad & cumplimiento para supervisar los remitentes de correo electrónico de su organización que usan SMTP autenticado (autenticación SMTP) para enviar mensajes de correo electrónico.
ms.openlocfilehash: 54798dfcad50c263705b027c879fdf71d0dabfba
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877566"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="cb9f7-103">Informes y información sobre los clientes de autenticación SMTP en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cb9f7-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cb9f7-104">El centro de **clientes de autenticación SMTP** información sobre el [Panel de flujo de correo](mail-flow-insights-v2.md) y el informe de clientes de [autenticación SMTP](#smtp-auth-clients-report) asociados en el [centro de seguridad & cumplimiento](https://protection.office.com) resaltan el uso del Protocolo de envío de cliente de autenticación SMTP por parte de los usuarios o las cuentas del sistema de la organización.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="cb9f7-105">Este protocolo heredado (que usa el punto de conexión smtp.office365.com) solo ofrece autenticación básica y es vulnerable a su uso por parte de cuentas comprometidas para enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="cb9f7-106">La información y el informe permiten buscar actividades inusuales para los envíos de correo electrónico de autenticación SMTP.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="cb9f7-107">También muestra los datos de uso de TLS para clientes o dispositivos que usan SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="cb9f7-108">El widget indica el número de usuarios o cuentas de servicio que han usado el protocolo de autenticación SMTP en los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Widget SMTP AUTH clients en el panel de flujo de correo del centro de seguridad & cumplimiento](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="cb9f7-110">Si hace clic en el número de mensajes del widget, aparece un control flotante **clientes de autenticación SMTP** .</span><span class="sxs-lookup"><span data-stu-id="cb9f7-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="cb9f7-111">El control flotante proporciona una vista agregada de los volúmenes y el uso de TLS para la semana pasada.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Flotante de detalles después de hacer clic en el widget de clientes de autenticación SMTP en el panel de flujo de correo](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="cb9f7-113">Puede hacer clic en el vínculo de **Informe clientes de autenticación SMTP** para ir al informe de clientes de autenticación SMTP, como se describe en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="cb9f7-114">Informe de clientes de autenticación SMTP</span><span class="sxs-lookup"><span data-stu-id="cb9f7-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="cb9f7-115">Vista informes para el informe de clientes de autenticación SMTP</span><span class="sxs-lookup"><span data-stu-id="cb9f7-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="cb9f7-116">De forma predeterminada, el informe muestra los datos de los últimos 7 días, pero los datos están disponibles para los últimos 90 días.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="cb9f7-117">La sección información general contiene los siguientes gráficos:</span><span class="sxs-lookup"><span data-stu-id="cb9f7-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="cb9f7-118">**Ver datos por: volumen de envío** : de forma predeterminada, el gráfico muestra el número de mensajes de cliente de autenticación SMTP que se enviaron desde todos los dominios ( **Mostrar datos para: todos los dominios de remite** están seleccionados de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="cb9f7-118">**View data by: Sending volume** : By default, the chart shows the number of SMTP Auth client messages that were sent from all domains ( **Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="cb9f7-119">Puede filtrar los resultados a un dominio de remitente específico haciendo clic en **Mostrar datos para** y seleccionando el dominio del remitente en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="cb9f7-120">Si pasa por un punto de datos específico (día), se muestra el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Envío de la vista de volumen en el informe de clientes de autenticación SMTP en el centro de seguridad & cumplimiento](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="cb9f7-122">**Ver datos por: uso de TLS** : el gráfico muestra el porcentaje de uso de TLS para todos los mensajes de cliente de autenticación SMTP durante el período de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-122">**View data by: TLS Usage** : The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="cb9f7-123">Este gráfico permite identificar y realizar acciones en usuarios y cuentas del sistema que todavía usan versiones anteriores de TLS.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Vista de uso de TLS en el informe de clientes de autenticación SMTP en el centro de seguridad & cumplimiento](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="cb9f7-125">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="cb9f7-126">Haga clic en **Solicitar informe** para recibir una versión más detallada del informe en un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="cb9f7-127">Puede especificar el intervalo de fechas y los destinatarios que recibirán el informe.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="cb9f7-128">Vista de tabla de detalles para el informe de clientes de autenticación SMTP</span><span class="sxs-lookup"><span data-stu-id="cb9f7-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="cb9f7-129">Si hace clic en **ver tabla de detalles** , la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="cb9f7-129">If you click **View details table** , the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cb9f7-130">**Ver datos por: volumen de envío** : la siguiente información se muestra en una tabla:</span><span class="sxs-lookup"><span data-stu-id="cb9f7-130">**View data by: Sending volume** : The following information is shown in a table:</span></span>

  - <span data-ttu-id="cb9f7-131">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="cb9f7-131">**Sender address**</span></span>
  - <span data-ttu-id="cb9f7-132">**Número de mensajes**</span><span class="sxs-lookup"><span data-stu-id="cb9f7-132">**Message count**</span></span>

  <span data-ttu-id="cb9f7-133">Si selecciona una fila, se muestran los mismos detalles en un control flotante.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="cb9f7-134">**Ver datos por: uso de TLS** : la siguiente información se muestra en una tabla:</span><span class="sxs-lookup"><span data-stu-id="cb9f7-134">**View data by: TLS Usage** : The following information is shown in a table:</span></span>

  - <span data-ttu-id="cb9f7-135">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="cb9f7-135">**Sender address**</span></span>
  - <span data-ttu-id="cb9f7-136">**TLS 1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cb9f7-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="cb9f7-137">**TLS 1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cb9f7-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="cb9f7-138">**TLS 1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cb9f7-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="cb9f7-139">**Número de mensajes**</span><span class="sxs-lookup"><span data-stu-id="cb9f7-139">**Message count**</span></span>

  <span data-ttu-id="cb9f7-140"><sup>\*</sup> Esta columna muestra el porcentaje y el número de mensajes del remitente.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="cb9f7-141">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="cb9f7-142">Si selecciona una fila, se muestran detalles similares en un control flotante:</span><span class="sxs-lookup"><span data-stu-id="cb9f7-142">If you select a row, similar details are shown in a flyout:</span></span>

![Flotante de detalles de la tabla de detalles de la vista uso de TLS en el informe de clientes de autenticación SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="cb9f7-144">Haga clic en **Solicitar informe** para recibir una versión más detallada del informe en un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="cb9f7-145">Puede especificar el intervalo de fechas y los destinatarios que recibirán el informe.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="cb9f7-146">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="cb9f7-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cb9f7-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cb9f7-147">Related topics</span></span>

<span data-ttu-id="cb9f7-148">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="cb9f7-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
