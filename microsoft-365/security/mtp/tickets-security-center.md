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
ms.openlocfilehash: bd5bf8533d38337c063acdf0dda073e4961e416a
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867250"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="20a5c-104">Crear y realizar un seguimiento de los vales de ServiceNow en el centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20a5c-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="20a5c-105">El [centro de seguridad de Microsoft 365](overview-security-center.md) se ha mejorado con la capacidad de crear y realizar un seguimiento de vales en ServiceNow de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="20a5c-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="20a5c-106">Obtenga más información sobre ServiceNow</span><span class="sxs-lookup"><span data-stu-id="20a5c-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="20a5c-107">En el centro de seguridad, los administradores de seguridad pueden enviar una acción de mejora de la [calificación segura de Microsoft](microsoft-secure-score.md) directamente a ServiceNow y crear un vale.</span><span class="sxs-lookup"><span data-stu-id="20a5c-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="20a5c-108">Se pueden crear tíquets de administración de incidentes y de administración de cambios.</span><span class="sxs-lookup"><span data-stu-id="20a5c-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="20a5c-109">Realice un seguimiento de las entradas en la Página principal del centro de seguridad y en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="20a5c-109">Track tickets in the security center home page and ServiceNow.</span></span>

- [<span data-ttu-id="20a5c-110">**Información sobre los requisitos previos, el intercambio de datos y la solución de problemas**</span><span class="sxs-lookup"><span data-stu-id="20a5c-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="20a5c-111">**Administrar vales de ServiceNow en el centro de cumplimiento** (próximamente)</span><span class="sxs-lookup"><span data-stu-id="20a5c-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="20a5c-112">Conectar el centro de seguridad de Microsoft 365 a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="20a5c-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="20a5c-113">Vaya a la página de inicio del centro de seguridad 365 de Microsoft para ver la tarjeta de conexión de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="20a5c-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![¿Usa ServiceNow?](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="20a5c-115">Seleccione "conectarse a ServiceNow" para ir a la página de configuración de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="20a5c-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="20a5c-116">Siga las instrucciones para autorizar la aplicación conector de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="20a5c-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="20a5c-117">Antes de autorizar la conexión entre el centro de seguridad de Microsoft 365 y ServiceNow, asegúrese de usar el inicio de sesión de usuario y la contraseña de integración que creó en los pasos de instalación.</span><span class="sxs-lookup"><span data-stu-id="20a5c-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="20a5c-118">No use sus credenciales personales.</span><span class="sxs-lookup"><span data-stu-id="20a5c-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="20a5c-119">Una vez que haya seguido las indicaciones y autorice la conexión, vea el estado de conexión en la página conexión del centro de seguridad de 365 de Microsoft y en la experiencia de la aplicación conector de vales de Microsoft 365 de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="20a5c-119">After you've followed the directions and authorized the connection, view the connection status in the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="20a5c-120">Ya está todo listo para empezar a crear tareas.</span><span class="sxs-lookup"><span data-stu-id="20a5c-120">Now you're all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="20a5c-121">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="20a5c-121">Troubleshooting</span></span>

<span data-ttu-id="20a5c-122">Obtenga información sobre errores comunes que pueden aparecer en el proceso de conexión y cómo mitigarlos en la sección de [solución de problemas](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="20a5c-122">Learn common errors you may come across in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="20a5c-123">Crear una tarea y compartirla en ServiceNow</span><span class="sxs-lookup"><span data-stu-id="20a5c-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="20a5c-124">Una vez que la integración esté configurada, cree tareas de ServiceNow basadas en acciones específicas para la mejora de la [calificación segura de Microsoft](microsoft-secure-score.md) .</span><span class="sxs-lookup"><span data-stu-id="20a5c-124">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="20a5c-125">Vaya a cualquier acción de mejora de la puntuación segura en el centro de seguridad 365 de Microsoft y seleccione **compartir**.</span><span class="sxs-lookup"><span data-stu-id="20a5c-125">Go to any Secure Score improvement action in the Microsoft 365 security center, and select **Share**.</span></span> <span data-ttu-id="20a5c-126">Una de las opciones de lista desplegable es ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="20a5c-126">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="20a5c-127">Se genera una tarea en la que puede establecer la prioridad y editar el nombre, la descripción o la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="20a5c-127">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="20a5c-128">Una vez que se hayan rellenado todos los campos obligatorios, envíe la tarea a ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="20a5c-128">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="20a5c-129">La tarea es visible en ServiceNow como una solicitud de cambio de configuración y seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="20a5c-129">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="20a5c-130">Seguimiento de vales</span><span class="sxs-lookup"><span data-stu-id="20a5c-130">Track tickets</span></span>

<span data-ttu-id="20a5c-131">Una vez que se hayan creado los vales de administración de cambios y la administración de cambios de ServiceNow, se mostrarán en las tarjetas de la Página principal del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="20a5c-131">Once ServiceNow change management and incident management tickets have been created, they're displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="20a5c-132">Desde estas tarjetas, puede crear un vale, ver todos los vales o administrar la configuración de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="20a5c-132">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Vales de administración de cambios de ServiceNow](../../media/change-management-375.png)  ![Vales de administración de incidentes de ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="20a5c-135">Para reprovisionar o administrar la integración de ServiceNow en el centro de seguridad de Microsoft 365, seleccione **administrar la configuración de servicenow** en una de las tarjetas.</span><span class="sxs-lookup"><span data-stu-id="20a5c-135">To reprovision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="20a5c-136">Desde allí, elimine la conexión de ServiceNow actual y personalice los nombres de los Estados de las incidencias.</span><span class="sxs-lookup"><span data-stu-id="20a5c-136">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="20a5c-137">Con los vales de ServiceNow visibles en el centro de seguridad de Microsoft 365, las tareas residen en un lugar en el que se puede realizar un seguimiento y actuar junto a otros elementos del panel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="20a5c-137">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="20a5c-138">Recursos</span><span class="sxs-lookup"><span data-stu-id="20a5c-138">Resources</span></span>

- [<span data-ttu-id="20a5c-139">Información sobre los requisitos previos, el intercambio de datos y la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="20a5c-139">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="20a5c-140">Puntuación de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="20a5c-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md)