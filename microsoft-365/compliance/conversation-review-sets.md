---
title: Revisar conversaciones en eDiscovery avanzado
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
description: Obtenga información sobre cómo usar la característica reconstrucción de conversaciones en eDiscovery avanzado para reconstruir, revisar y exportar conversaciones en curso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf5c39f567240b58546dbeb353e3e461e9b69e48
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358348"
---
# <a name="review-conversations-in-advanced-ediscovery"></a>Revisar conversaciones en eDiscovery avanzado 

La mensajería instantánea es una forma cómoda de hacer preguntas, compartir ideas o comunicarse rápidamente entre grandes audiencias. A medida que las plataformas de mensajería instantánea, como Microsoft Teams, se convierten en el núcleo de la colaboración empresarial, las organizaciones deben evaluar cómo su flujo de trabajo de exhibición de documentos electrónicos aborda estas nuevas formas de comunicación y colaboración. 

La característica Reconstrucción de conversación de eDiscovery avanzado está diseñada para ayudarle a identificar contenido contextual y producir vistas de conversación distintas. Esta funcionalidad le permite revisar de forma eficaz y rápida conversaciones de mensajes instantáneos completas (también denominadas conversaciones en *secuencias)* que se generan en plataformas como Microsoft Teams.

Con la reconstrucción de conversaciones, puede usar funciones integradas para reconstruir, revisar y exportar conversaciones en subprocesos. Use la reconstrucción avanzada de conversaciones de exhibición de documentos electrónicos para:

- Conservar metadatos únicos de nivel de mensaje en todos los mensajes de una conversación.

- Recopilar mensajes contextuales alrededor de los resultados de la búsqueda.

- Revisar, anotar y censurar conversaciones en subprocesos.

- Exportar mensajes individuales o conversaciones en secuencias

## <a name="terminology"></a>Terminología

Estas son algunas definiciones que le ayudarán a empezar a usar la reconstrucción de conversación.

- **Mensajes:** Representa la unidad más pequeña de una conversación. Los mensajes pueden variar en tamaño, estructura y metadatos. 

- **Conversación:** Representa una agrupación de uno o más mensajes. En diferentes aplicaciones, las conversaciones pueden representarse de diferentes maneras. En algunas aplicaciones, hay una acción explícita que se produce al responder a un mensaje existente. Las conversaciones se forman explícitamente como resultado de esta acción del usuario. Por ejemplo, aquí tiene una captura de pantalla de una conversación de canal en Microsoft Teams.

   ![Conversación del canal de Microsoft Teams](../media/threadedchat.png)

   En otras aplicaciones (como los mensajes de chat 1xN en Teams), no hay una cadena de respuesta formal y, en su lugar, los mensajes aparecen como un "hilo plano de mensajes" dentro de un solo subproceso. En estos tipos de aplicaciones, las conversaciones se deducen de un grupo de mensajes que se producen en un momento determinado. Esta "agrupación suave" de mensajes (en lugar de una cadena de respuesta) representa la conversación de "ida y vuelta" sobre un tema específico de interés. 

## <a name="step-1-run-a-search"></a>Paso 1: Ejecutar una búsqueda

Una vez identificados los administradores y las ubicaciones de contenido relevantes, puede crear una búsqueda para encontrar contenido potencialmente relevante. En la **pestaña Búsquedas** en el caso de eDiscovery avanzado, puede crear una búsqueda haciendo clic en **Nueva** búsqueda y siguiendo el asistente. Para obtener información acerca de cómo puede crear una búsqueda, crear una consulta de búsqueda y ver los resultados de la búsqueda, vea Recopilar datos [para un caso.](create-search-to-collect-data.md)

## <a name="step-2-create-a-conversation-review-set"></a>Paso 2: Crear un conjunto de revisión de conversación

