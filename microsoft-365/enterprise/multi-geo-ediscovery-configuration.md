---
title: Configurar eDiscovery para Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
ms.collection: Strat_SP_gtc
description: Obtenga información sobre cómo usar el parámetro Region para configurar la exhibición de documentos electrónicos para su uso en ubicaciones satélite en Microsoft 365 Multi-Geo.
ms.openlocfilehash: b0366470984abbdc0ed0b3e407ca8ef6b5a5743f
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2022
ms.locfileid: "63400942"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Configuración de eDiscovery de Microsoft 365 Multi-Geo

[Advanced eDiscovery permiten](../compliance/overview-ediscovery-20.md) a un administrador de exhibición de documentos electrónicos multigefia buscar en todas las geos sin necesidad de usar un filtro de seguridad "Región". Los datos se exportan a la instancia de Azure de la ubicación central del inquilino multigefia. Lo mismo sucede con la aplicación de una retención a un custodio, pero las estadísticas de retención dentro de la retención no aparecerán sin el filtro de seguridad "Región". Las estadísticas de retención que muestran 0 no significan que la retención falló siempre y cuando el estado de retención se muestre En (correcto).

Sin capacidades avanzadas de exhibición de documentos electrónicos, un administrador de exhibición de documentos electrónicos o un administrador de un inquilino multigefia solo podrá llevar a cabo la exhibición de documentos electrónicos en la ubicación central de ese espacio empresarial. Para admitir la capacidad de llevar a cabo la exhibición de documentos electrónicos para ubicaciones satélite, hay disponible un nuevo parámetro de filtro de seguridad de cumplimiento denominado "Región" a través de PowerShell. Este parámetro lo pueden usar los inquilinos cuya ubicación central se encuentra en Norteamérica, Europa o Asia Pacífico. Advanced eDiscovery se recomienda para los inquilinos cuya ubicación central no se encuentra en Norteamérica, Europa o Asia Pacífico y que necesitan realizar exhibición de documentos electrónicos en ubicaciones geográficas por satélite. 

El administrador global de Microsoft 365 debe asignar permisos al Administrador de exhibición de documentos electrónicos para permitir que otros realicen exhibición de documentos electrónicos y asigne un parámetro "Región" en su filtro de seguridad de cumplimiento aplicable para especificar la región para llevar a cabo la exhibición de documentos electrónicos como ubicación satélite, de lo contrario, no se llevará a cabo ninguna exhibición de documentos electrónicos para la ubicación satélite. Solo se admite un filtro de seguridad "Región" por usuario, por lo que todas las regiones deben estar dentro del mismo filtro de seguridad.

Cuando se establece el rol Administrador o Supervisor de eDiscovery para una ubicación satélite concreta, el administrador o supervisor de eDiscovery solo podrán realizar acciones de búsqueda de eDiscovery en sitios de SharePoint y OneDrive situados en esa ubicación satélite. Si un administrador o supervisor de eDiscovery intenta realizar búsquedas en sitios de SharePoint o OneDrive fuera de la ubicación satélite especificada, no se devolverá ningún resultado. Además, cuando el administrador o supervisor de eDiscovery de una ubicación satélite desencadena una exportación, los datos se exportan a la instancia de Azure de esa región. Esto ayuda a las organizaciones a mantener el cumplimiento al no permitir que el contenido se exporte a través de fronteras controladas.

> [!NOTE]
> Si es necesario que un supervisor de eDiscovery realice búsquedas en varias ubicaciones satélite de SharePoint, habrá que crear otra cuenta para el supervisor de eDiscovery que especifique la ubicación satélite alternativa donde se encuentran los sitios de OneDrive o SharePoint.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Para establecer el filtro de seguridad de cumplimiento para una región:

1. [Conéctese a PowerShell del Centro de seguridad y cumplimiento de Microsoft 365](/powershell/exchange/connect-to-scc-powershell).

2. Use la sintaxis que se muestre a continuación:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Por ejemplo:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Vea el articulo [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) para obtener más parámetros y sintaxis.
