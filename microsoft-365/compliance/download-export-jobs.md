---
title: Exportación de documentos a una cuenta de Azure Storage de la organización
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.custom: seo-marvel-mar2020
description: Exporte documentos de un conjunto de revisión a una cuenta de Azure Storage y, a continuación, use Explorador de Azure Storage para descargarlos en un equipo local.
ms.openlocfilehash: babac7d0289eee2384c12acfe05223bfceba1ce1
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64934849"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a>Exportación de documentos en un conjunto de revisión a una cuenta de Azure Storage

Al exportar documentos desde un conjunto de revisión en un caso de exhibición de documentos electrónicos (Premium), tiene la opción de exportarlos a una cuenta de Azure Storage administrada por su organización. Si usa esta opción, los documentos se cargan en la ubicación de Azure Storage. Después de exportarlos, puede acceder a los documentos (y descargarlos en un equipo local u otra ubicación) mediante el Explorador de Azure Storage. En este artículo se proporcionan instrucciones sobre cómo exportar documentos a la cuenta de Azure Storage y cómo usar el Explorador de Azure Storage para conectarse a una ubicación Azure Storage para descargar los documentos exportados. Para obtener más información sobre Explorador de Azure Storage, consulte [Uso de Explorador de Azure Storage](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).

## <a name="before-you-export-documents-from-a-review-set"></a>Antes de exportar documentos desde un conjunto de revisión

- Debe proporcionar un token de firma de acceso compartido (SAS) para la cuenta de Azure Storage y la dirección URL de un contenedor específico de la cuenta de almacenamiento para exportar documentos desde un conjunto de revisión. Asegúrese de tenerlos a mano (por ejemplo, copiados en un archivo de texto) al realizar el paso 2.

  - **Token de SAS**: asegúrese de que el token de SAS es para la cuenta de Azure Storage (y no para el contenedor). Puede generar un token de SAS para su cuenta en Azure Storage. Para ello, vaya a la cuenta de Azure Storage y seleccione **Compartir firma de acceso** en la configuración **de Configuración** de la hoja cuenta de almacenamiento. Use la configuración predeterminada y permita todos los tipos de recursos al generar el token de SAS.

  - **Dirección URL** del contenedor: debe crear un contenedor en el que cargar los documentos del conjunto de revisión y, a continuación, obtener una copia de la dirección URL del contenedor; por ejemplo, `https://ediscoverydata.blob.core.windows.net/exportdata`. Para obtener la dirección URL, vaya al contenedor en Azure Storage y seleccione **Propiedades** en la sección **Configuración** de la hoja contenedora.

