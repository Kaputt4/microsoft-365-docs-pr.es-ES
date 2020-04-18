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
ms.openlocfilehash: 4d91b81caee31e693ce29c6d8d629d563d973ae7
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551487"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="b9d45-103">Límites de la exhibición de documentos electrónicos principal</span><span class="sxs-lookup"><span data-stu-id="b9d45-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="b9d45-104">En la tabla siguiente se enumeran los límites de casos de eDiscovery principales y las retenciones asociadas a un caso de exhibición de documentos electrónicos principal.</span><span class="sxs-lookup"><span data-stu-id="b9d45-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="b9d45-105">Para obtener más información acerca de la exhibición de documentos electrónicos principal, vea [Overview of Core eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="b9d45-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="b9d45-106">**Descripción del límite**</span><span class="sxs-lookup"><span data-stu-id="b9d45-106">**Description of limit**</span></span>|<span data-ttu-id="b9d45-107">**Límite**</span><span class="sxs-lookup"><span data-stu-id="b9d45-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="b9d45-108">Número máximo de casos para una organización</span><span class="sxs-lookup"><span data-stu-id="b9d45-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="b9d45-109">Sin límite</span><span class="sxs-lookup"><span data-stu-id="b9d45-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="b9d45-110">Número máximo de retenciones de casos para una organización</span><span class="sxs-lookup"><span data-stu-id="b9d45-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="b9d45-111">10 000</span><span class="sxs-lookup"><span data-stu-id="b9d45-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="b9d45-112">Número máximo de buzones en una sola suspensión de casos</span><span class="sxs-lookup"><span data-stu-id="b9d45-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="b9d45-113">1.000</span><span class="sxs-lookup"><span data-stu-id="b9d45-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="b9d45-114">Número máximo de sitios de SharePoint y OneDrive para la empresa en una sola suspensión de mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="b9d45-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="b9d45-115">100</span><span class="sxs-lookup"><span data-stu-id="b9d45-115">100</span></span>  <br/> |
  |<span data-ttu-id="b9d45-116">Número máximo de escenarios mostrados en la Página principal de eDiscovery principal y el número máximo de elementos que se muestran en las pestañas suspensiones, búsquedas y exportación en un caso.</span><span class="sxs-lookup"><span data-stu-id="b9d45-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="b9d45-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b9d45-117"><sup>1</sup></span></span> |<span data-ttu-id="b9d45-118">1.000</span><span class="sxs-lookup"><span data-stu-id="b9d45-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="b9d45-119"><sup>1</sup> para ver una lista de más de 1.000 casos, suspensiones, búsquedas o exportaciones, puede usar el cmdlet de PowerShell de cumplimiento de & de seguridad de Office 365:</span><span class="sxs-lookup"><span data-stu-id="b9d45-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="b9d45-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="b9d45-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase) <br/> [<span data-ttu-id="b9d45-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="b9d45-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)<br/> [<span data-ttu-id="b9d45-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="b9d45-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)<br/> [<span data-ttu-id="b9d45-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="b9d45-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)
