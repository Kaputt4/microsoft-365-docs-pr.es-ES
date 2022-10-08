---
title: Tabla AlertInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de generación de alertas en la tabla AlertInfo del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, gravedad, categoría, MITRE, ATT&CK, Microsoft Defender para punto de conexión, Microsoft Defender para Office 365, Microsoft Defender for Cloud Apps y Microsoft Defender for Identity
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.openlocfilehash: b6dbab2c8537c2fd96a0081210ee28b4db3a12ba
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68064704"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender


## <a name="get-access"></a>Obtener acceso
Para usar la búsqueda avanzada u otras funcionalidades [de Microsoft 365 Defender](microsoft-365-defender.md), necesita un rol adecuado en Azure Active Directory. [Obtenga información sobre los roles y permisos necesarios para la búsqueda avanzada](custom-roles.md).

Además, el acceso a los datos de punto de conexión viene determinado por la configuración del control de acceso basado en rol (RBAC) en Microsoft Defender para punto de conexión. [Obtenga información sobre cómo administrar el acceso a Microsoft 365 Defender](m365d-permissions.md).

## <a name="alertinfo"></a>AlertInfo

La `AlertInfo` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las alertas de Microsoft Defender para punto de conexión, Microsoft Defender para Office 365, Microsoft Defender for Cloud Apps y Microsoft Defender for Identity. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `AlertId` | `string` | Identificador único de alerta. |
| `Title` | `string` | Título de la alerta. |
| `Category` | `string` | Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta |
| `Severity` | `string` | El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta. |
| `ServiceSource` | `string` | Producto o servicio que proporcionó la información de alerta |
| `DetectionSource` | `string` | Tecnología de detección o sensor que identificó el componente o actividad notable |
| `AttackTechniques` | `string` | MITRE ATT&técnicas de CK asociadas a la actividad que desencadenó la alerta |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
