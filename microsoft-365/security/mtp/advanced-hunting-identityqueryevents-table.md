---
title: Tabla IdentityQueryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de consulta de Active Directory en la tabla IdentityQueryEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identidades, consultas LDAP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 7016127a75bca48103f5325ce169faa3d7c31c85
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929819"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La tabla del esquema de búsqueda avanzada contiene información sobre las consultas realizadas en objetos de Active Directory, como `IdentityQueryEvents` usuarios, grupos, dispositivos y dominios. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos (valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `ActionType` | cadena | Tipo de actividad que desencadenó el evento. Consulta la [referencia del esquema del portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información |
| `Application` | string | Aplicación que realizó la acción grabada |
| `QueryType` | string | Tipo de consulta, como QueryGroup, QueryUser o EnumerateUsers |
| `QueryTarget` | string | Nombre del usuario, grupo, dispositivo, dominio o cualquier otro tipo de entidad que se esté consultando |
| `Query` | string | Cadena usada para ejecutar la consulta |
| `Protocol` | string | Protocolo usado durante la comunicación |
| `AccountName` | string | Nombre de usuario de la cuenta |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountUpn` | string | Nombre principal de usuario (UPN) de la cuenta |
| `AccountSid` | string | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | string | Identificador único de la cuenta en Azure AD |
| `AccountDisplayName` | string | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre o nombre, una iniciación intermedia y un apellido o apellido. |
| `DeviceName` | string | Nombre de dominio completo (FQDN) del extremo |
| `IPAddress` | string | Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas |
| `DestinationDeviceName` | string | Nombre del dispositivo que ejecuta la aplicación servidor que procesó la acción grabada |
| `DestinationIPAddress` | string | Dirección IP del dispositivo que ejecuta la aplicación servidor que procesó la acción grabada |
| `TargetDeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción grabada |
| `TargetAccountUpn` | string | Nombre principal de usuario (UPN) de la cuenta a la que se aplicó la acción grabada |
| `TargetAccountDisplayName` | string | Nombre para mostrar de la cuenta a la que se aplicó la acción grabada |
| `Location` | string | Ciudad, país u otra ubicación geográfica asociada al evento |
| `ReportId` | largo | Identificador único del evento |
| `AdditionalFields` | string | Información adicional sobre la entidad o el evento |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
