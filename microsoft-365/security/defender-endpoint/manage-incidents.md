---
title: Administrar Microsoft Defender para incidentes de punto de conexión
description: Administre los incidentes asignándolas, actualizando su estado o estableciendo su clasificación.
keywords: incidentes, administrar, asignar, estado, clasificación, alerta verdadera, alerta falsa
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: abb538972b48f8790286c0a546eecdd69fc83fb5
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862144"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="59037-104">Administrar Microsoft Defender para incidentes de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="59037-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="59037-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="59037-105">**Applies to:**</span></span>
- [<span data-ttu-id="59037-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="59037-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="59037-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59037-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="59037-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="59037-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="59037-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="59037-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="59037-110">La administración de incidentes es una parte importante de todas las operaciones de ciberseguridad.</span><span class="sxs-lookup"><span data-stu-id="59037-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="59037-111">Puede administrar incidentes seleccionando un incidente en la cola Incidentes **o** en el panel de **administración incidentes.**</span><span class="sxs-lookup"><span data-stu-id="59037-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="59037-112">Al seleccionar un incidente de la cola **Incidentes,** se abre el panel **Administración** de incidentes, donde puede abrir la página de incidentes para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="59037-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![Imagen del panel de administración de incidentes](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="59037-114">Puedes asignar incidentes a ti mismo, cambiar el estado y la clasificación, cambiar el nombre o comentarlos para realizar un seguimiento de su progreso.</span><span class="sxs-lookup"><span data-stu-id="59037-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="59037-115">Para obtener visibilidad adicional de un vistazo, los nombres de incidentes se generan automáticamente en función de los atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías.</span><span class="sxs-lookup"><span data-stu-id="59037-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="59037-116">Esto le permite comprender rápidamente el ámbito del incidente.</span><span class="sxs-lookup"><span data-stu-id="59037-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="59037-117">Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*</span><span class="sxs-lookup"><span data-stu-id="59037-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="59037-118">Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes conservarán sus nombres.</span><span class="sxs-lookup"><span data-stu-id="59037-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![Imagen de la página de detalles de incidentes](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="59037-120">Asignar incidentes</span><span class="sxs-lookup"><span data-stu-id="59037-120">Assign incidents</span></span>
<span data-ttu-id="59037-121">Si aún no se ha asignado un incidente, puedes seleccionar **Asignarme** para asignarte el incidente.</span><span class="sxs-lookup"><span data-stu-id="59037-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="59037-122">Esta asignación no incluye solo el incidente, sino también todas las alertas asociadas a él.</span><span class="sxs-lookup"><span data-stu-id="59037-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="59037-123">Establecer estado y clasificación</span><span class="sxs-lookup"><span data-stu-id="59037-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="59037-124">Estado del incidente</span><span class="sxs-lookup"><span data-stu-id="59037-124">Incident status</span></span>
<span data-ttu-id="59037-125">Puede categorizar los incidentes (por ejemplo, como **Activo** o **Resuelto**) cambiando su estado a medida que progresa la investigación.</span><span class="sxs-lookup"><span data-stu-id="59037-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="59037-126">Esto le ayuda a organizar y administrar la forma en que su equipo puede responder a incidencias.</span><span class="sxs-lookup"><span data-stu-id="59037-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="59037-127">Por ejemplo, el analista de SoC puede revisar los incidentes **activos** urgentes del día y decidir asignarlos a sí mismo para su investigación.</span><span class="sxs-lookup"><span data-stu-id="59037-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="59037-128">Como alternativa, el analista de SoC puede establecer el incidente como **Resuelto** si se ha corregido el incidente.</span><span class="sxs-lookup"><span data-stu-id="59037-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="59037-129">Clasificación</span><span class="sxs-lookup"><span data-stu-id="59037-129">Classification</span></span>
<span data-ttu-id="59037-130">Si lo desea, puede decidir no establecer ninguna clasificación o especificar si un incidente es verdadero o falso.</span><span class="sxs-lookup"><span data-stu-id="59037-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="59037-131">Al hacerlo, su equipo podrá ver los patrones y obtener información.</span><span class="sxs-lookup"><span data-stu-id="59037-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="59037-132">Agregar comentarios</span><span class="sxs-lookup"><span data-stu-id="59037-132">Add comments</span></span>
<span data-ttu-id="59037-133">Puede agregar comentarios y ver eventos históricos de un incidente para comprobar los cambios ya realizados.</span><span class="sxs-lookup"><span data-stu-id="59037-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="59037-134">Siempre que se realice un cambio o comentario en una alerta, esta se registra en la sección Comentarios e historial.</span><span class="sxs-lookup"><span data-stu-id="59037-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="59037-135">Los comentarios agregados aparecen al instante en el panel.</span><span class="sxs-lookup"><span data-stu-id="59037-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="59037-136">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="59037-136">Related topics</span></span>
- [<span data-ttu-id="59037-137">Cola de incidentes</span><span class="sxs-lookup"><span data-stu-id="59037-137">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="59037-138">Ver y organizar la cola de incidentes</span><span class="sxs-lookup"><span data-stu-id="59037-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="59037-139">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="59037-139">Investigate incidents</span></span>](investigate-incidents.md)
