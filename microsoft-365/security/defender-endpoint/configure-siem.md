---
title: Integrar las herramientas SIEM con Microsoft Defender para endpoint
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
ms.openlocfilehash: 1438e346f693ede4a54eeb7c850a2d8cd4164129
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074527"
---
# <a name="integrate-your-siem-tools-with-microsoft-defender-for-endpoint"></a>Integrar las herramientas SIEM con Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="ingest-alerts-using-security-information-and-events-management-siem-tools"></a>Ingerir alertas con herramientas de administración de eventos y información de seguridad (SIEM)

> [!NOTE]
>
> [Microsoft Defender para alerta de](alerts.md) extremo se compone de uno o varios eventos sospechosos o malintencionados que se produjeron en el dispositivo y sus detalles relacionados. La API de alerta de punto de conexión de Microsoft Defender es la API más reciente para el consumo de alertas y contiene una lista detallada de pruebas relacionadas para cada alerta. Para obtener más información, vea [Alert methods and properties y](alerts.md) List [alerts](get-alerts.md).

Microsoft Defender para endpoint admite la información de seguridad y las herramientas de administración de eventos (SIEM) que ingieren información del inquilino empresarial en Azure Active Directory (AAD) mediante el protocolo de autenticación OAuth 2.0 para una aplicación AAD registrada que represente la solución o conector SIEM específico instalado en el entorno.

Para más información, consulte lo siguiente:

- [Licencia de Microsoft Defender para API de extremo y términos de uso](api-terms-of-use.md) 
- [Acceder a las API de Microsoft Defender para punto de conexión](apis-intro.md)
- [Ejemplo de Hello World (describe cómo registrar una aplicación en Azure Active Directory)](api-hello-world.md)
- [Obtener acceso con el contexto de la aplicación](exposed-apis-create-app-webapp.md)


Microsoft Defender para endpoint admite actualmente las siguientes integraciones de soluciones SIEM: 

- [Ingerir incidentes y alertas de las API de REST de Microsoft 365 Defender y Microsoft Defender para incidentes de punto de conexión y alertas](#ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis)
- [Ingesta de eventos de Microsoft Defender para endpoint desde la API Microsoft 365 Defender streaming de eventos](#ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api)

## <a name="ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis"></a>Ingerir incidentes y alertas de las API de REST de Microsoft 365 Defender y Microsoft Defender para incidentes de punto de conexión y alertas

### <a name="ingesting-incidents-from-the-microsoft-365-defender-incidents-rest-api"></a>Ingerir incidentes desde la API de REST Microsoft 365 Defender incidentes

Para obtener más información sobre la API Microsoft 365 Defender incidentes, vea [incidents methods and properties](../defender/api-incident.md).

### <a name="ingesting-alerts-from-the-microsoft-defender-for-endpoint-alerts-rest-api"></a>Ingerir alertas desde la API de REST de Alertas de Microsoft Defender para extremo

Para obtener más información sobre la API de alertas de Microsoft Defender para puntos de conexión, vea [alerts methods and properties](alerts.md).

## <a name="siem-tool-integration-with-microsoft-defender-for-endpoint"></a>Integración de la herramienta SIEM con Microsoft Defender para endpoint

### <a name="splunk"></a>Splunk

Usar el Microsoft 365 Defender complemento para Splunk que admite:

- Ingesta de alertas de Microsoft Defender para puntos de conexión
- Actualización de alertas en Microsoft Defender para endpoint desde Splunk

Para obtener más información sobre Microsoft 365 Defender complemento para Splunk, vea [splunkbase](https://splunkbase.splunk.com/app/4959/).

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

El nuevo SmartConnector para Microsoft 365 Defender ingiere incidentes que contienen alertas de todos los productos de Microsoft 365 Defender (incluidos los de Microsoft Defender para endpoint) en ArcSight y los asigna a su Marco de eventos comunes (CEF).

Para obtener más información sobre el nuevo ArcSight SmartConnector para Microsoft 365 Defender, consulte [La documentación del producto de ArcSight](https://community.microfocus.com/cyberres/productdocs/w/connector-documentation/39246/smartconnector-for-microsoft-365-defender).

SmartConnector reemplaza el FlexConnector anterior para Microsoft 365 Defender.

### <a name="ibm-qradar"></a>IBM QRadar

>[!NOTE]
>
>La integración de IBM QRadar con Microsoft Defender para endpoint ahora es compatible con el nuevo módulo de soporte de dispositivos (DSM) de Microsoft 365 Defender que llama a la API de streaming de [Microsoft 365 Defender](../defender/streaming-api.md) que permite ingerir datos de eventos de streaming desde Microsoft 365 Defender  productos, incluido Microsoft Defender para Endpoint. Para obtener más información sobre los tipos de eventos admitidos, vea [Supported event types](../defender/supported-event-types.md).
Los nuevos clientes ya no se incorporarán con el anterior módulo de soporte de dispositivos de ATP (DSM) de Microsoft Defender de QRadar y se anima a los clientes existentes a adoptar el nuevo DSM de Microsoft 365 Defender como su único punto de integración con todos los productos Microsoft 365 Defender.

## <a name="ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api"></a>Ingesta de eventos de Microsoft Defender para endpoint desde la API Microsoft 365 Defender streaming de eventos

Microsoft 365 Defender datos de eventos de streaming incluyen alertas y otros eventos de Microsoft Defender para Endpoint y otros productos de Microsoft Defender. Estos eventos pueden transmitirse a una cuenta Azure Storage o a Azure Event Hubs. Splunk e IBM QRadar admiten actualmente el modelo de integración a través de centros de eventos.

Para obtener más información, [vea Microsoft 365 Defender integración siem](../defender/configure-siem-defender.md).
