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
description: Interacciones de servicios de grupos
ms.openlocfilehash: 6d5681b11cdbd837f784b6c8364cce23f964b167
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613231"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="74027-103">Interacciones de servicios de grupos</span><span class="sxs-lookup"><span data-stu-id="74027-103">Groups services interactions</span></span>

<span data-ttu-id="74027-104">Grupos de Microsoft 365 proporciona un tejido común para una serie de servicios y cargas de trabajo dentro de la plataforma de Microsoft 365 para ofrecer una experiencia conectada para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="74027-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="74027-105">En esencia, existe un grupo de Microsoft 365 para proporcionar:</span><span class="sxs-lookup"><span data-stu-id="74027-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="74027-106">Una forma de administrar la pertenencia (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="74027-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="74027-107">Un lugar para que se lleve a cabo la mensajería y las conversaciones (buzón de Exchange, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="74027-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="74027-108">Un lugar para almacenar archivos (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="74027-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="74027-109">Un calendario para programación (Exchange)</span><span class="sxs-lookup"><span data-stu-id="74027-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="74027-110">Un bloc de notas para capturar notas (OneNote)</span><span class="sxs-lookup"><span data-stu-id="74027-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="74027-111">En el momento de la creación del grupo, también se aprovisionan otros recursos, pero no son visibles hasta que se accede por primera vez desde el servicio:</span><span class="sxs-lookup"><span data-stu-id="74027-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="74027-112">Un panel para administrar tareas de grupo (Planner)</span><span class="sxs-lookup"><span data-stu-id="74027-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="74027-113">Un área de trabajo para informes (Power BI)</span><span class="sxs-lookup"><span data-stu-id="74027-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="74027-114">Un área para vídeos compartidos (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="74027-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="74027-115">Un área para formularios compartidos (formularios)</span><span class="sxs-lookup"><span data-stu-id="74027-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="74027-116">En Microsoft 365, otros servicios pueden interactuar con grupos de Microsoft 365 para ofrecer funcionalidades y funcionalidades adicionales a los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="74027-117">Algunos ejemplos de esto son:</span><span class="sxs-lookup"><span data-stu-id="74027-117">Examples of this include:</span></span>

- <span data-ttu-id="74027-118">Power Apps para aplicaciones</span><span class="sxs-lookup"><span data-stu-id="74027-118">Power Apps for apps</span></span>
- <span data-ttu-id="74027-119">Power Automate para flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="74027-119">Power Automate for workflows</span></span>
- <span data-ttu-id="74027-120">Proyecto en la web y mapa de ruta para la administración de proyectos basados en cascada</span><span class="sxs-lookup"><span data-stu-id="74027-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="74027-121">Teams para conversaciones basadas en canales</span><span class="sxs-lookup"><span data-stu-id="74027-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="74027-122">Yammer para comunidades de interés</span><span class="sxs-lookup"><span data-stu-id="74027-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="74027-123">Interacciones del usuario con grupos</span><span class="sxs-lookup"><span data-stu-id="74027-123">User interactions with groups</span></span>

<span data-ttu-id="74027-124">Los grupos de Microsoft 365 se pueden crear y administrar desde una variedad de interfaces, tanto por parte de los administradores como de los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="74027-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="74027-125">Experiencias administrativas</span><span class="sxs-lookup"><span data-stu-id="74027-125">Administrative experiences</span></span>

<span data-ttu-id="74027-126">Los administradores pueden crear y administrar grupos de Microsoft 365 desde varios de los centros de administración de carga de trabajo, interfaces de línea de comandos que admiten scripting, así como aplicaciones personalizadas que interactúan con la API de Graph.</span><span class="sxs-lookup"><span data-stu-id="74027-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="74027-127">La única excepción a esto son los grupos de Yammer, que deben crearse desde la interfaz web de Yammer.</span><span class="sxs-lookup"><span data-stu-id="74027-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="74027-128">**Configuración relacionada**</span><span class="sxs-lookup"><span data-stu-id="74027-128">**Related settings**</span></span>

<span data-ttu-id="74027-129">En las distintas interfaces administrativas que pueden administrar la configuración de grupo existen varias superposiciones que debes tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="74027-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="74027-130">**Centro de administración de Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="74027-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="74027-131">En el Centro de administración de Microsoft 365, el acceso de invitado a grupos está habilitado de forma predeterminada, al igual que la capacidad de permitir a los propietarios agregar invitados.</span><span class="sxs-lookup"><span data-stu-id="74027-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="74027-132">No hay más controles de nivel de organización disponibles para grupos desde este centro de administración.</span><span class="sxs-lookup"><span data-stu-id="74027-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="74027-133">**Centro de administración de Azure AD**</span><span class="sxs-lookup"><span data-stu-id="74027-133">**Azure AD admin center**</span></span>

<span data-ttu-id="74027-134">El Centro de administración de Azure AD ofrece controles sobre si los usuarios pueden crear grupos o asignar propietarios en Azure Portals, así como la configuración de directiva de expiración y nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="74027-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="74027-135">El Centro de administración también proporciona una serie de medidas de control de invitaciones de invitado que van más allá de la del Centro de administración de Microsoft 365, como la capacidad de limitar si los usuarios que no son propietarios también pueden invitar a invitados.</span><span class="sxs-lookup"><span data-stu-id="74027-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="74027-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="74027-136">**SharePoint**</span></span>

<span data-ttu-id="74027-137">Los sitios de SharePoint se crean con grupos de seguridad propietario, miembro y visitante, y los dos primeros coinciden con sus equivalentes de grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="74027-138">Aunque el grupo asociado de Microsoft 365 suele administrar la pertenencia a sitios de SharePoint Online, no es una relación bidireccional.</span><span class="sxs-lookup"><span data-stu-id="74027-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="74027-139">Los cambios en la pertenencia al nivel de grupo de Microsoft 365 se reflejan en SharePoint, pero si se cambia la pertenencia en el grupo de SharePoint, esto no se refleja en el grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="74027-140">Experiencias del usuario</span><span class="sxs-lookup"><span data-stu-id="74027-140">User experiences</span></span>

<span data-ttu-id="74027-141">Los usuarios finales pueden crear grupos desde varios de los servicios de Microsoft 365 y, en otros, solo pueden compartir con un grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="74027-142">Los siguientes servicios permiten la creación de grupos por parte de los usuarios finales:</span><span class="sxs-lookup"><span data-stu-id="74027-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="74027-143">Proyecto de Planeación de Outlook para la web de Microsoft Teams yammer de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74027-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="74027-144">**Restricción de la creación de grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-144">**Restriction of group creation**</span></span>

<span data-ttu-id="74027-145">Un enfoque común para controlar la expansión de equipos es limitar qué usuarios pueden crearlos.</span><span class="sxs-lookup"><span data-stu-id="74027-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="74027-146">Esto solo se puede hacer limitando la creación de grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="74027-147">Esto afecta a la capacidad de crear grupos desde otros servicios cuando esto puede ser necesario para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="74027-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="74027-148">Grupos de Microsoft 365 no admite la capacidad de restringir la creación de grupos desde algunas aplicaciones o servicios, a la vez que se permite desde otras.</span><span class="sxs-lookup"><span data-stu-id="74027-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="74027-149">La experiencia de restricción de creación de grupos varía entre aplicaciones y servicios:</span><span class="sxs-lookup"><span data-stu-id="74027-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="74027-150">Aplicación o servicio</span><span class="sxs-lookup"><span data-stu-id="74027-150">App or service</span></span>|<span data-ttu-id="74027-151">Experiencia</span><span class="sxs-lookup"><span data-stu-id="74027-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="74027-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="74027-152">Outlook</span></span>|<span data-ttu-id="74027-153">**La nueva opción** de grupo se quita del menú Nuevo de la página de personas</span><span class="sxs-lookup"><span data-stu-id="74027-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="74027-154">Planner</span><span class="sxs-lookup"><span data-stu-id="74027-154">Planner</span></span>|<span data-ttu-id="74027-155">**El nuevo plan** explica que se ha desactivado la creación de grupos y ofrece agregar el plan a un grupo existente</span><span class="sxs-lookup"><span data-stu-id="74027-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="74027-156">Proyecto para la web y plan de desarrollo</span><span class="sxs-lookup"><span data-stu-id="74027-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="74027-157">**El menú** Crear grupo explica que la creación de grupos está restringida y sugiere el uso de un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="74027-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="74027-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="74027-158">SharePoint</span></span>|<span data-ttu-id="74027-159">Aún puede crear un sitio de grupo que no esté conectado a un grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="74027-160">Stream</span><span class="sxs-lookup"><span data-stu-id="74027-160">Stream</span></span>|<span data-ttu-id="74027-161">**La** opción de grupo no aparece en el **menú Crear**.</span><span class="sxs-lookup"><span data-stu-id="74027-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="74027-162">Teams</span><span class="sxs-lookup"><span data-stu-id="74027-162">Teams</span></span>|<span data-ttu-id="74027-163">El usuario no puede crear un equipo con un nuevo grupo, pero aún puede crear un equipo que use un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="74027-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="74027-164">**Crear un botón de** equipo se reemplaza por **Crear equipo a partir de un grupo.**</span><span class="sxs-lookup"><span data-stu-id="74027-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="74027-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="74027-165">Yammer</span></span>|<span data-ttu-id="74027-166">**Crear una opción de** grupo se quita de la navegación principal grupos/comunidades.</span><span class="sxs-lookup"><span data-stu-id="74027-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="74027-167">Interacciones de servicios con grupos</span><span class="sxs-lookup"><span data-stu-id="74027-167">Services interactions with groups</span></span>

<span data-ttu-id="74027-168">Consulte el póster Grupos de Microsoft 365 para obtener información sobre los distintos tipos de grupos, cómo se crean y administran, y algunas recomendaciones de gobierno.</span><span class="sxs-lookup"><span data-stu-id="74027-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="74027-169">[![Imagen en miniatura para la infografía de grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="74027-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="74027-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="74027-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="74027-171">En la tabla siguiente se proporciona información general sobre las interacciones de Grupos de Microsoft 365 con varios servicios:</span><span class="sxs-lookup"><span data-stu-id="74027-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="74027-172">Producto</span><span class="sxs-lookup"><span data-stu-id="74027-172">Product</span></span>|<span data-ttu-id="74027-173">Características</span><span class="sxs-lookup"><span data-stu-id="74027-173">Features</span></span>|<span data-ttu-id="74027-174">¿El servicio?</span><span class="sxs-lookup"><span data-stu-id="74027-174">Does the service</span></span><br><span data-ttu-id="74027-175">existen sin un grupo</span><span class="sxs-lookup"><span data-stu-id="74027-175">exist without a group?</span></span>|<span data-ttu-id="74027-176">¿Puede el servicio?</span><span class="sxs-lookup"><span data-stu-id="74027-176">Can the service</span></span><br><span data-ttu-id="74027-177">crear un grupo</span><span class="sxs-lookup"><span data-stu-id="74027-177">create a group?</span></span>|<span data-ttu-id="74027-178">Elimina el</span><span class="sxs-lookup"><span data-stu-id="74027-178">Does deleting the</span></span><br><span data-ttu-id="74027-179">instance delete the group?</span><span class="sxs-lookup"><span data-stu-id="74027-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="74027-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="74027-180">Azure AD</span></span>|<span data-ttu-id="74027-181">Pertenencia, controles de grupo, Invitados</span><span class="sxs-lookup"><span data-stu-id="74027-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="74027-182">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-182">Yes</span></span>|<span data-ttu-id="74027-183">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-183">Yes</span></span>|<span data-ttu-id="74027-184">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-184">Yes</span></span>|
|<span data-ttu-id="74027-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="74027-185">Exchange</span></span>|<span data-ttu-id="74027-186">Calendario, buzón</span><span class="sxs-lookup"><span data-stu-id="74027-186">Calendar, mailbox</span></span>|<span data-ttu-id="74027-187">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-187">Yes</span></span>|<span data-ttu-id="74027-188">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-188">Yes</span></span>|<span data-ttu-id="74027-189">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-189">Yes</span></span>|
|<span data-ttu-id="74027-190">Formularios</span><span class="sxs-lookup"><span data-stu-id="74027-190">Forms</span></span>|<span data-ttu-id="74027-191">Form</span><span class="sxs-lookup"><span data-stu-id="74027-191">Form</span></span>|<span data-ttu-id="74027-192">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-192">Yes</span></span>|<span data-ttu-id="74027-193">No</span><span class="sxs-lookup"><span data-stu-id="74027-193">No</span></span>|<span data-ttu-id="74027-194">No</span><span class="sxs-lookup"><span data-stu-id="74027-194">No</span></span>|
|<span data-ttu-id="74027-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="74027-195">OneNote</span></span>|<span data-ttu-id="74027-196">Bloc de notas</span><span class="sxs-lookup"><span data-stu-id="74027-196">Notebook</span></span>|<span data-ttu-id="74027-197">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-197">Yes</span></span>|<span data-ttu-id="74027-198">No</span><span class="sxs-lookup"><span data-stu-id="74027-198">No</span></span>|<span data-ttu-id="74027-199">No</span><span class="sxs-lookup"><span data-stu-id="74027-199">No</span></span>|
|<span data-ttu-id="74027-200">Planner</span><span class="sxs-lookup"><span data-stu-id="74027-200">Planner</span></span>|<span data-ttu-id="74027-201">Panel de tareas</span><span class="sxs-lookup"><span data-stu-id="74027-201">Task board</span></span>|<span data-ttu-id="74027-202">No</span><span class="sxs-lookup"><span data-stu-id="74027-202">No</span></span>|<span data-ttu-id="74027-203">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-203">Yes</span></span>|<span data-ttu-id="74027-204">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-204">Yes</span></span>|
|<span data-ttu-id="74027-205">Aplicación Power Apps</span><span class="sxs-lookup"><span data-stu-id="74027-205">Power Apps app</span></span>|<span data-ttu-id="74027-206">Aplicación</span><span class="sxs-lookup"><span data-stu-id="74027-206">App</span></span>|<span data-ttu-id="74027-207">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-207">Yes</span></span>|<span data-ttu-id="74027-208">No</span><span class="sxs-lookup"><span data-stu-id="74027-208">No</span></span>|<span data-ttu-id="74027-209">No</span><span class="sxs-lookup"><span data-stu-id="74027-209">No</span></span>|
|<span data-ttu-id="74027-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="74027-210">Power Automate</span></span>|<span data-ttu-id="74027-211">Flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="74027-211">Workflow</span></span>|<span data-ttu-id="74027-212">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-212">Yes</span></span>|<span data-ttu-id="74027-213">No</span><span class="sxs-lookup"><span data-stu-id="74027-213">No</span></span>|<span data-ttu-id="74027-214">No</span><span class="sxs-lookup"><span data-stu-id="74027-214">No</span></span>|
|<span data-ttu-id="74027-215">Power BI (clásico)</span><span class="sxs-lookup"><span data-stu-id="74027-215">Power BI (classic)</span></span>|<span data-ttu-id="74027-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="74027-216">Workspace</span></span>|<span data-ttu-id="74027-217">No</span><span class="sxs-lookup"><span data-stu-id="74027-217">No</span></span>|<span data-ttu-id="74027-218">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-218">Yes</span></span>|<span data-ttu-id="74027-219">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-219">Yes</span></span>|
|<span data-ttu-id="74027-220">Power BI (nuevo)</span><span class="sxs-lookup"><span data-stu-id="74027-220">Power BI (new)</span></span>|<span data-ttu-id="74027-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="74027-221">Workspace</span></span>|<span data-ttu-id="74027-222">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-222">Yes</span></span>|<span data-ttu-id="74027-223">No</span><span class="sxs-lookup"><span data-stu-id="74027-223">No</span></span>|<span data-ttu-id="74027-224">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-224">Yes</span></span>|
|<span data-ttu-id="74027-225">Project para la Web</span><span class="sxs-lookup"><span data-stu-id="74027-225">Project for the web</span></span>|<span data-ttu-id="74027-226">Plan de proyecto</span><span class="sxs-lookup"><span data-stu-id="74027-226">Project plan</span></span>|<span data-ttu-id="74027-227">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-227">Yes</span></span>|<span data-ttu-id="74027-228">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-228">Yes</span></span>|<span data-ttu-id="74027-229">No</span><span class="sxs-lookup"><span data-stu-id="74027-229">No</span></span>|
|<span data-ttu-id="74027-230">Guía básica</span><span class="sxs-lookup"><span data-stu-id="74027-230">Roadmap</span></span>|<span data-ttu-id="74027-231">Guía básica</span><span class="sxs-lookup"><span data-stu-id="74027-231">Roadmap</span></span>|<span data-ttu-id="74027-232">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-232">Yes</span></span>|<span data-ttu-id="74027-233">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-233">Yes</span></span>|<span data-ttu-id="74027-234">No</span><span class="sxs-lookup"><span data-stu-id="74027-234">No</span></span>|
|<span data-ttu-id="74027-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="74027-235">SharePoint</span></span>|<span data-ttu-id="74027-236">Site</span><span class="sxs-lookup"><span data-stu-id="74027-236">Site</span></span>|<span data-ttu-id="74027-237">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-237">Yes</span></span>|<span data-ttu-id="74027-238">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-238">Yes</span></span>|<span data-ttu-id="74027-239">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-239">Yes</span></span>|
|<span data-ttu-id="74027-240">Stream</span><span class="sxs-lookup"><span data-stu-id="74027-240">Stream</span></span>|<span data-ttu-id="74027-241">Canal, vídeo</span><span class="sxs-lookup"><span data-stu-id="74027-241">Channel, video</span></span>|<span data-ttu-id="74027-242">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-242">Yes</span></span>|<span data-ttu-id="74027-243">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-243">Yes</span></span>|<span data-ttu-id="74027-244">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-244">Yes</span></span>|
|<span data-ttu-id="74027-245">Teams</span><span class="sxs-lookup"><span data-stu-id="74027-245">Teams</span></span>|<span data-ttu-id="74027-246">Equipo</span><span class="sxs-lookup"><span data-stu-id="74027-246">Team</span></span>|<span data-ttu-id="74027-247">No</span><span class="sxs-lookup"><span data-stu-id="74027-247">No</span></span>|<span data-ttu-id="74027-248">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-248">Yes</span></span>|<span data-ttu-id="74027-249">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-249">Yes</span></span>|
|<span data-ttu-id="74027-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="74027-250">Yammer</span></span>|<span data-ttu-id="74027-251">Group</span><span class="sxs-lookup"><span data-stu-id="74027-251">Group</span></span>|<span data-ttu-id="74027-252">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-252">Yes</span></span>|<span data-ttu-id="74027-253">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-253">Yes</span></span>|<span data-ttu-id="74027-254">Sí</span><span class="sxs-lookup"><span data-stu-id="74027-254">Yes</span></span>|

<span data-ttu-id="74027-255">Aunque la tabla anterior proporciona una introducción general de alto nivel de las interacciones de grupo con los servicios de Microsoft 365, hay una serie de matices e complejidades que debe comprender.</span><span class="sxs-lookup"><span data-stu-id="74027-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="74027-256">En las secciones siguientes se ofrece un análisis más detallado de las cargas de trabajo específicas y sus interacciones con los grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="74027-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="74027-257">Azure AD</span></span>

<span data-ttu-id="74027-258">Azure AD proporciona las capacidades subyacentes de administración de identidades en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="74027-259">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="74027-260">Pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="74027-260">Group membership</span></span>
- <span data-ttu-id="74027-261">Directiva de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="74027-261">Naming policy</span></span>
- <span data-ttu-id="74027-262">Directiva de expiración</span><span class="sxs-lookup"><span data-stu-id="74027-262">Expiration policy</span></span>
- <span data-ttu-id="74027-263">Invitados</span><span class="sxs-lookup"><span data-stu-id="74027-263">Guests</span></span>
- <span data-ttu-id="74027-264">Restricción de la creación de grupos</span><span class="sxs-lookup"><span data-stu-id="74027-264">Restriction of Group creation</span></span>

<span data-ttu-id="74027-265">**¿Puede Azure AD crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="74027-266">Sí, los grupos de Microsoft 365 se pueden crear desde Azure AD a través del portal web de administración, a través de PowerShell o la API de Graph.</span><span class="sxs-lookup"><span data-stu-id="74027-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="74027-267">**¿Azure AD existe sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="74027-268">Sí, Azure AD realiza un gran número de servicios que no tienen relación con grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="74027-269">Cada grupo de Microsoft 365 se representa como un objeto en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74027-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="74027-270">**¿Puede haber varias instancias de Azure AD por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="74027-271">No, solo hay una instancia de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74027-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="74027-272">**¿Se puede asociar Azure AD a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="74027-273">Sí, porque Azure AD es la plataforma subyacente que proporciona el servicio de pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="74027-274">**¿Puede cambiar la asociación de Azure AD con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="74027-275">No, Azure AD es la plataforma subyacente donde existen grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="74027-276">**¿Elimina la instancia el grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="74027-277">Al eliminar el grupo en Azure AD se eliminará el contenido y los servicios asociados a grupos relevantes.</span><span class="sxs-lookup"><span data-stu-id="74027-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="74027-278">Teams</span><span class="sxs-lookup"><span data-stu-id="74027-278">Teams</span></span>

<span data-ttu-id="74027-279">Teams es un área de trabajo centrada en chats destinada a mejorar la colaboración proporcionando una interfaz singular para interactuar con una variedad de servicios de Microsoft y de terceros.</span><span class="sxs-lookup"><span data-stu-id="74027-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="74027-280">De forma predeterminada, cuando se crea un equipo, el buzón y el calendario asociados con el grupo de Microsoft 365 se ocultan tanto de la lista global de direcciones de Exchange como de Outlook.</span><span class="sxs-lookup"><span data-stu-id="74027-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="74027-281">Un administrador puede invalidarlo manualmente si el usuario desea usar Outlook y Teams en el mismo grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="74027-282">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="74027-283">Conversaciones</span><span class="sxs-lookup"><span data-stu-id="74027-283">Conversations</span></span>
- <span data-ttu-id="74027-284">Pestañas & canales</span><span class="sxs-lookup"><span data-stu-id="74027-284">Channels & tabs</span></span>
- <span data-ttu-id="74027-285">Reuniones</span><span class="sxs-lookup"><span data-stu-id="74027-285">Meetings</span></span>

<span data-ttu-id="74027-286">**¿Puede Teams crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="74027-287">Sí, al crear un nuevo equipo se creará un nuevo grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="74027-288">También es posible crear un equipo para un grupo existente que actualmente no tiene uno.</span><span class="sxs-lookup"><span data-stu-id="74027-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="74027-289">**¿Existen equipos sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="74027-290">No, no es posible que un equipo exista sin un grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="74027-291">**¿Puede haber varios equipos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="74027-292">No, la relación entre un equipo y un grupo es 1:1.</span><span class="sxs-lookup"><span data-stu-id="74027-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="74027-293">**¿Se puede asociar un equipo a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-294">No, el equipo en sí solo se puede asociar a un solo grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="74027-295">**¿Puede cambiar la asociación de un equipo con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="74027-296">No, el equipo solo puede asociarse con el grupo al que se asoció originalmente.</span><span class="sxs-lookup"><span data-stu-id="74027-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="74027-297">**¿Elimina el equipo el grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="74027-298">Sí, al eliminar el equipo en Microsoft Teams se eliminará el grupo, los servicios asociados al grupo y el contenido.</span><span class="sxs-lookup"><span data-stu-id="74027-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="74027-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="74027-299">Exchange</span></span>

<span data-ttu-id="74027-300">Exchange Online proporciona mensajería, calendario, contacto y funcionalidad asociada.</span><span class="sxs-lookup"><span data-stu-id="74027-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="74027-301">En el contexto de un grupo, solo se asocia un único recurso, en lugar de una instancia de servicio completa.</span><span class="sxs-lookup"><span data-stu-id="74027-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="74027-302">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="74027-303">Buzón de correo y calendario</span><span class="sxs-lookup"><span data-stu-id="74027-303">Mailbox and calendar</span></span>
- <span data-ttu-id="74027-304">Capacidad de enviar un correo electrónico a todos los miembros del grupo</span><span class="sxs-lookup"><span data-stu-id="74027-304">Ability to email all Group members</span></span>
- <span data-ttu-id="74027-305">Almacenamiento de conversaciones de canal de Teams con fines de exhibición de documentos electrónicos, comentarios de Planner</span><span class="sxs-lookup"><span data-stu-id="74027-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="74027-306">**¿Puede Exchange crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="74027-307">Sí, es posible crear un grupo desde el Centro de administración de Exchange Online, así como desde Outlook.</span><span class="sxs-lookup"><span data-stu-id="74027-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="74027-308">También puede convertir listas de distribución de Exchange a grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="74027-309">**¿Existe Exchange sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="74027-310">Sí, Exchange Online proporciona una serie de servicios, incluidos los buzones y calendarios compartidos, sin ninguna asociación de grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="74027-311">**¿Puede haber varias instancias de buzones o calendarios de Exchange por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="74027-312">No, solo puede haber un único buzón y calendario de Exchange Online para un grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="74027-313">**¿Pueden asociarse buzones y calendarios de Exchange con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-314">No, el buzón y el calendario tienen una relación 1:1 con el grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="74027-315">Es posible compartir el buzón con otros usuarios o grupos, pero esto no establece ninguna forma de asociación de servicio.</span><span class="sxs-lookup"><span data-stu-id="74027-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="74027-316">**¿Puede cambiar la asociación del buzón o el calendario de Exchange con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="74027-317">No, el buzón y el calendario no se pueden cambiar a un grupo diferente.</span><span class="sxs-lookup"><span data-stu-id="74027-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="74027-318">Sin embargo, el contenido se puede mover de un buzón a otro dentro de Outlook o mediante una herramienta de terceros.</span><span class="sxs-lookup"><span data-stu-id="74027-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="74027-319">**¿Elimina el buzón de correo el grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="74027-320">Sí, al eliminar el buzón en Exchange se eliminará el grupo, así como los servicios y el contenido asociados al grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="74027-321">Formularios</span><span class="sxs-lookup"><span data-stu-id="74027-321">Forms</span></span>

<span data-ttu-id="74027-322">Forms proporciona encuestas y cuestionarios basados en web.</span><span class="sxs-lookup"><span data-stu-id="74027-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="74027-323">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="74027-324">Propiedad de los formularios</span><span class="sxs-lookup"><span data-stu-id="74027-324">Ownership of forms</span></span>

<span data-ttu-id="74027-325">**¿Pueden los formularios crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="74027-326">No, forms no puede crear un grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="74027-327">**¿Existen formularios sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="74027-328">Sí, las encuestas y cuestionarios se pueden crear directamente en la cuenta de un usuario final.</span><span class="sxs-lookup"><span data-stu-id="74027-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="74027-329">**¿Puede haber varios formularios por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="74027-330">Sí, puede haber varios formularios asociados a un grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="74027-331">**¿Se pueden asociar formularios a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-332">No, un formulario solo se puede asociar a un único grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="74027-333">**¿Puede cambiar la asociación de un formulario con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="74027-334">No, una vez que un formulario está asociado a un grupo (creado directamente dentro o transferido de una persona) no se puede mover a otro grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="74027-335">**¿Elimina el formulario el grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="74027-336">No, no es posible eliminar un grupo de la interfaz de formularios, solo formularios individuales.</span><span class="sxs-lookup"><span data-stu-id="74027-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="74027-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="74027-337">OneNote</span></span>

<span data-ttu-id="74027-338">OneNote es una aplicación de bloc de notas digital.</span><span class="sxs-lookup"><span data-stu-id="74027-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="74027-339">El bloc de notas de OneNote creado con un grupo es un archivo en el sitio de SharePoint asociado en lugar de un servicio conectado a grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="74027-340">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="74027-341">Bloc de notas compartido (almacenado en la biblioteca de SharePoint asociada a grupos)</span><span class="sxs-lookup"><span data-stu-id="74027-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="74027-342">**¿Puede OneNote crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="74027-343">No, la aplicación de OneNote no puede crear un grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="74027-344">**¿Existen blocs de notas de OneNote sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="74027-345">Sí, los blocs de notas se pueden crear directamente en OneDrive o en otras ubicaciones compartidas.</span><span class="sxs-lookup"><span data-stu-id="74027-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="74027-346">**¿Puede haber varios blocs de notas de OneNote por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="74027-347">Sí, se crea un bloc de notas de forma predeterminada y se pueden agregar otros, pero cualquier vínculo a OneNote desde los servicios asociados al grupo siempre irá al bloc de notas predeterminado.</span><span class="sxs-lookup"><span data-stu-id="74027-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="74027-348">**¿Se puede asociar un bloc de notas de OneNote con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-349">No, el bloc de notas se almacena en la biblioteca de sitios de SharePoint asociada a grupos y se vincula desde varias interfaces.</span><span class="sxs-lookup"><span data-stu-id="74027-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="74027-350">Sin embargo, se puede compartir con otros grupos de la misma manera que se puede compartir con personas.</span><span class="sxs-lookup"><span data-stu-id="74027-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="74027-351">**¿Puede cambiar la asociación del bloc de notas con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="74027-352">No, el propio bloc de notas está asociado al grupo y se puede acceder directamente desde otros servicios conectados a grupos, pero el contenido se puede mover de un bloc de notas a otro dentro de la aplicación de OneNote.</span><span class="sxs-lookup"><span data-stu-id="74027-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="74027-353">**¿Elimina el grupo la eliminación del bloc de notas?**</span><span class="sxs-lookup"><span data-stu-id="74027-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="74027-354">No, sin embargo, si se elimina el bloc de notas de OneNote, puede haber vínculos rotos en algunos de los servicios asociados a grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="74027-355">Planner</span><span class="sxs-lookup"><span data-stu-id="74027-355">Planner</span></span>

<span data-ttu-id="74027-356">Planner es un servicio ligero de administración de tareas de grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="74027-357">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="74027-358">Panel para administrar tareas de grupo</span><span class="sxs-lookup"><span data-stu-id="74027-358">Board for managing group tasks</span></span>

<span data-ttu-id="74027-359">**¿Puede Planner crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="74027-360">Sí, la creación de un plan creará un nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="74027-361">**¿Existe un comité de Planner sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="74027-362">No, un plan debe estar asociado a un grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="74027-363">**¿Puede haber varios planes por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="74027-364">Sí, puede haber varios planes por grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="74027-365">**¿Se puede asociar un plan a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-366">No, un plan depende únicamente de la pertenencia a grupos para determinar el acceso.</span><span class="sxs-lookup"><span data-stu-id="74027-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="74027-367">**¿Puede cambiar la asociación de un plan con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="74027-368">No, sin embargo, al copiar un plan se crea un nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="74027-369">Un grupo creado por cualquier otra aplicación no se mostrará automáticamente en Planner para un usuario.</span><span class="sxs-lookup"><span data-stu-id="74027-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="74027-370">Para obtener acceso al tablero inicialmente, tendrán que abrirlo desde otra interfaz basada en grupos, como Outlook.</span><span class="sxs-lookup"><span data-stu-id="74027-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="74027-371">**¿Elimina el plan el grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="74027-372">Sí, al eliminar el plan se eliminará el contenido y los servicios asociados a grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="74027-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="74027-373">Power Apps</span></span>

<span data-ttu-id="74027-374">Power Apps proporciona un lienzo para el desarrollo de aplicaciones sin código.</span><span class="sxs-lookup"><span data-stu-id="74027-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="74027-375">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="74027-376">Las aplicaciones se pueden compartir con un grupo que se va a ejecutar y modificar</span><span class="sxs-lookup"><span data-stu-id="74027-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="74027-377">**¿Power Apps puede crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="74027-378">No, Power Apps no puede crear un grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="74027-379">**¿Existen Power Apps sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="74027-380">Sí, las aplicaciones se pueden crear en Power Apps y residir en la cuenta de creadores hasta que se compartan o publiquen.</span><span class="sxs-lookup"><span data-stu-id="74027-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="74027-381">**¿Puede haber varias aplicaciones por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="74027-382">Sí, puede haber varias aplicaciones compartidas con un grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="74027-383">**¿Se pueden asociar aplicaciones a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-384">Sí, una aplicación se puede compartir con varios grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="74027-385">**¿Puede cambiar la asociación de una aplicación con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="74027-386">Sí, como la asociación entre Power Apps y un grupo de Microsoft 365 solo está compartiendo; la aplicación aún reside con el creador.</span><span class="sxs-lookup"><span data-stu-id="74027-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74027-387">[Los grupos deben estar habilitados para la seguridad antes de que las aplicaciones se puedan compartir con ellos.](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="74027-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="74027-388">**¿Elimina la aplicación el grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="74027-389">No, las aplicaciones no están conectadas al grupo que no sean compartidas con ellas.</span><span class="sxs-lookup"><span data-stu-id="74027-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="74027-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="74027-390">Power Automate</span></span>

<span data-ttu-id="74027-391">Power Automate (anteriormente conocido como Microsoft Flow) proporciona flujos de trabajo y servicios de automatización.</span><span class="sxs-lookup"><span data-stu-id="74027-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="74027-392">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="74027-393">Los flujos de trabajo se pueden compartir con un grupo que se va a ejecutar y modificar.</span><span class="sxs-lookup"><span data-stu-id="74027-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="74027-394">**¿Power Automate puede crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="74027-395">No, Power Automate no puede crear un grupo de Microsoft 365 en el contexto de asociarse a uno.</span><span class="sxs-lookup"><span data-stu-id="74027-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="74027-396">Sin embargo, es posible crear un flujo que realice diversas operaciones, como crear un grupo de seguridad de Azure AD o actualizar la pertenencia a un grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="74027-397">**¿Existen flujos sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="74027-398">Sí, los flujos se pueden crear en Power Automate y residir en la cuenta de creadores hasta que se compartan o publiquen.</span><span class="sxs-lookup"><span data-stu-id="74027-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="74027-399">**¿Puede haber varios flujos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="74027-400">Sí, puede haber varios flujos compartidos con un grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="74027-401">**¿Se puede asociar un flujo a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-402">Sí, un flujo se puede compartir con varios grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="74027-403">**¿Puede cambiar la asociación de un flujo con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="74027-404">Sí, como la asociación entre Power Automate y un grupo de Microsoft 365 solo está compartiendo: el flujo aún reside con el creador.</span><span class="sxs-lookup"><span data-stu-id="74027-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="74027-405">**¿Elimina un flujo el grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="74027-406">No, al igual que Power Apps, los flujos no están conectados al grupo que no sean compartidos con ellos.</span><span class="sxs-lookup"><span data-stu-id="74027-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="74027-407">Power BI (clásico)</span><span class="sxs-lookup"><span data-stu-id="74027-407">Power BI (classic)</span></span>

<span data-ttu-id="74027-408">Power BI proporciona paneles e informes interactivos controlados por datos.</span><span class="sxs-lookup"><span data-stu-id="74027-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="74027-409">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="74027-410">Informes de datos</span><span class="sxs-lookup"><span data-stu-id="74027-410">Data reporting</span></span>

<span data-ttu-id="74027-411">**¿Power BI puede crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="74027-412">Sí, al crear un área de trabajo clásica se creará un grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="74027-413">**¿Existe un área de trabajo clásica de Power BI sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="74027-414">No, [un área de trabajo clásica en Power BI debe estar asociada a un grupo.](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace)</span><span class="sxs-lookup"><span data-stu-id="74027-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="74027-415">**¿Puede haber varias áreas de trabajo de Power BI por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="74027-416">No, la relación entre un área de trabajo clásica y un grupo es 1:1.</span><span class="sxs-lookup"><span data-stu-id="74027-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="74027-417">**¿Se puede asociar un área de trabajo con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-418">Técnicamente no, mientras que el área de trabajo clásica se crea con el grupo, el contenido se puede compartir fuera del grupo con usuarios y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="74027-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="74027-419">**¿Puede cambiar la asociación del área de trabajo con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="74027-420">No, el área de trabajo clásica está asociada con el grupo, pero el contenido se puede mover de un área de trabajo a otra dentro de la interfaz de Power BI o mediante la exportación de contenido localmente.</span><span class="sxs-lookup"><span data-stu-id="74027-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="74027-421">**¿Elimina el grupo la eliminación del área de trabajo?**</span><span class="sxs-lookup"><span data-stu-id="74027-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="74027-422">Sí, al eliminar el área de trabajo en Power BI se eliminará el contenido y los servicios asociados a grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="74027-423">Power BI (nuevo)</span><span class="sxs-lookup"><span data-stu-id="74027-423">Power BI (new)</span></span>

<span data-ttu-id="74027-424">Power BI proporciona paneles e informes interactivos controlados por datos.</span><span class="sxs-lookup"><span data-stu-id="74027-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="74027-425">Aunque la creación de un nuevo área de trabajo en Power BI no crea un grupo de Microsoft 365, la creación de un grupo por cualquier otro medio crea un área de trabajo nueva (no clásica) en Power BI.</span><span class="sxs-lookup"><span data-stu-id="74027-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="74027-426">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="74027-427">Informes de datos</span><span class="sxs-lookup"><span data-stu-id="74027-427">Data reporting</span></span>

<span data-ttu-id="74027-428">**¿Power BI puede crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="74027-429">No, no es posible crear un grupo de Microsoft 365 desde la nueva interfaz de Power BI.</span><span class="sxs-lookup"><span data-stu-id="74027-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="74027-430">**¿Existe el nuevo área de trabajo de Power BI sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="74027-431">Sí, es posible tener informes y áreas de trabajo creadas en Power BI que no estén asociadas a grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="74027-432">**¿Puede haber varias áreas de trabajo por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="74027-433">Sí, [se pueden compartir varias áreas de trabajo creadas](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)por Power BI con un solo grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="74027-434">**¿Se puede asociar un área de trabajo con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-435">No, un área de trabajo creada por Power BI solo se puede asociar a un solo grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="74027-436">**¿Puede cambiar la asociación de un área de trabajo con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="74027-437">Sí y no.</span><span class="sxs-lookup"><span data-stu-id="74027-437">Yes and no.</span></span> <span data-ttu-id="74027-438">Un área de trabajo creada por Power BI solo se puede asociar a un solo grupo a la vez, pero puede cambiar la asociación en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="74027-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="74027-439">Un área de trabajo creada en Power BI por un grupo se asocia permanentemente a ese grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="74027-440">**¿Elimina el grupo la eliminación del área de trabajo?**</span><span class="sxs-lookup"><span data-stu-id="74027-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="74027-441">Sí, al eliminar el área de trabajo en Power BI se eliminará el contenido y los servicios asociados a grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="74027-442">Project para la Web</span><span class="sxs-lookup"><span data-stu-id="74027-442">Project for the web</span></span>

<span data-ttu-id="74027-443">Project para la web ofrece la posibilidad de crear planes de proyecto, diagramas de Gantt y mapas de ruta.</span><span class="sxs-lookup"><span data-stu-id="74027-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="74027-444">Características clave proporcionadas a los grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-444">Key features provided to groups.</span></span>

- <span data-ttu-id="74027-445">Planes del proyecto</span><span class="sxs-lookup"><span data-stu-id="74027-445">Project plans</span></span>

<span data-ttu-id="74027-446">**¿Project para la web puede crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="74027-447">Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde Project para la web.</span><span class="sxs-lookup"><span data-stu-id="74027-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="74027-448">**¿Existen proyectos sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="74027-449">Sí, los proyectos pueden existir sin estar asociados a un grupo de Microsoft 365, pero la asignación de tareas requiere la asociación de grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="74027-450">**¿Puede haber varios proyectos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="74027-451">Sí, es posible conectar varios proyectos en un solo grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="74027-452">**¿Se puede asociar el proyecto a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-453">No, un proyecto solo se puede asociar a un solo grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="74027-454">**¿Puede cambiar la asociación de un proyecto con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="74027-455">No, una vez establecida la asociación con un grupo, no puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="74027-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="74027-456">**¿Elimina el proyecto el grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="74027-457">No, al eliminar el proyecto en Project para la web no se eliminará el grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="74027-458">Guía básica</span><span class="sxs-lookup"><span data-stu-id="74027-458">Roadmap</span></span>

<span data-ttu-id="74027-459">El mapa de ruta proporciona la capacidad de crear guías básicas de proyectos con Project para la web y Project Online.</span><span class="sxs-lookup"><span data-stu-id="74027-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="74027-460">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="74027-461">Guías básicas del proyecto</span><span class="sxs-lookup"><span data-stu-id="74027-461">Project roadmaps</span></span>

<span data-ttu-id="74027-462">**¿Puede crear un grupo el mapa de ruta?**</span><span class="sxs-lookup"><span data-stu-id="74027-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="74027-463">Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde el mapa de ruta.</span><span class="sxs-lookup"><span data-stu-id="74027-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="74027-464">**¿Existe la guía básica sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="74027-465">Sí, pueden existir guías básicas sin estar asociadas a un grupo de Microsoft 365, pero compartirla requiere la asociación de grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="74027-466">**¿Puede haber varias guías básicas por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="74027-467">Sí, es posible conectar varias guías básicas a un solo grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="74027-468">**¿Se puede asociar un mapa de ruta con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-469">No, una guía básica solo se puede asociar a un solo grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="74027-470">**¿Puede cambiar la asociación de un mapa de ruta con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="74027-471">No, una vez establecida la asociación con un grupo, no puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="74027-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="74027-472">**¿Elimina el plan de desarrollo el grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="74027-473">No, al eliminar el mapa de ruta no se eliminará el grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="74027-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="74027-474">SharePoint</span></span>

<span data-ttu-id="74027-475">SharePoint es una plataforma de administración de contenido basada en web que proporciona, entre otras cosas, servicios de almacenamiento para una serie de servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="74027-476">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="74027-477">Biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="74027-477">Document library</span></span>
- <span data-ttu-id="74027-478">Biblioteca para el almacenamiento del bloc de notas de OneNote</span><span class="sxs-lookup"><span data-stu-id="74027-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="74027-479">Almacenamiento de archivos wiki de Teams</span><span class="sxs-lookup"><span data-stu-id="74027-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="74027-480">**¿Puede SharePoint crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="74027-481">Sí, la creación de un sitio de grupo en SharePoint creará un grupo de Microsoft 365 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="74027-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="74027-482">También es posible crear un grupo y, opcionalmente, un equipo para un sitio existente.</span><span class="sxs-lookup"><span data-stu-id="74027-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="74027-483">**¿Existen sitios de SharePoint sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="74027-484">Sí, SharePoint ofrece una serie de sitios y servicios no asociados a grupos, como sitios de concentradores y de comunicación.</span><span class="sxs-lookup"><span data-stu-id="74027-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="74027-485">**¿Puede haber varios sitios por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="74027-486">No, solo puede haber un único sitio por grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="74027-487">Los canales privados en Teams usan sitios adicionales que no están conectados al grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="74027-488">**¿Se pueden asociar sitios a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-489">Técnicamente no, pero mientras se crea un sitio con un grupo, el contenido se puede compartir con otros grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="74027-490">**¿Puede cambiar la asociación de un sitio con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="74027-491">No, el propio sitio está asociado al grupo, pero el contenido se puede mover de un sitio a otro dentro de la interfaz de SharePoint, exportando contenido localmente o mediante una herramienta de terceros.</span><span class="sxs-lookup"><span data-stu-id="74027-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="74027-492">**¿Elimina el sitio el grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="74027-493">Sí, al eliminar el sitio en SharePoint se eliminará el contenido y los servicios asociados a grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="74027-494">Stream</span><span class="sxs-lookup"><span data-stu-id="74027-494">Stream</span></span>

<span data-ttu-id="74027-495">Microsoft Stream es una plataforma de hospedaje y uso compartido de vídeo.</span><span class="sxs-lookup"><span data-stu-id="74027-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="74027-496">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="74027-497">Almacenamiento de vídeo</span><span class="sxs-lookup"><span data-stu-id="74027-497">Video storage</span></span>
- <span data-ttu-id="74027-498">Grabación de reuniones de Teams</span><span class="sxs-lookup"><span data-stu-id="74027-498">Teams meeting recording</span></span>
- <span data-ttu-id="74027-499">Canales de vídeo</span><span class="sxs-lookup"><span data-stu-id="74027-499">Video channels</span></span>

<span data-ttu-id="74027-500">**¿Puede Stream crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="74027-501">Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde Stream.</span><span class="sxs-lookup"><span data-stu-id="74027-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="74027-502">**¿Existe Stream sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="74027-503">Sí, los canales de vídeo y los vídeos pueden existir en Stream sin estar asociados a un grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="74027-504">**¿Puede haber varios vídeos y canales por grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="74027-505">Sí, puede haber varios vídeos y canales en cada grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="74027-506">**¿Se puede asociar un vídeo o canal con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="74027-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="74027-507">Sí, mientras se crea un vídeo o canal con un grupo, se puede compartir con otros grupos.</span><span class="sxs-lookup"><span data-stu-id="74027-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="74027-508">**¿Puede cambiar su asociación con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="74027-509">Sí y no; Los vídeos de Stream son propiedad del uploader original o la grabadora de reuniones, por lo que pueden asociarse con cualquier grupo, pero los canales de vídeo solo pueden asociarse con el grupo en el que se crearon originalmente.</span><span class="sxs-lookup"><span data-stu-id="74027-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="74027-510">**¿La eliminación de vídeos o canales elimina el grupo?**</span><span class="sxs-lookup"><span data-stu-id="74027-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="74027-511">No, la eliminación de vídeos o canales no elimina el grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="74027-512">Sin embargo, al eliminar el propio grupo en Stream se eliminarán los servicios y el contenido asociados al grupo, excepto los vídeos reales.</span><span class="sxs-lookup"><span data-stu-id="74027-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="74027-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="74027-513">Yammer</span></span>

<span data-ttu-id="74027-514">Yammer es una plataforma social empresarial diseñada para fomentar el compromiso de la comunidad dentro y entre organizaciones.</span><span class="sxs-lookup"><span data-stu-id="74027-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="74027-515">La creación de una comunidad (anteriormente conocida como "grupo") en Yammer crea un buzón, pero actualmente no se usa.</span><span class="sxs-lookup"><span data-stu-id="74027-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="74027-516">Un grupo de Microsoft 365 asociado a Yammer no se puede usar con un equipo de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="74027-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="74027-517">**Características clave proporcionadas a grupos**</span><span class="sxs-lookup"><span data-stu-id="74027-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="74027-518">Área de conversación</span><span class="sxs-lookup"><span data-stu-id="74027-518">Conversation area</span></span>

<span data-ttu-id="74027-519">**¿Puede Yammer crear un grupo de Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="74027-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="74027-520">Sí, la creación de un nuevo grupo en Yammer creará un nuevo grupo de Microsoft 365, si las plataformas están conectadas y el usuario tiene la capacidad de crear un grupo.</span><span class="sxs-lookup"><span data-stu-id="74027-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="74027-521">Un grupo de Yammer con el grupo asociado de Microsoft 365 no se puede crear en ninguna interfaz o servicio que no sea yammer.</span><span class="sxs-lookup"><span data-stu-id="74027-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="74027-522">**¿Existe un grupo de Yammer sin un grupo de Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="74027-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="74027-523">Sí, es posible crear un grupo de Yammer sin un grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="74027-524">Si la plataforma Yammer no está conectada a grupos de Microsoft 365 o los usuarios no pueden crear un grupo de Microsoft 365, los grupos de Yammer se crean sin una asociación de grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="74027-525">**¿Puede haber varios grupos de Yammer por grupo de Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="74027-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="74027-526">No, la relación entre un grupo de Yammer y un grupo de Microsoft 365 es 1:1.</span><span class="sxs-lookup"><span data-stu-id="74027-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="74027-527">**¿Se puede asociar un grupo de Yammer a varios grupos de Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="74027-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="74027-528">No, el grupo de Yammer solo se puede asociar a un único grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74027-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="74027-529">Es posible que las publicaciones se compartan o se traslade a otros grupos de Yammer.</span><span class="sxs-lookup"><span data-stu-id="74027-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="74027-530">**¿Puede cambiar la asociación de un grupo de Yammer con un grupo de Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="74027-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="74027-531">No, el grupo de Yammer solo puede asociarse con el grupo de Microsoft 365 al que se asoció originalmente.</span><span class="sxs-lookup"><span data-stu-id="74027-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="74027-532">**¿Elimina el grupo de Yammer el grupo de Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="74027-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="74027-533">Sí, al eliminar el grupo en Yammer se eliminará el contenido y los servicios asociados a grupos de Microsoft relacionados.</span><span class="sxs-lookup"><span data-stu-id="74027-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="74027-534">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="74027-534">Related topics</span></span>

[<span data-ttu-id="74027-535">Planeación paso a paso del gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="74027-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="74027-536">Crear un plan de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="74027-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

