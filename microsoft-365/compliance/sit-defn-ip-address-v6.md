---
title: Definición de entidad de dirección IP v6
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
description: Definición de entidad de tipo de información confidencial de dirección IP v6.
ms.openlocfilehash: fa7c4e64647b013857ddacef6af0bab6461ca4ab
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999998"
---
# <a name="ip-address-v6"></a>Dirección IP v6

## <a name="format"></a>Formato

Patrón complejo que cuenta con números IPv6 con formato (que incluyen dos puntos)

## <a name="pattern"></a>Patrón

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_ipv6_address` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_ipaddress`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_ipv6_address` regular busca contenido que coincida con el patrón.

```xml
      <!-- IP Address v6-->
      <Entity id="3f691089-7413-4926-ab3b-3c5ea8a1c17e" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ipv6_address" />
          <Match idRef="Keyword_ipaddress" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ipv6_address" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (distingue mayúsculas de minúsculas)
- dirección IP
- Direcciones IP
- internet protocol
- IP-כתובת ה