---
title: Definición de entidad de número de negocio de Australia
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
description: Definición de entidad de tipo de información confidencial de número de negocio de Australia.
ms.openlocfilehash: 5d3b238dc631086be26399e3adf6c4fa2ef0cf99
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999215"
---
# <a name="australia-business-number"></a>Código de identificación fiscal (ABN) de Australia

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

11 dígitos con delimitadores opcionales

## <a name="pattern"></a>Patrón

11 dígitos con delimitadores opcionales:

- dos dígitos
- un guion o espacio opcional
- tres dígitos
- un guion o espacio opcional
- tres dígitos
- un guion o espacio opcional
- tres dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función Func_australian_business_number busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de Keywords_australian_business_number.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función Func_australian_business_number busca contenido que coincida con el patrón.

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Palabras clave

### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- australia business no
- número de negocio
- Abn #
- businessid #
- id. de negocio
- Abn
- businessno #