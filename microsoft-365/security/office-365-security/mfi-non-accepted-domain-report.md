---
title: Informe de dominio no aceptado en el panel de flujo de correo
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
description: Los administradores pueden aprender a usar el informe de dominio no aceptado en el panel de flujo de correo del Centro de seguridad & y cumplimiento para supervisar los mensajes de la organización local donde el dominio del remitente no está configurado en Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 573fb0ba2bf7981b6eb7df4eec7c8c4e5d596cac
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150825"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="c9d1e-103">Informe de dominio no aceptado en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="c9d1e-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c9d1e-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="c9d1e-104">**Applies to**</span></span>
- [<span data-ttu-id="c9d1e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c9d1e-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="c9d1e-106">Microsoft Defender para Office 365 plan 1 y plan 2</span><span class="sxs-lookup"><span data-stu-id="c9d1e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="c9d1e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9d1e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c9d1e-108">El  informe de dominio [](mail-flow-insights-v2.md) no aceptado en el panel de flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) muestra información sobre los mensajes de la organización de correo electrónico local donde el dominio del remitente no está configurado como un dominio aceptado en su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9d1e-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="c9d1e-109">Microsoft 365 puede limitar estos mensajes si tenemos datos para demostrar que la intención de estos mensajes es malintencionada.</span><span class="sxs-lookup"><span data-stu-id="c9d1e-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="c9d1e-110">Por lo tanto, es importante que comprenda lo que está sucediendo y que solucione el problema.</span><span class="sxs-lookup"><span data-stu-id="c9d1e-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Widget dominio no aceptado en el panel flujo de correo del Centro de & cumplimiento](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="c9d1e-112">Vista de informe para el informe de dominio no aceptado</span><span class="sxs-lookup"><span data-stu-id="c9d1e-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="c9d1e-113">Al hacer clic en el gráfico del widget **Dominio** no aceptado, se le llevará al **informe de dominio no** aceptado.</span><span class="sxs-lookup"><span data-stu-id="c9d1e-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="c9d1e-114">De forma predeterminada, se muestra la actividad de todos los conectores afectados.</span><span class="sxs-lookup"><span data-stu-id="c9d1e-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="c9d1e-115">Si hace clic **en Mostrar datos para,** puede seleccionar un conector específico en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c9d1e-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="c9d1e-116">Si mantiene el puntero sobre un punto de datos (día) en el gráfico, verá el número total de mensajes para el conector.</span><span class="sxs-lookup"><span data-stu-id="c9d1e-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Vista de informe en el informe de dominio no aceptado](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="c9d1e-118">Vista de tabla de detalles para el informe de dominio no aceptado</span><span class="sxs-lookup"><span data-stu-id="c9d1e-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="c9d1e-119">Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c9d1e-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="c9d1e-120">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c9d1e-120">**Date**</span></span>
- <span data-ttu-id="c9d1e-121">**Nombre del conector de entrada**</span><span class="sxs-lookup"><span data-stu-id="c9d1e-121">**Inbound connector name**</span></span>
- <span data-ttu-id="c9d1e-122">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="c9d1e-122">**Sender domain**</span></span>
- <span data-ttu-id="c9d1e-123">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="c9d1e-123">**Message count**</span></span>
- <span data-ttu-id="c9d1e-124">**Mensajes de** ejemplo: los iDs de mensaje de una muestra de mensajes afectados.</span><span class="sxs-lookup"><span data-stu-id="c9d1e-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="c9d1e-125">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con fecha de **inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="c9d1e-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="c9d1e-126">Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **Solicitar descarga.**</span><span class="sxs-lookup"><span data-stu-id="c9d1e-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="c9d1e-127">Al seleccionar una fila de la tabla, aparece un menú desplegable con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c9d1e-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="c9d1e-128">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="c9d1e-128">**Date**</span></span>
- <span data-ttu-id="c9d1e-129">**Nombre del conector de entrada**</span><span class="sxs-lookup"><span data-stu-id="c9d1e-129">**Inbound connector name**</span></span>
- <span data-ttu-id="c9d1e-130">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="c9d1e-130">**Sender domain**</span></span>
- <span data-ttu-id="c9d1e-131">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="c9d1e-131">**Message count**</span></span>
- <span data-ttu-id="c9d1e-132">**Mensajes de** ejemplo: puede hacer clic en **Ver mensajes de** ejemplo para ver los resultados del seguimiento de mensajes de una muestra de los mensajes afectados. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="c9d1e-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Menú desplegable De detalles después de seleccionar una fila en la vista Tabla de detalles en el informe de dominio no aceptado](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="c9d1e-134">Para volver a la vista informes, haga clic **en Ver informe.**</span><span class="sxs-lookup"><span data-stu-id="c9d1e-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c9d1e-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c9d1e-135">Related topics</span></span>

<span data-ttu-id="c9d1e-136">Para obtener información sobre otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="c9d1e-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
