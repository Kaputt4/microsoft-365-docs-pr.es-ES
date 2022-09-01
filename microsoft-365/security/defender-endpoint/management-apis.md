---
title: Introducción a la administración y las API
ms.reviewer: ''
description: Obtenga información sobre las herramientas de administración y las categorías de API en Microsoft Defender para punto de conexión
keywords: onboarding, api, siem, rbac, access, portal, integration, investigation, response, entities, entity, user context, application context, streaming
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
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: 212a21accc314cc9ff235138eeb2784521a32502
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67516508"
---
# <a name="overview-of-management-and-apis"></a>Introducción a la administración y las API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mgt-apis-abovefoldlink)


Defender para punto de conexión admite una amplia variedad de opciones para garantizar que los clientes puedan adoptar fácilmente la plataforma.

Al reconocer que los entornos y estructuras de los clientes pueden variar, Se creó Defender para punto de conexión con flexibilidad y control granular para ajustarse a los distintos requisitos del cliente.

## <a name="endpoint-onboarding-and-portal-access"></a>Incorporación de puntos de conexión y acceso al portal

La incorporación de dispositivos está totalmente integrada en Microsoft Endpoint Manager y Microsoft Intune para dispositivos cliente y Microsoft Defender para dispositivos de servidor, lo que proporciona una experiencia completa de configuración, implementación y supervisión. Además, Microsoft Defender para punto de conexión admite directiva de grupo y otras herramientas de terceros que se usan para la administración de dispositivos.

Defender para punto de conexión proporciona un control específico sobre lo que los usuarios con acceso al portal pueden ver y hacer mediante la flexibilidad del control de acceso basado en rol (RBAC). El modelo RBAC admite todos los tipos de estructura de equipos de seguridad:

- Equipos de seguridad y organizaciones distribuidas globalmente
- Equipos de operaciones de seguridad de modelos en capas
- Divisiones completamente segregadas con equipos únicos centralizados de operaciones de seguridad global

## <a name="available-apis"></a>API disponibles

La solución Microsoft Defender para punto de conexión se basa en una plataforma lista para la integración.

Defender para punto de conexión expone gran parte de sus datos y acciones a través de un conjunto de API mediante programación. Esas API le permitirán automatizar flujos de trabajo e innovar en función de las funcionalidades de Defender para punto de conexión.

:::image type="content" source="images/mdatp-apis.png" alt-text="La API disponible y la integración en Microsoft Defender para punto de conexión" lightbox="images/mdatp-apis.png":::

Las API de Defender para punto de conexión se pueden agrupar en tres:

- API de Microsoft Defender para punto de conexión
- API de streaming de datos sin procesar
- Integración de SIEM

## <a name="microsoft-defender-for-endpoint-apis"></a>API de Microsoft Defender para punto de conexión

Defender for Endpoint ofrece un modelo de API por capas que expone datos y funcionalidades en un modelo estructurado, claro y fácil de usar, expuesto a través de un modelo estándar de autenticación y autorización basado en Azure AD que permite el acceso en contexto de usuarios o aplicaciones SaaS. El modelo de API se diseñó para exponer entidades y funcionalidades de forma coherente.

Vea este vídeo para obtener una introducción rápida a las API de Defender para punto de conexión.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4d73M]

**La API de investigación** expone la riqueza de Defender para punto de conexión: expone entidades calculadas o "perfiladas" (por ejemplo, dispositivos, usuarios y archivos) y eventos discretos (por ejemplo, creación de procesos y creación de archivos) que normalmente describen un comportamiento relacionado con una entidad, lo que permite el acceso a los datos a través de interfaces de investigación que permiten el acceso basado en consultas a los datos. Para obtener más información, consulte [API admitidas](exposed-apis-list.md).

**Response API** expone la capacidad de realizar acciones en el servicio y en los dispositivos, lo que permite a los clientes ingerir indicadores, administrar la configuración, el estado de las alertas, así como realizar acciones de respuesta en dispositivos mediante programación, como aislar dispositivos de la red, archivos de cuarentena y otros.

## <a name="raw-data-streaming-api"></a>API de streaming de datos sin procesar

La API de streaming de datos sin procesar de Defender para punto de conexión proporciona a los clientes la capacidad de enviar eventos y alertas en tiempo real desde sus instancias a medida que se producen dentro de un único flujo de datos, lo que proporciona un mecanismo de entrega de baja latencia y alto rendimiento.

La información de eventos de Defender para punto de conexión se inserta directamente en Azure Storage para la retención de datos a largo plazo o para Azure Event Hubs para su consumo por parte de los servicios de visualización o motores de procesamiento de datos adicionales.

Para obtener más información, consulte [Api de streaming de datos sin procesar](raw-data-export.md).

La nueva API de streaming de Microsoft 365 Defender incluye eventos de correo electrónico y alertas, además de eventos de dispositivo.
Para obtener más información, consulte [Microsoft 365 Defender Streaming API](../defender/streaming-api.md).

## <a name="siem-api"></a>SIEM API

Al habilitar la integración de administración de eventos e información de seguridad (SIEM), permite extraer detecciones de Microsoft 365 Defender mediante la solución SIEM o conectarse directamente a la API REST de detecciones. Esto activa la sección de detalles de acceso al conector SIEM con valores rellenados previamente y se crea una aplicación en el inquilino de Azure Active Directory (Azure AD). 

## <a name="related-topics"></a>Temas relacionados

- [Acceder a las API de Microsoft Defender para punto de conexión](apis-intro.md)
- [API admitidas](exposed-apis-list.md)
- [Oportunidades para asociados técnicos](partner-integration.md)
