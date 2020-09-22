---
title: Tabla IdentityDirectoryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de controlador de dominio y Active Directory en la tabla IdentityDirectoryEvents del esquema de búsqueda avanzada.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, IdentityDirectoryEvents, controlador de dominio, Active Directory, ATP de Azure, identidades
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
ms.openlocfilehash: 4a698bc0d6a7c1ebadec44357b932e9b56dc0a3c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196850"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La `IdentityDirectoryEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene eventos que implican un controlador de dominio local que ejecuta Active Directory (ad). Esta tabla captura varios eventos relacionados con la identidad, como cambios de contraseña, expiración de contraseñas y cambios de nombre principal de usuario (UPN). También captura eventos del sistema en el controlador de dominio, como la programación de tareas y la actividad de PowerShell. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos ( `ActionType` valores) admitidos por una tabla, use la [referencia de esquema integrada](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponible en el centro de seguridad.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `ActionType` | cadena | Tipo de actividad que ha desencadenado el evento. Consulte la [Referencia del esquema del portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más detalles |
| `Application` | string | Aplicación que realizó la acción grabada |
| `TargetAccountUpn` | string | Nombre principal de usuario (UPN) de la cuenta a la que se aplicó la acción registrada |
| `TargetAccountDisplayName` | string | Nombre para mostrar de la cuenta a la que se aplicó la acción registrada |
| `TargetDeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo al que se aplicó la acción grabada |
| `DestinationDeviceName` | string | Nombre del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada |
| `DestinationIPAddress` | string | Dirección IP del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada |
| `DestinationPort` | string | Puerto de destino de la actividad |
| `Protocol` | string | Protocolo usado durante la comunicación |
| `AccountName` | string | Nombre de usuario de la cuenta |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountUpn` | string | Nombre principal de usuario (UPN) de la cuenta |
| `AccountSid` | string | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | string | Identificador único de la cuenta en Azure AD |
| `AccountDisplayName` | string | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente es una combinación de un nombre determinado o de un nombre, un inicio en el medio y un apellido o un apellido. |
| `DeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo |
| `IPAddress` | string | Dirección IP asignada al dispositivo durante la comunicación |
| `Port` | string | Puerto TCP usado durante la comunicación |
| `Location` | string | Ciudad, país u otra ubicación geográfica asociada con el evento |
| `ISP` | string | Proveedor de servicios de Internet asociado con la dirección IP |
| `ReportId` | largo | Identificador único del evento |
| `AdditionalFields` | string | Información adicional acerca de la entidad o el evento |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
