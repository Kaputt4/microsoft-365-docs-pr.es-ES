---
title: Tabla AlertEvidence en el esquema de búsqueda avanzada
description: Información sobre archivos, direcciones de red, usuarios o dispositivos asociados con alertas generadas en la tabla AlertEvidence del esquema de búsqueda avanzada
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
ms.openlocfilehash: a0f2ae36752a4415da7c1bc39ce35bd7f744a764
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899356"
---
# <a name="alertevidence"></a>AlertEvidence

**Se aplica a:**
- Protección contra amenazas de Microsoft

La `AlertEvidence` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre diversas entidades (archivos, direcciones IP, direcciones URL, usuarios o dispositivos) asociadas con alertas de ATP de Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `AlertId` | string | Identificador único de alerta. |
| `EntityType` | string | Tipo de objeto, como un archivo, un proceso, un dispositivo o un usuario |
| `EvidenceRole` | string | Cómo interviene la entidad en una alerta, lo que indica si se ve afectada o si simplemente está relacionada. |
| `SHA1` | string | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `RemoteIP` | cadena | Dirección IP a la que se ha conectado |
| `RemoteUrl` | string | La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado. |
| `AccountName` | string | Nombre de usuario de la cuenta |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountSid` | string | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | string | Identificador único de la cuenta en Azure AD |
| `DeviceId` | string | Identificador único para el equipo en servicio |
| `ThreatFamily` | string | Familia de malware en la que el archivo o proceso malintencionado se clasificó en |
| `EvidenceDirection` | string | Indica si la entidad es el origen o el destino de una conexión de red. |
| `AdditionalFields` | string | Información adicional sobre el evento en el formato de matriz JSON |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
