---
title: Ver y organizar la cola de incidentes
ms.reviewer: ''
description: Consulta la lista de incidentes y aprende a aplicar filtros para limitar la lista y obtener una vista más centrada.
keywords: ver, organizar, incidentes, agregados, investigaciones, cola, ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56fd5aa10cf30e7bdcad213a68430b460e65647c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844231"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="b2e28-104">Ver y organizar la cola de Microsoft Defender para incidentes de extremo</span><span class="sxs-lookup"><span data-stu-id="b2e28-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b2e28-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b2e28-105">**Applies to:**</span></span>
- [<span data-ttu-id="b2e28-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b2e28-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b2e28-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2e28-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b2e28-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b2e28-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b2e28-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b2e28-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="b2e28-110">La **cola Incidentes muestra** una colección de incidentes marcados desde dispositivos de la red.</span><span class="sxs-lookup"><span data-stu-id="b2e28-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="b2e28-111">Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.</span><span class="sxs-lookup"><span data-stu-id="b2e28-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="b2e28-112">De forma predeterminada, la cola muestra incidentes vistos en los últimos 30 días, con el incidente más reciente que aparece en la parte superior de la lista, lo que le ayuda a ver primero los incidentes más recientes.</span><span class="sxs-lookup"><span data-stu-id="b2e28-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="b2e28-113">Hay varias opciones entre las que puede elegir para personalizar la vista de cola Incidentes.</span><span class="sxs-lookup"><span data-stu-id="b2e28-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="b2e28-114">En la navegación superior puede:</span><span class="sxs-lookup"><span data-stu-id="b2e28-114">On the top navigation you can:</span></span>
- <span data-ttu-id="b2e28-115">Personalizar columnas para agregar o quitar columnas</span><span class="sxs-lookup"><span data-stu-id="b2e28-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="b2e28-116">Modificar el número de elementos que se verán por página</span><span class="sxs-lookup"><span data-stu-id="b2e28-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="b2e28-117">Seleccionar los elementos que se mostrarán por página</span><span class="sxs-lookup"><span data-stu-id="b2e28-117">Select the items to show per page</span></span>
- <span data-ttu-id="b2e28-118">Selección por lotes de los incidentes que se asignarán</span><span class="sxs-lookup"><span data-stu-id="b2e28-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="b2e28-119">Navegar entre páginas</span><span class="sxs-lookup"><span data-stu-id="b2e28-119">Navigate between pages</span></span>
- <span data-ttu-id="b2e28-120">Aplicar filtros</span><span class="sxs-lookup"><span data-stu-id="b2e28-120">Apply filters</span></span>

![Imagen de cola de incidentes](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="b2e28-122">Ordenar y filtrar la cola de incidentes</span><span class="sxs-lookup"><span data-stu-id="b2e28-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="b2e28-123">Puede aplicar los siguientes filtros para limitar la lista de incidentes y obtener una vista más centrada.</span><span class="sxs-lookup"><span data-stu-id="b2e28-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="b2e28-124">Gravedad</span><span class="sxs-lookup"><span data-stu-id="b2e28-124">Severity</span></span>

<span data-ttu-id="b2e28-125">Gravedad del incidente</span><span class="sxs-lookup"><span data-stu-id="b2e28-125">Incident severity</span></span> | <span data-ttu-id="b2e28-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2e28-126">Description</span></span>
:---|:---
<span data-ttu-id="b2e28-127">Alto</span><span class="sxs-lookup"><span data-stu-id="b2e28-127">High</span></span> </br><span data-ttu-id="b2e28-128">(Rojo)</span><span class="sxs-lookup"><span data-stu-id="b2e28-128">(Red)</span></span> | <span data-ttu-id="b2e28-129">Amenazas asociadas a menudo con amenazas persistentes avanzadas (APT).</span><span class="sxs-lookup"><span data-stu-id="b2e28-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="b2e28-130">Estos incidentes indican un alto riesgo debido a la gravedad de los daños que pueden causar en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b2e28-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="b2e28-131">Medio</span><span class="sxs-lookup"><span data-stu-id="b2e28-131">Medium</span></span> </br><span data-ttu-id="b2e28-132">(Naranja)</span><span class="sxs-lookup"><span data-stu-id="b2e28-132">(Orange)</span></span> | <span data-ttu-id="b2e28-133">Las amenazas rara vez se observan en la organización, como cambios anómalos en el Registro, ejecución de archivos sospechosos y comportamientos observados típicos de fases de ataque.</span><span class="sxs-lookup"><span data-stu-id="b2e28-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="b2e28-134">Bajo</span><span class="sxs-lookup"><span data-stu-id="b2e28-134">Low</span></span> </br><span data-ttu-id="b2e28-135">(Amarillo)</span><span class="sxs-lookup"><span data-stu-id="b2e28-135">(Yellow)</span></span> | <span data-ttu-id="b2e28-136">Amenazas asociadas con malware y herramientas de piratería que no indican necesariamente una amenaza avanzada dirigida a la organización.</span><span class="sxs-lookup"><span data-stu-id="b2e28-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="b2e28-137">Informativo</span><span class="sxs-lookup"><span data-stu-id="b2e28-137">Informational</span></span> </br><span data-ttu-id="b2e28-138">(Gris)</span><span class="sxs-lookup"><span data-stu-id="b2e28-138">(Grey)</span></span> | <span data-ttu-id="b2e28-139">Es posible que los incidentes informativos no se consideren perjudiciales para la red, pero podrían ser buenos para realizar un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b2e28-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="b2e28-140">Asignado a</span><span class="sxs-lookup"><span data-stu-id="b2e28-140">Assigned to</span></span>
<span data-ttu-id="b2e28-141">Puede filtrar la lista seleccionando los incidentes asignados a cualquiera o solo los asignados a su usuario.</span><span class="sxs-lookup"><span data-stu-id="b2e28-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="b2e28-142">Categoría</span><span class="sxs-lookup"><span data-stu-id="b2e28-142">Category</span></span>
<span data-ttu-id="b2e28-143">Los incidentes se clasifican en función de la descripción de la fase en la que se encuentra la cadena de eliminación de ciberseguridad.</span><span class="sxs-lookup"><span data-stu-id="b2e28-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="b2e28-144">Esta vista ayuda al analista de amenazas a determinar la prioridad, la urgencia y la estrategia de respuesta correspondiente para implementar en función del contexto.</span><span class="sxs-lookup"><span data-stu-id="b2e28-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="b2e28-145">Estado</span><span class="sxs-lookup"><span data-stu-id="b2e28-145">Status</span></span>
<span data-ttu-id="b2e28-146">Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos.</span><span class="sxs-lookup"><span data-stu-id="b2e28-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="b2e28-147">Confidencialidad de datos</span><span class="sxs-lookup"><span data-stu-id="b2e28-147">Data sensitivity</span></span>
<span data-ttu-id="b2e28-148">Use este filtro para mostrar incidentes que contienen etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="b2e28-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="b2e28-149">Nomenclatura de incidentes</span><span class="sxs-lookup"><span data-stu-id="b2e28-149">Incident naming</span></span>

<span data-ttu-id="b2e28-150">Para comprender el ámbito del incidente de un vistazo, los nombres de incidentes se generan automáticamente en función de los atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías.</span><span class="sxs-lookup"><span data-stu-id="b2e28-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="b2e28-151">Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*</span><span class="sxs-lookup"><span data-stu-id="b2e28-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="b2e28-152">Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes conservarán su nombre.</span><span class="sxs-lookup"><span data-stu-id="b2e28-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="b2e28-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2e28-153">See also</span></span>
- [<span data-ttu-id="b2e28-154">Cola de incidentes</span><span class="sxs-lookup"><span data-stu-id="b2e28-154">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="b2e28-155">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="b2e28-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="b2e28-156">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="b2e28-156">Investigate incidents</span></span>](investigate-incidents.md)

