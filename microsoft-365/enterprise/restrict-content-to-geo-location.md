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
description: En este artículo, obtenga información sobre cómo restringir los sitios de SharePoint a una ubicación geográfica especificada en un entorno multigeográfico.
ms.openlocfilehash: f2a09f177c68d30121c207287e053b2b25405fbc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693690"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a><span data-ttu-id="19285-103">Restringir el contenido del sitio de SharePoint a una ubicación geográfica</span><span class="sxs-lookup"><span data-stu-id="19285-103">Restrict SharePoint site content to a geo location</span></span>

<span data-ttu-id="19285-104">En algunos casos, puede dejar un sitio y el contenido del archivo en la ubicación geográfica donde se creó, impidiendo que se mueva o que se almacene su contenido en otra ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="19285-104">Under some circumstances you may choose to enforce a site and its file content to remain in the geo location where the site was created, either by preventing the site from being moved or by preventing the caching of the site's file content in another geo location.</span></span>

<span data-ttu-id="19285-105">Para ello, use el cmdlet [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) con el parámetro **RestrictedToGeo**.</span><span class="sxs-lookup"><span data-stu-id="19285-105">You can do this by using the [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) cmdlet with the **RestrictedToGeo** parameter.</span></span> <span data-ttu-id="19285-106">Este parámetro tiene un valor predeterminado NULL, pero puede cambiarlo a uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="19285-106">This parameter has a default value of NULL, but you can change it to one of the following:</span></span>

|<span data-ttu-id="19285-107">Restriction</span><span class="sxs-lookup"><span data-stu-id="19285-107">Restriction</span></span>|<span data-ttu-id="19285-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="19285-108">Description</span></span>|
|:----------|:----------|
|<span data-ttu-id="19285-109">NoRestriction</span><span class="sxs-lookup"><span data-stu-id="19285-109">NoRestriction</span></span>|<span data-ttu-id="19285-110">Se puede mover el sitio a otra ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="19285-110">The site can be moved to another geo location.</span></span>|
|<span data-ttu-id="19285-111">BlockMoveOnly</span><span class="sxs-lookup"><span data-stu-id="19285-111">BlockMoveOnly</span></span>|<span data-ttu-id="19285-112">No se puede mover el sitio a otra ubicación geográfica, pero se puede almacenar en caché el contenido de sitio en otras ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="19285-112">Site cannot be moved to another geo location, but site content can be cached in other geo locations.</span></span>|
|<span data-ttu-id="19285-113">BlockFull</span><span class="sxs-lookup"><span data-stu-id="19285-113">BlockFull</span></span>|<span data-ttu-id="19285-114">No se puede mover el sitio a otra ubicación geográfica y el contenido del archivo completo no se almacena en caché en otras ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="19285-114">Site cannot be moved to another geo location, and full file content is not cached in other geo locations.</span></span> <span data-ttu-id="19285-115">El título (recolectado del contenido), el nombre y otras propiedades del archivo todavía pueden almacenarse en caché en otras ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="19285-115">Files' title (harvested from the content), file name, and other properties of the file can still be cached in other geo-locations.</span></span><br><span data-ttu-id="19285-116">El contenido almacenado en el sitio antes de configurarse como BlockFull, puede seguir almacenándose en caché en otras ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="19285-116">Content stored in the site before it was configured to BlockFull, may continue to be cached in other geo locations.</span></span>|

<span data-ttu-id="19285-117">Use la sintaxis que se muestre a continuación:</span><span class="sxs-lookup"><span data-stu-id="19285-117">Use the following syntax:</span></span>

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

<span data-ttu-id="19285-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="19285-118">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`
