---
title: Definición de entidad de número de ingresos interiores de Nueva Zelanda
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
description: Definición de entidad de tipo de información confidencial de número de ingresos interiores de Nueva Zelanda.
ms.openlocfilehash: 26604014771674a2177f3fee6c062e3bfcee4175
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951207"
---
# <a name="new-zealand-inland-revenue-number"></a>Número de ingresos interiores de Nueva Zelanda

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

ocho o nueve dígitos con delimitadores opcionales

## <a name="pattern"></a>Patrón

ocho o nueve dígitos con delimitadores opcionales

- dos o tres dígitos
- un espacio opcional o un guion
- tres dígitos
- un espacio opcional o un guion
- tres dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_new_zealand_inland_revenue_number` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_new_zealand_inland_revenue_number` .

Una directiva DLP tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_new_zealand_inland_revenue_number` busca contenido que coincida con el patrón.

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- Ird no.
- ird no #
- nz ird
- nueva Zelanda ird
- ird number
- número de ingresos interiores