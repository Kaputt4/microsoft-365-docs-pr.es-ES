---
title: Definición de entidad de número DE REGON de Polonia
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
description: Definición de entidad de tipo de información confidencial de número REGON de Polonia.
ms.openlocfilehash: 0c7de5f7645154d49a4bf7d8e53daa89ac6df1a5
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000289"
---
# <a name="poland-regon-number"></a>Número REGON de Polonia

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

Número de 9 o 14 dígitos

## <a name="pattern"></a>Patrón

nueve dígitos o número de 14 dígitos:

- nueve dígitos o
- nueve dígitos
- Guión
- cinco dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_polish_regon_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_polish_regon_number`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_polish_regon_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- id. de regon
- número estadístico
- identificador estadístico
- estadística no
- número de regon
- regonid #
- regonno #
- id. de empresa
- companyid #
- companyidno #
- numer statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #