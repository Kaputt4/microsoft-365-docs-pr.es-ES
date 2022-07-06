---
title: Notas de la versión sobre la compatibilidad de Microsoft Purview con el conjunto de caracteres de doble byte
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Notas de la versión para la compatibilidad con juegos de caracteres de doble byte.
ms.openlocfilehash: 593e1db04c5e4dc56bc4cc1a7fd11d907d4fe09d
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66622433"
---
# <a name="support-for-double-byte-character-set-release-notes"></a>Notas de la versión para la compatibilidad con juegos de caracteres de doble byte

 Microsoft 365 Information Protection ahora es compatible con los idiomas del conjunto de caracteres de doble byte para:

- Chino (simplificado)
- Chino (tradicional)
- Coreano
- Japonés

Esta compatibilidad está disponible para tipos de información confidencial y diccionarios de palabras clave y se reflejará en la prevención de pérdida de datos de Microsoft Purview (para Exchange Online, SharePoint Online, OneDrive para la Empresa y Teams), cumplimiento de comunicaciones, etiquetado automático en aplicaciones de Office y Microsoft Defender for Cloud Apps.

## <a name="known-issues"></a>Problemas conocidos

- Si un archivo de texto adjunto a un mensaje de correo electrónico está en formato UTF-8 sin marca de orden de bytes (BOM), el mensaje no se detecta mediante la directiva de Cumplimiento de comunicaciones.

- Las directivas de Cumplimiento de comunicaciones no pueden detectar valores si se especifica una frase para la condición de la directiva "El mensaje contiene cualquiera de estas palabras". Si el texto especificado en la directiva está escrito como una palabra, puede detectarse. Sin embargo, si está escrito en mitad de una oración, no se detectará.

- Las directivas de Cumplimiento de comunicaciones que especifican diccionarios como información de tipo no detectan chats privados ni chats de canales de Teams.

- Las condiciones siguientes no son compatibles con el Cumplimiento de comunicaciones en este momento (pensamos solucionar estos problemas en el futuro): 
  - "El mensaje contiene cualquiera de estas palabras"
  - "El mensaje no contiene ninguna de estas palabras"
  - "Los datos adjuntos contienen cualquiera de estas palabras"
  - "Los datos adjuntos contienen cualquiera de estas palabras"

- Las directivas de prevención de pérdida de datos son aplicables en dispositivos macOS (versión preliminar) que ejecutan Catalina 10.15 y versiones posteriores, excepto para las condiciones mencionadas a continuación para los idiomas del este asiático, como el japonés.
  - No se detectan números de ancho completo, como el uso de una plantilla integrada, como el número de cuenta bancaria de Japón
  - No se detectan números sin delimitadores
  - Las palabras clave separadas por un espacio de ancho medio no se detectan para un tipo de información confidencial. Por ejemplo, la palabra "japonés" se establece en el tipo de información confidencial y el diccionario no la detecta si está en una oración
  - No se detectan palabras que contengan inglés y japonés (東京2020)

En su lugar, recomendamos crear un Tipo de información confidencial personalizado (SIT) con el diccionario de palabras clave que detectará los patrones en mensajes y datos adjuntos, utilizando este SIT personalizado como condición de la directiva de Cumplimiento de las comunicaciones.
