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
ms.openlocfilehash: 67f15bb39ed75f40a8ef42747c0d4e2dfcb1297d
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64949617"
---
# <a name="limits-in-ediscovery-standard"></a>Límites en eDiscovery (estándar)

En la tabla siguiente se enumeran los límites de los casos principales de eDiscovery y las retenciones asociadas a un caso principal de eDiscovery. Para obtener más información sobre la exhibición de documentos electrónicos de Microsoft Purview (estándar), vea [Información general sobre eDiscovery (Estándar).](./get-started-core-ediscovery.md)
    
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

Para obtener más información sobre los límites relacionados con las búsquedas y las exportaciones asociadas a un caso de exhibición de documentos electrónicos (estándar[), vea Límites de búsqueda de contenido y exhibición de documentos electrónicos (estándar).](limits-for-content-search.md)