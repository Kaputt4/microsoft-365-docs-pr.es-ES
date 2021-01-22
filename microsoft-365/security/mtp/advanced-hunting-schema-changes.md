---
title: Cambios de nomenclatura en el esquema de búsqueda avanzada de Microsoft 365 Defender
description: Realizar un seguimiento y revisar las tablas y columnas de cambios de nomenclatura en el esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, datos, cambios de nomenclatura, cambiar el nombre, Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932207"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Esquema de búsqueda avanzada: cambios de nomenclatura

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

El [esquema de búsqueda avanzada se](advanced-hunting-schema-tables.md) actualiza periódicamente para agregar nuevas tablas y columnas. En algunos casos, se cambia el nombre de los nombres de las columnas existentes o se reemplazan para mejorar la experiencia del usuario. Consulte este artículo para revisar los cambios de nomenclatura que podrían afectar a las consultas.

Los cambios de nomenclatura se aplican automáticamente a las consultas que se guardan en el centro de seguridad, incluidas las consultas usadas por reglas de detección personalizadas. No es necesario actualizar estas consultas manualmente. Sin embargo, tendrá que actualizar las siguientes consultas:
- Consultas que se ejecutan con la API
- Consultas que se guardan en otro lugar fuera del centro de seguridad

## <a name="december-2020"></a>Diciembre de 2020

| Nombre de tabla | Nombre de columna original | Nombre de columna nueva | Motivo de la modificación
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailAction | EmailAction | Comentarios del cliente |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicy | EmailActionPolicy | Comentarios del cliente |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicyGuid | EmailActionPolicyGuid | Comentarios del cliente |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)