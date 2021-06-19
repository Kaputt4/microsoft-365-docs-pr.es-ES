---
title: Introducción a Microsoft 365 Defender API
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
ms.openlocfilehash: 2ca601c3c68df9f9f1cc4fb90bcfbe907850ce91
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029734"
---
# <a name="overview-of-microsoft-365-defender-apis"></a>Introducción a Microsoft 365 Defender API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Microsoft 365 Defender se basa en una plataforma lista para la integración.

Use las API Microsoft 365 Defender para automatizar flujos de trabajo basados en el incidente compartido y las tablas avanzadas de búsqueda.

- **[Cola de incidentes combinados:](api-incident.md)** céntrate en lo que es fundamental al agrupar el ámbito de ataque completo y todos los activos afectados en la API de incidentes.

- **[Búsqueda](api-advanced-hunting.md)** de amenazas entre productos: aproveche los conocimientos organizativos de su equipo de seguridad para buscar signos de peligro, mediante la creación de sus propias consultas personalizadas para realizar un control de los datos sin procesar recopilados en varios productos de protección.

Use la [API de streaming para](../defender-endpoint/raw-data-export.md) enviar alertas y eventos en tiempo real desde instancias a medida que se producen en un único flujo de datos.

Junto con estas API Microsoft 365 Defender específicas, cada uno de [](api-articles.md) nuestros otros productos de seguridad expone API adicionales para ayudarle a aprovechar sus capacidades únicas.

> [!NOTE]
> La transición al portal unificado no debe afectar a los paneles de PowerBi basados en Microsoft Defender para las API de extremo. Puede seguir trabajando con las API existentes independientemente de la transición del portal interactivo.

## <a name="learn-more"></a>Más información

| **Comprender cómo obtener acceso a las API** |
|-|
| [Más información sobre las cuotas de API y las licencias](api-terms.md) |
| [Obtener acceso a Microsoft 365 Defender API de acceso](api-access.md) |
| **Crear aplicaciones** |
| [Crear una aplicación "Hello world"](api-hello-world.md) |
| [Crear una aplicación para obtener acceso Microsoft 365 Defender API en nombre de un usuario](api-create-app-user-context.md) |
| [Crear una aplicación para acceder a Microsoft 365 Defender sin un usuario](api-create-app-web.md) |
| [Crear una aplicación con acceso de asociado multiinquilino a Microsoft 365 Defender API](api-partner-access.md) |
| **Solucionar problemas y mantener las aplicaciones** |
| [Comprender los códigos de error de la API](api-error-codes.md) |
| [Administrar secretos en las aplicaciones con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementar la autorización de OAuth 2.0 para el inicio de sesión del usuario](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |