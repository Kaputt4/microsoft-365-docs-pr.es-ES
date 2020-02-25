---
title: Detalles y resultados de una investigación automatizada
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
ms.openlocfilehash: 6b3bc068e5da99e02a64463891e32d137c448d64
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42261067"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="cc90c-104">Detalles y resultados de una investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="cc90c-104">Details and results of an automated investigation</span></span>

<span data-ttu-id="cc90c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="cc90c-105">**Applies to:**</span></span>
- <span data-ttu-id="cc90c-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="cc90c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="cc90c-107">Cuando se produce una investigación automatizada en la Protección contra amenazas de Microsoft, los detalles sobre esa investigación están disponibles durante y después del proceso de investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="cc90c-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="cc90c-108">Si tiene los [permisos necesarios](mtp-action-center.md#required-permissions-for-action-center-tasks), puede ver esos detalles en la vista de detalles de la investigación.</span><span class="sxs-lookup"><span data-stu-id="cc90c-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="cc90c-109">La vista de detalles de la investigación ofrece un estado actualizado y la capacidad de aprobar las acciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="cc90c-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Detalles de la investigación](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="cc90c-111">Abrir la vista de detalles de la investigación</span><span class="sxs-lookup"><span data-stu-id="cc90c-111">Open the investigation details view</span></span>

<span data-ttu-id="cc90c-112">Puede abrir un informe en la vista previa de impresión utilizando uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="cc90c-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="cc90c-113">Seleccionar un elemento en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="cc90c-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="cc90c-114">Seleccionar una investigación en una página de detalles de un incidente</span><span class="sxs-lookup"><span data-stu-id="cc90c-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="cc90c-115">Seleccionar un elemento en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="cc90c-115">Select an item in the Action center</span></span>

<span data-ttu-id="cc90c-116">Use el centro de actividades para ver las acciones que estén pendientes de aprobación (en la pestaña **pendiente**) o que ya se hayan aprobado (en la pestaña **historial**).</span><span class="sxs-lookup"><span data-stu-id="cc90c-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="cc90c-117">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="cc90c-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="cc90c-118">En el panel de navegación, elija **Centro de actividades**.</span><span class="sxs-lookup"><span data-stu-id="cc90c-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="cc90c-119">En la pestaña **pendiente** o **historial**, seleccione un elemento.</span><span class="sxs-lookup"><span data-stu-id="cc90c-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="cc90c-120">Si tiene los [permisos necesarios](mtp-action-center.md#required-permissions-for-action-center-tasks), puede aprobar (o rechazar) acciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="cc90c-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="cc90c-121">Abrir una investigación desde una página de detalles de un incidente</span><span class="sxs-lookup"><span data-stu-id="cc90c-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="cc90c-122">Use una página de detalles de un incidente para ver información detallada sobre un incidente, incluidas las alertas que contenían información acerca de cualquier dispositivo, cuenta de usuario o buzón que les afecten.</span><span class="sxs-lookup"><span data-stu-id="cc90c-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="cc90c-123">Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="cc90c-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="cc90c-124">En el panel de navegación, elija **incidentes**.</span><span class="sxs-lookup"><span data-stu-id="cc90c-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="cc90c-125">Seleccione un elemento de la lista para abrir la vista detalles del incidente.</span><span class="sxs-lookup"><span data-stu-id="cc90c-125">Select an item in the list to open the incident details view.</span></span><br/>![Detalles del incidente](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="cc90c-127">En la pestaña **investigaciones**, seleccione una investigación en la lista.</span><span class="sxs-lookup"><span data-stu-id="cc90c-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="cc90c-128">Detalles de la investigación</span><span class="sxs-lookup"><span data-stu-id="cc90c-128">Investigation details</span></span>

<span data-ttu-id="cc90c-129">Use la vista detalles de la investigación para ver la actividad pasada, actual y pendiente relacionada con una investigación.</span><span class="sxs-lookup"><span data-stu-id="cc90c-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="cc90c-130">La vista de detalles de la investigación es similar a la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="cc90c-130">The investigation details view resembles the following image:</span></span>

![Detalles de la investigación](../../media/mtp-air-investdetails.png)

<span data-ttu-id="cc90c-132">En la vista de detalles de la investigación, puede ver información en las pestañas **gráfico de investigación**, **alertas**, **dispositivos**, **identidades**, **resultados clave**, **entidades**, **registro**, y **acciones pendientes**, que se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="cc90c-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="cc90c-133">Pestaña</span><span class="sxs-lookup"><span data-stu-id="cc90c-133">Tab</span></span>    |<span data-ttu-id="cc90c-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc90c-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="cc90c-135">Gráfico de investigación</span><span class="sxs-lookup"><span data-stu-id="cc90c-135">Investigation graph</span></span>    |<span data-ttu-id="cc90c-136">Proporciona una representación visual de la investigación.</span><span class="sxs-lookup"><span data-stu-id="cc90c-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="cc90c-137">Se muestra una lista de las entidades y se muestran las amenazas, junto con las alertas y si hay acciones pendientes de aprobación.</span><span class="sxs-lookup"><span data-stu-id="cc90c-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="cc90c-138">Puede hacer clic en un elemento del gráfico para ver más detalles.</span><span class="sxs-lookup"><span data-stu-id="cc90c-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="cc90c-139">Por ejemplo, al hacer clic en el icono **amenazas detectadas** le llevará a la pestaña **resultados clave**.</span><span class="sxs-lookup"><span data-stu-id="cc90c-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="cc90c-140">Alertas</span><span class="sxs-lookup"><span data-stu-id="cc90c-140">Alerts</span></span> |<span data-ttu-id="cc90c-141">Muestra las alertas relacionadas con la investigación.</span><span class="sxs-lookup"><span data-stu-id="cc90c-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="cc90c-142">Las alertas pueden provenir de características de protección contra amenazas en el equipo de un usuario, en las aplicaciones de Office, Cloud App Security y otras características de Protección contra amenazas de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc90c-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="cc90c-143">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="cc90c-143">Devices</span></span>|<span data-ttu-id="cc90c-144">Muestra los equipos incluidos en la investigación junto con el nivel de corrección.</span><span class="sxs-lookup"><span data-stu-id="cc90c-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="cc90c-145">Resultados clave</span><span class="sxs-lookup"><span data-stu-id="cc90c-145">Key findings</span></span>   |<span data-ttu-id="cc90c-146">Muestra los resultados de la investigación junto con el estado y las acciones tomadas o pendientes.</span><span class="sxs-lookup"><span data-stu-id="cc90c-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="cc90c-147">Puede aprobar acciones pendientes para dispositivos e identidades en esta pestaña.</span><span class="sxs-lookup"><span data-stu-id="cc90c-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="cc90c-148">Entidades</span><span class="sxs-lookup"><span data-stu-id="cc90c-148">Entities</span></span>   |<span data-ttu-id="cc90c-149">Muestra las actividades del usuario, archivos, procesos, servicios, controladores, direcciones IP y métodos de persistencia asociados con la investigación, junto con el estado y las acciones tomadas.</span><span class="sxs-lookup"><span data-stu-id="cc90c-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="cc90c-150">Registro</span><span class="sxs-lookup"><span data-stu-id="cc90c-150">Log</span></span>    |<span data-ttu-id="cc90c-151">Ofrece una vista detallada de todos los pasos realizados durante la investigación, junto con el estado.</span><span class="sxs-lookup"><span data-stu-id="cc90c-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="cc90c-152">Acciones pendientes</span><span class="sxs-lookup"><span data-stu-id="cc90c-152">Pending actions</span></span>    |<span data-ttu-id="cc90c-153">Muestra los elementos que necesitan aprobación para continuar.</span><span class="sxs-lookup"><span data-stu-id="cc90c-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="cc90c-154">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="cc90c-154">Next steps</span></span>

- [<span data-ttu-id="cc90c-155">Obtener una visión general de los permisos del centro de actividades</span><span class="sxs-lookup"><span data-stu-id="cc90c-155">Get an overview of Action center permissions</span></span>](mtp-action-center.md#required-permissions-for-action-center-tasks)

- [<span data-ttu-id="cc90c-156">Aprobar o rechazar acciones relacionadas con la investigación y la respuesta automatizadas</span><span class="sxs-lookup"><span data-stu-id="cc90c-156">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

