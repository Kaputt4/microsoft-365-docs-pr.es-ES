---
title: Definición de entidad de clasificación internacional de enfermedades (ICD-9-CM)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial de clasificación internacional de enfermedades (ICD-9-CM).
ms.openlocfilehash: f2f482eb951066c0d3bdae084d9082cd8992da8f
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68378300"
---
# <a name="international-classification-of-diseases-icd-9-cm"></a>Clasificación Internacional de Enfermedades (CIE-9-MC)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Dictionary

## <a name="pattern"></a>Patrón

Palabra clave

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- Se encuentra una palabra clave de `Dictionary_icd_9_updated`.
- Se encuentra una palabra clave de `Dictionary_icd_9_codes`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- Se encuentra una palabra clave de `Dictionary_icd_9_updated`.

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

Cualquier término del diccionario de `Dictionary_icd_9_updated` palabras clave, que se basa en la [Clasificación Internacional de Enfermedades,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo solo busca el término, no los códigos de seguro.

Cualquier término del diccionario de `Dictionary_icd_9_codes` palabras clave, que se basa en la [Clasificación Internacional de Enfermedades,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo solo busca códigos de seguro, no la descripción.
