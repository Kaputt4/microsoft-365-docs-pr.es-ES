---
title: Definición de entidad de número de certificado residente de Taiwán (ARC/TARC)
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
description: Definición de entidad de tipo de información confidencial de número de certificado residente de Taiwán (ARC/TARC).
ms.openlocfilehash: 16e32c0fcfd9ae8be4f0dc7612329594b22ecc37
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472286"
---
# <a name="taiwan-resident-certificate-arctarc-number"></a>Número del certificado de residente de Taiwán (ARC/TARC)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

10 letras y dígitos

## <a name="pattern"></a>Patrón

10 letras y dígitos:

- dos letras (no distinguen mayúsculas de minúsculas)
- ocho dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_taiwan_resident_certificate` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_taiwan_resident_certificate`.

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- Certificado de residente
- Cert. residente

- Cert. residente

- Tarjeta de identificación
- Certificado de residente extranjero
- ARC
- Certificado de residente en el área de Taiwán
- TARC
- 居留證
- 外僑居留證
- 台灣地區居留證
