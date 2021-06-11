---
title: Límites en el caso principal de exhibición de documentos electrónicos
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
description: En este artículo se describen los límites en el caso principal de exhibición de documentos electrónicos en Microsoft 365.
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311429"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="ef489-103">Límites en eDiscovery principal</span><span class="sxs-lookup"><span data-stu-id="ef489-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="ef489-104">En la tabla siguiente se enumeran los límites de los casos principales de exhibición de documentos electrónicos y las retenciones asociadas a un caso de exhibición de documentos electrónicos principal.</span><span class="sxs-lookup"><span data-stu-id="ef489-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="ef489-105">Para obtener más información acerca de la exhibición de documentos electrónicos principales, vea [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="ef489-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span></span>
    
  | <span data-ttu-id="ef489-106">Descripción del límite</span><span class="sxs-lookup"><span data-stu-id="ef489-106">Description of limit</span></span> | <span data-ttu-id="ef489-107">Límite</span><span class="sxs-lookup"><span data-stu-id="ef489-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="ef489-108">Número máximo de casos para una organización.</span><span class="sxs-lookup"><span data-stu-id="ef489-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="ef489-109">Sin límite</span><span class="sxs-lookup"><span data-stu-id="ef489-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="ef489-110">Número máximo de retenciones de casos para una organización.</span><span class="sxs-lookup"><span data-stu-id="ef489-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="ef489-111">10 000</span><span class="sxs-lookup"><span data-stu-id="ef489-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="ef489-112">Número máximo de buzones en una única retención de casos.</span><span class="sxs-lookup"><span data-stu-id="ef489-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="ef489-113">Este límite incluye el total combinado de buzones de usuario y los buzones asociados con grupos de Microsoft 365, Microsoft Teams y Yammer grupos.</span><span class="sxs-lookup"><span data-stu-id="ef489-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="ef489-114">1.000</span><span class="sxs-lookup"><span data-stu-id="ef489-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="ef489-115">Número máximo de sitios en una única retención de casos.</span><span class="sxs-lookup"><span data-stu-id="ef489-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="ef489-116">Este límite incluye el total combinado de sitios OneDrive para la Empresa, SharePoint y los sitios asociados con grupos de Microsoft 365, Microsoft Teams y Yammer grupos.</span><span class="sxs-lookup"><span data-stu-id="ef489-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="ef489-117">100</span><span class="sxs-lookup"><span data-stu-id="ef489-117">100</span></span>  <br/> |
  |<span data-ttu-id="ef489-118">Número máximo de casos que se muestran en la página principal de exhibición de documentos electrónicos principal y el número máximo de elementos que se muestran en las pestañas Retenciones, Búsquedas y Exportación dentro de un caso.</span><span class="sxs-lookup"><span data-stu-id="ef489-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="ef489-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ef489-119"><sup>1</sup></span></span> |<span data-ttu-id="ef489-120">1.000</span><span class="sxs-lookup"><span data-stu-id="ef489-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="ef489-121"><sup>1</sup> Para ver una lista de más de 1.000 casos, retenciones, búsquedas o exportaciones, puede usar los cmdlets Office 365 Security & Compliance PowerShell correspondientes:</span><span class="sxs-lookup"><span data-stu-id="ef489-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="ef489-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="ef489-122">Get-ComplianceCase</span></span>](/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="ef489-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="ef489-123">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="ef489-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="ef489-124">Get-ComplianceSearch</span></span>](/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="ef489-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="ef489-125">Get-ComplianceSearchAction</span></span>](/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="ef489-126">Para obtener más información acerca de los límites relacionados con las búsquedas y exportaciones asociadas con un caso de exhibición de documentos electrónicos principales, vea [Limits for Content search y Core eDiscovery](limits-for-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="ef489-126">For more information about limits related to searches and exports associated with a Core eDiscovery case, see [Limits for Content search and Core eDiscovery](limits-for-content-search.md).</span></span>