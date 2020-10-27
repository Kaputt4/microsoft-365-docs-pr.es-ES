---
title: Crear y realizar un seguimiento de los vales de ServiceNow en el centro de seguridad de Microsoft 365
description: Obtenga información sobre cómo crear y realizar un seguimiento de vales en ServiceNow desde el centro de seguridad de Microsoft 365.
keywords: seguridad, Microsoft 365, M365, calificación segura, centro de seguridad, ServiceNow, billetes, tareas
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 8992efdd79295b6b56b8f033bd97b10f59a7a4d5
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769680"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="c207e-104">Crear y realizar un seguimiento de los vales de ServiceNow en el centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c207e-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="c207e-105">**El período de versión preliminar del conector de ServiceNow está finalizando**</span><span class="sxs-lookup"><span data-stu-id="c207e-105">**The preview period for the ServiceNow connector is ending**</span></span><br>
><span data-ttu-id="c207e-106">Esta capacidad ya no estará disponible al final de noviembre de 2020.</span><span class="sxs-lookup"><span data-stu-id="c207e-106">This capability will no longer available by the end of November 2020.</span></span> <span data-ttu-id="c207e-107">Gracias por sus comentarios y el soporte técnico continuo mientras determinamos los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="c207e-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="c207e-108">El [centro de seguridad de Microsoft 365](overview-security-center.md) se ha mejorado con la capacidad de crear y realizar un seguimiento de vales en ServiceNow de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="c207e-108">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="c207e-109">Obtenga más información sobre ServiceNow</span><span class="sxs-lookup"><span data-stu-id="c207e-109">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="c207e-110">En el centro de seguridad, los administradores de seguridad pueden enviar una acción de mejora de la [calificación segura de Microsoft](microsoft-secure-score.md) directamente a ServiceNow y crear un vale.</span><span class="sxs-lookup"><span data-stu-id="c207e-110">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="c207e-111">Se pueden crear tíquets de administración de incidentes y de administración de cambios.</span><span class="sxs-lookup"><span data-stu-id="c207e-111">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="c207e-112">Realice un seguimiento de las entradas en la Página principal del centro de seguridad y en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="c207e-112">Track tickets in the security center home page and ServiceNow.</span></span>

- [<span data-ttu-id="c207e-113">**Información sobre los requisitos previos, el intercambio de datos y la solución de problemas**</span><span class="sxs-lookup"><span data-stu-id="c207e-113">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="c207e-114">**Administrar vales de ServiceNow en el centro de cumplimiento** (no disponible)</span><span class="sxs-lookup"><span data-stu-id="c207e-114">**Manage ServiceNow tickets in the compliance center** (not available)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="c207e-115">Conectar el centro de seguridad de Microsoft 365 a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="c207e-115">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="c207e-116">Vaya a la página de inicio del centro de seguridad 365 de Microsoft para ver la tarjeta de conexión de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="c207e-116">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![¿Usa ServiceNow?](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="c207e-118">Seleccione "conectarse a ServiceNow" para ir a la página de configuración de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="c207e-118">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="c207e-119">Siga las instrucciones para autorizar la aplicación conector de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c207e-119">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="c207e-120">Antes de autorizar la conexión entre el centro de seguridad de Microsoft 365 y ServiceNow, asegúrese de usar el inicio de sesión de usuario y la contraseña de integración que creó en los pasos de instalación.</span><span class="sxs-lookup"><span data-stu-id="c207e-120">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="c207e-121">No use sus credenciales personales.</span><span class="sxs-lookup"><span data-stu-id="c207e-121">Do not use your personal credentials.</span></span>

<span data-ttu-id="c207e-122">Una vez que haya seguido las indicaciones y autorice la conexión, vea el estado de conexión en la página conexión del centro de seguridad de 365 de Microsoft y en la experiencia de la aplicación conector de vales de Microsoft 365 de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="c207e-122">After you've followed the directions and authorized the connection, view the connection status in the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="c207e-123">Ya está todo listo para empezar a crear tareas.</span><span class="sxs-lookup"><span data-stu-id="c207e-123">Now you're all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="c207e-124">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="c207e-124">Troubleshooting</span></span>

<span data-ttu-id="c207e-125">Obtenga información sobre errores comunes que pueden aparecer en el proceso de conexión y cómo mitigarlos en la sección de [solución de problemas](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="c207e-125">Learn common errors you may come across in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="c207e-126">Crear una tarea y compartirla en ServiceNow</span><span class="sxs-lookup"><span data-stu-id="c207e-126">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="c207e-127">Una vez que la integración esté configurada, cree tareas de ServiceNow basadas en acciones específicas para la mejora de la [calificación segura de Microsoft](microsoft-secure-score.md) .</span><span class="sxs-lookup"><span data-stu-id="c207e-127">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="c207e-128">Vaya a cualquier acción de mejora de la puntuación segura en el centro de seguridad 365 de Microsoft y seleccione **compartir** .</span><span class="sxs-lookup"><span data-stu-id="c207e-128">Go to any Secure Score improvement action in the Microsoft 365 security center, and select **Share** .</span></span> <span data-ttu-id="c207e-129">Una de las opciones de lista desplegable es ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="c207e-129">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="c207e-130">Se genera una tarea en la que puede establecer la prioridad y editar el nombre, la descripción o la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="c207e-130">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="c207e-131">Una vez que se hayan rellenado todos los campos obligatorios, envíe la tarea a ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="c207e-131">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="c207e-132">La tarea es visible en ServiceNow como una solicitud de cambio de configuración y seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c207e-132">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="c207e-133">Seguimiento de vales</span><span class="sxs-lookup"><span data-stu-id="c207e-133">Track tickets</span></span>

<span data-ttu-id="c207e-134">Una vez que se hayan creado los vales de administración de cambios y la administración de cambios de ServiceNow, se mostrarán en las tarjetas de la Página principal del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c207e-134">Once ServiceNow change management and incident management tickets have been created, they're displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="c207e-135">Desde estas tarjetas, puede crear un vale, ver todos los vales o administrar la configuración de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="c207e-135">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Vales de administración de cambios de ServiceNow](../../media/change-management-375.png)  ![Vales de administración de incidentes de ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="c207e-138">Para reprovisionar o administrar la integración de ServiceNow en el centro de seguridad de Microsoft 365, seleccione **administrar la configuración de servicenow** en una de las tarjetas.</span><span class="sxs-lookup"><span data-stu-id="c207e-138">To reprovision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="c207e-139">Desde allí, elimine la conexión de ServiceNow actual y personalice los nombres de los Estados de las incidencias.</span><span class="sxs-lookup"><span data-stu-id="c207e-139">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="c207e-140">Con los vales de ServiceNow visibles en el centro de seguridad de Microsoft 365, las tareas residen en un lugar en el que se puede realizar un seguimiento y actuar junto a otros elementos del panel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c207e-140">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="c207e-141">Recursos</span><span class="sxs-lookup"><span data-stu-id="c207e-141">Resources</span></span>

- [<span data-ttu-id="c207e-142">Información sobre los requisitos previos, el intercambio de datos y la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="c207e-142">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="c207e-143">Puntuación de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c207e-143">Microsoft Secure Score</span></span>](microsoft-secure-score.md)
