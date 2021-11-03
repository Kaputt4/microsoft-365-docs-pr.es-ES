---
title: Función FileProfile() en búsqueda avanzada para Microsoft 365 Defender
description: Obtenga información sobre cómo usar FileProfile() para enriquecer información sobre los archivos de los resultados avanzados de la consulta de búsqueda
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c7ad9678f797fd3e8df34b40fe39fea5672e13d5
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60670611"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La `FileProfile()` función es una función de enriquecimiento en búsqueda [avanzada](advanced-hunting-overview.md) que agrega los siguientes datos a los archivos encontrados por la consulta.

| Columna | Tipo de datos | Descripción |
|------------|---------------|-------------|
| `SHA1` | string | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo al que se aplicó la acción grabada |
| `MD5` | cadena | Hash MD5 del archivo al que se aplicó la acción grabada |
| `FileSize` | Entero | Tamaño del archivo en bytes |
| `GlobalPrevalence` | Entero | Número de instancias de la entidad observadas por Microsoft globalmente |
| `GlobalFirstSeen` | datetime | Fecha y hora en que Microsoft observó por primera vez la entidad globalmente |
| `GlobalLastSeen` | datetime | Fecha y hora en que Microsoft observó por última vez la entidad globalmente |
| `Signer` | cadena | Información sobre el firmante del archivo |
| `Issuer` | string | Información sobre la entidad emisora de certificados (CA) |
| `SignerHash` | cadena | Valor hash único que identifica el firmante |
| `IsCertificateValid` | booleano | Si el certificado usado para firmar el archivo es válido |
| `IsRootSignerMicrosoft` | booleano | Indica si el firmante del certificado raíz es Microsoft |
| `SignatureState` | string | Estado de la firma del archivo: SignedValid : el archivo está firmado con una firma válida, SignedInvalid - el archivo está firmado pero el certificado no es válido, No firmado - el archivo no está firmado, Desconocido - la información sobre el archivo no se puede recuperar.
| `IsExecutable` | booleano | Si el archivo es un archivo ejecutable portátil (PE) |
| `ThreatName` | cadena | Nombre de detección de cualquier malware u otras amenazas encontradas |
| `Publisher` | string | Nombre de la organización que publicó el archivo |
| `SoftwareName` | cadena | Nombre del producto de software |

## <a name="syntax"></a>Sintaxis

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumentos

- **x**—columna de id. de archivo para usar: `SHA1` , , o ; función usa si no se `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especifica
- **y**—limite al número de registros que se enriquecerán, de 1 a 1000; función usa 100 si no se especifica


>[!TIP]
> Las funciones de enriquecimiento mostrarán información adicional solo cuando estén disponibles. La disponibilidad de información es variada y depende de muchos factores. Asegúrese de tener esto en cuenta al usar FileProfile() en las consultas o al crear detecciones personalizadas. Para obtener los mejores resultados, se recomienda usar la función FileProfile() con SHA1.

## <a name="examples"></a>Ejemplos

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Project solo la columna SHA1 y enriquecer

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Enriquecer los primeros 500 registros y enumerar archivos de baja prevalencia

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Obtener más ejemplos de consulta](advanced-hunting-shared-queries.md)
