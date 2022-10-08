---
title: Tabla IdentityInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la información de la cuenta de usuario en la tabla IdentityInfo del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: aab05f07855749824a1bb40ef4eb8426a35d610b
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68084911"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La `IdentityInfo` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las cuentas de usuario obtenidas de varios servicios, incluido Azure Active Directory. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!NOTE]
>Se cambió el nombre de esta tabla desde `AccountInfo`. Durante el cambio de nombre, todas las consultas guardadas en el portal se actualizan automáticamente. Compruebe las consultas que ha guardado en otro lugar.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `AccountObjectId` | `string` | Identificador único de la cuenta en Azure AD |
| `AccountUpn` | `string` | Nombre principal de usuario (UPN) de la cuenta |
| `OnPremSid` | `string` | Identificador de seguridad local (SID) de la cuenta |
| `CloudSid` | `string` | Identificador de seguridad en la nube de la cuenta |
| `GivenName` | `string` | Nombre o nombre dados del usuario de la cuenta |
| `Surname` | `string` | Apellido, nombre de familia o apellido del usuario de la cuenta |
| `AccountDisplayName` | `string` | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre determinado o de nombre, una iniciación intermedia y un apellido o apellido. |
| `Department` | `string` | Nombre del departamento al que pertenece el usuario de la cuenta |
| `JobTitle` | `string` | Título del trabajo del usuario de la cuenta |
| `AccountName` | `string` | Nombre de usuario de la cuenta |
| `AccountDomain` | `string` | Dominio de la cuenta |
| `EmailAddress` | `string` | Dirección SMTP de la cuenta |
| `SipProxyAddress` | `string` | Dirección del protocolo de inicio de sesión (SIP) de voz a través de IP (VOIP) de la cuenta |
| `City` | `string` | Ciudad donde se encuentra el usuario de la cuenta |
| `Country` | `string` | País o región donde se encuentra el usuario de la cuenta |
| `IsAccountEnabled` | `boolean` | Indica si la cuenta está habilitada o no |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
