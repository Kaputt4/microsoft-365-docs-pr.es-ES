---
title: Información general sobre la administración y las API
ms.reviewer: ''
description: Obtenga información sobre las herramientas de administración y las categorías de API en ATP de Microsoft Defender
keywords: incorporación, api, siem, rbac, access, portal, integration, investigation, response, entities, entity, user context, application context, streaming
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 94cfe1cc053be896c137e0c0b9ee02ea53dd2717
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187558"
---
# <a name="overview-of-management-and-apis"></a>Información general sobre la administración y las API 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


Defender for Endpoint admite una amplia variedad de opciones para garantizar que los clientes puedan adoptar fácilmente la plataforma. 

Reconociendo que los entornos y estructuras de los clientes pueden variar, Defender for Endpoint se creó con flexibilidad y control pormenorizado para adaptarse a los distintos requisitos del cliente. 

## <a name="endpoint-onboarding-and-portal-access"></a>Incorporación de puntos de conexión y acceso al portal 

La incorporación de dispositivos está totalmente integrada en Microsoft Endpoint Manager y Microsoft Intune para dispositivos cliente y Azure Security Center para dispositivos de servidor, lo que proporciona una experiencia completa de extremo a extremo de configuración, implementación y supervisión. Además, Microsoft Defender para endpoint admite la directiva de grupo y otras herramientas de terceros usadas para la administración de dispositivos.

Defender for Endpoint proporciona un control preciso sobre lo que los usuarios con acceso al portal pueden ver y hacer a través de la flexibilidad del control de acceso basado en roles (RBAC). El modelo RBAC admite todos los sabores de la estructura de los equipos de seguridad:
- Organizaciones distribuidas globalmente y equipos de seguridad
- Equipos de operaciones de seguridad de modelos en niveles
- Divisiones totalmente segregadas con equipos de operaciones de seguridad global centralizados únicos 

## <a name="available-apis"></a>API disponibles
La solución de Microsoft Defender para endpoint se basa en una plataforma lista para la integración.

Defender for Endpoint expone gran parte de sus datos y acciones a través de un conjunto de API programáticas. Estas API le permitirán automatizar flujos de trabajo e innovar en función de las capacidades de Defender para endpoints.

![Imagen de la API e integración disponibles en Microsoft Defender para endpoint](images/mdatp-apis.png)  

Las API de Defender for Endpoint se pueden agrupar en tres:
- Microsoft Defender para api de punto de conexión 
- API de streaming de datos sin procesar
- Integración de SIEM

## <a name="microsoft-defender-for-endpoint-apis"></a>Microsoft Defender para api de punto de conexión

Defender for Endpoint ofrece un modelo de API en capas que expone datos y capacidades en un modelo estructurado, claro y fácil de usar, expuesto a través de un modelo estándar de autenticación y autorización basado en Azure AD que permite el acceso en contexto de usuarios o aplicaciones SaaS. El modelo de API se diseñó para exponer entidades y funcionalidades de forma coherente. 

Vea este vídeo para obtener una introducción rápida a las API de Defender para Endpoint. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

La **API** de investigación expone la riqueza de Defender para endpoint: expone entidades calculadas o "perfiladas" (por ejemplo, dispositivo, usuario y archivo) y eventos discretos (por ejemplo, creación de procesos y creación de archivos) que normalmente describen un comportamiento relacionado con una entidad, lo que habilita el acceso a los datos a través de interfaces de investigación que permiten un acceso basado en consultas a los datos. Para obtener más información, vea [Supported API](exposed-apis-list.md).

La **API** de respuesta expone la capacidad de realizar acciones en el servicio y en los dispositivos, lo que permite a los clientes ingerir indicadores, administrar la configuración, el estado de alerta, así como realizar acciones de respuesta en dispositivos mediante programación, como aislar dispositivos de la red, archivos de cuarentena y otros. 

## <a name="raw-data-streaming-api"></a>API de streaming de datos sin procesar 
La API de streaming de datos sin procesar de Defender for Endpoint ofrece a los clientes la capacidad de enviar eventos y alertas en tiempo real desde sus instancias a medida que se producen en un único flujo de datos, lo que proporciona un mecanismo de entrega de baja latencia y alto rendimiento.

La información del evento Defender for Endpoint se inserta directamente en Azure Storage para la retención de datos a largo plazo, o en Azure Event Hubs para su consumo por parte de servicios de visualización o motores de procesamiento de datos adicionales. 

Para obtener más información, vea [Raw data streaming API](raw-data-export.md).


## <a name="siem-api"></a>SIEM API
Al habilitar la integración de la información de seguridad y la administración de eventos (SIEM), permite extraer detecciones del Centro de seguridad de Microsoft Defender mediante la solución SIEM o mediante la conexión directa a la API rest de detecciones. Esto activa la sección detalles de acceso al conector SIEM con valores rellenados previamente y se crea una aplicación en el inquilino de Azure Active Directory (Azure AD). Para obtener más información, vea [Integración siem](enable-siem-integration.md).

## <a name="related-topics"></a>Temas relacionados
- [Obtener acceso a las API de Microsoft Defender para puntos de conexión ](apis-intro.md)
- [API compatibles](exposed-apis-list.md)
- [Oportunidades de socio técnico](partner-integration.md)

