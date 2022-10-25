---
title: Conservar los destinatarios de grupos de distribución expandidos y CCO para la exhibición de documentos electrónicos
description: In-Place directivas de suspensión, suspensión por juicio y retención de Microsoft 365 le permiten conservar el contenido del buzón para cumplir los requisitos normativos de cumplimiento y exhibición de documentos electrónicos.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
- ediscovery
ms.openlocfilehash: c68058974afb19778aa5674ae1217b6163ea0504
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687980"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>Conservar los destinatarios de grupos de distribución expandidos y CCO para la exhibición de documentos electrónicos
  
Las retenciones por litigio, las retenciones de eDiscovery y [las directivas de retención de Microsoft 365](./retention.md) creadas en el portal de cumplimiento Microsoft Purview permiten conservar el contenido del buzón para cumplir los requisitos normativos y de exhibición de documentos electrónicos. De forma predeterminada, la información sobre los destinatarios que se abordan directamente en los campos To y Cc de un mensaje se incluye en todos los mensajes. Pero su organización puede requerir la capacidad de buscar y reproducir detalles sobre todos los destinatarios de un mensaje. Esto incluye lo siguiente:
  
- **Destinatarios abordados mediante el campo CCO de un mensaje:** Los destinatarios CCO se almacenan en el mensaje en el buzón del remitente, pero no se incluyen en los encabezados del mensaje entregado a los destinatarios.
- **Destinatarios de grupos de distribución expandidos:** Destinatarios que reciben el mensaje porque son miembros de un grupo de distribución al que se ha dirigido el mensaje, ya sea en los campos To, Cc o Bcc.

Exchange Online y Exchange Server 2013 (actualización acumulativa 7 y versiones posteriores) conservan información sobre Bcc y los destinatarios de grupos de distribución expandidos. Puede buscar esta información mediante una herramienta eDiscovery en el portal de cumplimiento.
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Forma de conservación de los destinatarios CCO y los destinatarios del grupo de distribución expandido

La información sobre los destinatarios cco se almacena con el mensaje en el buzón del remitente. Esta información se indexa y está disponible para las búsquedas y retenciones de eDiscovery.

La información sobre los destinatarios del grupo de distribución expandido se almacena con el mensaje después de que se coloca en un buzón de correo en conservación local o retención por juicio. En Microsoft 365, esta información también se almacena cuando se aplica una directiva de retención de Microsoft Purview a un buzón. La pertenencia al grupo de distribución se determina en el momento en el que se envía el mensaje. La lista de destinatarios expandida almacenada con el mensaje no se ve afectada por los cambios en la pertenencia al grupo después de enviar el mensaje.

|Información sobre...|Se almacena en...|¿se almacena de forma predeterminada?|Es accesible para...|
|:-------------------|:--------------|:--------------------|:------------------|
|Para: y Cc: destinatarios|Propiedades del mensaje en los buzones de correo del remitente y los destinatarios|Sí|Remitente, destinatarios y responsables de cumplimiento normativo|
|Cco: destinatarios|Propiedad del mensaje en el buzón de correo del remitente|Sí|Remitente y responsables de cumplimento normativo|
|Destinatarios del grupo de distribución expandido|Propiedades del mensaje en el buzón de correo del remitente|No. La información de destinatarios del grupo de distribución expandido se almacena después de colocar un buzón en In-Place suspensión o suspensión por juicio, o se asigna a una directiva de retención de Microsoft Purview.|Responsables del cumplimiento normativo|

## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Buscar mensajes enviados a destinatarios CCO y del grupo de distribución expandido

When searching for messages sent to a recipient, eDiscovery search results now include messages sent to a distribution group that the recipient is a member of. The following table shows the scenarios where messages sent to Bcc and expanded distribution group recipients are returned in eDiscovery searches.

**Escenario 1**: Juan es miembro del grupo de distribución US-Sales. En esta tabla se muestran los resultados de la búsqueda de exhibición de documentos electrónicos cuando Bob envía un mensaje a John directa o indirectamente a través de un grupo de distribución.

|Al buscar mensajes enviados en el buzón de Bob...|Y el mensaje se envía con...|¿Los resultados incluyen el mensaje?|
|---|---|---|
|Para: Juan|Juan en A:|Sí|
|Para: Juan|US-Sales en Para:|Sí|
|Para: US-Sales|US-Sales en Para:|Sí|
|Cc: John|John en Cc:|Sí|
|Cc: John|US-Sales en Cc:|Sí|
|Cc: US-Sales|US-Sales en Cc:|Sí|

