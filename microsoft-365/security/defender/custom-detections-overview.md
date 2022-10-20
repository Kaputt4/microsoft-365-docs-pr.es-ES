---
title: Introducción a las detecciones personalizadas en Microsoft 365 Defender
description: Comprender cómo puede usar la búsqueda avanzada para crear detecciones personalizadas y generar alertas
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m - m365-security - tier2
ms.topic: conceptual
ms.openlocfilehash: 8cf385296243556ce9e131a47e5b00dca42e5864
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68640684"
---
# <a name="custom-detections-overview"></a>Introducción a las detecciones personalizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

Con las detecciones personalizadas, puede supervisar y responder de forma proactiva a diversos eventos y estados del sistema, incluida la actividad de infracción sospechosa y los puntos de conexión mal configurados. Esto es posible gracias a reglas de detección personalizables que desencadenan automáticamente alertas, así como acciones de respuesta.

Las detecciones personalizadas funcionan con [la búsqueda avanzada](advanced-hunting-overview.md), que proporciona un lenguaje de consulta eficaz y flexible que cubre un amplio conjunto de información del sistema y eventos de la red. Puede configurarlas para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.

Las detecciones personalizadas proporcionan:
- Alertas de detecciones basadas en reglas creadas a partir de consultas de búsqueda avanzadas
- Acciones de respuesta automática

## <a name="see-also"></a>Vea también
- [Creación y administración de reglas de detección personalizadas](custom-detection-rules.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión](advanced-hunting-migrate-from-mde.md)
