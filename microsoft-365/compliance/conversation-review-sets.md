---
title: Revisar conversaciones en eDiscovery avanzada
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
description: Obtenga información sobre la característica de reconstrucción de conversaciones en eDiscovery avanzada (denominada subprocesos de conversación) para reconstruir, revisar y exportar conversaciones de chat en grupos de Microsoft Teams y Yammer.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 12887ba8dd74c3dab445dcc76e155e274a371539
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838309"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a>Subprocesos de conversación en eDiscovery avanzado

La mensajería instantánea es una forma cómoda de hacer preguntas, compartir ideas o comunicarse rápidamente entre grandes audiencias. A medida que las plataformas de mensajería instantánea, como los grupos de Microsoft Teams y Yammer, se convierten en el núcleo de la colaboración empresarial, las organizaciones deben evaluar cómo su flujo de trabajo de exhibición de documentos electrónicos aborda estas nuevas formas de comunicación y colaboración.

La característica Reconstrucción de conversación de eDiscovery avanzada está diseñada para ayudarle a identificar contenido contextual y producir vistas de conversación distintas. Esta funcionalidad le permite revisar de forma eficaz y rápida conversaciones de mensajes instantáneos completas (también denominadas conversaciones enhebradas) que se generan en plataformas como Microsoft Teams.

Con la reconstrucción de conversación, puede usar las funciones integradas para reconstruir, revisar y exportar conversaciones en subprocesos. Use La reconstrucción avanzada de conversaciones de exhibición de documentos electrónicos para:

- Conserve metadatos únicos de nivel de mensaje en todos los mensajes de una conversación.

- Recopilar mensajes contextuales alrededor de los resultados de búsqueda.

- Revisar, anotar y redactar conversaciones enhebradas.

- Exportar mensajes individuales o conversaciones en subprocesos

## <a name="terminology"></a>Terminología

Estas son algunas definiciones que le ayudarán a empezar a usar la reconstrucción de conversación.

- **Mensajes:** Representa la unidad más pequeña de una conversación. Los mensajes pueden variar en tamaño, estructura y metadatos. 

- **Conversación:** Representa una agrupación de uno o varios mensajes. En diferentes aplicaciones, las conversaciones pueden representarse de diferentes maneras. En algunas aplicaciones, hay una acción explícita que resulta de responder a un mensaje existente. Las conversaciones se forman explícitamente como resultado de esta acción del usuario. Por ejemplo, esta es una captura de pantalla de una conversación de canal en Microsoft Teams.

   ![Conversación del canal de Microsoft Teams](../media/threadedchat.png)

   En otras aplicaciones (como los mensajes de chat de 1xN en Teams), no hay una cadena de respuesta formal y, en su lugar, los mensajes aparecen como un "río plano de mensajes" dentro de un solo subproceso. En estos tipos de aplicaciones, las conversaciones se deducen de un grupo de mensajes que se producen en un tiempo determinado. Esta "agrupación suave" de mensajes (en lugar de una cadena de respuesta) representa la conversación "ida y vuelta" sobre un tema específico de interés.

## <a name="step-1-create-a-draft-collection"></a>Paso 1: Crear una colección de borradores

Después de identificar los custodios relevantes y las ubicaciones de contenido, puede crear una búsqueda para buscar contenido potencialmente relevante. En la **ficha Colecciones** del caso eDiscovery avanzado, puede crear una colección haciendo clic en **Nueva** colección y siguiendo el asistente. Para obtener información sobre cómo crear una colección, crear una consulta de búsqueda y obtener una vista previa de los resultados de la [búsqueda,](create-draft-collection.md)vea Create a draft collection .

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a>Paso 2: Confirmar un borrador de colección en un conjunto de revisión

Después de revisar y finalizar la consulta de búsqueda en una colección, puede agregar los resultados de búsqueda a un conjunto de revisión. Al agregar los resultados de búsqueda a un conjunto de revisión, los datos originales se copian en un área de Azure Storage para facilitar el proceso de revisión y análisis. Para obtener más información acerca de cómo agregar resultados de búsqueda a un conjunto de revisión, vea [Commit a draft collection to a review set](commit-draft-collection.md).

Al agregar elementos de conversaciones a un conjunto de revisión, puede usar la opción conversaciones en subprocesos para recopilar mensajes contextuales de conversaciones que contienen elementos que coinciden con los criterios de búsqueda de la colección. Después de seleccionar la opción conversaciones de subprocesos, pueden suceder lo siguiente:

  ![Recuperación de conversaciones](../media/messagesandconversations.png)
  
1. Con una consulta de palabra clave y intervalo de fechas, la búsqueda devolvió un éxito en *el mensaje 3*. Este mensaje formaba parte de una conversación más grande, ilustrada por *CRC1*.
  
2. Al agregar los datos a un conjunto de revisión y habilitar las opciones de recuperación de conversaciones, eDiscovery avanzado volverá y recopilará otros elementos en *CRC1*.
  
3. Después de agregar los elementos al conjunto de revisión, puede revisar todos los mensajes individuales de *CRC1*.

