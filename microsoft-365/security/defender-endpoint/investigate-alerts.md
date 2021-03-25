---
title: Investigar alertas de punto de conexión de Microsoft Defender
description: Use las opciones de investigación para obtener detalles sobre las alertas que afectan a su red, lo que significan y cómo resolverlas.
keywords: investigar, investigar, dispositivos, dispositivos, cola de alertas, panel, dirección IP, archivo, enviar, envíos, análisis profundo, escala de tiempo, búsqueda, dominio, dirección URL, IP
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 498f2d83af6e2eb7fc56b232bafd9fc49d9d4fd9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075736"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="4b9d0-104">Investigar alertas en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="4b9d0-104">Investigate alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4b9d0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4b9d0-105">**Applies to:**</span></span>
- [<span data-ttu-id="4b9d0-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4b9d0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="4b9d0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b9d0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4b9d0-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4b9d0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4b9d0-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

<span data-ttu-id="4b9d0-110">Investigue las alertas que afectan a la red, comprenda lo que significan y cómo resolverlas.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-110">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>

<span data-ttu-id="4b9d0-111">Seleccione una alerta de la cola de alertas para ir a la página de alertas.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-111">Select an alert from the alerts queue to go to alert page.</span></span> <span data-ttu-id="4b9d0-112">Esta vista contiene el título de alerta, los activos afectados, el panel lateral de detalles y el artículo de alerta.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-112">This view contains the alert title, the affected assets, the details side pane, and the alert story.</span></span>

<span data-ttu-id="4b9d0-113">En la página de alertas, comience la investigación seleccionando los activos afectados o cualquiera de las entidades en la vista de árbol del artículo de alerta.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-113">From the alert page, begin your investigation by selecting the affected assets or any of the entities under the alert story tree view.</span></span> <span data-ttu-id="4b9d0-114">El panel de detalles se rellena automáticamente con más información sobre lo que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-114">The details pane automatically populates with further information about what you selected.</span></span> <span data-ttu-id="4b9d0-115">Para ver qué tipo de información puede ver aquí, lea [Review alerts in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts).</span><span class="sxs-lookup"><span data-stu-id="4b9d0-115">To see what kind of information you can view here, read [Review alerts in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts).</span></span>

## <a name="investigate-using-the-alert-story"></a><span data-ttu-id="4b9d0-116">Investigar con el artículo de alerta</span><span class="sxs-lookup"><span data-stu-id="4b9d0-116">Investigate using the alert story</span></span>

<span data-ttu-id="4b9d0-117">El artículo de alerta detalla por qué se desencadenó la alerta, los eventos relacionados que sucedieron antes y después, así como otras entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-117">The alert story details why the alert was triggered, related events that happened before and after, as well as other related entities.</span></span>

<span data-ttu-id="4b9d0-118">Las entidades pueden hacer clic y todas las entidades que no son una alerta se pueden expandir mediante el icono expandir situado a la derecha de la tarjeta de esa entidad.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-118">Entities are clickable and every entity that isn't an alert is expandable using the expand icon on the right side of that entity's card.</span></span> <span data-ttu-id="4b9d0-119">La entidad en el foco se indicará mediante una franja azul al lado izquierdo de la tarjeta de esa entidad, con la alerta en el título en el foco al principio.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-119">The entity in focus will be indicated by a blue stripe to the left side of that entity's card, with the alert in the title being in focus at first.</span></span>

<span data-ttu-id="4b9d0-120">Expanda entidades para ver los detalles de un vistazo.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-120">Expand entities to view details at a glance.</span></span> <span data-ttu-id="4b9d0-121">Al seleccionar una entidad, se cambia el contexto del panel de detalles a esta entidad y se le permite revisar más información, así como administrar esa entidad.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-121">Selecting an entity will switch the context of the details pane to this entity, and will allow you to review further information, as well as manage that entity.</span></span> <span data-ttu-id="4b9d0-122">Si selecciona *...* a la derecha de la tarjeta de entidad, se mostrarán todas las acciones disponibles para esa entidad.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-122">Selecting *...* to the right of the entity card will reveal all actions available for that entity.</span></span> <span data-ttu-id="4b9d0-123">Estas mismas acciones aparecen en el panel de detalles cuando esa entidad está en el foco.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-123">These same actions appear in the details pane when that entity is in focus.</span></span>

> [!NOTE]
> <span data-ttu-id="4b9d0-124">La sección de artículo de alerta puede contener más de una alerta, con alertas adicionales relacionadas con el mismo árbol de ejecución que aparecen antes o después de la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

![Un ejemplo de un artículo de alerta con una alerta en el foco y algunas tarjetas expandida](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a><span data-ttu-id="4b9d0-126">Realizar acciones desde el panel de detalles</span><span class="sxs-lookup"><span data-stu-id="4b9d0-126">Take action from the details pane</span></span>

<span data-ttu-id="4b9d0-127">Una vez que haya seleccionado una entidad de interés, el panel de detalles cambiará para mostrar información sobre  el tipo de entidad seleccionada, información histórica cuando esté disponible y ofrecer controles para realizar acciones en esta entidad directamente desde la página de alerta.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-127">Once you've selected an entity of interest, the details pane will change to display information about the selected entity type, historic information when it's available, and offer controls to **take action** on this entity directly from the alert page.</span></span>

<span data-ttu-id="4b9d0-128">Una vez que haya terminado de investigar, vuelva a la alerta con la que inició, marque el estado de la alerta como **Resuelto** y clasifique como **Alerta** falsa o **Alerta verdadera**.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-128">Once you're done investigating, go back to the alert you started with, mark the alert's status as **Resolved** and classify it as either **False alert** or **True alert**.</span></span> <span data-ttu-id="4b9d0-129">Clasificar alertas ayuda a ajustar esta funcionalidad para proporcionar alertas más verdaderas y menos falsas.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-129">Classifying alerts helps tune this capability to provide more true alerts and less false alerts.</span></span>

<span data-ttu-id="4b9d0-130">Si la clasifica como una alerta verdadera, también puede seleccionar una determinación, como se muestra en la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-130">If you classify it as a true alert, you can also select a determination, as shown in the image below.</span></span>

![Fragmento de código del panel de detalles con una alerta resuelta y la lista desplegable de determinación expandida](images/alert-details-resolved-true.png)

<span data-ttu-id="4b9d0-132">Si experimenta una alerta falsa con una aplicación de línea de negocio, cree una regla de supresión para evitar este tipo de alerta en el futuro.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-132">If you are experiencing a false alert with a line-of-business application, create a suppression rule to avoid this type of alert in the future.</span></span>

![acciones y clasificación en el panel de detalles con la regla de supresión resaltada](images/alert-false-suppression-rule.png)

> [!TIP]
> <span data-ttu-id="4b9d0-134">Si tienes algún problema que no se describe anteriormente, usa el botón para proporcionar comentarios 🙂 o abrir un vale de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="4b9d0-134">If you're experiencing any issues not described above, use the 🙂 button to provide feedback or open a support ticket.</span></span>


## <a name="related-topics"></a><span data-ttu-id="4b9d0-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4b9d0-135">Related topics</span></span>
- [<span data-ttu-id="4b9d0-136">Ver y organizar la cola de Alertas de punto de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4b9d0-136">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="4b9d0-137">Administrar alertas de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="4b9d0-137">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="4b9d0-138">Investigar un archivo asociado a una alerta de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4b9d0-138">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="4b9d0-139">Investigar dispositivos en la lista Defender para dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4b9d0-139">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="4b9d0-140">Investigar una dirección IP asociada a una alerta de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4b9d0-140">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="4b9d0-141">Investigar un dominio asociado a una alerta de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4b9d0-141">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="4b9d0-142">Investigar una cuenta de usuario en Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4b9d0-142">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)


