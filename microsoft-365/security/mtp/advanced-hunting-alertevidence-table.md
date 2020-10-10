---
title: Tabla AlertEvidence en el esquema de búsqueda avanzada
description: Información relacionada con las alertas en la tabla AlertEvidence del esquema de búsqueda avanzada
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ec6fe3d080efb396ce0ecacadd3d5d9a8fa9f8d1
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413203"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

La `AlertEvidence` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre diversas entidades (archivos, direcciones IP, direcciones URL, usuarios o dispositivos) asociadas con alertas de ATP de Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `AlertId` | string | Identificador único de alerta. |
| `ServiceSource` | string | Producto o servicio que ha proporcionado la información de alerta |
| `EntityType` | string | Tipo de objeto, como un archivo, un proceso, un dispositivo o un usuario |
| `EvidenceRole` | string | Cómo interviene la entidad en una alerta, lo que indica si se ve afectada o si simplemente está relacionada. |
| `EvidenceDirection` | string | Indica si la entidad es el origen o el destino de una conexión de red. |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | cadena | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele rellenarse; use la columna SHA1 cuando esté disponible. |
| `FileSize` | entero | Tamaño del archivo en bytes |
| `ThreatFamily` | string | Familia de malware en la que el archivo o proceso malintencionado se clasificó en |
| `RemoteIP` | cadena | Dirección IP a la que se ha conectado |
| `RemoteUrl` | cadena | La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado. |
| `AccountName` | cadena | Nombre de usuario de la cuenta |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountSid` | string | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | string | Identificador único de la cuenta en Azure Active Directory |
| `DeviceId` | string | Identificador único del dispositivo en el servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `LocalIP` | cadena | Dirección IP asignada al dispositivo local que se usa durante la comunicación |
| `NetworkMessageId` | cadena | Identificador único de correo electrónico, generado por Office 365 |
| `EmailSubject` | cadena | Asunto del correo electrónico. |
| `ApplicationId` | cadena | Identificador único de la aplicación |
| `Application` | string | Aplicación que realizó la acción grabada |
| `ProcessCommandLine` | string | Línea de comandos usada para crear el nuevo proceso |
| `AdditionalFields` | string | Información adicional sobre el evento en el formato de matriz JSON |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
