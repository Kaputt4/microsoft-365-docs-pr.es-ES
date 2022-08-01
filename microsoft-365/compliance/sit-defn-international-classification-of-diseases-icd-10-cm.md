---
title: Definición de entidad de clasificación internacional de enfermedades (ICD-10-CM)
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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial de clasificación internacional de enfermedades (ICD-10-CM).
ms.openlocfilehash: 414ad224f32a6eecb1fe244bdefde12afdc4b006
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999575"
---
# <a name="international-classification-of-diseases-icd-10-cm"></a>Clasificación Internacional de Enfermedades (CIE-10-MC)

## <a name="format"></a>Formato

Dictionary

## <a name="pattern"></a>Patrón

Palabra clave

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- Se encuentra una palabra clave de `Dictionary_icd_10_updated`.
- Se encuentra una palabra clave de `Dictionary_icd_10_codes`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- Se encuentra una palabra clave de `Dictionary_icd_10_ updated`.

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

## <a name="keywords"></a>Palabras clave

Cualquier término del `Dictionary_icd_10_updated` diccionario de palabras clave, que se basa en la [Clasificación Internacional de Enfermedades, Décima Revisión, Modificación Clínica (ICD-10-CM)](https://icd10cmtool.cdc.gov/). Este tipo solo busca el término, no los códigos de seguro.

Cualquier término del `Dictionary_icd_10_codes` diccionario de palabras clave, que se basa en la [Clasificación Internacional de Enfermedades, Décima Revisión, Modificación Clínica (ICD-10-CM)](https://icd10cmtool.cdc.gov/). Este tipo solo busca códigos de seguro, no la descripción.