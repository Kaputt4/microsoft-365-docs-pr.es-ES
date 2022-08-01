---
title: Definición de entidad de dirección IP v4
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
description: Definición de entidad de tipo de información confidencial de dirección IP v4.
ms.openlocfilehash: e145b4342c5b276b66d0ed463a2094b7ada47b01
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000001"
---
# <a name="ip-address-v4"></a>Dirección IP v4

## <a name="format"></a>Formato

Patrón complejo que tiene en cuenta las versiones con formato (puntos) y sin formato (sin puntos) de las direcciones IPv4.

## <a name="pattern"></a>Patrón

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_ipv4_address` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_ipaddress`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_ipv4_address` regular busca contenido que coincida con el patrón.

```xml
      <!-- IP Address v4-->
      <Entity id="a7dd5e5f-e7f9-4626-a2c6-86a8cb6830d2" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ipv4_address" />
          <Match idRef="Keyword_ipaddress" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ipv4_address" />
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