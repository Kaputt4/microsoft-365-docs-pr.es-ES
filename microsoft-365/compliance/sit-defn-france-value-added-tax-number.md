---
title: Definición de entidad de número de impuestos agregados de Francia
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
description: Definición de entidad de tipo de información confidencial del número de impuestos agregado de Francia.
ms.openlocfilehash: 0bec456bdfb4c41f4ab9c3cf4b33e99d7a91b9d4
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367255"
---
# <a name="france-value-added-tax-number"></a>Número del impuesto sobre el valor añadido de Francia

## <a name="format"></a>Formato

Patrón alfanumérico de 13 caracteres

## <a name="pattern"></a>Patrón

Patrón alfanumérico de 13 caracteres:

- dos letras: FR (sin distinción entre mayúsculas y minúsculas)
- un espacio opcional o un guion
- dos letras o dígitos
- un espacio opcional, un punto, un guion o una coma
- tres dígitos
- un espacio opcional, un punto, un guion o una coma
- tres dígitos
- un espacio opcional, un punto, un guion o una coma
- tres dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_france_value_added_tax_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_france_value_added_tax_number`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_france_value_added_tax_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Palabras clave

### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- número de iva
- vat no
- Iva #
- impuesto sobre el valor añadido
- siren identification no numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- numéro d'identification siren