---
title: Función FileProfile() en búsqueda avanzada para Microsoft Defender para endpoint
description: Obtenga información sobre cómo usar FileProfile() para enriquecer información sobre los archivos de los resultados avanzados de la consulta de búsqueda
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, ATP de Microsoft Defender, Microsoft Defender para endpoint, Windows Defender, WINDOWS DEFENDER ATP, protección contra amenazas avanzada de Windows Defender, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 668b3fe503268c46e4a1313f0c4cfb8a6a3dd602
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076008"
---
# <a name="fileprofile"></a>FileProfile()

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

La `FileProfile()` función es una función de enriquecimiento en búsqueda [avanzada](advanced-hunting-overview.md) que agrega los siguientes datos a los archivos encontrados por la consulta.

Column | Tipo de datos | Descripción
-|-|-
SHA1 | cadena | SHA-1 del archivo donde fue aplicada la acción registrada
SHA256 | string | SHA-256 del archivo al que se aplicó la acción grabada
MD5 | string | Hash MD5 del archivo al que se aplicó la acción grabada
FileSize | Entero | Tamaño del archivo en bytes
GlobalPrevalence | Entero | Número de instancias de la entidad observadas por Microsoft globalmente
GlobalFirstSeen | datetime | Fecha y hora en que Microsoft observó por primera vez la entidad globalmente
GlobalLastSeen | datetime | Fecha y hora en que Microsoft observó por última vez la entidad globalmente
Firmante | string | Información sobre el firmante del archivo
Emisor | string | Información sobre la entidad emisora de certificados (CA)
SignerHash | string | Valor hash único que identifica el firmante
IsCertificateValid | boolean | Si el certificado usado para firmar el archivo es válido
IsRootSignerMicrosoft | boolean | Indica si el firmante del certificado raíz es Microsoft
IsExecutable | boolean | Si el archivo es un archivo ejecutable portátil (PE)
ThreatName | string | Nombre de detección de cualquier malware u otras amenazas encontradas
Publisher | string | Nombre de la organización que publicó el archivo
SoftwareName | cadena | Nombre del producto de software

## <a name="syntax"></a>Sintaxis

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumentos

- **x** : columna de id. de archivo que se `SHA1` usará: `SHA256` , , o ; función usa si no se `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especifica
- **y:** límite al número de registros que se enriquecerán, de 1 a 1000; función usa 100 si no se especifica

## <a name="examples"></a>Ejemplos

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Proyecte solo la columna SHA1 y enriquezcala

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
- [Entender el esquema](advanced-hunting-schema-reference.md)
