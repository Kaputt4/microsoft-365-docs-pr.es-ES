---
title: Restringir el contenido del sitio de SharePoint a una ubicación geográfica
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
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: En este artículo, obtenga información sobre cómo restringir SharePoint a una ubicación geográfica especificada en un entorno multige geográfico.
ms.openlocfilehash: 1a10ebe8042f2385fa1fa6d3ff3329bb7c066c424b0cb4135f0a29a186f23dc2
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53904628"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>Restringir el contenido del sitio de SharePoint a una ubicación geográfica

En algunos casos, puede dejar un sitio y el contenido del archivo en la ubicación geográfica donde se creó, impidiendo que se mueva o que se almacene su contenido en otra ubicación geográfica.

Para ello, use el cmdlet [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) con el parámetro **RestrictedToGeo**. Este parámetro tiene un valor predeterminado NULL, pero puede cambiarlo a uno de los siguientes:

|Restriction|Descripción|
|:----------|:----------|
|NoRestriction|Se puede mover el sitio a otra ubicación geográfica.|
|BlockMoveOnly|No se puede mover el sitio a otra ubicación geográfica, pero se puede almacenar en caché el contenido de sitio en otras ubicaciones geográficas.|
|BlockFull|No se puede mover el sitio a otra ubicación geográfica y el contenido del archivo completo no se almacena en caché en otras ubicaciones geográficas. El título (recolectado del contenido), el nombre y otras propiedades del archivo todavía pueden almacenarse en caché en otras ubicaciones geográficas.<br>El contenido almacenado en el sitio antes de configurarse como BlockFull, puede seguir almacenándose en caché en otras ubicaciones geográficas.|

Use la sintaxis que se muestre a continuación:

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Por ejemplo:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`