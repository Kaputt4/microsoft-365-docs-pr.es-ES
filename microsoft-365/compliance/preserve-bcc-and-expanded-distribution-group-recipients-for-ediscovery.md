---
title: Conservar los destinatarios de grupos de distribución expandidos y CCO para la exhibición de documentos electrónicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: In-Place directivas de suspensión, suspensión por juicio y retención de Microsoft 365 le permiten conservar el contenido del buzón para cumplir los requisitos normativos y de exhibición de documentos electrónicos.
ms.openlocfilehash: a088407277f7ebced3aa69ee9ff807913f9b0c85
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64942125"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>Conservar los destinatarios de grupos de distribución expandidos y CCO para la exhibición de documentos electrónicos
  
Las retenciones por litigio, las retenciones de eDiscovery y [las directivas de retención de Microsoft 365](./retention.md) (creadas en el portal de cumplimiento de Microsoft Purview) le permiten conservar el contenido del buzón para cumplir los requisitos normativos y de eDiscovery. De forma predeterminada, la información sobre los destinatarios que se abordan directamente en los campos To y Cc de un mensaje se incluye en todos los mensajes. Pero su organización puede requerir la capacidad de buscar y reproducir detalles sobre todos los destinatarios de un mensaje. Incluye lo siguiente:
  
- **Destinatarios abordados mediante el campo CCO de un mensaje:** Los destinatarios CCO se almacenan en el mensaje en el buzón del remitente, pero no se incluyen en los encabezados del mensaje entregado a los destinatarios. 
    
- **Destinatarios de grupos de distribución expandidos:** Destinatarios que reciben el mensaje porque son miembros de un grupo de distribución al que se ha dirigido el mensaje, ya sea en los campos To, Cc o Bcc. 
    
Exchange Online y Exchange Server 2013 (actualización acumulativa 7 y versiones posteriores) conservan información sobre Bcc y los destinatarios de grupos de distribución expandidos. Puede buscar esta información mediante una herramienta eDiscovery en el portal de cumplimiento.
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Forma de conservación de los destinatarios CCO y los destinatarios del grupo de distribución expandido

Tal como se mencionó anteriormente, la información los destinatarios CCO se almacena con el mensaje en el buzón de correo del remitente. Esta información se indexa y está disponible para las búsquedas y retenciones de eDiscovery.

La información sobre los destinatarios del grupo de distribución expandido se almacena con el mensaje después de que se coloca en un buzón de correo en conservación local o retención por juicio. En Office 365, esta información también se almacena cuando se aplica una directiva de retención de Microsoft 365 a un buzón de correo. La pertenencia al grupo de distribución se determina en el momento en el que se envía el mensaje. La lista de destinatarios ampliada almacenada con el mensaje no se ve afectada por los cambios realizados en la pertenencia del grupo después de que se envía el mensaje.

|Información sobre...|Se almacena en...|¿se almacena de forma predeterminada?|Es accesible para...|
|---|---|---|---|
|Destinatarios de Para y CC|Propiedades del mensaje en los buzones de correo del remitente y los destinatarios|Sí|Remitente, destinatarios y responsables de cumplimiento normativo|
|Destinatarios CCO|Propiedad del mensaje en el buzón de correo del remitente|Sí|Remitente y responsables de cumplimento normativo|
|Destinatarios del grupo de distribución expandido|Propiedades del mensaje en el buzón de correo del remitente|No. La información de destinatarios del grupo de distribución expandido se almacena después de colocar un buzón en In-Place suspensión o suspensión por juicio, o bien se asigna a una directiva de retención de Microsoft 365.|Responsables de cumplimento normativo|

## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Buscar mensajes enviados a destinatarios CCO y del grupo de distribución expandido

Cuando se buscan mensajes enviados a un destinatario, los resultados de la búsqueda de exhibición de documentos electrónicos ahora incluyen los mensajes enviados a un grupo de distribución del que es miembro el destinatario. En la tabla siguiente se muestran los escenarios en los que los mensajes enviados a destinatarios CCO y del grupo de distribución ampliado se proporcionan en las búsquedas de exhibición de documentos electrónicos.

Escenario 1: John es miembro del grupo de distribución US-Sales En esta tabla se muestran los resultados de búsqueda de la exhibición de documentos electrónicos cuando Bob le envía un mensaje a John directamente o indirectamente mediante un grupo de distribución.

|Al buscar mensajes enviados en el buzón de Bob...|Y el mensaje se envía con...|¿Los resultados incluyen el mensaje?|
|---|---|---|
|To:John|John en TO|Sí|
|To:John|US-Sales en TO|Sí|
|To:US-Sales|US-Sales en TO|Sí|
|Cc:John|John en CC|Sí|
|Cc:John|US-Sales en CC|Sí|
|Cc:US-Sales|US-Sales en CC|Sí|

