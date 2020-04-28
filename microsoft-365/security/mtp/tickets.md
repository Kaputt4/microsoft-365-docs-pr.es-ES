---
title: Crear y realizar un seguimiento de las entradas a través de ServiceNow
description: El centro de seguridad 365 de Microsoft se está optimizando con la capacidad de crear y realizar un seguimiento de vales en ServiceNow de forma nativa. Los administradores de seguridad pueden enviar una recomendación de puntuación segura directamente a ServiceNow y crear un vale.
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
ms.openlocfilehash: eb6af6b11d2d932f3bd2165aa3f597c14feb5ae8
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901027"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="25719-105">Administrar tickets a través de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="25719-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="25719-106">ServiceNow es una plataforma de informática en la nube popular que ayuda a las empresas a administrar flujos de trabajo digitales para operaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="25719-106">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="25719-107">Su plataforma ahora tiene flujos de trabajo de ti, flujos de trabajo de empleados y flujos de trabajo de clientes.</span><span class="sxs-lookup"><span data-stu-id="25719-107">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> <span data-ttu-id="25719-108">Microsoft se ha asociado con ServiceNow para facilitar a los administradores de ti la administración de sus billetes y tareas en ambas plataformas.</span><span class="sxs-lookup"><span data-stu-id="25719-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> [<span data-ttu-id="25719-109">Obtenga más información sobre ServiceNow</span><span class="sxs-lookup"><span data-stu-id="25719-109">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="25719-110">Microsoft 365 Security Center ahora se ha mejorado con la capacidad de crear y realizar un seguimiento de vales en ServiceNow de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="25719-110">Microsoft 365 security center is now enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="25719-111">Los administradores de seguridad pueden enviar una acción de mejora de la [puntuación segura de Microsoft](microsoft-secure-score.md) directamente a ServiceNow y crear un vale.</span><span class="sxs-lookup"><span data-stu-id="25719-111">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="25719-112">Se pueden crear tíquets de administración de incidentes y de administración de cambios.</span><span class="sxs-lookup"><span data-stu-id="25719-112">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="25719-113">A continuación, se puede realizar un seguimiento en la Página principal del centro de seguridad de Microsoft y en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="25719-113">They can then be tracked in the Microsoft security center home page, and ServiceNow.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="25719-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="25719-114">Prerequisites</span></span>

<span data-ttu-id="25719-115">Tener acceso al centro de seguridad 365 de Microsoft y a una instancia de ServiceNow con:</span><span class="sxs-lookup"><span data-stu-id="25719-115">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="25719-116">Kingston o una versión superior</span><span class="sxs-lookup"><span data-stu-id="25719-116">Kingston or higher version</span></span>
* <span data-ttu-id="25719-117">Tener credenciales de admin HI</span><span class="sxs-lookup"><span data-stu-id="25719-117">Have admin HI credentials</span></span>
* <span data-ttu-id="25719-118">Tener privilegios de administrador en la instancia del proveedor de destino</span><span class="sxs-lookup"><span data-stu-id="25719-118">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="25719-119">ServiceNow recomienda que los usuarios conserven la configuración predeterminada en su instancia de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="25719-119">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="25719-120">La realización de personalizaciones puede provocar errores al completar la lista de comprobación de instalación e integración con el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="25719-120">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="25719-121">Intercambio de datos</span><span class="sxs-lookup"><span data-stu-id="25719-121">Data exchange</span></span>

