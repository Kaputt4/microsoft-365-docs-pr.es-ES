---
title: Introducción a las colecciones en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: Use colecciones en eDiscovery (Premium) para buscar y recopilar contenido relativo a su caso o investigación.
ms.openlocfilehash: ab2cb4baa1e8d60816fbf7c053d49b5a718746d5
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091057"
---
# <a name="learn-about-collections-in-ediscovery-premium"></a>Más información sobre las colecciones en eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Cuando las organizaciones se enfrentan a la recopilación de las comunicaciones y el contenido que pueden ser pertinentes para una investigación o un posible litigio, se enfrentan a un desafío significativo en las mejores circunstancias. En el área de trabajo moderna de hoy en día, el volumen, la variedad y la velocidad del contenido está permitiendo la innovación y el trabajo remoto, a la vez que amplía los requisitos y el proceso para administrar colecciones para investigaciones de exhibición de documentos electrónicos.

El flujo de trabajo de colección plantea importantes desafíos técnicos en torno a la extracción de contenido de orígenes y ubicaciones nativos. También es un punto crítico en la evaluación y la estrategia para escenarios comunes de litigios o investigaciones. A medida que las organizaciones comienzan a evaluar una investigación, las primeras preguntas que se hacen son¿quién participó? Después de identificar quién participó, estos custodios se pueden poner rápidamente en espera para conservar el contenido pertinente. La siguiente pregunta es qué ha tenido lugar? Para responder a esta segunda pregunta fundamental de cualquier investigación, los administradores deben recurrir a los datos. Para evaluar rápidamente el contenido más relevante para la pregunta de lo que ocurrió, los administradores comienzan a refinar el objetivo de la pregunta para asegurarse de que los resultados de la colección sean completos sin ser demasiado amplios.

Las colecciones de eDiscovery (Premium) ayudan a los administradores de exhibición de documentos electrónicos a limitar rápidamente la búsqueda de contenido entre correo electrónico, documentos y otro contenido en Microsoft 365. Las colecciones proporcionan a los administradores una estimación del contenido que puede ser relevante para el caso. Esto permite a los administradores tomar decisiones rápidas e informadas sobre el tamaño y el ámbito del contenido pertinente para un caso. Los administradores de eDiscovery pueden crear una colección para buscar orígenes de datos custodiales (como buzones de correo y sitios de SharePoint) y mediante criterios de búsqueda específicos (como palabras clave e intervalos de fechas) para definir rápidamente el ámbito de su colección.

Una vez definida la colección, los administradores de eDiscovery pueden guardar la colección como borrador y obtener estimaciones, incluidas las estimaciones para el volumen de datos, las ubicaciones de contenido que contienen resultados y el número de aciertos para la condición de consulta de búsqueda. Estas conclusiones pueden ayudar a informar si la colección se debe revisar para restringir o expandir el ámbito de la colección antes de pasar a las fases de revisión y análisis en el flujo de trabajo de eDiscovery.

Cuando el administrador está satisfecho con el ámbito de la colección y la cantidad estimada de contenido que es probable que responda, el administrador puede agregar o *confirmar* el contenido en un conjunto de revisión. Al confirmar una colección en un conjunto de revisión, ese administrador también tiene las opciones para incluir conversaciones de chat, datos adjuntos en la nube y versiones de documentos. El contenido de la colección también pasa por otro nivel de procesamiento durante la ingesta en el conjunto de revisión. y la colección se actualizará con el resumen final de la colección. Después de agregar contenido al conjunto de revisión, los administradores de eDiscovery pueden seguir consultando, agrupando y refinando el contenido en para ayudar con la minimización y revisión. Además, la colección se actualiza con información y estadísticas sobre el contenido confirmado en el conjunto de revisión. Esto proporciona una referencia histórica sobre el contenido de la colección.

Con el lanzamiento de colecciones en un eDiscovery (Premium), se ha cambiado el nombre de la pestaña **Búsquedas** a **Colecciones** en un caso de exhibición de documentos electrónicos (Premium) en el portal de cumplimiento de Microsoft Purview. Los pasos para definir el ámbito y el tamaño de la colección siguen el mismo proceso que la búsqueda para definir ubicaciones y condiciones. Guardar como borrador y obtener estimaciones de vista previa permite la validación rápida del ámbito de destino de las colecciones antes de confirmar una búsqueda completa y una recopilación en el conjunto de revisión. Esto permite una mejor administración de trabajos y iteraciones dirigidas para empezar a minimizar el contenido durante el proceso de búsqueda y recopilación.

