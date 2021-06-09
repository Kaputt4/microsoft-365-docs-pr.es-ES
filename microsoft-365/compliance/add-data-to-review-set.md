---
title: Agregar los resultados de búsqueda a un conjunto de revisión
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo agregar resultados de búsqueda o ejemplos de esos resultados de búsqueda a un Advanced eDiscovery de revisión de casos.
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919982"
---
# <a name="add-search-results-to-a-review-set"></a>Agregar los resultados de búsqueda a un conjunto de revisión

Cuando esté satisfecho con los resultados de una búsqueda y esté listo para revisar y analizar esos resultados de búsqueda, puede agregarlos a un conjunto de revisión en el caso. Copiar los datos originales en el conjunto de revisión también facilita el proceso de revisión y análisis al proporcionarle herramientas de análisis avanzadas, como la detección de temas, la detección casi duplicada y la identificación de subprocesos de correo electrónico. También puede agregar datos de orígenes de datos que no Microsoft 365 a un conjunto de revisión para que pueda revisar los datos además de los datos que recopila de Microsoft 365.

Al agregar los resultados de una búsqueda a un conjunto de revisión (los conjuntos de revisión en un caso aparecen en la pestaña **Conjuntos** de revisión), se producen lo siguiente:

- La búsqueda se vuelve a ejecutar. Esto significa que los resultados de búsqueda reales copiados en el conjunto de revisión pueden ser diferentes de los resultados estimados que se devolvieron cuando se presentó la búsqueda por última vez.

- Todos los elementos de los resultados de la búsqueda se copian del origen de datos original en los servicios en directo y se copian en una ubicación Azure Storage segura en la nube de Microsoft.

- Todos los elementos (incluidos el contenido y los metadatos) se reindexa para que todos los datos del conjunto de revisión puedan buscarse completamente durante la revisión de los datos del caso. La reindexación de los datos da como resultado búsquedas exhaustivas y rápidas al buscar los datos en el conjunto de revisión durante la investigación del caso.

- Un archivo cifrado con una tecnología de cifrado de [Microsoft](encryption.md) y se adjunta a un mensaje de correo electrónico que se devuelve en los resultados de la búsqueda se descifra cuando el mensaje de correo electrónico y el archivo adjunto se agregan al conjunto de revisión. Puede revisar y consultar el archivo descifrado en el conjunto de revisión. Debe tener asignado el rol Descifrar RMS para agregar datos adjuntos de correo electrónico descifrado a un conjunto de revisión. Para obtener más información, vea [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).

Para agregar datos a un conjunto de  revisión, haga clic en una búsqueda en la pestaña Búsquedas y, a continuación, haga clic en Agregar resultados para revisar el conjunto **en** la página desplegable.

Puede agregar a un conjunto de revisión existente o crear un nuevo conjunto de revisión.  Si agrega a un nuevo conjunto de revisión, especifique el nombre y, a continuación, haga clic en **Agregar** para mostrar la página desplegable.

![Seleccionar un conjunto de revisión y configurar opciones de colección](../media/AeD_AddToReviewSet.png)

Agregar datos a un conjunto de revisión es un proceso de larga ejecución. Este proceso incluye la recopilación de elementos de los orígenes de datos originales de Microsoft 365 (por ejemplo, de buzones y sitios), copiarlos en la ubicación de Azure Storage (este proceso de copia también se denomina *ingesta)* y, a continuación, volver a indizar los elementos. Puede realizar un seguimiento del progreso  en la pestaña **Trabajos** o en la pestaña Búsquedas supervisando el estado de la columna Datos agregados **para revisar el conjunto.** Una vez completado el procesamiento  del conjunto de revisión, haga clic en la pestaña Conjuntos de revisión del caso y, a continuación, haga clic en el conjunto de revisión para iniciar el proceso de filtrado, revisión, etiquetado y exportación de datos en el conjunto de revisión.

## <a name="define-options-to-scope-your-collection-for-review"></a>Definir opciones para definir el ámbito de la colección para su revisión

Al agregar el contenido de una búsqueda a un conjunto de revisión existente o nuevo, tiene las siguientes opciones para recopilar el contenido para su revisión:

- **Incluir versiones de SharePoint (beta):** use esta opción para habilitar la colección de todas las versiones de un documento SharePoint según los límites de versión y los parámetros de búsqueda de la colección. Si selecciona esta opción, aumentará significativamente el tamaño de los elementos que se agregan al conjunto de revisión.

- **Opciones de recuperación de** conversación: los elementos agregados al conjunto de revisión están habilitados para conversaciones en subprocesos para ayudar a revisar el contenido en contexto de la conversación de ida y vuelta. Para obtener más información, vea [Revisar conversaciones en Advanced eDiscovery](conversation-review-sets.md).

- **Habilitar la recuperación de datos adjuntos** modernos: use esta opción para incluir datos adjuntos modernos o archivos vinculados en la colección para su revisión. Para obtener más información acerca de las propiedades que se pueden buscar relacionadas con datos adjuntos modernos, vea Campos de [metadatos](document-metadata-fields-in-Advanced-eDiscovery.md)de documento en Advanced eDiscovery .

## <a name="add-a-sample-to-a-review-set"></a>Agregar un ejemplo a un conjunto de revisión

Si desea validar los resultados de una búsqueda más exhaustivamente antes de agregarlos todos a un conjunto de revisión, puede agregar una muestra de los resultados de búsqueda a un conjunto de revisión en lugar de agregarlo todo.

Para agregar un ejemplo a un conjunto de revisión, haga clic en una búsqueda en la pestaña **Búsquedas** y haga clic en **Ejemplo** en la página desplegable. En la **página Parámetros de** muestreo, elija una de las siguientes opciones:

- **Porcentaje de nivel** de confianza e intervalo de confianza **%:** los elementos agregados al conjunto de revisión se determinarán por los parámetros estadísticos que establezca. Si normalmente usa un nivel de confianza y un intervalo al muestrear los resultados, es preciso especificarlos en los cuadros desplegables. De lo contrario, use la configuración predeterminada.

- **% de ejemplo aleatorio:** los elementos agregados al conjunto de revisión se basan en una selección aleatoria del porcentaje especificado del número total de elementos devueltos por la búsqueda.

Después de seleccionar y configurar una de las opciones anteriores, elija un conjunto de revisión para agregar el ejemplo y, a continuación, haga clic en **Enviar**. De nuevo, puede realizar  un seguimiento del  progreso en la pestaña Trabajos o en la pestaña Búsquedas supervisando el estado de la columna Datos agregados para revisar **el** conjunto.

## <a name="optical-character-recognition"></a>Reconocimiento óptico de caracteres

Al agregar resultados de búsqueda a un conjunto de opiniones, la funcionalidad de reconocimiento óptico de caracteres (OCR) en Advanced eDiscovery extrae automáticamente texto de imágenes e incluye el texto de la imagen con los datos que se agregan a un conjunto de opiniones. Puede ver el texto extraído en el visor de texto del archivo de imagen seleccionado en el conjunto de revisión. Esto le permite realizar más análisis y revisar el texto de las imágenes. OCR es compatible con archivos sueltos, datos adjuntos de correo electrónico e imágenes incrustadas. Para obtener una lista de los formatos de archivo de imagen compatibles con OCR, vea [Tipos de archivo admitidos en Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).

Tiene que habilitar la funcionalidad de OCR para cada caso que cree en eDiscovery avanzado. Para obtener más información, vea [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).
