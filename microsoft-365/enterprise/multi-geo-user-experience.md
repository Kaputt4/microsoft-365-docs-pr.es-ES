---
title: Experiencia del usuario en un entorno multigeográfico
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Información sobre la experiencia del usuario de SharePoint, OneDrive y Exchange en un entorno multigeográfico para Microsoft 365.
ms.openlocfilehash: 4e752581f4ca692f9fecc5019f8e34543ebf7067
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362383"
---
# <a name="user-experience-in-a-multi-geo-environment"></a><span data-ttu-id="3b671-103">Experiencia del usuario en un entorno multigeográfico</span><span class="sxs-lookup"><span data-stu-id="3b671-103">User experience in a multi-geo environment</span></span>

<span data-ttu-id="3b671-104">Esto es lo que verán los usuarios en una configuración de OneDrive multigeográfico:</span><span class="sxs-lookup"><span data-stu-id="3b671-104">Here's what your users will see in a OneDrive Multi-Geo configuration:</span></span>

## <a name="exchange-mailbox"></a><span data-ttu-id="3b671-105">Buzón de Exchange</span><span class="sxs-lookup"><span data-stu-id="3b671-105">Exchange mailbox</span></span>

<span data-ttu-id="3b671-106">El buzón de Exchange de un usuario se aprovisiona en su ubicación de datos preferida y si esta cambia el buzón se reubica automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3b671-106">A user's Exchange mailbox is provisioned to their preferred data location, and is automatically relocated if their PDL changes.</span></span> <span data-ttu-id="3b671-107">Los usuarios pueden usar Outlook y Outlook en la Web normalmente sin cambios en la experiencia del usuario en un entorno de multigeográfico.</span><span class="sxs-lookup"><span data-stu-id="3b671-107">Users can use Outlook and Outlook on the web normally with no change in user experience in a multi-geo environment.</span></span>

## <a name="hub-sites"></a><span data-ttu-id="3b671-108">Sitios centrales</span><span class="sxs-lookup"><span data-stu-id="3b671-108">Hub sites</span></span>

<span data-ttu-id="3b671-109">Los sitios centrales de SharePoint mejoran la detección y la participación con contenido para los empleados, al crear una representación completa y coherente de proyectos, departamentos o regiones.</span><span class="sxs-lookup"><span data-stu-id="3b671-109">SharePoint Hub sites enhances the discovery and engagement with content for employees, while creating a complete and consistent representation of projects, departments or regions.</span></span> <span data-ttu-id="3b671-110">En un entorno multigeográfico, los sitios de ubicaciones satélite pueden asociarse fácilmente con un sitio central independientemente de su ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="3b671-110">In a multi-geo environment, sites from satellite locations can easily be associated with a hub site regardless the hub site's geo location.</span></span> <span data-ttu-id="3b671-111">Los usuarios pueden buscar y obtener resultados en la central mediante una experiencia de búsqueda única, independientemente de la ubicación geográfica de los sitios.</span><span class="sxs-lookup"><span data-stu-id="3b671-111">Users can search and get results across the hub through a single search experience, regardless of the geo location of the sites.</span></span>

## <a name="microsoft-365-app-launcher"></a><span data-ttu-id="3b671-112">Iniciador de aplicaciones de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3b671-112">Microsoft 365 app launcher</span></span>

<span data-ttu-id="3b671-113">El iniciador de aplicaciones es compatible con múltiples ubicaciones geográficas y dirigirá cada icono a la ubicación geográfica correspondiente de la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3b671-113">The app launcher is multi-geo aware and will direct each tile to the appropriate geo location of the workload.</span></span> <span data-ttu-id="3b671-114">Los iconos de SharePoint y OneDrive apuntarán al usuario a la ubicación correspondiente a la ubicación geográfica aprovisionada del usuario.</span><span class="sxs-lookup"><span data-stu-id="3b671-114">The SharePoint and OneDrive tiles will point the user to the location corresponding to the user's provisioned geo location.</span></span> <span data-ttu-id="3b671-115">Esto significa que si el usuario tiene un OneDrive en la ubicación central, el icono de SharePoint apuntarán a la página principal de SharePoint en la ubicación central, pero se aprovisionará su sitio de grupo en la ubicación correspondiente a su ubicación de datos preferida.</span><span class="sxs-lookup"><span data-stu-id="3b671-115">This means that is the user has a OneDrive in the central location, their SharePoint tile will point them to SP Home in the central location but their group site will be provisioned in the location corresponding to their PDL.</span></span> 

