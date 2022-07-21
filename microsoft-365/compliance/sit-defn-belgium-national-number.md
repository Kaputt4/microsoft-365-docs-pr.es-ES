---
title: Definición de entidad de número nacional de Bélgica
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
description: Definición de entidad de tipo de información confidencial de número nacional de Bélgica.
ms.openlocfilehash: 5fc644a8dcb275cba2986139dfdd16444e47c218
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951252"
---
# <a name="belgium-national-number"></a>Número nacional de Bélgica

## <a name="format"></a>Formato

11 dígitos más delimitadores opcionales

## <a name="pattern"></a>Patrón

11 dígitos más delimitadores:

- seis dígitos y dos períodos opcionales con el formato AAAA. MM.DD para la fecha de nacimiento
- Delimitador opcional de punto, guion, espacio
- tres dígitos secuenciales (impares para hombres, incluso para mujeres)
- Delimitador opcional de punto, guion, espacio
- dos dígitos de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una directiva DLP tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_belgium_national_number` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_belgium_national_number` .
- Se supera la suma de comprobación.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_belgium_national_number` busca contenido que coincida con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- Bnn #
- Bnn
- carte d'identité
- nacional de identificación
- identifiantnational #
- identificatie
- Identificación
- identificación
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- Identidad
- Inscripción
- número nacional
- registro nacional
- nationalnumber #
- nationalnumber
- Nif #
- Nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational #
- número de id. personal
- personalausweis
- personalidnumber #
- registratie
- Registro
- registrationsnumme
- registrierung
- social security number
- Ssn #
- Ssn
- steuernummer
- tax id
- identificación fiscal no
- número de identificación fiscal
- impuestos no #
- impuestos no
- número de impuestos
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- Lata #