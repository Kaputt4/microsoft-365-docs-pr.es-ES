---
title: Introducción a las API de Microsoft 365 Defender
description: Obtenga información sobre las API disponibles en Microsoft 365 Defender
keywords: api, apis, overview, incident, incidents, threat hunting, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 496ad5695d9cd491817bad5daf3c76a02addefd1
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904193"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Introducción a las API de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Microsoft 365 Defender se basa en una plataforma lista para la integración.

Usa las API de Microsoft 365 Defender para automatizar flujos de trabajo basados en el incidente compartido y las tablas avanzadas de búsqueda.

- **[Cola de incidentes combinados:](api-incident.md)** céntrate en lo que es fundamental al agrupar el ámbito de ataque completo y todos los activos afectados en la API de incidentes.

- **[Búsqueda](api-advanced-hunting.md)** de amenazas entre productos: aproveche los conocimientos organizativos de su equipo de seguridad para buscar signos de peligro, mediante la creación de sus propias consultas personalizadas para realizar un control de los datos sin procesar recopilados en varios productos de protección.

Junto con estas API específicas de Microsoft 365 Defender, [](api-articles.md) cada uno de nuestros otros productos de seguridad expone API adicionales para ayudarle a aprovechar sus capacidades únicas.


> [!NOTE]
> La transición al portal unificado no debe afectar a los paneles de PowerBi basados en Microsoft Defender para las API de extremo. Puede seguir trabajando con las API existentes independientemente de la transición del portal interactivo.


## <a name="learn-more"></a>Más información

| **Comprender cómo obtener acceso a las API** |
|-|
| [Más información sobre las cuotas de API y las licencias](api-terms.md) |
| [Obtener acceso a las API de Microsoft 365 Defender](api-access.md) |
| **Crear aplicaciones** |
| [Crear una aplicación "Hello world"](api-hello-world.md) |
| [Crear una aplicación para tener acceso a las API de Microsoft 365 Defender en nombre de un usuario](api-create-app-user-context.md) |
| [Crear una aplicación para tener acceso a Microsoft 365 Defender sin un usuario](api-create-app-web.md) |
| [Crear una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender](api-partner-access.md) |
| **Solucionar problemas y mantener las aplicaciones** |
| [Comprender los códigos de error de la API](api-error-codes.md) |
| [Administrar secretos en las aplicaciones con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementar la autorización de OAuth 2.0 para el inicio de sesión del usuario](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |