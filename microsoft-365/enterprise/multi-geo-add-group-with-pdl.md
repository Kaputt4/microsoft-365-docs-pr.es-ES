---
title: Creación de un grupo de Microsoft 365 con una ubicación de datos preferida específica
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
ms.localizationpriority: medium
description: Obtenga información sobre cómo crear un grupo de Microsoft 365 con una ubicación de datos preferida especificada en un entorno multigeográfico.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
ms.openlocfilehash: ee2bc775f7274722ad2a59a253d8da8ce6795ce6
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705192"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a>Creación de un grupo de Microsoft 365 con una ubicación de datos preferida específica

Cuando los usuarios de un entorno multigeográfico crean un grupo de Microsoft 365, la ubicación de datos preferida del grupo (PDL) se establece automáticamente en la del usuario. Los administradores globales, de SharePoint y de Exchange pueden crear grupos en cualquier región que seleccionen. 

Si necesita crear un grupo con una PDL específica, puede hacerlo desde el <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">Centro de administración de SharePoint</a> o a través del cmdlet de Microsoft PowerShell Exchange Online New-UnifiedGroup. Al hacerlo, tanto el buzón del grupo como el sitio de SharePoint asociado con el grupo se aprovisionarán en el PDL especificado.

Para crear un grupo de Microsoft 365 con la PDL que especifique, vaya al Centro de <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">administración de SharePoint</a> en la ubicación geográfica donde desea crear el sitio de grupo.

Por ejemplo:

Si desea crear un sitio de grupo en su ubicación de Australia, puede ir a `https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement`

1. Seleccione **+ Crear**.
2. Siga el proceso para crear un sitio de grupo.

El sitio de grupo se aprovisionará en la ubicación geográfica correspondiente al Centro de administración de SharePoint desde el que haya iniciado la solicitud de creación de sitios. 

Usar Exchange PowerShell 

Conéctese a Exchange Online PowerShell y pase el parámetro *-MailBoxRegion* con el código de ubicación geográfica.

Por ejemplo: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Captura de pantalla de New-UnifiedGroup cmdlet de PowerShell con sintaxis.](../media/multi-geo-new-group-with-pdl-powershell.png)

> [!Note]
> El aprovisionamiento de sitios de grupo de SharePoint es a petición. El sitio se aprovisionará la primera vez que un propietario o miembro del grupo intente acceder a él.

## <a name="geo-location-codes"></a>Códigos de ubicación geográfica

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Temas relacionados

[Conectarse a Exchange Online mediante PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

[Creación de grupos con una ubicación de datos preferida específica mediante Graph API](/graph/api/group-post-groups)
