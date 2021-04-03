---
title: Exportar documentos a la cuenta de Azure Storage de su organización
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
ms.custom: seo-marvel-mar2020
description: Exporte documentos en un conjunto de revisión en una cuenta de Azure Storage y, a continuación, use el Explorador de Azure Storage para descargarlos en un equipo local.
ms.openlocfilehash: dfb3892f31e857d4744f6da337c924efaa87ab11
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574732"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a>Exportar documentos en un conjunto de revisión en una cuenta de Azure Storage

Al exportar documentos de un conjunto de revisión en un caso de exhibición de documentos electrónicos avanzada, tiene la opción de exportarlos a una cuenta de Azure Storage administrada por su organización. Si usó esta opción, los documentos se cargarán en la ubicación de Azure Storage. Después de exportarlos, puede acceder a los documentos (y descargarlos en un equipo local u otra ubicación) mediante el Explorador de Azure Storage. En este artículo se proporcionan instrucciones sobre cómo exportar documentos a su cuenta de Azure Storage y el uso del Explorador de Azure Storage para conectarse a una ubicación de Azure Storage para descargar los documentos exportados. Para obtener más información acerca del Explorador de Azure Storage, consulte [Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).

## <a name="before-you-export-documents-from-a-review-set"></a>Antes de exportar documentos de un conjunto de revisión

- Debe proporcionar un token de firma de acceso compartido (SAS) para su cuenta de Azure Storage y la dirección URL de un contenedor específico de la cuenta de almacenamiento para exportar documentos de un conjunto de opiniones. Asegúrese de tener estos a mano (por ejemplo, copiados en un archivo de texto) al realizar el paso 2

  - **Token sas:** asegúrese de obtener el token sas es para su cuenta de Azure Storage (y no para el contenedor). Puede generar un token sas para su cuenta en Azure Storage. Para ello, vaya a la cuenta de Azure Storage  y seleccione **Compartir** firma de acceso en la hoja Configuración de la cuenta de almacenamiento. Use la configuración predeterminada y permita todos los tipos de recursos al generar el token sas.

  - **Dirección URL del** contenedor: debe crear un contenedor en el que cargar los documentos del conjunto de revisión y, a continuación, obtener una copia de la dirección URL del contenedor; por ejemplo, `https://ediscoverydata.blob.core.windows.net/exportdata` . Para obtener la dirección URL, vaya al contenedor de Azure Storage y seleccione **Propiedades** en la sección **Configuración** de la hoja contenedora.

