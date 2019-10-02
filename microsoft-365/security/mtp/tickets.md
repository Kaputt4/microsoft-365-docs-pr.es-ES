---
title: Crear y realizar un seguimiento de las entradas a través de ServiceNow
description: El centro de seguridad 365 de Microsoft se está optimizando con la capacidad de crear y realizar un seguimiento de vales en ServiceNow de forma nativa. Esto permite a los administradores de seguridad enviar una recomendación de puntuación segura directamente a ServiceNow y crear un vale.
keywords: seguridad, Microsoft 365, M365, calificación segura, centro de seguridad, ServiceNow, billetes, tareas
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350340"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="7fc67-105">Administrar vales a través de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7fc67-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="7fc67-106">El centro de seguridad 365 de Microsoft se está optimizando con la capacidad de crear y realizar un seguimiento de vales en ServiceNow de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="7fc67-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="7fc67-107">Esto permite a los administradores de seguridad enviar una acción de mejora de la [puntuación segura de Microsoft](microsoft-secure-score.md) directamente a ServiceNow y crear un vale.</span><span class="sxs-lookup"><span data-stu-id="7fc67-107">This allows security administrators to send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="7fc67-108">Se pueden crear tíquets de administración de incidentes y de administración de cambios.</span><span class="sxs-lookup"><span data-stu-id="7fc67-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7fc67-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7fc67-109">Prerequisites</span></span>

<span data-ttu-id="7fc67-110">Tener acceso al centro de seguridad 365 de Microsoft y a una instancia de ServiceNow con:</span><span class="sxs-lookup"><span data-stu-id="7fc67-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="7fc67-111">Kingston o una versión superior</span><span class="sxs-lookup"><span data-stu-id="7fc67-111">Kingston or higher version</span></span>
* <span data-ttu-id="7fc67-112">Tener credenciales de admin HI</span><span class="sxs-lookup"><span data-stu-id="7fc67-112">Have admin HI credentials</span></span>
* <span data-ttu-id="7fc67-113">Tener privilegios de administrador en la instancia del proveedor de destino</span><span class="sxs-lookup"><span data-stu-id="7fc67-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="7fc67-114">ServiceNow recomienda a los usuarios mantener la configuración de forma predeterminada (predeterminado) en su instancia de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7fc67-114">ServiceNow recommends users keep out of the box settings (default) in your ServiceNow instance.</span></span>  <span data-ttu-id="7fc67-115">La realización de personalizaciones puede provocar errores al completar la lista de comprobación de instalación e integración con el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7fc67-115">Having customizations could cause errors in completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="7fc67-116">Intercambio de datos</span><span class="sxs-lookup"><span data-stu-id="7fc67-116">Data exchange</span></span>

<span data-ttu-id="7fc67-117">Cuando conecte el centro de seguridad de Microsoft 365 a ServiceNow, Microsoft recibirá los siguientes datos adicionales:</span><span class="sxs-lookup"><span data-stu-id="7fc67-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft will be receiving the following additional data:</span></span>

* <span data-ttu-id="7fc67-118">Nombre de instancia de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7fc67-118">ServiceNow instance name</span></span>
* <span data-ttu-id="7fc67-119">IDENTIFICADOR de cliente de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7fc67-119">ServiceNow client ID</span></span>
* <span data-ttu-id="7fc67-120">Secreto de cliente de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7fc67-120">ServiceNow client secret</span></span>
* <span data-ttu-id="7fc67-121">Tokens de actualización & acceso a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7fc67-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="7fc67-122">Cuando se crea un vale de ServiceNow desde el centro de seguridad de Microsoft 365, se envían los siguientes datos a ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="7fc67-122">When you create a ServiceNow ticket from the Microsoft 365 security center the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="7fc67-123">IDENTIFICADOR de usuario que inicia la creación de vales</span><span class="sxs-lookup"><span data-stu-id="7fc67-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="7fc67-124">Nombre de tarea</span><span class="sxs-lookup"><span data-stu-id="7fc67-124">Task name</span></span>
* <span data-ttu-id="7fc67-125">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="7fc67-125">Task description</span></span>
* <span data-ttu-id="7fc67-126">Priority</span><span class="sxs-lookup"><span data-stu-id="7fc67-126">Priority</span></span>
* <span data-ttu-id="7fc67-127">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="7fc67-127">Due date</span></span>
* <span data-ttu-id="7fc67-128">Origen de la recomendación (recomendación del usuario o recomendación de Microsoft)</span><span class="sxs-lookup"><span data-stu-id="7fc67-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="7fc67-129">Categoría de recomendación (dispositivos, datos, aplicaciones, identidad, infraestructura)</span><span class="sxs-lookup"><span data-stu-id="7fc67-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="7fc67-130">Conectar el centro de seguridad de Microsoft 365 a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7fc67-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="7fc67-131">Vaya a la página de inicio del centro de seguridad 365 de Microsoft, donde verá una tarjeta que pregunta si usa ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7fc67-131">Navigate to the Microsoft 365 security center home page, where you will see a card asking if you use ServiceNow.</span></span>

