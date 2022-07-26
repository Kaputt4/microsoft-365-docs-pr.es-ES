---
title: Definición de entidad de número de empresa de Australia
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
description: Definición de entidad de tipo de información confidencial de número de empresa de Australia.
ms.openlocfilehash: a10addd7dee6bc481adbf9edf1380cdedf09bdd0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999209"
---
# <a name="australia-company-number"></a>Código de identificación fiscal (ACN) de Australia

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

nueve dígitos con delimitadores

## <a name="pattern"></a>Patrón

nueve dígitos con delimitadores:

- tres dígitos
- un espacio
- tres dígitos
- un espacio
- tres dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función Func_Australian_Company_Number busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de Keyword_Australian_Company_Number.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función Func_Australian_Company_Number busca contenido que coincida con el patrón.

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Palabras clave

### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- enlatar
- australia empresa no
- australia empresa no #
- número de empresa de Australia
- australian company no
- australian company no #
- número de empresa australiana
