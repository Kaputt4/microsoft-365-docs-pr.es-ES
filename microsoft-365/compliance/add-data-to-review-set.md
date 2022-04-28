---
title: Agregar los resultados de búsqueda a un conjunto de revisión
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
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo agregar resultados de búsqueda o ejemplos de esos resultados de búsqueda a un conjunto de revisión de casos de eDiscovery (Premium).
ms.openlocfilehash: cda1a7fcf33a5fc1b299fd2d66f7241ab1cef229
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65100971"
---
# <a name="add-search-results-to-a-review-set"></a>Agregar los resultados de búsqueda a un conjunto de revisión

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Cuando esté satisfecho con los resultados de una búsqueda y esté listo para revisar y analizar esos resultados de búsqueda, puede agregarlos a un conjunto de revisión en el caso. Copiar los datos originales en el conjunto de revisión también facilita el proceso de revisión y análisis, ya que proporciona herramientas de análisis avanzadas, como la detección de temas, la detección casi duplicada y la identificación de subprocesos de correo electrónico. También puede agregar datos de orígenes de datos que no son Microsoft 365 a un conjunto de revisión para que pueda revisar esos datos, además de los datos que recopila de Microsoft 365.

Al agregar los resultados de una búsqueda a un conjunto de revisión (los conjuntos de revisiones de un caso se muestran en la pestaña **Conjuntos de revisiones** ), se producen las siguientes cosas:

- La búsqueda se vuelve a ejecutar. Esto significa que los resultados reales de la búsqueda copiados en el conjunto de revisión pueden ser diferentes de los resultados estimados que se devolvieron cuando se ejecutó la búsqueda por última vez.

- Todos los elementos de los resultados de la búsqueda se copian del origen de datos original en los servicios en directo y se copian en una ubicación de Azure Storage segura en la nube de Microsoft.

- Todos los elementos (incluidos el contenido y los metadatos) se vuelven a indexar para que todos los datos del conjunto de revisión se puedan buscar completamente durante la revisión de los datos del caso. La reindexación de los datos da como resultado búsquedas exhaustivas y rápidas al buscar los datos en el conjunto de revisión durante la investigación del caso.

- Un archivo cifrado con una [tecnología de cifrado de Microsoft](encryption.md) y se adjunta a un mensaje de correo electrónico que se devuelve en los resultados de la búsqueda se descifra cuando el mensaje de correo electrónico y el archivo adjunto se agregan al conjunto de revisión. Puede revisar y consultar el archivo descifrado en el conjunto de revisión. Debe tener asignado el rol Descifrado de RMS para agregar datos adjuntos de correo electrónico descifrados a un conjunto de revisión. Para obtener más información, vea [Descifrado en herramientas de exhibición de documentos electrónicos de Microsoft Purview](ediscovery-decryption.md).

Para agregar datos a un conjunto de revisión, haga clic en una búsqueda en la pestaña **Búsquedas** y, a continuación, haga clic en **Agregar resultados para revisar establecidos** en la página de control flotante.

Puede agregar a un conjunto de revisión existente o crear un nuevo conjunto de revisión.  Si agrega a un nuevo conjunto de revisión, especifique el nombre y, a continuación, haga clic en **Agregar** para mostrar la página de control flotante.

![Seleccione un conjunto de revisión y configure las opciones de recopilación.](../media/AeD_AddToReviewSet.png)

Agregar datos a un conjunto de revisión es un proceso de larga ejecución. Este proceso incluye la recopilación de elementos de los orígenes de datos originales de Microsoft 365 (por ejemplo, de buzones y sitios), copiarlos en la ubicación Azure Storage (este proceso de copia también se denomina *ingesta*) y, a continuación, volver a indexar los elementos. Puede realizar un seguimiento del progreso en la pestaña **Trabajos** o en la pestaña **Búsquedas** supervisando el estado en la columna **Agregar datos para revisar el conjunto** . Una vez completado el procesamiento del conjunto de revisión, haga clic en la pestaña **Conjuntos de revisión** en el caso y, a continuación, haga clic en el conjunto de revisión para iniciar el proceso de filtrado, revisión, etiquetado y exportación de datos en el conjunto de revisión.

