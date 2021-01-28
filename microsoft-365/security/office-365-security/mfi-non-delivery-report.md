---
title: Informe de no entrega en el panel de flujo de correo
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
description: Los administradores pueden aprender a usar el informe de detalles de no entrega en el panel de flujo de correo del Centro de seguridad & y cumplimiento para supervisar los códigos de error encontrados con más frecuencia en los informes de no entrega (también conocidos como NDRs o mensajes de de retorno) de remitentes de su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbd27fc818a46a983874a04f0e313c622e047ea5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029839"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="a7a8a-103">Informe de no entrega en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="a7a8a-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a7a8a-104">El  informe de no [](mail-flow-insights-v2.md) entrega en el panel de flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) muestra los códigos de error más encontrados en los informes de no entrega (también conocidos como NDRs o mensajes de de retorno) para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="a7a8a-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="a7a8a-105">Este informe muestra los detalles de los NDRs para que pueda solucionar problemas de entrega de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a7a8a-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget Informe de no entrega en el panel flujo de correo del Centro de & cumplimiento](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="a7a8a-107">Vista de informe para el informe de no entrega</span><span class="sxs-lookup"><span data-stu-id="a7a8a-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="a7a8a-108">Al hacer clic en el widget **Informe de no** entrega, se le llevará al informe de no **entrega.**</span><span class="sxs-lookup"><span data-stu-id="a7a8a-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="a7a8a-109">De forma predeterminada, se muestra la actividad de todos los códigos de error.</span><span class="sxs-lookup"><span data-stu-id="a7a8a-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="a7a8a-110">Si hace clic **en Mostrar datos para,** puede seleccionar un código de error específico en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a7a8a-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="a7a8a-111">Si mantiene el puntero sobre un color específico (código de error) en un día específico del gráfico, verá el número total de mensajes del error.</span><span class="sxs-lookup"><span data-stu-id="a7a8a-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Vista de informe en el informe de dominio no aceptado](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="a7a8a-113">Vista de tabla de detalles para el informe de no entrega</span><span class="sxs-lookup"><span data-stu-id="a7a8a-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="a7a8a-114">Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a7a8a-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="a7a8a-115">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="a7a8a-115">**Date**</span></span>
- <span data-ttu-id="a7a8a-116">**Código de informe de no entrega**</span><span class="sxs-lookup"><span data-stu-id="a7a8a-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="a7a8a-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="a7a8a-117">**Count**</span></span>
- <span data-ttu-id="a7a8a-118">**Mensajes de** ejemplo: los iDs de mensaje de una muestra de mensajes afectados.</span><span class="sxs-lookup"><span data-stu-id="a7a8a-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="a7a8a-119">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con fecha de **inicio** y fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="a7a8a-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a7a8a-120">Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **Solicitar descarga.**</span><span class="sxs-lookup"><span data-stu-id="a7a8a-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="a7a8a-121">Al seleccionar una fila de la tabla, aparece un menú desplegable con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a7a8a-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="a7a8a-122">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="a7a8a-122">**Date**</span></span>
- <span data-ttu-id="a7a8a-123">**Código de informe de no** entrega: puede hacer clic en el vínculo para obtener más información sobre las causas y soluciones del código de error específico.</span><span class="sxs-lookup"><span data-stu-id="a7a8a-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="a7a8a-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="a7a8a-124">**Count**</span></span>
- <span data-ttu-id="a7a8a-125">**Mensajes de** ejemplo: puede hacer clic en **Ver mensajes de** ejemplo para ver los resultados del seguimiento de mensajes de una muestra de los mensajes afectados. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="a7a8a-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Menú desplegable Detalles después de seleccionar una fila en la vista Tabla de detalles en el informe de no entrega](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="a7a8a-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a7a8a-127">Related topics</span></span>

<span data-ttu-id="a7a8a-128">Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="a7a8a-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
