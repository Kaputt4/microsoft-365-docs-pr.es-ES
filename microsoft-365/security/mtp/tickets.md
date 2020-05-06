---
title: Crear y realizar un seguimiento de las entradas a través de ServiceNow
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
ms.openlocfilehash: 6070878d6cf0efd8a85d05ff6ef89ee49baf4144
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034193"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="2b24a-104">Administrar tickets a través de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2b24a-104">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="2b24a-105">ServiceNow es una plataforma de informática en la nube popular que ayuda a las empresas a administrar flujos de trabajo digitales para operaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="2b24a-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="2b24a-106">Su plataforma ahora tiene flujos de trabajo de ti, flujos de trabajo de empleados y flujos de trabajo de clientes.</span><span class="sxs-lookup"><span data-stu-id="2b24a-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> <span data-ttu-id="2b24a-107">Microsoft se ha asociado con ServiceNow para facilitar a los administradores de ti la administración de sus billetes y tareas en ambas plataformas.</span><span class="sxs-lookup"><span data-stu-id="2b24a-107">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> [<span data-ttu-id="2b24a-108">Obtenga más información sobre ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2b24a-108">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="2b24a-109">Microsoft 365 Security Center ahora se ha mejorado con la capacidad de crear y realizar un seguimiento de vales en ServiceNow de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="2b24a-109">Microsoft 365 security center is now enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="2b24a-110">Los administradores de seguridad pueden enviar una acción de mejora de la [puntuación segura de Microsoft](microsoft-secure-score.md) directamente a ServiceNow y crear un vale.</span><span class="sxs-lookup"><span data-stu-id="2b24a-110">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="2b24a-111">Se pueden crear tíquets de administración de incidentes y de administración de cambios.</span><span class="sxs-lookup"><span data-stu-id="2b24a-111">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="2b24a-112">A continuación, se puede realizar un seguimiento en la Página principal del centro de seguridad de Microsoft y en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-112">They can then be tracked in the Microsoft security center home page, and ServiceNow.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2b24a-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2b24a-113">Prerequisites</span></span>

<span data-ttu-id="2b24a-114">Tener acceso al centro de seguridad 365 de Microsoft y a una instancia de ServiceNow con:</span><span class="sxs-lookup"><span data-stu-id="2b24a-114">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="2b24a-115">Kingston o una versión superior</span><span class="sxs-lookup"><span data-stu-id="2b24a-115">Kingston or higher version</span></span>
* <span data-ttu-id="2b24a-116">Tener credenciales de admin HI</span><span class="sxs-lookup"><span data-stu-id="2b24a-116">Have admin HI credentials</span></span>
* <span data-ttu-id="2b24a-117">Tener privilegios de administrador en la instancia del proveedor de destino</span><span class="sxs-lookup"><span data-stu-id="2b24a-117">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="2b24a-118">ServiceNow recomienda que los usuarios conserven la configuración predeterminada en su instancia de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-118">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="2b24a-119">La realización de personalizaciones puede provocar errores al completar la lista de comprobación de instalación e integración con el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b24a-119">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="2b24a-120">Intercambio de datos</span><span class="sxs-lookup"><span data-stu-id="2b24a-120">Data exchange</span></span>

<span data-ttu-id="2b24a-121">Cuando conecta el centro de seguridad de Microsoft 365 a ServiceNow, Microsoft recibe los siguientes datos adicionales:</span><span class="sxs-lookup"><span data-stu-id="2b24a-121">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="2b24a-122">Nombre de instancia de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2b24a-122">ServiceNow instance name</span></span>
* <span data-ttu-id="2b24a-123">IDENTIFICADOR de cliente de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2b24a-123">ServiceNow client ID</span></span>
* <span data-ttu-id="2b24a-124">Secreto de cliente de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2b24a-124">ServiceNow client secret</span></span>
* <span data-ttu-id="2b24a-125">Tokens de actualización & acceso a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2b24a-125">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="2b24a-126">Cuando se crea un vale de ServiceNow a partir del centro de seguridad 365 de Microsoft, se envían los datos siguientes a ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="2b24a-126">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="2b24a-127">IDENTIFICADOR de usuario que inicia la creación de vales</span><span class="sxs-lookup"><span data-stu-id="2b24a-127">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="2b24a-128">Nombre de tarea</span><span class="sxs-lookup"><span data-stu-id="2b24a-128">Task name</span></span>
* <span data-ttu-id="2b24a-129">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="2b24a-129">Task description</span></span>
* <span data-ttu-id="2b24a-130">Priority</span><span class="sxs-lookup"><span data-stu-id="2b24a-130">Priority</span></span>
* <span data-ttu-id="2b24a-131">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="2b24a-131">Due date</span></span>
* <span data-ttu-id="2b24a-132">Origen de la recomendación (recomendación del usuario o recomendación de Microsoft)</span><span class="sxs-lookup"><span data-stu-id="2b24a-132">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="2b24a-133">Categoría de recomendación (dispositivos, datos, aplicaciones, identidad, infraestructura)</span><span class="sxs-lookup"><span data-stu-id="2b24a-133">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="2b24a-134">Conectar el centro de seguridad de Microsoft 365 a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2b24a-134">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="2b24a-135">Vaya a la página de inicio del centro de seguridad 365 de Microsoft para ver la tarjeta de conexión de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-135">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![¿Usa ServiceNow?](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="2b24a-137">Seleccione "conectarse a ServiceNow" para ir a la página de configuración de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-137">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="2b24a-138">Siga las instrucciones para autorizar la aplicación conector de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b24a-138">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="2b24a-139">Antes de autorizar la conexión entre el centro de seguridad de Microsoft 365 y ServiceNow, asegúrese de usar el inicio de sesión de usuario y la contraseña de integración que creó en los pasos de instalación.</span><span class="sxs-lookup"><span data-stu-id="2b24a-139">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="2b24a-140">No use sus credenciales personales.</span><span class="sxs-lookup"><span data-stu-id="2b24a-140">Do not use your personal credentials.</span></span>

<span data-ttu-id="2b24a-141">Una vez que haya seguido las instrucciones y la autorización de la conexión, vea el estado de conexión en la página conexión del centro de seguridad 365 de Microsoft y en la experiencia de la aplicación conector de vales de Microsoft 365 de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-141">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="2b24a-142">Ahora ya está todo listo para empezar a crear tareas.</span><span class="sxs-lookup"><span data-stu-id="2b24a-142">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="2b24a-143">Crear una tarea y compartirla en ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2b24a-143">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="2b24a-144">Una vez que la integración esté configurada, cree tareas de ServiceNow basadas en acciones específicas para la mejora de la calificación segura de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b24a-144">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="2b24a-145">Vaya a cualquier acción de mejora en puntuación segura en el portal del centro de seguridad 365 de Microsoft y seleccione el icono "compartir".</span><span class="sxs-lookup"><span data-stu-id="2b24a-145">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="2b24a-146">Una de las opciones de lista desplegable es ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-146">One of the dropdown options is ServiceNow.</span></span>

![Uso compartido de ServiceNow en calificación segura](../../media/servicenow-share.png)

<span data-ttu-id="2b24a-148">Se genera una tarea en la que puede establecer la prioridad y editar el nombre, la descripción o la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="2b24a-148">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="2b24a-149">Una vez que se hayan rellenado todos los campos obligatorios, envíe la tarea a ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-149">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="2b24a-150">La tarea es visible en ServiceNow como una solicitud de cambio de configuración y seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b24a-150">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="2b24a-151">Seguimiento de vales</span><span class="sxs-lookup"><span data-stu-id="2b24a-151">Track tickets</span></span>

<span data-ttu-id="2b24a-152">Una vez que se han creado los vales de administración de cambios y la administración de cambios de ServiceNow, se muestran en las tarjetas de la página de inicio del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b24a-152">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="2b24a-153">Desde estas tarjetas, puede crear un vale, ver todos los vales o administrar la configuración de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-153">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Vales de administración de cambios de ServiceNow](../../media/change-management-375.png)  ![Vales de administración de incidentes de ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="2b24a-156">Para volver a aprovisionar o administrar la integración de ServiceNow en el centro de seguridad de Microsoft 365, seleccione **administrar la configuración de servicenow** en una de las tarjetas.</span><span class="sxs-lookup"><span data-stu-id="2b24a-156">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="2b24a-157">Desde allí, elimine la conexión de ServiceNow actual y personalice los nombres de los Estados de las incidencias.</span><span class="sxs-lookup"><span data-stu-id="2b24a-157">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="2b24a-158">Con los vales de ServiceNow visibles en el centro de seguridad de Microsoft 365, las tareas residen en un lugar en el que se puede realizar un seguimiento y actuar junto a otros elementos del panel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2b24a-158">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2b24a-159">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="2b24a-159">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="2b24a-160">Recibe un error en el primer paso de la lista de comprobación de instalación (creación de OAuth)</span><span class="sxs-lookup"><span data-stu-id="2b24a-160">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="2b24a-161">**Mensaje de error**: se rechazó la operación de lectura contra ' oauth_entity ' del ámbito ' x_mioms_m365ticket ' debido a la Directiva de acceso entre ámbitos de la tabla</span><span class="sxs-lookup"><span data-stu-id="2b24a-161">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="2b24a-162">La aplicación supone que cualquier administrador de la instancia de ServiceNow puede crear y leer entidades de OAuth.</span><span class="sxs-lookup"><span data-stu-id="2b24a-162">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="2b24a-163">Este error puede deberse a una personalización en la instancia de ServiceNow, que restringe quién puede crear o leer entidades de OAuth.</span><span class="sxs-lookup"><span data-stu-id="2b24a-163">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="2b24a-164">**ServiceNow recomienda a los usuarios mantener la funcionalidad predeterminada.**</span><span class="sxs-lookup"><span data-stu-id="2b24a-164">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="2b24a-165">Establezca la configuración de la tabla "registros de aplicación" en default:</span><span class="sxs-lookup"><span data-stu-id="2b24a-165">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="2b24a-166">Label = registros de aplicación</span><span class="sxs-lookup"><span data-stu-id="2b24a-166">Label = Application Registeries</span></span>
* <span data-ttu-id="2b24a-167">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="2b24a-167">Name = oauth_entity</span></span>
* <span data-ttu-id="2b24a-168">Accesible desde = todos los ámbitos de aplicación</span><span class="sxs-lookup"><span data-stu-id="2b24a-168">Accessible from = All application scopes</span></span>
* <span data-ttu-id="2b24a-169">Puede leer = casilla de verificación seleccionada</span><span class="sxs-lookup"><span data-stu-id="2b24a-169">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="2b24a-170">Cómo validar la entidad de OAuth creada para el conector de cumplimiento de & de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b24a-170">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="2b24a-171">Vaya a la tabla registros de aplicaciones (**menú > el registro de aplicaciones de oauth > sistema**) en ServiceNow y busque la entidad OAuth que ha creado, con el nombre que le ha asignado.</span><span class="sxs-lookup"><span data-stu-id="2b24a-171">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="2b24a-172">Inicio de sesión como usuario de integración</span><span class="sxs-lookup"><span data-stu-id="2b24a-172">Logging in as the integration user</span></span>

<span data-ttu-id="2b24a-173">Antes de autorizar la conexión entre el centro de seguridad de Microsoft 365 y ServiceNow, asegúrese de usar el inicio de sesión de usuario y la contraseña de integración que creó en los pasos de instalación.</span><span class="sxs-lookup"><span data-stu-id="2b24a-173">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="2b24a-174">No use sus credenciales personales.</span><span class="sxs-lookup"><span data-stu-id="2b24a-174">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="2b24a-175">Vaya a la página de autorización en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-175">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="2b24a-176">Si ha iniciado sesión con sus credenciales personales, seleccione el vínculo **que desee** en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="2b24a-176">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="2b24a-177">Inicie sesión en ServiceNow como el usuario de integración que creó anteriormente a partir de la lista de comprobación de instalación.</span><span class="sxs-lookup"><span data-stu-id="2b24a-177">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="2b24a-178">Seleccione **permitir** en la página de servicenow que pregunta si el conector Security + Compliance Connector puede conectarse a su cuenta de servicenow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-178">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="2b24a-179">Continúe con los pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="2b24a-179">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="2b24a-180">Cómo validar el usuario de integración creado con la lista de comprobación de instalación para el conector de seguridad & cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b24a-180">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="2b24a-181">Vaya a la tabla de usuarios **(menú > User Administration >** users) en ServiceNow y busque el usuario de integración creado por usted, con el nombre que le haya asignado.</span><span class="sxs-lookup"><span data-stu-id="2b24a-181">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="2b24a-182">Su empresa tiene habilitado el inicio de sesión único, lo que le impide conectarse a ServiceNow a través del centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b24a-182">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="2b24a-183">Si su compañía ha habilitado el inicio de sesión único y recibe un error o el inicio de sesión es incorrecto, siga una de las dos soluciones.</span><span class="sxs-lookup"><span data-stu-id="2b24a-183">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="2b24a-184">Inicie sesión en ServiceNow como usuario de integración</span><span class="sxs-lookup"><span data-stu-id="2b24a-184">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="2b24a-185">Vuelva a navegar a la página Authorization en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-185">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="2b24a-186">Seleccione el vínculo **que desee** en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="2b24a-186">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="2b24a-187">Inicie sesión en ServiceNow como el usuario de integración que creó anteriormente a partir de la lista de comprobación de instalación.</span><span class="sxs-lookup"><span data-stu-id="2b24a-187">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="2b24a-188">Seleccione **permitir** en la página de servicenow que pregunta si el conector Security + Compliance Connector puede conectarse a su cuenta de servicenow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-188">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="2b24a-189">Continúe con los pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="2b24a-189">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="2b24a-190">Crear un usuario administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="2b24a-190">Create a security admin user</span></span>

1. <span data-ttu-id="2b24a-191">Cree un usuario con privilegios de administrador de seguridad en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b24a-191">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="2b24a-192">El usuario debe tener el mismo nombre y dirección de correo electrónico que el usuario de integración que ha creado a partir de la lista de comprobación de instalación.</span><span class="sxs-lookup"><span data-stu-id="2b24a-192">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="2b24a-193">Puede quitar el rol de administrador de seguridad una vez que se haya completado el inicio de sesión y la conexión.</span><span class="sxs-lookup"><span data-stu-id="2b24a-193">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="2b24a-194">Inicie sesión en el centro de seguridad 365 de Microsoft como este usuario y siga los pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="2b24a-194">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="2b24a-195">Filtrado IP</span><span class="sxs-lookup"><span data-stu-id="2b24a-195">IP filtering</span></span>

<span data-ttu-id="2b24a-196">Si ha habilitado el filtrado IP, es posible que necesite permitir de forma explícita direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="2b24a-196">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="2b24a-197">Consulte [IP address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) para obtener información sobre cómo permitir intervalos de IP en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2b24a-197">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="2b24a-198">Vea [intervalos IP de Azure y etiquetas de servicio: nube pública](https://www.microsoft.com/en-us/download/details.aspx?id=56519) para obtener una lista de las direcciones IP que se van a permitir.</span><span class="sxs-lookup"><span data-stu-id="2b24a-198">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="2b24a-199">La instalación se ha completado, pero no ve los vales y no se puede compartir</span><span class="sxs-lookup"><span data-stu-id="2b24a-199">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="2b24a-200">Si se han completado los pasos de instalación y configuración, pero no ve las tarjetas de ServiceNow en la Página principal y no puede compartir con ServiceNow desde la puntuación segura de Microsoft, compruebe el estado de la página https://security.microsoft.com/ticketProvisioningde aprovisionamiento en.</span><span class="sxs-lookup"><span data-stu-id="2b24a-200">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="2b24a-201">Seleccione **autorizar** y volver a la Página principal.</span><span class="sxs-lookup"><span data-stu-id="2b24a-201">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="2b24a-202">Deben aparecer las tarjetas.</span><span class="sxs-lookup"><span data-stu-id="2b24a-202">The cards should appear.</span></span>

