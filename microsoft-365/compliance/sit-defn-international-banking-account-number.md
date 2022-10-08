---
title: Definición de entidad de número de cuenta bancaria internacional (IBAN)
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
description: Definición de entidad de tipo de información confidencial de número de cuenta bancaria internacional (IBAN).
ms.openlocfilehash: 2bd3eeaec0bffb8b75180e60782ecb3aeedc32a5
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68378388"
---
# <a name="international-banking-account-number-iban"></a>Número de cuenta bancaria internacional (IBAN)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Código de país (dos letras) más dígitos de control (dos dígitos), más el número IBAN (hasta 30 caracteres)


## <a name="pattern"></a>Patrón

El patrón debe incluir todos estos patrones:

- Código de país de dos letras
- Dos dígitos de control (seguidos de un espacio opcional) 
- 1-7 grupos de cuatro letras o dígitos (pueden estar separados por espacios)
- 1-3 letras o dígitos

El formato de cada país es ligeramente diferente. El tipo de información confidencial IBAN abarca estos 68 países:

- ad
- Ae
- al
- En
- Az
- Ba
- Ser
- bg
- Bh
- br
- Ch
- Cr
- Cy
- Cz
- de
- Dk
- hacer
- ee
- es
- fi
- Fo
- fr
- Gb
- ge
- Gi
- gl
- Gr
- gt
- hr
- hu
- Ie
- Il
- is
- it
- Jo
- Kw
- Kz
- Lb
- Li
- lt
- Lu
- lv
- mc
- md
- me
- mk
- mr
- Mt
- Mu
- nl
- no
- Pk
- pl
- Ps
- pt
- Qa
- ro
- rs
- Sa
- se
- si
- sk
- Sm
- Tl
- Tn
- tr
- Vg
- Xk


## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_iban` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

Ninguno
