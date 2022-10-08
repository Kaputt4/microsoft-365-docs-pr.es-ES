---
title: Información general sobre las API de Microsoft 365 Defender
description: Obtenga información sobre las API disponibles en Microsoft 365 Defender
keywords: api, apis, overview, incident, incidents, threat hunting, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: f90b3b5a1221e7b91e70486b36bed64d50a222c0
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68089085"
---
# <a name="overview-of-microsoft-365-defender-apis"></a>Información general sobre las API de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Microsoft 365 Defender se basa en una plataforma lista para la integración.

Use las API de Microsoft 365 Defender para automatizar los flujos de trabajo en función de los incidentes compartidos y las tablas de búsqueda avanzadas.

- **[Cola de incidentes combinados](api-incident.md)** : céntrese en lo que es crítico mediante la agrupación del ámbito de ataque completo y todos los recursos afectados en la API de incidentes.

- **[Búsqueda de amenazas entre productos](api-advanced-hunting.md)** : aproveche los conocimientos de la organización del equipo de seguridad para buscar signos de peligro mediante la creación de sus propias consultas personalizadas para analizar los datos sin procesar recopilados en varios productos de protección.

- **[API de streaming](streaming-api.md)** de eventos: envía eventos y alertas en tiempo real en un único flujo de datos a medida que se producen.

Junto con estas API específicas de Microsoft 365 Defender, cada uno de nuestros otros productos de seguridad expone [API adicionales](api-articles.md) para ayudarle a aprovechar sus capacidades únicas.

> [!NOTE]
> La transición al portal unificado no debe afectar a los paneles de PowerBi en función de Microsoft Defender para punto de conexión API. Puede seguir trabajando con las API existentes independientemente de la transición del portal interactivo.

Vea este breve vídeo para obtener información sobre cómo puede usar Microsoft 365 Defender para automatizar flujos de trabajo e integrar aplicaciones.  
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M?rel=0]

## <a name="learn-more"></a>Más información

| **Información sobre cómo acceder a las API** |
|-|
| [Más información sobre las cuotas de API y las licencias](api-terms.md) |
| [Acceso a las API de Microsoft 365 Defender](api-access.md) |
| **Crear aplicaciones** |
| [Creación de una aplicación "Hola mundo"](api-hello-world.md) |
| [Creación de una aplicación para acceder a Microsoft 365 Defender API en nombre de un usuario](api-create-app-user-context.md) |
| [Creación de una aplicación para acceder a Microsoft 365 Defender sin un usuario](api-create-app-web.md) |
| [Creación de una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender](api-partner-access.md) |
| **Solución de problemas y mantenimiento de las aplicaciones** |
| [Descripción de los códigos de error de la API](api-error-codes.md) |
| [Administración de secretos en las aplicaciones con Azure Key Vault](/training/modules/manage-secrets-with-azure-key-vault/) |
| [Implementación de la autorización de OAuth 2.0 para el inicio de sesión de usuario](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
