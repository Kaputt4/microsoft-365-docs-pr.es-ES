---
title: Buscar en el registro de auditoría la actividad de usuario y de administrador en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MOE150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: 'El registro de auditoría de Office 365 es un registro de auditoría unificado. ¿Por qué un registro de auditoría unificado? Como los eventos de la mayoría de los servicios de Office 365 a los que está suscrito la organización se registran en un único registro de auditoría que puede buscar. Esto significa que puede buscar actividades de usuario y de administrador en estos servicios:'
ms.openlocfilehash: 1d3f45d24a8d1a83c20f5d36b12ced761e00f936
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37092948"
---
# <a name="search-the-audit-log-for-user-and-admin-activity-in-office-365"></a><span data-ttu-id="841f7-106">Buscar en el registro de auditoría la actividad de usuario y de administrador en Office 365</span><span class="sxs-lookup"><span data-stu-id="841f7-106">Search the audit log for user and admin activity in Office 365</span></span>

<span data-ttu-id="841f7-107">El registro de auditoría de Office 365 es un registro de auditoría unificado.</span><span class="sxs-lookup"><span data-stu-id="841f7-107">The Office 365 audit log is a unified audit log.</span></span> <span data-ttu-id="841f7-108">¿Por qué un registro de auditoría unificado?</span><span class="sxs-lookup"><span data-stu-id="841f7-108">Why a unified audit log?</span></span> <span data-ttu-id="841f7-109">Como los eventos de la mayoría de los servicios de Office 365 a los que está suscrito la organización se registran en un único registro de auditoría que puede buscar.</span><span class="sxs-lookup"><span data-stu-id="841f7-109">Because events from most Office 365 services that you're organization subscribes to are recorded in a single audit log that you can search.</span></span> <span data-ttu-id="841f7-110">Esto significa que puede buscar actividades de usuario y de administrador en estos servicios:</span><span class="sxs-lookup"><span data-stu-id="841f7-110">That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="841f7-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="841f7-111">SharePoint</span></span>
- <span data-ttu-id="841f7-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="841f7-112">OneDrive</span></span>
- <span data-ttu-id="841f7-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="841f7-113">Exchange</span></span>
- <span data-ttu-id="841f7-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="841f7-114">Azure Active Directory</span></span>
- <span data-ttu-id="841f7-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="841f7-115">Microsoft Teams</span></span>
- <span data-ttu-id="841f7-116">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="841f7-116">eDiscovery</span></span>
- <span data-ttu-id="841f7-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="841f7-117">Power BI</span></span>
- <span data-ttu-id="841f7-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="841f7-118">Yammer</span></span>
- <span data-ttu-id="841f7-119">Sway</span><span class="sxs-lookup"><span data-stu-id="841f7-119">Sway</span></span>
- <span data-ttu-id="841f7-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="841f7-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="841f7-121">Configurar la auditoría</span><span class="sxs-lookup"><span data-stu-id="841f7-121">Set up auditing</span></span>
  
<span data-ttu-id="841f7-122">Hay algunas cosas que debe hacer antes de poder buscar en el registro de auditoría de Office 365.</span><span class="sxs-lookup"><span data-stu-id="841f7-122">There's few things you have to do before you can search the Office 365 audit log.</span></span>
  
- <span data-ttu-id="841f7-123">[Active la búsqueda de registros de auditoría](turn-audit-log-search-on-or-off.md) para iniciar la grabación de eventos que puede buscar</span><span class="sxs-lookup"><span data-stu-id="841f7-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="841f7-124">[Habilitar la auditoría de buzones de correo](enable-mailbox-auditing.md) para que pueda buscar eventos relacionados con buzones de correo; como cuando un usuario inicia sesión en su buzón o depura elementos de la carpeta elementos recuperables</span><span class="sxs-lookup"><span data-stu-id="841f7-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="841f7-125">Búsquedas en el registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="841f7-125">Search the audit log</span></span>
  
<span data-ttu-id="841f7-126">Después de activar la auditoría, puede buscar cientos de tipos individuales de eventos de varios servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="841f7-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Office 365 services.</span></span>
  
- <span data-ttu-id="841f7-127">Buscar actividades de usuario y de administrador en [el registro de auditoría](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="841f7-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="841f7-128">[Comprender las propiedades detalladas](detailed-properties-in-the-office-365-audit-log.md) de cada registro de auditoría incluido en los resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="841f7-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="841f7-129">[Buscar actividades relacionadas con la exhibición](search-for-ediscovery-activities-in-the-audit-log.md) de documentos electrónicos realizadas por administradores y administradores de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="841f7-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
