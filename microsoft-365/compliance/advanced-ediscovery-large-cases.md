---
title: Casos grandes en Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
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
description: Use casos grandes en Advanced eDiscovery para que pueda agregar más elementos para revisar conjuntos y aprovechar otros límites aumentados.
ms.openlocfilehash: 9481f268e47f10955d4438a0088d7153ebf9d21b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203344"
---
# <a name="use-large-cases-in-advanced-ediscovery-preview"></a>Usar casos grandes en Advanced eDiscovery (versión preliminar)

Más organizaciones usan la solución Advanced eDiscovery en Microsoft 365 para procesos críticos de exhibición de documentos electrónicos. Esto incluye responder a solicitudes reglamentarias, investigaciones y litigios. A medida que aumenta el Advanced eDiscovery, un requisito común del cliente es expandir la cantidad total de contenido que se puede administrar en un único Advanced eDiscovery caso. Para ayudar a dar cabida a aumentos significativos en el tamaño de los casos, tanto para el volumen total de datos como para el número total de elementos, ahora puede elegir un formato de caso grande al crear un Advanced eDiscovery caso.  

## <a name="create-a-large-case"></a>Crear un caso grande

Para crear un caso grande:

1. Vaya a <https://compliance.microsoft.com> e inicie sesión.

2. En el panel de navegación izquierdo de la Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery > Advanced**.

3. En la **Advanced eDiscovery,** haga clic en la **pestaña Casos** y, a continuación, haga **clic en Crear un caso**.

   Se **muestra la página desplegable Nuevo** caso de exhibición de documentos electrónicos. La **sección Formato de** caso proporciona la opción de crear un caso grande. Elija este tipo de caso si necesita recopilar una gran cantidad de contenido en un breve período de tiempo.

   ![Opción de caso grande en la página Nuevo caso de exhibición de documentos electrónicos.](..\media\AeDLargeCases1.png)

4. Después de asignar un nombre al caso, seleccione la **opción Caso grande** y, a continuación, haga clic en **Guardar** para crear el caso grande.

## <a name="benefits-of-large-cases"></a>Ventajas de casos grandes

El nuevo formato de caso grande permite administrar casos que contienen más de 40 millones de elementos. Esta funcionalidad le ayuda a administrar eficazmente grandes volúmenes de datos de casos a través de todo el flujo de trabajo de exhibición de documentos electrónicos.

Esta es una lista de otras ventajas de los casos grandes en el flujo Advanced eDiscovery trabajo.

- **Colección:** en el formato de caso grande, puede recopilar hasta 1 TB de datos para una sola colección. 

   Para cada caso grande, la configuración de la colección recopilará de forma predeterminada datos adjuntos en la nube y datos Teams y Yammer contenido. Estas configuraciones ayudan a recopilar la imagen completa de las comunicaciones digitales dentro de una investigación. Para las conversaciones contextuales de Teams y Yammer, el formato de caso grande convertirá instantáneas basadas en tiempo de 1:1, 1: N y Conversaciones de canal en transcripciones html para ayudar a proporcionar contexto de conversaciones y reducir el número total de elementos producidos por contenido basado en chat.  

- **Revisión:** cada conjunto de revisión admitirá hasta 1 TB de contenido previo a la expansión. Los metadatos adicionales estarán disponibles para filtros y consultas, incluido el nombre del equipo, el nombre del canal y el nombre de la conversación para Teams contenido. Cada transcripción incluirá contenido basado en tiempo para antes y después del elemento dinámico. Para las conversaciones de canal, la publicación raíz y todas las respuestas se recopilarán para el contenido dinámico.  

- **Exportar:** puede exportar grandes conjuntos de contenido en un solo trabajo de exportación. El formato de caso grande permite exportar 5 millones de documentos o 500 GB, lo que sea menor en un trabajo de exportación.

Además, el nuevo formato de caso grande incluye una interfaz de usuario actualizada que muestra el tamaño total de cada conjunto de opiniones en el caso. Los tamaños de conjunto de revisión se muestran en una columna de la ficha **Conjuntos** de revisión y en un panel desplegable que persiste de todas las pestañas del caso.

![Estadísticas de casos grandes Advanced eDiscovery interfaz de usuario.](..\media\LargeCaseUI.png)

## <a name="known-issues"></a>Problemas conocidos

- La opción para exportar contenido como archivos sueltos y **archivos PST** no se admite actualmente en casos grandes (la opción está gris). Esta opción de exportación para casos grandes se admite próximamente. Para obtener más información acerca de la exportación de contenido, vea [Export documents from a review set in Advanced eDiscovery](export-documents-from-review-set.md).

- La indización avanzada que se produce cuando se agregan custodios y origen de datos no custodiados a un caso actualmente no se admite en casos grandes. El trabajo de indización se crea, pero no se completa. La indización avanzada en casos grandes se admite próximamente. Para obtener más información acerca de la indización avanzada, vea [Indexación avanzada de datos de custodia](indexing-custodian-data.md).

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**Si intento recopilar más de 1 TB en una sola colección, ¿funcionará?**

El rendimiento se verá afectado negativamente y puede causar inestabilidad en algunos casos.

**Si los datos adjuntos en la nube se incluyen de forma predeterminada en el formato de mayúsculas y minúsculas grandes; ¿Cómo puedo quitar ese contenido de mi experiencia de revisión?**  

Use los filtros de conjunto de revisión para filtrar por tipo de mensaje o para excluir datos adjuntos de la nube mediante el filtro HasAttachment. Para obtener más información, vea [Consulta y filtrar contenido en un conjunto de revisión.](review-set-search.md)

**Al exportar transcripciones de conversación de chat, ¿el archivo de carga contendrá todos los metadatos expandido y un solo elemento para cada transcripción?**

Todos los metadatos de una conversación están incrustados en el archivo de transcripción HTML.  Muchos de los campos comunes están disponibles en el archivo de carga. Para obtener más información acerca de los metadatos exportados, vea [Campos de metadatos de documento en Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).
