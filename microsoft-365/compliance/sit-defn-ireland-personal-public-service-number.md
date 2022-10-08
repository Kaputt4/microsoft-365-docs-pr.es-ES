---
title: Definición de entidad de número de servicio público personal (PPS) de Irlanda
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
description: Definición de entidad de tipo de información confidencial de número de servicio público personal (PPS) de Irlanda.
ms.openlocfilehash: da0451a437ad3ab7dd8437352c2f7b539b9d9a9c
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68378322"
---
# <a name="ireland-personal-public-service-pps-number"></a>Número de la seguridad social de Irlanda (PPS)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Formato antiguo (hasta el 31 de diciembre de 2012):

- siete dígitos seguidos de 1-2 letras

Nuevo formato (1 de enero de 2013 y posterior):

- siete dígitos seguidos de dos letras

## <a name="pattern"></a>Patrón

Formato antiguo (hasta el 31 de diciembre de 2012):

- siete dígitos
- de una a dos letras (no distingue mayúsculas de minúsculas)

Nuevo formato (1 de enero de 2013 y posterior):

- siete dígitos
- una letra (no distingue mayúsculas de minúsculas) que es un dígito de comprobación alfabético
- Una letra opcional en el intervalo A-I o "W"

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- Contenido de la función `Func_ireland_pps finds` que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_ireland_eu_national_id_card`.
- Se supera la suma de comprobación.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_ireland_pps` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- servicio de identidad de cliente
- identification number
- número de id. personal
- número de servicio público personal
- servicio personal no
- phearsanta seirbhíse poiblí
- pps no
- pps number
- pps num
- pps service no
- ppsn
- ppsno #
- ppsno
- Psp
- servicio público no
- publicserviceno #
- publicserviceno
- ingresos y número de seguro social
- rsi no
- número rsi
- rsin
- seirbhís aitheantais client
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
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
