---
title: Corrección de errores al procesar los datos
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
ms.assetid: ''
description: Obtenga información sobre cómo usar la corrección de errores para corregir problemas de datos en eDiscovery (Premium) que podrían impedir el procesamiento adecuado del contenido.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1f56ad34cb295103178c5f244ccd78d7ad3757b0
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64994554"
---
# <a name="error-remediation-when-processing-data"></a>Corrección de errores al procesar los datos

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

La corrección de errores permite a los administradores de eDiscovery corregir los problemas de datos que impiden que microsoft Purview eDiscovery (Premium) procese correctamente el contenido. Por ejemplo, los archivos protegidos con contraseña no se pueden procesar, ya que los archivos están bloqueados o cifrados. Mediante la corrección de errores, los administradores de eDiscovery pueden descargar archivos con estos errores, quitar la protección con contraseña y, a continuación, cargar los archivos corregidos.

Use el siguiente flujo de trabajo para corregir archivos con errores en casos de eDiscovery (Premium).

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Creación de una sesión de corrección de errores para corregir archivos con errores de procesamiento

> [!NOTE]
> Si el asistente para la corrección de errores se cierra en cualquier momento durante el procedimiento siguiente, puede volver a la sesión de corrección de errores en la pestaña **Procesamiento** seleccionando **Correcciones** en el menú desplegable **Ver** .

