---
title: Integración de las herramientas SIEM con Microsoft 365 Defender
description: Obtenga información sobre cómo usar la API REST y configurar las herramientas de administración de eventos e información de seguridad admitidas para recibir y extraer detecciones.
keywords: configurar siem, herramientas de administración de eventos e información de seguridad, splunk, arcsight, indicadores personalizados, API rest, definiciones de alertas, indicadores de riesgo
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
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.openlocfilehash: 06ea5fad75bf1eb004d6e6a50c6a08a29934ec16
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68643919"
---
# <a name="integrate-your-siem-tools-with-microsoft-365-defender"></a>Integración de las herramientas SIEM con Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="pull-microsoft-365-defender-incidents-and-streaming-event-data-using-security-information-and-events-management-siem-tools"></a>Extracción de Microsoft 365 Defender incidentes y datos de eventos de streaming mediante herramientas de administración de eventos e información de seguridad (SIEM)

> [!NOTE]
>
> - [Microsoft 365 Defender Incidentes](incident-queue.md) consta de colecciones de alertas correlacionadas y sus pruebas.
> - [Microsoft 365 Defender Streaming API](streaming-api.md) transmite datos de eventos de Microsoft 365 Defender a centros de eventos o cuentas de Almacenamiento de Azure.

Microsoft 365 Defender admite herramientas de administración de eventos e información de seguridad (SIEM) que ingieren información del inquilino empresarial en Azure Active Directory (AAD) mediante el protocolo de autenticación de OAuth 2.0 para una aplicación de AAD registrada que represente la solución o conector SIEM específica instalada en su entorno. 

Para obtener más información, consulte:

- [licencia y términos de uso de las API de Microsoft 365 Defender](api-terms.md)
- [Acceso a las API de Microsoft 365 Defender](api-access.md)
- [Hola mundo, ejemplo](api-hello-world.md)
- [Obtener acceso con el contexto de la aplicación](api-create-app-web.md)

Hay dos modelos principales para ingerir información de seguridad: 

1.  Ingerir Microsoft 365 Defender incidentes y sus alertas independientes de una API REST en Azure. 

2.  Ingerir datos de eventos de streaming a través de Azure Event Hubs o cuentas de Azure Storage. 

Microsoft 365 Defender admite actualmente las siguientes integraciones de soluciones SIEM: 

- [Ingesta de incidentes desde la API REST de incidentes](#ingesting-incidents-from-the-incidents-rest-api)
- [Ingesta de datos de eventos de streaming a través del centro de eventos](#ingesting-streaming-event-data-via-event-hubs)

## <a name="ingesting-incidents-from-the-incidents-rest-api"></a>Ingesta de incidentes desde la API REST de incidentes

### <a name="incident-schema"></a>Esquema de incidentes
Para obtener más información sobre Microsoft 365 Defender propiedades de incidentes, incluidos los metadatos de entidades de alerta y evidencia contenidas, consulte [Asignación de esquemas](../defender/api-list-incidents.md#schema-mapping).

### <a name="splunk"></a>Splunk

Usar el nuevo complemento Splunk totalmente compatible con Microsoft Security que admite:

- Ingerir incidentes que contienen alertas de los siguientes productos, que se asignan al modelo de información común (CIM) de Splunk:

  - Microsoft 365 Defender
  - Microsoft Defender para punto de conexión
  - Microsoft Defender for Identity y Azure Active Directory Identity Protection
  - Microsoft Defender for Cloud Apps

- Ingesta de alertas de Defender para punto de conexión (desde el punto de conexión de Azure de Defender para punto de conexión) y actualización de estas alertas

- La compatibilidad con la actualización de Microsoft 365 Defender incidentes o alertas de Microsoft Defender para punto de conexión y los paneles respectivos se ha movido a la aplicación de Microsoft 365 para Splunk. 

Para obtener más información sobre:

- El complemento Splunk para Microsoft Security, consulte el [complemento de seguridad de Microsoft en Splunkbase](https://splunkbase.splunk.com/app/6207/#/overview).

- La aplicación de Microsoft 365 para Splunk, consulte la [aplicación de Microsoft 365 en Splunkbase](https://splunkbase.splunk.com/app/3786/).

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

El nuevo SmartConnector para Microsoft 365 Defender ingiere incidentes en ArcSight y los asigna a su Common Event Framework (CEF).

Para obtener más información sobre el nuevo ArcSight SmartConnector para Microsoft 365 Defender, consulte [la documentación del producto ArcSight](https://community.microfocus.com/cyberres/productdocs/w/connector-documentation/39246/smartconnector-for-microsoft-365-defender).

SmartConnector reemplaza al anterior FlexConnector por Microsoft Defender para punto de conexión que ha quedado en desuso.
  

## <a name="ingesting-streaming-event-data-via-event-hubs"></a>Ingesta de datos de eventos de streaming a través de Event Hubs

En primer lugar, debe transmitir eventos desde el inquilino de AAD a event hubs o cuenta de Azure Storage. Para obtener más información, consulte [Streaming API](../defender/streaming-api.md).

Para obtener más información sobre los tipos de eventos admitidos por streaming API, consulte [Tipos de eventos de streaming admitidos](../defender/supported-event-types.md).

### <a name="splunk"></a>Splunk

Use el complemento Splunk para Microsoft Cloud Services para ingerir eventos de Azure Event Hubs.  

Para obtener más información sobre el complemento Splunk para Microsoft Cloud Services, consulte el [complemento de Microsoft Cloud Services en Splunkbase](https://splunkbase.splunk.com/app/3110/).
  

### <a name="ibm-qradar"></a>IBM QRadar
>Use el nuevo módulo ibm QRadar Microsoft 365 Defender Device Support Module (DSM) que llama a la [API de streaming de Microsoft 365 Defender](streaming-api.md) que permite ingerir datos de eventos de streaming de productos de Microsoft 365 Defender a través de Event Hubs o una cuenta de Azure Storage. Para obtener más información sobre los tipos de eventos admitidos, vea [Tipos de eventos admitidos](supported-event-types.md).
