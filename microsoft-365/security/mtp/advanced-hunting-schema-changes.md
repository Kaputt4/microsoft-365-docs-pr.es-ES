---
title: Cambios de nomenclatura en el esquema de búsqueda avanzada de Microsoft 365 Defender
description: Seguimiento y revisión de cambios de nomenclatura en tablas y columnas en el esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, datos, cambios de nomenclatura, cambio de nombre, Protección contra amenazas de Microsoft
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
ms.openlocfilehash: 31a2f647351c05842f36198ad05b149086b53b1f
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509307"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Esquema de búsqueda avanzada: cambios de nomenclatura

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

El [esquema de búsqueda avanzada](advanced-hunting-schema-tables.md) se actualiza regularmente para agregar nuevas tablas y columnas. En algunos casos, los nombres de columnas existentes se renombran o reemplazan para mejorar la experiencia del usuario. Consulte este artículo para revisar los cambios de nomenclatura que podrían afectar a las consultas.

Los cambios de nomenclatura se aplican automáticamente a las consultas que se guardan en el centro de seguridad, incluidas las consultas usadas por las reglas de detección personalizadas. No es necesario actualizar estas consultas manualmente. Sin embargo, deberá actualizar las siguientes consultas:
- Consultas que se ejecutan con la API
- Consultas que se guardan en otro lugar fuera del centro de seguridad

## <a name="december-2020"></a>Diciembre de 2020

| Nombre de tabla | Nombre de columna original | Nuevo nombre de columna | Motivo del cambio
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | Comentarios del cliente |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | Comentarios del cliente |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | Comentarios del cliente |

## <a name="january-2021"></a>Enero de 2021

| Nombre de columna | Nombre del valor original | Nuevo nombre de valor | Motivo del cambio
|--|--|--|--|
| `DetectionSource` | MCAS |    Microsoft Cloud App Security | Rebranding |
| `DetectionSource` | WindowsDefenderAtp|   EDR| Rebranding |
| `DetectionSource` | WindowsDefenderAv | Antivirus | Rebranding |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Rebranding |
| `DetectionSource` | CustomerTI |  TI personalizada | Rebranding |
| `DetectionSource` | OfficeATP | Microsoft Defender para Office 365 | Rebranding |
| `DetectionSource` | MTP   | Microsoft 365 Defender | Rebranding |
| `DetectionSource` | AzureATP |    Microsoft Defender for Identity | Rebranding |
| `DetectionSource` | CustomDetection   | Detección personalizada | Rebranding |
| `DetectionSource` | AutomatedInvestigation |Investigación automatizada | Rebranding |
| `DetectionSource` | ThreatExperts | Expertos en amenazas de Microsoft | Rebranding |
| `DetectionSource` | TI de terceros | Sensores de terceros | Rebranding |
| `ServiceSource` | inquilino dedicado| Microsoft Defender para punto de conexión | Rebranding |
|`ServiceSource` |Protección contra amenazas de Microsoft   | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | ATP de Office 365  |Microsoft Defender para Office 365 | Rebranding |
| `ServiceSource` |Azure ATP    |Microsoft Defender for Identity | Rebranding |

`DetectionSource`está disponible en la [tabla AlertInfo.](advanced-hunting-alertinfo-table.md) `ServiceSource`está disponible en las [tablas AlertEvidence](advanced-hunting-alertevidence-table.md) [y AlertInfo.](advanced-hunting-alertinfo-table.md) 

## <a name="february-2021"></a>Febrero de 2021

1. En las [tablas EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) y [EmailEvents,](advanced-hunting-emailevents-table.md) las columnas y se han `MalwareFilterVerdict` reemplazado por la `PhishFilterVerdict` `ThreatTypes` columna. Las `MalwareDetectionMethod` columnas y también se `PhishDetectionMethod` reemplazaron por la `DetectionMethods` columna. Esta racionalización nos permite proporcionar más información debajo de las nuevas columnas. La asignación se proporciona a continuación.

| Nombre de tabla | Nombre de columna original | Nuevo nombre de columna | Motivo del cambio
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Incluir más métodos de detección |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Incluir más tipos de amenazas |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Incluir más métodos de detección |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Incluir más tipos de amenazas |


2. En las `EmailAttachmentInfo` tablas `EmailEvents` y, la `ThreatNames` columna se agregó para proporcionar más información sobre la amenaza de correo electrónico. Esta columna contiene valores como Correo no deseado o Phish.

3. En la [tabla DeviceInfo,](advanced-hunting-deviceinfo-table.md) la `DeviceObjectId` columna se reemplazó por la `AadDeviceId` columna en función de los comentarios de los clientes.

4. En la [tabla DeviceEvents,](advanced-hunting-deviceevents-table.md) se modificaron varios nombres ActionType para reflejar mejor la descripción de la acción. Los detalles de los cambios se pueden encontrar a continuación.

| Nombre de tabla | Nombre ActionType original | Nuevo nombre actionType | Motivo del cambio
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | Comentarios del cliente |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | Comentarios del cliente |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | Comentarios del cliente |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | Comentarios del cliente |
| `DeviceEvents` | `AntivirusDetection` | `EdrBlock` | Comentarios del cliente |





## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)