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
# <a name="limits-in-core-ediscovery"></a>Límites en eDiscovery principal

En la tabla siguiente se enumeran los límites de los casos principales de exhibición de documentos electrónicos y las retenciones asociadas a un caso de exhibición de documentos electrónicos principal. Para obtener más información acerca de la exhibición de documentos electrónicos principales, vea [Overview of Core eDiscovery](./get-started-core-ediscovery.md).
    
  | Descripción del límite | Límite |
  |:-----|:-----|
  |Número máximo de casos para una organización.  <br/> |Sin límite  <br/> |
  |Número máximo de retenciones de casos para una organización.  <br/> |10,000  <br/> |
  |Número máximo de buzones en una única retención de casos. Este límite incluye el total combinado de buzones de usuario y los buzones asociados con grupos de Microsoft 365, Microsoft Teams y Yammer grupos.  <br/> |1,000  <br/> |
  |Número máximo de sitios en una única retención de casos. Este límite incluye el total combinado de sitios OneDrive para la Empresa, SharePoint y los sitios asociados con grupos de Microsoft 365, Microsoft Teams y Yammer grupos.  <br/> |100  <br/> |
  |Número máximo de casos que se muestran en la página principal de exhibición de documentos electrónicos principal y el número máximo de elementos que se muestran en las pestañas Retenciones, Búsquedas y Exportación dentro de un caso. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Para ver una lista de más de 1.000 casos, retenciones, búsquedas o exportaciones, puede usar los cmdlets Office 365 Security & Compliance PowerShell correspondientes:
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

Para obtener más información acerca de los límites relacionados con las búsquedas y exportaciones asociadas con un caso de exhibición de documentos electrónicos principales, vea [Limits for Content search y Core eDiscovery](limits-for-content-search.md).