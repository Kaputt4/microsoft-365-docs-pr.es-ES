---
title: Introducción a las experiencias de tema (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Información general sobre las experiencias de tema.
ms.openlocfilehash: 46f98a9a247160d73e52c51df5f3001aa2f0f6e0
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094824"
---
# <a name="topic-experiences-overview-preview"></a>Introducción a las experiencias de tema (versión preliminar)

> [!Note] 
> El contenido de este artículo es para Project Cortex Private Preview. [Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).

Las experiencias de tema usan la tecnología de IA de Microsoft, Microsoft 365, Microsoft Graph, Búsqueda y otros componentes y servicios para crear una red de conocimiento en su entorno de Microsoft 365. 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

</br>

Su objetivo es convertir la información en conocimientos y entregarla a los usuarios en aplicaciones que usan todos los días, como páginas modernas de SharePoint y Búsqueda de Microsoft.

Las experiencias de tema ayudan a abordar un problema empresarial clave en muchas empresas, ya que proporcionan la información a los usuarios cuando la necesitan. Por ejemplo, los nuevos empleados necesitan aprender una gran cantidad de información nueva rápidamente y encontrar términos de los que no saben nada al leer la información de la empresa. Para obtener más información, es posible que el usuario deba alejarse de lo que está haciendo y dedicar tiempo valioso a buscar detalles, como información sobre cuál es el término, quién en la organización es experto en la materia y quizás sitios y documentos relacionados con el término.

Las experiencias de tema usan la inteligencia artificial para buscar e identificar automáticamente **los temas** de la organización. Compila información sobre ellos, como una breve descripción, personas que trabajan en el tema y sitios, archivos y páginas relacionados con él. Un administrador de conocimientos o colaborador puede elegir actualizar la información del tema según sea necesario. Los temas están disponibles para los usuarios, lo que significa que para cada instancia del tema que aparece en un sitio de SharePoint moderno en noticias y páginas, se resaltará el texto. Los usuarios pueden elegir seleccionar el tema para obtener más información sobre él a través de los detalles del tema. Los temas también se pueden encontrar en La búsqueda de SharePoint.


## <a name="how-topics-are-displayed-to-users"></a>Cómo se muestran los temas a los usuarios

Cuando se menciona un tema en el contenido de las noticias y páginas de SharePoint, lo verá resaltado. Puede abrir el resumen del tema desde el resaltado. Abra los detalles del tema desde el título del resumen. El tema mencionado podría identificarse automáticamente o agregarse a la página con una referencia directa al tema por parte del autor de la página. 

   ![Aspectos destacados del tema](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a>Indización de conocimientos

Las experiencias de tema usan la tecnología de IA de Microsoft para identificar **temas** en su entorno de Microsoft 365.

Un tema es una frase o término que es importante o importante para la organización. Tiene un significado específico para la organización y tiene recursos relacionados con ella que pueden ayudar a los usuarios a comprender lo que es y encontrar más información sobre ella. Hay muchos tipos diferentes de temas que serán importantes para su organización. Inicialmente, la tecnología de inteligencia artificial de Microsoft se centra en los siguientes tipos:
- Project
- Evento
- Organización
- Ubicación
- Producto
- Trabajo creativo
- Campo de estudio


Cuando se identifica un tema y la inteligencia artificial determina que tiene  suficiente información para que sea un tema sugerido, una página de tema muestra la información que se recopila a través de la indización de temas, como:

- Nombres alternativos o acrónimos.
- Breve descripción del tema.
- Personas que puedan tener conocimientos sobre el tema.
- Archivos, páginas y sitios relacionados con el tema.

Los administradores de conocimientos pueden elegir rastrear todos los sitios de SharePoint de su espacio empresarial para obtener temas o seleccionar solo algunos.

Consulta [Detección y conservación de temas](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)

## <a name="roles"></a>Roles

Cuando use experiencias de tema en su entorno de Microsoft 365, los usuarios tendrán los siguientes roles:

- Visores de temas: usuarios que podrán ver los puntos destacados del  tema en los sitios modernos de SharePoint a los que tienen al menos acceso de lectura y en Microsoft Search. Podrán seleccionar los resaltados de temas para ver los detalles del tema en las páginas del tema. Los visores de temas podrán proporcionar comentarios sobre lo útil que es un tema para ellos.

- Colaboradores: usuarios que tienen derechos para editar temas existentes o crear otros nuevos. Los administradores de conocimientos asignan permisos de colaborador a los usuarios a través de la configuración de experiencias de tema en el Centro de administración de Microsoft 365. Tenga en cuenta que también puede conceder a todos los visores de temas permiso para editar y crear temas para que todos puedan contribuir a los temas que ven.

- Administradores de conocimientos: usuarios que guían los temas durante el ciclo de vida del tema. Los administradores  de conocimientos usan la página Administrar temas en el Centro de temas para confirmar temas sugeridos por IA, quitar temas que ya no son relevantes, así como editar temas existentes o crear otros nuevos, y son los únicos usuarios que tienen acceso a él. Los administradores de conocimientos asignan permisos de administrador de conocimientos a los usuarios a través de la configuración de administración de experiencias de tema en el Centro de administración de Microsoft 365. 

- Administradores del conocimiento: los administradores de conocimientos establecen las experiencias de tema y las administran a través de los controles de administración en el Centro de administración de Microsoft 365. Actualmente, un administrador global o de SharePoint de Microsoft 365 puede actuar como administrador de conocimientos.

Vea [roles de experiencias de](topic-experiences-roles.md) tema para obtener más información.

## <a name="topic-management"></a>Administración de temas

La administración de temas se realiza en **la página Administrar temas** en el Centro de temas de su **organización.** El Centro de temas se crea durante la instalación y sirve como centro de conocimientos para su organización. 

Aunque todos los usuarios con licencia podrán ver los temas con  los que están conectados en el Centro de temas, solo los usuarios con permisos administrar temas (administradores de conocimientos) podrán ver y usar la página Administrar temas.

Los administradores de conocimientos podrán:

- Confirme o quite los temas que se detectaron en su espacio empresarial.
- Cree nuevos temas manualmente según sea necesario (por ejemplo, si no se proporcionó suficiente información para que se detectara a través de AI).
- Editar páginas de temas existentes.</br>

Vea [Administrar temas en el Centro de temas](manage-topics.md) para obtener más información.  


## <a name="admin-controls"></a>Controles de administración

Los controles de administración del Centro de administración de Microsoft 365 le permiten administrar su red de conocimientos. Permiten que un administrador global o de SharePoint de Microsoft 365:

- Controle qué usuarios de su organización pueden ver temas en páginas modernas de SharePoint o en resultados de búsqueda de SharePoint.
- Controlar qué sitios de SharePoint se rastrearán para identificar temas.
- Excluir temas específicos de la búsqueda.
- Controlar qué usuarios pueden administrar los temas en el centro de temas.
- Controlar qué usuarios pueden crear y editar temas.
- Controlar qué usuario podrá ver los temas.

Vea [asignar permisos de usuario,](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions)administrar la [visibilidad de](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)temas y administrar la [detección de temas](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery) para obtener más información acerca de los controles de administración.

## <a name="topic-curation--feedback"></a>Comentarios sobre la & tema

La IA funcionará continuamente para proporcionarle sugerencias para mejorar los temas a medida que se produzcan cambios en su entorno. 

Los usuarios con permisos de edición o creación de temas pueden realizar actualizaciones en las páginas de temas directamente si desean realizar correcciones o agregar información adicional. También pueden agregar nuevos temas que la inteligencia artificial no pudo identificar. Si hay suficiente información sobre estos temas agregados manualmente y AI es capaz de identificar este tipo de tema, las sugerencias adicionales de AI pueden mejorar estos temas agregados manualmente 

Es posible que se pregunte a los usuarios a los que permite tener acceso para ver los temas de su trabajo diario si el tema les resultaba útil. El sistema examina estas respuestas y las usa para mejorar el resaltado del tema y ayuda a determinar lo que se muestra en los resúmenes de temas y en los detalles del tema.

Además, los usuarios con permisos adecuados pueden etiquetar elementos como la conversación de Yammer que son relevantes para un tema y agregarlos a un tema específico. 

Consulta [Detección y conservación de temas](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)


## <a name="see-also"></a>Consulte también

