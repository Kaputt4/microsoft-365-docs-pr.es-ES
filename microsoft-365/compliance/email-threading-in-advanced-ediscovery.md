---
title: Subprocesos de correo electrónico en Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: Al realizar un análisis Advanced eDiscovery, el subproceso de correo electrónico analiza una conversación de correo electrónico y separa cada mensaje en diferentes categorías.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 788858d6acaccbe07f3190b5adaaa05fe95c33a5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159795"
---
# <a name="email-threading-in-advanced-ediscovery"></a>Subprocesos de correo electrónico en Advanced eDiscovery

Considere una conversación de correo electrónico que ha estado sucediendo durante un tiempo. En la mayoría de los casos, el último mensaje del subproceso de correo electrónico incluirá el contenido de todos los mensajes anteriores. Por lo tanto, revisar el último mensaje dará un contexto completo de la conversación que ocurrió en el subproceso. El subproceso de correo electrónico identifica estos mensajes para que los revisores puedan revisar una fracción de documentos recopilados sin perder ningún contexto.

## <a name="what-does-email-threading-do"></a>¿Qué hace el subproceso de correo electrónico?

El subproceso de correo electrónico analiza cada subproceso de correo electrónico y lo deconstruye en mensajes individuales. Cada subproceso de correo electrónico es una cadena de mensajes individuales. Advanced eDiscovery analiza todos los mensajes de correo electrónico del conjunto de opiniones para determinar si un mensaje de correo electrónico tiene contenido único o si la cadena (mensajes primarios) está totalmente contenida en el mensaje final del subproceso de correo electrónico. Los mensajes de correo electrónico se dividen en cuatro valores inclusivos:

- **Inclusive:** un *correo electrónico* inclusivo es el mensaje de correo electrónico final de un subproceso de correo electrónico y contiene todo el contenido anterior de ese subproceso de correo electrónico.

- **Inclusive menos:** un mensaje de correo electrónico se designa como *Inclusive menos* si hay uno o más datos adjuntos asociados con el mensaje específico dentro del subproceso de correo electrónico. Un revisor puede usar el valor menos inclusivo para determinar qué mensaje de correo electrónico específico dentro del subproceso tiene datos adjuntos asociados. 

- **Copia inclusiva:** un mensaje  de correo electrónico se considera una copia inclusiva si es una copia exacta de un mensaje menos inclusivo o inclusivo. 

- **None:** el *valor None* indica que el contenido del mensaje está totalmente contenido en al menos otro mensaje de correo electrónico marcado como Inclusivo o Inclusivo menos.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>¿En qué se diferencia de las conversaciones de Outlook?

De un vistazo, esto suena similar a las agrupaciones de conversaciones en Outlook. Sin embargo, hay algunas distinciones importantes. Considere una conversación de correo electrónico que se bifurca en dos conversaciones; por ejemplo, alguien respondió a un correo electrónico que no es el más reciente de la conversación, por lo que los dos últimos correos electrónicos de la conversación tienen contenido único.

Outlook seguiría agrupando los correos electrónicos en una sola conversación; leer solo el último correo electrónico significaría faltar al contexto del segundo y último correo electrónico, que también contiene contenido único. Dado que el subproceso de correo electrónico analiza cada correo electrónico en componentes individuales y los compara, el subproceso de correo electrónico marcaría los dos últimos correos electrónicos como inclusivos, lo que garantiza que no se pierda ningún contexto mientras lea todos los correos electrónicos marcados como inclusivos.
