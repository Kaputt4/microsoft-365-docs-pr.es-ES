---
title: Nuevo formato de caso en Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: ninachen
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
description: Use el nuevo formato de caso en Advanced eDiscovery para que pueda agregar más elementos para revisar conjuntos y aprovechar otros límites aumentados y nuevas funciones.
ms.openlocfilehash: 9b0e87e7d24565bb89444fe5b1e5cbf43d915e42
ms.sourcegitcommit: 7f0c5b55e2966c0c1ce6a153a4e6a7ec035bd818
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2021
ms.locfileid: "61137211"
---
# <a name="use-the-new-case-format-in-advanced-ediscovery"></a>Use el nuevo formato de caso en Advanced eDiscovery

Más organizaciones usan la solución Advanced eDiscovery en Microsoft 365 para procesos críticos de exhibición de documentos electrónicos. Esto incluye responder a solicitudes normativas, investigaciones y litigios. A medida que aumenta el Advanced eDiscovery, un requisito común del cliente es expandir la cantidad total de contenido que se puede administrar en un único Advanced eDiscovery caso. Para ayudar a dar cabida a aumentos significativos en el tamaño del caso, tanto para el volumen total de datos como para el número total de elementos, ahora puede elegir el nuevo formato de caso al crear un Advanced eDiscovery caso.  

## <a name="create-a-case"></a>Crear un caso

Para crear un Advanced eDiscovery con el nuevo formato de caso:

1. Vaya a <https://compliance.microsoft.com> e inicie sesión.

2. En el panel de navegación izquierdo de la Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery > Advanced**.

3. En la **Advanced eDiscovery,** haga clic en la **pestaña Casos** y, a continuación, haga **clic en Crear un caso**.

   Se **muestra la página desplegable Nuevo** caso de exhibición de documentos electrónicos. La **sección Formato de** caso proporciona la opción de crear un caso con el nuevo formato.

   ![Nueva opción de formato de caso en la página Nuevo caso de exhibición de documentos electrónicos.](..\media\AeDNewCaseFormat1.png)

4. Después de asignar el nombre al caso,  seleccione la **opción** Nuevo y, a continuación, haga clic en Guardar para crear el caso con el nuevo formato.

## <a name="benefits-of-the-new-case-format"></a>Ventajas del nuevo formato de caso

El nuevo formato de caso permite administrar casos que contienen más de 40 millones de elementos. Esta funcionalidad le ayuda a administrar eficazmente grandes volúmenes de datos de casos a través de todo el flujo de trabajo de exhibición de documentos electrónicos.

Esta es una lista de otras ventajas de los casos grandes en el flujo Advanced eDiscovery trabajo.

- **Colección:** en el nuevo formato de caso, puede recopilar hasta 1 TB de datos para una sola colección.

   En cada caso, la configuración de la colección recopilará de forma predeterminada datos adjuntos en la nube y Teams y Yammer contenido. Estas configuraciones ayudan a recopilar la imagen completa de las comunicaciones digitales dentro de una investigación. Para las conversaciones contextuales de Teams y Yammer, el nuevo formato de caso convertirá instantáneas basadas en tiempo de 1:1, 1: N y Canal conversaciones en transcripciones HTML para ayudar a proporcionar contexto de conversaciones y reducir el número total de elementos producidos por contenido basado en chat.  

- **Revisión:** cada conjunto de revisión admitirá hasta 1 TB de contenido previo a la expansión. Los metadatos adicionales estarán disponibles para filtros y consultas, incluido el nombre del equipo, el nombre del canal y el nombre de la conversación para Teams contenido. Cada transcripción incluirá contenido basado en tiempo para antes y después del elemento dinámico. Para las conversaciones de canal, la publicación raíz y todas las respuestas se recopilarán para el contenido dinámico. Para obtener más información, vea [Advanced eDiscovery flujo de trabajo de contenido en Microsoft Teams (versión preliminar)](teams-workflow-in-advanced-ediscovery.md)

- **Exportar:** puede exportar grandes conjuntos de contenido en un solo trabajo de exportación. El nuevo formato de caso permite exportar 5 millones de documentos o 500 GB, lo que sea menor en un trabajo de exportación.

Además, el nuevo formato de caso incluye una interfaz de usuario actualizada que muestra el tamaño total de cada conjunto de opiniones en el caso. Los tamaños de conjunto de revisión se muestran en una columna de la **ficha Conjuntos de** revisión.

![Nuevas estadísticas de conjunto de opiniones Advanced eDiscovery interfaz de usuario.](..\media\LargeCaseUI.png)

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**Si intento recopilar más de 1 TB en una sola colección, ¿funcionará?**

El rendimiento se verá afectado negativamente y puede causar inestabilidad en algunos casos.

**Si los datos adjuntos en la nube se incluyen de forma predeterminada en el formato de mayúsculas y minúsculas grandes; ¿Cómo puedo quitar ese contenido de mi experiencia de revisión?**  

Use los filtros de conjunto de revisión para filtrar por tipo de mensaje o para excluir datos adjuntos de la nube mediante el filtro HasAttachment. Para obtener más información, vea [Consulta y filtrar contenido en un conjunto de revisión.](review-set-search.md)

**Al exportar transcripciones de conversación de chat, ¿el archivo de carga contendrá todos los metadatos expandido y un solo elemento para cada transcripción?**

Todos los metadatos de una conversación están incrustados en el archivo de transcripción HTML.  Muchos de los campos comunes están disponibles en el archivo de carga. Para obtener más información acerca de los metadatos exportados, vea [Campos de metadatos de documento en Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).
