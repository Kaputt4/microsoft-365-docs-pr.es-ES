---
title: Definición de entidad de la tarjeta de identificación de elector de la India
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
description: Definición de entidad de tipo de información confidencial de la tarjeta de identificación de elector de la India.
ms.openlocfilehash: 4556824999f44f6407e996fbca7c82e79fe2cafc
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999578"
---
# <a name="india-voter-id-card"></a>Tarjeta de identificación de electoral de India

## <a name="format"></a>Formato

Patrón alfanumérico de 10 caracteres

## <a name="pattern"></a>Patrón

10 letras o dígitos:

- tres letras
- siete dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_india_voter_id_card` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_india_voter_id_card`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_india_voter_id_card` regular busca contenido que coincida con el patrón.

```xml
      <!-- India Voter Id Card  -->
        <Entity id="646d643f-5228-4408-acc8-f2e81a6df897" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
           <Pattern confidenceLevel="75">
             <IdMatch idRef="Regex_india_voter_id_card" />
             <Match idRef="Keyword_india_voter_id_card" />
            </Pattern>
           <Pattern confidenceLevel="65">
              <IdMatch idRef="Regex_india_voter_id_card" />
            </Pattern>
        </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_india_voter_id_card"></a>Keyword_india_voter_id_card

- Votante
- voterid
- credencial de elector
- voteridcard
- tarjeta de identidad de foto electoral
- EPOPEYA
- ECI
- commmision de elecciones