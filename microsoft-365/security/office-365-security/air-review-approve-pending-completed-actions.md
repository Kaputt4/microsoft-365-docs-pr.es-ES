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
ms.openlocfilehash: 987771616acfd2f2faf425e525505b320155388e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108540"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="fc858-104">Revisar y administrar acciones de corrección en Office 365</span><span class="sxs-lookup"><span data-stu-id="fc858-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="fc858-105">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="fc858-105">**Applies to**</span></span>
- [<span data-ttu-id="fc858-106">Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fc858-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="fc858-107">A medida que las investigaciones automatizadas en el &  contenido de colaboración resultan en veredictos, como malintencionados o sospechosos, se crean determinadas acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="fc858-107">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="fc858-108">En Microsoft Defender para Office 365, las acciones de corrección pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="fc858-108">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="fc858-109">Eliminación de mensajes de correo electrónico o clústeres</span><span class="sxs-lookup"><span data-stu-id="fc858-109">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="fc858-110">Desactivar el reenvío de correo externo</span><span class="sxs-lookup"><span data-stu-id="fc858-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="fc858-111">Estas acciones de corrección no se toman a menos que el equipo de operaciones de seguridad las apruebe.</span><span class="sxs-lookup"><span data-stu-id="fc858-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="fc858-112">Se recomienda revisar y aprobar las acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas se completen de forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="fc858-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="fc858-113">En algunos casos, puede reconsiderar las acciones enviadas.</span><span class="sxs-lookup"><span data-stu-id="fc858-113">In some cases, you can reconsider submitted actions.</span></span>  <span data-ttu-id="fc858-114">Debe formar parte de la función de & de depuración antes de realizar cualquier acción.</span><span class="sxs-lookup"><span data-stu-id="fc858-114">You need to be part of Search & purge role before taking any actions.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="fc858-115">Aprobar (o rechazar) acciones pendientes</span><span class="sxs-lookup"><span data-stu-id="fc858-115">Approve (or reject) pending actions</span></span>
<span data-ttu-id="fc858-116">Hay cuatro formas diferentes de buscar y realizar acciones de investigación automática:</span><span class="sxs-lookup"><span data-stu-id="fc858-116">There are four different ways to find and take auto investigation actions:</span></span>

- [<span data-ttu-id="fc858-117">Cola de incidentes</span><span class="sxs-lookup"><span data-stu-id="fc858-117">Incident queue</span></span>](https://security.microsoft.com/incidents)
- [<span data-ttu-id="fc858-118">Centro de acciones</span><span class="sxs-lookup"><span data-stu-id="fc858-118">Action center</span></span>](https://security.microsoft.com/action-center/pending)
- <span data-ttu-id="fc858-119">Investigación en sí (a la que se accede a través de un incidente o desde una alerta)</span><span class="sxs-lookup"><span data-stu-id="fc858-119">Investigation itself (accessed via Incident or from an alert)</span></span>
- [<span data-ttu-id="fc858-120">Cola de investigaciones de investigación y corrección</span><span class="sxs-lookup"><span data-stu-id="fc858-120">Investigation and remediation investigations queue</span></span>](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a><span data-ttu-id="fc858-121">Cola de incidentes</span><span class="sxs-lookup"><span data-stu-id="fc858-121">Incident queue</span></span>

1. <span data-ttu-id="fc858-122">Abra el portal Microsoft 365 Defender ( <https://security.microsoft.com> ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="fc858-122">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="fc858-123">En el panel de navegación, seleccione **Incidentes & alertas > incidentes**.</span><span class="sxs-lookup"><span data-stu-id="fc858-123">In the navigation pane, select **Incidents & alerts > Incidents**.</span></span>
3. <span data-ttu-id="fc858-124">Seleccione un nombre de incidente para abrir su página de resumen.</span><span class="sxs-lookup"><span data-stu-id="fc858-124">Select an incident name to open its summary page.</span></span>
4. <span data-ttu-id="fc858-125">Seleccione la **pestaña Evidencia y** respuesta.</span><span class="sxs-lookup"><span data-stu-id="fc858-125">Select the **Evidence and Response** tab.</span></span>
5. <span data-ttu-id="fc858-126">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="fc858-126">Select an item in the list.</span></span> <span data-ttu-id="fc858-127">Se abre su panel lateral.</span><span class="sxs-lookup"><span data-stu-id="fc858-127">Its side pane opens.</span></span>
6. <span data-ttu-id="fc858-128">En el panel lateral, lleve a cabo acciones de aprobación o rechazo.</span><span class="sxs-lookup"><span data-stu-id="fc858-128">In the side pane, take approve or reject actions.</span></span>

## <a name="investigation-queue"></a><span data-ttu-id="fc858-129">Cola de investigación</span><span class="sxs-lookup"><span data-stu-id="fc858-129">Investigation queue</span></span>

1. <span data-ttu-id="fc858-130">Abra el portal Microsoft 365 Defender ( <https://security.microsoft.com> ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="fc858-130">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="fc858-131">Navegue desde la página alertas/incidentes.</span><span class="sxs-lookup"><span data-stu-id="fc858-131">Navigate from the alerts/incident page.</span></span>
3. <span data-ttu-id="fc858-132">En la página Investigación, vaya a la **pestaña Acciones pendientes.**</span><span class="sxs-lookup"><span data-stu-id="fc858-132">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="fc858-133">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="fc858-133">Select an item in the list.</span></span> <span data-ttu-id="fc858-134">Se abre su panel lateral.</span><span class="sxs-lookup"><span data-stu-id="fc858-134">Its side pane opens.</span></span>
5. <span data-ttu-id="fc858-135">En el panel lateral, lleve a cabo acciones de aprobación o rechazo.</span><span class="sxs-lookup"><span data-stu-id="fc858-135">In the side pane, take approve or reject actions.</span></span>

## <a name="action-center"></a><span data-ttu-id="fc858-136">Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="fc858-136">Action center</span></span>

1. <span data-ttu-id="fc858-137">Abra el portal Microsoft 365 Defender ( <https://security.microsoft.com> ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="fc858-137">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="fc858-138">En el panel de navegación, seleccione **Centro de acciones**.</span><span class="sxs-lookup"><span data-stu-id="fc858-138">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="fc858-139">En la **pestaña** Pendiente, revise la lista de acciones que están a la espera de su aprobación.</span><span class="sxs-lookup"><span data-stu-id="fc858-139">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
   - <span data-ttu-id="fc858-140">Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.</span><span class="sxs-lookup"><span data-stu-id="fc858-140">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="fc858-141">Seleccione **Aprobar** para iniciar una acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="fc858-141">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="fc858-142">Seleccione **Rechazar** para evitar que se haga una acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="fc858-142">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="investigation-and-remediation-investigations-queue"></a><span data-ttu-id="fc858-143">Cola de investigaciones de investigación y corrección</span><span class="sxs-lookup"><span data-stu-id="fc858-143">Investigation and remediation investigations queue</span></span>

1. <span data-ttu-id="fc858-144">Abra el portal Microsoft 365 Defender ( <https://security.microsoft.com> ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="fc858-144">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="fc858-145">Abrir investigaciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="fc858-145">Open pending investigations.</span></span>
3. <span data-ttu-id="fc858-146">En la página Investigación, vaya a la **pestaña Acciones pendientes.**</span><span class="sxs-lookup"><span data-stu-id="fc858-146">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="fc858-147">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="fc858-147">Select an item in the list.</span></span> <span data-ttu-id="fc858-148">Se abre su panel lateral.</span><span class="sxs-lookup"><span data-stu-id="fc858-148">Its side pane opens.</span></span>
5. <span data-ttu-id="fc858-149">En el panel lateral, lleve a cabo acciones de aprobación o rechazo.</span><span class="sxs-lookup"><span data-stu-id="fc858-149">In the side pane, take approve or reject actions.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="fc858-150">Cambiar o deshacer una acción de corrección</span><span class="sxs-lookup"><span data-stu-id="fc858-150">Change or undo one remediation action</span></span>

<span data-ttu-id="fc858-151">Hay dos formas diferentes de reconsiderar las acciones enviadas:</span><span class="sxs-lookup"><span data-stu-id="fc858-151">There are two different ways to reconsider submitted actions:</span></span>

- <span data-ttu-id="fc858-152">A través del [centro de acciones unificado](https://security.microsoft.com/action-center).</span><span class="sxs-lookup"><span data-stu-id="fc858-152">Through the [unified action center](https://security.microsoft.com/action-center).</span></span>
- <span data-ttu-id="fc858-153">Aunque el [Office de acción](https://security.microsoft.com/threatincidents).</span><span class="sxs-lookup"><span data-stu-id="fc858-153">Though the [Office action center](https://security.microsoft.com/threatincidents).</span></span>

## <a name="change-or-undo-through-the-unified-action-center"></a><span data-ttu-id="fc858-154">Cambiar o deshacer a través del centro de acciones unificado</span><span class="sxs-lookup"><span data-stu-id="fc858-154">Change or undo through the unified action center</span></span>

1. <span data-ttu-id="fc858-155">Vaya al centro [de acciones unificado](https://security.microsoft.com/action-center) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="fc858-155">Go to the [unified action center](https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="fc858-156">En la **pestaña** Historial, seleccione una acción que desee cambiar o deshacer.</span><span class="sxs-lookup"><span data-stu-id="fc858-156">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="fc858-157">En el panel de la parte derecha de la pantalla, seleccione la acción adecuada **(** mover a la bandeja de **entrada,** mover a correo no deseado **,** mover a elementos eliminados, eliminar temporalmente o eliminar de forma **permanente**).</span><span class="sxs-lookup"><span data-stu-id="fc858-157">In the pane on the right side of the screen, select the appropriate action (**move to inbox**, **move to junk**, **move to deleted items**, **soft delete**, or **hard delete**).</span></span>

## <a name="change-or-undo-through-the-office-action-center"></a><span data-ttu-id="fc858-158">Cambiar o deshacer a través del centro de Office acción</span><span class="sxs-lookup"><span data-stu-id="fc858-158">Change or undo through the Office action center</span></span>

1. <span data-ttu-id="fc858-159">Vaya al centro [de Office acción e](https://security.microsoft.com/threatincidents) inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="fc858-159">Go to the [Office action center](https://security.microsoft.com/threatincidents) and sign in.</span></span>
2. <span data-ttu-id="fc858-160">Seleccione la corrección adecuada.</span><span class="sxs-lookup"><span data-stu-id="fc858-160">Select the appropriate remediation.</span></span>
3. <span data-ttu-id="fc858-161">En el panel lateral, haga clic en la entrada envíos de correo y espere a que se cargue la lista.</span><span class="sxs-lookup"><span data-stu-id="fc858-161">In the side pane, click on the mail submissions entry and wait for the list to load.</span></span>
4. <span data-ttu-id="fc858-162">Espere a que el botón Acción de la parte superior habilite y seleccione el botón Acción para cambiar el tipo de acción.</span><span class="sxs-lookup"><span data-stu-id="fc858-162">Wait for the Action button at the top to enable and select the Action button to change the action type.</span></span>
5. <span data-ttu-id="fc858-163">Esto creará las acciones adecuadas.</span><span class="sxs-lookup"><span data-stu-id="fc858-163">This will create the appropriate actions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fc858-164">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fc858-164">Next steps</span></span>

- [<span data-ttu-id="fc858-165">Usar el Explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="fc858-165">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="fc858-166">Acciones de administrador /manual</span><span class="sxs-lookup"><span data-stu-id="fc858-166">Admin /Manual Actions</span></span>](remediate-malicious-email-delivered-office-365.md)
- [<span data-ttu-id="fc858-167">Cómo notificar falsos positivos/negativos en capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="fc858-167">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="fc858-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc858-168">See also</span></span>

- [<span data-ttu-id="fc858-169">Ver detalles y resultados de una investigación automatizada en Office 365</span><span class="sxs-lookup"><span data-stu-id="fc858-169">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
