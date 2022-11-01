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
ms.openlocfilehash: dd7048ea6eba4c8de7a0566c67d6588f395004c6
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68803669"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>Restringir el contenido del sitio de SharePoint a una ubicación geográfica

En determinadas circunstancias, puede optar por exigir que un sitio y su contenido de archivo permanezcan en la ubicación _geográfica_ donde se creó el sitio, ya sea evitando que el sitio se mueva o impidiendo el almacenamiento en caché del contenido del archivo del sitio en otra ubicación _geográfica_ .

Puede realizar esta tarea mediante el cmdlet [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) con el parámetro **RestrictedToGeo** . Este parámetro tiene un valor predeterminado de NULL, pero puede cambiarlo a una de las siguientes restricciones:

|Restriction|Descripción|
|:----------|:----------|
|NoRestriction|El sitio se puede mover a otra ubicación _de Geography_ .|
|BlockMoveOnly|El sitio no se puede mover a otra ubicación _de Geography_ , pero el contenido del sitio se puede almacenar en caché en otras ubicaciones _de Geography_ .|
|BlockFull|El sitio no se puede mover a otra ubicación _de Geography_ y el contenido de archivo completo no se almacena en caché en otras ubicaciones _geography_ . El título de los archivos (cosechados del contenido), el nombre de archivo y otras propiedades del archivo todavía se pueden almacenar en caché en otras ubicaciones _geográficas_ .<br>El contenido almacenado en el sitio antes de configurarse en BlockFull puede seguir almacenado en caché en otras ubicaciones _de Geography_ .|

Use la sintaxis que se muestre a continuación:

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Por ejemplo:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`
