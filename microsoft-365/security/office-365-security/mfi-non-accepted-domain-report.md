---
title: Informe de dominio no aceptado en el panel flujo de correo
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
description: Los administradores pueden aprender a usar el informe de dominio no aceptado en el panel flujo de correo del Centro de seguridad & cumplimiento para supervisar los mensajes de la organización local donde el dominio del remitente no está configurado en Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fb33feb56bf2b52731c03273ce0c6444c333f348
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207298"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="4a329-103">Informe de dominio no aceptado en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="4a329-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4a329-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="4a329-104">**Applies to**</span></span>
- [<span data-ttu-id="4a329-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4a329-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4a329-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="4a329-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4a329-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a329-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4a329-108">El  informe de dominio [](mail-flow-insights-v2.md) no aceptado en el panel Flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) muestra información sobre los mensajes de la organización de correo electrónico local donde el dominio del remitente no está configurado como un dominio aceptado en su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4a329-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="4a329-109">Microsoft 365 podría limitar estos mensajes si tenemos datos para demostrar que la intención de estos mensajes es malintencionada.</span><span class="sxs-lookup"><span data-stu-id="4a329-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="4a329-110">Por lo tanto, es importante que comprenda lo que está sucediendo y solucione el problema.</span><span class="sxs-lookup"><span data-stu-id="4a329-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Widget de dominio no aceptado en el panel Flujo de correo del Centro de & cumplimiento](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="4a329-112">Vista Informe para el informe de dominio no aceptado</span><span class="sxs-lookup"><span data-stu-id="4a329-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="4a329-113">Al hacer clic en el gráfico del widget **Dominio** no aceptado, se le llevará al **informe de dominio no** aceptado.</span><span class="sxs-lookup"><span data-stu-id="4a329-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="4a329-114">De forma predeterminada, se muestra la actividad de todos los conectores afectados.</span><span class="sxs-lookup"><span data-stu-id="4a329-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="4a329-115">Si hace clic **en Mostrar datos para**, puede seleccionar un conector específico en el desplegable.</span><span class="sxs-lookup"><span data-stu-id="4a329-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="4a329-116">Si mantiene el mouse sobre un punto de datos (día) en el gráfico, verá el número total de mensajes para el conector.</span><span class="sxs-lookup"><span data-stu-id="4a329-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Vista Informe en el informe de dominio no aceptado](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="4a329-118">Vista de tabla De detalles para el informe de dominio no aceptado</span><span class="sxs-lookup"><span data-stu-id="4a329-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="4a329-119">Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="4a329-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="4a329-120">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="4a329-120">**Date**</span></span>
- <span data-ttu-id="4a329-121">**Nombre del conector de entrada**</span><span class="sxs-lookup"><span data-stu-id="4a329-121">**Inbound connector name**</span></span>
- <span data-ttu-id="4a329-122">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="4a329-122">**Sender domain**</span></span>
- <span data-ttu-id="4a329-123">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="4a329-123">**Message count**</span></span>
- <span data-ttu-id="4a329-124">**Mensajes de** ejemplo: los IDs de mensaje de una muestra de mensajes afectados.</span><span class="sxs-lookup"><span data-stu-id="4a329-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="4a329-125">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="4a329-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="4a329-126">Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.</span><span class="sxs-lookup"><span data-stu-id="4a329-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="4a329-127">Al seleccionar una fila de la tabla, aparece un menú desplegable con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="4a329-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="4a329-128">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="4a329-128">**Date**</span></span>
- <span data-ttu-id="4a329-129">**Nombre del conector de entrada**</span><span class="sxs-lookup"><span data-stu-id="4a329-129">**Inbound connector name**</span></span>
- <span data-ttu-id="4a329-130">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="4a329-130">**Sender domain**</span></span>
- <span data-ttu-id="4a329-131">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="4a329-131">**Message count**</span></span>
- <span data-ttu-id="4a329-132">**Mensajes de** ejemplo: puede hacer clic **en Ver mensajes de ejemplo** para ver los resultados del seguimiento de mensajes de una muestra de los mensajes afectados. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="4a329-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![El menú desplegable de detalles después de seleccionar una fila en la vista Tabla de detalles en el informe de dominio no aceptado](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="4a329-134">Para volver a la vista informes, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="4a329-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4a329-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4a329-135">Related topics</span></span>

<span data-ttu-id="4a329-136">Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="4a329-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
