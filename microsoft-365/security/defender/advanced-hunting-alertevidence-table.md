---
title: Tabla AlertEvidence en el esquema de búsqueda avanzada
description: Obtenga información sobre la información asociada con las alertas en la tabla AlertEvidence del esquema de búsqueda avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, entidades, evidencia, archivo, dirección IP, dispositivo, máquina, usuario, cuenta
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c328094c9b9443b4e130ce91d418fa2694e7c402
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190478"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La tabla del esquema de búsqueda avanzada contiene información sobre varias entidades (archivos, direcciones IP, direcciones URL, usuarios o dispositivos) asociadas con alertas de Microsoft Defender para `AlertEvidence` endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender para [](advanced-hunting-overview.md) identity. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `AlertId` | string | Identificador único de alerta. |
| `ServiceSource` | string | Producto o servicio que proporcionó la información de alerta |
| `EntityType` | string | Tipo de objeto, como un archivo, un proceso, un dispositivo o un usuario |
| `EvidenceRole` | string | Cómo la entidad está implicada en una alerta, lo que indica si está afectada o simplemente está relacionada |
| `EvidenceDirection` | string | Indica si la entidad es el origen o el destino de una conexión de red |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | cadena | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo normalmente no se rellena: use la columna SHA1 cuando esté disponible. |
| `FileSize` | int | Tamaño del archivo en bytes |
| `ThreatFamily` | string | Familia de malware en la que el archivo o proceso sospechoso o malintencionado se ha clasificado en |
| `RemoteIP` | cadena | Dirección IP a la que se ha conectado |
| `RemoteUrl` | cadena | La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado. |
| `AccountName` | cadena | Nombre de usuario de la cuenta |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountSid` | string | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | string | Identificador único de la cuenta en Azure Active Directory |
| `AccountUpn` | string | Nombre principal de usuario (UPN) de la cuenta |
| `DeviceId` | string | Identificador único del dispositivo en el servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `LocalIP` | cadena | Dirección IP asignada al dispositivo local usado durante la comunicación |
| `NetworkMessageId` | cadena | Identificador único de correo electrónico, generado por Office 365 |
| `EmailSubject` | cadena | Asunto del correo electrónico. |
| `ApplicationId` | cadena | Identificador único de la aplicación |
| `Application` | string | Aplicación que realizó la acción grabada |
| `ProcessCommandLine` | string | Línea de comandos usada para crear el nuevo proceso |
| `AdditionalFields` | string | Información adicional sobre el evento en formato de matriz JSON |
| `RegistryKey` |string | Clave del Registro a la que se aplicó la acción grabada |
| `RegistryValueName` |string | Nombre del valor del Registro al que se aplicó la acción grabada |
| `RegistryValueData` |string | Datos del valor del Registro al que se aplicó la acción grabada |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
