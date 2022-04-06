---
title: Integrar las herramientas SIEM con Pertahanan Microsoft untuk Titik Akhir
description: Obtenga información sobre cómo ingerir incidentes y alertas e integrar herramientas SIEM.
keywords: configure siem, security information and events management tools, splunk, arcsight, custom indicators, rest api, alert definitions, indicators of compromise
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
ms.openlocfilehash: ed88048b506ecfcddb8394667e7d800927fc1d83
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634919"
---
# <a name="integrate-your-siem-tools-with-microsoft-defender-for-endpoint"></a>Integrar las herramientas SIEM con Pertahanan Microsoft untuk Titik Akhir

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="ingest-alerts-using-security-information-and-events-management-siem-tools"></a>Ingerir alertas con herramientas de administración de eventos y información de seguridad (SIEM)

> [!NOTE]
>
> [Pertahanan Microsoft untuk Titik Akhir Alert se](alerts.md) compone de uno o más eventos sospechosos o malintencionados que se produjeron en el dispositivo y sus detalles relacionados. La API Pertahanan Microsoft untuk Titik Akhir alerta es la API más reciente para el consumo de alertas y contiene una lista detallada de evidencia relacionada para cada alerta. Para obtener más información, vea [Alert methods and properties y](alerts.md) [List alerts](get-alerts.md).

Pertahanan Microsoft untuk Titik Akhir admite la información de seguridad y las herramientas de administración de eventos (SIEM) que ingieren información del inquilino de la empresa en Azure Active Directory (AAD) mediante el protocolo de autenticación OAuth 2.0 para un servidor AAD  aplicación que representa la solución o conector SIEM específico instalado en el entorno.

Para más información, vea:

- [Pertahanan Microsoft untuk Titik Akhir licencia de API y términos de uso](api-terms-of-use.md) 
- [Acceder a las API de Microsoft Defender para punto de conexión](apis-intro.md)
- [Hola mundo ejemplo (describe cómo registrar una aplicación en Azure Active Directory)](api-hello-world.md)
- [Obtener acceso con el contexto de la aplicación](exposed-apis-create-app-webapp.md)


Pertahanan Microsoft untuk Titik Akhir admite actualmente las siguientes integraciones de soluciones SIEM: 

- [Ingerir incidentes y alertas de las API de REST Microsoft 365 Defender y Pertahanan Microsoft untuk Titik Akhir y alertas](#ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis)
- [Ingerir Pertahanan Microsoft untuk Titik Akhir eventos de la API Microsoft 365 Defender streaming de eventos](#ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api)

## <a name="ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis"></a>Ingerir incidentes y alertas de las API de REST Microsoft 365 Defender y Pertahanan Microsoft untuk Titik Akhir y alertas

### <a name="ingesting-incidents-from-the-microsoft-365-defender-incidents-rest-api"></a>Ingerir incidentes desde la API de REST Microsoft 365 Defender incidentes

Para obtener más información sobre la API Microsoft 365 Defender incidentes, vea [incidents methods and properties](../defender/api-incident.md).

### <a name="ingesting-alerts-from-the-microsoft-defender-for-endpoint-alerts-rest-api"></a>Ingerir alertas desde la API de REST Pertahanan Microsoft untuk Titik Akhir alertas

Para obtener más información sobre la API Pertahanan Microsoft untuk Titik Akhir alertas, vea [alerts methods and properties](alerts.md).

## <a name="siem-tool-integration-with-microsoft-defender-for-endpoint"></a>Integración de herramientas SIEM con Pertahanan Microsoft untuk Titik Akhir

### <a name="splunk"></a>Splunk

Usar el Microsoft 365 Defender complemento para Splunk que admite:

- Ingesta de Pertahanan Microsoft untuk Titik Akhir alertas
- Actualizar alertas en Pertahanan Microsoft untuk Titik Akhir desde Splunk

Para obtener más información sobre Microsoft 365 Defender complemento para Splunk, vea [splunkbase](https://splunkbase.splunk.com/app/4959/).

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

El nuevo SmartConnector para Microsoft 365 Defender ingiere incidentes que contienen alertas de todos los productos de Microsoft 365 Defender (incluidos los de Pertahanan Microsoft untuk Titik Akhir) en ArcSight y los asigna a su Marco de eventos comunes (CEF).

Para obtener más información sobre el nuevo ArcSight SmartConnector para Microsoft 365 Defender, consulte [La documentación del producto de ArcSight](https://www.microfocus.com/documentation/arcsight/arcsight-smartconnectors/microsoft-365-defender/index.html).

SmartConnector reemplaza al FlexConnector anterior para Microsoft 365 Defender.

### <a name="ibm-qradar"></a>IBM QRadar

>[!NOTE]
>La integración de IBM QRadar con Microsoft 365 Defender, que incluye Pertahanan Microsoft untuk Titik Akhir, ahora es compatible con el nuevo módulo de soporte de dispositivos (DSM) de Microsoft 365 Defender que llama al [Microsoft 365 Defender  API de streaming](../defender/streaming-api.md) que permite ingerir datos de eventos de streaming Microsoft 365 Defender productos, incluidos Pertahanan Microsoft untuk Titik Akhir. Para obtener más información sobre el nuevo Microsoft 365 Defender DSM de QRadar, consulte [Ibm QRadar Product Documentation](https://www.ibm.com/docs/en/dsm?topic=microsoft-365-defender) y, para obtener más información sobre los tipos de eventos compatibles con la API de streaming, consulte [Supported event types](../defender/supported-event-types.md).

Los nuevos clientes ya no se incorporarán con el anterior módulo de soporte de dispositivos de ATP (DSM) de Microsoft Defender de QRadar y se anima a los clientes existentes a adoptar el nuevo DSM de Microsoft 365 Defender como su único punto de integración con todos los productos Microsoft 365 Defender.

## <a name="ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api"></a>Ingerir Pertahanan Microsoft untuk Titik Akhir eventos de la API Microsoft 365 Defender streaming de eventos

Microsoft 365 Defender datos de eventos de streaming incluyen alertas y otros eventos de Pertahanan Microsoft untuk Titik Akhir y otros productos de Microsoft Defender. Estos eventos pueden transmitirse a una cuenta Azure Storage o a Azure Event Hubs. Splunk e IBM QRadar admiten actualmente el modelo de integración a través de centros de eventos.

Para obtener más información, [vea Microsoft 365 Defender integración de SIEM](../defender/configure-siem-defender.md).
