---
title: Función FileProfile() en la búsqueda avanzada para Microsoft 365 Defender
description: Obtenga información sobre cómo usar FileProfile() para enriquecer información sobre archivos en los resultados de consulta de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929555"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La función es una función de enriquecimiento en la búsqueda avanzada que agrega los siguientes datos a `FileProfile()` los archivos encontrados por la consulta. [](advanced-hunting-overview.md)

| Columna | Tipo de datos | Descripción |
|------------|-------------|-------------|
| SHA1 | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| SHA256 | string | SHA-256 del archivo al que se aplicó la acción grabada |
| MD5 | string | Hash MD5 del archivo al que se aplicó la acción grabada |
| FileSize | entero | Tamaño del archivo en bytes |
| GlobalPrevalence | entero | Número de instancias de la entidad observadas por Microsoft globalmente |
| GlobalFirstSeen | datetime | Fecha y hora en que Microsoft observó por primera vez la entidad globalmente |
| GlobalLastSeen | datetime | Fecha y hora en que Microsoft observó la entidad por última vez globalmente |
| Firmante | string | Información sobre el firmante del archivo |
| Emisor | string | Información sobre la entidad de certificación (CA) emisora |
| SignerHash | string | Valor hash único que identifica al firmante |
| IsCertificateValid | boolean | Si el certificado usado para firmar el archivo es válido |
| IsRootSignerMicrosoft | boolean | Indica si el firmante del certificado raíz es Microsoft |
| IsExecutable | boolean | Si el archivo es un archivo portable ejecutable (PE) |
| ThreatName | string | Nombre de la detección de cualquier malware u otras amenazas encontradas |
| Publisher | string | Nombre de la organización que publicó el archivo |
| SoftwareName | cadena | Nombre del producto de software |

## <a name="syntax"></a>Sintaxis

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumentos

- **x**: columna de id. de archivo que se usa: `SHA1` , , o ; la función usa si no se `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especifica
- **y:** límite al número de registros que se enriquecerán, de 1 a 1000; usa 100 si no se especifica

## <a name="examples"></a>Ejemplos

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Proyectar solo la columna SHA1 y enriquecer

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
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Obtener más ejemplos de consulta](advanced-hunting-shared-queries.md)