1. En la pestaña **Procesamiento** del caso de exhibición de documentos electrónicos (Premium), seleccione **Errores** en el menú desplegable **Ver** y, a continuación, seleccione un conjunto de revisión o todo el caso en el menú desplegable **Ámbito**. Esta sección muestra todos los errores de caso o error de un conjunto de revisión específico.

   ![Corrección de errores.](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. Seleccione los errores que desea corregir haciendo clic en el botón de radio situado junto al tipo de error o tipo de archivo.  En el ejemplo siguiente, vamos a corregir un archivo protegido con contraseña.

3. Haga clic en **Nueva corrección de errores**.

    El flujo de trabajo de corrección de errores comienza con una fase de preparación en la que los archivos con errores se copian en una ubicación de Azure Storage proporcionada por Microsoft para que pueda descargarlos en el equipo local para corregirlos.

    ![Preparación de la corrección de errores.](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Una vez completada la preparación, haga clic en **Siguiente: Descargar archivos** para continuar con la descarga.

    ![Descargar archivos.](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Para descargar archivos, especifique la ruta **Destino para la descarga**. Se trata de una ruta de acceso a la carpeta principal del equipo local donde se descargará el archivo.  La ruta de acceso predeterminada, %USERPROFILE%\Downloads\errors, apunta a la carpeta de descargas del usuario que ha iniciado sesión. Puede cambiar esta ruta de acceso si lo desea. Si lo cambia, se recomienda usar una ruta de acceso de archivo local para obtener el mejor rendimiento. No use una ruta de acceso de red remota. Por ejemplo, podría usar la ruta **de acceso C:\Remediation**.

   La ruta de acceso a la carpeta primaria se agrega automáticamente al comando AzCopy (como valor del parámetro **/Dest** ).

6. Copie el comando predefinido haciendo clic en **Copiar en el Portapapeles**. Abra un símbolo del sistema Windows, pegue el comando AzCopy y presione **Entrar**.

    ![Prepárese para la corrección de errores.](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > Debe usar AzCopy v8.1 para usar correctamente el comando que se proporciona en la página **Descargar archivos** . También debe usar AzCopy v8.1 para cargar los archivos en el paso 10. Para instalar esta versión de AzCopy, consulte [Transferencia de datos con AzCopy v8.1 en Windows](/previous-versions/azure/storage/storage-use-azcopy). Si se produce un error en el comando AzCopy proporcionado, consulte [Solución de problemas de AzCopy en eDiscovery (Premium)](troubleshooting-azcopy.md).

    Los archivos que seleccionó se descargarán en la ubicación que especificó en el paso 5. En la carpeta principal (por ejemplo, **C:\Remediation**), se crea automáticamente la siguiente estructura de subcarpetas:

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - La *subcarpeta 1* recibe el nombre del Id. del caso o del conjunto de revisión, según el ámbito que seleccionó en el paso 1.

    - La *subcarpeta 2* recibe el nombre del Id. de archivo del archivo descargado.

    - El archivo descargado se encuentra en la *subcarpeta 2* y también recibe el nombre del Id. de archivo.

    Este es un ejemplo de la ruta de acceso de la carpeta y el nombre del archivo de error que se crea cuando los elementos se descargan en la carpeta primaria **C:\Remediation** :

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    Si se descargan varios archivos, cada uno de ellos se descarga en una subcarpeta denominada con el identificador de archivo.

    > [!IMPORTANT]
    > Al cargar archivos en los pasos 9 y 10, los archivos corregidos deben tener ese mismo nombre de archivo y estar ubicados en la misma estructura de subcarpetas. Los nombres de subcarpeta y archivo se usan para asociar el archivo corregido con el archivo de error original. Si se cambian la estructura de carpetas o los nombres de archivo, recibirá el siguiente error: `Cannot apply Error Remediation to the current Workingset`. Para evitar problemas, se recomienda mantener los archivos corregidos en la misma carpeta primaria y estructura de subcarpetas.

7. Después de descargar los archivos, puede corregirlos con una herramienta adecuada. En el caso de los archivos protegidos con contraseña, hay varias herramientas de descifrado de contraseñas que puede usar. Si conoce las contraseñas de los archivos, puede abrirlos y quitar la protección con contraseña.

8. Vuelva a eDiscovery (Premium) y al Asistente para la corrección de errores y, a continuación, haga clic en **Siguiente: Upload archivos**.  Esto lo lleva a la página siguiente, donde ahora puede cargar los archivos.

    ![archivos Upload.](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Especifique la carpeta principal donde se encuentran los archivos corregidos en el cuadro de texto **Ruta de acceso a la ubicación de los archivos** De nuevo, la carpeta primaria debe tener la misma estructura de subcarpetas que se creó al descargar los archivos.

    La ruta de acceso a la carpeta primaria se agrega automáticamente al comando AzCopy (como valor del parámetro **/Source** ).

10. Copie el comando predefinido haciendo clic en **Copiar en el Portapapeles**. Abra un símbolo del sistema Windows, pegue el comando AzCopy y presione **Entrar**. cargar los archivos.

    ![Resultados de la carga correcta de archivos corregidos en Azcopy.](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Después de ejecutar el comando AzCopy, haga clic en **Siguiente: Procesar archivos**.

    Una vez completado el procesamiento, puede ir a revisar el conjunto y ver los archivos corregidos.

## <a name="remediating-errors-in-container-files"></a>Corrección de errores en archivos de contenedor

En situaciones en las que eDiscovery (Premium) no puede extraer el contenido de un archivo contenedor (por ejemplo, un archivo .zip), los contenedores se pueden descargar y el contenido se expande a la misma carpeta en la que reside el contenedor original. Los archivos expandidos se atribuirán al contenedor primario como si fueran expandidos originalmente por eDiscovery (Premium). El proceso funciona como se describió anteriormente, excepto para cargar un único archivo como archivo de reemplazo.  Al cargar archivos corregidos, no incluya el archivo de contenedor original.

## <a name="remediating-errors-by-uploading-the-extracted-text"></a>Corrección de errores mediante la carga del texto extraído

A veces no es posible corregir un archivo a formato nativo que eDiscovery (Premium) puede interpretar. Pero puede reemplazar el archivo original por un archivo de texto que contenga el texto original del archivo nativo (en un proceso denominado *superposición de texto*). Para ello, siga los pasos descritos en este artículo, pero en lugar de corregir el archivo original en el formato nativo, crearía un archivo de texto que contenga el texto extraído del archivo original y, a continuación, cargaría el archivo de texto con el nombre de archivo original anexado con un sufijo .txt. Por ejemplo, descargue un archivo durante la corrección de errores con el nombre de archivo 335850cc-6602-4af0-acfa-1d14d9128ca2.abc. Abra el archivo en la aplicación nativa, copie el texto y péguelo en un nuevo archivo denominado 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt. Al hacerlo, asegúrese de quitar el archivo original en el formato nativo de la ubicación del archivo corregido en el equipo local antes de cargar el archivo de texto corregido en eDiscovery (Premium).

## <a name="what-happens-when-files-are-remediated"></a>¿Qué ocurre cuando se corrigen los archivos?

Cuando se cargan los archivos corregidos, se conservan los metadatos originales, excepto para los campos siguientes:

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- Texto
- WordCount
- WorkingsetId

Para obtener una definición de todos los campos de metadatos de eDiscovery (Premium), vea [Campos de metadatos de documento](document-metadata-fields-in-advanced-ediscovery.md).