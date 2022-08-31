---
title: Función SeenBy() en la búsqueda avanzada de Microsoft 365 Defender
description: Obtenga información sobre cómo usar la función SeenBy() para buscar qué dispositivos incorporados detectaron un determinado dispositivo
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, SeenBy, detección de dispositivos, función, enriquecimiento
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
ms.collection: m365-security-compliance
ms.topic: article
ms.openlocfilehash: c44288276431d5a479f47a46289dfaad8089448f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67477195"
---
# <a name="seenby"></a>SeenBy()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La `SeenBy()` función se invoca para ver una lista de dispositivos incorporados que han visto un determinado dispositivo mediante la característica de detección de dispositivos.

Esta función devuelve una tabla que tiene la columna siguiente:

| Column | Tipo de datos | Descripción |
|------------|---------------|-------------|
| `DeviceId` | `string` | Identificador único del dispositivo en el servicio |


## <a name="syntax"></a>Sintaxis

```kusto
invoke SeenBy(x)
```

- donde **x** es el identificador de dispositivo de interés

>[!TIP]
> Las funciones de enriquecimiento solo mostrarán información complementaria cuando estén disponibles. La disponibilidad de la información es variada y depende de muchos factores. Asegúrese de tener en cuenta esto al usar SeenBy() en las consultas o al crear detecciones personalizadas. Para obtener los mejores resultados, se recomienda usar la función SeenBy() con la tabla DeviceInfo.

### <a name="example-obtain-list-of-onboarded-devices-that-have-seen-a-device"></a>Ejemplo: Obtención de una lista de dispositivos incorporados que han visto un dispositivo

```kusto
DeviceInfo 
| where OnboardingStatus <> "Onboarded" 
| limit 100 | invoke SeenBy()
```

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Obtener más ejemplos de consulta](advanced-hunting-shared-queries.md)
