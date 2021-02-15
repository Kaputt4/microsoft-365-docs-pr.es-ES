---
title: Límites en el caso principal de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: En este artículo se describen los límites del caso principal de eDiscovery en Microsoft 365.
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799667"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="34d55-103">Límites de eDiscovery principal</span><span class="sxs-lookup"><span data-stu-id="34d55-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="34d55-104">En la tabla siguiente se enumeran los límites de casos y retenciones principales de eDiscovery asociados a un caso de eDiscovery principal.</span><span class="sxs-lookup"><span data-stu-id="34d55-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="34d55-105">Para obtener más información acerca de la exhibición de documentos electrónicos principal, vea [Información general sobre eDiscovery principal.](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="34d55-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="34d55-106">Descripción del límite</span><span class="sxs-lookup"><span data-stu-id="34d55-106">Description of limit</span></span> | <span data-ttu-id="34d55-107">Límite</span><span class="sxs-lookup"><span data-stu-id="34d55-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="34d55-108">Número máximo de casos para una organización</span><span class="sxs-lookup"><span data-stu-id="34d55-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="34d55-109">Sin límite</span><span class="sxs-lookup"><span data-stu-id="34d55-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="34d55-110">Número máximo de retenciones de casos para una organización</span><span class="sxs-lookup"><span data-stu-id="34d55-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="34d55-111">10 000</span><span class="sxs-lookup"><span data-stu-id="34d55-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="34d55-112">Número máximo de buzones en una única retención de casos</span><span class="sxs-lookup"><span data-stu-id="34d55-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="34d55-113">1,000</span><span class="sxs-lookup"><span data-stu-id="34d55-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="34d55-114">Número máximo de sitios de SharePoint y OneDrive para la Empresa en una única retención de casos</span><span class="sxs-lookup"><span data-stu-id="34d55-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="34d55-115">100</span><span class="sxs-lookup"><span data-stu-id="34d55-115">100</span></span>  <br/> |
  |<span data-ttu-id="34d55-116">Número máximo de casos que se muestran en la página principal de eDiscovery principal y el número máximo de elementos que se muestran en las pestañas Retenciones, Búsquedas y Exportación dentro de un caso.</span><span class="sxs-lookup"><span data-stu-id="34d55-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="34d55-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="34d55-117"><sup>1</sup></span></span> |<span data-ttu-id="34d55-118">1,000</span><span class="sxs-lookup"><span data-stu-id="34d55-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="34d55-119"><sup>1</sup> Para ver una lista de más de 1.000 casos, retenciones, búsquedas o exportaciones, puede usar los cmdlets de PowerShell de seguridad y cumplimiento de Office 36 & 5 correspondientes:</span><span class="sxs-lookup"><span data-stu-id="34d55-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="34d55-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="34d55-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="34d55-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="34d55-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="34d55-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="34d55-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="34d55-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="34d55-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="34d55-124">Para obtener más información acerca de los límites relacionados con las búsquedas de contenido y las exportaciones asociadas con un caso de exhibición de documentos electrónicos principal, vea Límites de búsqueda de contenido y exhibición de documentos [electrónicos principal.](limits-for-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="34d55-124">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>