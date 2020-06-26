---
title: Tabla IdentityInfo en el esquema de búsqueda avanzada
description: Información sobre la cuenta de usuario en la tabla IdentityInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AccountInfo, IdentityInfo, cuenta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b384e76439ae706520725e7193fa64224b724be0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898962"
---
# <a name="identityinfo"></a>IdentityInfo

**Se aplica a:**
- Protección contra amenazas de Microsoft

La `IdentityInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las cuentas de usuario obtenidas de varios servicios, incluido Azure Active Directory. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!NOTE]
>Se cambió el nombre de esta tabla de `AccountInfo` . Durante el cambio de nombre, se actualizan automáticamente todas las consultas guardadas en el portal. Compruebe las consultas que guardó en otra parte.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Identificador único de la cuenta en Azure AD |
| `AccountUpn` | string | Nombre principal de usuario (UPN) de la cuenta |
| `OnPremSid` | string | Identificador de seguridad local (SID) de la cuenta |
| `CloudSid` | string | Identificador de seguridad en la nube de la cuenta |
| `GivenName` | string | Nombre especificado o nombre del usuario de la cuenta |
| `Surname` | string | Apellidos, apellidos o familia del usuario de la cuenta |
| `AccountDisplayName` | string | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente es una combinación de un nombre determinado o de un nombre, un inicio en el medio y un apellido o un apellido. |
| `Department` | string | Nombre del Departamento al que pertenece el usuario de la cuenta |
| `JobTitle` | string | Puesto del usuario de la cuenta |
| `AccountName` | string | Nombre de usuario de la cuenta |
| `AccountDomain` | string | Dominio de la cuenta |
| `EmailAddress` | string | Dirección SMTP de la cuenta |
| `SipProxyAddress` | string | Voz de la dirección IP (VOIP) protocolo de inicio de sesión (SIP) de la cuenta |
| `City` | string | Ciudad en la que se encuentra el usuario de la cuenta |
| `Country` | string | País o región donde se encuentra el usuario de la cuenta |
| `IsAccountEnabled` | boolean | Indica si la cuenta está habilitada o no. |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
