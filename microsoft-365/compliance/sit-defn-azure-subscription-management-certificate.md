---
title: Definición de entidad de certificado de administración de suscripciones de Azure
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
description: Definición de entidad de tipo de información confidencial del certificado de administración de suscripciones de Azure.
ms.openlocfilehash: d75a012c92d31dc5a103e6379241b9ecb2812277
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2022
ms.locfileid: "68502992"
---
# <a name="azure-subscription-management-certificate"></a>Certificado de administración de suscripciones de Azure

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Esta SIT también se incluye en el SIT de [todas las credenciales](sit-defn-all-creds.md) agrupadas.

 ## <a name="format"></a>Formato

Combinación de hasta 20 000 caracteres que constan de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Una combinación de hasta 20 000 caracteres:
 
- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barra diagonal (/) o signo más (+)
- Hasta dos signos iguales (==)

Por ejemplo:

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM`

## <a name="credential-example"></a>Ejemplo de credencial 

`<Subscription id="f70163aa-03a8-4f4a-8a30-d38e3f38fde4" ManagementCertificate="MIIPuQIBAzCCD38GCSqGS...`

> [!IMPORTANT]
> Este ejemplo se ha truncado. No es un ejemplo detectable de este SIT.

## <a name="checksum"></a>Suma de comprobación

Sí

Los SIT que tienen sumas de comprobación usan un cálculo único para comprobar si la información es válida. Esto significa que cuando el valor **de suma de comprobación** es **Sí**, el servicio puede realizar una detección positiva solo en función de los datos confidenciales. Cuando el valor **de suma de comprobación** es **No** se deben detectar elementos adicionales (secundarios) para que el servicio realice una detección positiva.

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para autenticarse con el [modelo de implementación clásica](/azure/azure-resource-manager/management/deployment-models) proporcionado por Azure. Muchos programas y herramientas, como Visual Studio o el SDK de Azure, usan estos certificados para automatizar la configuración y la implementación de varios [servicios de Azure](/azure/azure-api-management-certs). 

Usa varios recursos principales:

- Patrones de literal de cadena codificada en Base64.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- Mii