- Descargue e instale el Explorador de Azure Storage. Para obtener instrucciones, consulte [Herramienta del Explorador de Azure Storage](https://go.microsoft.com/fwlink/p/?LinkId=544842). Use esta herramienta para conectarse al contenedor de su cuenta de Azure Storage y descargar los documentos que exportó en el paso 1.

## <a name="step-1-export-the-documents-from-a-review-set"></a>Paso 1: Exportar los documentos de un conjunto de revisión

El primer paso es crear un trabajo de exportación para exportar documentos fuera de un conjunto de revisión. Para obtener instrucciones más detalladas sobre todas las opciones de exportación, vea [Export documents from a review set](export-documents-from-review-set.md). El siguiente procedimiento resalta la configuración para exportar documentos a la cuenta de Azure Storage de su organización.

1. En el Centro de cumplimiento de Microsoft 365,  abra el caso eDiscovery avanzado, seleccione la pestaña Conjuntos de revisión y, a continuación, seleccione el conjunto de opiniones que desea exportar.

2. En el conjunto de revisión, haga clic **en Exportar**  >  **acción**.

3. En la página desplegable **Opciones** de exportación, escriba un nombre (obligatorio) y una descripción (opcional) para la exportación.

4. Configure la configuración en las secciones documentos, metadatos, contenido y opciones. Para obtener más información acerca de esta configuración, vea [Export documents from a review set](export-documents-from-review-set.md).

5. En la **sección Opciones de** salida, seleccione la opción Estructura de directorio **condensada exportada a su cuenta de Azure Storage.**

6. Pegue la dirección URL del contenedor y el token SAS de la cuenta de almacenamiento en los campos correspondientes.

   ![Pegue la dirección URL de conexión y el token SAS en los campos correspondientes](../media/AzureStorageOutputOptions.png)

7. Haga **clic en** Exportar para crear el trabajo de exportación.

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>Paso 2: Obtener la dirección URL de SAS del trabajo de exportación

El siguiente paso es obtener la dirección URL de SAS que se genera después de crear el trabajo de exportación en el paso 1. Use la dirección URL de SAS para conectarse al contenedor de la cuenta de Azure Storage a la que exportó los documentos del conjunto de revisión.

1. En la **página Exhibición de documentos electrónicos avanzada,** vaya al caso y, a continuación, haga clic en la **pestaña** Exportaciones.

2. En la **pestaña** Exportaciones, haga clic en el trabajo de exportación que desea descargar. Este es el trabajo de exportación que creó en el paso 1.

3. En la página desplegable, en **Ubicaciones**, copie la dirección URL de SAS que se muestra. Si es necesario, puede guardarlo en un archivo de texto para que pueda acceder a él en el paso 3.

   ![Copiar la dirección URL de SAS mostrada en Ubicaciones](../media/eDiscoExportJob.png)

   > [!TIP]
   > La dirección URL de SAS que se muestra en el trabajo de exportación es una concatenación de la dirección URL del contenedor y el token sas de la cuenta de Azure Storage. Puede copiarlo desde el trabajo de exportación o crearlo usted mismo combinando la dirección URL y el token sas.

## <a name="step-3-connect-to-the-azure-storage-container"></a>Paso 3: Conectarse al contenedor de Azure Storage

El paso final es usar el Explorador de Azure Storage y la dirección URL de SAS para conectarse al contenedor en su cuenta de Azure Storage y descargar los documentos exportados a un equipo local.

1. Inicie el Explorador de Azure Storage que descargó e instaló.

2. Haga clic en **el icono Abrir cuadro de diálogo** Conectar.

   ![Haga clic en el icono Agregar cuenta](../media/AzureStorageConnect.png)

3. En la página **Conectarse a Azure Storage,** haga clic en **Contenedor de blobs.**

4. En la **página Seleccionar método de autenticación,** seleccione la opción Firma de acceso compartido **(SAS)** y, a continuación, haga clic **en Siguiente**.

5. En la **página Escribir** información de conexión, pegue la dirección URL de SAS (que obtuvo en el trabajo de exportación del paso 2) en el cuadro Dirección URL sas del contenedor **de blobs.**

    ![Pegar la dirección URL de SAS en el cuadro URI](../media/AzureStorageConnect3.png)

    Observe que el nombre del contenedor se muestra en el **cuadro Nombre para** mostrar. Puede editar este nombre.

6. Haga **clic en** Siguiente para mostrar la página **de** resumen y, a continuación, haga clic en **Conectar**.

    Se **abre el nodo Contenedores** de blobs (en **Cuentas** de almacenamiento  >  **(contenedores** \> adjuntos).

    ![Exportar trabajos en el nodo contenedores blobs](../media/AzureStorageConnect5.png)

    Contiene un contenedor denominado con el nombre para mostrar del paso 5. Este contenedor contiene una carpeta para cada trabajo de exportación que haya descargado en el contenedor de su cuenta de Azure Storage. Estas carpetas se denominan con un identificador que corresponde al identificador del trabajo de exportación. Puede encontrar estos IDs de exportación (y  el nombre de la exportación) en Información de  soporte técnico en la página desplegable para cada trabajo de preparación de datos para exportación que aparece en la pestaña Trabajos en el caso eDiscovery avanzado. 

7. Haga doble clic en la carpeta de trabajos de exportación para abrirlo.

   Se muestra una lista de carpetas e informes de exportación.

    ![La carpeta de exportación contiene archivos exportados e informes de exportación](../media/AzureStorageConnect6.png)

8. Para exportar todo el contenido del trabajo de exportación, haga clic en la flecha **arriba** para volver a la carpeta de trabajos de exportación y, a continuación, haga clic en **Descargar**.

9. Especifique la ubicación donde desea descargar los archivos exportados y, a continuación, haga clic en Seleccionar carpeta.

    El Explorador de Azure Storage inicia el proceso de descarga. El estado de la descarga de los elementos exportados se muestra en el **panel** Actividades. Se muestra un mensaje cuando se completa la descarga.

> [!NOTE]
> En lugar de descargar todo el trabajo de exportación en el Explorador de Azure Storage, puede seleccionar elementos específicos para descargar y ver.

## <a name="more-information"></a>Más información

- La carpeta de trabajos de exportación contiene los siguientes elementos. Los elementos reales de la carpeta de exportación están determinados por las opciones de exportación configuradas cuando se creó el trabajo de exportación. Para obtener más información acerca de estas opciones, vea [Export documents from a review set](export-documents-from-review-set.md).

  - Export_load_file.csv: este archivo CSV es un informe de exportación detallado que contiene información sobre cada documento exportado. El archivo consta de una columna para cada propiedad de metadatos de un documento. Para obtener una lista y una descripción de los metadatos que se incluyen en este informe, vea la columna **Exported field name** en la tabla en Document metadata fields in Advanced [eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).

  - Summary.txt: un archivo de texto que contiene un resumen de la exportación, incluidas las estadísticas de exportación.

  - Extracted_text_files: esta carpeta contiene una versión de archivo de texto de cada documento exportado.

  - NativeFiles: esta carpeta contiene una versión de archivo nativa de cada documento exportado.

  - Error_files: esta carpeta incluye los siguientes elementos cuando el trabajo de exportación contiene archivos de error:

    - ExtractionError.csv: este archivo CSV contiene los metadatos disponibles para los archivos que no se extrajeron correctamente de su elemento primario.

    - ProcessingError: esta carpeta contiene documentos con errores de procesamiento. Este contenido está en un nivel de elemento, lo que significa que si un archivo adjunto tuvo un error de procesamiento, el documento que contiene los datos adjuntos también se incluirá en esta carpeta.
