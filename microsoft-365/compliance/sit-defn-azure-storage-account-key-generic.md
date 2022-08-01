---
title: Definición de entidad de clave de cuenta (genérica) de Azure Storage
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
description: Definición de entidad de tipo de información confidencial de clave de cuenta (genérica) de Azure Storage.
ms.openlocfilehash: 88139dfe26e654e664d74e8543ea791fd171da63
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999689"
---
# <a name="azure-storage-account-key-generic"></a>Clave de cuenta de Azure Storage (genérica)

## <a name="format"></a>Formato

Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, la barra diagonal (/) o signo más (+), precedida o seguida de los caracteres descritos en el patrón siguiente.

## <a name="pattern"></a>Patrón

- de cero a uno de los símbolos mayores que (>), apóstrofos ('), signo igual (=), comillas (") o signo de número (#)
- cualquier combinación de 86 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- dos signos iguales (=)

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `CEP_Regex_AzureStorageAccountKeyGeneric` regular busca contenido que coincida con el patrón.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```