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
description: 'Resumen: use PowerShell para Microsoft 365 para crear informes que no puede crear en el Centro de administración de Microsoft 365.'
ms.openlocfilehash: 10000f62b1d6a747cf0373623c6038b080666e1a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753983"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="3ef5e-103">Usar PowerShell para crear informes de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3ef5e-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="3ef5e-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3ef5e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3ef5e-105">Hay muchos informes diferentes disponibles en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ef5e-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3ef5e-106">Pero estos informes solo proporcionan mucha información y, a veces, se necesita más.</span><span class="sxs-lookup"><span data-stu-id="3ef5e-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="3ef5e-107">Es cuando necesita PowerShell para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ef5e-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="3ef5e-108">En estos artículos se describe cómo usar PowerShell para Microsoft 365 para obtener información de su inquilino de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="3ef5e-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="3ef5e-109">Introducción a los informes con PowerShell para Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="3ef5e-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="3ef5e-110">¿Por qué necesita usar PowerShell para Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="3ef5e-110">Why you need to use PowerShell for Microsoft 365</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
    
- <span data-ttu-id="3ef5e-111">Informes para licencias y cuentas de usuario:</span><span class="sxs-lookup"><span data-stu-id="3ef5e-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="3ef5e-112">Ver licencias y servicios de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ef5e-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="3ef5e-113">Ver usuarios con licencia y sin licencia de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ef5e-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="3ef5e-114">Ver detalles de servicio y licencia de cuenta de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ef5e-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="3ef5e-115">Ver cuentas de usuario de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ef5e-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="3ef5e-116">Informes de SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="3ef5e-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="3ef5e-117">Introducción al Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3ef5e-117">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="3ef5e-118">Get-SPOSiteGroup: obtiene todos los grupos de una colección de sitios especificada</span><span class="sxs-lookup"><span data-stu-id="3ef5e-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="3ef5e-119">Informes de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="3ef5e-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="3ef5e-120">Usar Exchange Online PowerShell para mostrar el buzón</span><span class="sxs-lookup"><span data-stu-id="3ef5e-120">Use Exchange Online PowerShell to display mailbox</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="3ef5e-121">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="3ef5e-121">Related articlesl</span></span>

[<span data-ttu-id="3ef5e-122">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ef5e-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3ef5e-123">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3ef5e-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3ef5e-124">Administrar SharePoint con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ef5e-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3ef5e-125">Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ef5e-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  