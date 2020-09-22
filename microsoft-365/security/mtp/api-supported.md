---
title: API de Protección contra amenazas de Microsoft compatibles
description: API de Protección contra amenazas de Microsoft compatibles
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
ms.openlocfilehash: fda90945f09abfadfe56ea11469687130d88b2a7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203700"
---
# <a name="supported-microsoft-threat-protection-apis"></a>API de Protección contra amenazas de Microsoft compatibles 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Protección contra amenazas de Microsoft

>[!IMPORTANT] 
>Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.


### <a name="end-point-uris"></a>URI de punto final:

- El URI de la base del servicio es: https://api.security.microsoft.com <br>

>[!NOTE]
>Para obtener un mejor rendimiento, puede usar el servidor más cerca de la ubicación geográfica:
> - api-us.security.microsoft.com
> - api-eu.security.microsoft.com
> - api-uk.security.microsoft.com

 - El recurso para la adquisición de token debe ser: https://api.security.microsoft.com

 - Todas las API de ```/api``` ruta de acceso son API de oData. p.ej. ```https://api.security.microsoft.com/api/incidents```

## <a name="list-of-available-apis"></a>Lista de API disponibles:

Tema | Descripción
:---|:---
[API de Búsqueda avanzada de amenazas](api-advanced-hunting.md) | Ejecutar consultas de búsqueda avanzada desde la API.
[API de incidentes](api-incident.md) | Ejecutar llamadas API relacionadas con incidentes como: enumerar incidentes, actualizar incidente y más.
