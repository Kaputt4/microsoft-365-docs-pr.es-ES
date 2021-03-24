---
title: Tabla DeviceFileCertificateInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la firma de archivos en la tabla DeviceFileCertificateInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, firma digital, certificado, firma de archivos, DeviceFileCertificateInfo
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 00e10c84c4bcb20f2e018bf05033b5b2235fd9ae
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071576"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La `DeviceFileCertificateInfo` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información acerca de los certificados de firma de archivos. En esta tabla se usan los datos obtenidos de las actividades de verificación de certificados que se realizan regularmente en los archivos de los puntos de conexión.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único para el equipo en servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `IsSigned` | boolean | Indica si el archivo está firmado |
| `SignatureType` | string | Indica si la información de firma se leyó como contenido incrustado en el propio archivo o si se leyó desde un archivo de catálogo externo. |
| `Signer` | string | Información sobre el firmante del archivo |
| `SignerHash` | string | Valor hash único que identifica el firmante |
| `Issuer` | string | Información sobre la entidad emisora de certificados (CA) |
| `IssuerHash` | string | Valor hash único que identifica la entidad emisora de certificados (CA) |
| `CertificateSerialNumber` | string | Identificador del certificado que es único para la entidad emisora de certificados (CA) |
| `CrlDistributionPointUrls` | string |  Matriz JSON que enumera las direcciones URL de recursos compartidos de red que contienen certificados y listas de revocación de certificados (CRL) |
| `CertificateCreationTime` | datetime | Fecha y hora en que se creó el certificado |
| `CertificateExpirationTime` | datetime | Fecha y hora en que el certificado está establecido para expirar |
| `CertificateCountersignatureTime` | datetime | Fecha y hora en que se contrasignó el certificado |
| `IsTrusted` | boolean | Indica si el archivo es de confianza en función de los resultados de la función WinVerifyTrust, que busca información de certificado raíz desconocido, firmas no válidas, certificados revocados y otros atributos cuestionables |
| `IsRootSignerMicrosoft` | boolean | Indica si el firmante del certificado raíz es Microsoft |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. | 

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
