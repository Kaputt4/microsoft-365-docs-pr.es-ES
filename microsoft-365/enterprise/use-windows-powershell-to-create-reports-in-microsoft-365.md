---
title: Usar PowerShell para crear informes de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 1ea4d4ec-af89-496f-9678-701867f5a6fc
description: 'Resumen: use PowerShell para Microsoft 365 para crear informes que no puede generar en el centro de administración de Microsoft 365.'
ms.openlocfilehash: 9e3b90dcdd32f80125175ad2e15a852db51e17f8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572746"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="de95e-103">Usar PowerShell para crear informes de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="de95e-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="de95e-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="de95e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="de95e-105">Muchos informes diferentes están disponibles en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de95e-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="de95e-106">Pero estos informes sólo proporcionan tanta información, y a veces se necesita más.</span><span class="sxs-lookup"><span data-stu-id="de95e-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="de95e-107">Ahí es cuando se necesita PowerShell para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de95e-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="de95e-108">Estos artículos describen cómo usar PowerShell para Microsoft 365 obtener información del inquilino de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="de95e-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="de95e-109">Comience con los informes mediante PowerShell para Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="de95e-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="de95e-110">¿Por qué necesita usar PowerShell para Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="de95e-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="de95e-111">Informes para licencias y cuentas de usuario:</span><span class="sxs-lookup"><span data-stu-id="de95e-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="de95e-112">Ver licencias y servicios de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="de95e-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="de95e-113">Ver Microsoft 365 usuarios con licencia y sin licencia con PowerShell</span><span class="sxs-lookup"><span data-stu-id="de95e-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="de95e-114">Ver Microsoft 365 licencia de cuenta y detalles del servicio con PowerShell</span><span class="sxs-lookup"><span data-stu-id="de95e-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="de95e-115">Ver cuentas de usuario Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="de95e-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="de95e-116">Informes de SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="de95e-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="de95e-117">Introducción al Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="de95e-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="de95e-118">Get-SPOSiteGroup: obtiene todos los grupos de una colección de sitios especificada</span><span class="sxs-lookup"><span data-stu-id="de95e-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="de95e-119">Informes de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="de95e-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="de95e-120">Use Exchange Online PowerShell para mostrar el buzón</span><span class="sxs-lookup"><span data-stu-id="de95e-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articles"></a><span data-ttu-id="de95e-121">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="de95e-121">Related articles</span></span>

[<span data-ttu-id="de95e-122">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="de95e-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="de95e-123">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="de95e-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="de95e-124">Administrar SharePoint con PowerShell</span><span class="sxs-lookup"><span data-stu-id="de95e-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="de95e-125">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="de95e-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
