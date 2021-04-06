---
title: Ver y administrar acciones en el Centro de acciones
description: Usar el Centro de acciones para ver y administrar acciones de corrección
keywords: action, center, autoair, automated, investigation, response, remediation
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 7106f5d2e740d2b4cacbcaeb0b9391095bbeb356
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592029"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="f7521-104">Ver y administrar acciones en el Centro de acciones</span><span class="sxs-lookup"><span data-stu-id="f7521-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f7521-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f7521-105">**Applies to:**</span></span>
- <span data-ttu-id="f7521-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7521-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f7521-107">Las características de protección contra amenazas en Microsoft 365 Defender pueden dar lugar a determinadas acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="f7521-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="f7521-108">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="f7521-108">Here are some examples:</span></span>
- <span data-ttu-id="f7521-109">[Las investigaciones automatizadas](m365d-autoir.md) pueden dar como resultado acciones de corrección que se toman automáticamente o esperan su aprobación.</span><span class="sxs-lookup"><span data-stu-id="f7521-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await approval.</span></span>
- <span data-ttu-id="f7521-110">Antivirus, antimalware y otras características de protección contra amenazas pueden provocar acciones de corrección, como bloquear un archivo, una dirección URL o un proceso, o enviar un artefacto a la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="f7521-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="f7521-111">El equipo de operaciones de seguridad puede realizar [](advanced-hunting-overview.md) acciones de corrección manualmente, como durante la búsqueda avanzada o al investigar [alertas](investigate-alerts.md) [o incidentes.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="f7521-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f7521-112">Debe tener los [permisos adecuados para](m365d-action-center.md#required-permissions-for-action-center-tasks) aprobar o rechazar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="f7521-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="f7521-113">Para obtener más información, vea [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="f7521-113">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="f7521-114">Revisar acciones pendientes en el Centro de acciones</span><span class="sxs-lookup"><span data-stu-id="f7521-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="f7521-115">Es importante aprobar (o rechazar) las acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas puedan continuar y completarse de forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="f7521-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

![Aprobar o rechazar una acción](../../media/air-actioncenter-itemselected.png)

1. <span data-ttu-id="f7521-117">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="f7521-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="f7521-118">En el panel de navegación, elija **Centro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="f7521-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="f7521-119">En el Centro de acciones, en la **pestaña** Pendiente, seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="f7521-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="f7521-120">Se abre el panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="f7521-120">Its flyout pane opens.</span></span>

4. <span data-ttu-id="f7521-121">Revise la información del panel desplegable y, a continuación, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7521-121">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="f7521-122">Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.</span><span class="sxs-lookup"><span data-stu-id="f7521-122">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="f7521-123">Seleccione **Aprobar** para iniciar una acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="f7521-123">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="f7521-124">Seleccione **Rechazar** para evitar que se haga una acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="f7521-124">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="f7521-125">Seleccione **Ir a la búsqueda** para ir a Búsqueda [avanzada.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f7521-125">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="f7521-126">Deshacer acciones completadas</span><span class="sxs-lookup"><span data-stu-id="f7521-126">Undo completed actions</span></span>

<span data-ttu-id="f7521-127">Si has determinado que un dispositivo o un archivo no es una amenaza, puedes deshacer las acciones de corrección que se realizaron, independientemente de si dichas acciones se realizaron de forma automática o manual.</span><span class="sxs-lookup"><span data-stu-id="f7521-127">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="f7521-128">En el Centro de acciones, en la **ficha** Historial, puede deshacer cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f7521-128">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="f7521-129">Origen de la acción</span><span class="sxs-lookup"><span data-stu-id="f7521-129">Action source</span></span> | <span data-ttu-id="f7521-130">Acciones admitidas</span><span class="sxs-lookup"><span data-stu-id="f7521-130">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="f7521-131">- Investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="f7521-131">- Automated investigation</span></span> <br/><span data-ttu-id="f7521-132">- Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f7521-132">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="f7521-133">- Acciones de respuesta manuales</span><span class="sxs-lookup"><span data-stu-id="f7521-133">- Manual response actions</span></span> | <span data-ttu-id="f7521-134">- Aislar dispositivo</span><span class="sxs-lookup"><span data-stu-id="f7521-134">- Isolate device</span></span> <br/><span data-ttu-id="f7521-135">- Restringir la ejecución de código</span><span class="sxs-lookup"><span data-stu-id="f7521-135">- Restrict code execution</span></span> <br/><span data-ttu-id="f7521-136">- Poner en cuarentena un archivo</span><span class="sxs-lookup"><span data-stu-id="f7521-136">- Quarantine a file</span></span> <br/><span data-ttu-id="f7521-137">- Quitar una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="f7521-137">- Remove a registry key</span></span> <br/><span data-ttu-id="f7521-138">- Detener un servicio</span><span class="sxs-lookup"><span data-stu-id="f7521-138">- Stop a service</span></span> <br/><span data-ttu-id="f7521-139">- Deshabilitar un controlador</span><span class="sxs-lookup"><span data-stu-id="f7521-139">- Disable a driver</span></span> <br/><span data-ttu-id="f7521-140">- Quitar una tarea programada</span><span class="sxs-lookup"><span data-stu-id="f7521-140">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="f7521-141">Deshacer una acción de corrección</span><span class="sxs-lookup"><span data-stu-id="f7521-141">Undo one remediation action</span></span>

1. <span data-ttu-id="f7521-142">Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="f7521-142">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="f7521-143">En la **pestaña** Historial, seleccione una acción que desee deshacer.</span><span class="sxs-lookup"><span data-stu-id="f7521-143">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="f7521-144">En el panel de la parte derecha de la pantalla, seleccione **Deshacer**.</span><span class="sxs-lookup"><span data-stu-id="f7521-144">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="f7521-145">Deshacer varias acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="f7521-145">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="f7521-146">Vaya al Centro de acciones ( https://security.microsoft.com/action-center) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="f7521-146">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="f7521-147">En la **pestaña** Historial, seleccione las acciones que desea deshacer.</span><span class="sxs-lookup"><span data-stu-id="f7521-147">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="f7521-148">Asegúrese de seleccionar los elementos que tienen el mismo tipo de acción.</span><span class="sxs-lookup"><span data-stu-id="f7521-148">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="f7521-149">Se abre un panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="f7521-149">A flyout pane opens.</span></span>

3. <span data-ttu-id="f7521-150">En el panel desplegable, seleccione **Deshacer**.</span><span class="sxs-lookup"><span data-stu-id="f7521-150">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="f7521-151">Para quitar un archivo de la cuarentena en varios dispositivos</span><span class="sxs-lookup"><span data-stu-id="f7521-151">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="f7521-152">Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="f7521-152">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="f7521-153">En la **pestaña** Historial, seleccione un archivo que tenga el tipo de acción **Archivo de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="f7521-153">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="f7521-154">En el panel de la parte derecha de la pantalla, seleccione **Aplicar a X más** instancias de este archivo y, a continuación, seleccione **Deshacer**.</span><span class="sxs-lookup"><span data-stu-id="f7521-154">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f7521-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f7521-155">Next steps</span></span>

- [<span data-ttu-id="f7521-156">Ver los detalles y los resultados de una investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="f7521-156">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="f7521-157">Obtenga información sobre cómo controlar falsos positivos/negativos (si obtiene uno)</span><span class="sxs-lookup"><span data-stu-id="f7521-157">Learn how to handle false positives/negatives (if you get one)</span></span>](m365d-autoir-report-false-positives-negatives.md)
