---
title: Definición de entidad de número de identificación fiscal de Países Bajos
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
description: Definición de entidad del tipo de información confidencial del número de identificación fiscal de Los Países Bajos.
ms.openlocfilehash: 03dc229b91636644075428b9b01fee1503c80da1
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000121"
---
# <a name="netherlands-tax-identification-number"></a>Número de identificación fiscal de los Países Bajos

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

nueve dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

nueve dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_netherlands_eu_tax_file_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_netherlands_eu_tax_file_number`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_netherlands_eu_tax_file_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- Netherlands Tax Identification Number -->
      <Entity id="01f42a64-eba7-4892-a67b-398237e4ade2" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- Identificación fiscal de hollânske
- hulandes impuesto id number
- identificación de hulandes impuesto
- identificatienummer belasting
- identificatienummer van belasting
- Impuesto número de identificación
- impuesto number
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- identificación fiscal de países bajos
- identificación fiscal de netherland
- estaño neerlandés
- lata de netherland
- tax id
- identificación fiscal no
- número de identificación fiscal
- tal de identificación fiscal
- impuestos no #
- impuestos no
- número de impuestos
- número de registro fiscal
- recuento de impuestos
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- Lata #