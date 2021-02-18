---
title: Información e informes de clientes de autenticación SMTP en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información y el informe de autenticación SMTP en el panel de flujo de correo del Centro de seguridad y cumplimiento de & para supervisar los remitentes de correo electrónico de su organización que usan SMTP autenticado (AUTH SMTP) para enviar mensajes de correo electrónico.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9050fd2c1bc3863a3bd78190cd5b27fda018479e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287802"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="366b4-103">Información e informes de clientes de autenticación SMTP en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="366b4-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="366b4-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="366b4-104">**Applies to**</span></span>
- [<span data-ttu-id="366b4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="366b4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="366b4-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="366b4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="366b4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="366b4-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="366b4-108">La información de los [](mail-flow-insights-v2.md) clientes de autenticación **SMTP** en el panel de flujo de correo y el informe de clientes de autenticación [SMTP](#smtp-auth-clients-report) asociados en el Centro de seguridad y cumplimiento de [&](https://protection.office.com) resaltan el uso del protocolo de envío de cliente AUTH SMTP por parte de los usuarios o cuentas del sistema de su organización.</span><span class="sxs-lookup"><span data-stu-id="366b4-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="366b4-109">Este protocolo heredado (que usa el punto de conexión smtp.office365.com) solo ofrece autenticación básica y es susceptible de ser usado por cuentas comprometidas para enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="366b4-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="366b4-110">La información y el informe le permiten comprobar si hay actividad inusual en los envíos de correo electrónico SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="366b4-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="366b4-111">También muestra los datos de uso de TLS para clientes o dispositivos que usan SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="366b4-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="366b4-112">El widget indica el número de usuarios o cuentas de servicio que han usado el protocolo de autenticación SMTP en los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="366b4-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Widget Clientes de autenticación SMTP en el panel flujo de correo del Centro de & cumplimiento](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="366b4-114">Si hace clic en el número de mensajes del widget, aparecerá un control flotante de clientes de autenticación **SMTP.**</span><span class="sxs-lookup"><span data-stu-id="366b4-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="366b4-115">El menú desplegable proporciona una vista agregada del uso de TLS y los volúmenes de la última semana.</span><span class="sxs-lookup"><span data-stu-id="366b4-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Control flotante de detalles después de hacer clic en el widget Clientes de autenticación SMTP en el panel flujo de correo](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="366b4-117">Puede hacer clic en el vínculo del informe de **clientes de** autenticación SMTP para ir al informe de clientes de autenticación SMTP, tal como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="366b4-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="366b4-118">Informe de clientes de autenticación SMTP</span><span class="sxs-lookup"><span data-stu-id="366b4-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="366b4-119">Vista de informes para el informe de clientes de autenticación SMTP</span><span class="sxs-lookup"><span data-stu-id="366b4-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="366b4-120">De forma predeterminada, el informe muestra los datos de los últimos 7 días, pero los datos están disponibles para los últimos 90 días.</span><span class="sxs-lookup"><span data-stu-id="366b4-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="366b4-121">La sección de información general contiene los siguientes gráficos:</span><span class="sxs-lookup"><span data-stu-id="366b4-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="366b4-122">**Ver datos por:** Volumen de envío: De forma predeterminada, el gráfico muestra el número de mensajes de cliente de autenticación SMTP que se enviaron desde todos los dominios ( Mostrar datos **para:** Todos los dominios de remitente está seleccionado de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="366b4-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="366b4-123">Puede filtrar los resultados a un  dominio de remitente específico haciendo clic en Mostrar datos para y seleccionando el dominio del remitente en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="366b4-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="366b4-124">Si mantiene el puntero sobre un punto de datos específico (día), se muestra el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="366b4-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Enviar la vista por volumen en el informe de clientes de autenticación SMTP en el Centro de & cumplimiento](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="366b4-126">**Ver datos por: Uso de TLS:** el gráfico muestra el porcentaje de uso de TLS para todos los mensajes de cliente de autenticación SMTP durante el período de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="366b4-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="366b4-127">Este gráfico le permite identificar y tomar medidas en usuarios y cuentas del sistema que siguen usando versiones anteriores de TLS.</span><span class="sxs-lookup"><span data-stu-id="366b4-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Vista de uso de TLS en el informe de clientes de autenticación SMTP en el Centro de & cumplimiento](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="366b4-129">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con fecha **de inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="366b4-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="366b4-130">Haga **clic en Solicitar** informe para recibir una versión más detallada del informe en un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="366b4-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="366b4-131">Puede especificar el intervalo de fechas y los destinatarios para recibir el informe.</span><span class="sxs-lookup"><span data-stu-id="366b4-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="366b4-132">Vista de tabla de detalles para el informe de clientes de autenticación SMTP</span><span class="sxs-lookup"><span data-stu-id="366b4-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="366b4-133">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="366b4-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="366b4-134">**Ver datos por: Volumen de envío:** en una tabla se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="366b4-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="366b4-135">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="366b4-135">**Sender address**</span></span>
  - <span data-ttu-id="366b4-136">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="366b4-136">**Message count**</span></span>

  <span data-ttu-id="366b4-137">Si seleccionas una fila, se muestran los mismos detalles en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="366b4-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="366b4-138">**Ver datos por: Uso de TLS:** en una tabla se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="366b4-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="366b4-139">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="366b4-139">**Sender address**</span></span>
  - <span data-ttu-id="366b4-140">**TLS1,0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="366b4-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="366b4-141">**TLS1,1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="366b4-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="366b4-142">**TLS1,2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="366b4-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="366b4-143">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="366b4-143">**Message count**</span></span>

  <span data-ttu-id="366b4-144"><sup>\*</sup> Esta columna muestra el porcentaje y el número de mensajes del remitente.</span><span class="sxs-lookup"><span data-stu-id="366b4-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="366b4-145">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con fecha de **inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="366b4-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="366b4-146">Si seleccionas una fila, se muestran detalles similares en un menú desplegable:</span><span class="sxs-lookup"><span data-stu-id="366b4-146">If you select a row, similar details are shown in a flyout:</span></span>

![Menú desplegable de detalles de la tabla de detalles de la vista de uso de TLS en el informe de clientes de autenticación SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="366b4-148">Haga **clic en Solicitar** informe para recibir una versión más detallada del informe en un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="366b4-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="366b4-149">Puede especificar el intervalo de fechas y los destinatarios para recibir el informe.</span><span class="sxs-lookup"><span data-stu-id="366b4-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="366b4-150">Para volver a la vista informes, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="366b4-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="366b4-151">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="366b4-151">Related topics</span></span>

<span data-ttu-id="366b4-152">Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="366b4-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