<span data-ttu-id="25719-122">Cuando conecta el centro de seguridad de Microsoft 365 a ServiceNow, Microsoft recibe los siguientes datos adicionales:</span><span class="sxs-lookup"><span data-stu-id="25719-122">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="25719-123">Nombre de instancia de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="25719-123">ServiceNow instance name</span></span>
* <span data-ttu-id="25719-124">IDENTIFICADOR de cliente de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="25719-124">ServiceNow client ID</span></span>
* <span data-ttu-id="25719-125">Secreto de cliente de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="25719-125">ServiceNow client secret</span></span>
* <span data-ttu-id="25719-126">Tokens de actualización & acceso a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="25719-126">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="25719-127">Cuando se crea un vale de ServiceNow a partir del centro de seguridad 365 de Microsoft, se envían los datos siguientes a ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="25719-127">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="25719-128">IDENTIFICADOR de usuario que inicia la creación de vales</span><span class="sxs-lookup"><span data-stu-id="25719-128">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="25719-129">Nombre de tarea</span><span class="sxs-lookup"><span data-stu-id="25719-129">Task name</span></span>
* <span data-ttu-id="25719-130">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="25719-130">Task description</span></span>
* <span data-ttu-id="25719-131">Priority</span><span class="sxs-lookup"><span data-stu-id="25719-131">Priority</span></span>
* <span data-ttu-id="25719-132">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="25719-132">Due date</span></span>
* <span data-ttu-id="25719-133">Origen de la recomendación (recomendación del usuario o recomendación de Microsoft)</span><span class="sxs-lookup"><span data-stu-id="25719-133">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="25719-134">Categoría de recomendación (dispositivos, datos, aplicaciones, identidad, infraestructura)</span><span class="sxs-lookup"><span data-stu-id="25719-134">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="25719-135">Conectar el centro de seguridad de Microsoft 365 a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="25719-135">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="25719-136">Vaya a la página de inicio del centro de seguridad 365 de Microsoft para ver la tarjeta de conexión de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="25719-136">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![¿Usa ServiceNow?](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="25719-138">Seleccione "conectarse a ServiceNow" para ir a la página de configuración de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="25719-138">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="25719-139">Siga las instrucciones para autorizar la aplicación conector de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="25719-139">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="25719-140">Antes de autorizar la conexión entre el centro de seguridad de Microsoft 365 y ServiceNow, asegúrese de usar el inicio de sesión de usuario y la contraseña de integración que creó en los pasos de instalación.</span><span class="sxs-lookup"><span data-stu-id="25719-140">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="25719-141">No use sus credenciales personales.</span><span class="sxs-lookup"><span data-stu-id="25719-141">Do not use your personal credentials.</span></span>

<span data-ttu-id="25719-142">Una vez que haya seguido las instrucciones y la autorización de la conexión, vea el estado de conexión en la página conexión del centro de seguridad 365 de Microsoft y en la experiencia de la aplicación conector de vales de Microsoft 365 de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="25719-142">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="25719-143">Ahora ya está todo listo para empezar a crear tareas.</span><span class="sxs-lookup"><span data-stu-id="25719-143">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="25719-144">Crear una tarea y compartirla en ServiceNow</span><span class="sxs-lookup"><span data-stu-id="25719-144">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="25719-145">Una vez que la integración esté configurada, cree tareas de ServiceNow basadas en acciones específicas para la mejora de la calificación segura de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="25719-145">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="25719-146">Vaya a cualquier acción de mejora en puntuación segura en el portal del centro de seguridad 365 de Microsoft y seleccione el icono "compartir".</span><span class="sxs-lookup"><span data-stu-id="25719-146">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="25719-147">Una de las opciones de lista desplegable es ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="25719-147">One of the dropdown options is ServiceNow.</span></span>

![Uso compartido de ServiceNow en calificación segura](../../media/servicenow-share.png)

<span data-ttu-id="25719-149">Se genera una tarea en la que puede establecer la prioridad y editar el nombre, la descripción o la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="25719-149">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="25719-150">Una vez que se hayan rellenado todos los campos obligatorios, envíe la tarea a ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="25719-150">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="25719-151">La tarea es visible en ServiceNow como una solicitud de cambio de configuración y seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="25719-151">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="25719-152">Seguimiento de vales</span><span class="sxs-lookup"><span data-stu-id="25719-152">Track tickets</span></span>

<span data-ttu-id="25719-153">Una vez que se han creado los vales de administración de cambios y la administración de cambios de ServiceNow, se muestran en las tarjetas de la página de inicio del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="25719-153">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="25719-154">Desde estas tarjetas, puede crear un vale, ver todos los vales o administrar la configuración de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="25719-154">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Vales de administración de cambios de ServiceNow](../../media/change-management-375.png)  ![Vales de administración de incidentes de ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="25719-157">Para volver a aprovisionar o administrar la integración de ServiceNow en el centro de seguridad de Microsoft 365, seleccione **administrar la configuración de servicenow** en una de las tarjetas.</span><span class="sxs-lookup"><span data-stu-id="25719-157">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="25719-158">Desde allí, elimine la conexión de ServiceNow actual y personalice los nombres de los Estados de las incidencias.</span><span class="sxs-lookup"><span data-stu-id="25719-158">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="25719-159">Con los vales de ServiceNow visibles en el centro de seguridad de Microsoft 365, las tareas residen en un lugar en el que se puede realizar un seguimiento y actuar junto a otros elementos del panel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="25719-159">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="25719-160">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="25719-160">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="25719-161">Recibe un error en el primer paso de la lista de comprobación de instalación (creación de OAuth)</span><span class="sxs-lookup"><span data-stu-id="25719-161">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="25719-162">**Mensaje de error**: se rechazó la operación de lectura contra ' oauth_entity ' del ámbito ' x_mioms_m365ticket ' debido a la Directiva de acceso entre ámbitos de la tabla</span><span class="sxs-lookup"><span data-stu-id="25719-162">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="25719-163">La aplicación supone que cualquier administrador de la instancia de ServiceNow puede crear y leer entidades de OAuth.</span><span class="sxs-lookup"><span data-stu-id="25719-163">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="25719-164">Este error puede deberse a una personalización en la instancia de ServiceNow, que restringe quién puede crear o leer entidades de OAuth.</span><span class="sxs-lookup"><span data-stu-id="25719-164">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="25719-165">**ServiceNow recomienda a los usuarios mantener la funcionalidad predeterminada.**</span><span class="sxs-lookup"><span data-stu-id="25719-165">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="25719-166">Establezca la configuración de la tabla "registros de aplicación" en default:</span><span class="sxs-lookup"><span data-stu-id="25719-166">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="25719-167">Label = registros de aplicación</span><span class="sxs-lookup"><span data-stu-id="25719-167">Label = Application Registeries</span></span>
* <span data-ttu-id="25719-168">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="25719-168">Name = oauth_entity</span></span>
* <span data-ttu-id="25719-169">Accesible desde = todos los ámbitos de aplicación</span><span class="sxs-lookup"><span data-stu-id="25719-169">Accessible from = All application scopes</span></span>
* <span data-ttu-id="25719-170">Puede leer = casilla de verificación seleccionada</span><span class="sxs-lookup"><span data-stu-id="25719-170">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="25719-171">Cómo validar la entidad de OAuth creada para el conector de cumplimiento de & de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="25719-171">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="25719-172">Vaya a la tabla registros de aplicaciones (**menú > el registro de aplicaciones de oauth > sistema**) en ServiceNow y busque la entidad OAuth que ha creado, con el nombre que le ha asignado.</span><span class="sxs-lookup"><span data-stu-id="25719-172">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="25719-173">Inicio de sesión como usuario de integración</span><span class="sxs-lookup"><span data-stu-id="25719-173">Logging in as the integration user</span></span>

<span data-ttu-id="25719-174">Antes de autorizar la conexión entre el centro de seguridad de Microsoft 365 y ServiceNow, asegúrese de usar el inicio de sesión de usuario y la contraseña de integración que creó en los pasos de instalación.</span><span class="sxs-lookup"><span data-stu-id="25719-174">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="25719-175">No use sus credenciales personales.</span><span class="sxs-lookup"><span data-stu-id="25719-175">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="25719-176">Vaya a la página de autorización en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="25719-176">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="25719-177">Si ha iniciado sesión con sus credenciales personales, seleccione el vínculo **que desee** en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="25719-177">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="25719-178">Inicie sesión en ServiceNow como el usuario de integración que creó anteriormente a partir de la lista de comprobación de instalación.</span><span class="sxs-lookup"><span data-stu-id="25719-178">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="25719-179">Seleccione **permitir** en la página de servicenow que pregunta si el conector Security + Compliance Connector puede conectarse a su cuenta de servicenow.</span><span class="sxs-lookup"><span data-stu-id="25719-179">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="25719-180">Continúe con los pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="25719-180">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="25719-181">Cómo validar el usuario de integración creado con la lista de comprobación de instalación para el conector de seguridad & cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="25719-181">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="25719-182">Vaya a la tabla de usuarios **(menú > User Administration >** users) en ServiceNow y busque el usuario de integración creado por usted, con el nombre que le haya asignado.</span><span class="sxs-lookup"><span data-stu-id="25719-182">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="25719-183">Su empresa tiene habilitado el inicio de sesión único, lo que le impide conectarse a ServiceNow a través del centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="25719-183">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="25719-184">Si su compañía ha habilitado el inicio de sesión único y recibe un error o el inicio de sesión es incorrecto, siga una de las dos soluciones.</span><span class="sxs-lookup"><span data-stu-id="25719-184">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="25719-185">Inicie sesión en ServiceNow como usuario de integración</span><span class="sxs-lookup"><span data-stu-id="25719-185">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="25719-186">Vuelva a navegar a la página Authorization en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="25719-186">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="25719-187">Seleccione el vínculo **que desee** en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="25719-187">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="25719-188">Inicie sesión en ServiceNow como el usuario de integración que creó anteriormente a partir de la lista de comprobación de instalación.</span><span class="sxs-lookup"><span data-stu-id="25719-188">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="25719-189">Seleccione **permitir** en la página de servicenow que pregunta si el conector Security + Compliance Connector puede conectarse a su cuenta de servicenow.</span><span class="sxs-lookup"><span data-stu-id="25719-189">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="25719-190">Continúe con los pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="25719-190">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="25719-191">Crear un usuario administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="25719-191">Create a security admin user</span></span>

1. <span data-ttu-id="25719-192">Cree un usuario con privilegios de administrador de seguridad en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="25719-192">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="25719-193">El usuario debe tener el mismo nombre y dirección de correo electrónico que el usuario de integración que ha creado a partir de la lista de comprobación de instalación.</span><span class="sxs-lookup"><span data-stu-id="25719-193">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="25719-194">Puede quitar el rol de administrador de seguridad una vez que se haya completado el inicio de sesión y la conexión.</span><span class="sxs-lookup"><span data-stu-id="25719-194">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="25719-195">Inicie sesión en el centro de seguridad 365 de Microsoft como este usuario y siga los pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="25719-195">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="25719-196">Filtrado IP</span><span class="sxs-lookup"><span data-stu-id="25719-196">IP filtering</span></span>

<span data-ttu-id="25719-197">Si ha habilitado el filtrado IP, es posible que necesite permitir de forma explícita direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="25719-197">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="25719-198">Consulte [IP address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) para obtener información sobre cómo permitir intervalos de IP en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="25719-198">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="25719-199">Vea [intervalos IP de Azure y etiquetas de servicio: nube pública](https://www.microsoft.com/en-us/download/details.aspx?id=56519) para obtener una lista de las direcciones IP que se van a permitir.</span><span class="sxs-lookup"><span data-stu-id="25719-199">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="25719-200">La instalación se ha completado, pero no ve los vales y no se puede compartir</span><span class="sxs-lookup"><span data-stu-id="25719-200">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="25719-201">Si se han completado los pasos de instalación y configuración, pero no ve las tarjetas de ServiceNow en la Página principal y no puede compartir con ServiceNow desde la puntuación segura de Microsoft, compruebe el estado de la página https://security.microsoft.com/ticketProvisioningde aprovisionamiento en.</span><span class="sxs-lookup"><span data-stu-id="25719-201">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="25719-202">Seleccione **autorizar** y volver a la Página principal.</span><span class="sxs-lookup"><span data-stu-id="25719-202">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="25719-203">Deben aparecer las tarjetas.</span><span class="sxs-lookup"><span data-stu-id="25719-203">The cards should appear.</span></span>

