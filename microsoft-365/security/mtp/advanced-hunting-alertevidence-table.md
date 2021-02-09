---
title: Tabla AlertEvidence en el esquema de búsqueda avanzada
description: Obtenga información sobre la información asociada a las alertas en la tabla AlertEvidence del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, entidades, evidencia, archivo, dirección IP, dispositivo, máquina, usuario, cuenta
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
ms.openlocfilehash: 7457084d49c5a9fef4ef79abc7702c6b473efcd2
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145306"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La tabla del esquema de búsqueda avanzada contiene información sobre diversas entidades (archivos, direcciones IP, direcciones URL, usuarios o dispositivos) asociadas con alertas de Microsoft Defender para Endpoint, Microsoft Defender para `AlertEvidence` Office 365, Microsoft Cloud App Security y Microsoft Defender para Identidad. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `AlertId` | string | Identificador único de alerta. |
| `ServiceSource` | string | Producto o servicio que proporcionaba la información de alerta |
| `EntityType` | string | Tipo de objeto, como un archivo, un proceso, un dispositivo o un usuario |
| `EvidenceRole` | string | Cómo participa la entidad en una alerta, indicando si está afectada o simplemente relacionada |
| `EvidenceDirection` | string | Indica si la entidad es el origen o el destino de una conexión de red. |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | cadena | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo normalmente no se rellena; use la columna SHA1 cuando esté disponible. |
| `FileSize` | entero | Tamaño del archivo en bytes |
| `ThreatFamily` | string | Familia de malware en la que se ha clasificado el archivo o proceso sospechoso o malintencionado |
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
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
