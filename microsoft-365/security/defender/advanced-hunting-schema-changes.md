---
title: Cambios de nomenclatura en el esquema de búsqueda avanzada de Microsoft 365 Defender
description: Seguimiento y revisión de tablas y columnas de cambios de nomenclatura en el esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, datos, cambios de nomenclatura, cambio de nombre
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
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.openlocfilehash: 41a46fce2c1767dc815006e0c15a0bb9b50a7706
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68622736"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Esquema de búsqueda avanzada: cambios de nomenclatura

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

El [esquema de búsqueda avanzada](advanced-hunting-schema-tables.md) se actualiza periódicamente para agregar nuevas tablas y columnas. En algunos casos, se cambia el nombre de las columnas existentes o se reemplazan para mejorar la experiencia del usuario. Consulte este artículo para revisar los cambios de nomenclatura que podrían afectar a las consultas.

Los cambios de nomenclatura se aplican automáticamente a las consultas que se guardan en Defender for Cloud, incluidas las consultas que usan las reglas de detección personalizadas. No es necesario actualizar estas consultas manualmente. Sin embargo, deberá actualizar las siguientes consultas:
- Consultas que se ejecutan mediante la API
- Consultas que se guardan en otro lugar fuera de Defender for Cloud

## <a name="december-2020"></a>Diciembre de 2020

| Nombre de tabla | Nombre de columna original | Nuevo nombre de columna | Motivo del cambio
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | Comentarios del cliente |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | Comentarios del cliente |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | Comentarios del cliente |

## <a name="january-2021"></a>Enero de 2021

| Nombre de columna | Nombre del valor original | Nuevo nombre de valor | Motivo del cambio
|--|--|--|--|
| `DetectionSource` | Defender for Cloud Apps | Microsoft Defender for Cloud Apps | Rebranding |
| `DetectionSource` | WindowsDefenderAtp| Edr| Rebranding |
| `DetectionSource` | WindowsDefenderAv | Antivirus | Rebranding |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Rebranding |
| `DetectionSource` | CustomerTI | TI personalizado | Rebranding |
| `DetectionSource` | OfficeATP | Microsoft Defender para Office 365 | Rebranding |
| `DetectionSource` | Mtp | Microsoft 365 Defender | Rebranding |
| `DetectionSource` | AzureATP | Microsoft Defender for Identity | Rebranding |
| `DetectionSource` | CustomDetection | Detección personalizada | Rebranding |
| `DetectionSource` | AutomatedInvestigation |Investigación automatizada | Rebranding |
| `DetectionSource` | ThreatExperts | Expertos en amenazas de Microsoft | Rebranding |
| `DetectionSource` | TI de terceros | Sensores de terceros | Rebranding |
| `ServiceSource` | ATP de Microsoft Defender| Microsoft Defender para punto de conexión | Rebranding |
|`ServiceSource` |Protección contra amenazas de Microsoft | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | ATP de Office 365 |Microsoft Defender para Office 365 | Rebranding |
| `ServiceSource` |Azure ATP |Microsoft Defender for Identity | Rebranding |

`DetectionSource` está disponible en la tabla [AlertInfo](advanced-hunting-alertinfo-table.md) . `ServiceSource` está disponible en las tablas [AlertEvidence](advanced-hunting-alertevidence-table.md) y [AlertInfo](advanced-hunting-alertinfo-table.md) . 

## <a name="february-2021"></a>Febrero de 2021

1. En las tablas [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) y [EmailEvents](advanced-hunting-emailevents-table.md) , las `MalwareFilterVerdict`columnas y `PhishFilterVerdict` se han reemplazado por la `ThreatTypes` columna . Las `MalwareDetectionMethod` columnas y `PhishDetectionMethod` también se reemplazaron por la `DetectionMethods` columna . Esta simplificación nos permite proporcionar más información en las nuevas columnas. La asignación se proporciona a continuación.

    | Nombre de tabla | Nombre de columna original | Nuevo nombre de columna | Motivo del cambio
    |--|--|--|--|
    | `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Incluir más métodos de detección |
    | `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Incluir más tipos de amenazas |
    | `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Incluir más métodos de detección |
    | `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Incluir más tipos de amenazas |


2. En las `EmailAttachmentInfo` tablas y `EmailEvents` , se agregó la `ThreatNames` columna para proporcionar más información sobre la amenaza de correo electrónico. Esta columna contiene valores como Spam o Phish.

3. En la tabla [DeviceInfo](advanced-hunting-deviceinfo-table.md) , la `DeviceObjectId` columna se reemplazó por la columna en función de los `AadDeviceId` comentarios del cliente.

4. En la tabla [DeviceEvents](advanced-hunting-deviceevents-table.md) , se modificaron varios nombres ActionType para reflejar mejor la descripción de la acción. Los detalles de los cambios se pueden encontrar a continuación.

    | Nombre de tabla | Nombre original de ActionType | Nuevo nombre de ActionType | Motivo del cambio
    |--|--|--|--|
    | `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | Comentarios del cliente |
    | `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | Comentarios del cliente |
    | `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | Comentarios del cliente |
    | `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | Comentarios del cliente |

## <a name="march-2021"></a>Marzo de 2021

La `DeviceTvmSoftwareInventoryVulnerabilities` tabla ha quedado en desuso. Reemplazarlo son las `DeviceTvmSoftwareInventory` tablas y `DeviceTvmSoftwareVulnerabilities` .

## <a name="may-2021"></a>Mayo de 2021

La `AppFileEvents` tabla ha quedado en desuso. La `CloudAppEvents` tabla incluye información que solía estar en la tabla, junto con otras actividades de servicios en la `AppFileEvents` nube.

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
