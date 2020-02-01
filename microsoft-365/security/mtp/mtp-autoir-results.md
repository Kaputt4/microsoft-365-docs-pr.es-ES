---
title: Ver los detalles y los resultados de una investigación automatizada
description: Durante y después de una investigación automatizada, puede ver los resultados y los resultados clave
keywords: automatizada, investigación, resultados, analizar, detalles, corrección, autoair
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
ms.openlocfilehash: 208cbb49afc2f4520fa44a4ef283194bcaff22be
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600097"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a><span data-ttu-id="8b6f9-104">Ver los detalles y los resultados de una investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="8b6f9-104">View the details and results of an automated investigation</span></span>

<span data-ttu-id="8b6f9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8b6f9-105">**Applies to:**</span></span>
- <span data-ttu-id="8b6f9-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8b6f9-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8b6f9-107">Cuando se produce una investigación automatizada en la Protección contra amenazas de Microsoft, los detalles sobre esa investigación están disponibles durante y después del proceso de investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="8b6f9-108">Si tiene los [permisos necesarios](mtp-action-center.md#required-permissions-for-action-center-tasks), puede ver esos detalles en la vista de detalles de la investigación.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="8b6f9-109">La vista de detalles de la investigación ofrece un estado actualizado y la capacidad de aprobar las acciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Detalles de la investigación](../images/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="8b6f9-111">Abrir la vista de detalles de la investigación</span><span class="sxs-lookup"><span data-stu-id="8b6f9-111">Open the investigation details view</span></span>

<span data-ttu-id="8b6f9-112">Puede abrir un informe en la vista previa de impresión utilizando uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8b6f9-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="8b6f9-113">Seleccionar un elemento en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="8b6f9-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="8b6f9-114">Seleccionar una investigación en una página de detalles de un incidente</span><span class="sxs-lookup"><span data-stu-id="8b6f9-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="8b6f9-115">Seleccionar un elemento en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="8b6f9-115">Select an item in the Action center</span></span>

<span data-ttu-id="8b6f9-116">Use el centro de actividades para ver las acciones que estén pendientes de aprobación (en la pestaña **pendiente**) o que ya se hayan aprobado (en la pestaña **historial**).</span><span class="sxs-lookup"><span data-stu-id="8b6f9-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="8b6f9-117">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="8b6f9-118">En el panel de navegación, elija **Centro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="8b6f9-119">En la pestaña **pendiente** o **historial**, seleccione un elemento.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="8b6f9-120">Si tiene los [permisos necesarios](mtp-action-center.md#required-permissions-for-action-center-tasks), puede aprobar (o rechazar) acciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="8b6f9-121">Abrir una investigación desde una página de detalles de un incidente</span><span class="sxs-lookup"><span data-stu-id="8b6f9-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="8b6f9-122">Use una página de detalles de un incidente para ver información detallada sobre un incidente, incluidas las alertas que contenían información acerca de cualquier dispositivo, cuenta de usuario o buzón que les afecten.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="8b6f9-123">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="8b6f9-124">En el panel de navegación, elija **incidentes**.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="8b6f9-125">Seleccione un elemento de la lista para abrir la vista detalles del incidente.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-125">Select an item in the list to open the incident details view.</span></span><br/>![Detalles del incidente](../images/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="8b6f9-127">En la pestaña **investigaciones**, seleccione una investigación en la lista.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="8b6f9-128">Detalles de la investigación</span><span class="sxs-lookup"><span data-stu-id="8b6f9-128">Investigation details</span></span>

<span data-ttu-id="8b6f9-129">Use la vista detalles de la investigación para ver la actividad pasada, actual y pendiente relacionada con una investigación.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="8b6f9-130">La vista de detalles de la investigación es similar a la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="8b6f9-130">The investigation details view resembles the following image:</span></span>

![Detalles de la investigación](../images/mtp-air-investdetails.png)

<span data-ttu-id="8b6f9-132">En la vista de detalles de la investigación, puede ver información en las pestañas **gráfico de investigación**, **alertas**, **dispositivos**, **identidades**, **resultados clave**, **entidades**, **registro**, y **acciones pendientes**, que se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="8b6f9-133">Pestaña</span><span class="sxs-lookup"><span data-stu-id="8b6f9-133">Tab</span></span>    |<span data-ttu-id="8b6f9-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b6f9-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="8b6f9-135">Gráfico de investigación</span><span class="sxs-lookup"><span data-stu-id="8b6f9-135">Investigation graph</span></span>    |<span data-ttu-id="8b6f9-136">Proporciona una representación visual de la investigación.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="8b6f9-137">Se muestra una lista de las entidades y se muestran las amenazas, junto con las alertas y si hay acciones pendientes de aprobación.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="8b6f9-138">Puede hacer clic en un elemento del gráfico para ver más detalles.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="8b6f9-139">Por ejemplo, al hacer clic en el icono **amenazas detectadas** le llevará a la pestaña **resultados clave**.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="8b6f9-140">Alertas</span><span class="sxs-lookup"><span data-stu-id="8b6f9-140">Alerts</span></span> |<span data-ttu-id="8b6f9-141">Muestra las alertas relacionadas con la investigación.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="8b6f9-142">Las alertas pueden provenir de características de protección contra amenazas en el equipo de un usuario, en las aplicaciones de Office, Cloud App Security y otras características de Protección contra amenazas de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="8b6f9-143">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="8b6f9-143">Devices</span></span>|<span data-ttu-id="8b6f9-144">Muestra los equipos incluidos en la investigación junto con el nivel de corrección.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="8b6f9-145">Resultados clave</span><span class="sxs-lookup"><span data-stu-id="8b6f9-145">Key findings</span></span>   |<span data-ttu-id="8b6f9-146">Muestra los resultados de la investigación junto con el estado y las acciones tomadas o pendientes.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="8b6f9-147">Puede aprobar acciones pendientes para dispositivos e identidades en esta pestaña.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="8b6f9-148">Entidades</span><span class="sxs-lookup"><span data-stu-id="8b6f9-148">Entities</span></span>   |<span data-ttu-id="8b6f9-149">Muestra las actividades del usuario, archivos, procesos, servicios, controladores, direcciones IP y métodos de persistencia asociados con la investigación, junto con el estado y las acciones tomadas.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="8b6f9-150">Registro</span><span class="sxs-lookup"><span data-stu-id="8b6f9-150">Log</span></span>    |<span data-ttu-id="8b6f9-151">Ofrece una vista detallada de todos los pasos realizados durante la investigación, junto con el estado.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="8b6f9-152">Acciones pendientes</span><span class="sxs-lookup"><span data-stu-id="8b6f9-152">Pending actions</span></span>    |<span data-ttu-id="8b6f9-153">Muestra los elementos que necesitan aprobación para continuar.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-153">Lists items that require approval to proceed.</span></span>|

## <a name="remediation-actions-following-automated-investigation"></a><span data-ttu-id="8b6f9-154">Acciones correctivas que siguen a la investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="8b6f9-154">Remediation actions following automated investigation</span></span>

<span data-ttu-id="8b6f9-155">Cuando una investigación automatizada se completa, se llega a un veredicto para cada evidencia involucrada, y se identifican las acciones correctivas.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-155">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="8b6f9-156">En algunos casos, las acciones correctivas se toman automáticamente, en otros casos, las acciones correctivas esperan aprobación.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-156">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="8b6f9-157">En la tabla siguiente se muestran los posibles resultados:</span><span class="sxs-lookup"><span data-stu-id="8b6f9-157">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="8b6f9-158">Veredicto</span><span class="sxs-lookup"><span data-stu-id="8b6f9-158">Verdict</span></span>    |<span data-ttu-id="8b6f9-159">Área</span><span class="sxs-lookup"><span data-stu-id="8b6f9-159">Area</span></span>   |<span data-ttu-id="8b6f9-160">Resultados</span><span class="sxs-lookup"><span data-stu-id="8b6f9-160">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="8b6f9-161">Malintencionado</span><span class="sxs-lookup"><span data-stu-id="8b6f9-161">Malicious</span></span>  |<span data-ttu-id="8b6f9-162">Dispositivos (puntos de conexión)</span><span class="sxs-lookup"><span data-stu-id="8b6f9-162">Devices (endpoints)</span></span>    |<span data-ttu-id="8b6f9-163">Las acciones de corrección se toman automáticamente</span><span class="sxs-lookup"><span data-stu-id="8b6f9-163">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="8b6f9-164">Malintencionado</span><span class="sxs-lookup"><span data-stu-id="8b6f9-164">Malicious</span></span>  |<span data-ttu-id="8b6f9-165">Contenido de correo electrónico (URL y datos adjuntos)</span><span class="sxs-lookup"><span data-stu-id="8b6f9-165">Email content (URLs or attachments)</span></span> | <span data-ttu-id="8b6f9-166">Acciones de corrección recomendadas pendientes de aprobación</span><span class="sxs-lookup"><span data-stu-id="8b6f9-166">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="8b6f9-167">Sospechoso</span><span class="sxs-lookup"><span data-stu-id="8b6f9-167">Suspicious</span></span> |<span data-ttu-id="8b6f9-168">Dispositivos o contenido de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="8b6f9-168">Devices or email content</span></span> |<span data-ttu-id="8b6f9-169">Acciones de corrección recomendadas pendientes de aprobación</span><span class="sxs-lookup"><span data-stu-id="8b6f9-169">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="8b6f9-170">Limpiar</span><span class="sxs-lookup"><span data-stu-id="8b6f9-170">Clean</span></span>  |<span data-ttu-id="8b6f9-171">Dispositivos o contenido de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="8b6f9-171">Devices or email content</span></span>   |<span data-ttu-id="8b6f9-172">No es necesario realizar ninguna acción correctiva</span><span class="sxs-lookup"><span data-stu-id="8b6f9-172">No remediation actions are needed</span></span>|

[<span data-ttu-id="8b6f9-173">Revisar una acción pendiente en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="8b6f9-173">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="8b6f9-174">Si cree que algo ha perdido o detectado erróneamente las características de respuesta e investigación automatizada en la protección contra amenazas de Microsoft, háganoslo saber.</span><span class="sxs-lookup"><span data-stu-id="8b6f9-174">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="8b6f9-175">Consulte [Cómo informar de falsos positivos/negativos en capacidades de investigación y respuesta automatizadas (Air) en la protección contra amenazas de Microsoft](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="8b6f9-175">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8b6f9-176">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="8b6f9-176">Next steps</span></span>

- [<span data-ttu-id="8b6f9-177">Obtener una visión general de los permisos del centro de actividades</span><span class="sxs-lookup"><span data-stu-id="8b6f9-177">Get an overview of Action center permissions</span></span>](mtp-action-center.md#required-permissions-for-action-center-tasks)
- [<span data-ttu-id="8b6f9-178">Aprobar o rechazar acciones relacionadas con la investigación y la respuesta automatizadas</span><span class="sxs-lookup"><span data-stu-id="8b6f9-178">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