![¿Usa ServiceNow?](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="7fc67-133">Desde allí, se enviará a la página configurar de ServiceNow, en la que seguirá las instrucciones para autorizar la aplicación conector de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7fc67-133">From there you will be sent to the ServiceNow set up page where you'll follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

<span data-ttu-id="7fc67-134">Al autorizar la conexión entre el centro de seguridad de Microsoft 365 y ServiceNow, asegúrese de usar el inicio de sesión de usuario y la contraseña de integración que creó en los pasos de instalación y no en sus credenciales personales.</span><span class="sxs-lookup"><span data-stu-id="7fc67-134">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

<span data-ttu-id="7fc67-135">Después de seguir las indicaciones y autorizar la conexión, puede ver el estado de la conexión en la página de conexión del centro de seguridad 365 de Microsoft y en la experiencia de la aplicación conector de vales de Microsoft 365 de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7fc67-135">After following the directions and authorizing the connection, you can view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="7fc67-136">Ahora ya está todo listo para empezar a crear tareas.</span><span class="sxs-lookup"><span data-stu-id="7fc67-136">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="7fc67-137">Crear una tarea y compartirla en ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7fc67-137">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="7fc67-138">Una vez configurada la integración, puede crear tareas de ServiceNow basadas en acciones específicas para la mejora de la calificación segura de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7fc67-138">Once the integration is set up, you can create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="7fc67-139">Vaya a cualquier acción de mejora en puntuación segura en el portal del centro de seguridad 365 de Microsoft y seleccione el icono "compartir".</span><span class="sxs-lookup"><span data-stu-id="7fc67-139">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="7fc67-140">Una de las opciones de lista desplegable es ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7fc67-140">One of the dropdown options is ServiceNow.</span></span>

![Uso compartido de ServiceNow en calificación segura](../images/servicenow-share.png)

<span data-ttu-id="7fc67-142">A continuación, se generará una tarea en la que puede establecer la prioridad y editar el nombre, la descripción o la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="7fc67-142">A task will then be generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="7fc67-143">Una vez que se hayan rellenado todos los campos obligatorios, puede enviar la tarea a ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7fc67-143">Once all the required fields are filled in, you can send the task to ServiceNow.</span></span>

<span data-ttu-id="7fc67-144">La tarea será visible en ServiceNow como una solicitud de cambio de configuración y seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7fc67-144">The task will be visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="7fc67-145">Seguimiento de vales</span><span class="sxs-lookup"><span data-stu-id="7fc67-145">Track tickets</span></span>

<span data-ttu-id="7fc67-146">Una vez creados la administración de cambios de ServiceNow y los vales de administración de incidentes, se mostrarán en las tarjetas de la Página principal del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7fc67-146">Once ServiceNow change management and incident management tickets have been created, they will be displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="7fc67-147">Desde estas tarjetas, puede crear un vale, ver todos los vales o administrar la configuración de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7fc67-147">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Vales de administración de cambios de ServiceNow](../images/change-management-375.png)  ![Vales de administración de incidentes de ServiceNow](../images/incident-management-375.png)

