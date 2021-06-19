---
title: Revisar y administrar acciones de corrección en Microsoft Defender para Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Obtenga información sobre las acciones de corrección en las capacidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 8fc01ab0dd5178032ea7b101f5361c25bb10bbea
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028936"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="f553d-104">Revisar y administrar acciones de corrección en Office 365</span><span class="sxs-lookup"><span data-stu-id="f553d-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="f553d-105">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="f553d-105">**Applies to**</span></span>
- [<span data-ttu-id="f553d-106">Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f553d-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="f553d-107">A medida que las investigaciones automatizadas en el &  contenido de colaboración resultan en veredictos, como malintencionados o sospechosos, se crean determinadas acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="f553d-107">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="f553d-108">En Microsoft Defender para Office 365, las acciones de corrección pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="f553d-108">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="f553d-109">Eliminación de mensajes de correo electrónico o clústeres</span><span class="sxs-lookup"><span data-stu-id="f553d-109">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="f553d-110">Desactivar el reenvío de correo externo</span><span class="sxs-lookup"><span data-stu-id="f553d-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="f553d-111">Estas acciones de corrección no se toman a menos que el equipo de operaciones de seguridad las apruebe.</span><span class="sxs-lookup"><span data-stu-id="f553d-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="f553d-112">Se recomienda revisar y aprobar las acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas se completen de forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="f553d-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="f553d-113">En algunos casos, puede reconsiderar las acciones enviadas.</span><span class="sxs-lookup"><span data-stu-id="f553d-113">In some cases, you can reconsider submitted actions.</span></span>  <span data-ttu-id="f553d-114">Debe formar parte de la función de & de depuración antes de realizar cualquier acción.</span><span class="sxs-lookup"><span data-stu-id="f553d-114">You need to be part of Search & purge role before taking any actions.</span></span>


## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="f553d-115">Aprobar (o rechazar) acciones pendientes</span><span class="sxs-lookup"><span data-stu-id="f553d-115">Approve (or reject) pending actions</span></span>
<span data-ttu-id="f553d-116">Hay cuatro formas diferentes de buscar y realizar acciones de investigación automática:</span><span class="sxs-lookup"><span data-stu-id="f553d-116">There are four different ways to find and take auto investigation actions:</span></span>

- [<span data-ttu-id="f553d-117">Cola de incidentes</span><span class="sxs-lookup"><span data-stu-id="f553d-117">Incident queue</span></span>](https://security.microsoft.com/incidents)
- [<span data-ttu-id="f553d-118">Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="f553d-118">Action center</span></span>](https://security.microsoft.com/action-center/pending)
- <span data-ttu-id="f553d-119">Investigación en sí (a la que se accede a través de un incidente o desde una alerta)</span><span class="sxs-lookup"><span data-stu-id="f553d-119">Investigation itself (accessed via Incident or from an alert)</span></span>
- [<span data-ttu-id="f553d-120">Cola de investigaciones de investigación y corrección</span><span class="sxs-lookup"><span data-stu-id="f553d-120">Investigation and remediation investigations queue</span></span>](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a><span data-ttu-id="f553d-121">Cola de incidentes</span><span class="sxs-lookup"><span data-stu-id="f553d-121">Incident queue</span></span>
1. <span data-ttu-id="f553d-122">Vaya al centro [Microsoft 365 seguridad e](https://security.microsoft.com) inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="f553d-122">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="f553d-123">En el panel de navegación, seleccione **Incidentes & alertas > incidentes**.</span><span class="sxs-lookup"><span data-stu-id="f553d-123">In the navigation pane, select **Incidents & alerts > Incidents**.</span></span>
3. <span data-ttu-id="f553d-124">Seleccione un nombre de incidente para abrir su página de resumen.</span><span class="sxs-lookup"><span data-stu-id="f553d-124">Select an incident name to open its summary page.</span></span>
4. <span data-ttu-id="f553d-125">Seleccione la **pestaña Evidencia y** respuesta.</span><span class="sxs-lookup"><span data-stu-id="f553d-125">Select the **Evidence and Response** tab.</span></span>
5. <span data-ttu-id="f553d-126">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="f553d-126">Select an item in the list.</span></span> <span data-ttu-id="f553d-127">Se abre su panel lateral.</span><span class="sxs-lookup"><span data-stu-id="f553d-127">Its side pane opens.</span></span>
6. <span data-ttu-id="f553d-128">En el panel lateral, lleve a cabo acciones de aprobación o rechazo.</span><span class="sxs-lookup"><span data-stu-id="f553d-128">In the side pane, take approve or reject actions.</span></span>

## <a name="investigation-queue"></a><span data-ttu-id="f553d-129">Cola de investigación</span><span class="sxs-lookup"><span data-stu-id="f553d-129">Investigation queue</span></span> 
1. <span data-ttu-id="f553d-130">Vaya al centro [Microsoft 365 seguridad e](https://security.microsoft.com) inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="f553d-130">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="f553d-131">Navegue desde la página alertas/incidentes.</span><span class="sxs-lookup"><span data-stu-id="f553d-131">Navigate from the alerts/incident page.</span></span> 
3. <span data-ttu-id="f553d-132">En la página Investigación, vaya a la **pestaña Acciones pendientes.**</span><span class="sxs-lookup"><span data-stu-id="f553d-132">On the Investigation page, go to the **pending actions** tab.</span></span> 
4. <span data-ttu-id="f553d-133">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="f553d-133">Select an item in the list.</span></span> <span data-ttu-id="f553d-134">Se abre su panel lateral.</span><span class="sxs-lookup"><span data-stu-id="f553d-134">Its side pane opens.</span></span>  
5. <span data-ttu-id="f553d-135">En el panel lateral, lleve a cabo acciones de aprobación o rechazo.</span><span class="sxs-lookup"><span data-stu-id="f553d-135">In the side pane, take approve or reject actions.</span></span>

## <a name="action-center"></a><span data-ttu-id="f553d-136">Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="f553d-136">Action center</span></span>
1. <span data-ttu-id="f553d-137">Vaya al centro [Microsoft 365 seguridad e](https://security.microsoft.com) inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="f553d-137">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="f553d-138">En el panel de navegación, seleccione **Centro de acciones**.</span><span class="sxs-lookup"><span data-stu-id="f553d-138">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="f553d-139">En la **pestaña** Pendiente, revise la lista de acciones que están a la espera de su aprobación.</span><span class="sxs-lookup"><span data-stu-id="f553d-139">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
   - <span data-ttu-id="f553d-140">Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.</span><span class="sxs-lookup"><span data-stu-id="f553d-140">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="f553d-141">Seleccione **Aprobar** para iniciar una acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="f553d-141">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="f553d-142">Seleccione **Rechazar** para evitar que se haga una acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="f553d-142">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="investigation-and-remediation-investigations-queue"></a><span data-ttu-id="f553d-143">Cola de investigaciones de investigación y corrección</span><span class="sxs-lookup"><span data-stu-id="f553d-143">Investigation and remediation investigations queue</span></span>
1. <span data-ttu-id="f553d-144">Vaya al centro [Microsoft 365 seguridad e](https://security.microsoft.com) inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="f553d-144">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="f553d-145">Abrir investigaciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="f553d-145">Open pending investigations.</span></span> 
3. <span data-ttu-id="f553d-146">En la página Investigación, vaya a la **pestaña Acciones pendientes.**</span><span class="sxs-lookup"><span data-stu-id="f553d-146">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="f553d-147">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="f553d-147">Select an item in the list.</span></span> <span data-ttu-id="f553d-148">Se abre su panel lateral.</span><span class="sxs-lookup"><span data-stu-id="f553d-148">Its side pane opens.</span></span>  
5. <span data-ttu-id="f553d-149">En el panel lateral, lleve a cabo acciones de aprobación o rechazo.</span><span class="sxs-lookup"><span data-stu-id="f553d-149">In the side pane, take approve or reject actions.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="f553d-150">Cambiar o deshacer una acción de corrección</span><span class="sxs-lookup"><span data-stu-id="f553d-150">Change or undo one remediation action</span></span>

<span data-ttu-id="f553d-151">Hay dos formas diferentes de reconsiderar las acciones enviadas:</span><span class="sxs-lookup"><span data-stu-id="f553d-151">There are two different ways to reconsider submitted actions:</span></span>
   - <span data-ttu-id="f553d-152">A través del [centro de acciones unificado](https://security.microsoft.com/action-center).</span><span class="sxs-lookup"><span data-stu-id="f553d-152">Through the [unified action center](https://security.microsoft.com/action-center).</span></span>
   - <span data-ttu-id="f553d-153">Aunque el [Office de acción](https://security.microsoft.com/threatincidents).</span><span class="sxs-lookup"><span data-stu-id="f553d-153">Though the [Office action center](https://security.microsoft.com/threatincidents).</span></span>
   
## <a name="change-or-undo-through-the-unified-action-center"></a><span data-ttu-id="f553d-154">Cambiar o deshacer a través del centro de acciones unificado</span><span class="sxs-lookup"><span data-stu-id="f553d-154">Change or undo through the unified action center</span></span>
1. <span data-ttu-id="f553d-155">Vaya al centro [de acciones unificado](https://security.microsoft.com/action-center) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="f553d-155">Go to the [unified action center](https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="f553d-156">En la **pestaña** Historial, seleccione una acción que desee cambiar o deshacer.</span><span class="sxs-lookup"><span data-stu-id="f553d-156">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="f553d-157">En el panel de la parte derecha de la pantalla, seleccione la acción adecuada **(** mover a la bandeja de **entrada,** mover a correo no **deseado,** mover a elementos eliminados , \*\*eliminación temporal" o eliminar de forma **permanente**).</span><span class="sxs-lookup"><span data-stu-id="f553d-157">In the pane on the right side of the screen, select the appropriate action (**move to inbox**, **move to junk**, **move to deleted items**, \*\*soft delete", or **hard delete**).</span></span>

 ## <a name="change-or-undo-through-the-office-action-center"></a><span data-ttu-id="f553d-158">Cambiar o deshacer a través del centro de Office acción</span><span class="sxs-lookup"><span data-stu-id="f553d-158">Change or undo through the Office action center</span></span> 
1. <span data-ttu-id="f553d-159">Vaya al centro [de Office acción e](https://security.microsoft.com/threatincidents) inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="f553d-159">Go to the [Office action center](https://security.microsoft.com/threatincidents) and sign in.</span></span>
2. <span data-ttu-id="f553d-160">Seleccione la corrección adecuada.</span><span class="sxs-lookup"><span data-stu-id="f553d-160">Select the appropriate remediation.</span></span>
3. <span data-ttu-id="f553d-161">En el panel lateral, haga clic en la entrada envíos de correo y espere a que se cargue la lista.</span><span class="sxs-lookup"><span data-stu-id="f553d-161">In the side pane, click on the mail submissions entry and wait for the list to load.</span></span> 
4. <span data-ttu-id="f553d-162">Espere a que el botón Acción de la parte superior habilite y seleccione el botón Acción para cambiar el tipo de acción.</span><span class="sxs-lookup"><span data-stu-id="f553d-162">Wait for the Action button at the top to enable and select the Action button to change the action type.</span></span> 
5. <span data-ttu-id="f553d-163">Esto creará las acciones adecuadas.</span><span class="sxs-lookup"><span data-stu-id="f553d-163">This will create the appropriate actions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f553d-164">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f553d-164">Next steps</span></span>

- [<span data-ttu-id="f553d-165">Usar el Explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="f553d-165">Use Threat Explorer</span></span>](threat-explorer.md) 
- [<span data-ttu-id="f553d-166">Acciones de administrador /manual</span><span class="sxs-lookup"><span data-stu-id="f553d-166">Admin /Manual Actions</span></span>](remediate-malicious-email-delivered-office-365.md)
- [<span data-ttu-id="f553d-167">Cómo notificar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="f553d-167">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="f553d-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="f553d-168">See also</span></span>

- [<span data-ttu-id="f553d-169">Ver detalles y resultados de una investigación automatizada en Office 365</span><span class="sxs-lookup"><span data-stu-id="f553d-169">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
