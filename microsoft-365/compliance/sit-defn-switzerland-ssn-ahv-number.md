---
title: Definición de entidad de número de AHV de SSN de Suiza
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
description: Definición de entidad de tipo de información confidencial de número SSN AHV de Suiza.
ms.openlocfilehash: e06ef00d0d8c919f4506d829899b0f6150394854
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000064"
---
# <a name="switzerland-ssn-ahv-number"></a>Número SSN AHV de Suiza

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

Número de 13 dígitos

## <a name="pattern"></a>Patrón

Número de 13 dígitos:

- tres dígitos: 756
- un punto opcional
- cuatro dígitos
- un punto opcional
- cuatro dígitos
- un punto opcional
- dos dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_swiss_social_security_number_ahv` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_swiss_social_security_number_ahv`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_swiss_social_security_number_ahv` encuentra contenido que coincide con el patrón.

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- Ahv
- Ssn
- pid
- número de seguro
- personalidno #
- social security number
- número de id. personal
- identificación personal no.
- insuranceno #
- uniqueidno #
- identificación única no.
- avs number
- identidad personal sin versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- id. de personal de identificación
- numéro de sécurité sociale