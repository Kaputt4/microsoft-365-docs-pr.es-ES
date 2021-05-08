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
description: Obtenga información sobre cómo seleccionar y exportar contenido de un conjunto de Advanced eDiscovery para presentaciones o revisiones externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 76865ae92d3b3090ae2bba01c9b3e9e0f1f86366
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244366"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Exportar documentos de un conjunto de revisión en Advanced eDiscovery

La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga al exportar el documento de un conjunto de revisión en Advanced eDiscovery.

Para exportar documentos de un conjunto de revisión:

1. En el Microsoft 365 de cumplimiento, abra el Advanced eDiscovery,  seleccione la pestaña Conjuntos de revisión y, a continuación, seleccione el conjunto de revisión que desea exportar.

2. En el conjunto de revisión, haga clic **en Exportar**  >  **acción**.

   La herramienta Exportar muestra la página desplegable con la configuración para configurar la exportación. Algunas opciones están seleccionadas de forma predeterminada, pero puede cambiar estas opciones. Consulte la siguiente sección para obtener descripciones de las opciones de exportación que puede configurar.

   ![Opciones de configuración para exportar elementos de un conjunto de revisión](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. Después de configurar la exportación, haga clic **en Exportar** para iniciar el proceso de exportación. Según la opción seleccionada  en la sección Opciones de salida, puede tener acceso a los archivos de exportación mediante descarga directa o en la cuenta de Azure Storage organización.

> [!NOTE]
> Los trabajos de exportación se conservan durante la duración del caso. Sin embargo, debe descargar el contenido de un trabajo de exportación en un plazo de 30 días después de que se complete el trabajo de exportación.

## <a name="export-options"></a>Opciones de exportación

Use las siguientes opciones para configurar la exportación. No todas las opciones están permitidas para algunas opciones de salida, sobre todo, la exportación de archivos de texto y archivos PDF redactadas no se permite al exportar al formato PST.

- **Nombre de exportación:** nombre del trabajo de exportación. Esto se usará para nombrar los archivos ZIP que se descargarán.

- **Descripción:** campo de texto libre para agregar una descripción.

- **Exportar estos documentos**

  - Solo documentos seleccionados: esta opción exporta solo los documentos seleccionados actualmente. Esta opción solo está disponible cuando los elementos están seleccionados en un conjunto de revisión.
  - Todos los documentos filtrados: esta opción exporta los documentos en un filtro activo. Esta opción solo está disponible cuando se aplica un filtro al conjunto de revisión.
  - Todos los documentos del conjunto de revisión: esta opción exporta todos los documentos del conjunto de revisión.

- **Opciones de** salida: el contenido exportado está disponible para su descarga directamente a través de un explorador web o se puede enviar a una cuenta Azure Storage usuario. Las dos primeras opciones habilitan la descarga directa.
  
  - Solo informes: solo se crean el archivo de resumen y carga.
  - Archivos sueltos y PST (el correo electrónico se agrega a los ARCHIVOS PST cuando es posible): los archivos se exportan en un formato similar a la estructura de directorio original que ven los usuarios en sus aplicaciones nativas.  Para obtener más información, vea [la sección Archivos sueltos y estructura de exportación de PST.](#loose-files-and-pst-export-structure)
  - Estructura de directorio condensada: los archivos se exportan e incluyen en la descarga.
  - Estructura de directorio condensada exportada a su Azure Storage: los archivos se exportan a la cuenta de Azure Storage organización. Para esta opción, debe proporcionar la dirección URL del contenedor en su cuenta de Azure Storage a la que exportar los archivos. También debe proporcionar el token de firma de acceso compartido (SAS) para su Azure Storage cuenta. Para obtener más información, vea [Export documents in a review set to an Azure Storage account](download-export-jobs.md).

- **Include**
  - Etiquetas: cuando se selecciona, la información de etiquetado se incluye en el archivo de carga.
  - Archivos de texto: esta opción incluye las versiones de texto extraídas de los archivos nativos en la exportación.
  - Reemplace los nativos redactados por archivos PDF convertidos: si los archivos PDF redactados se generan durante la revisión, estos archivos están disponibles para la exportación. Puede elegir exportar solo los archivos nativos que se han redactado (no seleccionando esta opción) o puede seleccionar esta opción para exportar los archivos PDF que contienen las redacciones reales.

## <a name="the-following-sections-describe-the-folder-structure-for-loose-files-and-condensed-directory-structure-options"></a>En las secciones siguientes se describe la estructura de carpetas para archivos sueltos y opciones de estructura de directorios condensadas

Las exportaciones se particionan en archivos ZIP con un tamaño máximo de contenido sin comprimir de 75 GB. Si el tamaño de exportación es inferior a 75 GB, la exportación constará de un archivo de resumen y un único archivo ZIP. Para las exportaciones que superen los 75 GB de datos sin comprimir, se crearán varios archivos ZIP. Una vez descargados, los archivos ZIP se pueden descomprimir en una sola ubicación para volver a crear la exportación completa.

### <a name="loose-files-and-pst-export-structure"></a>Archivos sueltos y estructura de exportación de PST

Si selecciona esta opción de exportación, el contenido exportado se organiza en la siguiente estructura:

- Summary.csv: incluye un resumen del contenido exportado desde el conjunto de revisión
- Carpeta raíz: esta carpeta en el nombre [Export Name] x de z.zip y se repetirá para cada partición de archivo ZIP.
  - Export_load_file_x de z.csv: el archivo de metadatos.
  - Advertencias y errores x de z.csv: este archivo incluye información sobre los errores detectados al intentar exportar desde el conjunto de revisión.
  - Exchange: esta carpeta contiene todo el contenido de Exchange almacenado en archivos PST. Los archivos PDF redactados no se pueden incluir con esta opción. Si se selecciona un archivo adjunto en el conjunto de revisión, el correo electrónico primario se exportará con los datos adjuntos adjuntos adjuntos.
  - SharePoint: esta carpeta contiene todo el contenido nativo de SharePoint en un formato de archivo nativo. Los archivos PDF redactados no se pueden incluir con esta opción.

### <a name="condensed-directory-structure"></a>Estructura de directorio condensada

- Summary.csv: incluye un resumen del contenido exportado desde el conjunto de revisión
- Carpeta raíz: esta carpeta en el nombre [Export Name] x de z.zip y se repetirá para cada partición de archivo ZIP.
  - Export_load_file_x de z.csv: el archivo de metadatos y también incluye la ubicación de cada archivo almacenado en el archivo ZIP.
  - Advertencias y errores x de z.csv: este archivo incluye información sobre los errores detectados al intentar exportar desde el conjunto de revisión.
  - NativeFiles: esta carpeta contiene todos los archivos nativos que se exportaron. Los archivos nativos se reemplazan por archivos PDF redactados si ha seleccionado la opción Reemplazar *nativos* redactados con ARCHIVOS PDF convertidos.
  - Error_files: esta carpeta contiene archivos que tuvieron un error de extracción u otro procesamiento. Los archivos se colocarán en carpetas independientes, ya sea ExtractionError o ProcessingError. Estos archivos se enumeran en el archivo de carga.
  - Extracted_text_files: esta carpeta contiene todos los archivos de texto extraídos que se generaron durante el procesamiento.

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a>Estructura de directorio condensada exportada a Azure Storage cuenta

Esta opción usa la misma estructura general que la estructura de directorio condensada, pero el contenido no está comprimido y los datos se guardan en su Azure Storage cuenta. Esta opción se usa generalmente al trabajar con un proveedor de exhibición de documentos electrónicos de terceros. Para obtener más información sobre cómo usar esta opción, vea Exportar documentos en una revisión [establecida en una cuenta Azure Storage .](download-export-jobs.md)
