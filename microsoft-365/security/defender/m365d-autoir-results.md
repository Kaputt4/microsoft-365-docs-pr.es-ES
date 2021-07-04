---
title: Detalles y resultados de una investigación automatizada
description: Ver los resultados y los resultados clave de la investigación automatizada en Microsoft 365 Defender
keywords: automatizada, investigación, resultados, analizar, detalles, corrección, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2cc83e24d4dd81c9d2e972fa274b48fc3946532a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289732"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="bddb5-104">Detalles y resultados de una investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="bddb5-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bddb5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bddb5-105">**Applies to:**</span></span>
- <span data-ttu-id="bddb5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bddb5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bddb5-107">Con Microsoft 365 Defender, cuando [se](m365d-autoir.md) ejecuta una investigación automatizada, los detalles sobre esa investigación están disponibles durante y después del proceso de investigación automatizado.</span><span class="sxs-lookup"><span data-stu-id="bddb5-107">With Microsoft 365 Defender, when an [automated investigation](m365d-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="bddb5-108">Si tiene los [permisos necesarios](m365d-action-center.md#required-permissions-for-action-center-tasks), puede ver esos detalles en la vista de detalles de la investigación.</span><span class="sxs-lookup"><span data-stu-id="bddb5-108">If you have the [necessary permissions](m365d-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="bddb5-109">Esta vista le proporciona el estado actualizado y la capacidad de aprobar cualquier acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="bddb5-109">This view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Detalles de la investigación":::

## <a name="new-unified-investigation-page"></a><span data-ttu-id="bddb5-111">(¡NUEVO!) Página de investigación unificada</span><span class="sxs-lookup"><span data-stu-id="bddb5-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="bddb5-112">La página de investigación se actualizó recientemente para incluir información en los dispositivos, el correo electrónico y el contenido de colaboración.</span><span class="sxs-lookup"><span data-stu-id="bddb5-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="bddb5-113">La nueva página de investigación unificada define un idioma común y proporciona una experiencia unificada para las investigaciones automáticas en [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para endpoint y Microsoft Defender [para Office 365](../office-365-security/defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="bddb5-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md).</span></span> <span data-ttu-id="bddb5-114">Para acceder a la página de investigación unificada, seleccione el vínculo en el banner amarillo que verá en:</span><span class="sxs-lookup"><span data-stu-id="bddb5-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>

- <span data-ttu-id="bddb5-115">Cualquier página de investigación en el Centro Office 365 seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="bddb5-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="bddb5-116">Cualquier página de investigación del Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="bddb5-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="bddb5-117">Cualquier incidente o experiencia del Centro de acciones en el portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) )</span><span class="sxs-lookup"><span data-stu-id="bddb5-117">Any incident or Action center experience in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="bddb5-118">Abrir la vista de detalles de la investigación</span><span class="sxs-lookup"><span data-stu-id="bddb5-118">Open the investigation details view</span></span>

<span data-ttu-id="bddb5-119">Puede abrir un informe en la vista previa de impresión utilizando uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bddb5-119">You can open the investigation details view by using one of the following methods:</span></span>

