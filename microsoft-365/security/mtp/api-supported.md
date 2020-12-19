---
title: API de Microsoft 365 Defender (versión preliminar) admitidas
description: API de Microsoft 365 Defender (versión preliminar) admitidas
keywords: MTP, API, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719327"
---
# <a name="supported-microsoft-365-defender-apis"></a>API de Microsoft 365 Defender (versión preliminar) admitidas 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="list-of-available-apis"></a>Lista de API disponibles

Artículo | Descripción
-|-
[API de Búsqueda avanzada de amenazas](api-advanced-hunting.md) | Ejecutar consultas de búsqueda avanzada.
[API de incidentes](api-incident.md) | Enumerar y actualizar incidentes, junto con otras tareas prácticas.

### <a name="endpoint-uris"></a>URI de extremo

El URI base para las dos API principales es: https://api.security.microsoft.com . Para obtener un mejor rendimiento, use un servidor más cercano a su ubicación geográfica:

- Estados Unidos: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Reino Unido: api-uk.security.microsoft.com

El acceso a los tokens puede adquirirse https://api.security.microsoft.com .

Todas las API a lo largo de la `/api` ruta de acceso usan el protocolo [OData](https://docs.microsoft.com/odata/overview) ; por ejemplo, https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre las API de Microsoft 365 defender](api-overview.md)
- [Acceso a las API de Microsoft Threat Protection](api-access.md)
- [Obtenga información sobre los límites de API y las licencias](api-terms.md)
- [Descripción de los códigos de error](api-error-codes.md)
