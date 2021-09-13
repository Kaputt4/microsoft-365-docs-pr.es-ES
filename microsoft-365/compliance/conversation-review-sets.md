---
title: Revisar conversaciones en Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre la característica de reconstrucción de conversación en Advanced eDiscovery (denominado subproceso de conversación) para reconstruir, revisar y exportar conversaciones de chat en Microsoft Teams y Yammer grupos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62ebfc054db260fd5e41fec3809ba1efdf46b44b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191584"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a>Subprocesos de conversación en Advanced eDiscovery

La mensajería instantánea es una forma cómoda de hacer preguntas, compartir ideas o comunicarse rápidamente entre grandes audiencias. A medida que las plataformas de mensajería instantánea, como los grupos Microsoft Teams y Yammer, se convierten en el núcleo de la colaboración empresarial, las organizaciones deben evaluar cómo su flujo de trabajo de exhibición de documentos electrónicos aborda estas nuevas formas de comunicación y colaboración.

La característica de reconstrucción de Advanced eDiscovery está diseñada para ayudarle a identificar contenido contextual y producir vistas de conversación distintas. Esta funcionalidad le permite revisar de forma eficaz y rápida conversaciones de mensajes instantáneos completas (también denominadas conversaciones enhebradas) que se generan en plataformas como Microsoft Teams.

Con la reconstrucción de conversaciones, puede usar funciones integradas para reconstruir, revisar y exportar conversaciones en subprocesos. Use Advanced eDiscovery reconstrucción de conversaciones para:

- Conserve metadatos únicos de nivel de mensaje en todos los mensajes de una conversación.

- Recopilar mensajes contextuales alrededor de los resultados de búsqueda.

- Revisar, anotar y redactar conversaciones enhebradas.

- Exportar mensajes individuales o conversaciones en subprocesos

## <a name="terminology"></a>Terminología

Estas son algunas definiciones que le ayudarán a empezar a usar la reconstrucción de la conversación.

- **Mensajes:** Representa la unidad más pequeña de una conversación. Los mensajes pueden variar en tamaño, estructura y metadatos.

- **Conversación:** Representa una agrupación de uno o varios mensajes. En diferentes aplicaciones, las conversaciones pueden representarse de diferentes maneras. En algunas aplicaciones, hay una acción explícita que resulta de responder a un mensaje existente. Las conversaciones se forman explícitamente como resultado de esta acción del usuario. Por ejemplo, esta es una captura de pantalla de una conversación de canal en Microsoft Teams.

   ![Microsoft Teams Conversación de canal.](../media/threadedchat.png)

   En otras aplicaciones (como los mensajes de chat en grupo en Teams), no hay una cadena de respuesta formal y, en su lugar, los mensajes aparecen como un "río plano de mensajes" dentro de un único subproceso. En estos tipos de aplicaciones, las conversaciones se deducen de un grupo de mensajes que se producen en un tiempo determinado. Esta "agrupación suave" de mensajes (en lugar de una cadena de respuesta) representa la conversación "ida y vuelta" sobre un tema específico de interés.

## <a name="step-1-create-a-draft-collection"></a>Paso 1: Crear una colección de borradores

Después de identificar los custodios relevantes y las ubicaciones de contenido, puede crear una búsqueda para buscar contenido potencialmente relevante. En la **ficha Colecciones** del Advanced eDiscovery, puede crear una colección haciendo clic en **Nueva** colección y siguiendo el asistente. Para obtener información sobre cómo crear una colección, crear una consulta de búsqueda y obtener una vista previa de los resultados de la [búsqueda,](create-draft-collection.md)vea Create a draft collection .

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a>Paso 2: Confirmar un borrador de colección en un conjunto de revisión

Después de revisar y finalizar la consulta de búsqueda en una colección, puede agregar los resultados de búsqueda a un conjunto de revisión. Al agregar los resultados de búsqueda a un conjunto de revisión, los datos originales se copian en un área de Azure Storage para facilitar el proceso de revisión y análisis. Para obtener más información acerca de cómo agregar resultados de búsqueda a un conjunto de revisión, vea [Commit a draft collection to a review set](commit-draft-collection.md).

