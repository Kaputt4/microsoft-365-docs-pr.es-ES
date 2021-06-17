---
title: Información general de Temas Microsoft Viva
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: cjtan; lauris
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Información general de Temas Viva.
ms.openlocfilehash: 785fddb7c951bb6f7c170971f0af4eb7ac8f9a83
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984909"
---
# <a name="microsoft-viva-topics-overview"></a>Información general de Temas Microsoft Viva 

Viva Topics usa la tecnología de inteligencia artificial de Microsoft, Microsoft 365, Microsoft Graph, Búsqueda y otros componentes y servicios para aportar conocimiento a los usuarios en las aplicaciones de Microsoft 365 que usan todos los días, empezando por SharePoint páginas modernas, Búsqueda de Microsoft y Búsqueda en Word, PowerPoint, Outlook y Excel.

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

<br/>

Viva Topics ayuda a abordar un problema empresarial clave en muchas empresas, ya que proporciona la información a los usuarios cuando la necesitan. Por ejemplo, los nuevos empleados necesitan obtener mucha información nueva rápidamente y se encuentran con términos que no conocen al leer el contenido de la compañía. Para obtener más información, es posible que el usuario deba dejar lo que está haciendo y dedicar un tiempo valioso a buscar detalles, como información sobre qué es el término, quién en la organización es un experto en la materia y quizás sitios y documentos relacionados con el término.

Temas Viva usa inteligencia artificial para buscar e identificar automáticamente *temas* en su organización. Compilan información sobre ellos, como una breve descripción, personas que trabajan en el tema y sitios, archivos y páginas relacionados con él. Un gestores de información o colaborador puede actualizar la información del tema según sea necesario. Los temas están disponibles para los usuarios, lo que significa que, para cada instancia del tema que aparece en las noticias y páginas de un sitio moderno de SharePoint, el texto se resaltará. Los usuarios pueden seleccionar el tema para obtener más información sobre él en los detalles del tema. Los temas también pueden encontrarse en la búsqueda de SharePoint.

## <a name="how-topics-are-displayed-to-users"></a>Cómo se muestran los temas a los usuarios

Los temas se muestran a los usuarios a través de:

