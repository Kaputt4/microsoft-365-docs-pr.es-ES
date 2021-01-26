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
ms.openlocfilehash: decc1a3aa5535b4d8bc97dc7d6b010eedd395741
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976596"
---
# <a name="topic-experiences-overview-preview"></a>Introducción a las experiencias de tema (versión preliminar)

> [!Note] 
> El contenido de este artículo es para Project Cortex Private Preview. [Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).

Las experiencias de tema usan la tecnología de IA de Microsoft, Microsoft 365, Delve, Microsoft Graph, Búsqueda y otros componentes y servicios para crear una red de conocimiento en su entorno de Microsoft 365. 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

</br>

Su objetivo es convertir la información en conocimientos y entregarla a los usuarios en aplicaciones que usan todos los días, como páginas modernas de SharePoint y Búsqueda de Microsoft.

Las experiencias de tema ayudan a solucionar un problema empresarial clave en muchas empresas, ya que proporcionan la información a los usuarios cuando la necesitan. Por ejemplo, los nuevos empleados necesitan aprender una gran cantidad de información nueva rápidamente y encontrar términos de los que no saben nada al leer la información de la empresa. Para obtener más información, es posible que el usuario deba alejarse de lo que está haciendo y dedicar tiempo valioso a buscar detalles, como información sobre cuál es el término, quién en la organización es experto en la materia y quizás sitios y documentos relacionados con el término.

Las experiencias de tema usan la inteligencia artificial para buscar e identificar automáticamente **los temas** de la organización. Compila información sobre ellos, como una breve descripción, expertos en la materia sobre el tema y sitios, archivos y páginas relacionados con él. Un administrador de conocimientos o colaborador puede elegir actualizar la información del tema según sea necesario. Los temas están disponibles para los usuarios, lo que significa que para cada instancia del tema que aparece en un sitio de SharePoint moderno en noticias y páginas, se resaltará el texto. Los usuarios pueden elegir seleccionar el tema para obtener más información sobre él a través de los detalles del tema. Los temas también se pueden encontrar en La búsqueda de SharePoint.


## <a name="how-topics-are-displayed-to-users"></a>Cómo se muestran los temas a los usuarios

Cuando se menciona un tema en el contenido de las noticias y páginas de SharePoint, lo verá resaltado. Puede abrir el resumen del tema desde el resaltado. Abra los detalles del tema desde el título del resumen. El tema mencionado podría identificarse automáticamente o agregarse a la página con una referencia directa al tema por parte del autor de la página. 

   ![Aspectos destacados del tema](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a>Indización de conocimientos

Las experiencias de tema usan la tecnología de IA de Microsoft para identificar **temas** en su entorno de Microsoft 365.

Un tema es una frase o término que es importante o importante para la organización. Tiene un significado específico para la organización y tiene recursos relacionados con ella que pueden ayudar a los usuarios a comprender qué es y encontrar más información al respecto.

Cuando se identifica un tema y la inteligencia artificial determina que tiene  suficiente información para que sea un tema sugerido, se crea una página de tema para él que contiene información que se recopila a través de la indización de temas, como:

- Nombres alternativos o acrónimos.
- Breve descripción del tema.
- Usuarios que pueden tener conocimientos sobre el tema.
- Archivos, páginas y sitios relacionados con el tema.

Los administradores de conocimientos pueden elegir rastrear todos los sitios de SharePoint de su espacio empresarial para obtener temas o seleccionar solo algunos.

## <a name="roles"></a>Roles

Al usar experiencias de tema en el entorno de Microsoft 365, los usuarios tendrán los siguientes roles:

- Visor de temas: usuarios que podrán ver los puntos destacados del  tema en los sitios modernos de SharePoint a los que tienen al menos acceso de lectura y en Microsoft Search. Podrán seleccionar los resaltados de temas para ver los detalles del tema en las páginas del tema. Los visores de temas podrán proporcionar comentarios sobre lo útil que es un tema para ellos.

- Colaboradores: usuarios que tienen derechos para editar temas existentes o crear otros nuevos. Los administradores de conocimientos asignan permisos de colaborador a los usuarios a través de la configuración de experiencias de tema en el Centro de administración de Microsoft 365. Tenga en cuenta que también puede conceder a todos los visores de temas permiso para editar y crear temas para que también puedan contribuir a los temas que ven.

- Administradores de conocimientos: usuarios que guían los temas durante el ciclo de vida del tema. Los administradores  de conocimientos usan la página Administrar temas en el Centro de temas para confirmar o quitar temas sugeridos por IA, así como editar temas existentes o crear otros nuevos, y son los únicos usuarios que tienen acceso a él. Los administradores de conocimientos asignan permisos de administrador de conocimientos a los usuarios a través de la configuración de administración de experiencias de tema en el Centro de administración de Microsoft 365. 

- Administradores del conocimiento: los administradores de conocimientos establecen las experiencias de tema y las administran a través de los controles de administración en el Centro de administración de Microsoft 365. Actualmente, un administrador global o de SharePoint de Microsoft 365 puede actuar como administrador de conocimientos.

Vea [roles de experiencias de](topic-experiences-roles.md) tema para obtener más información.

## <a name="topic-management"></a>Administración de temas

La administración de temas se realiza en **la página Administrar temas** en el Centro de temas de su **organización.** El Centro de temas se crea durante la instalación y sirve como centro de conocimientos para su organización. 

Aunque todos los usuarios con licencia podrán ver los temas con  los que están conectados en el Centro de temas, solo los usuarios con permisos administrar temas (administradores de conocimientos) podrán ver y usar la página Administrar temas.

Los administradores de conocimientos podrán:

- Confirme o rechace los temas que se detectaron en el espacio empresarial.
- Cree nuevos temas manualmente según sea necesario (por ejemplo, si no se proporcionó suficiente información para que se detectara a través de AI).
- Editar páginas de temas existentes.</br>

Vea [Administrar temas en el Centro de temas](manage-topics.md) para obtener más información.  


## <a name="admin-controls"></a>Controles de administración

Los controles de administración del Centro de administración de Microsoft 365 le permiten administrar su red de conocimientos. Permiten que un administrador global o de SharePoint de Microsoft 365:

- Controle qué usuarios de su organización pueden ver temas en páginas modernas de SharePoint o en resultados de búsqueda de SharePoint.
- Controlar qué sitios de SharePoint se rastrearán para buscar temas.
- Configurar la detección de temas para excluir temas específicos de la búsqueda.
- Controlar qué usuarios pueden administrar los temas en el centro de temas.
- Controlar qué usuarios pueden crear y editar temas en el centro de temas.
- Controlar qué usuario podrá ver los temas.

Vea [asignar permisos de usuario,](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions)administrar la [visibilidad de](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)temas y administrar la [detección de temas](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery) para obtener más información acerca de los controles de administración.

## <a name="topic-curation--feedback"></a>Comentarios sobre la & tema

La IA funcionará continuamente para proporcionarle sugerencias para mejorar los temas a medida que se produzcan cambios en su entorno. 

Es posible que se pregunte a los usuarios a los que permite tener acceso para ver los temas de su trabajo diario si les resultaba útil. La inteligencia artificial examina estas respuestas y las usa para ayudar a determinar lo que se muestra en los resúmenes de temas y en los detalles del tema.

Los usuarios con permisos de edición o creación de temas pueden realizar actualizaciones en las páginas de temas directamente si desean realizar correcciones o agregar información adicional. 

Además, los usuarios con permisos adecuados pueden etiquetar elementos como la conversación de Yammer que son relevantes para un tema y agregarlos a un tema específico. 


## <a name="see-also"></a>Consulte también

