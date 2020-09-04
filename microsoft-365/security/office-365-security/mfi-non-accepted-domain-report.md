---
title: Informe de dominio no aceptado en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el informe de dominio no aceptado en el panel de flujo de correo en el centro de seguridad & cumplimiento para supervisar los mensajes de la organización local donde el dominio del remitente no está configurado en Microsoft 365.
ms.openlocfilehash: 02692fbded20aa5062ce8add83925fb65c116630
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358583"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="02e22-103">Informe de dominio no aceptado en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="02e22-103">Non-accepted domain report in the Security & Compliance Center</span></span>

<span data-ttu-id="02e22-104">El informe de **dominio no aceptado** del [Panel de flujo de correo](mail-flow-insights-v2.md) en el centro de [seguridad & cumplimiento](https://protection.office.com) muestra información sobre los mensajes de la organización de correo electrónico local donde el dominio del remitente no está configurado como un dominio aceptado en la organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02e22-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="02e22-105">Microsoft 365 puede limitar estos mensajes si tenemos datos para probar que la intención de estos mensajes es malintencionada.</span><span class="sxs-lookup"><span data-stu-id="02e22-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="02e22-106">Por lo tanto, es importante que comprenda lo que está sucediendo y que solucione el problema.</span><span class="sxs-lookup"><span data-stu-id="02e22-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Widget de dominio no aceptado en el panel de flujo de correo en el centro de seguridad & cumplimiento](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="02e22-108">Vista informes para el informe de dominio no aceptado</span><span class="sxs-lookup"><span data-stu-id="02e22-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="02e22-109">Al hacer clic en el gráfico en el widget de **dominio no aceptado** , irá al informe de **dominio no aceptado** .</span><span class="sxs-lookup"><span data-stu-id="02e22-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="02e22-110">De forma predeterminada, se muestra la actividad de todos los conectores afectados.</span><span class="sxs-lookup"><span data-stu-id="02e22-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="02e22-111">Si hace clic en **Mostrar datos de**, puede seleccionar un conector específico en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="02e22-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="02e22-112">Si desplaza el puntero sobre un punto de datos (día) del gráfico, verá el número total de mensajes para el conector.</span><span class="sxs-lookup"><span data-stu-id="02e22-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Vista informes en el informe de dominio no aceptado](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="02e22-114">Vista de tabla de detalles para el informe de dominio no aceptado</span><span class="sxs-lookup"><span data-stu-id="02e22-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="02e22-115">Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="02e22-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="02e22-116">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="02e22-116">**Date**</span></span>
- <span data-ttu-id="02e22-117">**Nombre del conector de entrada**</span><span class="sxs-lookup"><span data-stu-id="02e22-117">**Inbound connector name**</span></span>
- <span data-ttu-id="02e22-118">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="02e22-118">**Sender domain**</span></span>
- <span data-ttu-id="02e22-119">**Número de mensajes**</span><span class="sxs-lookup"><span data-stu-id="02e22-119">**Message count**</span></span>
- <span data-ttu-id="02e22-120">**Mensajes de ejemplo**: los identificadores de mensaje de una muestra de mensajes afectados.</span><span class="sxs-lookup"><span data-stu-id="02e22-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="02e22-121">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="02e22-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="02e22-122">Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **solicitar descarga**.</span><span class="sxs-lookup"><span data-stu-id="02e22-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="02e22-123">Cuando se selecciona una fila de la tabla, aparece un control flotante con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="02e22-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="02e22-124">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="02e22-124">**Date**</span></span>
- <span data-ttu-id="02e22-125">**Nombre del conector de entrada**</span><span class="sxs-lookup"><span data-stu-id="02e22-125">**Inbound connector name**</span></span>
- <span data-ttu-id="02e22-126">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="02e22-126">**Sender domain**</span></span>
- <span data-ttu-id="02e22-127">**Número de mensajes**</span><span class="sxs-lookup"><span data-stu-id="02e22-127">**Message count**</span></span>
- <span data-ttu-id="02e22-128">**Mensajes de ejemplo**: puede hacer clic en **Ver mensajes de muestra** para ver los resultados de [seguimiento de mensajes](message-trace-scc.md) para obtener una muestra de los mensajes afectados.</span><span class="sxs-lookup"><span data-stu-id="02e22-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Flotante de detalles después de seleccionar una fila en la vista de tabla de detalles en el informe de dominio no aceptado](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="02e22-130">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="02e22-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="02e22-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="02e22-131">Related topics</span></span>

<span data-ttu-id="02e22-132">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="02e22-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