## <a name="office-applications"></a><span data-ttu-id="3b671-116">Aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="3b671-116">Office applications</span></span>

<span data-ttu-id="3b671-117">Office aplicaciones como Word, Excel y PowerPoint detectarán automáticamente la ubicación geográfica correcta OneDrive cada usuario cuando inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="3b671-117">Office applications such as Word, Excel, and PowerPoint will automatically detect the correct OneDrive geo-location for each user when they log in.</span></span> <span data-ttu-id="3b671-118">Los usuarios no tienen que escribir la dirección URL específica de geoárea de su instancia de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3b671-118">Users do not need to enter the geo-specific URL for their OneDrive or SharePoint sites.</span></span>

## <a name="onedrive-sync-app"></a><span data-ttu-id="3b671-119">Sincronización de OneDrive app</span><span class="sxs-lookup"><span data-stu-id="3b671-119">OneDrive sync app</span></span>

<span data-ttu-id="3b671-120">La aplicación Sincronización de OneDrive (versión 17.3.6943.0625 y posteriores) detectará automáticamente la ubicación geográfica OneDrive correcta para el usuario.</span><span class="sxs-lookup"><span data-stu-id="3b671-120">The OneDrive sync app (version 17.3.6943.0625 and later) will automatically detect the correct OneDrive geo location for the user.</span></span> <span data-ttu-id="3b671-121">La compatibilidad con aplicaciones de sincronización incluye la capacidad de sincronizar sitios basados en grupos independientemente de su ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="3b671-121">Sync app support includes the ability to sync groups-based sites regardless of their geo location.</span></span> <span data-ttu-id="3b671-122">Tenga en cuenta que el cliente de sincronización de Groove no es compatible con las capacidades multigeográficas.</span><span class="sxs-lookup"><span data-stu-id="3b671-122">Note that the Groove sync client is not supported for multi-geo.</span></span> 

## <a name="onedrive-location"></a><span data-ttu-id="3b671-123">OneDrive ubicación</span><span class="sxs-lookup"><span data-stu-id="3b671-123">OneDrive location</span></span>

<span data-ttu-id="3b671-124">Los usuarios tendrán su OneDrive en su ubicación de datos preferida.</span><span class="sxs-lookup"><span data-stu-id="3b671-124">Users will have their OneDrive provisioned in their preferred data location.</span></span> <span data-ttu-id="3b671-125">Si un usuario navega a una dirección URL de OneDrive que contiene una ubicación geográfica incorrecta (como un marcador de una ubicación geográfica anterior), se redirige automáticamente al OneDrive en la ubicación geográfica adecuada.</span><span class="sxs-lookup"><span data-stu-id="3b671-125">If a user navigates to a OneDrive URL that contains an incorrect geo location (such as a bookmark from a previous geo location), they are automatically redirected to the OneDrive in the appropriate geo location.</span></span>

## <a name="onedrive-ios-and-android"></a><span data-ttu-id="3b671-126">OneDrive para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="3b671-126">OneDrive iOS and Android</span></span> 

<span data-ttu-id="3b671-p107">Las aplicaciones móviles de OneDrive para iOS y Android mostrarán los archivos de OneDrive y los archivos compartidos con usted, independientemente de su ubicación geográfica. La búsqueda en las aplicaciones móviles de OneDrive mostrará resultados relevantes de todas las ubicaciones geográficas. Descargue la última versión de estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3b671-p107">The OneDrive iOS and Android mobile apps will show you your OneDrive files and files shared with you regardless of their geo location. Search from the OneDrive mobile apps will show relevant results from all geo locations. Please download the latest version of these apps.</span></span>

