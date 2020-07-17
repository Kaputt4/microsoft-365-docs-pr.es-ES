---
title: Integrar los vales de ServiceNow en el centro de seguridad y cumplimiento de Microsoft 365
description: Obtenga información sobre cómo crear y realizar un seguimiento de vales en ServiceNow desde el centro de seguridad y el centro de cumplimiento de Microsoft 365.
keywords: seguridad, Microsoft 365, M365, cumplimiento, centro de cumplimiento, centro de seguridad, ServiceNow, billetes, tareas, nieve, conexión
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
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086672"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="8d67b-104">Integrar los vales de ServiceNow en el centro de seguridad y cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d67b-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8d67b-105">ServiceNow es una plataforma de informática en la nube popular que ayuda a las empresas a administrar flujos de trabajo digitales para operaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="8d67b-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="8d67b-106">Su plataforma ahora tiene flujos de trabajo de ti, flujos de trabajo de empleados y flujos de trabajo de clientes.</span><span class="sxs-lookup"><span data-stu-id="8d67b-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="8d67b-107">Obtenga más información sobre ServiceNow</span><span class="sxs-lookup"><span data-stu-id="8d67b-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="8d67b-108">Microsoft se ha asociado con ServiceNow para facilitar a los administradores de ti la administración de sus billetes y tareas en ambas plataformas.</span><span class="sxs-lookup"><span data-stu-id="8d67b-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="8d67b-109">El [centro de seguridad 365](overview-security-center.md) de Microsoft y el [centro de cumplimiento de Microsoft 365](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) están mejorados con la capacidad de crear y realizar un seguimiento de vales en ServiceNow de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="8d67b-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="8d67b-110">**Administración de vales de ServiceNow en el centro de seguridad**</span><span class="sxs-lookup"><span data-stu-id="8d67b-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="8d67b-111">**Administrar vales de ServiceNow en el centro de cumplimiento** (próximamente)</span><span class="sxs-lookup"><span data-stu-id="8d67b-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d67b-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8d67b-112">Prerequisites</span></span>

<span data-ttu-id="8d67b-113">Tener acceso al centro de seguridad de Microsoft 365 o al centro de cumplimiento y a una instancia de ServiceNow con:</span><span class="sxs-lookup"><span data-stu-id="8d67b-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="8d67b-114">Kingston o una versión superior</span><span class="sxs-lookup"><span data-stu-id="8d67b-114">Kingston or higher version</span></span>
* <span data-ttu-id="8d67b-115">Tener credenciales de admin HI</span><span class="sxs-lookup"><span data-stu-id="8d67b-115">Have admin HI credentials</span></span>
* <span data-ttu-id="8d67b-116">Tener privilegios de administrador en la instancia del proveedor de destino</span><span class="sxs-lookup"><span data-stu-id="8d67b-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="8d67b-117">ServiceNow recomienda que los usuarios conserven la configuración predeterminada en su instancia de ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="8d67b-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="8d67b-118">La realización de personalizaciones puede provocar errores al completar la lista de comprobación de instalación e integración con el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d67b-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="8d67b-119">Intercambio de datos</span><span class="sxs-lookup"><span data-stu-id="8d67b-119">Data exchange</span></span>

<span data-ttu-id="8d67b-120">Cuando conecta el centro de seguridad de Microsoft 365 o el centro de cumplimiento a ServiceNow, Microsoft recibe los siguientes datos adicionales:</span><span class="sxs-lookup"><span data-stu-id="8d67b-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="8d67b-121">Nombre de instancia de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="8d67b-121">ServiceNow instance name</span></span>
* <span data-ttu-id="8d67b-122">IDENTIFICADOR de cliente de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="8d67b-122">ServiceNow client ID</span></span>
* <span data-ttu-id="8d67b-123">Secreto de cliente de ServiceNow</span><span class="sxs-lookup"><span data-stu-id="8d67b-123">ServiceNow client secret</span></span>
* <span data-ttu-id="8d67b-124">Tokens de actualización & acceso a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="8d67b-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="8d67b-125">Al crear un vale de ServiceNow desde el centro de seguridad de Microsoft 365 o el centro de cumplimiento, se envían los siguientes datos a ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="8d67b-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="8d67b-126">IDENTIFICADOR de usuario que inicia la creación de vales</span><span class="sxs-lookup"><span data-stu-id="8d67b-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="8d67b-127">Nombre de tarea</span><span class="sxs-lookup"><span data-stu-id="8d67b-127">Task name</span></span>
* <span data-ttu-id="8d67b-128">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="8d67b-128">Task description</span></span>
* <span data-ttu-id="8d67b-129">Priority</span><span class="sxs-lookup"><span data-stu-id="8d67b-129">Priority</span></span>
* <span data-ttu-id="8d67b-130">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="8d67b-130">Due date</span></span>
* <span data-ttu-id="8d67b-131">Origen de la recomendación (recomendación del usuario o recomendación de Microsoft)</span><span class="sxs-lookup"><span data-stu-id="8d67b-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="8d67b-132">Categoría de recomendación (dispositivos, datos, aplicaciones, identidad, infraestructura)</span><span class="sxs-lookup"><span data-stu-id="8d67b-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="8d67b-133">Conectarse a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="8d67b-133">Connect to ServiceNow</span></span>

