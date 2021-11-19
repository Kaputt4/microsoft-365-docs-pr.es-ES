---
title: Integración de las herramientas SIEM con Microsoft 365 Defender
description: Obtenga información sobre cómo usar la API de REST y configurar las herramientas de administración de eventos y información de seguridad admitidas para recibir y extraer detecciones.
keywords: configure siem, security information and events management tools, splunk, arcsight, custom indicators, rest api, alert definitions, indicators of compromise
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
ms.openlocfilehash: 210705bd3392e4aeeadd815ed8c1840e772f6ad9
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110432"
---
# <a name="integrate-your-siem-tools-with-microsoft-365-defender"></a>Integración de las herramientas SIEM con Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="pull-microsoft-365-defender-incidents-and-streaming-event-data-using-security-information-and-events-management-siem-tools"></a>Extraer Microsoft 365 Defender incidentes y datos de eventos de streaming con herramientas de administración de eventos y información de seguridad (SIEM)

> [!NOTE]
>
> - [Microsoft 365 Defender incidents](incident-queue.md) consta de colecciones de alertas correlacionadas y sus evidencias.
> - [Microsoft 365 Defender LA API de streaming](streaming-api.md) transmite datos de eventos Microsoft 365 Defender a centros de eventos o cuentas de Azure Storage.

Microsoft 365 Defender admite la información de seguridad y las herramientas de administración de eventos (SIEM) que ingieren información del inquilino empresarial en Azure Active Directory (AAD) mediante el protocolo de autenticación OAuth 2.0 para una aplicación AAD registrada que represente la solución o conector SIEM específico instalado en su entorno. 

Para más información, vea:

- [Microsoft 365 Defender licencia de API y términos de uso](api-terms.md)
- [Obtener acceso a Microsoft 365 Defender API de acceso](api-access.md)
- [Hola mundo, ejemplo](api-hello-world.md)
- [Obtener acceso con el contexto de la aplicación](api-create-app-web.md)

Hay dos modelos principales para ingerir información de seguridad: 

1.  Ingerir Microsoft 365 Defender incidentes y sus alertas contenidas desde una API de REST en Azure. 

2.  Ingerir datos de eventos de streaming a través de Azure Event Hubs o Azure Storage cuentas. 

Microsoft 365 Defender admite actualmente las siguientes integraciones de soluciones SIEM: 

- [Ingesta de incidentes desde la API de REST de incidentes](#ingesting-incidents-from-the-incidents-rest-api)
- [Ingesta de datos de eventos de streaming a través del Centro de eventos](#ingesting-streaming-event-data-via-event-hubs)

## <a name="ingesting-incidents-from-the-incidents-rest-api"></a>Ingesta de incidentes desde la API de REST de incidentes

### <a name="incident-schema"></a>Esquema de incidentes
Para obtener más información sobre Microsoft 365 Defender de incidentes incluidos los metadatos de entidades de alerta y evidencia contenidos, vea [Asignación de esquema](../defender/api-list-incidents.md#schema-mapping).

### <a name="splunk"></a>Splunk

Usar el Microsoft 365 Defender complemento para Splunk que admite:

- Ingerir incidentes que contienen alertas de los siguientes productos, que se asignan al modelo de información común (CIM) de Splunk:

  - Microsoft 365 Defender
  - Microsoft Defender para punto de conexión
  - Microsoft Defender para identity and Azure Active Directory identity protection
  - Microsoft Defender for Cloud Apps

- Actualizar incidentes en Microsoft 365 Defender desde Splunk

- Ingerir alertas de Defender para puntos de conexión (desde el punto de conexión de Azure de Defender for Endpoint) y actualizar estas alertas

Para obtener más información sobre Microsoft 365 Defender complemento para Splunk, vea [splunkbase](https://splunkbase.splunk.com/app/4959/).

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

El nuevo SmartConnector para Microsoft 365 Defender incidentes en ArcSight y los asigna a su Marco de eventos comunes (CEF).

Para obtener más información sobre el nuevo ArcSight SmartConnector para Microsoft 365 Defender, consulte [Documentación del producto de ArcSight](https://community.microfocus.com/cyberres/productdocs/w/connector-documentation/39246/smartconnector-for-microsoft-365-defender).

SmartConnector reemplaza al flexconnector anterior para Microsoft Defender para endpoint.
  

## <a name="ingesting-streaming-event-data-via-event-hubs"></a>Ingesta de datos de eventos de streaming a través de centros de eventos

Primero debe transmitir eventos desde el espacio empresarial AAD a los centros de eventos o Azure Storage cuenta. Para obtener más información, vea [Streaming API](../defender/streaming-api.md).

Para obtener más información sobre los tipos de eventos admitidos por la API de streaming, vea [Supported streaming event types](../defender/supported-event-types.md).

### <a name="splunk"></a>Splunk
Use el complemento Splunk para Microsoft Cloud Services para ingerir eventos de Azure Event Hubs.  


Para obtener más información sobre el complemento Splunk para Microsoft Cloud Services, vea [splunkbase](https://splunkbase.splunk.com/app/3110/).
  

### <a name="ibm-qradar"></a>IBM QRadar
>Use el nuevo módulo de soporte de dispositivos (DSM) de IBM QRadar Microsoft 365 Defender que llama a la API de streaming de [Microsoft 365 Defender](streaming-api.md) que permite ingerir datos de eventos de streaming de Microsoft 365 Defender productos. Para obtener más información sobre los tipos de eventos admitidos, vea [Supported event types](supported-event-types.md).
