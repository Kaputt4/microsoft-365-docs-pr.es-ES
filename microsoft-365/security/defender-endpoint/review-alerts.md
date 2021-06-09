---
title: Revisar alertas en Microsoft Defender para endpoint
description: Revise la información de alerta, incluido un artículo de alerta visualizado y detalles para cada paso de la cadena.
keywords: incidente, incidentes, máquinas, dispositivos, usuarios, alertas, alertas, investigación, gráfico, evidencia
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b17af7931b181a5fa30271a3eee07c7abf10a010
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844027"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="7017c-104">Revisar alertas en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="7017c-104">Review alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7017c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7017c-105">**Applies to:**</span></span>
- [<span data-ttu-id="7017c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7017c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="7017c-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7017c-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7017c-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="7017c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="7017c-109">La página de alertas de Microsoft Defender para endpoint proporciona un contexto completo a la alerta, mediante la combinación de señales de ataque y alertas relacionadas con la alerta seleccionada, para crear un artículo de alerta detallado.</span><span class="sxs-lookup"><span data-stu-id="7017c-109">The alert page in Microsoft Defender for Endpoint provides full context to the alert, by combining attack signals and alerts related to the selected alert, to construct a detailed alert story.</span></span>

<span data-ttu-id="7017c-110">Triage, investigue y tome medidas eficaces rápidamente en las alertas que afectan a su organización.</span><span class="sxs-lookup"><span data-stu-id="7017c-110">Quickly triage, investigate, and take effective action on alerts that affect your organization.</span></span> <span data-ttu-id="7017c-111">Comprenda por qué se desencadenaron y su impacto desde una ubicación.</span><span class="sxs-lookup"><span data-stu-id="7017c-111">Understand why they were triggered, and their impact from one location.</span></span> <span data-ttu-id="7017c-112">Obtenga más información en esta introducción.</span><span class="sxs-lookup"><span data-stu-id="7017c-112">Learn more in this overview.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a><span data-ttu-id="7017c-113">Introducción a una alerta</span><span class="sxs-lookup"><span data-stu-id="7017c-113">Getting started with an alert</span></span>

<span data-ttu-id="7017c-114">Si selecciona el nombre de una alerta en Defender for Endpoint, aparecerá en su página de alerta.</span><span class="sxs-lookup"><span data-stu-id="7017c-114">Selecting an alert's name in Defender for Endpoint will land you on its alert page.</span></span> <span data-ttu-id="7017c-115">En la página de alerta, toda la información se mostrará en el contexto de la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7017c-115">On the alert page, all the information will be shown in context of the selected alert.</span></span> <span data-ttu-id="7017c-116">Cada página de alerta consta de 4 secciones:</span><span class="sxs-lookup"><span data-stu-id="7017c-116">Each alert page consists of 4 sections:</span></span>

1. <span data-ttu-id="7017c-117">**El título de la** alerta muestra el nombre de la alerta y está allí para recordarle qué alerta inició la investigación actual independientemente de lo que haya seleccionado en la página.</span><span class="sxs-lookup"><span data-stu-id="7017c-117">**The alert title** shows the alert's name and is there to remind you which alert started your current investigation regardless of what you have selected on the page.</span></span>
2. <span data-ttu-id="7017c-118">[**Los activos afectados**](#review-affected-assets) enumeran tarjetas de dispositivos y usuarios afectados por esta alerta que se pueden hacer clic para obtener más información y acciones.</span><span class="sxs-lookup"><span data-stu-id="7017c-118">[**Affected assets**](#review-affected-assets) lists cards of devices and users affected by this alert that are clickable for further information and actions.</span></span>
3. <span data-ttu-id="7017c-119">El **artículo de alerta** muestra todas las entidades relacionadas con la alerta, interconectadas por una vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="7017c-119">The **alert story** displays all entities related to the alert, interconnected by a tree view.</span></span> <span data-ttu-id="7017c-120">La alerta del título será la que esté en foco cuando llegues por primera vez a la página de la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7017c-120">The alert in the title will be the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="7017c-121">Las entidades del artículo de alertas se pueden expandir y hacer clic, para proporcionar información adicional y acelerar la respuesta, ya que permiten realizar acciones directamente en el contexto de la página de alerta.</span><span class="sxs-lookup"><span data-stu-id="7017c-121">Entities in the alert story are expandable and clickable, to provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> <span data-ttu-id="7017c-122">Use el artículo de alerta para iniciar la investigación.</span><span class="sxs-lookup"><span data-stu-id="7017c-122">Use the alert story to start your investigation.</span></span> <span data-ttu-id="7017c-123">Obtenga información sobre [cómo en Investigar alertas en Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/investigate-alerts).</span><span class="sxs-lookup"><span data-stu-id="7017c-123">Learn how in [Investigate alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>
4. <span data-ttu-id="7017c-124">El **panel de detalles** mostrará los detalles de la alerta seleccionada al principio, con detalles y acciones relacionadas con esta alerta.</span><span class="sxs-lookup"><span data-stu-id="7017c-124">The **details pane** will show the details of the selected alert at first, with details and actions related to this alert.</span></span> <span data-ttu-id="7017c-125">Si selecciona cualquiera de los activos o entidades afectados en el artículo de alerta, el panel de detalles cambiará para proporcionar información contextual y acciones para el objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7017c-125">If you select any of the affected assets or entities in the alert story, the details pane will change to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="7017c-126">Tenga en cuenta el estado de detección de la alerta.</span><span class="sxs-lookup"><span data-stu-id="7017c-126">Note the detection status for your alert.</span></span> 
- <span data-ttu-id="7017c-127">Prevented: se evitó el intento de acción sospechosa.</span><span class="sxs-lookup"><span data-stu-id="7017c-127">Prevented – The attempted suspicious action was avoided.</span></span> <span data-ttu-id="7017c-128">Por ejemplo, un archivo no se escribió en el disco o se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="7017c-128">For example, a file either wasn’t written to disk or executed.</span></span>
<span data-ttu-id="7017c-129">![Se ha evitado una página de alerta que muestra la amenaza](images/detstat-prevented.png)</span><span class="sxs-lookup"><span data-stu-id="7017c-129">![An alert page showing threat was prevented](images/detstat-prevented.png)</span></span>
- <span data-ttu-id="7017c-130">Bloqueado: se ejecutó un comportamiento sospechoso y, a continuación, se bloqueó.</span><span class="sxs-lookup"><span data-stu-id="7017c-130">Blocked – Suspicious behavior was executed and then blocked.</span></span> <span data-ttu-id="7017c-131">Por ejemplo, se ejecutó un proceso, pero como posteriormente mostró comportamientos sospechosos, se finalizó el proceso.</span><span class="sxs-lookup"><span data-stu-id="7017c-131">For example, a process was executed but because it subsequently exhibited suspicious behaviors, the process was terminated.</span></span>
<span data-ttu-id="7017c-132">![Se bloqueó una página de alerta que muestra la amenaza](images/detstat-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="7017c-132">![An alert page showing threat was blocked](images/detstat-blocked.png)</span></span>
- <span data-ttu-id="7017c-133">Detectado: se detectó un ataque y posiblemente aún esté activo.</span><span class="sxs-lookup"><span data-stu-id="7017c-133">Detected – An attack was detected and is possibly still active.</span></span>
<span data-ttu-id="7017c-134">![Se detectó una página de alerta que muestra la amenaza](images/detstat-detected.png)</span><span class="sxs-lookup"><span data-stu-id="7017c-134">![An alert page showing threat was detected](images/detstat-detected.png)</span></span>




<span data-ttu-id="7017c-135">A continuación,  también puede revisar los detalles de la investigación automatizada en el panel de detalles de la alerta, para ver qué acciones ya se han realizado, así como leer la descripción de la alerta para las acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="7017c-135">You can then also review the *automated investigation details* in your alert's details pane, to see which actions were already taken, as well as reading the alert's description for recommended actions.</span></span>

![Fragmento de código del panel de detalles con la descripción de alerta y las secciones de investigación automática resaltadas](images/alert-air-and-alert-description.png)

<span data-ttu-id="7017c-137">Otra información disponible en el panel de detalles cuando se abre la alerta incluye técnicas MITRE, origen y detalles contextuales adicionales.</span><span class="sxs-lookup"><span data-stu-id="7017c-137">Other information available in the details pane when the alert opens includes MITRE techniques, source, and additional contextual details.</span></span>




## <a name="review-affected-assets"></a><span data-ttu-id="7017c-138">Revisar activos afectados</span><span class="sxs-lookup"><span data-stu-id="7017c-138">Review affected assets</span></span>

<span data-ttu-id="7017c-139">Al seleccionar un dispositivo o una tarjeta de usuario en las secciones activos afectados, se cambia a los detalles del dispositivo o usuario en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="7017c-139">Selecting a device or a user card in the affected assets sections will switch to the details of the device or user in the details pane.</span></span>

- <span data-ttu-id="7017c-140">**En el caso de** los dispositivos, el panel de detalles mostrará información sobre el propio dispositivo, como Dominio, Sistema operativo e IP.</span><span class="sxs-lookup"><span data-stu-id="7017c-140">**For devices**, the details pane will display information about the device itself, like Domain, Operating System, and IP.</span></span> <span data-ttu-id="7017c-141">Las alertas activas y los usuarios que han iniciado sesión en ese dispositivo también están disponibles.</span><span class="sxs-lookup"><span data-stu-id="7017c-141">Active alerts and the logged on users on that device are also available.</span></span> <span data-ttu-id="7017c-142">Puedes tomar medidas inmediatas al aislar el dispositivo, restringir la ejecución de la aplicación o ejecutar un examen antivirus.</span><span class="sxs-lookup"><span data-stu-id="7017c-142">You can take immediate action by isolating the device, restricting app execution, or running an antivirus scan.</span></span> <span data-ttu-id="7017c-143">Como alternativa, puedes recopilar un paquete de investigación, iniciar una investigación automatizada o ir a la página del dispositivo para investigar desde el punto de vista del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7017c-143">Alternatively, you could collect an investigation package, initiate an automated investigation, or go to the device page to investigate from the device's point of view.</span></span>

   ![Fragmento de código del panel de detalles cuando se selecciona un dispositivo](images/device-page-details.png)

- <span data-ttu-id="7017c-145">Para los **usuarios,** el panel de detalles mostrará información detallada del usuario, como el nombre SAM del usuario y SID, así como los tipos de inicio de sesión realizados por este usuario y las alertas e incidentes relacionados con él.</span><span class="sxs-lookup"><span data-stu-id="7017c-145">**For users**, the details pane will display detailed user information, such as the user's SAM name and SID, as well as logon types performed by this user and any alerts and incidents related to it.</span></span> <span data-ttu-id="7017c-146">Puede seleccionar Abrir *página de usuario para* continuar la investigación desde el punto de vista de ese usuario.</span><span class="sxs-lookup"><span data-stu-id="7017c-146">You can select *Open user page* to continue the investigation from that user's point of view.</span></span>

   ![Fragmento de código del panel de detalles cuando se selecciona un usuario](images/user-page-details.png)


## <a name="related-topics"></a><span data-ttu-id="7017c-148">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7017c-148">Related topics</span></span>

- [<span data-ttu-id="7017c-149">Ver y organizar la cola de incidentes</span><span class="sxs-lookup"><span data-stu-id="7017c-149">View and organize the incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="7017c-150">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="7017c-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="7017c-151">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="7017c-151">Manage incidents</span></span>](manage-incidents.md)
