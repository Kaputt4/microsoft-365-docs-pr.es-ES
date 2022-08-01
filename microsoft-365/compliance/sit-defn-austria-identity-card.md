---
title: Definición de entidad de tarjeta de identidad de Austria
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
description: Definición de entidad de tipo de información confidencial de la tarjeta de identidad de Austria.
ms.openlocfilehash: 5a7cae0eabfa179bda83a09dc6a70a3e6e5048a6
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000175"
---
# <a name="austria-identity-card"></a>Documento de identidad de Austria

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

Una combinación de 24 caracteres de letras, dígitos y caracteres especiales

## <a name="pattern"></a>Patrón

24 caracteres:

- 22 letras (sin distinguir mayúsculas de minúsculas), dígitos, barras diagonales inversas, barras diagonales o signos más

- dos letras (no distinguen mayúsculas de minúsculas), dígitos, barras diagonales inversas, barras diagonales, signos más o signos iguales

## <a name="checksum"></a>Suma de comprobación

No aplicable

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_austria_eu_national_id_card` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_austria_eu_national_id_card`.

```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- número de identidad
- national id
- personalausweis republik österreich