<span data-ttu-id="3b671-130">Vea [Usar OneDrive en iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) y [usar OneDrive para Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3b671-130">See Use [OneDrive on iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) and [Use OneDrive for Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) for more information.</span></span>

## <a name="onedrive-mobile-client"></a><span data-ttu-id="3b671-131">Cliente móvil de OneDrive</span><span class="sxs-lookup"><span data-stu-id="3b671-131">OneDrive Mobile Client</span></span> 

<span data-ttu-id="3b671-132">El cliente móvil de OneDrive es compatible con las capacidades multigeográficas y mostrará el contenido y los resultados relevantes de todas las ubicaciones geográfica.</span><span class="sxs-lookup"><span data-stu-id="3b671-132">The OneDrive Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="search"></a><span data-ttu-id="3b671-133">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="3b671-133">Search</span></span>

<span data-ttu-id="3b671-134">Cada ubicación geográfica tiene su propio índice de búsqueda y el Centro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3b671-134">Each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="3b671-135">Cuando un usuario busca, la consulta se envía a todas las ubicaciones geográficas y los resultados devueltos se combinan y, a continuación, se clasifican para que el usuario obtiene resultados unificados.</span><span class="sxs-lookup"><span data-stu-id="3b671-135">When a user searches, the query is sent to all the geo locations, and the returned results are merged and then ranked so the user gets unified results.</span></span> <span data-ttu-id="3b671-136">Los usuarios obtienen resultados de todas las ubicaciones geográficas independientemente de su propia ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="3b671-136">Users get results from all geo locations regardless of their own geo location.</span></span> <span data-ttu-id="3b671-137">Consulte [Configure Search for OneDrive Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span><span class="sxs-lookup"><span data-stu-id="3b671-137">See [Configure Search for OneDrive Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span></span>

<span data-ttu-id="3b671-138">Se admiten los siguientes clientes de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="3b671-138">The following search clients are supported:</span></span>

-   <span data-ttu-id="3b671-139">OneDrive</span><span class="sxs-lookup"><span data-stu-id="3b671-139">OneDrive</span></span>

-   <span data-ttu-id="3b671-140">Delve</span><span class="sxs-lookup"><span data-stu-id="3b671-140">Delve</span></span>

-   <span data-ttu-id="3b671-141">Página principal de SharePoint</span><span class="sxs-lookup"><span data-stu-id="3b671-141">SharePoint Home</span></span>

-   <span data-ttu-id="3b671-142">Centro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="3b671-142">The Search Center</span></span>

-   <span data-ttu-id="3b671-143">Aplicaciones de búsqueda personalizada que usan la API de SharePoint Search</span><span class="sxs-lookup"><span data-stu-id="3b671-143">Custom search applications that use the SharePoint Search API</span></span>

## <a name="sharepoint-home"></a><span data-ttu-id="3b671-144">Página principal de SharePoint</span><span class="sxs-lookup"><span data-stu-id="3b671-144">SharePoint Home</span></span> 

<span data-ttu-id="3b671-145">En SharePoint Multi-Geo su SharePoint se hospeda en la ubicación donde reside el usuario según lo determinado por su OneDrive ubicación.</span><span class="sxs-lookup"><span data-stu-id="3b671-145">In SharePoint Multi-Geo your SharePoint home is hosted in the location where the user resides as determined by their OneDrive location.</span></span> <span data-ttu-id="3b671-146">Por ejemplo: si el usuario tiene hospedado OneDrive en una ubicación satélite de Europa, la página principal de SharePoint se representará desde Europa.</span><span class="sxs-lookup"><span data-stu-id="3b671-146">For example: if the user has their OneDrive hosted in an European satellite location, their SharePoint Home will be rendered from Europe.</span></span> <span data-ttu-id="3b671-147">La página principal de SharePoint incluye todo el contenido relevante para el usuario independientemente de su ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="3b671-147">SharePoint home includes all content relevant to the user regardless of its geo location.</span></span> 

<span data-ttu-id="3b671-148">**Sitios seguidos, noticias de sitios, sitios recientes, sitios frecuentes y sitios sugeridos**</span><span class="sxs-lookup"><span data-stu-id="3b671-148">**Followed Sites, News from Sites, Recent Sites, Frequent Sites, and Suggested sites**</span></span>

<span data-ttu-id="3b671-149">Todos estos componentes se mostrarán con independencia de la ubicación geográfica donde se hospeda el contenido, siempre y cuando el usuario tenga permisos para dicho contenido.</span><span class="sxs-lookup"><span data-stu-id="3b671-149">All of these components will show up for the user regardless of the geo location where the content is hosted, so long as the user has permissions to said content.</span></span> 

<span data-ttu-id="3b671-150">**Vínculos destacados**</span><span class="sxs-lookup"><span data-stu-id="3b671-150">**Features Links**</span></span>

<span data-ttu-id="3b671-151">Los administradores pueden configurar vínculos destacados en la página principal de SharePoint según sea adecuado para cada ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="3b671-151">Admins may configure Featured links in SharePoint home as appropriate to each geo location.</span></span> <span data-ttu-id="3b671-152">Esto permite que el administrador destaque en la página principal de SharePoint de cada región los vínculos que sean apropiados para los usuarios de la región.</span><span class="sxs-lookup"><span data-stu-id="3b671-152">This allows the admin to feature in the SP Home for each region the links that are appropriate for users in the region.</span></span> 

## <a name="sharepoint-mobile-client"></a><span data-ttu-id="3b671-153">Cliente móvil de SharePoint</span><span class="sxs-lookup"><span data-stu-id="3b671-153">SharePoint Mobile Client</span></span> 

<span data-ttu-id="3b671-154">El cliente móvil de SharePoint es compatible con las capacidades multigeográficas y mostrará el contenido y los resultados relevantes de todas las ubicaciones geográfica.</span><span class="sxs-lookup"><span data-stu-id="3b671-154">The SharePoint Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="sharing"></a><span data-ttu-id="3b671-155">Uso compartido</span><span class="sxs-lookup"><span data-stu-id="3b671-155">Sharing</span></span>

<span data-ttu-id="3b671-156">La experiencia de selector de personas muestra todos los usuarios, independientemente de su ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="3b671-156">The People Picker experience shows all users regardless of their geo location.</span></span> <span data-ttu-id="3b671-157">Esto permite que un usuario pueda compartir con otro de su misma ubicación geográfica o en cualquier otra ubicación geográfica de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="3b671-157">This allows a user to share with another user in their same geo or in any other of your tenant's geo locations.</span></span> <span data-ttu-id="3b671-158">El contenido de diferentes ubicaciones  geográficas se mostrará en la vista Compartido conmigo en el OneDrive del usuario y se puede acceder a él con una experiencia de Sign-On única independientemente de la ubicación geográfica en la que se hospeda.</span><span class="sxs-lookup"><span data-stu-id="3b671-158">Content from different geo locations will show up in the **Shared with Me** view in the user's OneDrive and can be accessed with Single Sign-On experience regardless of which geo location it is hosted in.</span></span>

## <a name="teams-experience"></a><span data-ttu-id="3b671-159">Experiencia de Teams</span><span class="sxs-lookup"><span data-stu-id="3b671-159">Teams Experience</span></span>

<span data-ttu-id="3b671-160">Teams es un servicio multige geográfico.</span><span class="sxs-lookup"><span data-stu-id="3b671-160">Teams is a multi-geo service.</span></span> <span data-ttu-id="3b671-161">Los archivos de OneDrive y los archivos vistos recientemente se muestran independientemente de la ubicación geográfica del usuario.</span><span class="sxs-lookup"><span data-stu-id="3b671-161">OneDrive files and recently viewed files are shown regardless of the user's geo location.</span></span> <span data-ttu-id="3b671-162">Las @menciones funcionan con los usuarios de todas las ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="3b671-162">@ mentions work with users from all geo-locations.</span></span>

## <a name="user-profiles"></a><span data-ttu-id="3b671-163">Perfiles de usuario</span><span class="sxs-lookup"><span data-stu-id="3b671-163">User profiles</span></span>

<span data-ttu-id="3b671-p113">La información de perfiles de usuario se controla en la ubicación geográfica del usuario. Al seleccionar un usuario, se le dirigirá a la ubicación geográfica correcta del usuario, donde verá los detalles completos de su perfil.</span><span class="sxs-lookup"><span data-stu-id="3b671-p113">User profile information is mastered in the user's geo location. When selecting a user, you will be directed to the appropriate geo location for the user, where you will see their full profile details.</span></span>

<span data-ttu-id="3b671-166">Si Delve está desactivada, verá la experiencia de perfil clásica de SharePoint, que no es de reconocimiento multigeográfico.</span><span class="sxs-lookup"><span data-stu-id="3b671-166">If Delve is turned off, you will see the classic profile experience in SharePoint, which is not multi-geo aware.</span></span>