Para habilitar la opción conversaciones enhebradas, vea [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).
  
## <a name="step-3-review-and-export-threaded-conversations"></a>Paso 3: Revisar y exportar conversaciones enhebradas

Después de procesar y agregar el contenido al conjunto de revisión, puede empezar a revisar los datos del conjunto de revisión. Las funcionalidades de revisión son diferentes en función de si el contenido se agregó a un conjunto de revisión estándar o a un conjunto de revisión de conversación.

### <a name="reviewing-conversations-in-a-standard-review-set"></a>Revisar conversaciones en un conjunto de revisión estándar

En un conjunto de revisión estándar, los mensajes se procesan y se muestran como elementos individuales, de forma similar a como se almacenan en una carpeta de buzones. En este flujo de trabajo, cada mensaje se procesa como un elemento independiente. Como resultado, las opciones de resumen y exportación en subprocesos no están disponibles en un conjunto de revisión estándar.

  ![Conjunto de revisión estándar](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a>Revisión de conversaciones en un conjunto de revisión de conversación

En un conjunto de revisión de conversación, los mensajes individuales se enhebran y se presentan como conversaciones. Esto le permite revisar y exportar conversaciones contextuales. 

  ![Conjunto de revisión de conversación](../media/ConversationRSOptions.PNG)

En las secciones siguientes se describe la revisión y exportación de conversaciones en un conjunto de revisión de conversación.

#### <a name="reviewing-conversations"></a>Revisión de conversaciones

En un conjunto de revisión de conversación, puede usar las siguientes opciones para facilitar el proceso de revisión.

- **Agrupar por conversación:** Agrupa mensajes dentro de la misma conversación para ayudar a los usuarios a simplificar y acelerar su proceso de revisión.

- **Vista de resumen:** Muestra la conversación enhebrada. En esta vista, puede ver toda la conversación y también tener acceso a los metadatos de cada mensaje individual.  
  
   - Ver metadatos de mensajes individuales
   
   - Descargar mensajes individuales

- **Vista texto:** Proporciona el texto extraído para toda la conversación.

- **Vista Anotar:** Permite marcar una vista de subproceso de la conversación. Todos los mensajes de la conversación comparten el mismo documento anotado.

- **Etiquetado:** Al ver conversaciones en un conjunto de revisión, puede ver y aplicar etiquetas haciendo clic en **Panel de** etiquetado en el panel Codificación.

- **Volver a ejecutar la conversión de conversación:** Cuando se agregan mensajes a un conjunto de revisión de conversación, se ejecuta automáticamente un trabajo de conversión para crear el resumen enhebrado y anotar vistas. Si se produce un error en el trabajo de reconstrucción de conversación, puede volver a ejecutar este trabajo haciendo clic en Acción **> Crear archivos PDF de** conversación en el conjunto de revisión.

#### <a name="exporting-conversations"></a>Exportar conversaciones

En un conjunto de revisión de conversación, puede establecer las siguientes opciones para exportar conversaciones:

![Exportar opciones para conversaciones](../media/export.png)

a. Opciones de metadatos

   - **Cargar archivo:** Los metadatos se incluyen para cada mensaje individual, correo electrónico y documento. Hay una fila para cada mensaje de una conversación. 

   - **Etiquetas:** Las etiquetas del proceso de revisión se incluyen en el archivo de metadatos. Los mensajes de una conversación comparten las mismas etiquetas. 

b. Opciones de conversación
  
   - **Archivos de conversación:** Al exportar archivos de conversación, la vista anotada se convierte en un archivo PDF y se descarga en la carpeta de exportación. Los mensajes de un archivo de conversación apuntan a la versión PDF del mismo archivo de conversación.  
  
   - **Mensajes de chat individuales:** Al exportar mensajes individuales, cada mensaje único de la conversación se exporta como un elemento independiente. El archivo se exporta en el mismo formato que se guardó en el buzón. Para una conversación específica, recibe varios archivos .msg.

     >[!NOTE]
     > Si aplicó anotaciones al archivo de conversación, estas anotaciones no se transferirán a los mensajes individuales.

c. Otras opciones

   - **Generar archivos de texto para todo el contenido exportado:** Genera un archivo de texto para cada conversación exportada desde el conjunto de revisión.

   - **Reemplace el contenido exportado por archivos PDF redactados:** Si los archivos de conversación redactadas se generan durante el proceso de revisión, estos archivos estarán disponibles durante la exportación. Puede decidir si desea exportar solo los archivos nativos (no seleccionando esta opción) o reemplazar los archivos nativos por las versiones redactadas de los archivos nativos (seleccionando esta opción), que se exportan como archivos PDF.

## <a name="more-information"></a>Más información

Para obtener más información sobre cómo revisar los datos de casos en eDiscovery avanzada, vea los siguientes artículos:

- [Ver datos de casos](view-documents-in-review-set.md)

- [Analizar datos de casos](analyzing-data-in-review-set.md)

- [Exportar datos de casos](exporting-data-ediscover20.md)