En un conjunto de revisión, puede buscar, etiquetar, anotar y censurar documentos, mensajes de correo electrónico y conversaciones de chat. En eDiscovery avanzado, puede personalizar la revisión de las conversaciones, basadas en mensajes individuales o conversaciones en subprocesos. Esto viene determinado por el tipo de conjunto de revisión al que agrega los resultados de la búsqueda creada en el paso 1. Hay dos tipos diferentes de conjuntos de revisión: 
  
  - **Conjuntos de revisión estándar:** Los mensajes de las conversaciones se procesan y se muestran como elementos individuales. 
  
  -  **Conjuntos de revisión de conversación:** Los mensajes de las conversaciones se procesan individualmente, pero se muestran en una vista de conversación. En un conjunto de revisión de conversación, puede anotar, etiquetar y censurar mensajes en una vista de conversación en secuencia. 

Para obtener más información acerca de cómo revisar y administrar el contenido de un conjunto de revisión, vea [Administrar conjuntos de revisión.](managing-review-sets.md) 

## <a name="step-3-enable-conversation-retrieval-options"></a>Paso 3: Habilitar las opciones de recuperación de conversaciones

Después de revisar y finalizar la consulta de búsqueda, puede agregar los resultados de la búsqueda a un conjunto de revisión. Cuando agrega los resultados de búsqueda a un conjunto de revisión, los datos originales se copian en un área de Azure Storage para facilitar el proceso de revisión y análisis. Para obtener más información acerca de cómo agregar resultados de búsqueda a un conjunto de revisión, vea Agregar resultados [de búsqueda a un conjunto de revisión.](add-data-to-review-set.md) 

Al agregar datos de conversaciones a un conjunto de revisión, puede usar las opciones de recuperación de conversaciones para expandir la búsqueda e incluir mensajes contextuales. Después de establecer las opciones de recuperación de conversaciones, pueden suceder lo siguiente:

  ![Recuperación de conversación](../media/messagesandconversations.png)
  
1. Mediante una consulta de palabra clave y de intervalo de fechas, la búsqueda devolvió un resultado en *el mensaje 3*. Este mensaje formaba parte de una conversación más grande, ilustrada por *CRC1*. 
  
2. Al agregar los datos a un conjunto de revisión y habilitar las opciones de recuperación de conversaciones, eDiscovery avanzado volverá y recopilará otros elementos en *CRC1.* 
  
3. Después de agregar los elementos al conjunto de revisión, puede revisar todos los mensajes individuales de *CRC1*. 

Para habilitar la recuperación de conversaciones:
  
1. En la **pestaña Búsquedas** en el caso de eDiscovery avanzado, seleccione una búsqueda y, a continuación, haga clic en Agregar para revisar el conjunto en la página desplegable. 
  
2. Seleccione un conjunto de revisión existente o cree un conjunto de revisión. Puede configurar las opciones de recuperación al agregar resultados de búsqueda a un conjunto de revisión estándar o de conversación.
  
3. En **Opciones de colección,** configure las opciones de recuperación de conversaciones para  los orígenes de contenido que desea expandir en la búsqueda y, a continuación, haga clic en Agregar para iniciar el proceso.  
  
4. Una vez finalizado el trabajo  del conjunto **Agregar** a revisión en la pestaña Trabajos, puede empezar a revisar las conversaciones.

## <a name="step-4-review-and-export-conversations-in-a-review-set"></a>Paso 4: Revisar y exportar conversaciones en un conjunto de revisión

Una vez que el contenido se haya procesado y agregado al conjunto de revisión, puedes empezar a revisar los datos del conjunto de revisión. Las capacidades de revisión son diferentes en función de si el contenido se agregó a un conjunto de revisión estándar o a un conjunto de revisión de conversación. 

### <a name="reviewing-conversations-in-a-standard-review-set"></a>Revisión de conversaciones en un conjunto de revisión estándar