- Descargue e instale el Explorador de Azure Storage. Para obtener instrucciones, consulte [Explorador de Azure Storage herramienta](https://go.microsoft.com/fwlink/p/?LinkId=544842). Use esta herramienta para conectarse al contenedor de la cuenta de Azure Storage y descargar los documentos que exportó en el paso 1.

## <a name="step-1-export-the-documents-from-a-review-set"></a>Paso 1: Exportar los documentos de un conjunto de revisión

El primer paso consiste en crear un trabajo de exportación para exportar documentos de un conjunto de revisión. Para obtener instrucciones más detalladas sobre todas las opciones de exportación, consulte [Exportación de documentos desde un conjunto de revisión](export-documents-from-review-set.md). En el procedimiento siguiente se resalta la configuración para exportar documentos a la cuenta de Azure Storage de la organización.

1. En el portal de cumplimiento de Microsoft Purview, abra el caso de exhibición de documentos electrónicos (Premium), seleccione la pestaña **Conjuntos de revisión** y, a continuación, seleccione el conjunto de revisión que desea exportar.

2. En el conjunto de revisión, haga clic en **AcciónExportar** > .

3. En la página desplegable **Opciones de exportación** , escriba un nombre (obligatorio) y una descripción (opcional) para la exportación.

4. Configure los valores en las secciones documentos, metadatos, contenido y opciones. Para obtener más información sobre esta configuración, consulte [Exportación de documentos desde un conjunto de revisión](export-documents-from-review-set.md).

5. En la sección **Opciones de salida**, seleccione la **opción Estructura de directorios condensada exportada a la cuenta de Azure Storage**.

6. Pegue la dirección URL del contenedor y el token de SAS de la cuenta de almacenamiento en los campos correspondientes.

   ![Pegue la dirección URL de conexión y el token de SAS en los campos correspondientes.](../media/AzureStorageOutputOptions.png)

7. Haga clic en **Exportar** para crear el trabajo de exportación.

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>Paso 2: Obtener la dirección URL de SAS del trabajo de exportación

El siguiente paso es obtener la dirección URL de SAS que se genera después de crear el trabajo de exportación en el paso 1. Use la dirección URL de SAS para conectarse al contenedor de la cuenta de Azure Storage a la que exportó los documentos del conjunto de revisión.

1. En la página **eDiscovery (Premium),** vaya al caso y haga clic en la pestaña **Exportaciones**.

2. En la pestaña **Exportar**, haga clic en el trabajo de exportación que desea descargar. Este es el trabajo de exportación que creó en el paso 1.

3. En la página de control flotante, en **Ubicaciones**, copie la dirección URL de SAS que se muestra. Si es necesario, puede guardarlo en un archivo de texto para que pueda acceder a él en el paso 3.

   ![Copie la dirección URL de SAS que se muestra en Ubicaciones.](../media/eDiscoExportJob.png)

   > [!TIP]
   > La dirección URL de SAS que se muestra en el trabajo de exportación es una concatenación de la dirección URL del contenedor y el token de SAS de la cuenta de Azure Storage. Puede copiarlo desde el trabajo de exportación o crearlo usted mismo combinando la dirección URL y el token de SAS.

## <a name="step-3-connect-to-the-azure-storage-container"></a>Paso 3: Conectar al contenedor de Azure Storage

El último paso consiste en usar la Explorador de Azure Storage y la dirección URL de SAS para conectarse al contenedor de la cuenta de Azure Storage y descargar los documentos exportados en un equipo local.

1. Inicie el Explorador de Azure Storage que descargó e instaló.

2. Haga clic en el icono **Abrir Conectar cuadro de diálogo**.

   ![Haga clic en el icono Agregar cuenta.](../media/AzureStorageConnect.png)

3. En la página **Conectar para Azure Storage**, haga clic en **Contenedor de blobs**.

4. En la página **Seleccionar método de autenticación** , seleccione la opción **Firma de acceso compartido (SAS)** y haga clic en **Siguiente**.

5. En la página **Escribir información de conexión** , pegue la dirección URL de SAS (que obtuvo en el trabajo de exportación en el paso 2) en el cuadro **Dirección URL de SAS del contenedor de blobs** .

    ![Pegue la dirección URL de SAS en el cuadro URI.](../media/AzureStorageConnect3.png)

    Observe que el nombre del contenedor se muestra en el cuadro **Nombre para mostrar** . Puede editar este nombre.

6. Haga clic en **Siguiente** para mostrar la página **de resumen** y, a continuación, haga clic en **Conectar**.

    Se abre el nodo **Contenedores de blobs** (en **Storage Accounts** > **(Attached Containers).** \>

    ![Exporte trabajos en el nodo Contenedores de blobs.](../media/AzureStorageConnect5.png)

    Contiene un contenedor denominado con el nombre para mostrar del paso 5. Este contenedor contiene una carpeta para cada trabajo de exportación que ha descargado en el contenedor de la cuenta de Azure Storage. Estas carpetas se denominan con un identificador que corresponde al identificador del trabajo de exportación. Puede encontrar estos identificadores de exportación (y el nombre de la exportación) en **Información de soporte** técnico en la página desplegable de cada trabajo **preparación de datos para exportación** que aparece en la pestaña **Trabajos** en el caso de eDiscovery (Premium).

7. Haga doble clic en la carpeta del trabajo de exportación para abrirlo.

   Se muestra una lista de carpetas e informes de exportación.

    ![La carpeta de exportación contiene archivos exportados e informes de exportación.](../media/AzureStorageConnect6.png)

8. Para exportar todo el contenido del trabajo de exportación, haga clic en la flecha **Arriba** para volver a la carpeta del trabajo de exportación y, a continuación, haga clic en **Descargar**.

9. Especifique la ubicación en la que quiere descargar los archivos exportados y, a continuación, haga clic en Seleccionar carpeta.

    El Explorador de Azure Storage inicia el proceso de descarga. El estado de la descarga de los elementos exportados se muestra en el panel **Actividades** . Cuando se completa la descarga, se muestra un mensaje.

> [!NOTE]
> En lugar de descargar todo el trabajo de exportación en Explorador de Azure Storage, puede seleccionar elementos específicos para descargar y ver.

## <a name="more-information"></a>Más información

- La carpeta del trabajo de exportación contiene los siguientes elementos. Los elementos reales de la carpeta de exportación vienen determinados por las opciones de exportación configuradas cuando se creó el trabajo de exportación. Para obtener más información sobre estas opciones, consulte [Exportación de documentos desde un conjunto de revisión](export-documents-from-review-set.md).

  - Export_load_file.csv: este archivo CSV es un informe de exportación de detalles que contiene información sobre cada documento exportado. El archivo consta de una columna para cada propiedad de metadatos de un documento. Para obtener una lista y una descripción de los metadatos que se incluyen en este informe, vea la columna **Nombre de campo exportado** de la tabla en [Campos de metadatos del documento en eDiscovery (Premium)](document-metadata-fields-in-advanced-ediscovery.md).

  - Summary.txt: un archivo de texto que contiene un resumen de la exportación, incluidas las estadísticas de exportación.

  - Extracted_text_files: esta carpeta contiene una versión de archivo de texto de cada documento exportado.

  - NativeFiles: esta carpeta contiene una versión de archivo nativa de cada documento exportado.

  - Error_files: esta carpeta incluye los siguientes elementos cuando el trabajo de exportación contiene los archivos de error:

    - ExtractionError.csv: este archivo CSV contiene los metadatos disponibles para los archivos que no se extrajeron correctamente de su elemento primario.

    - ProcessingError: esta carpeta contiene documentos con errores de procesamiento. Este contenido se encuentra en un nivel de elemento, lo que significa que si los datos adjuntos tenían un error de procesamiento, el documento que contiene los datos adjuntos también se incluirá en esta carpeta.
