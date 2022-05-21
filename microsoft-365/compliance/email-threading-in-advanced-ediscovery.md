---
title: Subprocesos de correo electrónico en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Al realizar un análisis de eDiscovery (Premium), el subproceso de correo electrónico analiza una conversación de correo electrónico y separa cada mensaje en categorías diferentes.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6aa8bfdccf2f7430da1aa00ed444a9c218525ee8
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "65622134"
---
# <a name="email-threading-in-ediscovery-premium"></a>Subprocesos de correo electrónico en eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Considere la posibilidad de una conversación de correo electrónico que ha estado ocurriendo durante un tiempo. En la mayoría de los casos, el último mensaje del subproceso de correo electrónico incluirá el contenido de todos los mensajes anteriores. Por lo tanto, revisar el último mensaje proporcionará un contexto completo de la conversación que se produjo en el subproceso. El subproceso de correo electrónico identifica estos mensajes para que los revisores puedan revisar una fracción de los documentos recopilados sin perder ningún contexto.

## <a name="what-does-email-threading-do"></a>¿Qué hace el subproceso de correo electrónico?

El subproceso de correo electrónico analiza cada subproceso de correo electrónico y lo deconstruye en mensajes individuales. Cada subproceso de correo electrónico es una cadena de mensajes individuales. Microsoft Purview eDiscovery (Premium) analiza todos los mensajes de correo electrónico del conjunto de revisión para determinar si un mensaje de correo electrónico tiene contenido único o si la cadena (mensajes primarios) está totalmente contenida en el mensaje final en el subproceso de correo electrónico. Los mensajes de correo electrónico se dividen en cuatro valores inclusivos:

- **Inclusivo**: un correo electrónico *inclusivo* es el mensaje de correo electrónico final en un subproceso de correo electrónico y contiene todo el contenido anterior de ese subproceso de correo electrónico.

- **Menos inclusivo**: un mensaje de correo electrónico se designa como *Inclusive menos* si hay uno o más datos adjuntos asociados al mensaje específico dentro del subproceso de correo electrónico. Un revisor puede usar el valor Inclusive menos para determinar qué mensaje de correo electrónico específico dentro del subproceso tiene datos adjuntos asociados. 

- **Copia inclusiva**: un mensaje de correo electrónico se considera una *copia inclusiva* si es una copia exacta de un mensaje inclusivo o inclusivo menos. 

- **Ninguno**: el valor *None* indica que el contenido del mensaje está totalmente contenido en al menos otro mensaje de correo electrónico marcado como Inclusive o Inclusive menos.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>¿En qué se diferencia de las conversaciones de Outlook?

De un vistazo, esto suena similar a las agrupaciones de conversaciones en Outlook. Sin embargo, hay algunas distinciones importantes. Considere la posibilidad de una conversación de correo electrónico que se bifurca en dos conversaciones; por ejemplo, alguien respondió a un correo electrónico que no es el más reciente de la conversación, por lo que los dos últimos correos electrónicos de la conversación tienen contenido único.

Outlook seguiría agrupando los correos electrónicos en una sola conversación; leer solo el último correo electrónico significaría perder el contexto del segundo al último correo electrónico, que también contiene contenido único. Dado que el subproceso de correo electrónico analiza cada correo electrónico en componentes individuales y los compara, el subproceso de correo electrónico marcaría los dos últimos correos electrónicos como inclusivos, lo que garantiza que no se perderá ningún contexto siempre y cuando lea todos los correos electrónicos marcados como inclusivos.