En un conjunto de revisión estándar, los mensajes se procesan y se muestran como elementos individuales, de forma similar a como se almacenan en una carpeta de buzón. En este flujo de trabajo, cada mensaje se procesa como un elemento independiente. Como resultado, las opciones de resumen y exportación en subproceso no están disponibles en un conjunto de revisión estándar. 

  ![Conjunto de revisión estándar](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a>Revisión de conversaciones en un conjunto de revisión de conversación

En un conjunto de revisión de conversación, los mensajes individuales se en subprocesos y se presentan como conversaciones. Esto le permite revisar y exportar conversaciones contextuales. 

  ![Conjunto de revisión de conversación](../media/ConversationRSOptions.PNG)

En las secciones siguientes se describe la revisión y exportación de conversaciones en un conjunto de revisión de conversación.

#### <a name="reviewing-conversations"></a>Revisión de conversaciones

En un conjunto de revisión de conversación, puede usar las siguientes opciones para facilitar el proceso de revisión.

- **Agrupar por conversación:** Agrupa los mensajes dentro de la misma conversación para ayudar a los usuarios a simplificar y acelerar su proceso de revisión. 

- **Vista de resumen:** Muestra la conversación en secuencia. En esta vista, puede ver toda la conversación y también tener acceso a los metadatos de cada mensaje individual.  
  
   - Ver metadatos de mensajes individuales
   
   - Descargar mensajes individuales

- **Vista de texto:** Proporciona el texto extraído para toda la conversación. 

- **Vista anotada:** Permite marcar una vista en secuencia de la conversación. Todos los mensajes de la conversación comparten el mismo documento anotado.

- **Etiquetado:** Al ver conversaciones en un conjunto de revisión, puede ver y aplicar etiquetas haciendo clic en **el Panel de** etiquetado del Panel de codificación.

- **Vuelva a ejecutar la conversión de conversación:** Cuando se agregan mensajes a un conjunto de revisión de conversación, se ejecuta automáticamente un trabajo de conversión para crear el resumen en secuencias y anotar vistas. Si se produce un error en el trabajo de reconstrucción de conversación, puede volver a ejecutar este trabajo haciendo clic en Acción **> Crear** archivos PDF de conversación en el conjunto de revisión.

#### <a name="exporting-conversations"></a>Exportar conversaciones

En un conjunto de revisión de conversación, puede establecer las siguientes opciones para exportar conversaciones:

![Opciones de exportación para conversaciones](../media/export.png)

a. Opciones de metadatos

   - **Cargar archivo:** Los metadatos se incluyen para cada mensaje, correo electrónico y documento individuales. Hay una fila para cada mensaje en una conversación. 

   - **Etiquetas:** Las etiquetas del proceso de revisión se incluyen en el archivo de metadatos. Los mensajes de una conversación comparten las mismas etiquetas. 

b. Opciones de conversación
  
   - **Archivos de conversación:** Al exportar archivos de conversación, la vista anotada se convierte en un archivo PDF y se descarga en la carpeta de exportación. Los mensajes de un archivo de conversación apuntan a la versión PDF del mismo archivo de conversación.  
  
   - **Mensajes de chat individuales:** Al exportar mensajes individuales, cada mensaje único de la conversación se exporta como un elemento independiente. El archivo se exporta en el mismo formato que se guardó en el buzón. Para una conversación específica, recibe varios archivos .msg. 

     >[!NOTE]
     > Si aplicó anotaciones al archivo de conversación, estas anotaciones no se transferirán a los mensajes individuales. 

c. Otras opciones

   - **Generar archivos de texto para todo el contenido exportado:** Genera un archivo de texto para cada conversación exportada desde el conjunto de revisión. 

   - **Reemplace el contenido exportado por archivos PDF redactados:** Si los archivos de conversación redactadas se generan durante el proceso de revisión, estos archivos están disponibles durante la exportación. Puede decidir si exportar solo los archivos nativos (no seleccionando esta opción) o reemplazar los archivos nativos con las versiones redactadas de los archivos nativos (seleccionando esta opción), que se exportan como archivos PDF.

## <a name="more-information"></a>Más información

Para obtener más información sobre cómo revisar los datos de casos en eDiscovery avanzado, vea los siguientes artículos:

- [Ver datos de casos](view-documents-in-review-set.md)

- [Analizar datos de casos](analyzing-data-in-review-set.md)

- [Exportar datos de casos](exporting-data-ediscover20.md)
