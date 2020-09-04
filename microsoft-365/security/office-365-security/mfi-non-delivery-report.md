---
title: Informe de no entrega en el panel de flujo de correo
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
description: Los administradores pueden aprender a usar el informe de detalles de no entrega en el panel de flujo de correo en el centro de seguridad & cumplimiento para supervisar los códigos de error más comunes en los informes de no entrega (también conocidos como NDR o mensajes de devolución) de los remitentes de su organización.
ms.openlocfilehash: f9017a7f041037c5db2dc9b9f4f5155b038bf2c7
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357415"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="40e96-103">Informe de no entrega en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="40e96-103">Non-delivery report in the Security & Compliance Center</span></span>

<span data-ttu-id="40e96-104">El **Informe de no entrega** del [Panel de flujo de correo](mail-flow-insights-v2.md) del [centro de seguridad & cumplimiento](https://protection.office.com) muestra los códigos de error más encontrados en los informes de no entrega (también conocidos como NDR o mensajes de devolución) para los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="40e96-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="40e96-105">Este informe muestra los detalles de NDR para que pueda solucionar problemas de entrega de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="40e96-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget de informe de no entrega en el panel de flujo de correo en el centro de seguridad & cumplimiento](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="40e96-107">Vista informes para el informe de no entrega</span><span class="sxs-lookup"><span data-stu-id="40e96-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="40e96-108">Al hacer clic en el widget **Informe de no entrega** , irá al **Informe de no entrega**.</span><span class="sxs-lookup"><span data-stu-id="40e96-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="40e96-109">De forma predeterminada, se muestra la actividad de todos los códigos de error.</span><span class="sxs-lookup"><span data-stu-id="40e96-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="40e96-110">Si hace clic en **Mostrar datos de**, puede seleccionar un código de error específico en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="40e96-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="40e96-111">Si desplaza el puntero sobre un color específico (código de error) en un día específico del gráfico, verá el número total de mensajes para el error.</span><span class="sxs-lookup"><span data-stu-id="40e96-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Vista informes en el informe de dominio no aceptado](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="40e96-113">Vista de tabla de detalles para el informe de no entrega</span><span class="sxs-lookup"><span data-stu-id="40e96-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="40e96-114">Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="40e96-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="40e96-115">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="40e96-115">**Date**</span></span>
- <span data-ttu-id="40e96-116">**Código de informe de no entrega**</span><span class="sxs-lookup"><span data-stu-id="40e96-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="40e96-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="40e96-117">**Count**</span></span>
- <span data-ttu-id="40e96-118">**Mensajes de ejemplo**: los identificadores de mensaje de una muestra de mensajes afectados.</span><span class="sxs-lookup"><span data-stu-id="40e96-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="40e96-119">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="40e96-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="40e96-120">Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **solicitar descarga**.</span><span class="sxs-lookup"><span data-stu-id="40e96-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="40e96-121">Cuando se selecciona una fila de la tabla, aparece un control flotante con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="40e96-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="40e96-122">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="40e96-122">**Date**</span></span>
- <span data-ttu-id="40e96-123">Código de error de **Informe de no entrega**: puede hacer clic en el vínculo para buscar más información sobre las causas y soluciones para el código de error específico.</span><span class="sxs-lookup"><span data-stu-id="40e96-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="40e96-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="40e96-124">**Count**</span></span>
- <span data-ttu-id="40e96-125">**Mensajes de ejemplo**: puede hacer clic en **Ver mensajes de muestra** para ver los resultados de [seguimiento de mensajes](message-trace-scc.md) para obtener una muestra de los mensajes afectados.</span><span class="sxs-lookup"><span data-stu-id="40e96-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Flotante de detalles después de seleccionar una fila en la vista de tabla de detalles en el informe de no entrega](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="40e96-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="40e96-127">Related topics</span></span>

<span data-ttu-id="40e96-128">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="40e96-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
