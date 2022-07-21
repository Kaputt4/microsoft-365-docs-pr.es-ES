---
title: Definición de entidad de impuestos sobre el valor añadido de Austria
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
description: Definición de entidad de tipo de información confidencial sobre el valor añadido de Austria.
ms.openlocfilehash: b4d6841e857d81c42255eec1184e51623f78059f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951127"
---
# <a name="austria-value-added-tax"></a>Impuesto sobre el valor añadido de Austria

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

Patrón alfanumérico de 11 caracteres

## <a name="pattern"></a>Patrón

Patrón alfanumérico de 11 caracteres:

- A o un
- T o t
- Espacio opcional
- U o u
- espacio opcional
- dos o tres dígitos
- espacio opcional
- cuatro dígitos
- espacio opcional
- uno o dos dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función Func_Austria_Value_Added_Tax busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de Keyword_Austria_Value_Added_Tax.

Una directiva DLP tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función Func_Austria_Value_Added_Tax busca contenido que coincida con el patrón.

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Palabras clave

### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- número de iva
- Iva #
- austriaco número de iva
- vat no.
- vatno #
- número de impuestos de valor añadido
- vat austriaco
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- número de identificación de iva
- atu number
- número uid