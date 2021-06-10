---
title: Crear un grupo Microsoft 365 con una ubicación de datos preferida específica
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Obtenga información sobre cómo crear un grupo Microsoft 365 con una ubicación de datos preferida especificada en un entorno multige geográfico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41984dc24e0f30e5e7b7eb0f9672c75b6d65388f
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086829"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a><span data-ttu-id="dee8d-103">Crear un grupo Microsoft 365 con una ubicación de datos preferida específica</span><span class="sxs-lookup"><span data-stu-id="dee8d-103">Create a Microsoft 365 Group with a specific preferred data location</span></span>

<span data-ttu-id="dee8d-104">Cuando los usuarios de un entorno multige geográfico crean un grupo de Microsoft 365, la ubicación de datos preferida (PDL) del grupo se establece automáticamente en la del usuario.</span><span class="sxs-lookup"><span data-stu-id="dee8d-104">When users in a multi-geo environment create a Microsoft 365 Group, the group preferred data location (PDL) is automatically set to that of the user.</span></span> <span data-ttu-id="dee8d-105">Los administradores globales, de SharePoint y de Exchange pueden crear grupos en cualquier región que seleccionen.</span><span class="sxs-lookup"><span data-stu-id="dee8d-105">Global, SharePoint, and Exchange Administrators can create groups in any region they select.</span></span> 

<span data-ttu-id="dee8d-106">Si necesita crear un grupo con un PDL específico, puede hacerlo desde el Centro de administración de SharePoint o a través del cmdlet New-UnifiedGroup de Exchange Online de Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dee8d-106">If you need to create a group with a specific PDL, you can do that using from the SharePoint admin center or through the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="dee8d-107">Al hacerlo, tanto el buzón del grupo como el sitio de SharePoint asociado con el grupo se aprovisionarán en el PDL especificado.</span><span class="sxs-lookup"><span data-stu-id="dee8d-107">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="dee8d-108">Para crear un grupo Microsoft 365 con la PDL que especifique, vaya al Centro de administración de SharePoint en la ubicación geográfica donde desea crear el sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="dee8d-108">To create a Microsoft 365 Group with the PDL that you specify, go to the SharePoint admin center in the geo location where you want to create the group site.</span></span>

<span data-ttu-id="dee8d-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dee8d-109">For example:</span></span>

<span data-ttu-id="dee8d-110">Si desea crear un sitio de grupo en su ubicación de Australia, puede ir a https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span><span class="sxs-lookup"><span data-stu-id="dee8d-110">If you want to create a group site in your Australia location, you can go to https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span></span>

1. <span data-ttu-id="dee8d-111">Seleccione **+ Crear**.</span><span class="sxs-lookup"><span data-stu-id="dee8d-111">Select **+ Create**.</span></span>
2. <span data-ttu-id="dee8d-112">Siga el proceso para crear un sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="dee8d-112">Follow the process to create a group site.</span></span>

<span data-ttu-id="dee8d-113">El sitio de grupo se aprovisionará en la ubicación geográfica correspondiente al Centro de administración de SharePoint desde el que haya iniciado la solicitud de creación de sitios.</span><span class="sxs-lookup"><span data-stu-id="dee8d-113">Your group site will be provisioned in the geo location corresponding to the SharePoint admin center from which you initiated the site creation request.</span></span> 

<span data-ttu-id="dee8d-114">Usar Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="dee8d-114">Using Exchange PowerShell</span></span> 

<span data-ttu-id="dee8d-115">Conéctese a Exchange Online PowerShell y pase el parámetro *-MailBoxRegion* con el código de ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="dee8d-115">Connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="dee8d-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dee8d-116">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Captura de pantalla del cmdlet de PowerShell New-UnifiedGroup con la sintaxis](../media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="dee8d-118">Tenga en cuenta que el aprovisionamiento de sitios de grupo de SharePoint se realiza a petición.</span><span class="sxs-lookup"><span data-stu-id="dee8d-118">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="dee8d-119">El sitio se aprovisionará la primera vez que un propietario o miembro del grupo intente acceder a él.</span><span class="sxs-lookup"><span data-stu-id="dee8d-119">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="dee8d-120">Códigos de ubicación geográfica</span><span class="sxs-lookup"><span data-stu-id="dee8d-120">Geo location codes</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a><span data-ttu-id="dee8d-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="dee8d-121">Related topics</span></span>

[<span data-ttu-id="dee8d-122">Conectarse a Exchange Online mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="dee8d-122">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
