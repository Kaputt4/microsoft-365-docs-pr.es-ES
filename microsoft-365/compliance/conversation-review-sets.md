---
title: Revisar conversaciones en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
ms.assetid: ''
description: Obtenga información sobre la característica de reconstrucción de conversaciones en Microsoft Purview eDiscovery (Premium) (denominado subproceso de conversación) para reconstruir, revisar y exportar conversaciones de chat en grupos de Microsoft Teams y Yammer.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 43b9bccd06ab9ca5ac94f48efa40b1c06707dde5
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66634795"
---
# <a name="conversation-threading-in-ediscovery-premium"></a>Subprocesos de conversación en eDiscovery (Premium)

La mensajería instantánea es una manera cómoda de formular preguntas, compartir ideas o comunicarse rápidamente entre grandes audiencias. A medida que las plataformas de mensajería instantánea, como Microsoft Teams y los grupos de Yammer, se convierten en el núcleo de la colaboración empresarial, las organizaciones deben evaluar cómo su flujo de trabajo de eDiscovery aborda estas nuevas formas de comunicación y colaboración.

La característica de reconstrucción de conversaciones de Microsoft Purview eDiscovery (Premium) está diseñada para ayudarle a identificar contenido contextual y generar vistas de conversación distintas. Esta funcionalidad permite revisar de forma eficaz y rápida las conversaciones de mensajes instantáneos completas (también *denominadas conversaciones en subprocesos*) que se generan en plataformas como Microsoft Teams.

Con la reconstrucción de conversaciones, puede usar funcionalidades integradas para reconstruir, revisar y exportar conversaciones en subprocesos. Use la reconstrucción de conversaciones de eDiscovery (Premium) para:

- Conservar metadatos únicos de nivel de mensaje en todos los mensajes de una conversación.

- Recopile mensajes contextuales en torno a los resultados de la búsqueda.

- Revise, anote y redacte las conversaciones en subproceso.

- Exportación de mensajes individuales o conversaciones en subproceso

## <a name="terminology"></a>Terminología

Estas son algunas definiciones que le ayudarán a empezar a usar la reconstrucción de la conversación.

- **Mensajes:** Representa la unidad más pequeña de una conversación. Los mensajes pueden variar en tamaño, estructura y metadatos.

- **Conversación:** Representa una agrupación de uno o varios mensajes. En distintas aplicaciones, las conversaciones se pueden representar de maneras diferentes. En algunas aplicaciones, hay una acción explícita que resulta de responder a un mensaje existente. Las conversaciones se forman explícitamente como resultado de esta acción del usuario. Por ejemplo, esta es una captura de pantalla de una conversación de canal en Microsoft Teams.

   ![Conversación de canal de Microsoft Teams.](../media/threadedchat.png)

   En otras aplicaciones (como mensajes de chat de grupo en Teams), no hay una cadena de respuesta formal y, en su lugar, los mensajes aparecen como un "río plano de mensajes" dentro de un único subproceso. En estas aplicaciones de tipos, las conversaciones se deducen de un grupo de mensajes que se producen en un tiempo determinado. Esta "agrupación temporal" de mensajes (en lugar de una cadena de respuesta) representa la conversación "de ida y vuelta" sobre un tema específico de interés.

## <a name="step-1-create-a-draft-collection"></a>Paso 1: Crear una colección de borradores

Una vez que haya identificado los custodios y las ubicaciones de contenido pertinentes, puede crear una búsqueda para encontrar contenido potencialmente relevante. En la pestaña **Colecciones** del caso eDiscovery (Premium), puede crear una colección haciendo clic en **Nueva colección** y siguiendo el asistente. Para obtener información sobre cómo puede crear una colección, crear una consulta de búsqueda y obtener una vista previa de los resultados de la búsqueda, consulte [Creación de una colección de borradores](create-draft-collection.md).

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a>Paso 2: Confirmación de una colección de borradores en un conjunto de revisión

Después de revisar y finalizar la consulta de búsqueda en una colección, puede agregar los resultados de la búsqueda a un conjunto de revisión. Al agregar los resultados de la búsqueda a un conjunto de revisión, los datos originales se copian en un área de Azure Storage para facilitar el proceso de revisión y análisis. Para obtener más información sobre cómo agregar resultados de búsqueda a un conjunto de revisión, consulte [Confirmación de una colección de borradores en un conjunto de revisión](commit-draft-collection.md).

