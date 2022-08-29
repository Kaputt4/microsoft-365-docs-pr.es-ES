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
ms.openlocfilehash: 5aebedbcedd04fcf63e9c365329f7eb46fa80740
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369836"
---
# <a name="netherlands-tax-identification-number"></a>Número de identificación fiscal de los Países Bajos

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
- núm. identificación fiscal
- número de identificación fiscal
- tal de identificación fiscal
- n.º de id. fiscal#
- n.º fiscal
- número de id. fiscal
- número de registro fiscal
- recuento de impuestos
- Id.fiscal#
- númidfiscal#
- númeroidentificaciónfiscal#
- núm.fiscal#
- núm.id.fiscal#
- núm.id.fisca
- id. tributaria
- n.º de id. tributario
- Número de identificación tributaria