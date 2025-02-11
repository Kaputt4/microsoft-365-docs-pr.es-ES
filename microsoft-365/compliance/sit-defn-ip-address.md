---
title: Definición de entidad de dirección IP
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
description: Definición de entidad de tipo de información confidencial de direcciones IP.
ms.openlocfilehash: 35ef4b8715fb7d49e40aa83bfacb75a817f88bab
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68380456"
---
# <a name="ip-address"></a>Dirección IP

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

### <a name="ipv4"></a>IPv4: 
Patrón complejo que tiene en cuenta las versiones con formato (puntos) y sin formato (sin puntos) de las direcciones IPv4

### <a name="ipv6"></a>IPv6: 
Patrón complejo que cuenta con números IPv6 con formato (que incluyen dos puntos)

## <a name="pattern"></a>Patrón

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Para IPv6, una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_ipv6_address` encuentra contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de `Keyword_ipaddress` .

Para IPv4, una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_ipv4_address` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_ipaddress`.

Para IPv6, una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_ipv6_address` encuentra contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de `Keyword_ipaddress` .

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (esta palabra clave distingue mayúsculas de minúsculas)
- dirección IP
- Direcciones IP
- internet protocol
- IP-כתובת ה
