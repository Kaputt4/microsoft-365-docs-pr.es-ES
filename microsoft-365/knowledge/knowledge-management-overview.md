---
title: Introducción a la administración del conocimiento (vista previa)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Información general sobre la administración del conocimiento en Project Cortex.
ms.openlocfilehash: c4f7ff7d65ec08740dc14f717712731d839bd903
ms.sourcegitcommit: d648356b27842e779921859480b1b405a1804c7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361956"
---
# <a name="knowledge-management-overview-preview"></a>Introducción a la administración del conocimiento (vista previa)

> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).

La administración de conocimiento usa la tecnología de Microsoft AI, Microsoft 365, Delve, búsqueda y otros componentes y servicios para crear una red de conocimiento en el entorno de Microsoft 365. 

   ![Flujo de administración de conocimiento](../media/content-understanding/knowledge-management-flowchart.png) </br> 

El objetivo es proporcionar información a los usuarios en las aplicaciones que usan diariamente, como Outlook, Teams y SharePoint.

Por ejemplo, los usuarios ven términos desconocidos en sus correos electrónicos, sitios de SharePoint o conversaciones en Microsoft Teams, de los que quieren saber más. La administración de conocimiento usa AI para buscar e identificar automáticamente estos **temas**y compila información sobre ellos, como una breve descripción, los expertos en la materia y los sitios, los archivos y las páginas que están relacionados con el tema. Puede optar por actualizar la información del tema según sea necesario. A continuación, puede poner los temas a disposición de los usuarios, lo que significa que, para cada instancia del tema que aparece en aplicaciones como Outlook, Teams y SharePoint, el texto se resaltará. Los usuarios pueden elegir seleccionar el tema para obtener más información mediante el tema detalles.


## <a name="topic-discovery"></a>Detección de temas

La administración de conocimiento usa la tecnología de Microsoft AI para buscar **temas** en su entorno de Office 365.

Un tema es una frase o un término que es importante en cuanto a la organización. Tiene un significado específico para la organización y tiene recursos relacionados con ella que pueden ayudar a los usuarios a comprender lo que es y encontrar más información sobre ella.

Cuando se detecta un tema, se crea una **Página de tema** para el mismo que contiene información que se recopiló a través de la detección de temas, por ejemplo:

- Una breve descripción del tema.
- Usuarios que podrían conocer el tema.
- Archivos, páginas y sitios relacionados con el tema.


## <a name="topic-management"></a>Administración de temas

La administración de temas se lleva a cabo en el **centro de temas**de la organización. El sitio del centro de temas se crea durante la instalación y sirve como centro de conocimientos para su organización. Contendrá una lista de todos los temas que se detectaron en su entorno, así como todas las páginas de temas que se crearon para estos temas. 

Los usuarios que disponen de los permisos correctos podrán hacer lo siguiente en el centro de temas:

- Confirme o rechace los temas que se detectaron en su espacio empresarial.
- Cree temas nuevos de forma manual según sea necesario (por ejemplo, si no se proporcionó suficiente información para que se detectase a través de AI).
- Edite las páginas del tema existentes.</br>

Consulte [trabajar con el tema en el centro de temas](work-with-topics.md) para obtener más información.  


## <a name="admin-controls"></a>Controles de administración

Los controles de administración en el centro de administración de Microsoft 365 le permiten administrar su red de conocimientos. Permiten a un administrador global o de SharePoint de Microsoft 365:

- Controlar qué usuarios de la organización pueden ver temas en sus aplicaciones cliente o en los resultados de la búsqueda de SharePoint.
- Controle los sitios de SharePoint que se rastrearán para buscar temas.
- Configure la detección de temas para excluir términos específicos que no desea que sea un tema.
- Controlar qué usuarios pueden confirmar o rechazar temas en el centro de temas.
- Controlar qué usuarios pueden crear y editar temas en el centro de temas.

Consulte [Manage Your Knowledge Network](manage-knowledge-network.md) para obtener más información. 

## <a name="topic-curation"></a>Tema curation

AI continuará trabajando continuamente para proporcionar sugerencias para mejorar los temas a medida que se produzcan cambios en el entorno.

Los usuarios a los que permite el acceso ven temas en su trabajo diario pueden realizar sugerencias para mejorarlos. Por ejemplo, si un usuario ve la página del tema y ve información que es incorrecta o tiene que agregarse, un vínculo en la página del tema les permite enviar una solicitud para actualizar la información.

Además, los usuarios con los permisos adecuados pueden etiquetar elementos como la conversación de Microsoft teams que son relevantes para un tema y agregarlos a un tema específico.




## <a name="see-also"></a>Consulte también
[Configuración de la administración del conocimiento](set-up-knowledge-network.md)</br>
[Información general sobre el centro de temas](topic-center-overview.md)
