---
title: Mapa de flujo de correo
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
description: Los administradores pueden aprender a usar el mapa de flujo de correo en el panel de flujo de correo del Centro de seguridad y cumplimiento de & para visualizar y realizar un seguimiento de cómo fluye el correo hacia y desde su organización a través de conectores y sin usar conectores.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c07730f3abcec8905285cdfdf1579ffb71573ec1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029923"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="472fd-103">Mapa de flujo de correo en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="472fd-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="472fd-104">El **mapa de flujo de correo** en el panel de [flujo](mail-flow-insights-v2.md) de correo del Centro de seguridad [& cumplimiento](https://protection.office.com) ofrece información sobre cómo fluye el correo a través de la organización.</span><span class="sxs-lookup"><span data-stu-id="472fd-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="472fd-105">Puedes usar esta información para aprender patrones, identificar anomalías y solucionar problemas a medida que se producen.</span><span class="sxs-lookup"><span data-stu-id="472fd-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget Mapa de flujo de correo en el panel flujo de correo en el Centro de & cumplimiento](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="472fd-107">De forma predeterminada, el widget muestra el patrón de flujo de correo del día anterior en un gráfico conocido como *diagrama Sankey.*</span><span class="sxs-lookup"><span data-stu-id="472fd-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="472fd-108">Puede usar la flecha izquierda flecha izquierda y flecha derecha flecha ![ derecha para mostrar información de diferentes ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) días.</span><span class="sxs-lookup"><span data-stu-id="472fd-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="472fd-109">Cada color diferente representa el flujo de correo sobre un conector entrante o saliente diferente (o sin conectores).</span><span class="sxs-lookup"><span data-stu-id="472fd-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="472fd-110">Si mueve el puntero sobre un color específico, se muestra el número de mensajes para ese tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="472fd-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="472fd-111">Vista de informe para el mapa de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="472fd-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="472fd-112">Al hacer clic en el widget **Mapa de flujo de** correo, se le llevará al informe de mapa de flujo **de** correo.</span><span class="sxs-lookup"><span data-stu-id="472fd-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="472fd-113">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="472fd-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="472fd-114">**Mostrar datos para: Información general:** Básicamente se trata de una vista más grande del widget.</span><span class="sxs-lookup"><span data-stu-id="472fd-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="472fd-115">Si mantiene el puntero sobre un color específico, se muestra el número de mensajes para ese tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="472fd-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Vista de información general en el informe de mapa de flujo de correo](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="472fd-117">**Mostrar datos para: Detalle:** esta vista muestra detalles sobre los conectores y los dominios de destino.</span><span class="sxs-lookup"><span data-stu-id="472fd-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="472fd-118">Se enumeran los dominios principales de remitente y destinatario, y el resto se coloca en **Otros**.</span><span class="sxs-lookup"><span data-stu-id="472fd-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="472fd-119">Si mantiene el puntero sobre un color y una sección específicos, se muestra el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="472fd-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Vista de detalles en el informe de mapa de flujo de correo](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="472fd-121">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con fecha **de inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="472fd-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="472fd-122">Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **Solicitar descarga.**</span><span class="sxs-lookup"><span data-stu-id="472fd-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="472fd-123">Las conclusiones relacionadas se muestran debajo del mapa de flujo de correo si están disponibles (por ejemplo, corregir la posible información del [bucle de correo).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="472fd-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="472fd-124">Vista de tabla de detalles para el mapa de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="472fd-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="472fd-125">Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="472fd-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="472fd-126">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="472fd-126">**Date**</span></span>
- <span data-ttu-id="472fd-127">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="472fd-127">**Category**</span></span>
- <span data-ttu-id="472fd-128">**Conector/proveedor de servicios de terceros**</span><span class="sxs-lookup"><span data-stu-id="472fd-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="472fd-129">**Dominio de remitente o destinatario**</span><span class="sxs-lookup"><span data-stu-id="472fd-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="472fd-130">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="472fd-130">**Message count**</span></span>

<span data-ttu-id="472fd-131">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con fecha de **inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="472fd-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="472fd-132">Si seleccionas una fila, se muestran detalles similares en un menú desplegable:</span><span class="sxs-lookup"><span data-stu-id="472fd-132">If you select a row, similar details are shown in a flyout:</span></span>

![Control de detalles de la tabla de detalles en el mapa de flujo de correo](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="472fd-134">Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **Solicitar descarga.**</span><span class="sxs-lookup"><span data-stu-id="472fd-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="472fd-135">Para volver a la vista informes, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="472fd-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="472fd-136">Consulta también</span><span class="sxs-lookup"><span data-stu-id="472fd-136">See also</span></span>

<span data-ttu-id="472fd-137">Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="472fd-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
