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
description: En este artículo, obtenga información sobre cómo restringir los sitios de SharePoint a una ubicación geográfica especificada en un entorno multige geográfico.
ms.openlocfilehash: 74255db19b2ecf9b333d33208c63da260b2bd747
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927269"
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