Escenario 2: Bob le envía un correo electrónico a John (Para/CC) y Jack (CCO directamente o indirectamente mediante un grupo de distribución). En la tabla siguiente se muestran los resultados de búsqueda de la exhibición de documentos electrónicos.

|Al buscar...|Para los mensajes enviados...|¿Los resultados incluyen el mensaje?|Notas|
|---|---|---|---|
|Buzón de correo de Bob|To/Cc:John|Sí|Presenta una indicación de que Jack se incluyó en CCO.|
|Buzón de correo de Bob|Bcc:Jack|Sí|Presenta una indicación de que Jack se incluyó en CCO.|
|Buzón de correo de Bob|Bcc:Jack (mediante grupo de distribución)|Sí|La lista de miembros del grupo de distribución CCO, expandido cuando se envió el mensaje, está visible en la vista previa, exportación y registros de la búsqueda de eDiscovery.|
|Buzón de correo de John|To/Cc:John|Sí|Sin indicación de los destinatarios CCO.|
|Buzón de correo de John|Bcc:Jack (directamente o mediante grupo de distribución)|No|La información de CCO no se almacena en el mensaje que se entrega a los destinatarios. Debe buscar en el buzón de correo del remitente.|
|Buzón de correo de Jack|To/Cc:John (directamente o mediante grupo de distribución)|Sí|La información de Para/CC se incluye en el mensaje que se entrega a todos los destinatarios.|
|Buzón de correo de Jack|Bcc:Jack (directamente o mediante grupo de distribución)|No|La información de CCO no se almacena en el mensaje que se entrega a los destinatarios. Debe buscar en el buzón de correo del remitente.|

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

 **P. ¿Cuándo y dónde se almacena la información de destinatarios CCO?**

R. La información de CCO se conserva de forma predeterminada en el mensaje original en el buzón de correo del remitente. Si el destinatario de CCO es un grupo de distribución, la pertenencia al grupo de distribución solo se expande si el buzón del remitente está en espera o asignado a una directiva de retención de Microsoft 365.

 **P. ¿Cuándo y dónde está almacenada la lista de destinatarios del grupo de distribución expandido?**

R. La pertenencia al grupo se expande en el momento en el que se envía el mensaje. La lista de miembros del grupo de distribución expandido se almacena en el mensaje original en el buzón de correo del remitente. El buzón del remitente debe estar en In-Place suspensión, suspensión por juicio o estar asignado a una directiva de retención de Microsoft 365.

 **P. ¿Los destinatarios incluidos en Para/CC: pueden ver qué destinatarios figuran en CCO?**

R. No. Esta información no se incluye en los encabezados del mensaje y no está visible para los destinatarios incluidos en Para/CC. El remitente puede ver el campo CCO almacenado en el mensaje original almacenado en el buzón de correo. Los responsables de cumplimento normativo pueden ver esta información cuando buscan en el buzón de correo del remitente.

 **Q. ¿Cómo puedo asegurarme de que los destinatarios del grupo de distribución expandido siempre se conserven?**

R. Para asegurarse de que los miembros del grupo de distribución expandido siempre se conservan con un mensaje, [coloque todos los buzones en espera](/Exchange/policy-and-compliance/holds/place-all-mailboxes-on-hold) o cree una directiva de retención de Microsoft 365 para toda la organización.

 **P. ¿Qué tipos de grupos se admiten?**

R. Se admiten grupos de distribución, grupos de seguridad habilitados para correo y grupos de distribución dinámicos.

 **P. ¿Existe un límite en la cantidad de destinatarios del grupo de distribución que se amplía y se almacena en el mensaje?**

R. Se conservan hasta 10.000 miembros de un grupo de distribución.

 **P. ¿Se admiten los grupos de distribución anidados?**

R. Sí, se expanden 25 niveles de grupos de distribución anidados.

 **P. ¿Dónde se puede ver la información de los destinatarios del grupo de distribución expandido y CCO?**

R. La información de los destinatarios CCO y del grupo de distribución expandido aparece visible para los responsables del cumplimiento normativo cuando se realiza una búsqueda de exhibición de documentos electrónicos. Los destinatarios CCO y del grupo de distribución expandido se incluyen en los resultados de la búsqueda que se hayan copiado en un buzón de correo de detección o se hayan exportado a un archivo PST y en el registro de exhibición de documentos electrónicos incluidos en los resultados de la búsqueda. La información de los destinatarios CCO también se encuentra disponible en la vista previa de la búsqueda.

 **P. ¿Qué ocurre si se oculta un miembro de un grupo de distribución de lista global de direcciones de la organización (GAL)?**

R. No pasa nada. Si los destinatarios están ocultos en la GAL, siguen incluidos en la lista de destinatarios del grupo de distribución expandido.
