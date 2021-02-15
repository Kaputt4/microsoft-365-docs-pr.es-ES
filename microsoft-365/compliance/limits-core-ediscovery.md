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
# <a name="limits-in-core-ediscovery"></a>Límites de eDiscovery principal

En la tabla siguiente se enumeran los límites de casos y retenciones principales de eDiscovery asociados a un caso de eDiscovery principal. Para obtener más información acerca de la exhibición de documentos electrónicos principal, vea [Información general sobre eDiscovery principal.](ediscovery-cases.md)
    
  | Descripción del límite | Límite |
  |:-----|:-----|
  |Número máximo de casos para una organización  <br/> |Sin límite  <br/> |
  |Número máximo de retenciones de casos para una organización  <br/> |10 000  <br/> |
  |Número máximo de buzones en una única retención de casos  <br/> |1,000  <br/> |
  |Número máximo de sitios de SharePoint y OneDrive para la Empresa en una única retención de casos  <br/> |100  <br/> |
  |Número máximo de casos que se muestran en la página principal de eDiscovery principal y el número máximo de elementos que se muestran en las pestañas Retenciones, Búsquedas y Exportación dentro de un caso. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Para ver una lista de más de 1.000 casos, retenciones, búsquedas o exportaciones, puede usar los cmdlets de PowerShell de seguridad y cumplimiento de Office 36 & 5 correspondientes:
   > 
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

Para obtener más información acerca de los límites relacionados con las búsquedas de contenido y las exportaciones asociadas con un caso de exhibición de documentos electrónicos principal, vea Límites de búsqueda de contenido y exhibición de documentos [electrónicos principal.](limits-for-content-search.md)