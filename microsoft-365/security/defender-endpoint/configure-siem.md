---
title: Integración de las herramientas siem con Microsoft Defender para punto de conexión
description: Obtenga información sobre cómo ingerir incidentes y alertas e integrar herramientas SIEM.
keywords: configurar siem, herramientas de administración de eventos e información de seguridad, splunk, arcsight, indicadores personalizados, API rest, definiciones de alertas, indicadores de riesgo
search.appverid: met150
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.openlocfilehash: b00a9f02f4cd370985dfa5c094c6be36aa34ab1e
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67679523"
---
# <a name="integrate-your-siem-tools-with-microsoft-defender-for-endpoint"></a>Integración de las herramientas siem con Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="ingest-alerts-using-security-information-and-events-management-siem-tools"></a>Ingesta de alertas mediante herramientas de administración de eventos e información de seguridad (SIEM)

> [!NOTE]
>
> [Microsoft Defender para punto de conexión Alerta](alerts.md) se compone de uno o varios eventos sospechosos o malintencionados que se produjeron en el dispositivo y sus detalles relacionados. La API de alertas de Microsoft Defender para punto de conexión es la API más reciente para el consumo de alertas y contiene una lista detallada de pruebas relacionadas para cada alerta. Para obtener más información, vea [Métodos y propiedades de alerta](alerts.md) y [Lista de alertas](get-alerts.md).

Microsoft Defender para punto de conexión admite herramientas de administración de eventos e información de seguridad (SIEM) que ingieren información del inquilino empresarial en Azure Active Directory (AAD) mediante el protocolo de autenticación de OAuth 2.0 para una aplicación de AAD registrada que represente la solución SIEM o el conector específico instalado en su entorno.

Para obtener más información, consulte:

- [Microsoft Defender para punto de conexión licencia y términos de uso de las API](api-terms-of-use.md) 
- [Acceder a las API de Microsoft Defender para punto de conexión](apis-intro.md)
- [Hola mundo ejemplo (describe cómo registrar una aplicación en Azure Active Directory)](api-hello-world.md)
- [Obtener acceso con el contexto de la aplicación](exposed-apis-create-app-webapp.md)


Microsoft Defender para punto de conexión admite actualmente las siguientes integraciones de soluciones SIEM: 

- [Ingesta de incidentes y alertas desde las API REST de Microsoft 365 Defender y Microsoft Defender para punto de conexión incidentes y alertas](#ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis)
- [Ingesta de eventos Microsoft Defender para punto de conexión desde la API de streaming de eventos de Microsoft 365 Defender](#ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api)

## <a name="ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis"></a>Ingesta de incidentes y alertas desde las API REST de Microsoft 365 Defender y Microsoft Defender para punto de conexión incidentes y alertas

### <a name="ingesting-incidents-from-the-microsoft-365-defender-incidents-rest-api"></a>Ingesta de incidentes desde la API REST de incidentes de Microsoft 365 Defender

Para obtener más información sobre la API de incidentes de Microsoft 365 Defender, consulte [métodos y propiedades de incidentes](../defender/api-incident.md).

### <a name="ingesting-alerts-from-the-microsoft-defender-for-endpoint-alerts-rest-api"></a>Ingesta de alertas desde la API REST de alertas de Microsoft Defender para punto de conexión

Para obtener más información sobre la API de alertas de Microsoft Defender para punto de conexión, consulte [métodos y propiedades de alertas](alerts.md).

## <a name="siem-tool-integration-with-microsoft-defender-for-endpoint"></a>Integración de herramientas SIEM con Microsoft Defender para punto de conexión

### <a name="splunk"></a>Splunk

Uso del complemento Microsoft 365 Defender para Splunk que admite:

- Ingesta de alertas de Microsoft Defender para punto de conexión
- Actualización de alertas en Microsoft Defender para punto de conexión desde Splunk

Para obtener más información sobre el complemento de Microsoft 365 Defender para Splunk, consulte [splunkbase](https://splunkbase.splunk.com/app/4959/).

### <a name="datadog"></a>Datadog

Microsoft 365 Defender para la integración de puntos de conexión con Datadog admite:

- Ingesta Microsoft Defender para punto de conexión alertas e incidentes
- Paneles que habilitan la supervisión de métricas entre puntos de conexión, amenazas y vulnerabilidades y software

Para obtener más información sobre la integración, consulte [Datadog Marketplace](https://app.datadoghq.com/marketplace/app/crest-data-systems-microsoft-defender/support).

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

El nuevo SmartConnector para Microsoft 365 Defender ingiere incidentes que contienen alertas de todos los productos Microsoft 365 Defender ,incluidos los Microsoft Defender para punto de conexión, en ArcSight y los asigna a su Common Event Framework (CEF).

Para obtener más información sobre el nuevo ArcSight SmartConnector para Microsoft 365 Defender, consulte la [documentación del producto ArcSight](https://www.microfocus.com/documentation/arcsight/arcsight-smartconnectors/microsoft-365-defender/index.html).

SmartConnector reemplaza al FlexConnector anterior para Microsoft 365 Defender.

### <a name="ibm-qradar"></a>IBM QRadar

>[!NOTE]
>La integración de IBM QRadar con Microsoft 365 Defender, que incluyen Microsoft Defender para punto de conexión, ahora es compatible con el nuevo módulo de compatibilidad de dispositivos de Microsoft 365 Defender (DSM) que llama al [Microsoft 365 Defender  API de streaming](../defender/streaming-api.md) que permite ingerir datos de eventos de streaming de productos de Microsoft 365 Defender, incluidos Microsoft Defender para punto de conexión. Para obtener más información sobre el nuevo QRadar Microsoft 365 Defender DSM, consulte [la documentación del producto IBM QRadar](https://www.ibm.com/docs/en/dsm?topic=microsoft-365-defender) y para obtener más información sobre los tipos de eventos compatibles con Streaming API, consulte [Tipos de eventos admitidos](../defender/supported-event-types.md).

Los nuevos clientes ya no se incorporan con el módulo de soporte técnico de dispositivos de ATP (DSM) de Microsoft Defender de QRadar anterior, y se recomienda a los clientes existentes que adopten el nuevo Microsoft 365 Defender DSM como su único punto de integración con todos los productos Microsoft 365 Defender.

## <a name="ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api"></a>Ingesta de eventos Microsoft Defender para punto de conexión desde la API de streaming de eventos de Microsoft 365 Defender

Microsoft 365 Defender datos de eventos de streaming incluye alertas y otros eventos de Microsoft Defender para punto de conexión y otros productos de Microsoft Defender. Estos eventos se pueden transmitir a una cuenta de Azure Storage o a Azure Event Hubs. Splunk e IBM QRadar admiten actualmente el modelo de integración a través de event Hubs.

Para obtener más información, consulte [Microsoft 365 Defender integración de SIEM](../defender/configure-siem-defender.md).
