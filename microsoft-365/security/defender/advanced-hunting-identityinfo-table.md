---
title: Tabla IdentityInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la cuenta de usuario en la tabla IdentityInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AccountInfo, IdentityInfo, cuenta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ce1a3d5153d324d008d2d46048838351eb7bc047
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935826"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La tabla del esquema de búsqueda avanzada contiene información sobre las cuentas de usuario obtenidas de varios `IdentityInfo` servicios, incluido Azure Active Directory. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!NOTE]
>Esta tabla cambió el nombre de `AccountInfo` . Durante los cambios de nombre, todas las consultas guardadas en el portal se actualizan automáticamente. Comprueba las consultas que has guardado en otro lugar.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Identificador único de la cuenta en Azure AD |
| `AccountUpn` | cadena | Nombre principal de usuario (UPN) de la cuenta |
| `OnPremSid` | cadena | Identificador de seguridad local (SID) de la cuenta |
| `CloudSid` | cadena | Identificador de seguridad en la nube de la cuenta |
| `GivenName` | cadena | Nombre o nombre del usuario de la cuenta |
| `Surname` | cadena | Apellidos, apellidos o apellidos del usuario de la cuenta |
| `AccountDisplayName` | cadena | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre o un nombre determinado, un inicio intermedio y un apellido o apellido. |
| `Department` | cadena | Nombre del departamento al que pertenece el usuario de la cuenta |
| `JobTitle` | cadena | Título del trabajo del usuario de la cuenta |
| `AccountName` | cadena | Nombre de usuario de la cuenta |
| `AccountDomain` | cadena | Dominio de la cuenta |
| `EmailAddress` | cadena | Dirección SMTP de la cuenta |
| `SipProxyAddress` | cadena | Dirección del protocolo de inicio de sesión (SIP) de voz sobre IP (VOIP) de la cuenta |
| `City` | cadena | Ciudad donde se encuentra el usuario de la cuenta |
| `Country` | cadena | País o región donde se encuentra el usuario de la cuenta |
| `IsAccountEnabled` | boolean | Indica si la cuenta está habilitada o no |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
