---
title: Revisar y administrar acciones correctivas en Microsoft Defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.date: 01/29/2021
ms.openlocfilehash: bcff8f12133ea16e3d91e293943be1593eaf9659
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142698"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="5b7d9-104">Revisar y administrar acciones de corrección en Office 365</span><span class="sxs-lookup"><span data-stu-id="5b7d9-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="5b7d9-105">A medida que las investigaciones automatizadas en el correo & contenido de colaboración resultan en veredictos, como *malintencionados* o *sospechosos,* se crean determinadas acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="5b7d9-106">En Microsoft Defender para Office 365, las acciones de corrección pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="5b7d9-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="5b7d9-107">Bloqueo de una dirección URL (tiempo de clic)</span><span class="sxs-lookup"><span data-stu-id="5b7d9-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="5b7d9-108">Eliminación de mensajes de correo electrónico o clústeres de forma flexible</span><span class="sxs-lookup"><span data-stu-id="5b7d9-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="5b7d9-109">Quarantining email or email attachments</span><span class="sxs-lookup"><span data-stu-id="5b7d9-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="5b7d9-110">Desactivar el reenvío de correo externo</span><span class="sxs-lookup"><span data-stu-id="5b7d9-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="5b7d9-111">Estas acciones de corrección no se toman a menos que el equipo de operaciones de seguridad las apruebe y hasta que el equipo de operaciones de seguridad las apruebe.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="5b7d9-112">Se recomienda revisar y aprobar las acciones pendientes lo antes posible para que las investigaciones automatizadas se completen de forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="5b7d9-113">En algunos casos, puede deshacer una acción de corrección.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-113">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="5b7d9-114">Aprobar (o rechazar) acciones pendientes</span><span class="sxs-lookup"><span data-stu-id="5b7d9-114">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="5b7d9-115">Vaya al Centro de seguridad de Microsoft 365) [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-115">Go to the Microsoft 365 security center [https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="5b7d9-116">En el panel de navegación, seleccione **Centro de acciones.**</span><span class="sxs-lookup"><span data-stu-id="5b7d9-116">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="5b7d9-117">En la **pestaña** Pendiente, revisa la lista de acciones que están a la espera de su aprobación.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-117">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="5b7d9-118">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-118">Select an item in the list.</span></span> <span data-ttu-id="5b7d9-119">Se abre el panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-119">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="5b7d9-120">Revise la información del panel desplegable y, a continuación, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5b7d9-120">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="5b7d9-121">Seleccione **abrir la página de investigación** para ver más detalles sobre la investigación.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-121">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="5b7d9-122">Seleccione **Aprobar** para iniciar una acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-122">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="5b7d9-123">Seleccione **Rechazar** para evitar que se haga una acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-123">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="5b7d9-124">Deshacer una acción de corrección</span><span class="sxs-lookup"><span data-stu-id="5b7d9-124">Undo one remediation action</span></span>

1. <span data-ttu-id="5b7d9-125">Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-125">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="5b7d9-126">En la **pestaña** Historial, seleccione una acción que desee deshacer.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-126">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="5b7d9-127">En el panel del lado derecho de la pantalla, seleccione **Deshacer**.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-127">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="5b7d9-128">Deshacer varias acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="5b7d9-128">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="5b7d9-129">Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-129">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="5b7d9-130">En la **pestaña** Historial, seleccione las acciones que desea deshacer.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-130">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="5b7d9-131">Asegúrese de seleccionar los elementos que tienen el mismo tipo de acción.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-131">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="5b7d9-132">Se abre un panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-132">A flyout pane opens.</span></span>
3. <span data-ttu-id="5b7d9-133">En el panel desplegable, seleccione Deshacer.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-133">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="5b7d9-134">Para quitar un archivo de la cuarentena en varios dispositivos</span><span class="sxs-lookup"><span data-stu-id="5b7d9-134">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="5b7d9-135">Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-135">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="5b7d9-136">En la **pestaña** Historial, seleccione un archivo que tenga el tipo de acción **Quarantine file**.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-136">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="5b7d9-137">En el panel del lado derecho de la pantalla, seleccione Aplicar a **X más** instancias de este archivo y, a continuación, **seleccione Deshacer**.</span><span class="sxs-lookup"><span data-stu-id="5b7d9-137">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5b7d9-138">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="5b7d9-138">Next steps</span></span>

- [<span data-ttu-id="5b7d9-139">Usar el Explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="5b7d9-139">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="5b7d9-140">Cómo notificar falsos positivos/negativos en las capacidades automatizadas de investigación y respuesta</span><span class="sxs-lookup"><span data-stu-id="5b7d9-140">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="5b7d9-141">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5b7d9-141">See also</span></span>

- [<span data-ttu-id="5b7d9-142">Ver detalles y resultados de una investigación automatizada en Office 365</span><span class="sxs-lookup"><span data-stu-id="5b7d9-142">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
