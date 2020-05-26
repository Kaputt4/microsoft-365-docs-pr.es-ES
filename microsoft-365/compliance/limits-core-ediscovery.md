---
title: Límites en caso de exhibición de documentos electrónicos principal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
ms.openlocfilehash: 00df8cff683701ce5ee38dca12b6f7af5b31c8b0
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351901"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="713d2-103">Límites de la exhibición de documentos electrónicos principal</span><span class="sxs-lookup"><span data-stu-id="713d2-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="713d2-104">En la tabla siguiente se enumeran los límites de casos de eDiscovery principales y las retenciones asociadas a un caso de exhibición de documentos electrónicos principal.</span><span class="sxs-lookup"><span data-stu-id="713d2-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="713d2-105">Para obtener más información acerca de la exhibición de documentos electrónicos principal, vea [Overview of Core eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="713d2-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="713d2-106">**Descripción del límite**</span><span class="sxs-lookup"><span data-stu-id="713d2-106">**Description of limit**</span></span>|<span data-ttu-id="713d2-107">**Límite**</span><span class="sxs-lookup"><span data-stu-id="713d2-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="713d2-108">Número máximo de casos para una organización</span><span class="sxs-lookup"><span data-stu-id="713d2-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="713d2-109">Sin límite</span><span class="sxs-lookup"><span data-stu-id="713d2-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="713d2-110">Número máximo de retenciones de casos para una organización</span><span class="sxs-lookup"><span data-stu-id="713d2-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="713d2-111">10 000</span><span class="sxs-lookup"><span data-stu-id="713d2-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="713d2-112">Número máximo de buzones en una sola suspensión de casos</span><span class="sxs-lookup"><span data-stu-id="713d2-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="713d2-113">1.000</span><span class="sxs-lookup"><span data-stu-id="713d2-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="713d2-114">Número máximo de sitios de SharePoint y OneDrive para la empresa en una sola suspensión de mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="713d2-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="713d2-115">100</span><span class="sxs-lookup"><span data-stu-id="713d2-115">100</span></span>  <br/> |
  |<span data-ttu-id="713d2-116">Número máximo de escenarios mostrados en la Página principal de eDiscovery principal y el número máximo de elementos que se muestran en las pestañas suspensiones, búsquedas y exportación en un caso.</span><span class="sxs-lookup"><span data-stu-id="713d2-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="713d2-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="713d2-117"><sup>1</sup></span></span> |<span data-ttu-id="713d2-118">1.000</span><span class="sxs-lookup"><span data-stu-id="713d2-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="713d2-119"><sup>1</sup> para ver una lista de más de 1.000 casos, suspensiones, búsquedas o exportaciones, puede usar el cmdlet de PowerShell de cumplimiento de & de seguridad de Office 365:</span><span class="sxs-lookup"><span data-stu-id="713d2-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="713d2-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="713d2-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [<span data-ttu-id="713d2-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="713d2-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [<span data-ttu-id="713d2-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="713d2-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [<span data-ttu-id="713d2-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="713d2-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
