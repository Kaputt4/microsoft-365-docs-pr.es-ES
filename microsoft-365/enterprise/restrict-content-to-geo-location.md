---
title: Restringir el contenido del sitio de SharePoint a una ubicación geográfica
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
ms.collection: Strat_SP_gtc
ms.localizationpriority: medium
description: En este artículo, aprenderá a restringir los sitios de SharePoint a una ubicación geográfica especificada en un entorno multigeográfico.
ms.openlocfilehash: 03e1738b88d10717892152655a9e4f3de7a2d847
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67673049"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>Restringir el contenido del sitio de SharePoint a una ubicación geográfica

En determinadas circunstancias, puede optar por aplicar un sitio y su contenido de archivo para que permanezcan en la ubicación geográfica donde se creó el sitio, ya sea evitando que el sitio se mueva o impidiendo el almacenamiento en caché del contenido del archivo del sitio en otra ubicación geográfica.

Puede realizar esta tarea mediante el cmdlet [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) con el parámetro **RestrictedToGeo** . Este parámetro tiene un valor predeterminado de NULL, pero puede cambiarlo a una de las siguientes restricciones:

|Restriction|Descripción|
|:----------|:----------|
|NoRestriction|Se puede mover el sitio a otra ubicación geográfica.|
|BlockMoveOnly|No se puede mover el sitio a otra ubicación geográfica, pero se puede almacenar en caché el contenido de sitio en otras ubicaciones geográficas.|
|BlockFull|No se puede mover el sitio a otra ubicación geográfica y el contenido del archivo completo no se almacena en caché en otras ubicaciones geográficas. El título (recolectado del contenido), el nombre y otras propiedades del archivo todavía pueden almacenarse en caché en otras ubicaciones geográficas.<br>El contenido almacenado en el sitio antes de configurarse como BlockFull, puede seguir almacenándose en caché en otras ubicaciones geográficas.|

Use la sintaxis que se muestre a continuación:

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Por ejemplo:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`
