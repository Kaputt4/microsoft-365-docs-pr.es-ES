---
title: Nuevo formato de caso en eDiscovery (Premium)
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
description: Use el nuevo formato de caso en eDiscovery (Premium) para que pueda agregar más elementos para revisar conjuntos y aprovechar otros límites aumentados y nuevas funciones.
ms.openlocfilehash: 36650a369d2bac2742eb7f0d5ea76b3a530a1a03
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64947437"
---
# <a name="use-the-new-case-format-in-ediscovery-premium"></a>Usar el nuevo formato de caso en eDiscovery (Premium)

Más organizaciones usan la solución eDiscovery (Premium) en Microsoft 365 para procesos críticos de eDiscovery. Esto incluye responder a solicitudes normativas, investigaciones y litigios. A medida que aumenta el uso de eDiscovery (Premium), un requisito común del cliente es expandir la cantidad total de contenido que se puede administrar en un único caso de exhibición de documentos electrónicos (Premium). Para ayudar a dar cabida a aumentos significativos en el tamaño de los casos, tanto para el volumen total de datos como para el número total de elementos, ahora puede elegir el nuevo formato de caso al crear un caso de exhibición de documentos electrónicos (Premium).  

## <a name="create-a-case"></a>Crear un caso

Para crear un caso de eDiscovery (Premium) con el nuevo formato de caso:

1. Vaya a <https://compliance.microsoft.com> e inicie sesión.

2. En el panel de navegación izquierdo del portal de cumplimiento de Microsoft Purview, haga clic en **eDiscovery > Avanzado**.

3. En la página **eDiscovery (Premium),** haga clic en la pestaña **Casos** y, a continuación, haga clic en **Crear un caso**.

   Se muestra la página de control flotante **Nuevo caso de exhibición de** documentos electrónicos. La sección **Formato de** caso proporciona la opción de crear un caso con el nuevo formato.

   ![Nueva opción de formato de caso en la página Nuevo caso de exhibición de documentos electrónicos.](..\media\AeDNewCaseFormat1.png)

4. Después de asignar un nombre al caso, seleccione la opción **Nuevo** y, a continuación, haga clic en **Guardar** para crear el caso con el nuevo formato.

## <a name="benefits-of-the-new-case-format"></a>Ventajas del nuevo formato de caso

El nuevo formato de caso le permite administrar casos que contienen más de 40 millones de elementos. Esta funcionalidad le ayuda a administrar de forma eficaz grandes volúmenes de datos de casos a través de todo el flujo de trabajo de eDiscovery.

Esta es una lista de otras ventajas de los casos grandes en el flujo de trabajo de eDiscovery (Premium).

- **Colección**: en el nuevo formato de caso, puede recopilar hasta 1 TB de datos para una sola colección.

   En cada caso, la configuración de la colección recopilará de forma predeterminada datos adjuntos en la nube y Teams contextuales y Yammer contenido. Esta configuración ayuda a recopilar la imagen completa de las comunicaciones digitales dentro de una investigación. Para Teams y Yammer conversaciones contextuales, el nuevo formato de caso convertirá las instantáneas basadas en el tiempo de las conversaciones 1:1, 1: N y Channel en transcripciones HTML para ayudar a proporcionar contexto de conversaciones y reducir el número total de elementos generados por el contenido basado en chat.  

- **Revisión**: cada conjunto de revisión admitirá hasta 1 TB de contenido previo a la expansión. Habrá metadatos adicionales disponibles para filtros y consultas, incluidos el nombre del equipo, el nombre del canal y el nombre de la conversación para Teams contenido. Cada transcripción incluirá contenido basado en el tiempo para antes y después del elemento con capacidad de respuesta. En el caso de las conversaciones de canal, la publicación raíz y todas las respuestas se recopilarán para el contenido con capacidad de respuesta. Para obtener más información, vea flujo de [trabajo de eDiscovery (Premium) para obtener contenido en Microsoft Teams (versión preliminar)](teams-workflow-in-advanced-ediscovery.md)

- **Exportar**: puede exportar grandes conjuntos de contenido en un único trabajo de exportación. El nuevo formato de caso le permite exportar 5 millones de documentos o 500 GB, lo que sea más pequeño en un trabajo de exportación.

Además, el nuevo formato de caso incluye una interfaz de usuario actualizada que muestra el tamaño total de cada conjunto de revisión en el caso. Los tamaños del conjunto de revisión se muestran en una columna de la pestaña **Conjuntos de revisión** .

![Nuevas estadísticas del conjunto de revisiones en la interfaz de usuario de eDiscovery (Premium).](..\media\LargeCaseUI.png)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**Si intento recopilar más de 1 TB en una sola colección, ¿funcionará?**

El rendimiento se verá afectado negativamente y puede causar inestabilidad en algunos casos.

**Si los datos adjuntos en la nube se incluyen de forma predeterminada en el formato de mayúsculas y minúsculas; ¿cómo puedo quitar ese contenido de mi experiencia de revisión?**  

Use filtros de conjunto de revisión para filtrar por tipo de mensaje o para excluir datos adjuntos en la nube mediante el filtro HasAttachment. Para obtener más información, consulte [Consulta y filtrado de contenido en un conjunto de revisión](review-set-search.md).

**Al exportar transcripciones de conversación de chat, ¿el archivo de carga contendrá todos los metadatos expandidos y un solo elemento para cada transcripción?**

Todos los metadatos de una conversación se incrustan en el archivo de transcripción HTML.  Muchos de los campos comunes están disponibles en el archivo de carga. Para obtener más información sobre los metadatos exportados, vea [Campos de metadatos de documento en eDiscovery (Premium)](document-metadata-fields-in-Advanced-eDiscovery.md).
