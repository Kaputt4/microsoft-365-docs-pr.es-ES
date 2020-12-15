---
title: Aprobar o rechazar acciones pendientes tras una investigación automatizada
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.openlocfilehash: b34f4a532571d6215500ab2bec022489fd462d0f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683372"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="677e0-104">Aprobar o rechazar acciones pendientes tras una investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="677e0-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="677e0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="677e0-105">**Applies to:**</span></span>
- <span data-ttu-id="677e0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="677e0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="677e0-107">Cuando se ejecuta una investigación automatizada, puede resultar en una o más [acciones de corrección](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) que requieran la aprobación para continuar.</span><span class="sxs-lookup"><span data-stu-id="677e0-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="677e0-108">Por ejemplo, es posible que sea necesario eliminar un clúster de mensajes de correo electrónico o quitar un archivo en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="677e0-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="677e0-109">Es importante aprobar (o rechazar) acciones pendientes lo antes posible para que las investigaciones automatizadas puedan continuar y completarse de forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="677e0-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="677e0-110">Si cree que algo se perdió o no se detectó de forma incorrecta en las características de investigación y respuesta automatizadas de Microsoft 365 defender, háganoslo saber.</span><span class="sxs-lookup"><span data-stu-id="677e0-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="677e0-111">Consulte [Cómo informar de falsos positivos/negativos en capacidades de investigación y respuesta automatizadas (Air) en Microsoft 365 defender](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="677e0-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="677e0-112">Las acciones pendientes se pueden revisar y aprobar mediante el [centro de actividades](#review-a-pending-action-in-the-action-center) o la [vista detalles](#review-a-pending-action-in-the-investigation-details-view)de la investigación.</span><span class="sxs-lookup"><span data-stu-id="677e0-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="677e0-113">Debe tener [los permisos adecuados](mtp-action-center.md#required-permissions-for-action-center-tasks) para aprobar o rechazar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="677e0-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="677e0-114">Para obtener más información, vea [requisitos previos para la investigación y la respuesta automatizadas en Microsoft 365 defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="677e0-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="677e0-115">Revisar una acción pendiente en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="677e0-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="677e0-116">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="677e0-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="677e0-117">En el panel de navegación, elija **Centro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="677e0-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="677e0-118">En el centro de actividades, en la ficha **pendiente** , seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="677e0-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="677e0-119">Si selecciona un elemento en la columna **número de investigación** , se abrirá la página Detalles de la investigación.</span><span class="sxs-lookup"><span data-stu-id="677e0-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="677e0-120">Allí puede ver los resultados de la investigación y, a continuación, aprobar o rechazar la acción recomendada.</span><span class="sxs-lookup"><span data-stu-id="677e0-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="677e0-121">Si selecciona una fila de la lista, se abre un control flotante, donde puede ver información sobre el elemento.</span><span class="sxs-lookup"><span data-stu-id="677e0-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Aprobar o rechazar una acción](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="677e0-123">Use los vínculos para ver una alerta asociada o una investigación y aprobar o rechazar la acción.</span><span class="sxs-lookup"><span data-stu-id="677e0-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="677e0-124">Revisar una acción pendiente en la vista detalles de la investigación</span><span class="sxs-lookup"><span data-stu-id="677e0-124">Review a pending action in the investigation details view</span></span>

![Detalles de la investigación](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="677e0-126">En una página de detalles de la [investigación](mtp-autoir-results.md) , seleccione la pestaña **acciones pendientes** (o **acciones**). Los elementos que están pendientes de aprobación se enumeran aquí.</span><span class="sxs-lookup"><span data-stu-id="677e0-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="677e0-127">Seleccione un elemento de la lista y, a continuación, elija **aprobar** o **rechazar**.</span><span class="sxs-lookup"><span data-stu-id="677e0-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="677e0-128">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="677e0-128">Next steps</span></span>

- [<span data-ttu-id="677e0-129">Ver los detalles y los resultados de una investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="677e0-129">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="677e0-130">Controlar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="677e0-130">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
