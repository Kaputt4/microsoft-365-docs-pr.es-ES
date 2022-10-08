---
title: Número de tarjeta de identificación de Qatar
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
description: Definición de entidad de tipo de información confidencial del número de tarjeta de identificación de Qatar.
ms.openlocfilehash: 35b609753afd7f63674ef8b50f42257c78409e16
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472813"
---
# <a name="qatari-id-card-number"></a>Número de tarjeta de identificación de Qatar

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

once dígitos

## <a name="pattern"></a>Patrón

Once dígitos:

- un dígito 2 o 3 
- dos dígitos que representan los dos últimos números del año de nacimiento 
- tres dígitos que representan el código de país ISO 
- cinco dígitos.

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres: 

- La expresión regular Regex_qatari_id_card busca contenido que coincida con el patrón. 
- Se encuentra una palabra clave de Keyword_qatari_id_card. 

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres: 

- La expresión regular Regex_qatari_id_card busca contenido que coincida con el patrón. 

```xml
     <!-- Qatari ID Card Number-->
        <Entity id="52b1b60e-a4be-4b5a-a67b-6f9bbb7811da" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
          <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_qatari_id_card" />
            <Match idRef="Keyword_qatari_id_card" />
          </Pattern>
          <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_qatari_id_card" />
          </Pattern>
        </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_qatari_id_card"></a>Keyword_qatari_id_card

- Gp 
- Dob 
- D.O.B 
- Fecha de nacimiento 
- Fecha de nacimiento 
- fecha de emisión 
- fecha de expiración 
