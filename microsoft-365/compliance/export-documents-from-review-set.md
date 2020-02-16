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
description: ''
ms.openlocfilehash: 9a732258e787de3407731f0fdfc98ed07653df71
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074366"
---
# <a name="export-documents-from-a-review-set"></a>Exportar documentos desde un conjunto de revisión

Puede exportar el contenido para la presentación o la revisión externa a partir de un conjunto de revisión por uno de los siguientes métodos:

- [Descargar documentos](#download-documents-from-a-review-set)
 
- [Exportar documentos](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a>Descargar documentos de un conjunto de revisión

La descarga ofrece una forma sencilla de descargar contenido de un conjunto de revisión en formato nativo. Aprovecha las características de transferencia de datos del explorador para que aparezca un mensaje del explorador una vez que la descarga esté lista. Los archivos descargados con este método se comprimen en un archivo contenedor y serán archivos de nivel de elemento. Esto significa que, si selecciona un archivo adjunto, recibirá automáticamente el correo electrónico con los datos adjuntos incluidos. De forma similar, si selecciona una hoja de cálculo de Excel que estaba incrustada en un documento de Word, recibirá el documento de Word con la hoja de cálculo de Excel incrustada. Los elementos descargados conservarán la fecha de la última modificación, que se puede ver como una propiedad de archivo.

Para descargar contenido de un conjunto de revisión, seleccione los archivos que desea descargar y, a continuación, seleccione "Descargar" en el menú acciones.

![Una captura de pantalla de una descripción de equipo generada automáticamente](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a>Exportar documentos desde un conjunto de revisión

La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga. Proporciona una página de configuración con la siguiente configuración:

### <a name="metadata-file"></a>Archivo de metadatos

Esto puede considerarse el "Cargar archivo" que contiene metadatos asociados con los archivos que se exportan. Para obtener una lista de los campos exportados disponibles en el archivo de metadatos, consulte [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md). Por lo general, este archivo puede ser recopilado por herramientas de terceros.

### <a name="tag-data"></a>Datos de etiqueta

Este contenido se agregaría como campos en el archivo de metadatos. Contiene toda la información de etiqueta aplicada en los conjuntos de revisión.

### <a name="text-files"></a>Archivos de texto

Los archivos de texto se pueden generar para cada archivo exportado de un conjunto de revisión. A menudo, los asociados de servicios necesitan estos archivos como parte de la recopilación de datos en herramientas de terceros.

### <a name="redacted-files"></a>Archivos censurados

Si se generan archivos PDF censurados durante la revisión, estos archivos están disponibles durante la exportación. Puede decidir si desea exportar solo los archivos nativos o reemplazar los archivos nativos que requerían censura con los archivos PDF que contienen las redacciones reales.

### <a name="export-location"></a>Ubicación de exportación

El contenido exportado se entrega en un BLOB de Azure o el BLOB de un cliente de Microsoft se puede usar si los detalles se proporcionan en la exportación.

### <a name="export-structure"></a>Exportar estructura

Cuando se exporta contenido desde un conjunto de revisión, el contenido se organiza en la estructura siguiente.

  - Carpeta raíz: identificador de descarga
    
      - Exportar\_archivo\_de carga. csv = archivo de metadatos
    
      - Summary. txt = un archivo de resumen con las estadísticas de exportación
    
      - Archivos\_nativos\_o de entrada = contiene todos los archivos nativos
    
      - Archivos\_de errores = contiene los archivos de error incluidos en la exportación
        
          - ExtractionError: un CSV que contiene los metadatos disponibles de los archivos que no se han extraído correctamente de los archivos principales
        
          - ProcessingError: contenido con errores de procesamiento. Este contenido es el significado del nivel de elemento si los datos adjuntos experimentan un error de procesamiento, el correo electrónico que contiene los datos adjuntos se incluirá en esta carpeta.
    
      - Archivos\_de\_texto extraídos = contiene todos los archivos de texto extraídos generados en el procesamiento.
