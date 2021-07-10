---
title: Capacidades multige geográficas en Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: Obtenga información sobre cómo Teams funciona con Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9fe9b289b0ffbef12327c4232b9deb6727b6d718
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362671"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a><span data-ttu-id="dcaa8-103">Capacidades multige geográficas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dcaa8-103">Multi-Geo capabilities in Microsoft Teams</span></span>

<span data-ttu-id="dcaa8-104">Las funcionalidades multige geográficas de Teams permiten que Teams datos de chat se almacenen en reposo en una ubicación geográfica especificada.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-104">Multi-Geo capabilities in Teams enables Teams chat data to be stored at rest in a specified geo location.</span></span> <span data-ttu-id="dcaa8-105">Los datos de chat constan de mensajes de chat, incluidos mensajes privados, mensajes de canal e imágenes usadas en chats.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-105">Chat data consists of chat messages, including private messages, channel messages, and images used in chats.</span></span>

<span data-ttu-id="dcaa8-106">Teams la ubicación de datos preferida (PDL) para que los usuarios y grupos determinen dónde almacenar los datos.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-106">Teams uses the Preferred Data Location (PDL) for users and groups to determine where to store data.</span></span> <span data-ttu-id="dcaa8-107">Si la PDL no está establecida o no es válida, los datos se almacenan en la ubicación central del inquilino.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-107">If the PDL is not set or is invalid, data is stored in the tenant's central location.</span></span>

## <a name="user-chat"></a><span data-ttu-id="dcaa8-108">Chat de usuario</span><span class="sxs-lookup"><span data-stu-id="dcaa8-108">User chat</span></span>

<span data-ttu-id="dcaa8-109">El chat de usuario incluye mensajes de reunión uno a uno, uno a varios y privados.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-109">User chat includes one-to-one, one-to-many, and private meeting messages.</span></span>

<span data-ttu-id="dcaa8-110">Cuando se crea un nuevo usuario, Teams lee la PDL del usuario y almacena todos sus datos de chat en esa ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-110">When a new user is created, Teams reads the user's PDL and stores all their chat data in that geo location.</span></span>

<span data-ttu-id="dcaa8-111">Para los usuarios existentes, si un administrador agrega o modifica la PDL de un usuario, los datos de chat de ese usuario se agregan a una cola de migración que se va a mover a la ubicación geográfica especificada.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-111">For existing users, if an administrator adds or modifies the PDL for a user, that user's chat data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="dcaa8-112">La ubicación de almacenamiento de un chat de uno a uno o uno a varios se basa en la PDL de la persona que creó el chat.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-112">The storage location for a one-to-one or one-to-many chat is based on the PDL of the person who created the chat.</span></span> <span data-ttu-id="dcaa8-113">Si se cambia la PDL de ese usuario, el chat se migrará a la nueva ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-113">If that user's PDL is changed, the chat will be migrated to the new geo location.</span></span> <span data-ttu-id="dcaa8-114">La ubicación de almacenamiento de un chat de reunión se basa en la PDL del organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-114">The storage location for a meeting chat is based on the PDL of the meeting organizer.</span></span>

