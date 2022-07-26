---
title: Definición de entidad de certificado de administración de suscripciones de Azure (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial del certificado de administración de suscripciones de Azure.
ms.openlocfilehash: 7ce7b09fdeae6f9622a3aac4f92beb446715f8df
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999242"
---
# <a name="azure-subscription-management-certificate-preview"></a>Certificado de administración de suscripciones de Azure (versión preliminar)

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

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para autenticarse con el [modelo de implementación clásica](/azure/azure-resource-manager/management/deployment-models) proporcionado por Azure. Muchos programas y herramientas, como Visual Studio o el SDK de Azure, usan estos certificados para automatizar la configuración y la implementación de varios [servicios de Azure](/azure/azure-api-management-certs). 

Usa varios recursos principales:

- Patrones de literal de cadena codificada en Base64.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- MII
