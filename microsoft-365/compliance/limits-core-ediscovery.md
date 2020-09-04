---
title: Límites en caso de exhibición de documentos electrónicos principal
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
ms.openlocfilehash: 6224ce5ecb8fc0439e43ab5e1362f8a618194202
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358518"
---
# <a name="limits-in-core-ediscovery"></a>Límites de la exhibición de documentos electrónicos principal

En la tabla siguiente se enumeran los límites de casos de eDiscovery principales y las retenciones asociadas a un caso de exhibición de documentos electrónicos principal. Para obtener más información acerca de la exhibición de documentos electrónicos principal, vea [Overview of Core eDiscovery](ediscovery-cases.md).
    
  |**Descripción del límite**|**Límite**|
  |:-----|:-----|
  |Número máximo de casos para una organización  <br/> |Sin límite  <br/> |
  |Número máximo de retenciones de casos para una organización  <br/> |10 000  <br/> |
  |Número máximo de buzones en una sola suspensión de casos  <br/> |1,000  <br/> |
  |Número máximo de sitios de SharePoint y OneDrive para la empresa en una sola suspensión de mayúsculas y minúsculas  <br/> |100  <br/> |
  |Número máximo de escenarios mostrados en la Página principal de eDiscovery principal y el número máximo de elementos que se muestran en las pestañas suspensiones, búsquedas y exportación en un caso. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> para ver una lista de más de 1.000 casos, suspensiones, búsquedas o exportaciones, puede usar el cmdlet de PowerShell de cumplimiento de & de seguridad de Office 365:<br/> [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
