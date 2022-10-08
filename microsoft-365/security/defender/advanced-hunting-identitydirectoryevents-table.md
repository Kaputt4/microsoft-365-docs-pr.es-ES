---
title: Tabla IdentityDirectoryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre el controlador de dominio y los eventos de Active Directory en la tabla IdentityDirectoryEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, IdentityDirectoryEvents, controlador de dominio, Active Directory, Microsoft Defender for Identity, identidades
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
ms.openlocfilehash: be326262ca22b8db117ed380b04f1b5918a2597a
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68062240"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La `IdentityDirectoryEvents` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene eventos que implican un controlador de dominio local que ejecuta Active Directory (AD). Esta tabla captura varios eventos relacionados con la identidad, como los cambios de contraseña, la expiración de contraseñas y los cambios de nombre principal de usuario (UPN). También captura eventos del sistema en el controlador de dominio, como la programación de tareas y la actividad de PowerShell. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada sobre los tipos de eventos (`ActionType` valores) admitidos por una tabla, use la referencia de esquema integrada disponible en Defender for Cloud.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `ActionType` | `string` | Tipo de actividad que desencadenó el evento. Consulte la [referencia de esquema en el portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información. |
| `Application` | `string` | Aplicación que realizó la acción registrada |
| `TargetAccountUpn` | `string` | Nombre principal de usuario (UPN) de la cuenta a la que se aplicó la acción registrada |
| `TargetAccountDisplayName` | `string` | Nombre para mostrar de la cuenta a la que se aplicó la acción registrada |
| `TargetDeviceName` | `string` | Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción registrada |
| `DestinationDeviceName` | `string` | Nombre del dispositivo que ejecuta la aplicación de servidor que procesó la acción registrada |
| `DestinationIPAddress` | `string` | Dirección IP del dispositivo que ejecuta la aplicación de servidor que procesó la acción registrada |
| `DestinationPort` | `string` | Puerto de destino de la actividad |
| `Protocol` | `string` | Protocolo usado durante la comunicación |
| `AccountName` | `string` | Nombre de usuario de la cuenta |
| `AccountDomain` | `string` | Dominio de la cuenta |
| `AccountUpn` | `string` | Nombre principal de usuario (UPN) de la cuenta |
| `AccountSid` | `string` | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | `string` | Identificador único de la cuenta en Azure Active Directory |
| `AccountDisplayName` | `string` | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre determinado o de nombre, una iniciación intermedia y un apellido o apellido. |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN) del dispositivo |
| `IPAddress` | `string` | Dirección IP asignada al dispositivo durante la comunicación |
| `Port` | `string` | Puerto TCP usado durante la comunicación |
| `Location` | `string` | Ciudad, país u otra ubicación geográfica asociada al evento |
| `ISP` | `string` | Proveedor de servicios de Internet asociado a la dirección IP |
| `ReportId` | `long` | Identificador único del evento |
| `AdditionalFields` | `string` | Información adicional sobre la entidad o el evento |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