Al agregar elementos de conversaciones a un conjunto de revisión, puede usar la opción conversaciones en subprocesos para recopilar mensajes contextuales de conversaciones que contienen elementos que coinciden con los criterios de búsqueda de la colección. Después de seleccionar la opción conversaciones de subproceso, pueden ocurrir lo siguiente:

  ![Recuperación de conversación.](../media/messagesandconversations.png)

1. Con una palabra clave y una consulta de intervalo de fechas, la búsqueda devolvió una acierto en el *mensaje 3*. Este mensaje formaba parte de una conversación mayor, ilustrada por *CRC1*.

2. Al agregar los datos a un conjunto de revisión y habilitar las opciones de recuperación de conversaciones, eDiscovery (Premium) volverá y recopilará otros elementos en *CRC1*.

3. Una vez agregados los elementos al conjunto de revisión, puede revisar todos los mensajes individuales de *CRC1*.

Para habilitar la opción conversaciones en subproceso, consulte [Confirmación de una colección de borradores en un conjunto de revisión](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).

## <a name="step-3-review-and-export-threaded-conversations"></a>Paso 3: Revisión y exportación de conversaciones en subproceso

Una vez procesado y agregado el contenido al conjunto de revisión, puede empezar a revisar los datos del conjunto de revisión. Los mensajes individuales se enhebran juntos y se presentan como conversaciones. Esto le permite revisar y exportar conversaciones contextuales.

  ![Conjunto de revisión de conversación.](../media/ConversationRSOptions.PNG)

En las secciones siguientes se describe la revisión y exportación de conversaciones.

### <a name="reviewing-conversations"></a>Revisión de conversaciones

En un conjunto de revisión, puede usar las siguientes opciones para facilitar el proceso de revisión.

- **Agrupar por conversación:** Agrupa los mensajes dentro de la misma conversación para ayudar a los usuarios a simplificar y acelerar su proceso de revisión.

- **Vista de resumen:** Muestra la conversación en subproceso. En esta vista, puede ver toda la conversación y también acceder a los metadatos de cada mensaje individual.

   - Visualización de metadatos para mensajes individuales

   - Descarga de mensajes individuales

- **Vista de texto:** Proporciona el texto extraído para toda la conversación.

- **Anotación de la vista:** Permite marcar una vista en subprocesos de la conversación. Todos los mensajes de la conversación comparten el mismo documento anotado.

- **Etiquetado:** Al ver conversaciones en un conjunto de revisión, puede ver y aplicar etiquetas haciendo clic en el **panel Etiquetado** en el panel Codificación.

- **Volver a ejecutar la conversión de conversación:** Cuando se agregan mensajes a un conjunto de revisión de conversación, se ejecuta automáticamente un trabajo de conversión para crear el resumen subproceso y anotar vistas. Si se produce un error en el trabajo de reconstrucción de conversaciones, puede volver a ejecutar este trabajo haciendo clic en **Acción > Crear archivos PDF de conversación** en el conjunto de revisión.

### <a name="exporting-conversations"></a>Exportación de conversaciones

Para ver las opciones que puede seleccionar al exportar conversaciones desde un conjunto de revisión, consulte [Exportación de documentos desde un conjunto de revisión](export-documents-from-review-set.md#export-options).

En concreto, puede exportar conversaciones de chat completas en un único archivo PDF o puede exportar cada mensaje de chat en una conversación como un archivo individual.

## <a name="more-information"></a>Más información

Para obtener más información sobre cómo revisar los datos de casos en eDiscovery (Premium), consulte los artículos siguientes:

- [Consultar y filtrar el contenido de un conjunto de revisión](review-set-search.md)
- [Etiquetar documentos en un conjunto de revisión](tagging-documents.md)
- [Visualización de datos de casos](view-documents-in-review-set.md)
- [Analizar datos de casos](analyzing-data-in-review-set.md)
- [Exportar datos de casos](exporting-data-ediscover20.md)