Al agregar elementos de conversaciones a un conjunto de revisión, puede usar la opción conversaciones en subprocesos para recopilar mensajes contextuales de conversaciones que contienen elementos que coinciden con los criterios de búsqueda de la colección. Después de seleccionar la opción conversaciones de subprocesos, pueden suceder lo siguiente:

  ![Recuperación de conversaciones.](../media/messagesandconversations.png)

1. Con una consulta de palabra clave y intervalo de fechas, la búsqueda devolvió un éxito en *el mensaje 3*. Este mensaje formaba parte de una conversación más grande, ilustrada por *CRC1*.

2. Al agregar los datos a un conjunto de revisión y habilitar las opciones de recuperación de conversaciones, Advanced eDiscovery volverá y recopilará otros elementos en *CRC1*.

3. Después de agregar los elementos al conjunto de revisión, puede revisar todos los mensajes individuales de *CRC1*.

Para habilitar la opción conversaciones enhebradas, vea [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).

## <a name="step-3-review-and-export-threaded-conversations"></a>Paso 3: Revisar y exportar conversaciones enhebradas

Después de procesar y agregar el contenido al conjunto de revisión, puede empezar a revisar los datos del conjunto de revisión. Los mensajes individuales se enhebran juntos y se presentan como conversaciones. Esto le permite revisar y exportar conversaciones contextuales.

  ![Conjunto de revisión de conversación.](../media/ConversationRSOptions.PNG)

En las secciones siguientes se describe la revisión y exportación de conversaciones.

### <a name="reviewing-conversations"></a>Revisión de conversaciones

En un conjunto de revisión, puede usar las siguientes opciones para facilitar el proceso de revisión.

- **Agrupar por conversación:** Agrupa mensajes dentro de la misma conversación para ayudar a los usuarios a simplificar y acelerar su proceso de revisión.

- **Vista de resumen:** Muestra la conversación enhebrada. En esta vista, puede ver toda la conversación y también tener acceso a los metadatos de cada mensaje individual.

   - Ver metadatos de mensajes individuales

   - Descargar mensajes individuales

- **Vista texto:** Proporciona el texto extraído para toda la conversación.

- **Vista Anotar:** Permite marcar una vista de subproceso de la conversación. Todos los mensajes de la conversación comparten el mismo documento anotado.

- **Etiquetado:** Al ver conversaciones en un conjunto de revisión, puede ver y aplicar etiquetas haciendo clic en **Panel de** etiquetado en el panel Codificación.

- **Volver a ejecutar la conversión de conversación:** Cuando se agregan mensajes a un conjunto de revisión de conversación, se ejecuta automáticamente un trabajo de conversión para crear el resumen enhebrado y anotar vistas. Si se produce un error en el trabajo de reconstrucción de conversación, puede volver a ejecutar este trabajo haciendo clic en Acción **> Crear archivos PDF de** conversación en el conjunto de revisión.

### <a name="exporting-conversations"></a>Exportar conversaciones

Para obtener las opciones que puede seleccionar al exportar conversaciones de un conjunto de revisión, vea [Exportar documentos de un conjunto de revisión.](export-documents-from-review-set.md#export-options)

En concreto, puede exportar conversaciones de chat completa en un único archivo PDF o exportar cada mensaje de chat de una conversación como un archivo individual.

## <a name="more-information"></a>Más información

Para obtener más información sobre cómo revisar los datos de casos Advanced eDiscovery, vea los siguientes artículos:

- [Consultar y filtrar el contenido de un conjunto de revisión](review-set-search.md)
- [Etiquetar documentos en un conjunto de revisión](tagging-documents.md)
- [Ver datos de casos](view-documents-in-review-set.md)
- [Analizar datos de casos](analyzing-data-in-review-set.md)
- [Exportar datos de casos](exporting-data-ediscover20.md)
