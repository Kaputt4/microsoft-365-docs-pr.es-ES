---
title: Configurar eDiscovery para Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Obtenga información sobre cómo usar el parámetro Region para configurar la exhibición de documentos electrónicos para su uso en ubicaciones satélite en Microsoft 365 Multi-Geo.
ms.openlocfilehash: d1d66a9e7953b540e318c8364bdcb8d72654b482
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636810"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="e0e06-103">Configuración de eDiscovery de Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="e0e06-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="e0e06-104">[Las capacidades avanzadas](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) de exhibición de documentos electrónicos permiten a un administrador de exhibición de documentos electrónicos multigefico buscar en todas las ubicaciones geográficas sin necesidad de usar un filtro de seguridad "Región".</span><span class="sxs-lookup"><span data-stu-id="e0e06-104">[Advanced eDiscovery capabilities](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) allow a multi-geo eDiscovery administrator to search all of the geos without needing to utilize a "Region" security filter.</span></span> <span data-ttu-id="e0e06-105">Los datos se exportan a la instancia de Azure de la ubicación central del inquilino multigemico.</span><span class="sxs-lookup"><span data-stu-id="e0e06-105">Data is exported to the Azure instance of the central location of the multi-geo tenant.</span></span> 

<span data-ttu-id="e0e06-106">Sin las capacidades avanzadas de exhibición de documentos electrónicos, un administrador de exhibición de documentos electrónicos o un administrador de un inquilino multigemico solo podrá llevar a cabo la exhibición de documentos electrónicos en la ubicación central de ese espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="e0e06-106">Without advanced eDiscovery capabilities, an eDiscovery manager or administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="e0e06-107">Para admitir la capacidad de llevar a cabo la exhibición de documentos electrónicos para ubicaciones satélite, hay disponible un nuevo parámetro de filtro de seguridad de cumplimiento denominado "Región" a través de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0e06-107">To support the ability to conduct eDiscovery for satellite locations, a new compliance security filter parameter named "Region" is available via PowerShell.</span></span> <span data-ttu-id="e0e06-108">Este parámetro lo pueden usar los inquilinos cuya ubicación central se encuentra en Norteamérica, Europa o Asia Pacífico.</span><span class="sxs-lookup"><span data-stu-id="e0e06-108">This parameter can be used by tenants whose central location is in North America, Europe, or Asia Pacific.</span></span> <span data-ttu-id="e0e06-109">Se recomienda eDiscovery avanzado para los inquilinos cuya ubicación central no está en Norteamérica, Europa o Asia Pacífico y que necesitan realizar eDiscovery en ubicaciones geográficas satélite.</span><span class="sxs-lookup"><span data-stu-id="e0e06-109">Advanced eDiscovery is recommended for tenants whose central location is not in North America, Europe, or Asia Pacific and who need to perform eDiscovery across satellite geo locations.</span></span> 

<span data-ttu-id="e0e06-110">El administrador global de Microsoft 365 debe asignar permisos de supervisor de eDiscovery para que otros usuarios puedan ejecutar eDiscovery y asignar un parámetro "Región" en el filtro de seguridad de cumplimiento correspondiente para especificar la región donde se ejecutará eDiscovery como ubicación por satélite; en caso contrario, no se ejecutará eDiscovery en la ubicación por satélite.</span><span class="sxs-lookup"><span data-stu-id="e0e06-110">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="e0e06-p103">Cuando se establece el rol Administrador o Supervisor de eDiscovery para una ubicación satélite concreta, el administrador o supervisor de eDiscovery solo podrán realizar acciones de búsqueda de eDiscovery en sitios de SharePoint y OneDrive situados en esa ubicación satélite. Si un administrador o supervisor de eDiscovery intenta realizar búsquedas en sitios de SharePoint o OneDrive fuera de la ubicación satélite especificada, no se devolverá ningún resultado. Además, cuando el administrador o supervisor de eDiscovery de una ubicación satélite desencadena una exportación, los datos se exportan a la instancia de Azure de esa región. Esto ayuda a las organizaciones a mantener el cumplimiento al no permitir que el contenido se exporte a través de fronteras controladas.</span><span class="sxs-lookup"><span data-stu-id="e0e06-p103">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location. If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned. Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region. This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="e0e06-115">Si es necesario que un supervisor de eDiscovery realice búsquedas en varias ubicaciones satélite de SharePoint, habrá que crear otra cuenta para el supervisor de eDiscovery que especifique la ubicación satélite alternativa donde se encuentran los sitios de OneDrive o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e0e06-115">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="e0e06-116">Para establecer el filtro de seguridad de cumplimiento para una región:</span><span class="sxs-lookup"><span data-stu-id="e0e06-116">To set the Compliance Security Filter for a Region:</span></span>

1. <span data-ttu-id="e0e06-117">[Conéctese a PowerShell del Centro de seguridad y cumplimiento de Microsoft 365](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="e0e06-117">[Connect to Microsoft 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)</span></span>

2. <span data-ttu-id="e0e06-118">Use la sintaxis que se muestre a continuación:</span><span class="sxs-lookup"><span data-stu-id="e0e06-118">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="e0e06-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e0e06-119">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="e0e06-120">Vea el articulo [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter) para obtener más parámetros y sintaxis.</span><span class="sxs-lookup"><span data-stu-id="e0e06-120">See the [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>
