---
title: Información general sobre las colecciones en eDiscovery avanzada
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
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Use colecciones en eDiscovery avanzada para buscar y recopilar contenido relacionado con su caso o investigación.
ms.openlocfilehash: e3f383fab31ec39f22bd781fc84644e3eeee57bb
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838968"
---
# <a name="learn-about-collections-in-advanced-ediscovery"></a>Obtenga información sobre las colecciones de eDiscovery avanzada

> [!NOTE]
> Estamos implementando una nueva experiencia de colecciones en eDiscovery avanzada, que se describe en este artículo. Este lanzamiento llevará varias semanas antes de que esté disponible para todas las organizaciones. Si la nueva experiencia de colecciones no está disponible en su organización, puede recopilar contenido de casos con la herramienta de búsqueda [eDiscovery avanzada](create-search-to-collect-data.md).

Cuando las organizaciones se enfrentan a la recopilación de las comunicaciones y el contenido que pueden ser relevantes para una investigación o un posible litigio, se enfrentan a un desafío importante en las mejores circunstancias. En el lugar de trabajo moderno actual, el volumen, la variedad y la velocidad del contenido permiten la innovación y el trabajo remoto, al tiempo que amplían los requisitos y el proceso para administrar colecciones para investigaciones de exhibición de documentos electrónicos.

El flujo de trabajo de la colección plantea importantes desafíos técnicos en torno a la extracción de contenido de orígenes y ubicaciones nativas. También es un punto crítico en la evaluación y estrategia para escenarios comunes de litigios o investigaciones. A medida que las organizaciones comienzan a evaluar una investigación, las primeras preguntas que se han hecho son quiénes participaron. Después de identificar quién estaba implicado, estos custodios se pueden colocar rápidamente en espera para conservar el contenido relevante. La siguiente pregunta es ¿qué ocurrió? Para responder a esta segunda pregunta fundamental de cualquier investigación, los administradores deben recurrir a los datos. Para evaluar rápidamente el contenido más relevante para la pregunta de lo que ha tenido lugar, los administradores comienzan a refinar el objetivo de la pregunta para garantizar que los resultados de la colección sean completos sin ser demasiado amplios.

Las colecciones de eDiscovery avanzado ayudan a los administradores de exhibición de documentos electrónicos a buscar rápidamente contenido en correo electrónico, documentos y otro contenido en Microsoft 365. Las colecciones proporcionan a los administradores una estimación del contenido que puede ser relevante para el caso. Esto permite a los administradores tomar decisiones rápidas e informadas sobre el tamaño y el ámbito del contenido relevante para un caso. Los administradores de exhibición de documentos electrónicos pueden crear una colección para buscar orígenes de datos de custodia (como buzones y sitios de SharePoint) y mediante criterios de búsqueda específicos (como palabras clave e intervalos de fechas) para definir rápidamente el ámbito de su colección.

Una vez definida la colección, los administradores de exhibición de documentos electrónicos pueden guardar la colección como borrador y obtener estimaciones, incluidas las estimaciones del volumen de datos, las ubicaciones de contenido que contienen resultados y el número de aciertos para la condición de consulta de búsqueda. Estas conclusiones pueden ayudar a informar si la colección debe revisarse para restringir o expandir el ámbito de la colección antes de pasar a la revisión y analizar las etapas del flujo de trabajo de exhibición de documentos electrónicos.

Cuando el administrador está satisfecho con el ámbito de la colección y la cantidad estimada de  contenido que es probable que responda, el administrador puede agregar o confirmar el contenido a un conjunto de revisión. Al confirmar una colección en un conjunto de revisión, ese administrador también tiene las opciones para incluir conversaciones de chat, datos adjuntos en la nube y versiones de documentos. El contenido de la colección también pasa por otro nivel de procesamiento durante la ingesta en el conjunto de revisión. y la colección se actualizará con el resumen final de la colección. Después de agregar contenido al conjunto de revisión, los administradores de exhibición de documentos electrónicos pueden seguir consultando, agrupando y refinando el contenido para ayudar con la minimización y la revisión. Además, la colección se actualiza con información y estadísticas sobre el contenido confirmado en el conjunto de revisión. Esto proporciona una referencia histórica sobre el contenido de la colección.

