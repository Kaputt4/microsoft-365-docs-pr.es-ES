---
title: Configurar eDiscovery para Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
ms.collection: Strat_SP_gtc
description: Obtenga información sobre cómo usar el parámetro Region para configurar eDiscovery para su uso en ubicaciones satélite en Microsoft 365 Multi-Geo.
ms.openlocfilehash: f46699221c257319dbe9bba356c9487e74d0dd2a
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804404"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Configuración de eDiscovery de Microsoft 365 Multi-Geo

[Las funcionalidades de eDiscovery (Premium)](../compliance/overview-ediscovery-20.md) permiten a un administrador de eDiscovery multigeográfica buscar en todas las _zonas geográficas_ sin necesidad de usar un filtro de seguridad "Región". Los datos se exportan a la instancia de Azure de la ubicación _geografía aprovisionada principal_ del _inquilino multigeográfico_.

Sin las funcionalidades de eDiscovery (Premium), un administrador de eDiscovery o un administrador de un _inquilino multigeográfico_ solo podrá realizar eDiscovery en la ubicación _geografía aprovisionada principal_ de ese _inquilino_. Para admitir la capacidad de realizar eDiscovery para ubicaciones _de geografía satélite_ , hay disponible un nuevo parámetro de filtro de seguridad de cumplimiento denominado "Región" a través de PowerShell. Los _inquilinos_ cuya ubicación _geográfica aprovisionada principal_ se encuentra en Norteamérica, Europa o Asia Pacífico pueden usar este parámetro. eDiscovery (Premium) se recomienda para _los inquilinos_ cuya ubicación _geográfica aprovisionada principal_ no está en Norteamérica, Europa o Asia Pacífico y que necesitan realizar eDiscovery en ubicaciones _de geografía satélite_.

El administrador global de Microsoft 365 debe asignar permisos de administrador de exhibición de documentos electrónicos para permitir que otros usuarios realicen eDiscovery y asignen un parámetro "Region" en su filtro de seguridad de cumplimiento aplicable para _especificar geography para_ llevar a cabo eDiscovery como ubicación _de geografía satélite_ ; de lo contrario, no se llevará a cabo ninguna eDiscovery para la ubicación _de Geografía satélite_ . Solo se admite un filtro de seguridad "Región" por usuario.

Cuando se establece el rol administrador o administrador de eDiscovery para una ubicación de _geografía satélite_ determinada, el administrador o administrador de exhibición de documentos electrónicos solo podrá realizar acciones de búsqueda de exhibición de documentos electrónicos en los sitios de SharePoint y los sitios de OneDrive ubicados en esa ubicación _de Geografía satélite_ . Si un administrador o administrador de eDiscovery intenta buscar sitios de SharePoint o OneDrive fuera de la ubicación _de geografía satélite_ especificada, no se devolverá ningún resultado. Además, cuando el Administrador de eDiscovery o el administrador de una ubicación _de geografía satélite_ desencadenan una exportación, los datos se exportan a la instancia de Azure de esa región. Esto ayuda a las organizaciones a mantenerse en cumplimiento al no permitir que el contenido se exporte entre fronteras controladas.

> [!NOTE]
> Si es necesario que un Administrador de exhibición de documentos electrónicos busque en varias ubicaciones de Geografía _satélite_ de SharePoint, tendrá que crear otra cuenta de usuario para el Administrador de exhibición de documentos electrónicos, que especifica la ubicación _geográfica satélite_ alternativa donde se encuentran los sitios de OneDrive o SharePoint.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Para establecer el filtro de seguridad de cumplimiento para una región:

1. [Conexión a PowerShell de cumplimiento de & seguridad de Microsoft 365](/powershell/exchange/connect-to-scc-powershell)

2. Use la sintaxis que se muestre a continuación:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Por ejemplo:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Vea el articulo [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) para obtener más parámetros y sintaxis.
