---
title: Las API de Microsoft 365 Defender compatibles
description: Las API de Microsoft 365 Defender compatibles
keywords: Microsoft 365 Defender, API, API
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: 71c4586e37f36418320c6baff456f2e9839cb1af
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482833"
---
# <a name="supported-microsoft-365-defender-apis"></a>Las API de Microsoft 365 Defender compatibles 

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
[API de streaming](streaming-api.md) | Envíe eventos y alertas en tiempo real a medida que se producen en un único flujo de datos.

### <a name="endpoint-uris"></a>URI de punto de conexión

El URI base para ambas API principales es: https://api.security.microsoft.com. Para mejorar el rendimiento, use un servidor más cercano a la geolocalización:

- El Estados Unidos: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Reino Unido: api-uk.security.microsoft.com

Los tokens se pueden adquirir accediendo a https://api.security.microsoft.com.

Todas las API a lo largo de la `/api` ruta de acceso usan el protocolo [OData](/odata/overview) ; por ejemplo, https://api.security.microsoft.com/api/incidents.

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [Acceso a las API de Microsoft 365 Defender](api-access.md)
- [API de streaming](../defender-endpoint/raw-data-export.md)
- [Más información sobre los límites de API y las licencias](api-terms.md)
- [Descripción de los códigos de error](api-error-codes.md)
