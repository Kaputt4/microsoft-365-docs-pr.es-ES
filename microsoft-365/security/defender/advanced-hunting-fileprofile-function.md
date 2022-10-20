---
title: Función FileProfile() en la búsqueda avanzada de Microsoft 365 Defender
description: Obtenga información sobre cómo usar FileProfile() para enriquecer información sobre los archivos de los resultados de la consulta de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.openlocfilehash: 836b38d5dabd67503b0221bfbe4b811f0ae639bf
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68645811"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La `FileProfile()` función es una función de enriquecimiento en [la búsqueda avanzada](advanced-hunting-overview.md) que agrega los siguientes datos a los archivos encontrados por la consulta.

| Column | Tipo de datos | Descripción |
|------------|---------------|-------------|
| `SHA1` | `string` | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | `string` | SHA-256 del archivo al que se aplicó la acción registrada |
| `MD5` | `string` | Hash MD5 del archivo al que se aplicó la acción registrada |
| `FileSize` | `int` | Tamaño del archivo en bytes |
| `GlobalPrevalence` | `int` | Número de instancias de la entidad observadas por Microsoft globalmente |
| `GlobalFirstSeen` | `datetime` | Fecha y hora en que Microsoft observó por primera vez la entidad globalmente |
| `GlobalLastSeen` | `datetime` | Fecha y hora en que Microsoft observó por última vez la entidad globalmente |
| `Signer` | `string` | Información sobre el firmante del archivo |
| `Issuer` | `string` | Información sobre la entidad de certificación (CA) emisora |
| `SignerHash` | `string` | Valor hash único que identifica el firmante |
| `IsCertificateValid` | `boolean` | Si el certificado usado para firmar el archivo es válido |
| `IsRootSignerMicrosoft` | `boolean` | Indica si el firmante del certificado raíz es Microsoft y el archivo está integrado en el sistema operativo Windows. |
| `SignatureState` | `string` | Estado de la firma del archivo: SignedValid: el archivo está firmado con una firma válida, SignedInvalid: el archivo está firmado, pero el certificado no es válido, No firmado: el archivo no está firmado, Desconocido: no se puede recuperar la información sobre el archivo.
| `IsExecutable` | `boolean` | Si el archivo es un archivo ejecutable portátil (PE) |
| `ThreatName` | `string` | Nombre de detección de cualquier malware u otras amenazas encontradas |
| `Publisher` | `string` | Nombre de la organización que publicó el archivo |
| `SoftwareName` | `string` | Nombre del producto de software |

## <a name="syntax"></a>Sintaxis

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumentos

- **x**: columna de identificador de archivo que se va a usar: `SHA1`, `SHA256`, `InitiatingProcessSHA1`o `InitiatingProcessSHA256`; la función usa `SHA1` si no se especifica
- **y**: limite al número de registros que se enriquecerán, 1-1000; la función usa 100 si no se especifica


>[!TIP]
> Las funciones de enriquecimiento solo mostrarán información complementaria cuando estén disponibles. La disponibilidad de la información es variada y depende de muchos factores. Asegúrese de tener en cuenta esto al usar FileProfile() en las consultas o al crear detecciones personalizadas. Para obtener los mejores resultados, se recomienda usar la función FileProfile() con SHA1.

## <a name="examples"></a>Ejemplos

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Proyectar solo la columna SHA1 y enriquecerla

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Enriquecer los primeros 500 registros y enumerar los archivos de baja prevalencia

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
