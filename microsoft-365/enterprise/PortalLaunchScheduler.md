---
title: Iniciar el portal con el programador de inicio del portal
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: En este artículo se describe cómo iniciar el portal con el programador de inicio del portal
ms.openlocfilehash: bf01f6ae93b424543a6a509f89961a1b7a0c9ad7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841671"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="f83d9-103">Inicie el portal con el programador de inicio SharePoint portal de inicio</span><span class="sxs-lookup"><span data-stu-id="f83d9-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="f83d9-104">Un portal es un sitio de comunicación SharePoint en la intranet que es de alto tráfico, un sitio que tiene entre 10.000 y más de 100.000 espectadores en el transcurso de varias semanas.</span><span class="sxs-lookup"><span data-stu-id="f83d9-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="f83d9-105">Use el programador de inicio del portal para iniciar el portal para garantizar que los usuarios tengan una experiencia de visualización fluida al obtener acceso a su nuevo SharePoint portal.</span><span class="sxs-lookup"><span data-stu-id="f83d9-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="f83d9-106">El programador de inicio del portal está diseñado para ayudarle a seguir un enfoque de implementación por fases mediante el procesamiento por lotes de visores en oleadas y la administración de los redireccionamientos de dirección URL para el nuevo portal.</span><span class="sxs-lookup"><span data-stu-id="f83d9-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="f83d9-107">Durante el inicio de cada oleada, puede recopilar comentarios de los usuarios, supervisar el rendimiento del portal y pausar el inicio para resolver problemas antes de continuar con la siguiente oleada.</span><span class="sxs-lookup"><span data-stu-id="f83d9-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="f83d9-108">Obtenga más información sobre cómo [planear un inicio de portal en SharePoint](/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="f83d9-108">Learn more about how to [plan a portal launch in SharePoint](/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span>

<span data-ttu-id="f83d9-109">**Hay dos tipos de redirección:**</span><span class="sxs-lookup"><span data-stu-id="f83d9-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="f83d9-110">**Bidireccional: inicie** un nuevo portal de SharePoint moderno para reemplazar un portal SharePoint clásico o moderno</span><span class="sxs-lookup"><span data-stu-id="f83d9-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="f83d9-111">**Redirigir a una página temporal:** inicie un nuevo portal de SharePoint moderno sin un portal SharePoint existente</span><span class="sxs-lookup"><span data-stu-id="f83d9-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="f83d9-112">Los permisos de sitio deben configurarse por separado de las oleadas como parte del inicio.</span><span class="sxs-lookup"><span data-stu-id="f83d9-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="f83d9-113">Por ejemplo, si va a liberar un portal para toda la organización, puede establecer permisos en "Todos excepto los usuarios externos", a continuación, separar los usuarios en oleadas mediante grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f83d9-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="f83d9-114">Agregar un grupo de seguridad a una ola no proporciona a ese grupo de seguridad acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="f83d9-114">Adding a security group to a wave does not give that security group access to the site.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f83d9-115">Esta característica será accesible desde el panel **de Configuración** en la página principal de los sitios de comunicación de SharePoint para clientes de lanzamiento dirigido a partir de mayo de 2021 y estará disponible para todos los clientes en julio de 2021</span><span class="sxs-lookup"><span data-stu-id="f83d9-115">This feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="f83d9-116">La versión de PowerShell de esta herramienta está disponible hoy</span><span class="sxs-lookup"><span data-stu-id="f83d9-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="f83d9-117">Esta característica solo se puede usar en sitios de comunicación SharePoint modernos</span><span class="sxs-lookup"><span data-stu-id="f83d9-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="f83d9-118">Debe tener permisos de propietario del sitio para que el sitio personalice y programe el inicio de un portal</span><span class="sxs-lookup"><span data-stu-id="f83d9-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="f83d9-119">Los inicios deben programarse con al menos siete días de antelación y cada oleada puede durar entre uno y siete días.</span><span class="sxs-lookup"><span data-stu-id="f83d9-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="f83d9-120">El número de oleadas requeridas se determina automáticamente por el número esperado de usuarios</span><span class="sxs-lookup"><span data-stu-id="f83d9-120">The number of waves required is automatically determined by the expected number of users</span></span>
> - <span data-ttu-id="f83d9-121">Antes de programar el inicio de un portal, se debe ejecutar la herramienta Diagnóstico [de](https://aka.ms/perftool) página para SharePoint para comprobar que la página principal del sitio está en buen estado</span><span class="sxs-lookup"><span data-stu-id="f83d9-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="f83d9-122">Al final del inicio, todos los usuarios con permisos para el sitio podrán acceder al nuevo sitio</span><span class="sxs-lookup"><span data-stu-id="f83d9-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="f83d9-123">Si su organización usa [Viva Connections,](/SharePoint/viva-connections)es posible que los usuarios vean el icono de su organización en la barra de aplicaciones de Microsoft Teams, pero cuando el icono esté seleccionado los usuarios no podrán acceder al portal hasta que se haya iniciado la ola.</span><span class="sxs-lookup"><span data-stu-id="f83d9-123">If your organization is using [Viva Connections](/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="f83d9-124">Esta característica no está disponible para Office 365 Alemania, Office 365 operado por 21Vianet (China) o Microsoft 365 planes del Gobierno de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="f83d9-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

## <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="f83d9-125">Comprender las diferencias entre las opciones del programador de inicio del portal:</span><span class="sxs-lookup"><span data-stu-id="f83d9-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="f83d9-126">Anteriormente, los inicios del portal solo se podían programar a través SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f83d9-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="f83d9-127">Ahora, tiene dos opciones para ayudarle a programar y administrar el inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="f83d9-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="f83d9-128">Obtenga información sobre las diferencias clave entre ambas herramientas:</span><span class="sxs-lookup"><span data-stu-id="f83d9-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="f83d9-129">**SharePoint Versión de PowerShell:**</span><span class="sxs-lookup"><span data-stu-id="f83d9-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="f83d9-130">Las credenciales de administrador son necesarias para [usar SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="f83d9-130">Admin credentials are required to use [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)</span></span>
- <span data-ttu-id="f83d9-131">Requisito mínimo de una ola</span><span class="sxs-lookup"><span data-stu-id="f83d9-131">Minimum requirement of one wave</span></span>
- <span data-ttu-id="f83d9-132">Programar el inicio en función de la zona horaria universal coordinada (UTC)</span><span class="sxs-lookup"><span data-stu-id="f83d9-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="f83d9-133">**Versión del producto:**</span><span class="sxs-lookup"><span data-stu-id="f83d9-133">**In-product version:**</span></span>

- <span data-ttu-id="f83d9-134">Las credenciales del propietario del sitio son necesarias</span><span class="sxs-lookup"><span data-stu-id="f83d9-134">Site owner credentials are required</span></span>
- <span data-ttu-id="f83d9-135">Requisito mínimo de dos oleadas</span><span class="sxs-lookup"><span data-stu-id="f83d9-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="f83d9-136">Programar el inicio en función de la zona horaria local del portal, tal como se indica en la configuración regional</span><span class="sxs-lookup"><span data-stu-id="f83d9-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>

## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="f83d9-137">Introducción al programador de inicio del portal</span><span class="sxs-lookup"><span data-stu-id="f83d9-137">Get started using the Portal launch scheduler</span></span>

1. <span data-ttu-id="f83d9-138">Antes de usar la herramienta programador de inicio del [portal,](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) agregue todos los usuarios que necesiten acceso a este sitio a través de permisos de sitio como propietario del sitio, miembro del sitio o visitante. </span><span class="sxs-lookup"><span data-stu-id="f83d9-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2. <span data-ttu-id="f83d9-139">A continuación, comience a programar el inicio del portal accediendo al programador de inicio del portal de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="f83d9-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

   <span data-ttu-id="f83d9-140">**Opción 1:** las primeras veces que edite y vuelva a publicar los cambios en la página principal (o hasta la versión 3.0 de la página principal) se le pedirá que use la herramienta programador de inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="f83d9-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="f83d9-141">Seleccione **Programar inicio** para avanzar con la programación.</span><span class="sxs-lookup"><span data-stu-id="f83d9-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="f83d9-142">O **bien, seleccione Volver a publicar** para volver a publicar las ediciones de la página sin programar el inicio.</span><span class="sxs-lookup"><span data-stu-id="f83d9-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>

   ![Imagen del símbolo del sistema para usar el programador de inicio del portal al volver a publicar la página principal](../media/portal-launch-republish-2.png)

   <span data-ttu-id="f83d9-144">**Opción 2:** En cualquier momento, puede navegar a la página principal del sitio  de comunicación de SharePoint, seleccionar **Configuración** y, a continuación, programar el inicio del sitio para programar el inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="f83d9-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>

   ![Imagen del panel Configuración con Programar un inicio de sitio resaltado](../media/portal-launch-settings-2.png)

3. <span data-ttu-id="f83d9-146">A continuación, confirme la puntuación de mantenimiento del portal y realice mejoras en el portal si es necesario mediante la herramienta Diagnóstico [de](https://aka.ms/perftool) página para SharePoint hasta que el portal reciba una **puntuación en** buen estado.</span><span class="sxs-lookup"><span data-stu-id="f83d9-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="f83d9-147">A continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f83d9-147">Then, select **Next**.</span></span>

   ![Imagen de la herramienta programador de inicio de portal](../media/portal-launch-panel-2.png)

   > [!NOTE]
   > <span data-ttu-id="f83d9-149">El nombre y la descripción del sitio no se pueden editar desde  el programador  de inicio del portal y, en su lugar, se pueden cambiar seleccionando Configuración y, a continuación, la información del sitio de la página principal.</span><span class="sxs-lookup"><span data-stu-id="f83d9-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>

4. <span data-ttu-id="f83d9-150">Seleccione el **número de usuarios esperados** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f83d9-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="f83d9-151">Esta figura representa el número de usuarios que probablemente necesitarán acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="f83d9-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="f83d9-152">El programador de inicio del portal determinará automáticamente el número ideal de oleadas en función de los usuarios esperados como este:</span><span class="sxs-lookup"><span data-stu-id="f83d9-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>

   - <span data-ttu-id="f83d9-153">Menos de 10.000 usuarios: dos oleadas</span><span class="sxs-lookup"><span data-stu-id="f83d9-153">Less than 10k users: Two waves</span></span>
   - <span data-ttu-id="f83d9-154">Usuarios de 10 a 30 k: tres oleadas</span><span class="sxs-lookup"><span data-stu-id="f83d9-154">10k to 30k users: Three waves</span></span>
   - <span data-ttu-id="f83d9-155">Usuarios de entre 30 y 100 k: cinco oleadas</span><span class="sxs-lookup"><span data-stu-id="f83d9-155">30k+ to 100k users: Five waves</span></span>
   - <span data-ttu-id="f83d9-156">Más de 100.000 usuarios: cinco oleadas y póngase en contacto con Microsoft a través de los pasos enumerados en la sección Iniciar portal con más de 100.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="f83d9-156">More than 100k users: Five waves and contact your Microsoft via the steps listed in Launch portal with over 100k users section.</span></span>

5. <span data-ttu-id="f83d9-157">A continuación, determine **el tipo de redireccionamiento** necesario:</span><span class="sxs-lookup"><span data-stu-id="f83d9-157">Then, determine the **Type of redirect** needed:</span></span>

   <span data-ttu-id="f83d9-158">**Opción 1: Enviar** usuarios a una página de SharePoint existente (bidireccional): use esta opción al iniciar un nuevo portal SharePoint moderno para reemplazar un portal de SharePoint existente.</span><span class="sxs-lookup"><span data-stu-id="f83d9-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="f83d9-159">Los usuarios en oleadas activas se redirigirán al nuevo sitio independientemente de si navegan al sitio antiguo o nuevo.</span><span class="sxs-lookup"><span data-stu-id="f83d9-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="f83d9-160">Los usuarios de una oleada no iniciada que intenten acceder al nuevo sitio se redirigirán de nuevo al sitio antiguo hasta que se inicia la oleada.</span><span class="sxs-lookup"><span data-stu-id="f83d9-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f83d9-161">Al usar la opción bidireccional, la persona que programa el inicio también debe tener permisos de propietario del sitio en el otro portal SharePoint web.</span><span class="sxs-lookup"><span data-stu-id="f83d9-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>

   <span data-ttu-id="f83d9-162">Opción 2: Enviar usuarios a una página temporal **autogenerada (redirección** temporal de páginas): se debe usar una redirección de página temporal cuando no exista ningún portal de SharePoint página existente.</span><span class="sxs-lookup"><span data-stu-id="f83d9-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="f83d9-163">Los usuarios se dirigen a un nuevo portal de SharePoint moderno y si un usuario está en una ola que no se ha iniciado, se redirigirá a una página temporal.</span><span class="sxs-lookup"><span data-stu-id="f83d9-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>

   <span data-ttu-id="f83d9-164">**Opción 3: Enviar** usuarios a una página externa: proporcionar una dirección URL externa a una experiencia de página de aterrizaje temporal hasta que se inicia la ola del usuario.</span><span class="sxs-lookup"><span data-stu-id="f83d9-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>

6. <span data-ttu-id="f83d9-165">Divide tu audiencia en oleadas.</span><span class="sxs-lookup"><span data-stu-id="f83d9-165">Break up your audience into waves.</span></span> <span data-ttu-id="f83d9-166">Agregue hasta 20 grupos de seguridad por oleada.</span><span class="sxs-lookup"><span data-stu-id="f83d9-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="f83d9-167">Los detalles de la onda se pueden editar hasta el inicio de cada onda.</span><span class="sxs-lookup"><span data-stu-id="f83d9-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="f83d9-168">Cada onda puede durar como mínimo un día (24 horas) y como máximo siete días.</span><span class="sxs-lookup"><span data-stu-id="f83d9-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="f83d9-169">Esto permite SharePoint y su entorno técnico una oportunidad de aclimatarse y escalar al gran volumen de usuarios del sitio.</span><span class="sxs-lookup"><span data-stu-id="f83d9-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="f83d9-170">Al programar un inicio a través de la interfaz de usuario, la zona horaria se basa en la configuración regional del sitio.</span><span class="sxs-lookup"><span data-stu-id="f83d9-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="f83d9-171">El programador de inicio del portal tendrá automáticamente como valor predeterminado un mínimo de 2 oleadas.</span><span class="sxs-lookup"><span data-stu-id="f83d9-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="f83d9-172">Sin embargo, la versión de PowerShell de esta herramienta permitirá 1 oleada.</span><span class="sxs-lookup"><span data-stu-id="f83d9-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
   > - <span data-ttu-id="f83d9-173">Microsoft 365 los grupos no son compatibles con esta versión del programador de inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="f83d9-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="f83d9-174">Determine quién debe ver el sitio inmediatamente e introduzca su información en el **campo Usuarios exentos de oleadas.**</span><span class="sxs-lookup"><span data-stu-id="f83d9-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="f83d9-175">Estos usuarios se excluyen de las oleadas y no se redirigirán antes, durante o después del inicio.</span><span class="sxs-lookup"><span data-stu-id="f83d9-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f83d9-176">Se pueden agregar hasta 50 usuarios o grupos de seguridad distintos como máximo.</span><span class="sxs-lookup"><span data-stu-id="f83d9-176">Up to 50 distinct users or security groups max can be added.</span></span> <span data-ttu-id="f83d9-177">Use grupos de seguridad cuando necesite más de 50 personas para obtener acceso al portal antes de que las oleadas comiencen a iniciarse.</span><span class="sxs-lookup"><span data-stu-id="f83d9-177">Use security groups when you need more than 50 individuals to get access to the portal before the waves start launching.</span></span>

8. <span data-ttu-id="f83d9-178">Confirme los detalles de inicio del portal y seleccione **Programar**.</span><span class="sxs-lookup"><span data-stu-id="f83d9-178">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="f83d9-179">Una vez programado el inicio, los cambios en la página principal del portal de SharePoint tendrán que recibir un resultado de diagnóstico correcto antes de que se reanude el inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="f83d9-179">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>

### <a name="launch-a-portal-with-over-100k-users"></a><span data-ttu-id="f83d9-180">Iniciar un portal con más de 100.000 usuarios</span><span class="sxs-lookup"><span data-stu-id="f83d9-180">Launch a portal with over 100k users</span></span>

<span data-ttu-id="f83d9-181">Si tiene previsto iniciar un portal con más de 100.000 usuarios, envíe una solicitud de soporte técnico siguiendo los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="f83d9-181">If you are planning to launch a portal with over 100,000 users, submit a support request following the steps listed below.</span></span> <span data-ttu-id="f83d9-182">Asegúrese de incluir toda la información solicitada.</span><span class="sxs-lookup"><span data-stu-id="f83d9-182">Make sure to include all the requested information.</span></span>

<span data-ttu-id="f83d9-183">**Siga estos pasos:**</span><span class="sxs-lookup"><span data-stu-id="f83d9-183">**Follow these steps:**</span></span>

1. <span data-ttu-id="f83d9-184">Vaya a <https://admin.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="f83d9-184">Go to <https://admin.microsoft.com>.</span></span>
2. <span data-ttu-id="f83d9-185">Asegúrese de que está usando la nueva vista previa del centro de administración</span><span class="sxs-lookup"><span data-stu-id="f83d9-185">Ensure you are using the new admin center preview</span></span>
3. <span data-ttu-id="f83d9-186">En el panel de navegación izquierdo, seleccione **Soporte** técnico y, a continuación, **nueva solicitud de servicio**</span><span class="sxs-lookup"><span data-stu-id="f83d9-186">On the left navigational pane, select **Support**, and then select **New Service Request**</span></span>

   <span data-ttu-id="f83d9-187">Se activará el panel **¿Necesita ayuda?**, en la parte derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="f83d9-187">This will activate the **Need Help?** pane on the right-hand side of your screen.</span></span>

4. <span data-ttu-id="f83d9-188">Para **describir brevemente el problema,** escriba "Iniciar SharePoint portal con 100.000 usuarios"</span><span class="sxs-lookup"><span data-stu-id="f83d9-188">For **Briefly describe your issue**, enter "Launch SharePoint Portal with 100k users"</span></span></br>
5. <span data-ttu-id="f83d9-189">A continuación, seleccione **Ponerse en contacto con el soporte técnico**</span><span class="sxs-lookup"><span data-stu-id="f83d9-189">Then, select **Contact Support**</span></span>
6. <span data-ttu-id="f83d9-190">En **Descripción,** escriba "Iniciar SharePoint portal con 100 mil usuarios"</span><span class="sxs-lookup"><span data-stu-id="f83d9-190">Under **Description**, enter "Launch SharePoint Portal with 100k users"</span></span>
7. <span data-ttu-id="f83d9-191">Rellene la información restante y, a continuación, seleccione **Póngase en contacto conmigo**</span><span class="sxs-lookup"><span data-stu-id="f83d9-191">Fill out the remaining information, and then select **Contact me**</span></span>
8. <span data-ttu-id="f83d9-192">Una vez que se haya creado el vale, asegúrese de que proporciona al agente de soporte técnico la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f83d9-192">After the ticket has been created, ensure you provide the support agent with the following information:</span></span>
   - <span data-ttu-id="f83d9-193">Url del portal</span><span class="sxs-lookup"><span data-stu-id="f83d9-193">Portal URL's</span></span>
   - <span data-ttu-id="f83d9-194">Número de usuarios esperados</span><span class="sxs-lookup"><span data-stu-id="f83d9-194">Number of users expected</span></span>
   - <span data-ttu-id="f83d9-195">Programación de inicio estimada</span><span class="sxs-lookup"><span data-stu-id="f83d9-195">Estimated launch schedule</span></span>

## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="f83d9-196">Realizar cambios en un inicio de portal programado</span><span class="sxs-lookup"><span data-stu-id="f83d9-196">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="f83d9-197">Los detalles de inicio se pueden editar para cada onda hasta la fecha de inicio de la onda.</span><span class="sxs-lookup"><span data-stu-id="f83d9-197">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span>

1. <span data-ttu-id="f83d9-198">Para editar los detalles de inicio del portal, vaya **a Configuración** y seleccione Programar inicio **de sitio**.</span><span class="sxs-lookup"><span data-stu-id="f83d9-198">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2. <span data-ttu-id="f83d9-199">A continuación, **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="f83d9-199">Then, select **Edit**.</span></span>
3. <span data-ttu-id="f83d9-200">Cuando haya terminado de realizar las modificaciones, seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="f83d9-200">When you are finished making your edits, select **Update**.</span></span>

## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="f83d9-201">Eliminar un inicio de portal programado</span><span class="sxs-lookup"><span data-stu-id="f83d9-201">Delete a scheduled portal launch</span></span>

<span data-ttu-id="f83d9-202">Los inicios programados con la herramienta programador de inicio del portal se pueden cancelar o eliminar en cualquier momento, incluso si ya se han iniciado algunas oleadas.</span><span class="sxs-lookup"><span data-stu-id="f83d9-202">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1. <span data-ttu-id="f83d9-203">Para cancelar el inicio del portal, vaya a **Configuración** **y Programar inicio del sitio**.</span><span class="sxs-lookup"><span data-stu-id="f83d9-203">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2. <span data-ttu-id="f83d9-204">A continuación, **seleccione Eliminar** y, a continuación, cuando vea el mensaje siguiente, seleccione **Eliminar de** nuevo.</span><span class="sxs-lookup"><span data-stu-id="f83d9-204">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

   ![Imagen de la herramienta programador de inicio de portal](../media/portal-launch-delete-2.png)

## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="f83d9-206">Usar el programador de inicio de PowerShell Portal</span><span class="sxs-lookup"><span data-stu-id="f83d9-206">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="f83d9-207">La herramienta de programador de inicio de SharePoint Portal de SharePoint estaba disponible originalmente a través de [powershell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) y seguirá siendo compatible con PowerShell para los clientes que prefieran este método.</span><span class="sxs-lookup"><span data-stu-id="f83d9-207">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="f83d9-208">Las mismas notas al principio de este artículo se aplican a ambas versiones del programador de inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="f83d9-208">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span>

> [!NOTE]
> <span data-ttu-id="f83d9-209">Necesita permisos de administrador para usar SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f83d9-209">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="f83d9-210">Los detalles de inicio del portal para los inicios creados en PowerShell aparecerán y se pueden administrar en la nueva herramienta del programador de inicio de portal en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f83d9-210">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>

### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="f83d9-211">Configuración de la aplicación y conexión a SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f83d9-211">App setup and connecting to SharePoint Online</span></span>

1. <span data-ttu-id="f83d9-212">[Descargue el Shell de administración de SharePoint Online más reciente](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="f83d9-212">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="f83d9-p118">Si instaló una versión anterior del Shell de administración de SharePoint Online, vaya a Agregar o quitar programas y desinstale "Shell de administración de SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="f83d9-p118">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="f83d9-214">En la página Centro de descarga, seleccione su idioma y haga clic en el botón Descargar.</span><span class="sxs-lookup"><span data-stu-id="f83d9-214">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="f83d9-215">Se le pedirá que elija entre descargar un archivo .msi x64 y x86.</span><span class="sxs-lookup"><span data-stu-id="f83d9-215">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="f83d9-216">Descargue el archivo x64 si está ejecutando la versión de 64 bits de Windows o el archivo x86 si está ejecutando la versión de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="f83d9-216">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="f83d9-217">Si no lo sabe, consulte [¿Qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="f83d9-217">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="f83d9-218">Después de descargar el archivo, ejecútelo y siga los pasos del Asistente de configuración.</span><span class="sxs-lookup"><span data-stu-id="f83d9-218">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="f83d9-219">Conéctese a SharePoint como un [administrador global o como un administrador de SharePoint](/sharepoint/sharepoint-admin-role) en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f83d9-219">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="f83d9-220">Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="f83d9-220">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="f83d9-221">Ver las configuraciones de inicio de portal existentes</span><span class="sxs-lookup"><span data-stu-id="f83d9-221">View any existing portal launch setups</span></span>

<span data-ttu-id="f83d9-222">Para ver si hay configuraciones de inicio de portal existentes:</span><span class="sxs-lookup"><span data-stu-id="f83d9-222">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="f83d9-223">Programar un inicio de portal en el sitio</span><span class="sxs-lookup"><span data-stu-id="f83d9-223">Schedule a portal launch on the site</span></span>

<span data-ttu-id="f83d9-224">El número de oleadas necesarias depende del tamaño de inicio esperado.</span><span class="sxs-lookup"><span data-stu-id="f83d9-224">The number of waves required depends on your expected launch size.</span></span>

- <span data-ttu-id="f83d9-225">Menos de 10.000 usuarios: una ola</span><span class="sxs-lookup"><span data-stu-id="f83d9-225">Less than 10k users: One wave</span></span>
- <span data-ttu-id="f83d9-226">Usuarios de 10 a 30 k: tres oleadas</span><span class="sxs-lookup"><span data-stu-id="f83d9-226">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="f83d9-227">Usuarios de entre 30 y 100 k: cinco oleadas</span><span class="sxs-lookup"><span data-stu-id="f83d9-227">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="f83d9-228">Más de 100.000 usuarios: cinco oleadas y póngase en contacto con el equipo de su cuenta microsoft</span><span class="sxs-lookup"><span data-stu-id="f83d9-228">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="f83d9-229">Pasos para la redirección bidireccional</span><span class="sxs-lookup"><span data-stu-id="f83d9-229">Steps for bidirectional redirection</span></span>

<span data-ttu-id="f83d9-230">La redirección bidireccional implica el lanzamiento de un nuevo portal SharePoint Online para reemplazar un portal SharePoint clásico o moderno.</span><span class="sxs-lookup"><span data-stu-id="f83d9-230">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="f83d9-231">Los usuarios en oleadas activas se redirigirán al nuevo sitio independientemente de si navegan al sitio antiguo o nuevo.</span><span class="sxs-lookup"><span data-stu-id="f83d9-231">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="f83d9-232">Los usuarios de una oleada no iniciada que intenten acceder al nuevo sitio se redirigirán de nuevo al sitio antiguo hasta que se inicia la oleada.</span><span class="sxs-lookup"><span data-stu-id="f83d9-232">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>

<span data-ttu-id="f83d9-233">Solo se admite el redireccionamiento entre la página principal predeterminada del sitio antiguo y la página principal predeterminada del nuevo sitio.</span><span class="sxs-lookup"><span data-stu-id="f83d9-233">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="f83d9-234">Si tiene administradores o propietarios que necesitan acceso a los sitios antiguos y nuevos sin ser redirigidos, asegúrese de que aparecen con el `WaveOverrideUsers` parámetro.</span><span class="sxs-lookup"><span data-stu-id="f83d9-234">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="f83d9-235">Para migrar usuarios de un sitio SharePoint a un nuevo SharePoint de forma por fases:</span><span class="sxs-lookup"><span data-stu-id="f83d9-235">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="f83d9-236">Ejecute el siguiente comando para designar las oleadas de inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="f83d9-236">Run the following command to designate portal launch waves.</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="f83d9-237">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f83d9-237">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="f83d9-238">Validación completa.</span><span class="sxs-lookup"><span data-stu-id="f83d9-238">Complete validation.</span></span> <span data-ttu-id="f83d9-239">El redireccionamiento puede tardar entre 5 y 10 minutos en completar su configuración en todo el servicio.</span><span class="sxs-lookup"><span data-stu-id="f83d9-239">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span>

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="f83d9-240">Pasos para la redirección a la página temporal</span><span class="sxs-lookup"><span data-stu-id="f83d9-240">Steps for redirection to temporary page</span></span>

<span data-ttu-id="f83d9-241">El redireccionamiento temporal de páginas debe usarse cuando no exista SharePoint portal existente.</span><span class="sxs-lookup"><span data-stu-id="f83d9-241">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="f83d9-242">Los usuarios se dirigen a un nuevo portal SharePoint Online de forma por fases.</span><span class="sxs-lookup"><span data-stu-id="f83d9-242">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="f83d9-243">Si un usuario está en una oleada que no se ha iniciado, se le redirigirá a una página temporal (cualquier dirección URL).</span><span class="sxs-lookup"><span data-stu-id="f83d9-243">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span>

1. <span data-ttu-id="f83d9-244">Ejecute el siguiente comando para designar las oleadas de inicio del portal.</span><span class="sxs-lookup"><span data-stu-id="f83d9-244">Run the following command to designate portal launch waves.</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="f83d9-245">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f83d9-245">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="f83d9-246">Validación completa.</span><span class="sxs-lookup"><span data-stu-id="f83d9-246">Complete validation.</span></span> <span data-ttu-id="f83d9-247">El redireccionamiento puede tardar entre 5 y 10 minutos en completar su configuración en todo el servicio.</span><span class="sxs-lookup"><span data-stu-id="f83d9-247">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span>

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="f83d9-248">Pausar o reiniciar el inicio de un portal en el sitio</span><span class="sxs-lookup"><span data-stu-id="f83d9-248">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="f83d9-249">Para pausar el inicio de un portal en curso y evitar temporalmente que se produzcan próximas progresión de onda, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f83d9-249">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="f83d9-250">Valide que todos los usuarios se redirigen al sitio antiguo.</span><span class="sxs-lookup"><span data-stu-id="f83d9-250">Validate that all users are redirected to the old site.</span></span>

3. <span data-ttu-id="f83d9-251">Para reiniciar un inicio de portal que se ha pausado, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f83d9-251">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```

4. <span data-ttu-id="f83d9-252">Valide que el redireccionamiento ya está restaurado.</span><span class="sxs-lookup"><span data-stu-id="f83d9-252">Validate that the redirection is now restored.</span></span>

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="f83d9-253">Eliminar un inicio de portal en el sitio</span><span class="sxs-lookup"><span data-stu-id="f83d9-253">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="f83d9-254">Ejecute el siguiente comando para eliminar un inicio de portal programado o en curso para un sitio.</span><span class="sxs-lookup"><span data-stu-id="f83d9-254">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="f83d9-255">Valide que no se produce ninguna redirección para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f83d9-255">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="f83d9-256">Más información</span><span class="sxs-lookup"><span data-stu-id="f83d9-256">Learn more</span></span>

[<span data-ttu-id="f83d9-257">Planeación del plan de lanzamiento del portal en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f83d9-257">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="f83d9-258">Planear el sitio de comunicación</span><span class="sxs-lookup"><span data-stu-id="f83d9-258">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