<span data-ttu-id="8d67b-134">Vaya a [crear y realizar un seguimiento de los vales de ServiceNow en el centro de seguridad de Microsoft 365](tickets-security-center.md) para obtener información sobre cómo conectarse a ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="8d67b-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="8d67b-135">La conexión desde el centro de cumplimiento de Microsoft 365 estará disponible próximamente.</span><span class="sxs-lookup"><span data-stu-id="8d67b-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8d67b-136">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="8d67b-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="8d67b-137">Recibe un error en el primer paso de la lista de comprobación de instalación (creación de OAuth)</span><span class="sxs-lookup"><span data-stu-id="8d67b-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="8d67b-138">**Mensaje de error**: se rechazó la operación de lectura contra ' oauth_entity ' del ámbito ' x_mioms_m365ticket ' debido a la Directiva de acceso entre ámbitos de la tabla</span><span class="sxs-lookup"><span data-stu-id="8d67b-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="8d67b-139">La aplicación supone que cualquier administrador de la instancia de ServiceNow puede crear y leer entidades de OAuth.</span><span class="sxs-lookup"><span data-stu-id="8d67b-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="8d67b-140">Este error puede deberse a una personalización en la instancia de ServiceNow, que restringe quién puede crear o leer entidades de OAuth.</span><span class="sxs-lookup"><span data-stu-id="8d67b-140">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="8d67b-141">**ServiceNow recomienda a los usuarios mantener la funcionalidad predeterminada.**</span><span class="sxs-lookup"><span data-stu-id="8d67b-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="8d67b-142">Establezca la configuración de la tabla "registros de aplicación" en default:</span><span class="sxs-lookup"><span data-stu-id="8d67b-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="8d67b-143">Label = registros de aplicación</span><span class="sxs-lookup"><span data-stu-id="8d67b-143">Label = Application Registeries</span></span>
* <span data-ttu-id="8d67b-144">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="8d67b-144">Name = oauth_entity</span></span>
* <span data-ttu-id="8d67b-145">Accesible desde = todos los ámbitos de aplicación</span><span class="sxs-lookup"><span data-stu-id="8d67b-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="8d67b-146">Puede leer = casilla de verificación seleccionada</span><span class="sxs-lookup"><span data-stu-id="8d67b-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="8d67b-147">Cómo validar la entidad de OAuth creada para el conector de cumplimiento de & de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d67b-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="8d67b-148">Vaya a la tabla registros de aplicaciones (**menú > el registro de aplicaciones de oauth > sistema**) en ServiceNow y busque la entidad OAuth que ha creado, con el nombre que le ha asignado.</span><span class="sxs-lookup"><span data-stu-id="8d67b-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="8d67b-149">Inicio de sesión como usuario de integración</span><span class="sxs-lookup"><span data-stu-id="8d67b-149">Logging in as the integration user</span></span>

