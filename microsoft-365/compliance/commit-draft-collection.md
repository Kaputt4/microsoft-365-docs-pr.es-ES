---
title: Confirmar una colección de borrador en un conjunto de revisión
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Después de crear e iterar en una colección de borradores, puede confirmarla en un conjunto de revisión. Al confirmar una colección de borradores, los elementos recopilados se agregan a la revisión establecida en el caso. Una vez que los elementos recopilados están en el conjunto de revisión, puede analizarlos, revisarlos y exportarlos.
ms.openlocfilehash: f908d17d804487cd5e7e93085e418f9a94915c8e
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64997942"
---
# <a name="commit-a-draft-collection-to-a-review-set-in-ediscovery-premium"></a>Confirmación de una colección de borradores en un conjunto de revisión en eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Cuando esté satisfecho con los elementos que ha recopilado en una colección de borradores y esté listo para analizarlos, etiquetarlos y revisarlos, puede agregar una colección a un conjunto de revisión en el caso. Al confirmar una colección de borradores en un conjunto de revisión, los elementos recopilados se copian de su ubicación de contenido original en Microsoft 365 a un conjunto de revisión. Un conjunto de revisión es una ubicación Azure Storage segura y proporcionada por Microsoft en la nube de Microsoft.

## <a name="commit-a-draft-collection-to-a-review-set"></a>Confirmar una colección de borrador en un conjunto de revisión

1. En el portal de cumplimiento de Microsoft Purview, abra el caso de exhibición de documentos electrónicos de Microsoft Purview (Premium) y, a continuación, seleccione la pestaña **Colecciones** para mostrar una lista de las colecciones en el caso.

   ![Lista de colecciones en un caso.](../media/CommitDraftCollections1.png)

   > [!TIP]
   > Un valor de en `Estimated` la columna **Estado** identifica las colecciones de borradores que se pueden agregar a un conjunto de revisión. Un estado de `Committed` indica que ya se ha agregado una colección a un conjunto de revisión.

2. En la página **Colecciones** , seleccione la colección de borradores que desea confirmar en un conjunto de revisión.

3. En la parte inferior de la página de control flotante, seleccione **ActionsEdit collection (AccionesEditar** >  colección).

4. En el Asistente para editar colecciones, haga clic en **Siguiente** hasta que se muestre la página **Guardar borrador o recopilar** .

