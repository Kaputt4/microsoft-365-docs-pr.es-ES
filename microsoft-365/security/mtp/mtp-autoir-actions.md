---
title: Aprobar o rechazar acciones pendientes después de una investigación automatizada
description: Usar el Centro de actividades para administrar acciones relacionadas con la investigación y respuesta automatizadas
keywords: acción, centro, autoair, automatizado, investigación, respuesta, corrección
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930383"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="7a9a7-104">Aprobar o rechazar acciones pendientes después de una investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="7a9a7-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7a9a7-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7a9a7-105">**Applies to:**</span></span>
- <span data-ttu-id="7a9a7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7a9a7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7a9a7-107">Cuando se ejecuta una investigación automatizada, puede dar como resultado una o más acciones de [corrección](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) que requieren aprobación para continuar.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="7a9a7-108">Por ejemplo, es posible que sea necesario eliminar un clúster de mensajes de correo electrónico o que se deba quitar un archivo en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="7a9a7-109">Es importante aprobar (o rechazar) las acciones pendientes lo antes posible para que las investigaciones automatizadas puedan continuar y completarse de forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="7a9a7-110">Si cree que se ha perdido algo o que las características de investigación y respuesta automatizadas de Microsoft 365 Defender han detectado algo incorrectamente, háganoslo saber.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="7a9a7-111">Vea cómo informar de falsos positivos/negativos en las capacidades de investigación y respuesta [automatizada (AIR) en Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="7a9a7-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="7a9a7-112">Las acciones pendientes se pueden revisar y aprobar mediante el Centro [de actividades](#review-a-pending-action-in-the-action-center) o la vista de detalles de [la investigación.](#review-a-pending-action-in-the-investigation-details-view)</span><span class="sxs-lookup"><span data-stu-id="7a9a7-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="7a9a7-113">Debe tener los [permisos adecuados para](mtp-action-center.md#required-permissions-for-action-center-tasks) aprobar o rechazar acciones correctivas.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="7a9a7-114">Para obtener más información, vea [Requisitos previos para la investigación automatizada y la respuesta en Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="7a9a7-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="7a9a7-115">Revisar una acción pendiente en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="7a9a7-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="7a9a7-116">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="7a9a7-117">En el panel de navegación, elija **Centro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="7a9a7-118">En el Centro de acciones, en la **pestaña** Pendiente, seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="7a9a7-119">Si selecciona un elemento en la columna **Número** de investigación, se abrirá la página de detalles de la investigación.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="7a9a7-120">Allí, puede ver los resultados de la investigación y, a continuación, aprobar o rechazar la acción recomendada.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="7a9a7-121">Si selecciona una fila de la lista, se abrirá un menú desplegable, donde podrá ver información sobre ese elemento.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Aprobar o rechazar una acción](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="7a9a7-123">Use los vínculos para ver una alerta asociada o una investigación, y aprobar o rechazar la acción.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="7a9a7-124">Revisar una acción pendiente en la vista de detalles de la investigación</span><span class="sxs-lookup"><span data-stu-id="7a9a7-124">Review a pending action in the investigation details view</span></span>

![Detalles de la investigación](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="7a9a7-126">En una [página de detalles de](mtp-autoir-results.md) la investigación, seleccione la pestaña Acciones pendientes **(o** Acciones).  Los elementos que están pendientes de aprobación se enumeran aquí.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="7a9a7-127">Seleccione un elemento de la lista y, a continuación, elija **Aprobar** o **Rechazar**.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="undo-completed-actions"></a><span data-ttu-id="7a9a7-128">Deshacer acciones completadas</span><span class="sxs-lookup"><span data-stu-id="7a9a7-128">Undo completed actions</span></span>

<span data-ttu-id="7a9a7-129">Si has determinado que un dispositivo o un archivo no es una amenaza, puedes deshacer las acciones de corrección que se realizaron, independientemente de si dichas acciones se realizaron de forma automática o manual.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-129">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="7a9a7-130">En el Centro de actividades, en la **ficha** Historial, puede deshacer cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-130">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="7a9a7-131">Origen de la acción</span><span class="sxs-lookup"><span data-stu-id="7a9a7-131">Action source</span></span> | <span data-ttu-id="7a9a7-132">Acciones admitidas</span><span class="sxs-lookup"><span data-stu-id="7a9a7-132">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="7a9a7-133">- Investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="7a9a7-133">- Automated investigation</span></span> <br/><span data-ttu-id="7a9a7-134">- Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7a9a7-134">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="7a9a7-135">- Acciones de respuesta manuales</span><span class="sxs-lookup"><span data-stu-id="7a9a7-135">- Manual response actions</span></span> | <span data-ttu-id="7a9a7-136">- Aislar dispositivo</span><span class="sxs-lookup"><span data-stu-id="7a9a7-136">- Isolate device</span></span> <br/><span data-ttu-id="7a9a7-137">- Restringir la ejecución de código</span><span class="sxs-lookup"><span data-stu-id="7a9a7-137">- Restrict code execution</span></span> <br/><span data-ttu-id="7a9a7-138">- Poner en cuarentena un archivo</span><span class="sxs-lookup"><span data-stu-id="7a9a7-138">- Quarantine a file</span></span> <br/><span data-ttu-id="7a9a7-139">- Quitar una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="7a9a7-139">- Remove a registry key</span></span> <br/><span data-ttu-id="7a9a7-140">- Detener un servicio</span><span class="sxs-lookup"><span data-stu-id="7a9a7-140">- Stop a service</span></span> <br/><span data-ttu-id="7a9a7-141">- Deshabilitar un controlador</span><span class="sxs-lookup"><span data-stu-id="7a9a7-141">- Disable a driver</span></span> <br/><span data-ttu-id="7a9a7-142">- Quitar una tarea programada</span><span class="sxs-lookup"><span data-stu-id="7a9a7-142">- Remove a scheduled task</span></span> |

### <a name="to-undo-a-remediation-action"></a><span data-ttu-id="7a9a7-143">Para deshacer una acción de corrección</span><span class="sxs-lookup"><span data-stu-id="7a9a7-143">To undo a remediation action</span></span>

1. <span data-ttu-id="7a9a7-144">Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-144">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="7a9a7-145">En la **pestaña** Historial, seleccione una acción que desee deshacer.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-145">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="7a9a7-146">En el panel del lado derecho de la pantalla, seleccione **Deshacer**.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-146">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="7a9a7-147">Para quitar un archivo de la cuarentena en varios dispositivos</span><span class="sxs-lookup"><span data-stu-id="7a9a7-147">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="7a9a7-148">Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-148">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="7a9a7-149">En la **pestaña** Historial, seleccione un archivo que tenga el archivo de cuarentena de tipo **de acción.**</span><span class="sxs-lookup"><span data-stu-id="7a9a7-149">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="7a9a7-150">En el panel del lado derecho de la pantalla, seleccione Aplicar a **X más** instancias de este archivo y, a continuación, **seleccione Deshacer**.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-150">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7a9a7-151">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="7a9a7-151">Next steps</span></span>

- [<span data-ttu-id="7a9a7-152">Ver los detalles y los resultados de una investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="7a9a7-152">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="7a9a7-153">Controlar falsos positivos/negativos en las capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="7a9a7-153">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
