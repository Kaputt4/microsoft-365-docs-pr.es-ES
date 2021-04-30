---
title: Crear un grupo Microsoft 365 con una ubicación de datos preferida específica
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Obtenga información sobre cómo crear un grupo Microsoft 365 con una ubicación de datos preferida especificada en un entorno multige geográfico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41984dc24e0f30e5e7b7eb0f9672c75b6d65388f
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086829"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a>Crear un grupo Microsoft 365 con una ubicación de datos preferida específica

Cuando los usuarios de un entorno multige geográfico crean un grupo de Microsoft 365, la ubicación de datos preferida (PDL) del grupo se establece automáticamente en la del usuario. Los administradores globales, de SharePoint y de Exchange pueden crear grupos en cualquier región que seleccionen. 

Si necesita crear un grupo con un PDL específico, puede hacerlo desde el Centro de administración de SharePoint o a través del cmdlet New-UnifiedGroup de Exchange Online de Microsoft PowerShell. Al hacerlo, tanto el buzón del grupo como el sitio de SharePoint asociado con el grupo se aprovisionarán en el PDL especificado.

Para crear un grupo Microsoft 365 con la PDL que especifique, vaya al Centro de administración de SharePoint en la ubicación geográfica donde desea crear el sitio de grupo.

Por ejemplo:

Si desea crear un sitio de grupo en su ubicación de Australia, puede ir a https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. Seleccione **+ Crear**.
2. Siga el proceso para crear un sitio de grupo.

El sitio de grupo se aprovisionará en la ubicación geográfica correspondiente al Centro de administración de SharePoint desde el que haya iniciado la solicitud de creación de sitios. 

Usar Exchange PowerShell 

Conéctese a Exchange Online PowerShell y pase el parámetro *-MailBoxRegion* con el código de ubicación geográfica.

Por ejemplo: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Captura de pantalla del cmdlet de PowerShell New-UnifiedGroup con la sintaxis](../media/multi-geo-new-group-with-pdl-powershell.png)

Tenga en cuenta que el aprovisionamiento de sitios de grupo de SharePoint se realiza a petición. El sitio se aprovisionará la primera vez que un propietario o miembro del grupo intente acceder a él.

## <a name="geo-location-codes"></a>Códigos de ubicación geográfica

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Temas relacionados

[Conectarse a Exchange Online mediante PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)
