---
title: Microsoft 365 Defender de eventos admitidos en la API de streaming de eventos
description: Información sobre qué tipos de eventos de búsqueda (tablas) son compatibles con la API de streaming
keywords: Exportación de datos sin procesar, API de streaming, API, centros de eventos, almacenamiento de Azure, cuenta de almacenamiento, búsqueda, uso compartido de datos sin procesar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 780cac298206127d52e14b3888a0a8d7f05ae0c5
ms.sourcegitcommit: afee35210f8d68a7f20676ff2a829464b0b0adb2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2021
ms.locfileid: "60216975"
---
# <a name="supported-microsoft-365-defender-event-types-in-event-streaming-api"></a>Tipos Microsoft 365 Defender eventos admitidos en la API de streaming de eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


La API de streaming de eventos se expande constantemente para admitir más tipos de eventos. Obtén información sobre qué tablas de búsqueda están disponibles en general, actualmente en versión preliminar pública o aún no se admiten. 
**Nuevo: los tipos de eventos de correo electrónico y las tablas ahora son GA**

## <a name="hunting-tables-support-status-in-event-streaming-api"></a>Las tablas de búsqueda admiten el estado en la API de streaming de eventos

| Nombre de tabla | Estado |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | GA |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | GA  |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Aún no compatible |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** |GA |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** |GA |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | GA |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | GA |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | GA |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | GA |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** |GA |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | GA |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | GA |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | GA |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | GA |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | GA |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | GA |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | GA |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Aún no compatible |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Aún no compatible |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Aún no compatible |

