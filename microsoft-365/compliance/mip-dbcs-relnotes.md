---
title: Notas de la versión sobre la compatibilidad de Microsoft 365 con el conjunto de caracteres de doble byte
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Notas de la versión para la compatibilidad con juegos de caracteres de doble byte.
ms.openlocfilehash: b7883495c5b187b98e6b0539eaa075e4f8d3af6e
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256392"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a>Notas de la versión sobre la compatibilidad con juegos de caracteres de doble byte (vista previa)

 Microsoft 365 Information Protection ahora es compatible con los idiomas del conjunto de caracteres de doble byte para:

- Chino (simplificado)
- Chino (tradicional)
- Coreano
- Japonés

Esta compatibilidad está disponible para los tipos de información confidencial y los diccionarios de palabras clave y se reflejará en la prevención de la pérdida de datos (para Exchange Online, SharePoint Online, OneDrive para la Empresa y Teams), el cumplimiento de las comunicaciones, el etiquetado automático en las aplicaciones de oficina y Microsoft Cloud App Security.

## <a name="known-issues"></a>Problemas conocidos

- Cuando un archivo de texto adjunto a un correo electrónico está en formato UTF-8 sin marca de orden de bytes (BOM), el correo electrónico no se detecta mediante la directiva de cumplimiento de cumplimiento de comunicaciones.

- Las directivas de cumplimiento de comunicaciones no pueden detectar valores si se especifica una frase para la condición de la directiva: "el mensaje contiene alguna de estas palabras". Si el texto especificado en la directiva está escrito como una palabra, puede detectarse; sin embargo, si está escrito en mitad de una oración, no se detectará.

- Las directivas de Cumplimiento de comunicaciones que especifican diccionarios como información de tipo no detectan chats privados y chats de canales de Teams.

- Las condiciones siguientes no son compatibles con el Cumplimiento de comunicaciones en este momento (pensamos solucionar estos problemas en el futuro): 
  - "El mensaje contiene cualquiera de estas palabras"
  - "El mensaje no contiene ninguna de estas palabras"
  - "Los datos adjuntos contienen cualquiera de estas palabras"
  - "Los datos adjuntos contienen cualquiera de estas palabras"

En su lugar, recomendamos crear un Tipo de información confidencial personalizado (SIT) con el diccionario de palabras clave que detectará los patrones en mensajes y datos adjuntos, utilizando este SIT personalizado como condición de la directiva de Cumplimiento de las comunicaciones.


