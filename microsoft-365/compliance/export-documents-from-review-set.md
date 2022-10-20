---
title: Exportación de documentos desde un conjunto de revisión en eDiscovery (Premium)
description: Obtenga información sobre cómo seleccionar y exportar contenido de un conjunto de revisiones de eDiscovery (Premium) para presentaciones o revisiones externas.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
- ediscovery
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ff08e00966a81e936b8960e51af462dbbb362e9
ms.sourcegitcommit: cf3811117bf20cdd27c43390cb2f10c6afc525c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68648396"
---
# <a name="export-documents-from-a-review-set-in-ediscovery-premium"></a>Exportación de documentos desde un conjunto de revisión en eDiscovery (Premium)

La exportación permite a los usuarios personalizar el contenido que se incluye en el paquete de descarga al exportar el documento desde un conjunto de revisión en eDiscovery (Premium).

Para exportar documentos de un conjunto de revisión:

1. En el portal de cumplimiento Microsoft Purview, abra el caso de exhibición de documentos electrónicos (Premium), seleccione la pestaña **Conjuntos de revisión** y, a continuación, seleccione el conjunto de revisión que desea exportar.

2. En el conjunto de revisión, seleccione **Acción** > **Exportar**.

   La herramienta Exportar muestra la página de control flotante con los valores para configurar la exportación. Algunas opciones se seleccionan de forma predeterminada, pero puede cambiarlas. Consulte la sección siguiente para obtener descripciones de las opciones de exportación que puede configurar.

   ![Opciones de configuración para exportar elementos de un conjunto de revisión.](../media/ediscovery-review-set-export-options.png)

3. Después de configurar la exportación, seleccione **Exportar** para iniciar el proceso de exportación. En función de la opción que haya seleccionado en la sección **Opciones de salida** , puede acceder a los archivos de exportación mediante descarga directa o en la cuenta de Azure Storage de su organización.

> [!NOTE]
> Los trabajos de exportación se conservan durante la vida útil del caso. Sin embargo, debe descargar el contenido de un trabajo de exportación en un plazo de 30 días después de que se complete el trabajo de exportación.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="export-options"></a>Opciones de exportación

Use las siguientes opciones para configurar la exportación. No todas las opciones se permiten para algunas opciones de salida, especialmente la exportación de archivos de texto y archivos PDF redactados no se permiten al exportar al formato PST.

- **Nombre de exportación**: nombre del trabajo de exportación. Se usará para asignar un nombre a los archivos ZIP que se descargarán.

- **Descripción**: campo de texto libre para agregar una descripción.

- **Exportación de estos documentos**

  - Solo documentos seleccionados: esta opción exporta solo los documentos que están seleccionados actualmente. Esta opción solo está disponible cuando se seleccionan elementos en un conjunto de revisión.
  
  - Todos los documentos filtrados: esta opción exporta los documentos en un filtro activo. Esta opción solo está disponible cuando se aplica un filtro al conjunto de revisión.
  
  - Todos los documentos del conjunto de revisión: esta opción exporta todos los documentos del conjunto de revisión.

