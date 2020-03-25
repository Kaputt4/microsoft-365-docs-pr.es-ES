---
title: Tabla AccountInfo en el esquema de búsqueda avanzada
description: Información sobre la cuenta de usuario en la tabla AccountInfo del esquema de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, entidades, evidencia, archivo, dirección IP, dispositivo, equipo, usuario, cuenta
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929533"
---
# <a name="accountinfo"></a>AccountInfo

**Se aplica a:**
- Protección contra amenazas de Microsoft

La `AccountInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las cuentas de usuario obtenidas de varios servicios, incluido Azure Active Directory. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

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
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
