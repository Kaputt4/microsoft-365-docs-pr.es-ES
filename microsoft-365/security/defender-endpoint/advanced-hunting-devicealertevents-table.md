---
title: Tabla DeviceAlertEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de generación de alertas en la tabla DeviceAlertEvents del esquema de búsqueda avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, microsoft defender para el punto de conexión, búsqueda wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, DeviceAlertEvents, alerta, gravedad, categoría
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: f4f6ecdc57d8602f49fb389c741c5e01dc1b41b5
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939655"
---
# <a name="devicealertevents"></a>DeviceAlertEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

La `DeviceAlertEvents` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información sobre alertas en el Centro de seguridad de Microsoft Defender. Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea la referencia de esquema [de búsqueda avanzada](advanced-hunting-schema-reference.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `AlertId` | string | Identificador único de alerta. |
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único del dispositivo en el servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN) del dispositivo |
| `Severity` | cadena | El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta. |
| `Category` | cadena | Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta |
| `Title` | cadena | Título de la alerta. |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `RemoteUrl` | cadena | La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado. |
| `RemoteIP` | cadena | Dirección IP a la que se ha conectado |
| `AttackTechniques` | cadena | MITRE ATT&técnicas de CK asociadas con la actividad que desencadenó la alerta |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las `DeviceName` columnas y `Timestamp` |
| `Table` | cadena | Tabla con el contenido detallado del evento |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
