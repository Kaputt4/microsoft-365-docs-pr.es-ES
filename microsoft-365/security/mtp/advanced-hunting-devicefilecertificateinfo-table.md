---
title: Tabla DeviceFileCertificateInfo en el esquema de búsqueda avanzada
description: Información sobre la firma de archivos en la tabla DeviceFileCertificateInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, firma digital, certificado, firma de archivos DeviceFileCertificateInfo
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 926f129b95e1d9d6b07f56955bdf061884d4340b
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430117"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

La `DeviceFileCertificateInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre los certificados de firma de archivos. En esta tabla se usan los datos obtenidos de las actividades de comprobación de certificados realizadas regularmente en los archivos de los extremos.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único para el equipo en servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `IsSigned` | boolean | Indica si el archivo está firmado |
| `SignatureType` | string | Indica si la información de firma se leyó como contenido insertado en el propio archivo o se lee en un archivo de catálogo externo |
| `Signer` | string | Información sobre el firmante del archivo |
| `SignerHash` | string | Valor hash único que identifica al firmante |
| `Issuer` | string | Información sobre la entidad de certificación (CA) emisora |
| `IssuerHash` | string | Valor hash único que identifica a la entidad emisora de certificados (CA) |
| `CertificateSerialNumber` | string | Identificador del certificado que es único para la entidad de certificación (CA) emisora |
| `CrlDistributionPointUrls` | string |  Matriz JSON donde se muestran las direcciones URL de los recursos compartidos de red que contienen certificados y listas de revocación de certificados (CRL) |
| `CertificateCreationTime` | datetime | Fecha y hora de creación del certificado |
| `CertificateExpirationTime` | datetime | Fecha y hora en que el certificado está configurado para expirar |
| `CertificateCountersignatureTime` | datetime | Fecha y hora en que se contrasignó el certificado |
| `IsTrusted` | boolean | Indica si el archivo es de confianza en función de los resultados de la función WinVerifyTrust, que comprueba si hay información de certificado raíz desconocida, firmas no válidas, certificados revocados y otros atributos cuestionables |
| `IsRootSignerMicrosoft` | boolean | Indica si el firmante del certificado raíz es Microsoft |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y timestamp. | 

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
