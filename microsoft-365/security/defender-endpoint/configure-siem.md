---
title: Extraer detecciones a las herramientas SIEM desde Microsoft Defender para endpoint
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0b9ce376736e5f00ee0f6a4f308d783e75052357
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163308"
---
# <a name="pull-detections-to-your-siem-tools"></a>Extraer detecciones a las herramientas SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a>Extraer detecciones mediante herramientas de administración de eventos y información de seguridad (SIEM)

>[!NOTE]
>- [Microsoft Defender para alerta de](alerts.md) extremo se compone de una o más detecciones.
>- [Microsoft Defender para la detección de](api-portal-mapping.md) puntos de conexión se compone del evento sospechoso que se produjo en el dispositivo y sus detalles de alerta relacionados.
>-La API de alertas de punto de conexión de Microsoft Defender es la API más reciente para el consumo de alertas y contiene una lista detallada de pruebas relacionadas para cada alerta. Para obtener más información, vea [Alert methods and properties y](alerts.md) List [alerts](get-alerts.md).

Defender for Endpoint admite las herramientas de administración de eventos y de información de seguridad (SIEM) para extraer detecciones. Defender for Endpoint expone alertas a través de un extremo HTTPS hospedado en Azure. El extremo se puede configurar para extraer detecciones del inquilino de la empresa en Azure Active Directory (AAD) mediante el protocolo de autenticación de OAuth 2.0 para una aplicación de AAD que representa el conector SIEM específico instalado en el entorno.

Defender para endpoint actualmente admite las siguientes herramientas de solución SIEM específicas a través de un modelo de integración SIEM dedicado:

- IBM QRadar
- Micro Focus ArcSight

Otras soluciones SIEM (como Splunk, RSA NetWitness) se admiten a través de un modelo de integración diferente basado en la nueva API de alertas. Para obtener más información, vea la [página Aplicación de partners](https://securitycenter.microsoft.com/interoperability/partners) y seleccione la sección Información de seguridad y análisis para obtener información completa.

Para usar cualquiera de estas herramientas SIEM compatibles, deberá:

- [Habilitar la integración de SIEM en Defender for Endpoint](enable-siem-integration.md)
- Configurar la herramienta SIEM compatible:
     - [Configurar HP ArcSight para extraer Defender para detecciones de puntos de conexión](configure-arcsight.md)
     - Configurar IBM QRadar para extraer Defender para detecciones de puntos de conexión Para obtener más información, vea [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).

Para obtener más información sobre la lista de campos expuestos en la API de detección, vea [Defender for Endpoint Detection fields](api-portal-mapping.md).
