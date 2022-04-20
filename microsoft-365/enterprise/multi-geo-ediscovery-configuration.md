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
description: Obtenga información sobre cómo usar el parámetro Region para configurar eDiscovery para su uso en ubicaciones satélite en Microsoft 365 multigeográfica.
ms.openlocfilehash: 6160087006e77de085f6a28614b95d1136890fd3
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64973297"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Configuración de eDiscovery de Microsoft 365 Multi-Geo

[Las funcionalidades de eDiscovery (Premium)](../compliance/overview-ediscovery-20.md) permiten a un administrador de exhibición de documentos electrónicos multigeográfica buscar en todas las zonas geográficas sin necesidad de usar un filtro de seguridad "Región". Los datos se exportan a la instancia de Azure de la ubicación central del inquilino multigeográfico. Lo mismo sucede con la aplicación de una suspensión en un custodio, pero las estadísticas de suspensión dentro de la suspensión no aparecerán sin el filtro de seguridad "Región". Las estadísticas de suspensión que muestran 0 no significa que se haya producido un error en la suspensión siempre y cuando el estado de suspensión se muestre Activado (correcto).

Sin las funcionalidades de eDiscovery (Premium), un administrador de exhibición de documentos electrónicos o un administrador de un inquilino multigeográfico solo podrá realizar eDiscovery en la ubicación central de ese inquilino. Para admitir la capacidad de realizar eDiscovery para ubicaciones satélite, hay disponible un nuevo parámetro de filtro de seguridad de cumplimiento denominado "Región" a través de PowerShell. Los inquilinos cuya ubicación central se encuentra en Norteamérica, Europa o Asia Pacífico pueden usar este parámetro. Se recomienda eDiscovery (Premium) para los inquilinos cuya ubicación central no está en Norteamérica, Europa o Asia Pacífico y que necesitan realizar eDiscovery en ubicaciones geográficas por satélite. 

El administrador global de Microsoft 365 debe asignar permisos del Administrador de exhibición de documentos electrónicos para permitir que otros usuarios realicen eDiscovery y asignen un parámetro "Region" en su filtro de seguridad de cumplimiento aplicable para especificar la región para realizar eDiscovery como ubicación satélite; de lo contrario, no se llevará a cabo ninguna eDiscovery para la ubicación satélite. Solo se admite un filtro de seguridad "Región" por usuario, por lo que todas las regiones deben estar dentro del mismo filtro de seguridad.

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
