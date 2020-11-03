---
title: La función FileProfile () en la búsqueda avanzada de Microsoft 365 defender
description: Obtenga información sobre cómo usar FileProfile () para enriquecer la información sobre los archivos en los resultados de la consulta de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.openlocfilehash: 31959ed146df52aa6568f7aa60617b74ab8dd4db
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847457"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender

La `FileProfile()` función es una función de enriquecimiento de la [búsqueda avanzada](advanced-hunting-overview.md) que agrega los siguientes datos a los archivos encontrados por la consulta.

| Columna | Tipo de datos | Description |
|------------|-------------|-------------|
| SHA1 | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| SHA256 | string | SHA-256 del archivo al que se aplicó la acción grabada |
| MD5 | string | Hash MD5 del archivo al que se aplicó la acción grabada |
| FileSize | entero | Tamaño del archivo en bytes |
| GlobalPrevalence | entero | Número de instancias de la entidad observadas por Microsoft globalmente |
| GlobalFirstSeen | datetime | Fecha y hora en que Microsoft observó por primera vez la entidad |
| GlobalLastSeen | datetime | Fecha y hora en que Microsoft recibió la última observación global de la entidad |
| Firmante | string | Información sobre el firmante del archivo |
| Emisor | string | Información sobre la entidad de certificación (CA) emisora |
| SignerHash | string | Valor hash único que identifica al firmante |
| IsCertificateValid | boolean | Si el certificado usado para firmar el archivo es válido |
| IsRootSignerMicrosoft | boolean | Indica si el firmante del certificado raíz es Microsoft |
| IsExecutable | boolean | Si el archivo es un archivo ejecutable portable (PE) |
| ThreatName | string | Nombre de detección de cualquier malware u otras amenazas encontradas |
| Publisher | string | Nombre de la organización que publicó el archivo |
| SoftwareName | cadena | Nombre del producto de software |

## <a name="syntax"></a>Sintaxis

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumentos

- **x** — columna de identificador de archivo que se debe usar: `SHA1` ,, `SHA256` `InitiatingProcessSHA1` o `InitiatingProcessSHA256` ; la función usa `SHA1` si no se especifica
- **y** : límite para el número de registros para enriquecer, 1-1000; la función usa 100 si no se especifica

## <a name="examples"></a>Ejemplos

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Proyectar sólo la columna SHA1 y enriquecerla

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Enriquezca los primeros 500 registros y enumere los archivos de baja difusión

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
