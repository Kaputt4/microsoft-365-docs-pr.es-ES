---
title: 'Detección y curación de temas de Temas de Microsoft Viva  '
description: Información general sobre cómo se detectan los temas.
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 2f4c726849d438738f3c0d432daab53ee27b19ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917433"
---
# <a name="microsoft-viva-topics-discovery-and-curation"></a>Detección y conservación de los temas de Microsoft Viva 

Viva Topics organiza información para conocimientos en su entorno de Microsoft 365. Todos hemos experimentado la lectura a través de documentos y páginas de sitio donde encontramos términos con los que no estamos familiarizados. Muchas veces detenemos lo que estamos haciendo para dedicar tiempo valioso a buscar más información.

Viva Topics usa Microsoft Graph y AI para identificar **temas** de su organización.  Un tema es una frase o término que tiene un significado específico para la organización y tiene recursos relacionados con él que pueden ayudar a las personas a comprender lo que es y a encontrar más información al respecto. Hay muchos tipos diferentes de temas que serán importantes para su organización. Inicialmente, se pueden identificar los siguientes tipos de temas:
- Proyecto
- Evento
- Organización
- Ubicación
- Producto
- Trabajo creativo
- Campo de estudio

La IA identifica las personas y el contenido conectado al tema y, si se detecta suficiente, se convierte en un tema sugerido. Busca identificar las siguientes propiedades y mostrarlas en una **página de tema:**
- Nombres alternativos o acrónimos.
- Breve descripción del tema.
- Personas que puedan tener más información sobre el tema.
- Archivos, páginas y sitios relacionados con el tema.

Las propiedades se identifican a partir de los archivos y páginas que forman parte de la evidencia para identificar el tema. Los nombres y acrónimos alternativos se encuentran en estos archivos y páginas. La breve descripción se origen de estos archivos y páginas, o de Internet a través de Wikipedia. Se hace referencia al archivo de origen, página o artículo de Wikipedia junto con las propiedades sugeridas. Se sugiere a las personas en función de sus contribuciones activas (por ejemplo, ediciones) a los archivos y páginas. Una referencia a la cantidad de contribuciones de una persona determinada proporciona una sugerencia sobre por qué se ha identificado a la persona. Los archivos, páginas y sitios se clasifican en función de si son centrales en el tema, si pueden proporcionar información general o introducción al tema. 

No todos los temas identificados serán útiles para su organización. Es posible que no haya identificado ninguno de los nombres alternativos, descripciones, personas o contenido adecuados. Por lo tanto, la capacidad de agregar temas que no se identifican, mantener temas sugeridos y temas de curación es fundamental para mejorar la calidad de los temas que se pueden detectar en su organización.

A continuación, Viva Topics, cuando el contexto sea adecuado, sugerirá que estos temas se resalten en todas las páginas de sitio modernas de SharePoint del espacio empresarial. El autor de la página también puede hacer referencia directamente al tema en la página del sitio moderno de SharePoint. Cuando un usuario tiene curiosidad por obtener más información sobre un  tema, puede seleccionar el tema resaltado para ver una tarjeta de resumen de tema que proporciona una breve descripción. Y si quieren obtener más información, pueden seleccionar un vínculo **Detalles** del tema en el resumen para abrir la página de temas detallada.

![Contenido destacado del tema](../media/knowledge-management/saturn.png) </br>

Además, los usuarios también podrán encontrar temas a través de Microsoft Search.

## <a name="topic-curation-and-feedback"></a>Curación de temas y comentarios

Viva Topics agradece la contribución humana para mejorar la calidad de los temas. Aunque la IA identifica y sugiere temas inicialmente, las modificaciones realizadas manualmente en el contenido de colaboradores, los temas agregados manualmente, la confirmación de los usuarios sobre las propiedades y el contenido detectados por AI y los comentarios sobre la utilidad de los temas son fundamentales.

- Los jefes de  conocimientos de la organización pueden revisar los temas. El administrador de conocimientos puede revisar los temas que tienen permisos para ver. En la página Administrar temas del Centro de temas, pueden elegir confirmar los temas generados por la IA ("temas sugeridos") como válidos, rechazar temas para evitar que el contenido se vea como un tema, crear temas que no fueron detectados por AI o identificar temas que podrían beneficiarse de algunas ediciones de expertos en la materia para ser más útiles o precisos. Para obtener más información, vea [Administrar temas en el Centro de temas](manage-topics.md).

- Puede asignar permisos *crear y editar temas* a cualquiera de los usuarios con licencia para que puedan realizar cambios en los temas existentes o crear nuevos temas. Esto permite a los usuarios que tienen conocimientos sobre el tema actualizar la página del tema directamente para realizar correcciones o agregar información adicional. También pueden agregar nuevos temas que la inteligencia artificial no ha sido capaz de identificar. Si hay suficiente información sobre estos temas agregados manualmente y AI puede identificar este tipo de tema, las sugerencias adicionales de AI pueden mejorar estos temas agregados manualmente. Juntos, los humanos y la inteligencia artificial pueden mantener el conocimiento preciso con el tiempo y no tener este descanso en una sola persona. Para obtener más información, vea [Create a new topic](./create-a-topic.md) y Edit a [topic](./edit-a-topic.md).

- Incluso a los usuarios que solo tienen acceso de lectura al tema (visores de temas) se les pedirá que comprueben la utilidad de temas específicos. Se preguntan comentarios en la **tarjeta de resumen del** tema para mejorar el valor del tema y su información. Las preguntas sobre la calidad y la utilidad de las sugerencias de IA se presentan a los usuarios de una en una. Entre las preguntas se incluyen:</br>

    1. Es útil identificar el tema en la página de SharePoint. Hay una oportunidad de quitar el resaltado si no es preciso o útil. Si hay suficientes personas que indican que un tema no está identificado correctamente en una página determinada, este resaltado se quitará finalmente para todos los usuarios. 

    2. Si el tema sugerido es valioso para la organización. Si hay suficientes personas que indican que el tema sugerido es valioso, el tema se confirma automáticamente. Como alternativa, si el tema sugerido no es valioso, el tema se rechaza automáticamente. El Administrador de conocimientos puede observar esta actividad en la vista Administrar temas.

    3. Si las personas y las sugerencias de recursos son útiles.

    4. En la página principal del Centro de temas, puede ver los temas de su organización a los que tiene una conexión. Puede optar por seguir en la lista del tema o quitarse usted mismo. Estos comentarios se reflejan en todos los usuarios que descubran este tema. Vea [Información general del centro de temas](./topic-center-overview.md) para obtener más información en la página principal del centro de temas.

Incluso con las ediciones humanas, la IA buscará continuamente más información sobre temas y buscará la verificación humana. Por ejemplo, si AI cree que es una persona que debe aparecer como experto en un tema, le pedirá que lo confirme. 


## <a name="see-also"></a>Consulte también