<span data-ttu-id="dcaa8-115">Para buscar la ubicación actual de los datos de Teams usuario, conéctese a [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="dcaa8-115">To find the current location of a user's Teams data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a><span data-ttu-id="dcaa8-116">Mensajes de canal</span><span class="sxs-lookup"><span data-stu-id="dcaa8-116">Channel messages</span></span>

<span data-ttu-id="dcaa8-117">Cada Microsoft 365 tiene una ubicación de datos preferida (PDL) que indica la ubicación geográfica donde se almacenarán los datos relacionados.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-117">Each Microsoft 365 group has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="dcaa8-118">Teams usa la PDL para el grupo asociado a cada equipo para determinar dónde almacenar los datos de mensajería de canal para ese equipo.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-118">Teams uses the PDL for the group associated with each team to determine where to store channel messaging data for that team.</span></span> <span data-ttu-id="dcaa8-119">Esto incluye el chat que se produce dentro de una reunión de canal.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-119">This includes chat that occurs within a channel meeting.</span></span>

<span data-ttu-id="dcaa8-120">Cuando un usuario crea un nuevo equipo, la PDL de ese usuario determina qué PDL se asigna al grupo Microsoft 365 usuario.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-120">When a user creates a new team, that user's PDL determines what PDL is assigned to the Microsoft 365 group.</span></span> <span data-ttu-id="dcaa8-121">La PDL de grupo determina dónde se almacenan los datos de ese equipo.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-121">The group PDL determines where that team's data is stored.</span></span> <span data-ttu-id="dcaa8-122">Si la PDL de ese usuario cambia más adelante, no se cambia la PDL del grupo.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-122">If that user's PDL later changes, the group's PDL is not changed.</span></span>

<span data-ttu-id="dcaa8-123">En el caso de los equipos existentes, si un administrador agrega o modifica la PDL para el grupo de Microsoft 365 que hace una copia de seguridad de un equipo, los datos de mensajería de canal de ese equipo se agregan a una cola de migración que se va a mover a la ubicación geográfica especificada.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-123">For existing teams, if an administrator adds or modifies the PDL for the Microsoft 365 group that backs a team, that team's channel messaging data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="dcaa8-124">Al cambiar la PDL del grupo de Microsoft 365, se ponen en cola Teams datos para migrar a la ubicación elegida.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-124">Changing the PDL of the Microsoft 365 group queues the Teams data to migrate to the chosen location.</span></span> <span data-ttu-id="dcaa8-125">Sin embargo, esto no migra automáticamente el SharePoint o los archivos asociados con el grupo.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-125">However, this does not migrate the SharePoint site or files associated with the Group automatically.</span></span> <span data-ttu-id="dcaa8-126">Debe mover el sitio por separado siguiendo los procedimientos descritos en [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations).</span><span class="sxs-lookup"><span data-stu-id="dcaa8-126">You must move the site separately by following the procedures in [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations).</span></span> <span data-ttu-id="dcaa8-127">Asegúrese de realizar ambos pasos para evitar los Teams y los SharePoint para un grupo en ubicaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-127">Be sure to do both steps to avoid Teams data and SharePoint data for one group in different locations.</span></span>

<span data-ttu-id="dcaa8-128">Para buscar la ubicación actual de los datos de un equipo, conéctese a [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="dcaa8-128">To find the current location of a team's data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a><span data-ttu-id="dcaa8-129">Experiencia del usuario</span><span class="sxs-lookup"><span data-stu-id="dcaa8-129">User Experience</span></span>

<span data-ttu-id="dcaa8-130">Teams Multi-Geo es perfecto para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-130">Teams Multi-Geo is seamless to the end user.</span></span> <span data-ttu-id="dcaa8-131">Una vez que cambie la PDL de un usuario o un grupo, los datos respectivos se pondrán en cola para la migración y la migración se producirá automáticamente sin ningún impacto para el usuario o su cliente de Teams incluso si están activos mientras se produce la migración.</span><span class="sxs-lookup"><span data-stu-id="dcaa8-131">Once you change the PDL of a user or a group, the respective data will queue for migration and the migration will occur automatically with no impact to the user or their Teams client even if they are active while the migration occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="dcaa8-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcaa8-132">See also</span></span>

[<span data-ttu-id="dcaa8-133">Configuración de inquilino de Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="dcaa8-133">Microsoft 365 Multi-Geo tenant configuration</span></span>](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[<span data-ttu-id="dcaa8-134">Administración de un entorno multigeográfico</span><span class="sxs-lookup"><span data-stu-id="dcaa8-134">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="dcaa8-135">Administración de buzones de correo de Exchange Online en un entorno multigeográfico</span><span class="sxs-lookup"><span data-stu-id="dcaa8-135">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
