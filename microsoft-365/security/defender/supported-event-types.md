---
title: Microsoft 365 Defender de eventos de streaming admitidos en la API de streaming de eventos
description: Información sobre qué tipos de eventos de streaming (tablas) son compatibles con la API de streaming
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
ms.openlocfilehash: e8264ccb9e3181f6b58a6206417eb2b842bec6e7
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364801"
---
# <a name="supported-microsoft-365-defender-streaming-event-types-in-event-streaming-api"></a>Tipos Microsoft 365 Defender eventos de streaming admitidos en la API de streaming de eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


La API de streaming de eventos se expande constantemente para admitir más tipos de eventos. Obtén información sobre qué tablas de búsqueda están disponibles en general, actualmente en versión preliminar pública o aún no se admiten. 
**Nuevo: los tipos de eventos de correo electrónico y las tablas ahora son GA**

## <a name="hunting-tables-support-status-in-event-streaming-api"></a>Las tablas de búsqueda admiten el estado en la API de streaming de eventos

La tabla siguiente solo incluye la lista de tablas admitidas en la API de streaming y no incluye todo el esquema AH. Para obtener una lista completa de la API, vea [Learn the schema tables](advanced-hunting-schema-tables.md#learn-the-schema-tables).


| Nombre de tabla | Estado |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | GA |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | GA  |
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