**Escenario 2**: Bob envía un correo electrónico a John (To/Cc) y Jack (CCO directa o indirectamente a través de un grupo de distribución). En la tabla siguiente se muestran los resultados de búsqueda de la exhibición de documentos electrónicos.

|Al buscar...|Para los mensajes enviados...|¿Los resultados incluyen el mensaje?|Notas|
|---|---|---|---|
|Buzón de correo de Bob|To:/Cc: John|Sí|Presenta una indicación de que Jack se incluyó en CCO.|
|Buzón de correo de Bob|Cco: Jack|Sí|Presenta una indicación de que Jack se incluyó en CCO.|
|Buzón de correo de Bob|Cco: Jack (a través del grupo de distribución)|Sí|La lista de miembros del grupo de distribución CCO, expandido cuando se envió el mensaje, está visible en la vista previa, exportación y registros de la búsqueda de eDiscovery.|
|Buzón de correo de John|To:/Cc: John|Sí|Sin indicación de los destinatarios CCO.|
|Buzón de correo de John|Cco: Jack (directamente o a través del grupo de distribución)|No|Cco: la información no se almacena en el mensaje entregado a los destinatarios. Debe buscar en el buzón de correo del remitente.|
|Buzón de correo de Jack|To:/Cc: John (directamente o a través del grupo de distribución)|Yes|Para:/Cc: la información se incluye en el mensaje entregado a todos los destinatarios.|
|Buzón de correo de Jack|Cco: Jack (directamente o a través del grupo de distribución)|No|Cco: la información no se almacena en el mensaje entregado a los destinatarios. Debe buscar en el buzón de correo del remitente.|

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Cuándo y dónde se almacena la información del destinatario de CCO?**

La información de CCO se conserva de forma predeterminada en el mensaje original en el buzón de correo del remitente. Si el destinatario de cco es un grupo de distribución, la pertenencia a grupos de distribución solo se expande si el buzón del remitente está en espera o asignado a una directiva de retención de Microsoft 365.

**¿Cuándo y dónde se almacena la lista de destinatarios del grupo de distribución expandido?**

La pertenencia al grupo se expande en el momento en el que se envía el mensaje. La lista de miembros del grupo de distribución expandido se almacena en el mensaje original en el buzón de correo del remitente. El buzón del remitente debe estar en In-Place suspensión, suspensión por juicio o estar asignado a una directiva de retención de Microsoft 365.

**¿Pueden los destinatarios de to/cc ver qué destinatarios eran cco'ed?**

No. Esta información no se incluye en los encabezados de mensaje y no es visible para los destinatarios de To/Cc. El remitente puede ver el campo CCO almacenado en el mensaje original almacenado en el buzón de correo. Los responsables de cumplimento normativo pueden ver esta información cuando buscan en el buzón de correo del remitente.

**¿Cómo puedo asegurarme de que los destinatarios del grupo de distribución expandido siempre se conserven?**

Para asegurarse de que los miembros del grupo de distribución expandido siempre se conservan con un mensaje, [coloque todos los buzones en espera](/Exchange/policy-and-compliance/holds/place-all-mailboxes-on-hold) o cree una directiva de retención de Microsoft 365 para toda la organización.

**¿Qué tipos de grupos se admiten?**

Se admiten grupos de distribución, grupos de seguridad habilitados para correo y grupos de distribución dinámicos.

**¿Hay un límite en el número de destinatarios del grupo de distribución que se expanden y almacenan en el mensaje?**

Se conservan hasta 10.000 miembros de un grupo de distribución.

**¿Se admiten los grupos de distribución anidados?**

Sí, se expanden 25 niveles de grupos de distribución anidados.

**¿Dónde está visible la información del destinatario del grupo de distribución ampliado y CCO?**

La información de los destinatarios CCO y del grupo de distribución expandido aparece visible para los responsables del cumplimiento normativo cuando se realiza una búsqueda de exhibición de documentos electrónicos. Los destinatarios CCO y del grupo de distribución expandido se incluyen en los resultados de la búsqueda que se hayan copiado en un buzón de correo de detección o se hayan exportado a un archivo PST y en el registro de exhibición de documentos electrónicos incluidos en los resultados de la búsqueda. La información de los destinatarios CCO también se encuentra disponible en la vista previa de la búsqueda.

**¿Qué ocurre si un miembro de un grupo de distribución está oculto de la lista global de direcciones (GAL) de la organización?**

No pasa nada. Si los destinatarios están ocultas en la GAL, todavía se incluirán en la lista de destinatarios del grupo de distribución expandido.
