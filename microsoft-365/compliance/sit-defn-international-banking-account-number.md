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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial de número de cuenta bancaria internacional (IBAN).
ms.openlocfilehash: 739c0a1fd90da1da817f46019cd1023be8ab27a3
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999857"
---
# <a name="international-banking-account-number-iban"></a>Número de cuenta bancaria internacional (IBAN)

## <a name="format"></a>Formato

Código de país (dos letras) más dígitos de control (dos dígitos), más el número IBAN (hasta 30 caracteres)


## <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:

- Código de país de dos letras
- Dos dígitos de control (seguidos de un espacio opcional) 
- 1-7 grupos de cuatro letras o dígitos (pueden estar separados por espacios)
- 1-3 letras o dígitos

El formato de cada país es ligeramente diferente. El tipo de información confidencial del IBAN cubre estos 60 países:

- ad
- Ae
- al
- En
- Az
- Ba
- Ser
- bg
- Bh
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
- hr
- hu
- Ie
- Il
- is
- it
- Kw
- Kz
- Lb
- Li
- lt
- Lu
- lv
- Mc
- md
- me
- mk
- mr
- Mt
- Mu
- nl
- no
- pl
- pt
- ro
- rs
- Sa
- se
- si
- sk
- Sm
- Tn
- tr
- Vg

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