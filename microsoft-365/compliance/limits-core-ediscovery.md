---
title: Límites en el caso principal de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: En este artículo se describen los límites en el caso principal de eDiscovery en Microsoft 365.
ms.openlocfilehash: 2d920fbe5973d07b7da656d6247038ab785bbe5c
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "64822658"
---
# <a name="limits-in-core-ediscovery"></a>Límites en eDiscovery principal

En la tabla siguiente se enumeran los límites de los casos principales de eDiscovery y las retenciones asociadas a un caso principal de eDiscovery. Para obtener más información sobre core eDiscovery, vea [Información general de eDiscovery](./get-started-core-ediscovery.md) principal.
    
  | Descripción del límite | Límite |
  |:-----|:-----|
  |Número máximo de casos para una organización.  <br/> |Sin límite  <br/> |
  |Número máximo de retenciones de casos para una organización.  <br/> |10,000  <br/> |
  |Número máximo de buzones en una única retención de mayúsculas y minúsculas. Este límite incluye el total combinado de buzones de usuario y los buzones asociados a Grupos de Microsoft 365, Microsoft Teams y grupos de Yammer.  <br/> |1,000  <br/> |
  |Número máximo de sitios en una única retención de mayúsculas y minúsculas. Este límite incluye el total combinado de sitios de OneDrive para la Empresa, sitios SharePoint y los sitios asociados con Grupos de Microsoft 365, Microsoft Teams y grupos de Yammer.  <br/> |100  <br/> |
  |Número máximo de casos mostrados en la página principal de eDiscovery principal y el número máximo de elementos que se muestran en las pestañas Holds, Searches y Export dentro de un caso. <sup>1</sup> |1,000|

   > [!NOTE]
   > <sup>1</sup> Para ver una lista de más de 1000 casos, retenciones, búsquedas o exportaciones, puede usar los cmdlets de PowerShell correspondientes Office 365 Security & Compliance:
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

Para obtener más información sobre los límites relacionados con las búsquedas y las exportaciones asociadas a un caso de eDiscovery principal, vea [Límites para la búsqueda de contenido y eDiscovery principal](limits-for-content-search.md).