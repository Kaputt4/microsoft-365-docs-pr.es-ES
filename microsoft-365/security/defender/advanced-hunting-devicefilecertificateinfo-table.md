---
title: Tabla DeviceFileCertificateInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la información de firma de archivos en la tabla DeviceFileCertificateInfo del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, firma digital, certificado, firma de archivos, DeviceFileCertificateInfo
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
ms.topic: conceptual
ms.openlocfilehash: 694d5dd15dbead030e392f3095c0cc578dc8f85f
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68640904"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

La `DeviceFileCertificateInfo` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre los certificados de firma de archivos. En esta tabla se usan los datos obtenidos de las actividades de comprobación de certificados que se realizan periódicamente en los archivos de los puntos de conexión.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `DeviceId` | `string` | Identificador único para el equipo en servicio |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `SHA1` | `string` | SHA-1 del archivo donde fue aplicada la acción registrada |
| `IsSigned` | `boolean` | Indica si el archivo está firmado |
| `SignatureType` | `string` | Indica si la información de firma se leyó como contenido incrustado en el propio archivo o si se leyó desde un archivo de catálogo externo. |
| `Signer` | `string` | Información sobre el firmante del archivo |
| `SignerHash` | `string` | Valor hash único que identifica el firmante |
| `Issuer` | `string` | Información sobre la entidad de certificación (CA) emisora |
| `IssuerHash` | `string` | Valor hash único que identifica la entidad de certificación emisora (CA) |
| `CertificateSerialNumber` | `string` | Identificador del certificado que es único para la entidad de certificación (CA) emisora. |
| `CrlDistributionPointUrls` | `string` |  Matriz JSON que enumera las direcciones URL de los recursos compartidos de red que contienen certificados y listas de revocación de certificados (CRL) |
| `CertificateCreationTime` | `datetime` | Fecha y hora en que se creó el certificado |
| `CertificateExpirationTime` | `datetime` | Fecha y hora en que el certificado está establecido para expirar |
| `CertificateCountersignatureTime` | `datetime` | Fecha y hora en que se contrasignó el certificado |
| `IsTrusted` | `boolean` | Indica si el archivo es de confianza en función de los resultados de la función WinVerifyTrust, que comprueba si hay información de certificado raíz desconocida, firmas no válidas, certificados revocados y otros atributos cuestionables. |
| `IsRootSignerMicrosoft` | `boolean` | Indica si el firmante del certificado raíz es Microsoft y si el archivo está incluido en el sistema operativo Windows. |
| `ReportId` | `long` | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. | 

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