- **Opciones de salida**: el contenido exportado está disponible para su descarga directamente a través de un explorador web o se puede enviar a una cuenta de Azure Storage. Las dos primeras opciones permiten la descarga directa.
  
  - Solo informes: solo se crean el archivo de resumen y carga.
  
  - Archivos flexibles y PST (el correo electrónico se agrega a las PST cuando sea posible): los archivos se exportan en un formato similar a la estructura de directorios original que ven los usuarios en sus aplicaciones nativas.  Para obtener más información, vea la sección [Estructura de exportación de archivos flexibles y PST](#loose-files-and-pst-export-structure) .
  
  - Estructura de directorios condensada: los archivos se exportan e incluyen en la descarga.
  
  - Estructura de directorios condensada exportada a la cuenta de Azure Storage: los archivos se exportan a la cuenta de Azure Storage de la organización. Para esta opción, debe proporcionar la dirección URL del contenedor en la cuenta de Azure Storage a la que exportar los archivos. También tiene que proporcionar el token de firma de acceso compartido (SAS) para la cuenta de Azure Storage. Para obtener más información, consulte [Exportación de documentos en un conjunto de revisión a una cuenta de Azure Storage](download-export-jobs.md).

- **Include**
  
  - Etiquetas: cuando se selecciona, la información de etiquetado se incluye en el archivo de carga.
  
  - Archivos de texto: esta opción incluye las versiones de texto extraídas de los archivos nativos en la exportación.
  
  - Reemplace los nativos redactados por archivos PDF convertidos: si se generan archivos PDF redactados durante la revisión, estos archivos están disponibles para su exportación. Puede optar por exportar solo los archivos nativos que se redactaron (sin seleccionar esta opción) o puede seleccionar esta opción para exportar los archivos PDF que contienen las censuras reales.

En las secciones siguientes se describe la estructura de carpetas para los archivos flexibles y las opciones de estructura de directorios condensadas. Las exportaciones se dividen en archivos ZIP con un tamaño máximo de contenido sin comprimir de 75 GB. Si el tamaño de exportación es inferior a 75 GB, la exportación constará de un archivo de resumen y un único archivo ZIP. Para las exportaciones de más de 75 GB de datos sin comprimir, se crearán varios archivos ZIP. Una vez descargados, los archivos ZIP se pueden descomprimir en una sola ubicación para volver a crear la exportación completa.

### <a name="loose-files-and-pst-export-structure"></a>Archivos flexibles y estructura de exportación de PST

Si selecciona esta opción de exportación, el contenido exportado se organiza en la estructura siguiente:

- Summary.csv: incluye un resumen del contenido exportado desde el conjunto de revisión

- Carpeta raíz: esta carpeta en denominada [Nombre de exportación] x de z.zip y se repetirá para cada partición de archivo ZIP. La carpeta raíz contiene lo siguiente:
  
  - Export_load_file_x de z.csv: el archivo de metadatos.
  
  - Advertencias y errores x de z.csv: este archivo incluye información sobre los errores detectados al intentar exportar desde el conjunto de revisión.
  
  - Exchange: esta carpeta contiene todo el contenido de Exchange almacenado en archivos PST. Los archivos PDF redactados no se pueden incluir con esta opción. Si se selecciona un archivo adjunto en el conjunto de revisión, el mensaje de correo electrónico primario se exportará con los datos adjuntos adjuntos adjuntos.
  
    La carpeta de Exchange también puede contener una subcarpeta denominada mailboxname_loosefiles.zip, que contiene los siguientes elementos:

    - Mensajes protegidos por Information Rights Management (IRM) que se han descodificado.
    - Mensajes corregidos por errores.
    - Datos adjuntos o vínculos modernos a los que se hace referencia en los mensajes.
    - Elementos cifrados (que no se incluyen en los archivos PST de la carpeta de Exchange).
  
  - SharePoint: esta carpeta contiene todo el contenido nativo de SharePoint en un formato de archivo nativo. Los archivos PDF redactados no se pueden incluir con esta opción.

### <a name="condensed-directory-structure"></a>Estructura de directorios condensada

- Summary.csv: incluye un resumen del contenido exportado desde el conjunto de revisión

- Carpeta raíz: esta carpeta en denominada [Nombre de exportación] x de z.zip y se repetirá para cada partición de archivo ZIP.
  
  - Export_load_file_x de z.csv: el archivo de metadatos y también incluye la ubicación de cada archivo almacenado en el archivo ZIP.
  
  - Advertencias y errores x de z.csv: este archivo incluye información sobre los errores detectados al intentar exportar desde el conjunto de revisión.

  - NativeFiles: esta carpeta contiene todos los archivos nativos que se exportaron. Los archivos nativos se reemplazan por archivos PDF redactados si *seleccionó la opción Reemplazar nativos redactados con archivos PDF convertidos* .
  
  - Error_files: esta carpeta contiene archivos que tenían errores de extracción u otro tipo de procesamiento. Los archivos se colocarán en carpetas independientes, Ya sea ExtractionError o ProcessingError. Estos archivos aparecen en el archivo de carga.

  - Extracted_text_files: esta carpeta contiene todos los archivos de texto extraídos que se generaron durante el procesamiento.

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a>Estructura de directorios condensada exportada a la cuenta de Azure Storage

Esta opción usa la misma estructura general que la *estructura de directorios condensada*, pero el contenido no se comprime y los datos se guardan en la cuenta de Azure Storage. Esta opción se usa generalmente cuando se trabaja con un proveedor de exhibición de documentos electrónicos de terceros. Para obtener más información sobre cómo usar esta opción, consulte [Exportación de documentos en un conjunto de revisión a una cuenta de Azure Storage](download-export-jobs.md).
