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
description: Obtenga información sobre cómo seleccionar y exportar contenido de un conjunto de revisiones para presentaciones o revisiones externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285366"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Exportar documentos de un conjunto de revisión en eDiscovery avanzado

La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga. La herramienta Exportar proporciona una página de configuración con las siguientes opciones:

![Opciones para exportar elementos de un conjunto de revisión](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a>Opciones de exportación

- Nombre de exportación: nombre del trabajo de exportación.

- Descripción: campo de texto libre para agregar una descripción.

- Exporte estos documentos:

  - Sólo documentos seleccionados: exporta solo los documentos seleccionados actualmente.
  
  - Todos los documentos del conjunto de revisión: exporta todos los documentos del conjunto de revisión

- Metadata
  
  - Cargar archivo: este archivo contiene metadatos para cada archivo. Vea [los campos de metadatos del documento en eDiscovery avanzado](document-metadata-fields-in-Advanced-eDiscovery.md) para obtener más información sobre los campos que se incluyen. Normalmente, las herramientas de exhibición de documentos electrónicos de terceros pueden ingerir este archivo.
  
  - Etiquetas: cuando se selecciona, la información de etiquetado se incluirá en el archivo de carga.

- Contenido
  
  - Archivos nativos: active esta casilla para incluir los archivos nativos.
  
  - Opciones de conversación
    
    - Archivos de conversación: exportar mensajes de chat reconstruidos. Este formato presenta las conversaciones en un formulario similar al que ven los usuarios en la aplicación nativa.
    
    - Mensajes de chat individuales: exporte los archivos de conversación originales tal como se almacenan en Microsoft 365.

- Opciones

  - Archivos de texto: incluye versiones de texto extraídas de archivos nativos.
  
  - Reemplazar nativos redactados por archivos PDF convertidos: si se generan archivos PDF redactados durante la revisión, estos archivos están disponibles para su exportación. Puede elegir exportar solo los archivos nativos que se censuraron (no seleccionando esta opción) o puede seleccionar esta opción para exportar los archivos PDF que contienen las redacciones reales.

- Opciones de salida (el contenido exportado está disponible para su descarga directamente a través de un explorador web o se puede enviar a una cuenta de Azure Storage. Las dos primeras opciones habilitan la descarga directa).
  
  - Archivos sueltos y ARCHIVOSTS (el correo electrónico se agrega a los archivos PST cuando es posible): los archivos se exportan en un formato similar a la estructura de directorios original que ven los usuarios en sus aplicaciones nativas.  Para obtener más información, vea la [sección Sobre archivos sueltos y la estructura de exportación de](#loose-files-and-pst-export-structure) PST.
  
  - Estructura de directorios condensada: los archivos se exportan e incluyen en la descarga.
  
  - Estructura de directorios condensada exportada a su cuenta de Azure Storage: los archivos se exportan a la cuenta de Azure Storage de su organización.

## <a name="loose-files-and-pst-export-structure"></a>Archivos sueltos y estructura de exportación de PST

Si selecciona esta opción de exportación, el contenido exportado se organiza en la siguiente estructura:

- Carpeta raíz: esta carpeta en el nombre ExportName.zip
  
  - Export_load_file.csv: archivo de metadatos.
  
  - Summary.csv: un archivo de resumen que también contiene estadísticas de exportación.
  
  - Exchange: esta carpeta contiene todo el contenido de Exchange en formato de archivo nativo. Los archivos nativos se reemplazan por archivos PDF redactados si seleccionaste la opción Reemplazar **nativos redactados con archivos PDF** convertidos.
  
  - SharePoint = Esta carpeta contiene todo el contenido nativo de SharePoint en un formato de archivo nativo. Los archivos nativos se reemplazan por archivos PDF redactados si seleccionaste la opción Reemplazar **nativos redactados con archivos PDF** convertidos.

## <a name="condensed-directory-structure"></a>Estructura de directorios condensada

- Carpeta raíz: esta carpeta se denomina ExportName.zip
  
  - Export_load_file.csv: archivo de metadatos.
  
  - Summary.txt: un archivo de resumen que también contiene estadísticas de exportación.
  
  - Input_or_native_files: esta carpeta contiene todos los archivos nativos que se exportaron. Si exporta archivos PDF redactados, no se colocarán en archivos PST. En su lugar, se agregan a una carpeta separada.
  
  - Error_files: esta carpeta contiene los siguientes archivos de error, si se incluyen en la exportación:
    
    - ExtractionError. Un archivo CSV que contiene los metadatos disponibles de los archivos que no se extrajeron correctamente de los archivos primarios.
    
    - ProcessingError: este archivo contiene una lista de documentos con errores de procesamiento. Este contenido es de nivel de elemento, lo que significa que si un archivo adjunto produjo un error de procesamiento, el mensaje de correo electrónico que contiene los datos adjuntos se incluirá en esta carpeta.
  
  - Extracted_text_files: esta carpeta contiene todos los archivos de texto extraídos que se generaron durante el procesamiento.

> [!NOTE]
> Los trabajos de exportación se conservan durante el tiempo que dura el caso y se pueden descargar siempre que no se elimine el caso.
