---
title: Aprobar o rechazar acciones pendientes tras la investigación automatizada
description: Usar el centro de actividades para administrar acciones relacionadas con investigación y respuesta automatizadas
keywords: acción, centro, autoair, automatizado, investigación, respuesta, corrección
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 5118f7fddaee0fa768675597dee862eb75e4ed96
ms.sourcegitcommit: 48b69caf6550e68cb14472ea8cfc76b53e7ae9c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225498"
---
# <a name="approve-or-reject-pending-actions-from-automated-investigations"></a><span data-ttu-id="fe16c-104">Aprobar o rechazar acciones pendientes de investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="fe16c-104">Approve or reject pending actions from automated investigations</span></span>

<span data-ttu-id="fe16c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="fe16c-105">**Applies to:**</span></span>
- <span data-ttu-id="fe16c-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fe16c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="fe16c-107">Cuando se ejecuta una investigación automatizada, puede resultar en una o más [acciones de corrección](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) que requieran la aprobación para continuar.</span><span class="sxs-lookup"><span data-stu-id="fe16c-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="fe16c-108">Por ejemplo, es posible que sea necesario eliminar un clúster de mensajes de correo electrónico o quitar un archivo en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="fe16c-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="fe16c-109">Es importante aprobar (o rechazar) acciones pendientes lo antes posible para que las investigaciones automatizadas puedan continuar y completarse de forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="fe16c-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="fe16c-110">Si cree que algo ha perdido o detectado erróneamente las características de respuesta e investigación automatizada en la protección contra amenazas de Microsoft, háganoslo saber.</span><span class="sxs-lookup"><span data-stu-id="fe16c-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="fe16c-111">Consulte [Cómo informar de falsos positivos/negativos en capacidades de investigación y respuesta automatizadas (Air) en la protección contra amenazas de Microsoft](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="fe16c-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="fe16c-112">Las acciones pendientes se pueden revisar y aprobar mediante uno de varios métodos:</span><span class="sxs-lookup"><span data-stu-id="fe16c-112">Pending actions can be reviewed and approved by using one of several methods:</span></span>
- [<span data-ttu-id="fe16c-113">Usar el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="fe16c-113">Use the Action center</span></span>](#review-a-pending-action-in-the-action-center)
- [<span data-ttu-id="fe16c-114">Usar la vista detalles de la investigación</span><span class="sxs-lookup"><span data-stu-id="fe16c-114">Use the investigation details view</span></span>](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> <span data-ttu-id="fe16c-115">Debe tener [los permisos adecuados](mtp-action-center.md#required-permissions-for-action-center-tasks) para aprobar o rechazar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="fe16c-115">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="fe16c-116">Revisar una acción pendiente en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="fe16c-116">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="fe16c-117">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="fe16c-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="fe16c-118">En el panel de navegación, elija **Centro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="fe16c-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="fe16c-119">En el centro de actividades, en la ficha **pendiente** , seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="fe16c-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="fe16c-120">Si selecciona un elemento en la columna **número de investigación** , se abrirá la página Detalles de la investigación.</span><span class="sxs-lookup"><span data-stu-id="fe16c-120">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="fe16c-121">Allí puede ver los resultados de la investigación y, a continuación, aprobar o rechazar la acción recomendada.</span><span class="sxs-lookup"><span data-stu-id="fe16c-121">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="fe16c-122">Si selecciona una fila de la lista, se abre un control flotante, donde puede ver información sobre el elemento.</span><span class="sxs-lookup"><span data-stu-id="fe16c-122">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Aprobar o rechazar una acción](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="fe16c-124">Use los vínculos para ver una alerta asociada o una investigación y aprobar o rechazar la acción.</span><span class="sxs-lookup"><span data-stu-id="fe16c-124">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="fe16c-125">Revisar una acción pendiente en la vista detalles de la investigación</span><span class="sxs-lookup"><span data-stu-id="fe16c-125">Review a pending action in the investigation details view</span></span>

![Detalles de la investigación](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="fe16c-127">En la página Detalles de la [investigación](mtp-autoir-results.md) , seleccione la pestaña **acciones pendientes** (o **acciones**). los elementos que están pendientes de aprobación aparecen aquí.</span><span class="sxs-lookup"><span data-stu-id="fe16c-127">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="fe16c-128">Seleccione un elemento de la lista y, a continuación, elija **aprobar** o **rechazar**.</span><span class="sxs-lookup"><span data-stu-id="fe16c-128">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe16c-129">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fe16c-129">Next steps</span></span>

- [<span data-ttu-id="fe16c-130">Más información sobre el Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="fe16c-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="fe16c-131">Más información sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="fe16c-131">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="fe16c-132">Obtener información sobre la búsqueda</span><span class="sxs-lookup"><span data-stu-id="fe16c-132">Learn about hunting</span></span>](advanced-hunting-overview.md)
