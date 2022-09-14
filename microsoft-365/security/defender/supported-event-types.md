---
title: Microsoft 365 Defender tipos de eventos de streaming admitidos en Event Streaming API
description: Obtenga información sobre qué tipos de eventos de streaming (tablas) admite la API de streaming.
keywords: exportación de datos sin procesar, Streaming API, API, Event Hubs, Azure Storage, cuenta de almacenamiento, Búsqueda, uso compartido de datos sin procesar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: a8a95e7e7831696189d21037ed87fdd6fd82c722
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67678545"
---
# <a name="supported-microsoft-365-defender-streaming-event-types-in-event-streaming-api"></a>Tipos de eventos de streaming Microsoft 365 Defender admitidos en la API de streaming de eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


Event Streaming API se está expandiendo constantemente para admitir más tipos de eventos. Obtenga información sobre qué tablas de búsqueda están disponibles con carácter general, actualmente en versión preliminar pública o aún no se admiten. 
**Nuevo: Email tipos de eventos o tablas ya están disponibles**

## <a name="hunting-tables-support-status-in-event-streaming-api"></a>Estado de compatibilidad de las tablas de búsqueda en Event Streaming API

La tabla siguiente solo incluye la lista de las tablas admitidas en la API de streaming y no incluye todo el esquema ah. Para obtener una lista completa de la API, consulte [Las tablas de esquema](advanced-hunting-schema-tables.md#learn-the-schema-tables).

| Nombre de tabla | Estado<br>(Comercial) | GCC | GCC High | DoD |
|----|----|----|----|----|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | GA | GA | GA | GA |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | GA | GA | GA | GA |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** |GA | GA | GA | GA |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** |GA | GA | GA | GA |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | GA | GA | GA | GA |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | GA | GA | GA | GA |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | GA | GA | GA | GA |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | GA | GA | GA | GA |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** |GA | GA | GA | GA |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | GA | GA | GA | GA |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | GA | GA | GA | GA |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | GA | GA | GA | GA |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | GA |![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | GA |![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | GA |![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | GA |![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)**|GA|![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)**|GA|![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)**|GA|![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)**|GA|![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|![No](../defender-endpoint/images/svg/check-no.svg)|