## <a name="define-options-to-scope-your-collection-for-review"></a>Definición de opciones para definir el ámbito de la colección para su revisión

Al agregar el contenido de una búsqueda a un conjunto de revisión existente o nuevo, tiene las siguientes opciones para recopilar el contenido para su revisión:

- **Incluir versiones de SharePoint (beta):** use esta opción para habilitar la colección de todas las versiones de un documento de SharePoint según los límites de versión y los parámetros de búsqueda de la colección. Si selecciona esta opción, aumentará significativamente el tamaño de los elementos que se agregan al conjunto de revisión.

- **Opciones de recuperación de** conversaciones: los elementos agregados al conjunto de revisión están habilitados para las conversaciones en subprocesos con el fin de ayudar a revisar el contenido en el contexto de la conversación de ida y vuelta. Para obtener más información, vea [Revisar conversaciones en eDiscovery (Premium)](conversation-review-sets.md).

- **Habilitar la recuperación para los datos adjuntos modernos**: use esta opción para incluir datos adjuntos modernos o archivos vinculados en la colección para su posterior revisión. Para obtener más información sobre las propiedades que se pueden buscar relacionadas con los datos adjuntos [modernos, vea Campos de metadatos del documento en eDiscovery (Premium)](document-metadata-fields-in-Advanced-eDiscovery.md).

## <a name="add-a-sample-to-a-review-set"></a>Adición de un ejemplo a un conjunto de revisión

Si desea validar los resultados de una búsqueda más exhaustivamente antes de agregarlos todos a un conjunto de revisión, puede agregar un ejemplo de los resultados de la búsqueda a un conjunto de revisión en lugar de agregarlo todo.

Para agregar un ejemplo a un conjunto de revisión, haga clic en una búsqueda en la pestaña **Búsquedas** y haga clic en **Ejemplo** en la página de control flotante. En la página **Parámetros de muestreo** , elija una de las siguientes opciones:

- **% de nivel de confianza** e **intervalo de confianza %** : los elementos agregados al conjunto de revisión se determinarán mediante los parámetros estadísticos que establezca. Si normalmente usa un nivel de confianza e intervalo al realizar el muestreo de los resultados, especifíquelos en los cuadros desplegables. De lo contrario, use la configuración predeterminada.

- **% de ejemplo aleatorio** : los elementos agregados al conjunto de revisión se basan en una selección aleatoria del porcentaje especificado del número total de elementos devueltos por la búsqueda.

Después de seleccionar y configurar una de las opciones anteriores, elija un conjunto de revisión al que agregar el ejemplo y, a continuación, haga clic en **Enviar**. De nuevo, puede realizar un seguimiento del progreso en la pestaña **Trabajos** o en la pestaña **Búsquedas** supervisando el estado de la columna **Datos agregados para revisar el conjunto** .

## <a name="optical-character-recognition"></a>Reconocimiento óptico de caracteres

Al agregar resultados de búsqueda a un conjunto de revisión, la funcionalidad de reconocimiento óptico de caracteres (OCR) en eDiscovery (Premium) extrae automáticamente texto de las imágenes e incluye el texto de la imagen con los datos que se agregan a un conjunto de revisión. Puede ver el texto extraído en el Visor de texto del archivo de imagen seleccionado en el conjunto de revisión. Esto le permite realizar más análisis y revisar el texto de las imágenes. OCR es compatible con archivos sueltos, datos adjuntos de correo electrónico e imágenes incrustadas. Para obtener una lista de los formatos de archivo de imagen que se admiten para OCR, vea [Tipos de archivo admitidos en eDiscovery (Premium)](supported-filetypes-ediscovery20.md#image).

Debe habilitar la funcionalidad OCR para cada caso que cree en eDiscovery (Premium). Para obtener más información, consulte [Configuración de las opciones de búsqueda y análisis](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).
