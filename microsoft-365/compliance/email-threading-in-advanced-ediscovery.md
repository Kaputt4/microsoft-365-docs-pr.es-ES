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
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Al realizar un análisis Advanced eDiscovery, el subproceso de correo electrónico analiza una conversación de correo electrónico y separa cada mensaje en diferentes categorías.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285566"
---
# <a name="email-threading-in-advanced-ediscovery"></a>Subprocesos de correo electrónico en Advanced eDiscovery

Considere una conversación de correo electrónico que ha estado sucediendo durante un tiempo. En la mayoría de los casos, el último correo electrónico del subproceso incluirá el contenido de todos los correos electrónicos anteriores; revisar el último correo electrónico le dará un contexto completo de la conversación que ocurrió en el subproceso. El subproceso de correo electrónico identifica dichos correos electrónicos para que los revisores puedan revisar una fracción de documentos recopilados sin perder ningún contexto.

## <a name="what-does-email-threading-do"></a>¿Qué hace el subproceso de correo electrónico?

El subproceso de correo electrónico analiza cada correo electrónico y lo deconstruye en mensajes individuales; cada correo electrónico es una cadena de mensajes individuales. A continuación, analiza todos los correos electrónicos del conjunto de revisión para determinar si un correo electrónico tiene contenido único o si la cadena está totalmente contenida en un correo electrónico diferente. Al final, los correos electrónicos se dividen en cuatro categorías:

- **Hilo completo**: el último mensaje del correo electrónico tiene contenido único y, además, el correo electrónico tiene todos los datos adjuntos que se incluyeron en otros correos electrónicos cuyo contenido está contenido en este correo electrónico.

- **Hilo completo sin un adjunto**: el último mensaje del correo electrónico tiene contenido único, pero el correo electrónico no contiene algunos de los datos adjuntos que se incluyeron en otros correos electrónicos cuyo contenido contenga este correo electrónico.

- **Copia de hilo completo**: una copia exacta de un correo electrónico de hilo completo o hilo completo sin un adjunto

- **Ninguno**: el contenido de este correo electrónico está contenido en al menos un correo electrónico que se marca como "menos inclusivo/inclusivo".

## <a name="how-is-it-different-from-conversations-in-outlook"></a>¿En qué se diferencia de las conversaciones de Outlook?

De un vistazo, esto suena similar a las agrupaciones de conversaciones en Outlook. Sin embargo, hay algunas distinciones importantes. Considere una conversación de correo electrónico que se bifurca en dos conversaciones; por ejemplo, alguien respondió a un correo electrónico que no es el más reciente de la conversación, por lo que los dos últimos correos electrónicos de la conversación tienen contenido único.

Outlook seguiría agrupando los correos electrónicos en una sola conversación; leer solo el último correo electrónico significaría faltar al contexto del segundo y último correo electrónico, que también contiene contenido único. Dado que el subproceso de correo electrónico analiza cada correo electrónico en componentes individuales y los compara, el subproceso de correo electrónico marcaría los dos últimos correos electrónicos como inclusivos, lo que garantiza que no se pierda ningún contexto mientras lea todos los correos electrónicos marcados como inclusivos.
