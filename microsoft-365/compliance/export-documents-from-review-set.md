---
title: Exportar documentos desde un conjunto de revisión
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
description: Obtenga información sobre cómo seleccionar y exportar contenido de un conjunto de revisión avanzada de exhibición de documentos electrónicos para presentaciones o revisiones externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581024"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Exportar documentos desde un conjunto de revisión en exhibición de documentos electrónicos avanzada

La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga al exportar el documento de un conjunto de revisión de eDiscovery avanzado.

Para exportar documentos de un conjunto de revisión:

1. En el Centro de cumplimiento de Microsoft 365,  abra el caso eDiscovery avanzado, seleccione la pestaña Conjuntos de revisión y, a continuación, seleccione el conjunto de opiniones que desea exportar.

2. En el conjunto de revisión, haga clic **en Exportar**  >  **acción**.

   La herramienta Exportar muestra la página desplegable con la configuración para configurar la exportación. Algunas opciones están seleccionadas de forma predeterminada, pero puede cambiar estas opciones. Consulte la siguiente sección para obtener descripciones de las opciones de exportación que puede configurar.

   ![Opciones de configuración para exportar elementos de un conjunto de revisión](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. Después de configurar la exportación, haga clic **en Exportar** para iniciar el proceso de exportación. Según la opción seleccionada  en la sección Opciones de salida, puede tener acceso a los archivos de exportación mediante descarga directa o en la cuenta de Azure Storage de su organización.

> [!NOTE]
> Los trabajos de exportación se conservan durante la duración del caso. Sin embargo, debe descargar el contenido de un trabajo de exportación en un plazo de 30 días después de que se complete el trabajo de exportación.

## <a name="export-options"></a>Opciones de exportación

Use las siguientes opciones para configurar la exportación.

- **Nombre de exportación:** nombre del trabajo de exportación.

- **Descripción:** campo de texto libre para agregar una descripción.

- **Exportar estos documentos**

  - **Solo documentos seleccionados:** esta opción exporta solo los documentos seleccionados actualmente.
  
  - **Todos los documentos del conjunto de revisión:** esta opción exporta todos los documentos del conjunto de revisión.

- **Metadatos**
  
  - **Cargar archivo:** este archivo contiene metadatos para cada archivo. Este archivo normalmente puede ser ingerido por herramientas de exhibición de documentos electrónicos de terceros. Para obtener más información acerca de los campos que se incluyen, vea [Campos de metadatos de documento en Exhibición de documentos electrónicos avanzada.](document-metadata-fields-in-Advanced-eDiscovery.md)
  
  - **Etiquetas:** cuando se selecciona, la información de etiquetado se incluye en el archivo de carga.

- **Contenido**
  
  - **Archivos nativos:** active esta casilla para incluir los archivos nativos de los documentos en el conjunto de revisión. Si elige exportar archivos nativos, tiene las siguientes opciones para exportar conversaciones de chat.
  
  - **Opciones de conversación**

    - **Archivos de conversación:** esta opción exporta conversaciones de chat reconstruidas. Este formato presenta conversaciones en un formulario que se asemeja a lo que los usuarios ven en la aplicación nativa.

    - **Mensajes de chat individuales:** esta opción exporta los archivos de conversación originales a medida que se almacenan en Microsoft 365.

- **Opciones**

  - **Archivos de** texto: esta opción incluye las versiones de texto extraídas de los archivos nativos en la exportación.
  
  - **Reemplace los nativos redactados por archivos PDF convertidos:** si los archivos PDF redactados se generan durante la revisión, estos archivos están disponibles para la exportación. Puede elegir exportar solo los archivos nativos que se han redactado (no seleccionando esta opción) o puede seleccionar esta opción para exportar los archivos PDF que contienen las redacciones reales.

- **Opciones de** salida: el contenido exportado está disponible para su descarga directamente a través de un explorador web o se puede enviar a una cuenta de Azure Storage. Las dos primeras opciones habilitan la descarga directa.
  
  - **Archivos sueltos y PST (el** correo electrónico se agrega a los PST cuando es posible): los archivos se exportan en un formato similar a la estructura de directorio original que ven los usuarios en sus aplicaciones nativas.  Para obtener más información, vea [la sección Archivos sueltos y estructura de exportación de PST.](#loose-files-and-pst-export-structure)
  
  - **Estructura de directorio condensada:** los archivos se exportan e incluyen en la descarga.
  
  - **Estructura de directorio condensada exportada a su** cuenta de Azure Storage: los archivos se exportan a la cuenta de Azure Storage de su organización. Para esta opción, debe proporcionar la dirección URL del contenedor en su cuenta de Azure Storage para exportar los archivos. También debe proporcionar el token de firma de acceso compartido (SAS) para su cuenta de Azure Storage. Para obtener más información, vea [Export documents in a review set to an Azure Storage account](download-export-jobs.md).

En las secciones siguientes se describe la estructura de carpetas para archivos sueltos y opciones de estructura de directorios condensadas.

### <a name="loose-files-and-pst-export-structure"></a>Archivos sueltos y estructura de exportación de PST

Si selecciona esta opción de exportación, el contenido exportado se organiza en la siguiente estructura:

- Carpeta raíz: esta carpeta en el nombre ExportName.zip
  
  - Export_load_file.csv: el archivo de metadatos.
  
  - Summary.csv: un archivo de resumen que también contiene estadísticas de exportación.
  
  - Exchange: esta carpeta contiene todo el contenido de Exchange en formato de archivo nativo. Los archivos nativos se reemplazan por archivos PDF redactados si ha seleccionado la opción Reemplazar **nativos** redactados con ARCHIVOS PDF convertidos.
  
  - SharePoint: esta carpeta contiene todo el contenido nativo de SharePoint en un formato de archivo nativo. Los archivos nativos se reemplazan por archivos PDF redactados si ha seleccionado la opción Reemplazar **nativos** redactados con ARCHIVOS PDF convertidos.

### <a name="condensed-directory-structure"></a>Estructura de directorio condensada

- Carpeta raíz: esta carpeta se denomina ExportName.zip
  
  - Export_load_file.csv: el archivo de metadatos.
  
  - Summary.txt: un archivo de resumen que también contiene estadísticas de exportación.
  
  - NativeFiles: esta carpeta contiene todos los archivos nativos que se exportaron. Si exporta archivos PDF redactados, no se colocarán en archivos PST. En su lugar, se agregan a una carpeta separada.
  
  - Error_files: esta carpeta contiene los siguientes archivos de error, si se incluyen en la exportación:

    - ExtractionError: un archivo CSV que contiene los metadatos disponibles de archivos que no se extrajeron correctamente de los archivos primarios.

    - ProcessingError: este archivo contiene una lista de documentos con errores de procesamiento. Este contenido es de nivel de elemento, lo que significa que si un archivo adjunto produjo un error de procesamiento, el mensaje de correo electrónico que contiene los datos adjuntos se incluye en esta carpeta.
  
  - Extracted_text_files: esta carpeta contiene todos los archivos de texto extraídos que se generaron durante el procesamiento.
