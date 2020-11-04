---
title: Mapa de flujo de correo
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
description: Los administradores pueden aprender a usar el mapa del flujo de correo en el panel de flujo de correo en el centro de seguridad & cumplimiento para visualizar y realizar un seguimiento de la forma en que el correo fluye hacia y desde la organización a través de conectores y sin usar conectores.
ms.openlocfilehash: fc03f05db77c40dbf726692e6fb6069d587a5ffc
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877770"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="a9114-103">Mapa de flujo de correo en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="a9114-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a9114-104">El **mapa de flujo de correo** en el [Panel de flujo de correo](mail-flow-insights-v2.md) en el centro de [seguridad & cumplimiento](https://protection.office.com) ofrece información sobre cómo fluye el correo a través de la organización.</span><span class="sxs-lookup"><span data-stu-id="a9114-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="a9114-105">Puede usar esta información para aprender patrones, identificar anomalías y corregir problemas a medida que se produzcan.</span><span class="sxs-lookup"><span data-stu-id="a9114-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget mail Flow Map en el panel de flujo de correo en el centro de seguridad & cumplimiento](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="a9114-107">De forma predeterminada, el widget muestra el patrón de flujo de correo del día anterior en un gráfico conocido como diagrama de *Sankey* .</span><span class="sxs-lookup"><span data-stu-id="a9114-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="a9114-108">Puede usar la flecha izquierda ![ y la flecha ](../../media/scc-left-arrow.png) derecha a la izquierda ![ ](../../media/scc-right-arrow.png) para mostrar información de distintos días.</span><span class="sxs-lookup"><span data-stu-id="a9114-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="a9114-109">Cada color diferente representa el flujo de correo a través de un conector de entrada o de salida diferente (o sin usar conectores).</span><span class="sxs-lookup"><span data-stu-id="a9114-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="a9114-110">Si pasa el mouse sobre un color específico, se muestra el número de mensajes para ese tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="a9114-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="a9114-111">Vista informes para el mapa de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="a9114-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="a9114-112">Al hacer clic en el widget **mapa de flujo de correo** , irá al informe de mapa de flujo de **correo** .</span><span class="sxs-lookup"><span data-stu-id="a9114-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="a9114-113">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="a9114-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a9114-114">**Mostrar datos para: información general** : esta es básicamente una vista más amplia del widget.</span><span class="sxs-lookup"><span data-stu-id="a9114-114">**Show data for: Overview** : This is basically a larger view of the widget.</span></span> <span data-ttu-id="a9114-115">Si pasa el mouse sobre un color específico, se muestra el número de mensajes para ese tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="a9114-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Vista general en el informe de mapa de flujo de correo](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="a9114-117">**Mostrar datos para: detalles** : esta vista muestra detalles sobre los conectores y los dominios de destino.</span><span class="sxs-lookup"><span data-stu-id="a9114-117">**Show data for: Detail** : This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="a9114-118">Se enumeran los principales dominios del remitente y el destinatario, y el resto se colocan en **otros**.</span><span class="sxs-lookup"><span data-stu-id="a9114-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="a9114-119">Si pasa el mouse sobre un color y una sección específicos, se muestra el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a9114-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Vista de detalles en el informe de mapa de flujo de correo](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="a9114-121">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="a9114-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a9114-122">Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **solicitar descarga**.</span><span class="sxs-lookup"><span data-stu-id="a9114-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="a9114-123">La información relacionada se muestra debajo del mapa de flujo de correo si está disponible (por ejemplo, la [revisión posible del bucle de correo](mfi-mail-loop-insight.md)).</span><span class="sxs-lookup"><span data-stu-id="a9114-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="a9114-124">Vista de tabla de detalles del mapa de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="a9114-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="a9114-125">Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a9114-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="a9114-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="a9114-126">**Date**</span></span>
- <span data-ttu-id="a9114-127">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="a9114-127">**Category**</span></span>
- <span data-ttu-id="a9114-128">**Conector/proveedor de servicios de terceros**</span><span class="sxs-lookup"><span data-stu-id="a9114-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="a9114-129">**Dominio de remitente/destinatario**</span><span class="sxs-lookup"><span data-stu-id="a9114-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="a9114-130">**Número de mensajes**</span><span class="sxs-lookup"><span data-stu-id="a9114-130">**Message count**</span></span>

<span data-ttu-id="a9114-131">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="a9114-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a9114-132">Si selecciona una fila, se muestran detalles similares en un control flotante:</span><span class="sxs-lookup"><span data-stu-id="a9114-132">If you select a row, similar details are shown in a flyout:</span></span>

![Flotante de detalles de la tabla de detalles en el mapa de flujo de correo](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="a9114-134">Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **solicitar descarga**.</span><span class="sxs-lookup"><span data-stu-id="a9114-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="a9114-135">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="a9114-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9114-136">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a9114-136">See also</span></span>

<span data-ttu-id="a9114-137">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="a9114-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