Con el lanzamiento de colecciones en una  exhibición de documentos electrónicos avanzada, la pestaña Búsquedas se ha cambiado a **Colecciones** en un caso de exhibición de documentos electrónicos avanzada en el Centro de cumplimiento de Microsoft 365. Los pasos para definir el ámbito y el tamaño de la colección siguen el mismo proceso que la búsqueda para definir ubicaciones y condiciones. Guardar como borrador y obtener estimaciones de vista previa permite la validación rápida del ámbito de destino de las colecciones antes de confirmar una búsqueda completa y una colección en el conjunto de revisión. Esto permite una administración de trabajos mejorada e iteraciones dirigidas para empezar a minimizar el contenido durante el proceso de búsqueda y recopilación.

## <a name="collections-workflow"></a>Flujo de trabajo de colecciones

Para empezar a usar colecciones en eDiscovery avanzada, este es un flujo de trabajo básico y descripciones de cada paso del proceso.

![Flujo de trabajo de colecciones en eDiscovery avanzado](../media/CollectionsWorkflow.png)

1. **Crear y ejecutar una colección borrador**. El primer paso es crear un borrador de colección y definir los orígenes de datos de custodia y no custodia que se buscarán. También puede buscar en otros orígenes de datos que no se han agregado al caso. Después de agregar los orígenes de datos, configure la consulta de búsqueda para buscar en los orígenes de datos contenido relevante para el caso. Puede usar palabras clave, propiedades y condiciones para crear consultas de búsqueda que devuelvan contenido que probablemente sea más relevante para el caso. Para obtener más información, vea [Create a draft collection](create-draft-collection.md).

2. **Revisar estimaciones y estadísticas**. Después de crear una colección borrador y ejecutarla, el siguiente paso es ver las estadísticas de la colección para ayudarle a comprobar si se encuentra contenido relevante y las ubicaciones de contenido con más visitas. También puede obtener una vista previa de una muestra de los resultados de la búsqueda para ayudarle a determinar si el contenido está dentro del ámbito de la investigación. Para obtener más información, vea [Statistics and reports for draft collections](collection-statistics-reports.md#statistics-and-reports-for-draft-collections).

3. **Revise y vuelva a ejecutar una colección borrador**. En función de las estimaciones y estadísticas devueltas por la colección, puede editar la colección borrador cambiando los orígenes de datos que se buscan y la consulta de búsqueda para expandir o restringir la colección. Puede actualizar y volver a ejecutar la colección borrador hasta que esté seguro de que la colección contiene el contenido más relevante para su caso.

4. **Confirmar un borrador de colección en un conjunto de revisión**. Cuando esté satisfecho de que la colección devuelve el tipo de contenido que es relevante para el caso, puede confirmar la colección en el conjunto de revisión. Al confirmar una colección, tiene la opción de agregar subprocesos de conversación, datos adjuntos en la nube y versiones de documentos al conjunto de revisión, todos los cuales podrían ser relevantes para el caso. Las siguientes cosas suceden al confirmar una colección:

   - Los elementos secundarios (como datos adjuntos de correo electrónico, firmas de correo electrónico e imágenes) se extraen de un elemento primario (como un mensaje de correo electrónico, un mensaje de chat o un documento), se indizan (en un proceso denominado indización *profunda)* y se agregan al conjunto de revisión como archivos independientes.

   - La indización profunda se realiza en elementos recopilados de orígenes de datos adicionales. Estos tipos de orígenes de datos son ubicaciones de contenido distintas de los orígenes de datos de custodia y no custodia que se agregaron anteriormente al caso.

   Para obtener más información, vea [Commit a draft collection to a review set](commit-draft-collection.md).

5. **Revisar resumen y estadísticas de la colección**. Después de confirmar una colección en un conjunto de revisión, se conserva información sobre la colección, como estadísticas sobre elementos extraídos, indización profunda, la consulta de búsqueda usada para la colección y las ubicaciones de contenido de las que se recopilaron los elementos. Además, las colecciones comprometidas no se pueden editar ni volver a ejecutar. Solo puede copiarlos o eliminarlos. Conservar colecciones proporciona un registro histórico de los elementos recopilados que se agregaron a un conjunto de revisión. Para obtener más información, vea [Statistics and reports for committed collections](collection-statistics-reports.md#statistics-and-reports-for-committed-collections).
