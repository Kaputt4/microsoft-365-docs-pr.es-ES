---
title: API de Microsoft 365 Defender (versión preliminar) admitidas
description: API de Microsoft 365 Defender (versión preliminar) admitidas
keywords: MTP, API, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b2239b960106d756cbd29504af05af77a553067d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068975"
---
# <a name="supported-microsoft-365-defender-apis"></a>API de Microsoft 365 Defender (versión preliminar) admitidas 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

## <a name="list-of-available-apis"></a>Lista de API disponibles

Artículo | Descripción
-|-
[API de Búsqueda avanzada de amenazas](api-advanced-hunting.md) | Ejecute consultas de búsqueda avanzada.
[API de incidentes](api-incident.md) | Enumerar y actualizar incidentes, junto con otras tareas prácticas.

### <a name="endpoint-uris"></a>URI de extremo

El URI base para ambas API principales es: https://api.security.microsoft.com . Para obtener un mejor rendimiento, use un servidor más cercano a la geolocalización:

- Estados Unidos: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Reino Unido: api-uk.security.microsoft.com

Los tokens se pueden adquirir accediendo https://api.security.microsoft.com a .

Todas las API a lo `/api` largo de la ruta de acceso usan el protocolo [OData;](/odata/overview) por ejemplo, https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [Obtener acceso a las API de Protección contra amenazas de Microsoft](api-access.md)
- [Más información sobre los límites de api y las licencias](api-terms.md)
- [Comprender códigos de error](api-error-codes.md)