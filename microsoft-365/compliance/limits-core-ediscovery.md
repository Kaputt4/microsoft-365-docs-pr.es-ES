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
description: En este artículo se describen los límites del caso principal de exhibición de documentos electrónicos en Microsoft 365.
ms.openlocfilehash: 2699e9b2511c742bb295f69611a976f6a3955980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423451"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="47dce-103">Límites en eDiscovery principal</span><span class="sxs-lookup"><span data-stu-id="47dce-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="47dce-104">En la tabla siguiente se enumeran los límites de los casos principales de exhibición de documentos electrónicos y las retenciones asociadas a un caso de exhibición de documentos electrónicos principal.</span><span class="sxs-lookup"><span data-stu-id="47dce-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="47dce-105">Para obtener más información acerca de la exhibición de documentos electrónicos principales, vea [Overview of Core eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="47dce-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="47dce-106">Descripción del límite</span><span class="sxs-lookup"><span data-stu-id="47dce-106">Description of limit</span></span> | <span data-ttu-id="47dce-107">Límite</span><span class="sxs-lookup"><span data-stu-id="47dce-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="47dce-108">Número máximo de casos para una organización.</span><span class="sxs-lookup"><span data-stu-id="47dce-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="47dce-109">Sin límite</span><span class="sxs-lookup"><span data-stu-id="47dce-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="47dce-110">Número máximo de retenciones de casos para una organización.</span><span class="sxs-lookup"><span data-stu-id="47dce-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="47dce-111">10 000</span><span class="sxs-lookup"><span data-stu-id="47dce-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="47dce-112">Número máximo de buzones en una única retención de casos.</span><span class="sxs-lookup"><span data-stu-id="47dce-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="47dce-113">Este límite incluye el total combinado de buzones de usuario y los buzones asociados con grupos de Microsoft 365, Microsoft Teams y grupos de Yammer.</span><span class="sxs-lookup"><span data-stu-id="47dce-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="47dce-114">1,000</span><span class="sxs-lookup"><span data-stu-id="47dce-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="47dce-115">Número máximo de sitios en una única retención de casos.</span><span class="sxs-lookup"><span data-stu-id="47dce-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="47dce-116">Este límite incluye el total combinado de sitios de OneDrive para la Empresa, sitios de SharePoint y los sitios asociados con Grupos de Microsoft 365, Microsoft Teams y Grupos de Yammer.</span><span class="sxs-lookup"><span data-stu-id="47dce-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="47dce-117">100</span><span class="sxs-lookup"><span data-stu-id="47dce-117">100</span></span>  <br/> |
  |<span data-ttu-id="47dce-118">Número máximo de casos que se muestran en la página principal de exhibición de documentos electrónicos principal y el número máximo de elementos que se muestran en las pestañas Retenciones, Búsquedas y Exportación dentro de un caso.</span><span class="sxs-lookup"><span data-stu-id="47dce-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="47dce-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="47dce-119"><sup>1</sup></span></span> |<span data-ttu-id="47dce-120">1,000</span><span class="sxs-lookup"><span data-stu-id="47dce-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="47dce-121"><sup>1</sup> Para ver una lista de más de 1.000 casos, retenciones, búsquedas o exportaciones, puede usar los cmdlets de PowerShell de seguridad de Office 365 correspondientes & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="47dce-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="47dce-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="47dce-122">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="47dce-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="47dce-123">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="47dce-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="47dce-124">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="47dce-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="47dce-125">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="47dce-126">Para obtener más información acerca de los límites relacionados con las búsquedas de contenido y las exportaciones asociadas con un caso de exhibición de documentos electrónicos principales, vea [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="47dce-126">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>