---
title: Definición de entidad de número de identificación fiscal de España
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
description: Definición de entidad de tipo de información confidencial del número de identificación fiscal de España.
ms.openlocfilehash: de7075c6ff81c97537b9f7145fd269a671b8e1dc
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000079"
---
# <a name="spain-tax-identification-number"></a>Número de identificación fiscal de España

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicaciones
- administración del ciclo de vida de datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

siete u ocho dígitos y una o dos letras en el patrón especificado

## <a name="pattern"></a>Patrón

Personas físicas españolas con tarjeta nacional de identidad de España:

- ocho dígitos
- una letra mayúscula (distingue mayúsculas de minúsculas)

Españoles no residentes sin tarjeta nacional de identidad de España

- una letra mayúscula "L" (distingue mayúsculas de minúsculas)
- siete dígitos
- una letra mayúscula (distingue mayúsculas de minúsculas)

Españoles residentes menores de 14 años sin tarjeta de identidad nacional de España:

- una letra mayúscula "K" (distingue mayúsculas de minúsculas)
- siete dígitos
- una letra mayúscula (distingue mayúsculas de minúsculas)

Extranjeros con un número de identificación de extranjero

- una letra mayúscula que es "X", "Y" o "Z" (distingue mayúsculas de minúsculas)
- siete dígitos
- una letra mayúscula (distingue mayúsculas de minúsculas)

Extranjeros sin el número de identificación de extranjero

- una letra mayúscula que es "M" (distingue mayúsculas de minúsculas)
- siete dígitos
- una letra mayúscula (distingue mayúsculas de minúsculas)

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_spain_eu_tax_file_number` o `Func_spain_eu_DL_and_NI_number_citizen` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_spain_eu_tax_file_number`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_spain_eu_tax_file_number` o `Func_spain_eu_DL_and_NI_number_citizen` encuentra contenido que coincide con el patrón.

```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- Cif
- cifid #
- cifnúmero #
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- archivo fiscal no
- tax file number
- tax id
- núm. identificación fiscal
- número de identificación fiscal
- n.º de id. fiscal#
- n.º fiscal
- número de id. fiscal
- número de registro fiscal
- Id.fiscal#
- númidfiscal#
- númeroidentificaciónfiscal#
- núm.fiscal#
- núm.id.fiscal#
- núm.id.fisca
- id. tributaria
- n.º de id. tributario
- Número de identificación tributaria