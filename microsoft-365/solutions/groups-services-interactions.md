---
title: Interacciones de los servicios de grupos
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
description: Interacciones de los servicios de grupos
ms.openlocfilehash: 6d5681b11cdbd837f784b6c8364cce23f964b167
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613231"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="36ae7-103">Interacciones de los servicios de grupos</span><span class="sxs-lookup"><span data-stu-id="36ae7-103">Groups services interactions</span></span>

<span data-ttu-id="36ae7-104">Microsoft 365 grupos proporciona una estructura común para varios servicios y cargas de trabajo dentro de la plataforma de Microsoft 365 para ofrecer una experiencia de conexión para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="36ae7-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="36ae7-105">En esencia, existe un grupo de Microsoft 365 para proporcionar:</span><span class="sxs-lookup"><span data-stu-id="36ae7-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="36ae7-106">Una forma de administrar la pertenencia (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="36ae7-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="36ae7-107">Un espacio para la mensajería y las conversaciones que se deben realizar (buzón de correo de Exchange, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="36ae7-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="36ae7-108">Un espacio para que se almacenen los archivos (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="36ae7-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="36ae7-109">Un calendario para la programación (Exchange)</span><span class="sxs-lookup"><span data-stu-id="36ae7-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="36ae7-110">Un bloc de notas para capturar notas (OneNote)</span><span class="sxs-lookup"><span data-stu-id="36ae7-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="36ae7-111">En el punto de creación del grupo, también se aprovisionan otros recursos, aunque no son visibles hasta que se accede a ellos por primera vez desde el servicio:</span><span class="sxs-lookup"><span data-stu-id="36ae7-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="36ae7-112">Un panel para administrar tareas de grupo (Planner)</span><span class="sxs-lookup"><span data-stu-id="36ae7-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="36ae7-113">Un área de trabajo para informes (Power BI)</span><span class="sxs-lookup"><span data-stu-id="36ae7-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="36ae7-114">Un área para vídeos compartidos (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="36ae7-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="36ae7-115">Un área para formularios compartidos (formularios)</span><span class="sxs-lookup"><span data-stu-id="36ae7-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="36ae7-116">En Microsoft 365, otros servicios pueden interactuar con los grupos de Microsoft 365 para ofrecer funcionalidad y capacidades adicionales a los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="36ae7-117">Algunos ejemplos son:</span><span class="sxs-lookup"><span data-stu-id="36ae7-117">Examples of this include:</span></span>

- <span data-ttu-id="36ae7-118">Power apps for apps</span><span class="sxs-lookup"><span data-stu-id="36ae7-118">Power Apps for apps</span></span>
- <span data-ttu-id="36ae7-119">Automatizar la alimentación para flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="36ae7-119">Power Automate for workflows</span></span>
- <span data-ttu-id="36ae7-120">Proyecto en la web y mapa de ruta para la administración de proyectos en cascada</span><span class="sxs-lookup"><span data-stu-id="36ae7-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="36ae7-121">Teams para conversaciones basadas en canal</span><span class="sxs-lookup"><span data-stu-id="36ae7-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="36ae7-122">Yammer para comunidades de interés</span><span class="sxs-lookup"><span data-stu-id="36ae7-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="36ae7-123">Interacciones del usuario con grupos</span><span class="sxs-lookup"><span data-stu-id="36ae7-123">User interactions with groups</span></span>

<span data-ttu-id="36ae7-124">Los grupos de 365 de Microsoft se pueden crear y administrar desde una amplia variedad de interfaces, tanto por los administradores como por los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="36ae7-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="36ae7-125">Experiencias administrativas</span><span class="sxs-lookup"><span data-stu-id="36ae7-125">Administrative experiences</span></span>

<span data-ttu-id="36ae7-126">Los administradores pueden crear y administrar grupos de Microsoft 365 desde varios centros de administración de cargas de trabajo, interfaces de línea de comandos que admitan scripting, así como aplicaciones personalizadas que interactúen con la API de Graph.</span><span class="sxs-lookup"><span data-stu-id="36ae7-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="36ae7-127">La única excepción a esto son los grupos de Yammer, que se deben crear desde dentro de la interfaz Web de Yammer.</span><span class="sxs-lookup"><span data-stu-id="36ae7-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="36ae7-128">**Configuración relacionada**</span><span class="sxs-lookup"><span data-stu-id="36ae7-128">**Related settings**</span></span>

<span data-ttu-id="36ae7-129">En las distintas interfaces administrativas que pueden administrar la configuración de un grupo existen varios solapamiento que debe tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="36ae7-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="36ae7-130">**Centro de administración de Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="36ae7-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="36ae7-131">En el centro de administración de 365 de Microsoft, el acceso de invitado a grupos está habilitado de forma predeterminada, al igual que la capacidad de permitir que los propietarios agreguen invitados.</span><span class="sxs-lookup"><span data-stu-id="36ae7-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="36ae7-132">No hay otros controles de nivel de organización disponibles para los grupos desde este centro de administración.</span><span class="sxs-lookup"><span data-stu-id="36ae7-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="36ae7-133">**Centro de administración de Azure AD**</span><span class="sxs-lookup"><span data-stu-id="36ae7-133">**Azure AD admin center**</span></span>

<span data-ttu-id="36ae7-134">El centro de administración de Azure AD ofrece controles sobre si los usuarios pueden crear grupos o asignar propietarios en los portales de Azure, así como la configuración de caducidad y de la Directiva de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="36ae7-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="36ae7-135">El centro de administración también proporciona varias medidas de control de invitación de invitado que van más allá de la del centro de administración de Microsoft 365, como la capacidad de limitar si los no propietarios también pueden invitar a invitados</span><span class="sxs-lookup"><span data-stu-id="36ae7-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="36ae7-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="36ae7-136">**SharePoint**</span></span>

<span data-ttu-id="36ae7-137">Los sitios de SharePoint se crean con grupos de seguridad de propietario, miembro y visitante, con las dos primeras que coinciden con sus homólogos de grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36ae7-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="36ae7-138">Aunque la pertenencia a sitios de SharePoint Online suele estar administrada por el grupo de Microsoft 365 asociado, no es una relación bidireccional.</span><span class="sxs-lookup"><span data-stu-id="36ae7-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="36ae7-139">Los cambios en la pertenencia en el nivel de grupo de Microsoft 365 se reflejan en SharePoint, sin embargo, si se modifica la pertenencia en el grupo de SharePoint, esto no se refleja en el grupo 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36ae7-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="36ae7-140">Experiencias de usuario</span><span class="sxs-lookup"><span data-stu-id="36ae7-140">User experiences</span></span>

<span data-ttu-id="36ae7-141">Los usuarios finales pueden crear grupos a partir de varios de los servicios de Microsoft 365 y en otros que solo pueden compartir con un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="36ae7-142">Los siguientes servicios permiten la creación de grupos por parte de los usuarios finales:</span><span class="sxs-lookup"><span data-stu-id="36ae7-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="36ae7-143">Proyecto de Outlook Planner para la secuencia de SharePoint Web Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="36ae7-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="36ae7-144">**Restricción de la creación de grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-144">**Restriction of group creation**</span></span>

<span data-ttu-id="36ae7-145">Un enfoque común para controlar la proliferación de equipos es limitar los usuarios que pueden crearlos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="36ae7-146">Esto solo puede hacerse limitando la creación de grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="36ae7-147">Esto afecta a la capacidad de crear grupos desde otros servicios en los que puede ser necesario para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="36ae7-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="36ae7-148">Los grupos de 365 de Microsoft no admiten la capacidad de restringir la creación de grupos a partir de algunas aplicaciones o servicios a la vez que se permite en otros.</span><span class="sxs-lookup"><span data-stu-id="36ae7-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="36ae7-149">La experiencia de la restricción de creación de grupos varía entre aplicaciones y servicios:</span><span class="sxs-lookup"><span data-stu-id="36ae7-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="36ae7-150">Aplicación o servicio</span><span class="sxs-lookup"><span data-stu-id="36ae7-150">App or service</span></span>|<span data-ttu-id="36ae7-151">Experiencia</span><span class="sxs-lookup"><span data-stu-id="36ae7-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="36ae7-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="36ae7-152">Outlook</span></span>|<span data-ttu-id="36ae7-153">La opción **nuevo grupo** se ha quitado del menú nuevo en la página personas</span><span class="sxs-lookup"><span data-stu-id="36ae7-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="36ae7-154">Planner</span><span class="sxs-lookup"><span data-stu-id="36ae7-154">Planner</span></span>|<span data-ttu-id="36ae7-155">**Nuevo plan** explica que la creación de grupos se ha desactivado y ofrece agregar el plan a un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="36ae7-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="36ae7-156">Proyecto para la web y la guía básica</span><span class="sxs-lookup"><span data-stu-id="36ae7-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="36ae7-157">El menú **Crear grupo** explica que la creación de grupos está restringida y sugiere el uso de un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="36ae7-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="36ae7-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="36ae7-158">SharePoint</span></span>|<span data-ttu-id="36ae7-159">Todavía puede crear un sitio de grupo que no esté conectado a un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="36ae7-160">Stream</span><span class="sxs-lookup"><span data-stu-id="36ae7-160">Stream</span></span>|<span data-ttu-id="36ae7-161">La opción **Grupo** no aparece en el **menú crear**.</span><span class="sxs-lookup"><span data-stu-id="36ae7-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="36ae7-162">Teams</span><span class="sxs-lookup"><span data-stu-id="36ae7-162">Teams</span></span>|<span data-ttu-id="36ae7-163">El usuario no puede crear un equipo con un grupo nuevo, pero todavía puede crear un equipo que use un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="36ae7-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="36ae7-164">**El botón crear un equipo** se ha reemplazado por **crear equipo desde un grupo**.</span><span class="sxs-lookup"><span data-stu-id="36ae7-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="36ae7-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="36ae7-165">Yammer</span></span>|<span data-ttu-id="36ae7-166">**Crear una** opción de grupo se ha quitado de la navegación de grupos principales/comunidades.</span><span class="sxs-lookup"><span data-stu-id="36ae7-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="36ae7-167">Interacciones de servicios con grupos</span><span class="sxs-lookup"><span data-stu-id="36ae7-167">Services interactions with groups</span></span>

<span data-ttu-id="36ae7-168">Vea los grupos en el póster de Microsoft 365 para obtener información sobre los distintos tipos de grupos, cómo se crean y administran, y algunas recomendaciones de gobierno.</span><span class="sxs-lookup"><span data-stu-id="36ae7-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="36ae7-169">[![Imagen en miniatura para la infografía de grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="36ae7-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="36ae7-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="36ae7-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="36ae7-171">En la siguiente tabla se proporciona una introducción a las interacciones de Microsoft 365 Groups con varios servicios:</span><span class="sxs-lookup"><span data-stu-id="36ae7-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="36ae7-172">Producto</span><span class="sxs-lookup"><span data-stu-id="36ae7-172">Product</span></span>|<span data-ttu-id="36ae7-173">Características</span><span class="sxs-lookup"><span data-stu-id="36ae7-173">Features</span></span>|<span data-ttu-id="36ae7-174">¿El servicio</span><span class="sxs-lookup"><span data-stu-id="36ae7-174">Does the service</span></span><br><span data-ttu-id="36ae7-175">¿existe sin un grupo?</span><span class="sxs-lookup"><span data-stu-id="36ae7-175">exist without a group?</span></span>|<span data-ttu-id="36ae7-176">Puede el servicio</span><span class="sxs-lookup"><span data-stu-id="36ae7-176">Can the service</span></span><br><span data-ttu-id="36ae7-177">¿crear un grupo?</span><span class="sxs-lookup"><span data-stu-id="36ae7-177">create a group?</span></span>|<span data-ttu-id="36ae7-178">Elimina el</span><span class="sxs-lookup"><span data-stu-id="36ae7-178">Does deleting the</span></span><br><span data-ttu-id="36ae7-179">instancia ¿eliminar el grupo?</span><span class="sxs-lookup"><span data-stu-id="36ae7-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="36ae7-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="36ae7-180">Azure AD</span></span>|<span data-ttu-id="36ae7-181">Pertenencia, controles de grupo, invitados</span><span class="sxs-lookup"><span data-stu-id="36ae7-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="36ae7-182">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-182">Yes</span></span>|<span data-ttu-id="36ae7-183">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-183">Yes</span></span>|<span data-ttu-id="36ae7-184">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-184">Yes</span></span>|
|<span data-ttu-id="36ae7-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="36ae7-185">Exchange</span></span>|<span data-ttu-id="36ae7-186">Calendario, buzón de correo</span><span class="sxs-lookup"><span data-stu-id="36ae7-186">Calendar, mailbox</span></span>|<span data-ttu-id="36ae7-187">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-187">Yes</span></span>|<span data-ttu-id="36ae7-188">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-188">Yes</span></span>|<span data-ttu-id="36ae7-189">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-189">Yes</span></span>|
|<span data-ttu-id="36ae7-190">Forms</span><span class="sxs-lookup"><span data-stu-id="36ae7-190">Forms</span></span>|<span data-ttu-id="36ae7-191">Form</span><span class="sxs-lookup"><span data-stu-id="36ae7-191">Form</span></span>|<span data-ttu-id="36ae7-192">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-192">Yes</span></span>|<span data-ttu-id="36ae7-193">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-193">No</span></span>|<span data-ttu-id="36ae7-194">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-194">No</span></span>|
|<span data-ttu-id="36ae7-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="36ae7-195">OneNote</span></span>|<span data-ttu-id="36ae7-196">Bloc de notas</span><span class="sxs-lookup"><span data-stu-id="36ae7-196">Notebook</span></span>|<span data-ttu-id="36ae7-197">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-197">Yes</span></span>|<span data-ttu-id="36ae7-198">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-198">No</span></span>|<span data-ttu-id="36ae7-199">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-199">No</span></span>|
|<span data-ttu-id="36ae7-200">Planner</span><span class="sxs-lookup"><span data-stu-id="36ae7-200">Planner</span></span>|<span data-ttu-id="36ae7-201">Panel de tareas</span><span class="sxs-lookup"><span data-stu-id="36ae7-201">Task board</span></span>|<span data-ttu-id="36ae7-202">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-202">No</span></span>|<span data-ttu-id="36ae7-203">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-203">Yes</span></span>|<span data-ttu-id="36ae7-204">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-204">Yes</span></span>|
|<span data-ttu-id="36ae7-205">Aplicación de Power apps</span><span class="sxs-lookup"><span data-stu-id="36ae7-205">Power Apps app</span></span>|<span data-ttu-id="36ae7-206">Aplicación</span><span class="sxs-lookup"><span data-stu-id="36ae7-206">App</span></span>|<span data-ttu-id="36ae7-207">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-207">Yes</span></span>|<span data-ttu-id="36ae7-208">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-208">No</span></span>|<span data-ttu-id="36ae7-209">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-209">No</span></span>|
|<span data-ttu-id="36ae7-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="36ae7-210">Power Automate</span></span>|<span data-ttu-id="36ae7-211">Flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="36ae7-211">Workflow</span></span>|<span data-ttu-id="36ae7-212">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-212">Yes</span></span>|<span data-ttu-id="36ae7-213">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-213">No</span></span>|<span data-ttu-id="36ae7-214">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-214">No</span></span>|
|<span data-ttu-id="36ae7-215">Power BI (clásico)</span><span class="sxs-lookup"><span data-stu-id="36ae7-215">Power BI (classic)</span></span>|<span data-ttu-id="36ae7-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="36ae7-216">Workspace</span></span>|<span data-ttu-id="36ae7-217">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-217">No</span></span>|<span data-ttu-id="36ae7-218">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-218">Yes</span></span>|<span data-ttu-id="36ae7-219">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-219">Yes</span></span>|
|<span data-ttu-id="36ae7-220">Power BI (nueva)</span><span class="sxs-lookup"><span data-stu-id="36ae7-220">Power BI (new)</span></span>|<span data-ttu-id="36ae7-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="36ae7-221">Workspace</span></span>|<span data-ttu-id="36ae7-222">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-222">Yes</span></span>|<span data-ttu-id="36ae7-223">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-223">No</span></span>|<span data-ttu-id="36ae7-224">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-224">Yes</span></span>|
|<span data-ttu-id="36ae7-225">Project para la Web</span><span class="sxs-lookup"><span data-stu-id="36ae7-225">Project for the web</span></span>|<span data-ttu-id="36ae7-226">Plan del proyecto</span><span class="sxs-lookup"><span data-stu-id="36ae7-226">Project plan</span></span>|<span data-ttu-id="36ae7-227">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-227">Yes</span></span>|<span data-ttu-id="36ae7-228">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-228">Yes</span></span>|<span data-ttu-id="36ae7-229">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-229">No</span></span>|
|<span data-ttu-id="36ae7-230">Guía básica</span><span class="sxs-lookup"><span data-stu-id="36ae7-230">Roadmap</span></span>|<span data-ttu-id="36ae7-231">Guía básica</span><span class="sxs-lookup"><span data-stu-id="36ae7-231">Roadmap</span></span>|<span data-ttu-id="36ae7-232">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-232">Yes</span></span>|<span data-ttu-id="36ae7-233">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-233">Yes</span></span>|<span data-ttu-id="36ae7-234">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-234">No</span></span>|
|<span data-ttu-id="36ae7-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="36ae7-235">SharePoint</span></span>|<span data-ttu-id="36ae7-236">Site</span><span class="sxs-lookup"><span data-stu-id="36ae7-236">Site</span></span>|<span data-ttu-id="36ae7-237">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-237">Yes</span></span>|<span data-ttu-id="36ae7-238">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-238">Yes</span></span>|<span data-ttu-id="36ae7-239">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-239">Yes</span></span>|
|<span data-ttu-id="36ae7-240">Stream</span><span class="sxs-lookup"><span data-stu-id="36ae7-240">Stream</span></span>|<span data-ttu-id="36ae7-241">Canal, vídeo</span><span class="sxs-lookup"><span data-stu-id="36ae7-241">Channel, video</span></span>|<span data-ttu-id="36ae7-242">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-242">Yes</span></span>|<span data-ttu-id="36ae7-243">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-243">Yes</span></span>|<span data-ttu-id="36ae7-244">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-244">Yes</span></span>|
|<span data-ttu-id="36ae7-245">Teams</span><span class="sxs-lookup"><span data-stu-id="36ae7-245">Teams</span></span>|<span data-ttu-id="36ae7-246">Equipo</span><span class="sxs-lookup"><span data-stu-id="36ae7-246">Team</span></span>|<span data-ttu-id="36ae7-247">No</span><span class="sxs-lookup"><span data-stu-id="36ae7-247">No</span></span>|<span data-ttu-id="36ae7-248">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-248">Yes</span></span>|<span data-ttu-id="36ae7-249">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-249">Yes</span></span>|
|<span data-ttu-id="36ae7-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="36ae7-250">Yammer</span></span>|<span data-ttu-id="36ae7-251">Group</span><span class="sxs-lookup"><span data-stu-id="36ae7-251">Group</span></span>|<span data-ttu-id="36ae7-252">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-252">Yes</span></span>|<span data-ttu-id="36ae7-253">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-253">Yes</span></span>|<span data-ttu-id="36ae7-254">Sí</span><span class="sxs-lookup"><span data-stu-id="36ae7-254">Yes</span></span>|

<span data-ttu-id="36ae7-255">Aunque en la tabla anterior se proporciona una descripción general de alto nivel de las interacciones de grupo con los servicios de Microsoft 365, hay una serie de matices y complejidades que debe comprender.</span><span class="sxs-lookup"><span data-stu-id="36ae7-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="36ae7-256">En las siguientes secciones se ofrece una visión más detallada de las cargas de trabajo específicas y sus interacciones con los grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="36ae7-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="36ae7-257">Azure AD</span></span>

<span data-ttu-id="36ae7-258">Azure AD proporciona las capacidades de administración de identidades subyacentes en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36ae7-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="36ae7-259">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="36ae7-260">Pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="36ae7-260">Group membership</span></span>
- <span data-ttu-id="36ae7-261">Directiva de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="36ae7-261">Naming policy</span></span>
- <span data-ttu-id="36ae7-262">Directiva de expiración</span><span class="sxs-lookup"><span data-stu-id="36ae7-262">Expiration policy</span></span>
- <span data-ttu-id="36ae7-263">Visitantes</span><span class="sxs-lookup"><span data-stu-id="36ae7-263">Guests</span></span>
- <span data-ttu-id="36ae7-264">Restricción de la creación de grupos</span><span class="sxs-lookup"><span data-stu-id="36ae7-264">Restriction of Group creation</span></span>

<span data-ttu-id="36ae7-265">**¿Puede Azure AD crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="36ae7-266">Sí, los grupos de 365 de Microsoft se pueden crear desde Azure AD a través del portal web de administración, a través de PowerShell o la API de Graph.</span><span class="sxs-lookup"><span data-stu-id="36ae7-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="36ae7-267">**¿Hay Azure AD sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="36ae7-268">Sí, Azure AD realiza un gran número de servicios que no tienen relación con los grupos de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36ae7-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="36ae7-269">Cada grupo de Microsoft 365 se representa como un objeto en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="36ae7-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="36ae7-270">**¿Puede haber varias instancias de Azure AD por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="36ae7-271">No, solo hay una instancia de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="36ae7-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="36ae7-272">**¿Puede asociarse Azure AD con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="36ae7-273">Sí, porque Azure AD es la plataforma subyacente que proporciona el servicio de pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="36ae7-274">**¿Puede la Asociación de Azure AD con un cambio de grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="36ae7-275">No, Azure AD es la plataforma subyacente en la que se encuentran los grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="36ae7-276">**¿Se elimina la instancia, elimine el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="36ae7-277">Al eliminar el grupo en Azure AD, se eliminará el contenido y los servicios relacionados con el grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="36ae7-278">Teams</span><span class="sxs-lookup"><span data-stu-id="36ae7-278">Teams</span></span>

<span data-ttu-id="36ae7-279">Teams es un área de trabajo centrada en chat que tiene como objetivo mejorar la colaboración al ofrecer una interfaz singular para interactuar con una variedad de servicios de Microsoft y de terceros.</span><span class="sxs-lookup"><span data-stu-id="36ae7-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="36ae7-280">De forma predeterminada, cuando se crea un equipo, el buzón y el calendario asociados con el grupo de Microsoft 365 están ocultos en la lista global de direcciones de Exchange, así como en Outlook.</span><span class="sxs-lookup"><span data-stu-id="36ae7-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="36ae7-281">Esto puede ser reemplazado manualmente por un administrador si el usuario desea usar Outlook y Teams en el mismo grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36ae7-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="36ae7-282">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="36ae7-283">Conversaciones</span><span class="sxs-lookup"><span data-stu-id="36ae7-283">Conversations</span></span>
- <span data-ttu-id="36ae7-284">Fichas de & de canales</span><span class="sxs-lookup"><span data-stu-id="36ae7-284">Channels & tabs</span></span>
- <span data-ttu-id="36ae7-285">Reuniones</span><span class="sxs-lookup"><span data-stu-id="36ae7-285">Meetings</span></span>

<span data-ttu-id="36ae7-286">**¿Puede Teams crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="36ae7-287">Sí, la creación de un nuevo equipo creará un nuevo grupo de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36ae7-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="36ae7-288">También es posible crear un equipo para un grupo existente que no tiene actualmente uno.</span><span class="sxs-lookup"><span data-stu-id="36ae7-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="36ae7-289">**¿Existen equipos sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="36ae7-290">No, no es posible que exista un equipo sin un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="36ae7-291">**¿Puede haber varios equipos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="36ae7-292">No, la relación entre un equipo y un grupo es de 1:1.</span><span class="sxs-lookup"><span data-stu-id="36ae7-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="36ae7-293">**¿Se puede asociar un equipo a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-294">No, el equipo en sí solo puede estar asociado a un único grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="36ae7-295">**¿Puede una asociación de un equipo con un cambio de grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="36ae7-296">No, el equipo solo puede asociarse con el grupo al que estaba asociado originalmente.</span><span class="sxs-lookup"><span data-stu-id="36ae7-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="36ae7-297">**¿Se elimina el equipo, ¿eliminar el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="36ae7-298">Sí, al eliminar el equipo en Microsoft Teams, se eliminarán el grupo, los servicios asociados a grupos y el contenido.</span><span class="sxs-lookup"><span data-stu-id="36ae7-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="36ae7-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="36ae7-299">Exchange</span></span>

<span data-ttu-id="36ae7-300">Exchange Online proporciona mensajería, calendario, contactos y funcionalidad asociada.</span><span class="sxs-lookup"><span data-stu-id="36ae7-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="36ae7-301">En el contexto de un grupo, solo hay asociado un único recurso, en lugar de una instancia de servicio completa.</span><span class="sxs-lookup"><span data-stu-id="36ae7-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="36ae7-302">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="36ae7-303">Buzón y calendario</span><span class="sxs-lookup"><span data-stu-id="36ae7-303">Mailbox and calendar</span></span>
- <span data-ttu-id="36ae7-304">Capacidad para enviar por correo electrónico todos los miembros del grupo</span><span class="sxs-lookup"><span data-stu-id="36ae7-304">Ability to email all Group members</span></span>
- <span data-ttu-id="36ae7-305">Almacenamiento de conversaciones de canal de Microsoft Teams para fines de eDiscovery, comentarios de Planner</span><span class="sxs-lookup"><span data-stu-id="36ae7-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="36ae7-306">**¿Puede Exchange crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="36ae7-307">Sí, es posible crear un grupo desde el centro de administración de Exchange Online, así como desde Outlook.</span><span class="sxs-lookup"><span data-stu-id="36ae7-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="36ae7-308">También puede convertir las listas de distribución de Exchange a grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36ae7-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="36ae7-309">**¿Existe Exchange sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="36ae7-310">Sí, Exchange Online proporciona una serie de servicios, como buzones y calendarios compartidos, sin ninguna asociación de grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="36ae7-311">**¿Puede haber varias instancias de buzones o calendarios de Exchange por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="36ae7-312">No, solo puede haber un único buzón de correo de Exchange Online y un calendario para un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="36ae7-313">**¿Los buzones de correo y los calendarios de Exchange se pueden asociar a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-314">No, el buzón y el calendario tienen una relación de 1:1 con el grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="36ae7-315">Es posible compartir el buzón con otros usuarios o grupos, pero esto no establece ninguna asociación de servicio.</span><span class="sxs-lookup"><span data-stu-id="36ae7-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="36ae7-316">**¿Puede cambiar el buzón o la Asociación del calendario de Exchange con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="36ae7-317">No, el buzón y el calendario no se pueden cambiar a un grupo diferente.</span><span class="sxs-lookup"><span data-stu-id="36ae7-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="36ae7-318">Sin embargo, el contenido se puede mover de un buzón de correo a otro dentro de Outlook o mediante una herramienta de terceros.</span><span class="sxs-lookup"><span data-stu-id="36ae7-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="36ae7-319">**¿Se elimina el buzón ¿eliminar el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="36ae7-320">Sí, al eliminar el buzón de Exchange se eliminará el grupo, así como el contenido y los servicios asociados a un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="36ae7-321">Forms</span><span class="sxs-lookup"><span data-stu-id="36ae7-321">Forms</span></span>

<span data-ttu-id="36ae7-322">Forms proporciona encuestas y cuestionarios basados en Web.</span><span class="sxs-lookup"><span data-stu-id="36ae7-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="36ae7-323">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="36ae7-324">Propiedad de los formularios</span><span class="sxs-lookup"><span data-stu-id="36ae7-324">Ownership of forms</span></span>

<span data-ttu-id="36ae7-325">**¿Los formularios pueden crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="36ae7-326">No, los formularios no pueden crear un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="36ae7-327">**¿Existen formularios sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="36ae7-328">Sí, se pueden crear encuestas y cuestionarios directamente en una cuenta de usuario final.</span><span class="sxs-lookup"><span data-stu-id="36ae7-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="36ae7-329">**¿Puede haber varios formularios por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="36ae7-330">Sí, puede haber varios formularios asociados a un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="36ae7-331">**¿Se pueden asociar formularios a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-332">No, un formulario solo se puede asociar con un único grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="36ae7-333">**¿Puede la Asociación de un formulario con un grupo cambiar?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="36ae7-334">No, una vez que un formulario está asociado a un grupo (ya sea creado directamente dentro del o se ha transferido de una persona) no se puede mover a otro grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="36ae7-335">**¿Se elimina el formulario ¿eliminar el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="36ae7-336">No, no es posible eliminar un grupo de la interfaz de formularios, sino sólo formularios individuales.</span><span class="sxs-lookup"><span data-stu-id="36ae7-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="36ae7-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="36ae7-337">OneNote</span></span>

<span data-ttu-id="36ae7-338">OneNote es una aplicación digital para blocs de notas.</span><span class="sxs-lookup"><span data-stu-id="36ae7-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="36ae7-339">El Bloc de notas de OneNote creado con un grupo es un archivo en el sitio de SharePoint asociado, en lugar de un servicio conectado a un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="36ae7-340">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="36ae7-341">Bloc de notas compartido (almacenado en la biblioteca de SharePoint asociada al grupo)</span><span class="sxs-lookup"><span data-stu-id="36ae7-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="36ae7-342">**¿Puede OneNote crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="36ae7-343">No, la aplicación de OneNote no puede crear un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="36ae7-344">**¿Los blocs de notas de OneNote existen sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="36ae7-345">Sí, los blocs de notas se pueden crear directamente en OneDrive o en otras ubicaciones compartidas.</span><span class="sxs-lookup"><span data-stu-id="36ae7-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="36ae7-346">**¿Puede haber varios blocs de notas de OneNote por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="36ae7-347">Sí, se crea un bloc de notas de forma predeterminada y se pueden agregar otros, pero cualquier vínculo a OneNote desde servicios asociados del grupo siempre va al bloc de notas predeterminado.</span><span class="sxs-lookup"><span data-stu-id="36ae7-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="36ae7-348">**¿Puede asociarse un bloc de notas de OneNote con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-349">No, el Bloc de notas se almacena en la biblioteca de sitio de SharePoint asociada al grupo y se vincula desde varias interfaces.</span><span class="sxs-lookup"><span data-stu-id="36ae7-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="36ae7-350">Sin embargo, puede compartirse con otros grupos de la misma manera que se puede compartir con los usuarios.</span><span class="sxs-lookup"><span data-stu-id="36ae7-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="36ae7-351">**¿Puede cambiar la Asociación del Bloc de notas a un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="36ae7-352">No, el Bloc de notas está asociado con el grupo y se puede tener acceso directamente a él desde otros servicios conectados a un grupo, pero el contenido se puede mover de un bloc de notas a otro dentro de la aplicación de OneNote.</span><span class="sxs-lookup"><span data-stu-id="36ae7-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="36ae7-353">**¿Se elimina el Bloc de notas, ¿eliminar el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="36ae7-354">No obstante, si se elimina el Bloc de notas de OneNote, es posible que haya vínculos rotos en algunos de los servicios relacionados con el grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="36ae7-355">Planner</span><span class="sxs-lookup"><span data-stu-id="36ae7-355">Planner</span></span>

<span data-ttu-id="36ae7-356">Planner es un servicio de administración de tareas de grupo ligero.</span><span class="sxs-lookup"><span data-stu-id="36ae7-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="36ae7-357">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="36ae7-358">Panel para administrar tareas de grupo</span><span class="sxs-lookup"><span data-stu-id="36ae7-358">Board for managing group tasks</span></span>

<span data-ttu-id="36ae7-359">**¿Puede el organizador crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="36ae7-360">Sí, la creación de un plan creará un grupo nuevo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="36ae7-361">**¿Hay un panel de Planner sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="36ae7-362">No, un plan debe estar asociado a un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="36ae7-363">**¿Puede haber varios planes por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="36ae7-364">Sí, puede haber varios planes por grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="36ae7-365">**¿Se puede asociar un plan a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-366">No, un plan depende exclusivamente de la pertenencia al grupo para determinar el acceso.</span><span class="sxs-lookup"><span data-stu-id="36ae7-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="36ae7-367">**¿Puede una asociación de plan con un cambio de grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="36ae7-368">No, sin embargo, al copiar un plan se crea un grupo nuevo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="36ae7-369">Un grupo creado por cualquier otra aplicación no se mostrará en Planner automáticamente para un usuario.</span><span class="sxs-lookup"><span data-stu-id="36ae7-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="36ae7-370">Para tener acceso a la placa inicialmente, deberá abrirla desde otra interfaz basada en grupos, como Outlook.</span><span class="sxs-lookup"><span data-stu-id="36ae7-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="36ae7-371">**¿La eliminación del plan elimina el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="36ae7-372">Sí, al eliminar el plan se eliminarán el contenido y los servicios asociados con el grupo y el grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="36ae7-373">PowerApps</span><span class="sxs-lookup"><span data-stu-id="36ae7-373">Power Apps</span></span>

<span data-ttu-id="36ae7-374">Power apps proporciona un lienzo para el desarrollo de aplicaciones sin código.</span><span class="sxs-lookup"><span data-stu-id="36ae7-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="36ae7-375">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="36ae7-376">Las aplicaciones se pueden compartir con un grupo para ejecutarse y modificarse</span><span class="sxs-lookup"><span data-stu-id="36ae7-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="36ae7-377">**¿Pueden las aplicaciones Power crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="36ae7-378">No, Power apps no puede crear un grupo de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36ae7-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="36ae7-379">**¿Hay aplicaciones de energía sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="36ae7-380">Sí, las aplicaciones se pueden crear en Power apps y residir dentro de la cuenta de los creadores hasta compartirla o publicarla.</span><span class="sxs-lookup"><span data-stu-id="36ae7-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="36ae7-381">**¿Puede haber varias aplicaciones por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="36ae7-382">Sí, puede haber varias aplicaciones compartidas con un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="36ae7-383">**¿Las aplicaciones se pueden asociar a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-384">Sí, se puede compartir una aplicación con varios grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="36ae7-385">**¿Puede la Asociación de una aplicación con un grupo cambiar?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="36ae7-386">Sí, puesto que la asociación entre Power apps y un grupo de 365 de Microsoft está compartiendo solo: la aplicación sigue residiendo con el creador.</span><span class="sxs-lookup"><span data-stu-id="36ae7-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36ae7-387">Los [grupos deben estar habilitados para la seguridad antes de que las aplicaciones se puedan compartir con ellos](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="36ae7-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="36ae7-388">**¿La eliminación de la aplicación elimina el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="36ae7-389">No, las aplicaciones no están conectadas al grupo que no sea compartido con ellas.</span><span class="sxs-lookup"><span data-stu-id="36ae7-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="36ae7-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="36ae7-390">Power Automate</span></span>

<span data-ttu-id="36ae7-391">Power Automated (anteriormente conocido como Microsoft Flow) proporciona flujos de trabajo y servicios de automatización.</span><span class="sxs-lookup"><span data-stu-id="36ae7-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="36ae7-392">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="36ae7-393">Los flujos de trabajo pueden compartirse con un grupo para ejecutarse y modificarse.</span><span class="sxs-lookup"><span data-stu-id="36ae7-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="36ae7-394">**¿Es posible automatizar la creación de un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="36ae7-395">No, la automatización de la energía no puede crear un grupo de 365 de Microsoft en el contexto de estar asociado a uno.</span><span class="sxs-lookup"><span data-stu-id="36ae7-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="36ae7-396">Sin embargo, es posible crear un flujo que realice varias operaciones, como crear un grupo de seguridad de Azure AD o actualizar la pertenencia de un grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36ae7-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="36ae7-397">**¿Existen flujos sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="36ae7-398">Sí, se pueden crear flujos dentro de la automatización de la alimentación y residir dentro de la cuenta de los creadores hasta compartirla o publicarla.</span><span class="sxs-lookup"><span data-stu-id="36ae7-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="36ae7-399">**¿Puede haber varios flujos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="36ae7-400">Sí, puede haber varios flujos compartidos con un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="36ae7-401">**¿Se puede asociar un flujo con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-402">Sí, se puede compartir un flujo con varios grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="36ae7-403">**¿Puede una asociación de flujo con un cambio de grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="36ae7-404">Sí, puesto que la asociación entre la automatización de energía y un grupo de 365 de Microsoft está compartiendo solo: el flujo sigue teniendo el creador.</span><span class="sxs-lookup"><span data-stu-id="36ae7-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="36ae7-405">**¿Se elimina un flujo, ¿eliminar el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="36ae7-406">No, al igual que las aplicaciones de energía, los flujos no están conectados al grupo que no sea compartido con ellos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="36ae7-407">Power BI (clásico)</span><span class="sxs-lookup"><span data-stu-id="36ae7-407">Power BI (classic)</span></span>

<span data-ttu-id="36ae7-408">Power BI ofrece paneles e informes interactivos controlados por datos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="36ae7-409">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="36ae7-410">Informes de datos</span><span class="sxs-lookup"><span data-stu-id="36ae7-410">Data reporting</span></span>

<span data-ttu-id="36ae7-411">**¿Puede Power BI crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="36ae7-412">Sí, al crear un área de trabajo clásica se creará un grupo de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36ae7-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="36ae7-413">**¿Hay un área de trabajo clásica de Power BI sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="36ae7-414">No, [un área de trabajo clásica de Power BI debe estar asociada a un grupo](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="36ae7-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="36ae7-415">**¿Puede haber varias áreas de trabajo de Power BI por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="36ae7-416">No, la relación entre un área de trabajo clásica y un grupo es de 1:1.</span><span class="sxs-lookup"><span data-stu-id="36ae7-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="36ae7-417">**¿Se puede asociar un área de trabajo con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-418">Técnicamente no, mientras se crea el área de trabajo clásica con el grupo, el contenido se puede compartir fuera del grupo con usuarios y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="36ae7-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="36ae7-419">**¿Puede la Asociación del área de trabajo con un cambio de grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="36ae7-420">No, el espacio de trabajo clásico está asociado al grupo, pero el contenido se puede mover de un área de trabajo a otra dentro de la interfaz de Power BI o exportando el contenido de forma local.</span><span class="sxs-lookup"><span data-stu-id="36ae7-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="36ae7-421">**¿Se elimina el área de trabajo y se elimina el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="36ae7-422">Sí, al eliminar el área de trabajo en Power BI, se eliminará el contenido y los servicios asociados a grupos y grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="36ae7-423">Power BI (nueva)</span><span class="sxs-lookup"><span data-stu-id="36ae7-423">Power BI (new)</span></span>

<span data-ttu-id="36ae7-424">Power BI ofrece paneles e informes interactivos controlados por datos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="36ae7-425">Al crear un área de trabajo nueva en Power BI no se crea un grupo de 365 de Microsoft, la creación de un grupo por cualquier otro método crea un nuevo espacio de trabajo (no clásico) en Power BI.</span><span class="sxs-lookup"><span data-stu-id="36ae7-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="36ae7-426">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="36ae7-427">Informes de datos</span><span class="sxs-lookup"><span data-stu-id="36ae7-427">Data reporting</span></span>

<span data-ttu-id="36ae7-428">**¿Puede Power BI crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="36ae7-429">No, no se puede crear un grupo de Microsoft 365 desde la nueva interfaz de Power BI.</span><span class="sxs-lookup"><span data-stu-id="36ae7-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="36ae7-430">**¿El nuevo área de trabajo de Power BI existe sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="36ae7-431">Sí, es posible que los informes y áreas de trabajo creados en Power BI no estén asociados a grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36ae7-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="36ae7-432">**¿Puede haber varias áreas de trabajo por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="36ae7-433">Sí, [se pueden compartir varias áreas de trabajo creadas por Power BI con un único grupo](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span><span class="sxs-lookup"><span data-stu-id="36ae7-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="36ae7-434">**¿Se puede asociar un área de trabajo con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-435">No, un área de trabajo creada por Power BI solo se puede asociar a un único grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="36ae7-436">**¿Puede una asociación de un área de trabajo con un cambio de grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="36ae7-437">Sí y no.</span><span class="sxs-lookup"><span data-stu-id="36ae7-437">Yes and no.</span></span> <span data-ttu-id="36ae7-438">Un área de trabajo creada por Power BI solo se puede asociar a un grupo individual a la vez, pero puede cambiar la asociación en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="36ae7-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="36ae7-439">Un área de trabajo creada en Power BI por un grupo está permanentemente asociada a ese grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="36ae7-440">**¿Se elimina el área de trabajo y se elimina el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="36ae7-441">Sí, al eliminar el área de trabajo en Power BI, se eliminará el contenido y los servicios asociados con el grupo y el grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="36ae7-442">Project para la Web</span><span class="sxs-lookup"><span data-stu-id="36ae7-442">Project for the web</span></span>

<span data-ttu-id="36ae7-443">Project for the Web ofrece la capacidad de crear planes de proyectos, diagramas de Gantt y guías básicas.</span><span class="sxs-lookup"><span data-stu-id="36ae7-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="36ae7-444">Características clave que se proporcionan a los grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-444">Key features provided to groups.</span></span>

- <span data-ttu-id="36ae7-445">Planes de proyecto</span><span class="sxs-lookup"><span data-stu-id="36ae7-445">Project plans</span></span>

<span data-ttu-id="36ae7-446">**¿Es posible que el proyecto para el Web cree un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="36ae7-447">Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde Project para la Web.</span><span class="sxs-lookup"><span data-stu-id="36ae7-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="36ae7-448">**¿Existen proyectos sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="36ae7-449">Sí, los proyectos pueden existir sin estar asociados con un grupo de 365 de Microsoft, aunque la asignación de tareas requiere la Asociación de grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="36ae7-450">**¿Puede haber varios proyectos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="36ae7-451">Sí, es posible conectar varios proyectos en un único grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="36ae7-452">**¿Es posible asociar un proyecto con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-453">No, un proyecto solo se puede asociar con un único grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="36ae7-454">**¿Puede una asociación de un proyecto con un grupo cambia?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="36ae7-455">No, una vez que se establece la asociación con un grupo, no puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="36ae7-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="36ae7-456">**¿Se elimina el proyecto, ¿se elimina el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="36ae7-457">No, al eliminar el proyecto en el proyecto para el Web no se eliminará el grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="36ae7-458">Guía básica</span><span class="sxs-lookup"><span data-stu-id="36ae7-458">Roadmap</span></span>

<span data-ttu-id="36ae7-459">Roadmap proporciona la capacidad de crear guías básicas del proyecto con Project para web y Project online.</span><span class="sxs-lookup"><span data-stu-id="36ae7-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="36ae7-460">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="36ae7-461">Guías básicas del proyecto</span><span class="sxs-lookup"><span data-stu-id="36ae7-461">Project roadmaps</span></span>

<span data-ttu-id="36ae7-462">**¿Se puede crear un grupo de planeación?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="36ae7-463">Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde el mapa de ruta.</span><span class="sxs-lookup"><span data-stu-id="36ae7-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="36ae7-464">**¿Existe un plan de desarrollo sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="36ae7-465">Sí, los planes de desarrollo pueden existir sin estar asociados con un grupo de 365 de Microsoft, pero compartir el plan requiere la Asociación de grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="36ae7-466">**¿Puede haber varias guías básicas por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="36ae7-467">Sí, es posible conectar varias guías planas a un único grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="36ae7-468">**¿Se puede asociar un plan a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-469">No, un plan de desarrollo solo se puede asociar a un único grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="36ae7-470">**¿Puede una asociación de plan con un cambio de grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="36ae7-471">No, una vez que se establece la asociación con un grupo, no puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="36ae7-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="36ae7-472">**¿Se elimina el plan de desarrollo ¿eliminar el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="36ae7-473">No, al eliminar el plan no se eliminará el grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="36ae7-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="36ae7-474">SharePoint</span></span>

<span data-ttu-id="36ae7-475">SharePoint es una plataforma de administración de contenido basada en Web que ofrece, entre otras cosas, servicios de almacenamiento para una cantidad de servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36ae7-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="36ae7-476">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="36ae7-477">Biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="36ae7-477">Document library</span></span>
- <span data-ttu-id="36ae7-478">Biblioteca para el almacenamiento de blocs de notas de OneNote</span><span class="sxs-lookup"><span data-stu-id="36ae7-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="36ae7-479">Almacenamiento de los archivos wiki de Teams</span><span class="sxs-lookup"><span data-stu-id="36ae7-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="36ae7-480">**¿Puede SharePoint crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="36ae7-481">Sí, al crear un sitio de grupo en SharePoint se creará un grupo de Microsoft 365 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="36ae7-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="36ae7-482">También es posible crear un grupo y, opcionalmente, un equipo para un sitio existente.</span><span class="sxs-lookup"><span data-stu-id="36ae7-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="36ae7-483">**¿Existen sitios de SharePoint sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="36ae7-484">Sí, SharePoint ofrece una serie de servicios y sitios no asociados a grupos, como sitios de comunicación y de concentradores.</span><span class="sxs-lookup"><span data-stu-id="36ae7-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="36ae7-485">**¿Puede haber varios sitios por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="36ae7-486">No, solo puede haber un único sitio por grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="36ae7-487">Los canales privados en Microsoft Teams usan sitios adicionales que no están conectados al grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="36ae7-488">**¿Se pueden asociar sitios a varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-489">Técnicamente no, pero mientras se crea un sitio con un grupo, el contenido se puede compartir con otros grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="36ae7-490">**¿Puede cambiar la Asociación de un sitio con un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="36ae7-491">No, el sitio en sí está asociado con el grupo, pero el contenido se puede mover de un sitio a otro dentro de la interfaz de SharePoint, exportando el contenido localmente o con una herramienta de terceros.</span><span class="sxs-lookup"><span data-stu-id="36ae7-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="36ae7-492">**¿La eliminación del sitio elimina el grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="36ae7-493">Sí, al eliminar el sitio en SharePoint se eliminarán el contenido y los servicios asociados a grupos y grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="36ae7-494">Stream</span><span class="sxs-lookup"><span data-stu-id="36ae7-494">Stream</span></span>

<span data-ttu-id="36ae7-495">Microsoft Stream es una plataforma de hospedaje y uso compartido de vídeo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="36ae7-496">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="36ae7-497">Almacenamiento de vídeo</span><span class="sxs-lookup"><span data-stu-id="36ae7-497">Video storage</span></span>
- <span data-ttu-id="36ae7-498">Grabación de reuniones de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="36ae7-498">Teams meeting recording</span></span>
- <span data-ttu-id="36ae7-499">Canales de vídeo</span><span class="sxs-lookup"><span data-stu-id="36ae7-499">Video channels</span></span>

<span data-ttu-id="36ae7-500">**¿Puede la secuencia crear un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="36ae7-501">Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde la secuencia.</span><span class="sxs-lookup"><span data-stu-id="36ae7-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="36ae7-502">**¿Existe la secuencia sin un grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="36ae7-503">Sí, los canales de vídeo y los vídeos pueden existir en la secuencia sin estar asociados a un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="36ae7-504">**¿Puede haber varios vídeos y canales por grupo?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="36ae7-505">Sí, puede haber varios vídeos y canales en cada grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="36ae7-506">**¿Se puede asociar un vídeo o un canal con varios grupos?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="36ae7-507">Sí, mientras se crea un vídeo o un canal con un grupo, se puede compartir con otros grupos.</span><span class="sxs-lookup"><span data-stu-id="36ae7-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="36ae7-508">**¿Puede su asociación con un grupo cambiar?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="36ae7-509">Sí y no; los vídeos de la secuencia son propiedad de la carga original del cargador o la grabadora de reuniones, por lo que se pueden asociar a cualquier grupo, pero los canales de vídeo solo pueden asociarse con el grupo en el que se crearon originalmente.</span><span class="sxs-lookup"><span data-stu-id="36ae7-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="36ae7-510">**¿Se elimina el grupo de vídeos o canales?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="36ae7-511">No, la eliminación de vídeos o canales no elimina el grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="36ae7-512">Sin embargo, la eliminación del grupo en secuencia eliminará el contenido y los servicios asociados a los grupos, excepto los vídeos reales.</span><span class="sxs-lookup"><span data-stu-id="36ae7-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="36ae7-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="36ae7-513">Yammer</span></span>

<span data-ttu-id="36ae7-514">Yammer es una plataforma social empresarial diseñada para fomentar la participación de la comunidad dentro de las organizaciones y entre ellas.</span><span class="sxs-lookup"><span data-stu-id="36ae7-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="36ae7-515">La creación de una comunidad (antes denominada "grupo") en Yammer crea un buzón de correo, pero, en este momento, no se usa.</span><span class="sxs-lookup"><span data-stu-id="36ae7-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="36ae7-516">Un grupo de Microsoft 365 asociado con Yammer no se puede usar con un equipo en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="36ae7-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="36ae7-517">**Características clave que se proporcionan a los grupos**</span><span class="sxs-lookup"><span data-stu-id="36ae7-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="36ae7-518">Área de conversación</span><span class="sxs-lookup"><span data-stu-id="36ae7-518">Conversation area</span></span>

<span data-ttu-id="36ae7-519">**¿Puede Yammer crear un grupo de Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="36ae7-520">Sí, al crear un grupo nuevo en Yammer, se creará un nuevo grupo de Microsoft 365, si las plataformas están conectadas y si el usuario tiene la capacidad de crear un grupo.</span><span class="sxs-lookup"><span data-stu-id="36ae7-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="36ae7-521">No se puede crear un grupo de Yammer con el grupo de Microsoft 365 asociado en ninguna interfaz o servicio que no sea Yammer en sí.</span><span class="sxs-lookup"><span data-stu-id="36ae7-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="36ae7-522">**¿Existe un grupo de Yammer sin un grupo de Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="36ae7-523">Sí, es posible crear un grupo de Yammer sin un grupo de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36ae7-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="36ae7-524">Si la plataforma Yammer no está conectada a grupos de Microsoft 365, o los usuarios no tienen la capacidad de crear un grupo 365 de Microsoft, los grupos de Yammer se crean sin una asociación de grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36ae7-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="36ae7-525">**¿Puede haber varios grupos de Yammer por grupo de Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="36ae7-526">No, la relación entre un grupo de Yammer y un grupo de 365 de Microsoft es 1:1.</span><span class="sxs-lookup"><span data-stu-id="36ae7-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="36ae7-527">**¿Se puede asociar un grupo de Yammer con varios grupos de Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="36ae7-528">No, el grupo de Yammer solo se puede asociar con un solo grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36ae7-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="36ae7-529">Es posible que las publicaciones se compartan o se muevan a otros grupos de Yammer.</span><span class="sxs-lookup"><span data-stu-id="36ae7-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="36ae7-530">**¿Puede una asociación de un grupo de Yammer con un cambio de grupo de Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="36ae7-531">No, el grupo de Yammer solo se puede asociar al grupo de 365 de Microsoft al que estaba asociado originalmente.</span><span class="sxs-lookup"><span data-stu-id="36ae7-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="36ae7-532">**¿Se elimina el grupo de Yammer? eliminar el grupo 365 de Microsoft?**</span><span class="sxs-lookup"><span data-stu-id="36ae7-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="36ae7-533">Sí, al eliminar el grupo en Yammer, se eliminará el contenido y los servicios asociados de grupo de Microsoft y el grupo relacionados.</span><span class="sxs-lookup"><span data-stu-id="36ae7-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="36ae7-534">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="36ae7-534">Related topics</span></span>

[<span data-ttu-id="36ae7-535">Paso a paso de la planeación del gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="36ae7-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="36ae7-536">Crear el plan de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="36ae7-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

