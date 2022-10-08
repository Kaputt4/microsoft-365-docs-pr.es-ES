---
title: Límites en el caso de eDiscovery (estándar)
description: En este artículo se describen los límites en el caso de exhibición de documentos electrónicos (estándar) en Microsoft 365.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
- ediscovery
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6dac70d326f6d6c0480797bf7a7b00ec0ea2be7f
ms.sourcegitcommit: 4dfb5de8c61847b8ddd10410ad20d34860eed8f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68131991"
---
# <a name="limits-in-ediscovery-standard"></a>Límites en eDiscovery (estándar)

En la tabla siguiente se enumeran los límites de los casos de exhibición de documentos electrónicos (estándar) y las retenciones asociadas a un caso de exhibición de documentos electrónicos (estándar). Para obtener más información sobre Microsoft Purview eDiscovery (estándar), vea [Información general sobre eDiscovery (Estándar).](./get-started-core-ediscovery.md)
    
  | Descripción del límite | Límite |
  |:-----|:-----|
  |Número máximo de casos para una organización.  <br/> |Sin límite  <br/> |
  |Número máximo de retenciones de casos para una organización.  <br/> |10,000  <br/> |
  |Número máximo de buzones en una sola retención de casos. Este límite incluye el total combinado de buzones de usuario y los buzones asociados a Grupos de Microsoft 365, Microsoft Teams y grupos de Yammer.  <br/> |1,000  <br/> |
  |Número máximo de sitios en una única retención de mayúsculas y minúsculas. Este límite incluye el total combinado de sitios de OneDrive para la Empresa, sitios de SharePoint y los sitios asociados a Grupos de Microsoft 365, Microsoft Teams y grupos de Yammer.  <br/> |100  <br/> |
  |Número máximo de casos mostrados en la página principal de eDiscovery (Estándar) y el número máximo de elementos que se muestran en las pestañas Holds, Searches y Export dentro de un caso. <sup>1</sup> |1,000|

   > [!NOTE]
   > <sup>1</sup> Para ver una lista de más de 1000 casos, retenciones, búsquedas o exportaciones, puede usar los cmdlets de PowerShell correspondientes Office 365 Security & Compliance:
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

Para obtener más información sobre los límites relacionados con las búsquedas y las exportaciones asociadas a un caso de exhibición de documentos electrónicos (estándar[), vea Límites de búsqueda de contenido y exhibición de documentos electrónicos (estándar).](limits-for-content-search.md)