## <a name="collections-workflow"></a>Flujo de trabajo de colecciones

Para empezar a usar colecciones en eDiscovery (Premium), este es un flujo de trabajo básico y descripciones de cada paso del proceso.

![Flujo de trabajo de colecciones en eDiscovery (Premium).](../media/CollectionsWorkflow.png)

1. **Cree y ejecute una colección de borradores**. El primer paso consiste en crear una colección de borradores y definir los orígenes de datos custodiales y no custodiales que se van a buscar. También puede buscar en otros orígenes de datos que no se hayan agregado al caso. Después de agregar los orígenes de datos, configure la consulta de búsqueda para buscar en los orígenes de datos contenido relevante para el caso. Puede usar palabras clave, propiedades y condiciones para crear consultas de búsqueda que devuelvan contenido que probablemente sea más relevante para el caso. Para obtener más información, consulte [Creación de una colección de borradores](create-draft-collection.md).

2. **Revise las estimaciones y las estadísticas**. Después de crear una colección de borradores y ejecutarla, el siguiente paso es ver las estadísticas de recopilación para ayudarle a comprobar si se encuentra contenido relevante y las ubicaciones de contenido con más visitas. También puede obtener una vista previa de un ejemplo de los resultados de la búsqueda para ayudarle a determinar si el contenido está dentro del ámbito de la investigación. Para obtener más información, vea [Estadísticas e informes para colecciones de borradores](collection-statistics-reports.md#statistics-and-reports-for-draft-collections).

3. **Revise y vuelva a ejecutar una colección de borradores**. En función de las estimaciones y estadísticas devueltas por la colección, puede editar la colección de borradores cambiando los orígenes de datos que se buscan y la consulta de búsqueda para expandir o restringir la colección. Puede actualizar y volver a ejecutar la colección de borradores hasta que esté seguro de que la colección contiene el contenido más relevante para su caso.

4. **Confirme una colección de borradores en un conjunto de revisión**. Cuando esté satisfecho de que la colección devuelve el contenido de tipo que es relevante para el caso, puede confirmar la colección en el conjunto de revisión. Al confirmar una colección, tiene la opción de agregar subprocesos de conversación, datos adjuntos en la nube y versiones de documentos al conjunto de revisión, todos los cuales podrían ser relevantes para el caso.

   Al confirmar una colección, los elementos secundarios, como las firmas de correo electrónico y las imágenes, se extraen de un elemento primario (como un mensaje de correo electrónico, un mensaje de chat o un documento) y, a continuación, se procesan mediante reconocimiento óptico de caracteres (OCR) para extraer cualquier texto del elemento secundario. A continuación, el texto extraído de elementos secundarios se agrega a su elemento primario para que pueda verlo en el conjunto de revisión. Al no agregar elementos secundarios al conjunto de revisión como un archivo independiente, eDiscovery (Premium) ayuda a limitar el número de elementos potencialmente inmateriales agregados al conjunto de revisión. Para obtener más información sobre cómo se controlan los elementos secundarios, consulte [Estadísticas e informes de recopilación](collection-statistics-reports.md#collection-contents).

   Para obtener más información, consulte [Confirmación de una colección de borradores en un conjunto de revisión](commit-draft-collection.md).

5. **Revise el resumen de la colección y las estadísticas**. Después de confirmar una colección en un conjunto de revisión, se conserva información sobre la colección, como estadísticas sobre elementos extraídos, indexación profunda, la consulta de búsqueda usada para la colección y las ubicaciones de contenido de las que se recopilaron los elementos. Además, las colecciones confirmadas no se pueden editar ni volver a ejecutar. Solo puede copiarlos o eliminarlos. La conservación de colecciones proporciona un registro histórico de los elementos recopilados que se agregaron a un conjunto de revisión. Para obtener más información, vea [Estadísticas e informes para colecciones confirmadas](collection-statistics-reports.md#statistics-and-reports-for-committed-collections).
