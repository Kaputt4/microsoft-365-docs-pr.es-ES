---
title: Introducción a las API de Microsoft 365 Defender
description: Más información sobre las API disponibles en Microsoft 365 Defender
keywords: api, api, información general, incidente, incidentes, búsqueda de amenazas, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8e06d4b4f7c895b532091c73e8269411fb38bf21
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931007"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Introducción a las API de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información está relacionada con el producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender se basa en una plataforma lista para la integración.

Use las API de Microsoft 365 Defender para automatizar flujos de trabajo basados en las tablas de incidentes compartidos y búsqueda avanzada.

- **[Cola de incidentes combinados:](api-incident.md)** céntrate en lo que es fundamental al agrupar el ámbito de ataque completo y todos los activos afectados en la API de incidentes.

- **[Búsqueda](api-advanced-hunting.md)** de amenazas entre productos: aproveche los conocimientos organizativos de su equipo de seguridad para buscar signos de peligro mediante la creación de sus propias consultas personalizadas para realizar un control de los datos sin procesar recopilados en varios productos de protección.

Junto con estas API específicas de Microsoft 365 Defender, [](api-articles.md) cada uno de nuestros otros productos de seguridad expone API adicionales para ayudarle a aprovechar sus capacidades únicas.

## <a name="learn-more"></a>Más información

| **Comprender cómo obtener acceso a las API** |
|-|
| [Más información sobre las cuotas de API y las licencias](api-terms.md) |
| [Obtener acceso a las API de Microsoft 365 Defender](api-access.md) |
| **Crear aplicaciones** |
| [Crear una aplicación "Hola a todos"](api-hello-world.md) |
| [Crear una aplicación para acceder a las API de Microsoft 365 Defender en nombre de un usuario](api-create-app-user-context.md) |
| [Crear una aplicación para acceder a Microsoft 365 Defender sin un usuario](api-create-app-web.md) |
| [Crear una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender](api-partner-access.md) |
| **Solucionar problemas y mantener las aplicaciones** |
| [Comprender los códigos de error de la API](api-error-codes.md) |
| [Administrar secretos en las aplicaciones con Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementar la autorización de OAuth 2.0 para el inicio de sesión del usuario](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