- [Temas resaltados](topic-experiences-overview.md#sharepoint-highlights) en SharePoint páginas
- Respuestas de temas en [los resultados de búsqueda](topic-experiences-overview.md#search-results)
- Búsqueda en [aplicaciones de office](topic-experiences-overview.md#office-application-search)
- [Página principal del centro](topic-experiences-overview.md#topic-center) de temas

### <a name="sharepoint-highlights"></a>SharePoint destacados

Cuando se menciona un tema en el contenido de noticias y páginas de SharePoint, lo verá resaltado. Puede abrir el resumen del tema desde el contenido resaltado. Abra los detalles del tema desde el título del resumen para ver la página de tema completa. El tema mencionado podría identificarse automáticamente o el autor de la página podría haber hecho referencia directamente al tema. 

   ![Captura de pantalla que muestra los aspectos destacados del tema.](../media/knowledge-management/saturn.png) 

### <a name="search-results"></a>Resultados de la búsqueda

Puede ver [](search.md#topic-answer) una respuesta de tema en los resultados de la búsqueda cuando busca desde la página de inicio de SharePoint, la búsqueda en Office.com o la búsqueda desde un sitio de SharePoint después de cambiar el ámbito de búsqueda para incluir la organización completa. La respuesta al tema aparecerá en el tema de la lista de resultados y le dará un breve conjunto de información relacionada con ese tema. 

   ![Captura de pantalla que muestra los resultados de una búsqueda SharePoint sitio web.](../media/knowledge-management/site-search-results.png) 

### <a name="office-application-search"></a>Office búsqueda de aplicaciones

Cuando usas la búsqueda en aplicaciones de Office como Word, PowerPoint, Outlook o Excel, ya sea a  través del cuadro de búsqueda o seleccionando Buscar en el menú contextual, las respuestas de los temas se muestran en los resultados de la búsqueda.

   ![Captura de pantalla que muestra la búsqueda en Word a través del cuadro Buscar.](../media/knowledge-management/word-search-2.png)

   ![Captura de pantalla que muestra la búsqueda en Word a través del menú contextual Buscar.](../media/knowledge-management/word-search-1.png)

### <a name="topic-center"></a>Centro de temas

Los usuarios pueden ver los temas de su organización a los que tienen una conexión en la página principal [del centro de temas](topic-center-overview.md#home-page).

## <a name="knowledge-indexing"></a>Indexación de información

Temas Viva usa tecnología de inteligencia artificial de Microsoft para identificar los *temas* de su entorno de Microsoft 365.

Un tema es una frase o un término que es significativo o importante para la organización. Tiene un significado específico en la organización y cuenta con recursos relacionados que pueden ayudar a comprender qué es y a encontrar más información acerca de él. Hay muchos tipos diferentes de temas que serán importantes para su organización. Inicialmente, la tecnología de inteligencia artificial de Microsoft se centra en los siguientes tipos:

- Proyecto
- Evento
- Organización
- Ubicación
- Producto
- Trabajo creativo
- Campo de estudio

Cuando se identifica un tema y la inteligencia artificial determina que tiene suficiente información para que sea un tema sugerido, una *página de tema* muestra la información que se ha recopilado a través de la indexación del tema, como la siguiente:

- Nombres y acrónimos alternativos.
- Breve descripción del tema.
- Personas que puedan tener más información sobre el tema.
- Archivos, páginas y sitios relacionados con el tema.

Los administradores de información pueden rastrear todos los sitios de SharePoint de su espacio empresarial por temas o seleccionar algunos determinados.

Para obtener más información, vea [Detección de temas y curación.](./topic-experiences-discovery-curation.md)

## <a name="roles"></a>Funciones

Al usar Temas Viva en su entorno de Microsoft 365, los usuarios tendrán las siguientes funciones:

- Visualizadores de temas: Usuarios que pueden ver contenido destacado de los temas en sitios modernos de SharePoint para los que tengan al menos acceso de *Lectura* y en Búsqueda de Microsoft. Pueden seleccionar el contenido destacado de un tema para ver los detalles del mismo en las páginas de temas. Los visualizadores de temas pueden aportar comentarios sobre lo útil que les resulta un tema a ellos.

- Colaboradores: Usuarios que tienen permisos para editar los temas existentes o crear nuevos. Los administradores de información asignan permisos de colaborador a los usuarios a través de la configuración de Temas Viva en el Centro de administración de Microsoft 365. Tenga en cuenta que también puede dar permiso a todos los visualizadores de temas para editar y crear temas para que todos puedan colaborar en los temas que ven.

- Gestores de información: Usuarios que guían los temas a través de su ciclo de vida. Los administradores  de conocimientos usan la página Administrar temas del centro de temas para confirmar temas sugeridos por la IA, quitar temas que ya no son relevantes, así como editar temas existentes o crear otros nuevos y son los únicos usuarios que tienen acceso a él. Los administradores de información asignan permisos de gestores de información a los usuarios a través de la configuración de Temas Viva en el Centro de administración de Microsoft 365. 

- Administradores de conocimientos: los administradores establecen Viva Topics y lo administran a través de los controles de administración de la Centro de administración de Microsoft 365. Actualmente, un administrador del servicio SharePoint o global de Microsoft 365 puede servir como administrador del información.

Para obtener más información, vea [Roles de Temas de Viva](topic-experiences-roles.md).

## <a name="topic-management"></a>Administración de temas

La administración de temas se realiza en la **página Administrar temas** del centro de temas de su *organización.* El centro de temas se crea durante la instalación y sirve como centro de conocimiento para su organización. 

Aunque todos los usuarios con licencia pueden ver los temas  con los que están conectados en el centro de temas, solo los usuarios con permisos administrar temas (administradores de conocimientos) pueden ver y usar la página Administrar **temas.**

Los gestores de información pueden realizar las siguientes acciones:

- Confirmar o quitar los temas detectados en su espacio empresarial.
- Crear nuevos temas manualmente según sea necesario (por ejemplo, si no se ha proporcionado suficiente información para que lo detecte la inteligencia artificial).
- Editar páginas de temas existentes.

Para obtener más información, vea [Manage topics in the topic center](manage-topics.md).  

## <a name="admin-controls"></a>Controles de administración

Los controles de administración Centro de administración de Microsoft 365 permiten administrar Temas de Viva. Permiten a un administrador del servicio SharePoint o global de Microsoft 365 realizar las siguientes acciones:

- Controlar qué usuarios de su organización pueden ver temas en las páginas modernas de SharePoint o en los resultados de la búsqueda de SharePoint.
- Controlar los sitios de SharePoint que se rastrearán para identificar temas.
- Excluir temas específicos de la búsqueda.
- Controlar qué usuarios pueden administrar temas en el centro de temas.
- Controlar qué usuarios pueden crear y editar temas.
- Controlar qué usuarios pueden ver temas.

Para obtener más información acerca de los controles de administración, vea [asignar permisos de usuario,](./plan-topic-experiences.md#user-permissions)administrar la [visibilidad del](./topic-experiences-knowledge-rules.md)tema y administrar la [detección de temas.](./topic-experiences-discovery.md)

## <a name="topic-curation--feedback"></a>Comentarios y conservación de temas

La inteligencia artificial trabajará sin descanso para ofrecerle sugerencias para mejorar los temas a medida que se produzcan cambios en su entorno. 

Los usuarios con permisos de edición o creación de temas pueden hacer actualizaciones en las páginas de temas directamente si quieren realizar correcciones o agregar información adicional. También pueden agregar nuevos temas que la inteligencia artificial no ha sido capaz de identificar. Si hay suficiente información sobre estos temas agregados manualmente y AI puede identificar este tipo de tema, las sugerencias adicionales de AI podrían mejorar estos temas agregados manualmente.

Es posible que se pregunte a los usuarios a los que permite acceder a ver temas en su trabajo diario si estos les han resultado útiles. El sistema examina estas respuestas y las usa para mejorar el contenido resaltado del tema y ayudar a determinar lo que se muestra en los resúmenes y detalles de los temas.

Para obtener más información, vea [Detección de temas y curación.](./topic-experiences-discovery-curation.md)

## <a name="see-also"></a>Vea también

[Use Búsqueda de Microsoft para buscar temas en Temas de Viva](./search.md)
