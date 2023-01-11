---
title: Definición de entidad número GST de la India
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
description: Definición de entidad de tipo de información confidencial de número GST de India.
ms.openlocfilehash: 6fc840d994311a88ddbb5cc86a26a9b36969213a
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68379686"
---
# <a name="india-gst-number"></a>Número GST de India

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Patrón alfanumérico de 15 caracteres

## <a name="pattern"></a>Patrón

15 letras o dígitos:

- dos dígitos que representan código de estado válido
- un espacio o guion opcionales
- diez caracteres que representan el número de cuenta permanente (PAN)
- una letra o un dígito
- un espacio o guion opcionales
- una letra 'z' o 'Z'
- un espacio o guion opcionales
- un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_india_gst_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_india_gst_number`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_india_gst_number` encuentra contenido que coincide con el patrón.

```xml
    <!-- India GST number  -->
      <Entity id="9f5a721c-2fd2-446a-a27e-0c02fbe4630c" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_india_gst_number" />
          <Match idRef="Keyword_india_gst_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_india_gst_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_india_gst_number"></a>Keyword_india_gst_number

- Gst
- gstin
- impuesto sobre bienes y servicios
- impuestos sobre bienes y servicios
