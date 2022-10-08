---
title: ASP.NET definición de entidad de clave de máquina (versión preliminar)
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
description: ASP.NET definición de entidad de tipo de información confidencial de clave de máquina.
ms.openlocfilehash: 1fe8616229bca7a00581d026a318db4029fc2200
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476405"
---
# <a name="aspnet-machine-key-preview"></a>ASP.NET clave de máquina (versión preliminar)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Claves simétricas en la configuración XML.

## <a name="pattern"></a>Patrón

Varios formatos de clave simétrica en XML, por ejemplo:

```xml
<machineKey decryptionKey="******** </br> 
<machineKey validationKey="********
```
## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición


Esta SIT está diseñada para coincidir con la información de seguridad que se usa para cifrar o hash datos en [ASP.NET](/dotnet/api/system.web.security.machinekey?view=netframework-4.8) autenticación de formularios y ver el estado. 

Usa varios recursos principales:

- Patrones de contexto de clave simétrica en archivos xml.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.


## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickeycontextinxml"></a>Keyword_SymmetricKeyContextInXml:

- contraseña
- clave
- Connectionstring

