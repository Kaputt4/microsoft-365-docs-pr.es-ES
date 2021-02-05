---
title: 'Detección y conservación de temas de Temas de Microsoft Viva  '
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
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 435544de1016552c6ce3d39c73f7127223f36331
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107713"
---
# <a name="microsoft-viva-topics-discovery-and-curation"></a>Detección y conservación de temas de Microsoft Viva 

Viva Topics organiza la información a los conocimientos en su entorno de Microsoft 365. Hemos experimentado la lectura a través de documentos y páginas del sitio donde encontramos términos con los que no estamos familiarizados. Muchas veces detenemos lo que estamos haciendo para dedicar mucho tiempo a buscar más información.

Viva Topics usa Microsoft Graph y AI para identificar **los temas** de su organización.  Un tema es una frase o término que tiene un significado específico para la organización y tiene recursos relacionados con él que pueden ayudar a los usuarios a comprender lo que es y encontrar más información al respecto. Hay muchos tipos diferentes de temas que serán importantes para su organización. Inicialmente, se pueden identificar los siguientes tipos de temas:
- Project
- Evento
- Organización
- Ubicación
- Producto
- Trabajo creativo
- Campo de estudio

La inteligencia artificial identifica a las personas y el contenido conectados al tema y, si se detecta suficiente, se convierte en un tema sugerido. Busca identificar las siguientes propiedades y mostrarlas en una **página de tema:**
- Nombres alternativos o acrónimos.
- Breve descripción del tema.
- Personas que puedan tener conocimientos sobre el tema.
- Archivos, páginas y sitios relacionados con el tema.

Las propiedades se identifican a partir de los archivos y páginas que forman parte de la evidencia para identificar el tema. Los nombres alternativos y los acrónimos se encuentran en estos archivos y páginas. La descripción breve se encuentra en estos archivos y páginas, o desde Internet a través de Wikipedia. Se hace referencia al archivo de origen, página o artículo de Wikipedia junto con las propiedades sugeridas. Las personas se sugieren en función de sus contribuciones activas (por ejemplo, ediciones) a los archivos y páginas. Una referencia a la cantidad de contribuciones de una persona determinada proporciona una sugerencia sobre por qué se ha identificado a la persona. Los archivos, las páginas y los sitios se clasifican en función de si son fundamentales para el tema, si pueden proporcionar información general o una introducción al tema. 

No todos los temas identificados serán útiles para su organización. Es posible que no haya identificado ninguno de los nombres, descripciones, personas o contenido alternativos correctos. Por lo tanto, la capacidad de agregar temas que no se identifican, mantener temas sugeridos y conservar temas es fundamental para mejorar la calidad de los temas que se pueden detectar en su organización.

A continuación, Cuando el contexto sea adecuado, Temas Viva sugerirá que estos temas se resalte en todas las páginas de sitio modernas de SharePoint en su espacio empresarial. El autor de la página también puede hacer referencia directamente al tema en la página del sitio moderno de SharePoint. Cuando un usuario tiene curiosidad por obtener más información sobre un  tema, puede seleccionar el tema resaltado para ver una tarjeta de resumen de tema que proporciona una breve descripción. Y si quieren obtener más información, pueden seleccionar un vínculo **Detalles** del tema en el resumen para abrir la página de temas detallada.

![Aspectos destacados del tema](../media/knowledge-management/saturn.png) </br>

Además, los usuarios también podrán encontrar temas a través de Microsoft Search.

## <a name="topic-curation-and-feedback"></a>Comentarios y conservación de temas

Temas Viva agradece la contribución humana para mejorar la calidad de sus temas. Aunque la inteligencia artificial identifica y sugiere temas inicialmente, las modificaciones realizadas manualmente en el contenido de colaboradores, los temas agregados manualmente, la confirmación de los usuarios para las propiedades y el contenido detectados por la IA, y los comentarios sobre la utilidad de los temas son esenciales.

- Los administradores de conocimientos de su organización pueden **revisar** los temas. El administrador de conocimientos puede revisar los temas que tienen permisos para ver. En la página Administrar temas del Centro de temas, pueden elegir confirmar los temas generados por IA ("temas sugeridos") como válidos, rechazar los temas para evitar que el contenido se vea como un tema, crear temas que no fueron detectados por AI o identificar los temas que podrían beneficiarse de algunas modificaciones de expertos en la materia para que sean más útiles o precisos. Para obtener más información, vea [Administrar temas en el Centro de temas.](manage-topics.md)

- Puede asignar permisos de creación y *edición* de temas a cualquiera de los usuarios con licencia para que puedan realizar cambios en los temas existentes o crear nuevos temas. Esto permite a los usuarios que tienen conocimientos sobre el tema actualizar la página del tema directamente para realizar correcciones o agregar información adicional. También pueden agregar nuevos temas que la inteligencia artificial no pudo identificar. Si hay suficiente información sobre estos temas agregados manualmente y AI es capaz de identificar este tipo de tema, las sugerencias adicionales de AI pueden mejorar estos temas agregados manualmente. Juntos, las personas y la inteligencia artificial pueden mantener la precisión de los conocimientos con el tiempo y no tener este reposo en una sola persona. Para obtener más información, [vea Crear un nuevo tema](https://docs.microsoft.com/microsoft-365/knowledge/create-a-topic) y Editar un [tema.](https://docs.microsoft.com/microsoft-365/knowledge/edit-a-topic)

- Incluso a los usuarios que solo tienen acceso de lectura a un tema (visores de temas) se les pedirá que comprueben la utilidad de temas específicos. Las preguntas sobre comentarios se preguntan en **la tarjeta de resumen** del tema para mejorar el valor del tema y su información. Las preguntas sobre la calidad y la utilidad de las sugerencias de IA se presentan a los usuarios de una en una. Entre las preguntas se incluyen:</br>

    1. Indica si es útil identificar el tema en la página de SharePoint. Hay una oportunidad de quitar el resaltado si no es preciso o útil. Si hay suficientes personas que indican que un tema no se ha identificado correctamente en una página determinada, este resaltado se quitará finalmente para todos los usuarios. 

    2. Si el tema sugerido es útil para la organización. Si hay suficientes personas que indican que el tema sugerido es valioso, el tema se confirma automáticamente. Como alternativa, si el tema sugerido no es útil, el tema se rechaza automáticamente. El Administrador de conocimientos puede observar esta actividad en la vista Administrar temas.

    3. Si las sugerencias de personas y recursos son útiles.

    4. En la página principal del Centro de temas, puede ver los temas de su organización a los que tiene una conexión. Puede optar por seguir en la lista del tema o quitarse. Estos comentarios se reflejan para todos los usuarios que descubran este tema. Vea [información general del Centro de](https://docs.microsoft.com/microsoft-365/knowledge/topic-center-overview) temas para obtener más información en la página principal del centro de temas.

Incluso con las ediciones humanas, la inteligencia artificial buscará continuamente más información sobre los temas y buscará la verificación humana. Por ejemplo, si AI cree que es una persona que debe aparecer como experto en un tema, le pedirá que lo confirme. 


## <a name="see-also"></a>Consulte también