- [<span data-ttu-id="bddb5-120">Seleccionar un elemento en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="bddb5-120">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="bddb5-121">Seleccionar una investigación en una página de detalles de un incidente</span><span class="sxs-lookup"><span data-stu-id="bddb5-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="bddb5-122">Seleccionar un elemento en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="bddb5-122">Select an item in the Action center</span></span>

<span data-ttu-id="bddb5-123">El Centro [de acción](m365d-action-center.md) mejorado ( ) reúne acciones de corrección en todos los dispositivos, correo electrónico & contenido de colaboración e [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) [](m365d-remediation-actions.md) identidades.</span><span class="sxs-lookup"><span data-stu-id="bddb5-123">The improved [Action center](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](m365d-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="bddb5-124">Las acciones enumeradas incluyen acciones de corrección que se realizaron de forma automática o manual.</span><span class="sxs-lookup"><span data-stu-id="bddb5-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="bddb5-125">En el Centro de acciones, puede ver las acciones que están esperando la aprobación y las acciones que ya se aprobaron o completaron.</span><span class="sxs-lookup"><span data-stu-id="bddb5-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="bddb5-126">También puede navegar a más detalles, como una página de investigación.</span><span class="sxs-lookup"><span data-stu-id="bddb5-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="bddb5-127">Debe tener [ciertos permisos para](m365d-action-center.md#required-permissions-for-action-center-tasks) aprobar, rechazar o deshacer acciones.</span><span class="sxs-lookup"><span data-stu-id="bddb5-127">You must have [certain permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="bddb5-128">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="bddb5-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="bddb5-129">En el panel de navegación, elija **Centro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="bddb5-129">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="bddb5-130">En la pestaña **pendiente** o **historial**, seleccione un elemento.</span><span class="sxs-lookup"><span data-stu-id="bddb5-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="bddb5-131">Se abre el panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="bddb5-131">Its flyout pane opens.</span></span>

4. <span data-ttu-id="bddb5-132">Revise la información del panel desplegable y, a continuación, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bddb5-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="bddb5-133">Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.</span><span class="sxs-lookup"><span data-stu-id="bddb5-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="bddb5-134">Seleccione **Aprobar** para iniciar una acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="bddb5-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="bddb5-135">Seleccione **Rechazar** para evitar que se haga una acción pendiente.</span><span class="sxs-lookup"><span data-stu-id="bddb5-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="bddb5-136">Seleccione **Ir a la búsqueda** para ir a Búsqueda [avanzada.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bddb5-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="bddb5-137">Abrir una investigación desde una página de detalles de un incidente</span><span class="sxs-lookup"><span data-stu-id="bddb5-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="bddb5-138">Use una página de detalles de un incidente para ver información detallada sobre un incidente, incluidas las alertas que contenían información acerca de cualquier dispositivo, cuenta de usuario o buzón que les afecten.</span><span class="sxs-lookup"><span data-stu-id="bddb5-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="bddb5-139">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="bddb5-139">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="bddb5-140">En el panel de navegación, elija **Incidentes &**  >  **alertas incidentes**.</span><span class="sxs-lookup"><span data-stu-id="bddb5-140">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 

3. <span data-ttu-id="bddb5-141">Seleccione un elemento de la lista y, a continuación, elija **Abrir página de incidentes**.</span><span class="sxs-lookup"><span data-stu-id="bddb5-141">Select an item in the list, and then choose **Open incident page**.</span></span>

4. <span data-ttu-id="bddb5-142">Seleccione la **pestaña Investigaciones** y, a continuación, seleccione una investigación en la lista.</span><span class="sxs-lookup"><span data-stu-id="bddb5-142">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="bddb5-143">Se abre el panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="bddb5-143">Its flyout pane opens.</span></span>

5. <span data-ttu-id="bddb5-144">Seleccione **Abrir página de investigación**.</span><span class="sxs-lookup"><span data-stu-id="bddb5-144">Select **Open investigation page**.</span></span> 

<span data-ttu-id="bddb5-145">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bddb5-145">Here's an example.</span></span>

:::image type="content" source="../../media/mtp-incidentdetails-tabs.png" alt-text="Detalles del incidente":::

## <a name="investigation-details"></a><span data-ttu-id="bddb5-147">Detalles de la investigación</span><span class="sxs-lookup"><span data-stu-id="bddb5-147">Investigation details</span></span>

<span data-ttu-id="bddb5-148">Use la vista detalles de la investigación para ver la actividad pasada, actual y pendiente relacionada con una investigación.</span><span class="sxs-lookup"><span data-stu-id="bddb5-148">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="bddb5-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bddb5-149">Here's an example.</span></span>

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Detalles de la investigación":::

<span data-ttu-id="bddb5-151">En la vista de detalles de la investigación, puede ver información en las pestañas **gráfico de investigación**, **alertas**, **dispositivos**, **identidades**, **resultados clave**, **entidades**, **registro**, y **acciones pendientes**, que se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="bddb5-151">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="bddb5-152">Las pestañas específicas que se ven en una página de detalles de investigación dependen de lo que incluya la suscripción.</span><span class="sxs-lookup"><span data-stu-id="bddb5-152">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="bddb5-153">Por ejemplo, si su suscripción no incluye Microsoft Defender para Office 365 plan 2, no verá una pestaña **Buzones.**</span><span class="sxs-lookup"><span data-stu-id="bddb5-153">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="bddb5-154">Pestaña</span><span class="sxs-lookup"><span data-stu-id="bddb5-154">Tab</span></span> | <span data-ttu-id="bddb5-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="bddb5-155">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="bddb5-156">**Gráfico de investigación**</span><span class="sxs-lookup"><span data-stu-id="bddb5-156">**Investigation graph**</span></span> | <span data-ttu-id="bddb5-157">Proporciona una representación visual de la investigación.</span><span class="sxs-lookup"><span data-stu-id="bddb5-157">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="bddb5-158">Se muestra una lista de las entidades y se muestran las amenazas, junto con las alertas y si hay acciones pendientes de aprobación.</span><span class="sxs-lookup"><span data-stu-id="bddb5-158">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="bddb5-159">Puede seleccionar un elemento en el gráfico para ver más detalles.</span><span class="sxs-lookup"><span data-stu-id="bddb5-159">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="bddb5-160">Por ejemplo, al seleccionar el icono  **Evidencia,** te llevará a la pestaña Evidencia, donde puedes ver las entidades detectadas y sus veredictos.</span><span class="sxs-lookup"><span data-stu-id="bddb5-160">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="bddb5-161">**Alertas**</span><span class="sxs-lookup"><span data-stu-id="bddb5-161">**Alerts**</span></span> | <span data-ttu-id="bddb5-162">Muestra las alertas relacionadas con la investigación.</span><span class="sxs-lookup"><span data-stu-id="bddb5-162">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="bddb5-163">Las alertas pueden venir de características de protección contra amenazas en el dispositivo de un usuario, en aplicaciones Office, Microsoft Cloud App Security y otras características Microsoft 365 Defender usuario.</span><span class="sxs-lookup"><span data-stu-id="bddb5-163">Alerts can come from threat protection features on a user's device, in Office apps, Microsoft Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="bddb5-164">**Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="bddb5-164">**Devices**</span></span> | <span data-ttu-id="bddb5-165">Enumera los dispositivos incluidos en la investigación junto con su nivel de corrección.</span><span class="sxs-lookup"><span data-stu-id="bddb5-165">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="bddb5-166">(Los niveles de corrección corresponden [al nivel de automatización de los grupos de dispositivos](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)).)</span><span class="sxs-lookup"><span data-stu-id="bddb5-166">(Remediation levels correspond to [the automation level for device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="bddb5-167">**Buzones**</span><span class="sxs-lookup"><span data-stu-id="bddb5-167">**Mailboxes**</span></span> |<span data-ttu-id="bddb5-168">Enumera los buzones que se verán afectados por las amenazas detectadas.</span><span class="sxs-lookup"><span data-stu-id="bddb5-168">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="bddb5-169">**Users**</span><span class="sxs-lookup"><span data-stu-id="bddb5-169">**Users**</span></span>  | <span data-ttu-id="bddb5-170">Enumera las cuentas de usuario afectadas por las amenazas detectadas.</span><span class="sxs-lookup"><span data-stu-id="bddb5-170">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="bddb5-171">**Evidencia**</span><span class="sxs-lookup"><span data-stu-id="bddb5-171">**Evidence**</span></span> | <span data-ttu-id="bddb5-172">Enumera partes de pruebas generadas por alertas o investigaciones.</span><span class="sxs-lookup"><span data-stu-id="bddb5-172">Lists pieces of evidence raised by alerts or investigations.</span></span> <span data-ttu-id="bddb5-173">Incluye veredictos ( Malintencionado , *Sospechoso*, Desconocido o *Sin* amenazas encontradas ) y estado de corrección.</span><span class="sxs-lookup"><span data-stu-id="bddb5-173">Includes verdicts (*Malicious*, *Suspicious*, *Unknown*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="bddb5-174">**Entities**</span><span class="sxs-lookup"><span data-stu-id="bddb5-174">**Entities**</span></span> | <span data-ttu-id="bddb5-175">Proporciona detalles sobre cada entidad analizada, incluido un veredicto para cada tipo de entidad ( Malintencionada , *Sospechosa* o *Sin amenazas encontradas*).</span><span class="sxs-lookup"><span data-stu-id="bddb5-175">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="bddb5-176">**Log**</span><span class="sxs-lookup"><span data-stu-id="bddb5-176">**Log**</span></span> | <span data-ttu-id="bddb5-177">Proporciona una vista cronológica y detallada de todas las acciones de investigación realizadas después de desencadenar una alerta.</span><span class="sxs-lookup"><span data-stu-id="bddb5-177">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="bddb5-178">**Historial de acciones pendientes**</span><span class="sxs-lookup"><span data-stu-id="bddb5-178">**Pending actions history**</span></span> | <span data-ttu-id="bddb5-179">Muestra los elementos que necesitan aprobación para continuar.</span><span class="sxs-lookup"><span data-stu-id="bddb5-179">Lists items that require approval to proceed.</span></span> <span data-ttu-id="bddb5-180">Vaya al Centro de acciones ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) para aprobar acciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="bddb5-180">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="bddb5-181">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="bddb5-181">Next steps</span></span>

- [<span data-ttu-id="bddb5-182">Ver y aprobar acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="bddb5-182">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="bddb5-183">Más información sobre las acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="bddb5-183">Learn more about remediation actions</span></span>](m365d-remediation-actions.md)