<span data-ttu-id="7fc67-150">Para volver a aprovisionar o administrar la integración de ServiceNow en el centro de seguridad de Microsoft 365, seleccione **administrar la configuración de servicenow** en una de las tarjetas.</span><span class="sxs-lookup"><span data-stu-id="7fc67-150">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="7fc67-151">Desde allí, puede quitar la conexión de ServiceNow actual y personalizar los nombres de estado de los tíquets.</span><span class="sxs-lookup"><span data-stu-id="7fc67-151">From there you can  remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="7fc67-152">Con los vales de ServiceNow visibles en el centro de seguridad de Microsoft 365, las tareas se colocarán en un lugar en el que se puede realizar un seguimiento y actuar con ellos junto a otros elementos del panel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7fc67-152">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks will live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="7fc67-153">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="7fc67-153">Frequently asked questions</span></span>

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="7fc67-154">Estoy recibiendo un error en el primer paso de la lista de comprobación de la instalación (creación de OAuth)</span><span class="sxs-lookup"><span data-stu-id="7fc67-154">I am receiving an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="7fc67-155">**Mensaje de error**: se rechazó la operación de lectura contra ' oauth_entity ' del ámbito ' x_mioms_m365ticket ' debido a la Directiva de acceso entre ámbitos de la tabla</span><span class="sxs-lookup"><span data-stu-id="7fc67-155">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="7fc67-156">Nuestra aplicación asume que cualquier administrador de la instancia de ServiceNow puede crear y leer entidades de OAuth.</span><span class="sxs-lookup"><span data-stu-id="7fc67-156">Our app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="7fc67-157">Este error puede deberse a una personalización en la instancia de ServiceNow, que restringe quién puede crear o leer entidades de OAuth.</span><span class="sxs-lookup"><span data-stu-id="7fc67-157">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span> <span data-ttu-id="7fc67-158">ServiceNow recomienda a los usuarios mantener la funcionalidad de forma predeterminada (predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7fc67-158">ServiceNow recommends users keep out of the box functionality (default).</span></span>

<span data-ttu-id="7fc67-159">Establezca la configuración de la tabla "registros de aplicación" en default:</span><span class="sxs-lookup"><span data-stu-id="7fc67-159">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="7fc67-160">Label = registros de aplicación</span><span class="sxs-lookup"><span data-stu-id="7fc67-160">Label = Application Registeries</span></span>
* <span data-ttu-id="7fc67-161">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="7fc67-161">Name = oauth_entity</span></span>
* <span data-ttu-id="7fc67-162">Accesible desde = todos los ámbitos de aplicación</span><span class="sxs-lookup"><span data-stu-id="7fc67-162">Accessible from = All application scopes</span></span>
* <span data-ttu-id="7fc67-163">Puede leer = casilla de verificación seleccionada</span><span class="sxs-lookup"><span data-stu-id="7fc67-163">Can read = check box selected</span></span>

<span data-ttu-id="7fc67-164">**ServiceNow recomienda a los usuarios mantener la funcionalidad de forma predeterminada (predeterminado).**</span><span class="sxs-lookup"><span data-stu-id="7fc67-164">**ServiceNow recommends users keep out of the box functionality (default).**</span></span>

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="7fc67-165">¿Cómo puedo validar la entidad de OAuth creada para el conector de cumplimiento de & de seguridad de Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="7fc67-165">How do I validate the OAuth entity created for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="7fc67-166">Vaya a la tabla registros de aplicaciones (menú > el registro de aplicaciones de OAuth > sistema) en ServiceNow y busque la entidad OAuth que ha creado el usuario (nombre que le ha asignado).</span><span class="sxs-lookup"><span data-stu-id="7fc67-166">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="7fc67-167">¿Cómo puedo validar el usuario de integración creado en el paso dos de la lista de comprobación de instalación de Microsoft 365 Security & Compliance Connector?</span><span class="sxs-lookup"><span data-stu-id="7fc67-167">How do I validate the Integration User created in step two of installation checklist for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="7fc67-168">Vaya a la tabla de usuarios (menú > usuarios de > de administración de usuarios) en ServiceNow y busque el usuario de integración creado por usted (nombre que le ha asignado).</span><span class="sxs-lookup"><span data-stu-id="7fc67-168">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

<span data-ttu-id="7fc67-169">Al autorizar la conexión entre el centro de seguridad de Microsoft 365 y ServiceNow, asegúrese de usar el inicio de sesión de usuario y la contraseña de integración que creó en los pasos de instalación y no en sus credenciales personales.</span><span class="sxs-lookup"><span data-stu-id="7fc67-169">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a><span data-ttu-id="7fc67-170">He completado la instalación y he configurado los pasos, pero no veo las tarjetas de ServiceNow en la Página principal y no puede ver el icono compartir en la puntuación segura de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7fc67-170">I have completed the installation and set up steps, but I am unable to see the ServiceNow cards on the home page and cannot see the Share icon in Microsoft Secure Score</span></span>

<span data-ttu-id="7fc67-171">Comprueba el estado de la página de aprovisionamiento yendo a https://security.microsoft.com/ticketProvisioning.</span><span class="sxs-lookup"><span data-stu-id="7fc67-171">Check the status of the provisioning page by going to https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="7fc67-172">Seleccione **Guardar** y volver a la Página principal.</span><span class="sxs-lookup"><span data-stu-id="7fc67-172">Select **Save** and return to the home page.</span></span> <span data-ttu-id="7fc67-173">Deben aparecer las tarjetas.</span><span class="sxs-lookup"><span data-stu-id="7fc67-173">The cards should appear.</span></span>