5. Configure las siguientes opciones:

   1. Seleccione **Recopilar elementos y agregar para revisar el conjunto**.

   2. Decida si desea agregar la colección a un nuevo conjunto de revisión (que se crea después de enviar la colección) o agregarla a un conjunto de revisión existente. Complete esta sección en función de su decisión.

   3. Configure las opciones de recopilación adicionales:

      ![Configure opciones de recopilación adicionales.](../media/AeDAdditionalCollectionSettings.png).

       a. **mensajes Teams y Yammer**: seleccione esta opción para agregar subprocesos de conversación a la colección que incluyan los elementos de chat devueltos por la consulta de búsqueda en la colección. Esto significa que se reconstruye la conversación de chat que contiene elementos que coinciden con los criterios de búsqueda. Esto le permite revisar los elementos de chat en el contexto de la conversación de ida y vuelta. Para obtener más información, vea [Subprocesos de conversación en eDiscovery (Premium)](conversation-review-sets.md).

       b. **Datos adjuntos en la nube**: seleccione esta opción para incluir datos adjuntos modernos o archivos vinculados cuando los resultados de la colección se agreguen al conjunto de revisión. Esto significa que el archivo de destino de un archivo adjunto o vinculado moderno se agrega al conjunto de revisión.

       > [!NOTE]
       > Las dos opciones para recopilar Teams contextuales y Yammer mensajes y datos adjuntos en la nube se seleccionan de forma predeterminada (y se atenuan) para los casos creados con el nuevo formato de caso. Para obtener más información, consulte [Uso del nuevo formato de caso](advanced-ediscovery-new-case-format.md).

       c. **Elementos indizados parcialmente**: seleccione esta opción para agregar elementos parcialmente indizados de orígenes de datos adicionales al conjunto de revisión. Si la colección ha buscado orígenes de datos adicionales (como se especifica en la página **Ubicaciones adicionales** del Asistente para colecciones), es posible que haya elementos indizados parcialmente de estas ubicaciones que quiera agregar al conjunto de revisión. Los orígenes de datos custodios y no custodios normalmente no tienen elementos indizados parcialmente. Esto se debe a que el proceso de indexación avanzada vuelve a indexar elementos cuando se agregan orígenes de datos de custodia y no custodia a un caso. Además, agregar elementos parcialmente indizados aumentará el número de elementos agregados al conjunto de revisión. <p> Después de agregar elementos parcialmente indizados al conjunto de revisión, puede aplicar un filtro para ver específicamente estos elementos. Para obtener más información, vea [Filtrar elementos parcialmente indizados](review-set-search.md#filter-partially-indexed-items).

      d. **SharePoint versiones**: seleccione esta opción para habilitar la colección de todas las versiones de un documento de SharePoint según los límites de versión y los parámetros de búsqueda de la colección. Si selecciona esta opción, aumentará significativamente el tamaño de los elementos que se agregan al conjunto de revisión. Una vez agregadas las versiones del documento al conjunto de revisión, 

   4. Configure los valores para definir la escala de la colección que se va a agregar al conjunto de revisión:

      - **Agregar todos los resultados de la colección**: seleccione esta opción para agregar al conjunto de revisión todos los elementos que coincidan con los criterios de búsqueda de la colección.

      - **Agregar un ejemplo de los resultados de la colección**: seleccione esta opción para agregar un ejemplo de los resultados de la colección al conjunto de revisión en lugar de agregar todos los resultados. Si selecciona esta opción, haga clic en **Editar parámetros de ejemplo** y elija una de las siguientes opciones:

         - **Ejemplo basado en la confianza**: los elementos de la colección se agregan al conjunto de revisión se determinarán mediante los parámetros estadísticos que establezca. Si normalmente usa un nivel de confianza e intervalo al realizar el muestreo de los resultados, especifíquelos en los cuadros desplegables. De lo contrario, use la configuración predeterminada.

         - **Ejemplo aleatorio**: los elementos de la colección se agregan al conjunto de revisión en función de una selección aleatoria del porcentaje especificado del número total de elementos devueltos por la búsqueda.

6. En la página **Revisar la colección** , puede revisar la configuración de recopilación que configuró en la página anterior. Haga clic en **Editar** si desea cambiarlos.

7. Haga clic en **Enviar** para crear la colección de borradores. Se muestra una página que confirma que se creó la colección.

## <a name="what-happens-after-you-commit-a-draft-collection"></a>¿Qué ocurre después de confirmar una colección de borradores?

Cuando se confirma una colección de borradores en un conjunto de revisión, sucede lo siguiente:

- Si ha creado un nuevo conjunto de revisión en el que confirmar la colección, el conjunto de revisión se crea y se muestra en la pestaña **Conjuntos de revisión** en el caso. El estado del nuevo conjunto de revisión es **Listo**. Este valor de estado significa que se ha creado el conjunto de revisión; no significa que la colección se haya agregado al conjunto de revisión. El estado de agregar elementos de la colección al conjunto de revisión se muestra en la pestaña **Colecciones** .

- La consulta de búsqueda de recopilación se vuelve a ejecutar. Esto significa que los resultados de búsqueda reales copiados en el conjunto de revisión pueden ser diferentes de los resultados estimados que se devolvieron cuando se ejecutó por última vez la búsqueda de recopilación.

- Todos los elementos de los resultados de la búsqueda se copian del origen de datos original en el servicio en directo y se copian en una ubicación de Azure Storage segura en la nube de Microsoft.

- Los mensajes de correo electrónico adjuntos cifrados SharePoint y OneDrive y archivos cifrados que se devuelven en los resultados de búsqueda se descifran al confirmar la colección en un conjunto de revisión. Puede revisar y consultar los archivos descifrados en el conjunto de revisión. Para obtener más información, vea [Descifrado en Microsoft 365 herramientas de exhibición de documentos electrónicos](ediscovery-decryption.md).

- La funcionalidad de reconocimiento óptico de caracteres (OCR) extrae texto de imágenes e incluye el texto de la imagen con el contenido que se agrega a un conjunto de revisión. Para obtener más información, consulte la sección [Reconocimiento óptico de caracteres](#optical-character-recognition) de este artículo.

- Una vez completada correctamente la confirmación, el valor de la columna de estado de en la pestaña **Colecciones** se cambia a `Committed`.

## <a name="optical-character-recognition"></a>Reconocimiento óptico de caracteres

Al confirmar una colección en un conjunto de revisión, la funcionalidad de reconocimiento óptico de caracteres (OCR) en eDiscovery (Premium) extrae automáticamente texto de las imágenes e incluye el texto de la imagen con el contenido que se agrega a un conjunto de revisión. Puede ver el texto extraído en el Visor de texto del archivo de imagen seleccionado en el conjunto de revisión. Esto le permite realizar más análisis y revisar el texto de las imágenes. OCR es compatible con archivos sueltos, datos adjuntos de correo electrónico e imágenes incrustadas. Para obtener una lista de los formatos de archivo de imagen que se admiten para OCR, vea [Tipos de archivo admitidos en eDiscovery (Premium)](supported-filetypes-ediscovery20.md#image).

Debe habilitar la funcionalidad OCR para cada caso que cree en eDiscovery (Premium). Para obtener más información, consulte [Configuración de las opciones de búsqueda y análisis](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).
