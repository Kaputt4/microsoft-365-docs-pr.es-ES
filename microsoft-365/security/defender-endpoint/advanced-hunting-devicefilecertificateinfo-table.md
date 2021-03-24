---
title: Tabla DeviceFileCertificateInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la firma de archivos en la tabla DeviceFileCertificateInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda de wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, firma digital, certificado, firma de archivos, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: b3b5af8093107925c6c12c901e8138960c5eeaf6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072419"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

La `DeviceFileCertificateInfo` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información acerca de los certificados de firma de archivos. En esta tabla se usan los datos obtenidos de las actividades de verificación de certificados que se realizan regularmente en los archivos de los puntos de conexión.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea la referencia de esquema [de búsqueda avanzada](advanced-hunting-schema-reference.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único del dispositivo en el servicio |
| `DeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo |
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
- [Entender el esquema](advanced-hunting-schema-reference.md)