<span data-ttu-id="8d67b-150">Antes de autorizar la conexión entre el centro de seguridad de Microsoft 365 y ServiceNow, asegúrese de usar el inicio de sesión de usuario y la contraseña de integración que creó en los pasos de instalación.</span><span class="sxs-lookup"><span data-stu-id="8d67b-150">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="8d67b-151">No use sus credenciales personales.</span><span class="sxs-lookup"><span data-stu-id="8d67b-151">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="8d67b-152">Vaya a la página de autorización en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="8d67b-152">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="8d67b-153">Si ha iniciado sesión con sus credenciales personales, seleccione el vínculo **que desee** en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="8d67b-153">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="8d67b-154">Inicie sesión en ServiceNow como el usuario de integración que creó anteriormente a partir de la lista de comprobación de instalación.</span><span class="sxs-lookup"><span data-stu-id="8d67b-154">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="8d67b-155">Seleccione **permitir** en la página de servicenow que pregunta si el conector Security + Compliance Connector puede conectarse a su cuenta de servicenow.</span><span class="sxs-lookup"><span data-stu-id="8d67b-155">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="8d67b-156">Continúe con los pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="8d67b-156">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="8d67b-157">Cómo validar el usuario de integración creado con la lista de comprobación de instalación para el conector de seguridad & cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d67b-157">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="8d67b-158">Vaya a la tabla de usuarios **(menú > User Administration >** users) en ServiceNow y busque el usuario de integración creado por usted, con el nombre que le haya asignado.</span><span class="sxs-lookup"><span data-stu-id="8d67b-158">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="8d67b-159">Su empresa tiene habilitado el inicio de sesión único, lo que le impide conectarse a ServiceNow a través del centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d67b-159">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="8d67b-160">Si su compañía ha habilitado el inicio de sesión único y recibe un error o el inicio de sesión es incorrecto, siga una de las dos soluciones.</span><span class="sxs-lookup"><span data-stu-id="8d67b-160">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="8d67b-161">Inicie sesión en ServiceNow como usuario de integración</span><span class="sxs-lookup"><span data-stu-id="8d67b-161">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="8d67b-162">Vuelva a navegar a la página Authorization en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="8d67b-162">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="8d67b-163">Seleccione el vínculo **que desee** en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="8d67b-163">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="8d67b-164">Inicie sesión en ServiceNow como el usuario de integración que creó anteriormente a partir de la lista de comprobación de instalación.</span><span class="sxs-lookup"><span data-stu-id="8d67b-164">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="8d67b-165">Seleccione **permitir** en la página de servicenow que pregunta si el conector Security + Compliance Connector puede conectarse a su cuenta de servicenow.</span><span class="sxs-lookup"><span data-stu-id="8d67b-165">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="8d67b-166">Continúe con los pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="8d67b-166">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="8d67b-167">Crear un usuario administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="8d67b-167">Create a security admin user</span></span>

1. <span data-ttu-id="8d67b-168">Cree un usuario con privilegios de administrador de seguridad en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8d67b-168">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="8d67b-169">El usuario debe tener el mismo nombre y dirección de correo electrónico que el usuario de integración que ha creado a partir de la lista de comprobación de instalación.</span><span class="sxs-lookup"><span data-stu-id="8d67b-169">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="8d67b-170">Puede quitar el rol de administrador de seguridad una vez que se haya completado el inicio de sesión y la conexión.</span><span class="sxs-lookup"><span data-stu-id="8d67b-170">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="8d67b-171">Inicie sesión en el centro de seguridad 365 de Microsoft como este usuario y siga los pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="8d67b-171">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="8d67b-172">Filtrado IP</span><span class="sxs-lookup"><span data-stu-id="8d67b-172">IP filtering</span></span>

<span data-ttu-id="8d67b-173">Si ha habilitado el filtrado IP, es posible que necesite permitir de forma explícita direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="8d67b-173">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="8d67b-174">Consulte [IP address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) para obtener información sobre cómo permitir intervalos de IP en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="8d67b-174">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="8d67b-175">Vea [intervalos IP de Azure y etiquetas de servicio: nube pública](https://www.microsoft.com/en-us/download/details.aspx?id=56519) para obtener una lista de las direcciones IP que se van a permitir.</span><span class="sxs-lookup"><span data-stu-id="8d67b-175">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="8d67b-176">La instalación se ha completado, pero no ve los vales y no se puede compartir</span><span class="sxs-lookup"><span data-stu-id="8d67b-176">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="8d67b-177">Si se han completado los pasos de instalación y configuración, pero no ve las tarjetas de ServiceNow en la Página principal y no puede compartir con ServiceNow desde la puntuación segura de Microsoft, compruebe el estado de la página de aprovisionamiento en https://security.microsoft.com/ticketProvisioning .</span><span class="sxs-lookup"><span data-stu-id="8d67b-177">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="8d67b-178">Seleccione **autorizar** y volver a la Página principal.</span><span class="sxs-lookup"><span data-stu-id="8d67b-178">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="8d67b-179">Deben aparecer las tarjetas.</span><span class="sxs-lookup"><span data-stu-id="8d67b-179">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="8d67b-180">Recursos</span><span class="sxs-lookup"><span data-stu-id="8d67b-180">Resources</span></span>

- [<span data-ttu-id="8d67b-181">Administración de vales de ServiceNow en el centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="8d67b-181">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)