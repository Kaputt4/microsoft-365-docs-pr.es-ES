---
title: Interacciones de servicios de grupos
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Interacciones de servicios de grupos
ms.openlocfilehash: f9b0d7ca61d55e3d23aa94577fc8257073b26675
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539208"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="fdd0e-103">Interacciones de servicios de grupos</span><span class="sxs-lookup"><span data-stu-id="fdd0e-103">Groups services interactions</span></span>

<span data-ttu-id="fdd0e-104">Microsoft 365 Los grupos proporcionan un tejido común para una serie de servicios y cargas de trabajo dentro de la plataforma Microsoft 365 para ofrecer una experiencia conectada para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="fdd0e-105">En su núcleo, existe Microsoft 365 grupo para proporcionar:</span><span class="sxs-lookup"><span data-stu-id="fdd0e-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="fdd0e-106">Una forma de administrar la pertenencia (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="fdd0e-107">Un lugar para que se lleve a cabo la mensajería y las conversaciones (Exchange buzón, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="fdd0e-108">Un lugar para que los archivos se almacenen (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="fdd0e-109">Un calendario para la programación (Exchange)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="fdd0e-110">Bloc de notas para capturar notas (OneNote)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="fdd0e-111">En el punto de creación de grupos, también se aprovisionan otros recursos, pero no son visibles hasta que se accede por primera vez desde el servicio:</span><span class="sxs-lookup"><span data-stu-id="fdd0e-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="fdd0e-112">Un panel para administrar tareas de grupo (Planner)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="fdd0e-113">Un área de trabajo para informes (Power BI)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="fdd0e-114">Un área para vídeos compartidos (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="fdd0e-115">Un área para formularios compartidos (formularios)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="fdd0e-116">En Microsoft 365, otros servicios pueden interactuar con grupos de Microsoft 365 para ofrecer funcionalidades y funcionalidades adicionales a los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="fdd0e-117">Algunos ejemplos de esto son:</span><span class="sxs-lookup"><span data-stu-id="fdd0e-117">Examples of this include:</span></span>

- <span data-ttu-id="fdd0e-118">Power Apps aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fdd0e-118">Power Apps for apps</span></span>
- <span data-ttu-id="fdd0e-119">Power Automate para flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="fdd0e-119">Power Automate for workflows</span></span>
- <span data-ttu-id="fdd0e-120">Project web y guía básica para la administración de proyectos basada en cascada</span><span class="sxs-lookup"><span data-stu-id="fdd0e-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="fdd0e-121">Teams para conversaciones basadas en canal</span><span class="sxs-lookup"><span data-stu-id="fdd0e-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="fdd0e-122">Yammer para comunidades de interés</span><span class="sxs-lookup"><span data-stu-id="fdd0e-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="fdd0e-123">Interacciones del usuario con grupos</span><span class="sxs-lookup"><span data-stu-id="fdd0e-123">User interactions with groups</span></span>

<span data-ttu-id="fdd0e-124">Microsoft 365 Los grupos se pueden crear y administrar desde una variedad de interfaces, tanto por administradores como por usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="fdd0e-125">Experiencias administrativas</span><span class="sxs-lookup"><span data-stu-id="fdd0e-125">Administrative experiences</span></span>

<span data-ttu-id="fdd0e-126">Los administradores pueden crear y administrar grupos de Microsoft 365 desde varios de los centros de administración de cargas de trabajo, interfaces de línea de comandos que admiten scripting, así como aplicaciones personalizadas que interactúan con la API de Graph carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="fdd0e-127">La única excepción a esto es Yammer grupos, que deben crearse desde la interfaz Yammer web.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="fdd0e-128">**Configuración relacionada**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-128">**Related settings**</span></span>

<span data-ttu-id="fdd0e-129">En las distintas interfaces administrativas que pueden administrar la configuración de grupo existen varias superposiciones que debe tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="fdd0e-130">**Centro de administración de Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="fdd0e-131">En el centro Microsoft 365 administración, el acceso de invitado a grupos está habilitado de forma predeterminada, al igual que la capacidad de permitir que los propietarios agreguen invitados.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="fdd0e-132">No hay más controles de nivel de organización disponibles para grupos desde este centro de administración.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="fdd0e-133">**Centro de administración de Azure AD**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-133">**Azure AD admin center**</span></span>

<span data-ttu-id="fdd0e-134">El Centro de administración de Azure AD ofrece controles sobre si los usuarios pueden crear grupos o asignar propietarios en Azure Portals, así como la configuración de la directiva de expiración y nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="fdd0e-135">El Centro de administración también proporciona una serie de medidas de control de invitaciones de invitado que van más allá de la del centro de administración de Microsoft 365, como la capacidad de limitar si los no propietarios también pueden invitar invitados</span><span class="sxs-lookup"><span data-stu-id="fdd0e-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="fdd0e-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-136">**SharePoint**</span></span>

<span data-ttu-id="fdd0e-137">SharePoint sitios se crean con grupos de seguridad Propietario, Miembro y Visitante, y los dos primeros coinciden con sus equivalentes Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="fdd0e-138">Aunque la pertenencia SharePoint los sitios en línea generalmente se administra mediante el grupo Microsoft 365 asociado, no es una relación bidireccional.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="fdd0e-139">Cualquier cambio en la pertenencia en el nivel de grupo de Microsoft 365 se refleja en SharePoint, pero si se cambia la pertenencia en el grupo SharePoint, esto no se refleja en el grupo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="fdd0e-140">Experiencias de usuario</span><span class="sxs-lookup"><span data-stu-id="fdd0e-140">User experiences</span></span>

<span data-ttu-id="fdd0e-141">Los usuarios finales pueden crear grupos a partir de varios de los servicios de Microsoft 365 y, en otros, solo pueden compartir con un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="fdd0e-142">Los siguientes servicios permiten la creación de grupos por usuarios finales:</span><span class="sxs-lookup"><span data-stu-id="fdd0e-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="fdd0e-143">Outlook Planner Project para la web SharePoint Stream Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="fdd0e-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="fdd0e-144">**Restricción de creación de grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-144">**Restriction of group creation**</span></span>

<span data-ttu-id="fdd0e-145">Un enfoque común para controlar la expansión de los equipos es limitar los usuarios que pueden crearlos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="fdd0e-146">Esto solo se puede hacer limitando la creación de grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="fdd0e-147">Esto afecta a la capacidad de crear grupos desde otros servicios cuando esto puede ser necesario para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="fdd0e-148">Microsoft 365 Los grupos no admiten la capacidad de restringir la creación de grupos desde algunas aplicaciones o servicios mientras se permiten desde otras.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="fdd0e-149">La experiencia de restricción de creación de grupos varía entre aplicaciones y servicios:</span><span class="sxs-lookup"><span data-stu-id="fdd0e-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="fdd0e-150">Aplicación o servicio</span><span class="sxs-lookup"><span data-stu-id="fdd0e-150">App or service</span></span>|<span data-ttu-id="fdd0e-151">Experiencia</span><span class="sxs-lookup"><span data-stu-id="fdd0e-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="fdd0e-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="fdd0e-152">Outlook</span></span>|<span data-ttu-id="fdd0e-153">**La nueva opción** de grupo se quita del menú Nuevo en la página personas</span><span class="sxs-lookup"><span data-stu-id="fdd0e-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="fdd0e-154">Planner</span><span class="sxs-lookup"><span data-stu-id="fdd0e-154">Planner</span></span>|<span data-ttu-id="fdd0e-155">**El nuevo plan** explica que la creación de grupos se ha desactivado y ofrece agregar el plan a un grupo existente</span><span class="sxs-lookup"><span data-stu-id="fdd0e-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="fdd0e-156">Project web y guía básica</span><span class="sxs-lookup"><span data-stu-id="fdd0e-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="fdd0e-157">**El menú** Crear grupo explica que la creación de grupos está restringida y sugiere el uso de un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="fdd0e-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fdd0e-158">SharePoint</span></span>|<span data-ttu-id="fdd0e-159">Sigue siendo capaz de crear un sitio de grupo que no esté conectado a un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="fdd0e-160">Stream</span><span class="sxs-lookup"><span data-stu-id="fdd0e-160">Stream</span></span>|<span data-ttu-id="fdd0e-161">**La** opción Grupo no aparece en el **menú Crear**.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="fdd0e-162">Teams</span><span class="sxs-lookup"><span data-stu-id="fdd0e-162">Teams</span></span>|<span data-ttu-id="fdd0e-163">El usuario no puede crear un equipo con un grupo nuevo, pero puede crear un equipo que use un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="fdd0e-164">**Crear un botón** de equipo se reemplaza por **Crear equipo desde un grupo.**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="fdd0e-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="fdd0e-165">Yammer</span></span>|<span data-ttu-id="fdd0e-166">**Crear una opción de** grupo se quita de la navegación grupos/comunidades principales.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="fdd0e-167">Interacciones de servicios con grupos</span><span class="sxs-lookup"><span data-stu-id="fdd0e-167">Services interactions with groups</span></span>

<span data-ttu-id="fdd0e-168">Vea el póster Grupos en Microsoft 365 para obtener información sobre los distintos tipos de grupos, cómo se crean y administran, y algunas recomendaciones de gobierno.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="fdd0e-169">[![Imagen en miniatura para la infografía de grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="fdd0e-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="fdd0e-171">En la tabla siguiente se proporciona información general sobre Microsoft 365 de grupos con diversos servicios:</span><span class="sxs-lookup"><span data-stu-id="fdd0e-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="fdd0e-172">Producto</span><span class="sxs-lookup"><span data-stu-id="fdd0e-172">Product</span></span>|<span data-ttu-id="fdd0e-173">Características</span><span class="sxs-lookup"><span data-stu-id="fdd0e-173">Features</span></span>|<span data-ttu-id="fdd0e-174">¿El servicio</span><span class="sxs-lookup"><span data-stu-id="fdd0e-174">Does the service</span></span><br><span data-ttu-id="fdd0e-175">existen sin un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-175">exist without a group?</span></span>|<span data-ttu-id="fdd0e-176">¿Puede el servicio?</span><span class="sxs-lookup"><span data-stu-id="fdd0e-176">Can the service</span></span><br><span data-ttu-id="fdd0e-177">crear un grupo</span><span class="sxs-lookup"><span data-stu-id="fdd0e-177">create a group?</span></span>|<span data-ttu-id="fdd0e-178">Elimina la</span><span class="sxs-lookup"><span data-stu-id="fdd0e-178">Does deleting the</span></span><br><span data-ttu-id="fdd0e-179">instancia eliminar el grupo?</span><span class="sxs-lookup"><span data-stu-id="fdd0e-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="fdd0e-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="fdd0e-180">Azure AD</span></span>|<span data-ttu-id="fdd0e-181">Pertenencia, Controles de grupo, Invitados</span><span class="sxs-lookup"><span data-stu-id="fdd0e-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="fdd0e-182">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-182">Yes</span></span>|<span data-ttu-id="fdd0e-183">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-183">Yes</span></span>|<span data-ttu-id="fdd0e-184">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-184">Yes</span></span>|
|<span data-ttu-id="fdd0e-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="fdd0e-185">Exchange</span></span>|<span data-ttu-id="fdd0e-186">Calendario, buzón</span><span class="sxs-lookup"><span data-stu-id="fdd0e-186">Calendar, mailbox</span></span>|<span data-ttu-id="fdd0e-187">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-187">Yes</span></span>|<span data-ttu-id="fdd0e-188">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-188">Yes</span></span>|<span data-ttu-id="fdd0e-189">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-189">Yes</span></span>|
|<span data-ttu-id="fdd0e-190">Formularios</span><span class="sxs-lookup"><span data-stu-id="fdd0e-190">Forms</span></span>|<span data-ttu-id="fdd0e-191">Form</span><span class="sxs-lookup"><span data-stu-id="fdd0e-191">Form</span></span>|<span data-ttu-id="fdd0e-192">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-192">Yes</span></span>|<span data-ttu-id="fdd0e-193">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-193">No</span></span>|<span data-ttu-id="fdd0e-194">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-194">No</span></span>|
|<span data-ttu-id="fdd0e-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="fdd0e-195">OneNote</span></span>|<span data-ttu-id="fdd0e-196">Bloc de notas</span><span class="sxs-lookup"><span data-stu-id="fdd0e-196">Notebook</span></span>|<span data-ttu-id="fdd0e-197">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-197">Yes</span></span>|<span data-ttu-id="fdd0e-198">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-198">No</span></span>|<span data-ttu-id="fdd0e-199">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-199">No</span></span>|
|<span data-ttu-id="fdd0e-200">Planner</span><span class="sxs-lookup"><span data-stu-id="fdd0e-200">Planner</span></span>|<span data-ttu-id="fdd0e-201">Panel de tareas</span><span class="sxs-lookup"><span data-stu-id="fdd0e-201">Task board</span></span>|<span data-ttu-id="fdd0e-202">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-202">No</span></span>|<span data-ttu-id="fdd0e-203">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-203">Yes</span></span>|<span data-ttu-id="fdd0e-204">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-204">Yes</span></span>|
|<span data-ttu-id="fdd0e-205">Power Apps app</span><span class="sxs-lookup"><span data-stu-id="fdd0e-205">Power Apps app</span></span>|<span data-ttu-id="fdd0e-206">Aplicación</span><span class="sxs-lookup"><span data-stu-id="fdd0e-206">App</span></span>|<span data-ttu-id="fdd0e-207">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-207">Yes</span></span>|<span data-ttu-id="fdd0e-208">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-208">No</span></span>|<span data-ttu-id="fdd0e-209">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-209">No</span></span>|
|<span data-ttu-id="fdd0e-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="fdd0e-210">Power Automate</span></span>|<span data-ttu-id="fdd0e-211">Flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="fdd0e-211">Workflow</span></span>|<span data-ttu-id="fdd0e-212">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-212">Yes</span></span>|<span data-ttu-id="fdd0e-213">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-213">No</span></span>|<span data-ttu-id="fdd0e-214">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-214">No</span></span>|
|<span data-ttu-id="fdd0e-215">Power BI (clásico)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-215">Power BI (classic)</span></span>|<span data-ttu-id="fdd0e-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="fdd0e-216">Workspace</span></span>|<span data-ttu-id="fdd0e-217">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-217">No</span></span>|<span data-ttu-id="fdd0e-218">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-218">Yes</span></span>|<span data-ttu-id="fdd0e-219">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-219">Yes</span></span>|
|<span data-ttu-id="fdd0e-220">Power BI (nuevo)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-220">Power BI (new)</span></span>|<span data-ttu-id="fdd0e-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="fdd0e-221">Workspace</span></span>|<span data-ttu-id="fdd0e-222">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-222">Yes</span></span>|<span data-ttu-id="fdd0e-223">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-223">No</span></span>|<span data-ttu-id="fdd0e-224">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-224">Yes</span></span>|
|<span data-ttu-id="fdd0e-225">Project para la web</span><span class="sxs-lookup"><span data-stu-id="fdd0e-225">Project for the web</span></span>|<span data-ttu-id="fdd0e-226">Project plan</span><span class="sxs-lookup"><span data-stu-id="fdd0e-226">Project plan</span></span>|<span data-ttu-id="fdd0e-227">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-227">Yes</span></span>|<span data-ttu-id="fdd0e-228">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-228">Yes</span></span>|<span data-ttu-id="fdd0e-229">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-229">No</span></span>|
|<span data-ttu-id="fdd0e-230">Guía básica</span><span class="sxs-lookup"><span data-stu-id="fdd0e-230">Roadmap</span></span>|<span data-ttu-id="fdd0e-231">Guía básica</span><span class="sxs-lookup"><span data-stu-id="fdd0e-231">Roadmap</span></span>|<span data-ttu-id="fdd0e-232">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-232">Yes</span></span>|<span data-ttu-id="fdd0e-233">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-233">Yes</span></span>|<span data-ttu-id="fdd0e-234">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-234">No</span></span>|
|<span data-ttu-id="fdd0e-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fdd0e-235">SharePoint</span></span>|<span data-ttu-id="fdd0e-236">Site</span><span class="sxs-lookup"><span data-stu-id="fdd0e-236">Site</span></span>|<span data-ttu-id="fdd0e-237">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-237">Yes</span></span>|<span data-ttu-id="fdd0e-238">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-238">Yes</span></span>|<span data-ttu-id="fdd0e-239">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-239">Yes</span></span>|
|<span data-ttu-id="fdd0e-240">Stream</span><span class="sxs-lookup"><span data-stu-id="fdd0e-240">Stream</span></span>|<span data-ttu-id="fdd0e-241">Canal, vídeo</span><span class="sxs-lookup"><span data-stu-id="fdd0e-241">Channel, video</span></span>|<span data-ttu-id="fdd0e-242">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-242">Yes</span></span>|<span data-ttu-id="fdd0e-243">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-243">Yes</span></span>|<span data-ttu-id="fdd0e-244">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-244">Yes</span></span>|
|<span data-ttu-id="fdd0e-245">Teams</span><span class="sxs-lookup"><span data-stu-id="fdd0e-245">Teams</span></span>|<span data-ttu-id="fdd0e-246">Equipo</span><span class="sxs-lookup"><span data-stu-id="fdd0e-246">Team</span></span>|<span data-ttu-id="fdd0e-247">No</span><span class="sxs-lookup"><span data-stu-id="fdd0e-247">No</span></span>|<span data-ttu-id="fdd0e-248">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-248">Yes</span></span>|<span data-ttu-id="fdd0e-249">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-249">Yes</span></span>|
|<span data-ttu-id="fdd0e-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="fdd0e-250">Yammer</span></span>|<span data-ttu-id="fdd0e-251">Group</span><span class="sxs-lookup"><span data-stu-id="fdd0e-251">Group</span></span>|<span data-ttu-id="fdd0e-252">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-252">Yes</span></span>|<span data-ttu-id="fdd0e-253">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-253">Yes</span></span>|<span data-ttu-id="fdd0e-254">Sí</span><span class="sxs-lookup"><span data-stu-id="fdd0e-254">Yes</span></span>|

<span data-ttu-id="fdd0e-255">Aunque la tabla anterior proporciona una introducción general de alto nivel de las interacciones de grupo con los servicios Microsoft 365, hay una serie de matices e complejidades que debe comprender.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="fdd0e-256">En las secciones siguientes se hace un análisis más detallado de las cargas de trabajo específicas y sus interacciones con los grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="fdd0e-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="fdd0e-257">Azure AD</span></span>

<span data-ttu-id="fdd0e-258">Azure AD proporciona las capacidades de administración de identidades subyacentes en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="fdd0e-259">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="fdd0e-260">Pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="fdd0e-260">Group membership</span></span>
- <span data-ttu-id="fdd0e-261">Directiva de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="fdd0e-261">Naming policy</span></span>
- <span data-ttu-id="fdd0e-262">Directiva de expiración</span><span class="sxs-lookup"><span data-stu-id="fdd0e-262">Expiration policy</span></span>
- <span data-ttu-id="fdd0e-263">Invitados</span><span class="sxs-lookup"><span data-stu-id="fdd0e-263">Guests</span></span>
- <span data-ttu-id="fdd0e-264">Restricción de creación de grupos</span><span class="sxs-lookup"><span data-stu-id="fdd0e-264">Restriction of Group creation</span></span>

<span data-ttu-id="fdd0e-265">**¿Puede Azure AD crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="fdd0e-266">Sí, Microsoft 365 pueden crearse desde Azure AD a través del portal web de administración, a través de PowerShell o Graph API.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="fdd0e-267">**¿Azure AD existe sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="fdd0e-268">Sí, Azure AD realiza un gran número de servicios que no tienen relación con Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="fdd0e-269">Cada Microsoft 365 grupo se representa como un objeto en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="fdd0e-270">**¿Puede haber varias instancias de Azure AD por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="fdd0e-271">No, solo hay una instancia de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="fdd0e-272">**¿Azure AD se puede asociar a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="fdd0e-273">Sí, porque Azure AD es la plataforma subyacente que proporciona el servicio de pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="fdd0e-274">**¿Puede cambiar la asociación de Azure AD con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="fdd0e-275">No, Azure AD es la plataforma subyacente donde existen grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="fdd0e-276">**¿Elimina la instancia el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="fdd0e-277">Al eliminar el grupo en Azure AD, se eliminará el contenido y los servicios asociados al grupo correspondientes.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="fdd0e-278">Teams</span><span class="sxs-lookup"><span data-stu-id="fdd0e-278">Teams</span></span>

<span data-ttu-id="fdd0e-279">Teams es un área de trabajo centrada en chat destinada a mejorar la colaboración proporcionando una interfaz singular para interactuar con una variedad de servicios de Microsoft y de terceros.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="fdd0e-280">De forma predeterminada, cuando se crea un equipo, el buzón y el calendario asociados con el grupo Microsoft 365 se ocultan de la lista global de direcciones de Exchange, así como Outlook.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="fdd0e-281">Un administrador puede invalidar esto manualmente si el usuario desea usar tanto Outlook como Teams en el mismo Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="fdd0e-282">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="fdd0e-283">Conversaciones</span><span class="sxs-lookup"><span data-stu-id="fdd0e-283">Conversations</span></span>
- <span data-ttu-id="fdd0e-284">Canales & pestañas</span><span class="sxs-lookup"><span data-stu-id="fdd0e-284">Channels & tabs</span></span>
- <span data-ttu-id="fdd0e-285">Reuniones</span><span class="sxs-lookup"><span data-stu-id="fdd0e-285">Meetings</span></span>

<span data-ttu-id="fdd0e-286">**¿Teams crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="fdd0e-287">Sí, la creación de un nuevo equipo creará un nuevo Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="fdd0e-288">También es posible crear un equipo para un grupo existente que no tenga uno actualmente.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="fdd0e-289">**¿Existen equipos sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="fdd0e-290">No, no es posible que un equipo exista sin un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="fdd0e-291">**¿Puede haber varios equipos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="fdd0e-292">No, la relación entre un equipo y un grupo es 1:1.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="fdd0e-293">**¿Se puede asociar un equipo a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-294">No, el equipo en sí solo puede asociarse con un solo grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="fdd0e-295">**¿Puede cambiar la asociación de un equipo con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="fdd0e-296">No, el equipo solo se puede asociar al grupo al que estaba asociado originalmente.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="fdd0e-297">**¿Elimina el equipo el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="fdd0e-298">Sí, al eliminar el equipo de Microsoft Teams se eliminará el grupo, los servicios asociados al grupo y el contenido.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="fdd0e-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="fdd0e-299">Exchange</span></span>

<span data-ttu-id="fdd0e-300">Exchange Online proporciona mensajería, calendario, contacto y funcionalidad asociada.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="fdd0e-301">En el contexto de un grupo, solo se asocia un único recurso, en lugar de una instancia de servicio completa.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="fdd0e-302">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="fdd0e-303">Buzón y calendario</span><span class="sxs-lookup"><span data-stu-id="fdd0e-303">Mailbox and calendar</span></span>
- <span data-ttu-id="fdd0e-304">Capacidad de enviar un correo electrónico a todos los miembros del grupo</span><span class="sxs-lookup"><span data-stu-id="fdd0e-304">Ability to email all Group members</span></span>
- <span data-ttu-id="fdd0e-305">Storage de Teams conversaciones de canal con fines de exhibición de documentos electrónicos, comentarios de Planner</span><span class="sxs-lookup"><span data-stu-id="fdd0e-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="fdd0e-306">**¿Exchange crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="fdd0e-307">Sí, es posible crear un grupo desde el Exchange Online de administración, así como desde Outlook.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="fdd0e-308">También puede convertir listas Exchange distribución a Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="fdd0e-309">**¿Exchange existe sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="fdd0e-310">Sí, Exchange Online proporciona una serie de servicios, incluidos los buzones y calendarios compartidos, sin ninguna asociación de grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="fdd0e-311">**¿Puede haber varias instancias de buzones Exchange o calendarios por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="fdd0e-312">No, solo puede haber un único buzón Exchange Online y un calendario para un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="fdd0e-313">**¿Exchange buzones y calendarios se pueden asociar a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-314">No, el buzón y el calendario tienen una relación 1:1 con el grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="fdd0e-315">Es posible compartir el buzón con otros usuarios o grupos, pero esto no establece ninguna forma de asociación de servicio.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="fdd0e-316">**¿Puede Exchange la asociación del buzón o calendario con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="fdd0e-317">No, el buzón y el calendario no se pueden cambiar a un grupo diferente.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="fdd0e-318">Sin embargo, el contenido se puede mover de un buzón a otro dentro de Outlook o mediante una herramienta de terceros.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="fdd0e-319">**¿Elimina el buzón de correo el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="fdd0e-320">Sí, al eliminar el buzón de Exchange se eliminará el grupo, así como los servicios y el contenido asociados al grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="fdd0e-321">Formularios</span><span class="sxs-lookup"><span data-stu-id="fdd0e-321">Forms</span></span>

<span data-ttu-id="fdd0e-322">Forms proporciona encuestas y cuestionarios basados en web.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="fdd0e-323">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="fdd0e-324">Propiedad de los formularios</span><span class="sxs-lookup"><span data-stu-id="fdd0e-324">Ownership of forms</span></span>

<span data-ttu-id="fdd0e-325">**¿Pueden los formularios crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="fdd0e-326">No, Forms no puede crear un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="fdd0e-327">**¿Existen formularios sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="fdd0e-328">Sí, las encuestas y los cuestionarios se pueden crear directamente en la cuenta de un usuario final.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="fdd0e-329">**¿Puede haber varios formularios por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="fdd0e-330">Sí, puede haber varios formularios asociados a un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="fdd0e-331">**¿Los formularios se pueden asociar a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-332">No, un formulario solo se puede asociar a un único grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="fdd0e-333">**¿Puede cambiar la asociación de un formulario con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="fdd0e-334">No, una vez que un formulario está asociado a un grupo (ya sea creado directamente dentro o la propiedad transferida de un individuo) no se puede mover a otro grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="fdd0e-335">**¿Elimina el formulario el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="fdd0e-336">No, no es posible eliminar un grupo de la interfaz formularios, solo formularios individuales.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="fdd0e-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="fdd0e-337">OneNote</span></span>

<span data-ttu-id="fdd0e-338">OneNote es una aplicación de bloc de notas digital.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="fdd0e-339">El bloc OneNote de notas creado con un grupo es un archivo en el sitio SharePoint asociado en lugar de un servicio conectado a un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="fdd0e-340">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="fdd0e-341">Bloc de notas compartido (almacenado en la biblioteca SharePoint grupo)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="fdd0e-342">**¿OneNote crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="fdd0e-343">No, la OneNote no puede crear un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="fdd0e-344">**¿OneNote blocs de notas existen sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="fdd0e-345">Sí, los blocs de notas se pueden crear directamente en OneDrive o en otras ubicaciones compartidas.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="fdd0e-346">**¿Puede haber varios blocs OneNote por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="fdd0e-347">Sí, se crea un bloc de notas de forma predeterminada y se pueden agregar otros, pero cualquier vínculo a OneNote de los servicios asociados al grupo siempre irá al bloc de notas predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="fdd0e-348">**¿Se puede asociar OneNote bloc de notas a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-349">No, el bloc de notas se almacena en la biblioteca de sitios asociada SharePoint grupo y se vincula desde varias interfaces.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="fdd0e-350">Sin embargo, se puede compartir con otros grupos de la misma manera que se puede compartir con individuos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="fdd0e-351">**¿Puede cambiar la asociación del bloc de notas con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="fdd0e-352">No, el bloc de notas en sí está asociado al grupo y se puede acceder directamente desde otros servicios conectados a grupos, sin embargo, el contenido se puede mover de un bloc de notas a otro dentro de la aplicación OneNote grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="fdd0e-353">**¿Elimina el bloc de notas el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="fdd0e-354">No, sin embargo, si OneNote bloc de notas se elimina, puede haber vínculos rotos en algunos de los servicios asociados al grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="fdd0e-355">Planner</span><span class="sxs-lookup"><span data-stu-id="fdd0e-355">Planner</span></span>

<span data-ttu-id="fdd0e-356">Planner es un servicio ligero de administración de tareas de grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="fdd0e-357">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="fdd0e-358">Junta para administrar tareas de grupo</span><span class="sxs-lookup"><span data-stu-id="fdd0e-358">Board for managing group tasks</span></span>

<span data-ttu-id="fdd0e-359">**¿Planner puede crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="fdd0e-360">Sí, la creación de un plan creará un nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="fdd0e-361">**¿Existe un consejo de Planner sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="fdd0e-362">No, un plan debe estar asociado a un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="fdd0e-363">**¿Puede haber varios planes por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="fdd0e-364">Sí, puede haber varios planes por grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="fdd0e-365">**¿Se puede asociar un plan a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-366">No, un plan se basa únicamente en la pertenencia a grupos para determinar el acceso.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="fdd0e-367">**¿Puede cambiar la asociación de un plan con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="fdd0e-368">No, sin embargo, al copiar un plan se crea un nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="fdd0e-369">Un grupo creado por cualquier otra aplicación no se mostrará automáticamente en Planner para un usuario.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="fdd0e-370">Para tener acceso al tablero inicialmente, tendrán que abrirlo desde otra interfaz basada en grupo, como Outlook.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="fdd0e-371">**¿Elimina el plan el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="fdd0e-372">Sí, al eliminar el plan se eliminará el contenido y los servicios asociados al grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="fdd0e-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="fdd0e-373">Power Apps</span></span>

<span data-ttu-id="fdd0e-374">Power Apps proporciona un lienzo para el desarrollo de aplicaciones sin código.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="fdd0e-375">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="fdd0e-376">Las aplicaciones se pueden compartir con un grupo que se va a ejecutar y modificar</span><span class="sxs-lookup"><span data-stu-id="fdd0e-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="fdd0e-377">**¿Power Apps crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="fdd0e-378">No, Power Apps puede crear un Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="fdd0e-379">**¿Power Apps existen sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="fdd0e-380">Sí, las aplicaciones se pueden crear en Power Apps y residir en la cuenta de creadores hasta que se compartan o publiquen.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="fdd0e-381">**¿Puede haber varias aplicaciones por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="fdd0e-382">Sí, puede haber varias aplicaciones compartidas con un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="fdd0e-383">**¿Las aplicaciones se pueden asociar a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-384">Sí, una aplicación se puede compartir con varios grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="fdd0e-385">**¿Puede cambiar la asociación de una aplicación con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="fdd0e-386">Sí, como la asociación entre Power Apps y un grupo de Microsoft 365 está compartiendo solo: la aplicación sigue residiendo con el creador.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fdd0e-387">[Los grupos deben estar habilitados para que las aplicaciones puedan compartirse con ellos.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-387">[Groups must be security enabled before apps can be shared with them](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="fdd0e-388">**¿Elimina la aplicación el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="fdd0e-389">No, las aplicaciones no están conectadas al grupo que no se compartan con ellas.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="fdd0e-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="fdd0e-390">Power Automate</span></span>

<span data-ttu-id="fdd0e-391">Power Automate (anteriormente conocido como Microsoft Flow) proporciona flujos de trabajo y servicios de automatización.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="fdd0e-392">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="fdd0e-393">Los flujos de trabajo se pueden compartir con un grupo que se va a ejecutar y modificar.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="fdd0e-394">**¿Power Automate crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="fdd0e-395">No, Power Automate puede crear un grupo Microsoft 365 en el contexto de asociarse a uno.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="fdd0e-396">Sin embargo, es posible crear un flujo que realice varias operaciones, como crear un grupo de seguridad de Azure AD o actualizar la pertenencia a un grupo Microsoft 365 usuario.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="fdd0e-397">**¿Existen flujos sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="fdd0e-398">Sí, los flujos se pueden crear en Power Automate y residir en la cuenta de creadores hasta que se compartan o publiquen.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="fdd0e-399">**¿Puede haber varios flujos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="fdd0e-400">Sí, puede haber varios flujos compartidos con un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="fdd0e-401">**¿Se puede asociar un flujo a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-402">Sí, un flujo se puede compartir con varios grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="fdd0e-403">**¿Puede cambiar la asociación de un flujo con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="fdd0e-404">Sí, como la asociación entre Power Automate y un grupo Microsoft 365 está compartiendo solamente: el flujo sigue residiendo con el creador.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="fdd0e-405">**¿Elimina un flujo el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="fdd0e-406">No, como Power Apps, los flujos no están conectados al grupo que no se compartan con ellos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="fdd0e-407">Power BI (clásico)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-407">Power BI (classic)</span></span>

<span data-ttu-id="fdd0e-408">Power BI proporciona paneles e informes interactivos controlados por datos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="fdd0e-409">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="fdd0e-410">Informes de datos</span><span class="sxs-lookup"><span data-stu-id="fdd0e-410">Data reporting</span></span>

<span data-ttu-id="fdd0e-411">**¿Power BI crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="fdd0e-412">Sí, la creación de un área de trabajo clásica creará Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="fdd0e-413">**¿Existe Power BI área de trabajo clásica sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="fdd0e-414">No, [un área de trabajo clásica Power BI debe asociarse con un grupo](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="fdd0e-414">No, [a classic workspace in Power BI must be associated with a group](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="fdd0e-415">**¿Puede haber varias áreas Power BI por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="fdd0e-416">No, la relación entre un área de trabajo clásica y un grupo es 1:1.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="fdd0e-417">**¿Se puede asociar un área de trabajo a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-418">Técnicamente no, mientras que el área de trabajo clásica se crea con el grupo, el contenido se puede compartir fuera del grupo con usuarios y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="fdd0e-419">**¿Puede cambiar la asociación del área de trabajo con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="fdd0e-420">No, el área de trabajo clásica en sí está asociada con el grupo, pero el contenido se puede mover de un área de trabajo a otra dentro de la interfaz Power BI o exportando contenido localmente.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="fdd0e-421">**¿Elimina el área de trabajo el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="fdd0e-422">Sí, al eliminar el área de trabajo en Power BI se eliminará el contenido y los servicios asociados a grupos y grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="fdd0e-423">Power BI (nuevo)</span><span class="sxs-lookup"><span data-stu-id="fdd0e-423">Power BI (new)</span></span>

<span data-ttu-id="fdd0e-424">Power BI proporciona paneles e informes interactivos controlados por datos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="fdd0e-425">Al crear un nuevo área de trabajo en Power BI no crea un grupo de Microsoft 365, la creación de un grupo por cualquier otro medio crea un área de trabajo nueva (no clásica) en Power BI.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="fdd0e-426">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="fdd0e-427">Informes de datos</span><span class="sxs-lookup"><span data-stu-id="fdd0e-427">Data reporting</span></span>

<span data-ttu-id="fdd0e-428">**¿Power BI crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="fdd0e-429">No, no es posible crear un grupo Microsoft 365 desde la nueva interfaz Power BI usuario.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="fdd0e-430">**¿Existe el nuevo Power BI de trabajo sin grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="fdd0e-431">Sí, es posible crear informes y áreas de trabajo en Power BI que no estén asociados con Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="fdd0e-432">**¿Puede haber varias áreas de trabajo por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="fdd0e-433">Sí, [varias áreas de trabajo creadas por Power BI pueden compartirse con un único grupo](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span><span class="sxs-lookup"><span data-stu-id="fdd0e-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="fdd0e-434">**¿Se puede asociar un área de trabajo a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-435">No, un área de trabajo creada por Power BI solo se puede asociar a un único grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="fdd0e-436">**¿Puede cambiar la asociación de un área de trabajo con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="fdd0e-437">Sí y no.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-437">Yes and no.</span></span> <span data-ttu-id="fdd0e-438">Un área de trabajo creada por Power BI solo se puede asociar a un solo grupo a la vez, pero puede cambiar la asociación en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="fdd0e-439">Un área de trabajo creada Power BI por un grupo está asociada permanentemente a ese grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="fdd0e-440">**¿Elimina el área de trabajo el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="fdd0e-441">Sí, al eliminar el área de trabajo en Power BI se eliminará el contenido y los servicios asociados al grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="fdd0e-442">Project para la web</span><span class="sxs-lookup"><span data-stu-id="fdd0e-442">Project for the web</span></span>

<span data-ttu-id="fdd0e-443">Project web ofrece la posibilidad de crear planes de proyecto, gráficos de Gantt y mapas de ruta.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="fdd0e-444">Características clave que se proporcionan a los grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-444">Key features provided to groups.</span></span>

- <span data-ttu-id="fdd0e-445">Project planes</span><span class="sxs-lookup"><span data-stu-id="fdd0e-445">Project plans</span></span>

<span data-ttu-id="fdd0e-446">**¿Project para la web crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="fdd0e-447">Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde Project para la web.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="fdd0e-448">**¿Existen proyectos sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="fdd0e-449">Sí, los proyectos pueden existir sin estar asociados a un grupo Microsoft 365, pero la asignación de tareas requiere asociación de grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="fdd0e-450">**¿Puede haber varios proyectos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="fdd0e-451">Sí, es posible conectar varios proyectos en un solo grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="fdd0e-452">**¿El proyecto se puede asociar a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-453">No, un proyecto solo se puede asociar a un único grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="fdd0e-454">**¿Puede cambiar la asociación de un proyecto con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="fdd0e-455">No, una vez establecida la asociación con un grupo, no puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="fdd0e-456">**¿Elimina el proyecto el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="fdd0e-457">No, la eliminación del proyecto en Project para la web no eliminará el grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="fdd0e-458">Guía básica</span><span class="sxs-lookup"><span data-stu-id="fdd0e-458">Roadmap</span></span>

<span data-ttu-id="fdd0e-459">Roadmap proporciona la capacidad de crear hojas de ruta de proyectos con Project web y Project Online.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="fdd0e-460">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="fdd0e-461">Project rutas básicas</span><span class="sxs-lookup"><span data-stu-id="fdd0e-461">Project roadmaps</span></span>

<span data-ttu-id="fdd0e-462">**¿Puede roadmap crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="fdd0e-463">Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde el mapa de ruta.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="fdd0e-464">**¿Existe roadmap sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="fdd0e-465">Sí, pueden existir hojas de ruta sin estar asociadas con un grupo Microsoft 365, pero para compartir la hoja de ruta es necesario asociarse a un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="fdd0e-466">**¿Puede haber varias hojas de ruta por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="fdd0e-467">Sí, es posible conectar varias hojas de ruta a un solo grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="fdd0e-468">**¿Se puede asociar un mapa de ruta con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-469">No, un mapa de ruta solo se puede asociar a un único grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="fdd0e-470">**¿Puede cambiar la asociación de un plan con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="fdd0e-471">No, una vez establecida la asociación con un grupo, no puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="fdd0e-472">**¿Elimina el plan de ruta el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="fdd0e-473">No, la eliminación del mapa de ruta no eliminará el grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="fdd0e-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fdd0e-474">SharePoint</span></span>

<span data-ttu-id="fdd0e-475">SharePoint es una plataforma de administración de contenido basada en web que proporciona, entre otras cosas, servicios de almacenamiento para una serie de Microsoft 365 web.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="fdd0e-476">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="fdd0e-477">Biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="fdd0e-477">Document library</span></span>
- <span data-ttu-id="fdd0e-478">Biblioteca para el almacenamiento de OneNote bloc de notas</span><span class="sxs-lookup"><span data-stu-id="fdd0e-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="fdd0e-479">Storage de Teams wiki</span><span class="sxs-lookup"><span data-stu-id="fdd0e-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="fdd0e-480">**¿SharePoint crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="fdd0e-481">Sí, la creación de un sitio de grupo en SharePoint creará un grupo Microsoft 365 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="fdd0e-482">También es posible crear un grupo y, opcionalmente, un equipo para un sitio existente.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="fdd0e-483">**¿SharePoint sitios existen sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="fdd0e-484">Sí, SharePoint ofrece una serie de sitios y servicios no asociados a grupos, como sitios de comunicaciones y concentradores.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="fdd0e-485">**¿Puede haber varios sitios por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="fdd0e-486">No, solo puede haber un solo sitio por grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="fdd0e-487">Los canales privados Teams usar sitios adicionales que no están conectados al grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="fdd0e-488">**¿Los sitios se pueden asociar a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-489">Técnicamente no, pero mientras se crea un sitio con un grupo, el contenido se puede compartir con otros grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="fdd0e-490">**¿Puede cambiar la asociación de un sitio con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="fdd0e-491">No, el propio sitio está asociado con el grupo, pero el contenido se puede mover de un sitio a otro dentro de la interfaz de SharePoint, exportando contenido localmente o mediante una herramienta de terceros.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="fdd0e-492">**¿Elimina el sitio el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="fdd0e-493">Sí, al eliminar el sitio en SharePoint se eliminará el contenido y los servicios asociados a grupos y grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="fdd0e-494">Stream</span><span class="sxs-lookup"><span data-stu-id="fdd0e-494">Stream</span></span>

<span data-ttu-id="fdd0e-495">Microsoft Stream es una plataforma de hospedaje y uso compartido de vídeo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="fdd0e-496">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="fdd0e-497">Almacenamiento de vídeo</span><span class="sxs-lookup"><span data-stu-id="fdd0e-497">Video storage</span></span>
- <span data-ttu-id="fdd0e-498">Teams de reuniones</span><span class="sxs-lookup"><span data-stu-id="fdd0e-498">Teams meeting recording</span></span>
- <span data-ttu-id="fdd0e-499">Canales de vídeo</span><span class="sxs-lookup"><span data-stu-id="fdd0e-499">Video channels</span></span>

<span data-ttu-id="fdd0e-500">**¿Stream puede crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="fdd0e-501">Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde Stream.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="fdd0e-502">**¿Existe Stream sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="fdd0e-503">Sí, los canales de vídeo y los vídeos pueden existir en Stream sin estar asociados a un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="fdd0e-504">**¿Puede haber varios vídeos y canales por grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="fdd0e-505">Sí, puede haber varios vídeos y canales en cada grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="fdd0e-506">**¿Se puede asociar un vídeo o canal a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="fdd0e-507">Sí, mientras se crea un vídeo o canal con un grupo, se puede compartir con otros grupos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="fdd0e-508">**¿Puede cambiar su asociación con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="fdd0e-509">Sí y no; Los vídeos de Stream son propiedad del cargador original o la grabadora de reuniones, por lo que se pueden asociar a cualquier grupo, pero los canales de vídeo solo pueden asociarse con el grupo en el que se crearon originalmente.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="fdd0e-510">**¿Elimina vídeos o canales el grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="fdd0e-511">No, la eliminación de vídeos o canales no elimina el grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="fdd0e-512">Sin embargo, al eliminar el propio grupo en Stream, se eliminarán los servicios y el contenido asociados al grupo, excepto para los vídeos reales.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="fdd0e-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="fdd0e-513">Yammer</span></span>

<span data-ttu-id="fdd0e-514">Yammer es una plataforma social empresarial diseñada para fomentar la participación de la comunidad dentro y entre organizaciones.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="fdd0e-515">La creación de una comunidad (anteriormente conocida como "grupo") en Yammer crea un buzón, pero en este momento no se usa.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="fdd0e-516">Un Microsoft 365 que está asociado con Yammer no se puede usar con un equipo de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="fdd0e-517">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="fdd0e-518">Área de conversación</span><span class="sxs-lookup"><span data-stu-id="fdd0e-518">Conversation area</span></span>

<span data-ttu-id="fdd0e-519">**¿Yammer crear un Microsoft 365 grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="fdd0e-520">Sí, la creación de un nuevo grupo en Yammer creará un nuevo grupo de Microsoft 365, si las plataformas están conectadas y el usuario tiene la capacidad de crear un grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="fdd0e-521">Un Yammer con un grupo Microsoft 365 asociado no se puede crear en ninguna interfaz o servicio que no sea Yammer propio.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="fdd0e-522">**¿Existe Yammer grupo sin Microsoft 365 grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="fdd0e-523">Sí, es posible crear un grupo de Yammer sin un Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="fdd0e-524">Si la plataforma Yammer no está conectada a grupos de Microsoft 365 o los usuarios no tienen la capacidad de crear un grupo de Microsoft 365, Yammer se crean grupos sin una asociación Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="fdd0e-525">**¿Puede haber varios Yammer por Microsoft 365 grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="fdd0e-526">No, la relación entre un grupo Yammer y un grupo Microsoft 365 es 1:1.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="fdd0e-527">**¿Se puede asociar Yammer grupo a varios Microsoft 365 grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="fdd0e-528">No, el Yammer solo se puede asociar a un único Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="fdd0e-529">Es posible que las publicaciones se compartan con otros grupos de Yammer se puedan mover a ellos.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="fdd0e-530">**¿Puede cambiar Yammer asociación de un grupo de Microsoft 365 grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="fdd0e-531">No, el Yammer solo se puede asociar al grupo Microsoft 365 al que estaba asociado originalmente.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="fdd0e-532">**¿Elimina el grupo Yammer elimina el Microsoft 365 grupo?**</span><span class="sxs-lookup"><span data-stu-id="fdd0e-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="fdd0e-533">Sí, si se elimina el grupo en Yammer se eliminará el contenido y los servicios asociados al grupo relacionados de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fdd0e-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fdd0e-534">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fdd0e-534">Related topics</span></span>

[<span data-ttu-id="fdd0e-535">Planeación paso a paso de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="fdd0e-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="fdd0e-536">Crear el plan de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="fdd0e-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)