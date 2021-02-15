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
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Aprenda a usar la corrección de errores para corregir problemas de datos en eDiscovery avanzado que podrían impedir el procesamiento adecuado del contenido.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c6ef1076e44fca0d060d766fc85a435550c40059
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750803"
---
# <a name="error-remediation-when-processing-data"></a>Corrección de errores al procesar los datos

La corrección de errores permite a los administradores de exhibición de documentos electrónicos corregir problemas de datos que impiden que eDiscovery avanzado procese correctamente el contenido. Por ejemplo, los archivos protegidos con contraseña no se pueden procesar ya que los archivos están bloqueados o cifrados. Mediante la corrección de errores, los administradores de exhibición de documentos electrónicos pueden descargar archivos con estos errores, quitar la protección con contraseña y, a continuación, cargar los archivos corregidos.

Use el siguiente flujo de trabajo para corregir archivos con errores en casos de eDiscovery avanzado.

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Crear una sesión de corrección de errores para corregir archivos con errores de procesamiento

>[!NOTE]
>Si el asistente para corrección de errores se cierra en cualquier momento durante el siguiente procedimiento,  puede volver  a la sesión de corrección de errores desde la pestaña Procesamiento seleccionando Correcciones en el menú desplegable Ver. 

1. En **la** pestaña Procesamiento en el caso de  eDiscovery avanzado, seleccione Errores en el menú  desplegable Ver y, a continuación, seleccione un conjunto de revisión o todo el caso en el menú desplegable Ámbito.  En esta sección se muestran todos los errores del caso o error de un conjunto de revisión específico.

   ![Corrección de errores](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. Seleccione los errores que desea corregir haciendo clic en el botón de radio situado junto al tipo de error o al tipo de archivo.  En el siguiente ejemplo, estamos remediando un archivo protegido con contraseña.

3. Haga **clic en Nueva corrección de errores.**

    El flujo de trabajo de corrección de errores comienza con una fase de preparación en la que los archivos con errores se copian en una ubicación de Azure Storage proporcionada por Microsoft para que pueda descargarlos en el equipo local para corregirlos.

    ![Preparar la corrección de errores](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Una vez completada la preparación, haga clic en **Siguiente: Descargar archivos** para continuar con la descarga.

    ![Descargar archivos](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Para descargar archivos, especifique la ruta **de destino para la descarga.** Se trata de una ruta de acceso a la carpeta principal del equipo local donde se descargará el archivo.  La ruta de acceso predeterminada, %USERPROFILE%\Downloads\errors, apunta a la carpeta de descargas del usuario que ha iniciado sesión. Puede cambiar esta ruta de acceso si lo desea. Si lo cambia, le recomendamos que use una ruta de acceso de archivo local para obtener el mejor rendimiento. No use una ruta de acceso de red remota. Por ejemplo, puede usar la ruta **de acceso C:\Remediation**. 

   La ruta de acceso a la carpeta principal se agrega automáticamente al comando AzCopy (como el valor del **parámetro /Dest).**

6. Copie el comando predefinido haciendo clic en **Copiar en el Portapapeles.** Abra un símbolo del sistema de Windows, pegue el comando AzCopy y, a continuación, presione **Entrar**.  

    ![Prepararse para la corrección de errores](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > Debe usar AzCopy v8.1 para usar correctamente el comando que se proporciona en la página Descargar **archivos.** También debe usar AzCopy v8.1 para cargar los archivos en el paso 10. Para instalar esta versión de AzCopy, vea [Transferir datos con AzCopy v8.1 en Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy). Si se produce un error en el comando AzCopy proporcionado, consulte Solucionar problemas [de AzCopy en eDiscovery avanzado.](troubleshooting-azcopy.md)

    Los archivos que seleccionó se descargan en la ubicación que especificó en el paso 5. En la carpeta principal (por ejemplo, **C:\Remediation),** se crea automáticamente la siguiente estructura de subcarpetas:

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - *La subcarpeta 1* se denomina con el identificador del caso o del conjunto de revisión, en función del ámbito seleccionado en el paso 1.

    - *El nombre de la* subcarpeta 2 se denomina con el identificador de archivo del archivo descargado.

    - El archivo descargado se encuentra en subcarpeta *2* y también se le denomina con el identificador de archivo.

    Este es un ejemplo de la ruta de acceso de carpeta y el nombre del archivo de error que se crea cuando los elementos se descargan en la carpeta principal **C:\Remediation:**

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    Si se descargan varios archivos, cada uno de ellos se descarga en una subcarpeta con el nombre del identificador de archivo.

    > [!IMPORTANT]
    > Al cargar archivos en los pasos 9 y 10, los archivos corregidos deben tener el mismo nombre de archivo y estar ubicados en la misma estructura de subcarpetas. La subcarpeta y los nombres de archivo se usan para asociar el archivo corregido con el archivo de error original. Si se modifica la estructura de carpetas o los nombres de archivo, recibirá el siguiente error: `Cannot apply Error Remediation to the current Workingset` . Para evitar problemas, se recomienda mantener los archivos corregidos en la misma estructura de subcarpetas y carpetas primarias.

7. Después de descargar los archivos, puede corregirlos con una herramienta adecuada. Para los archivos protegidos con contraseña, hay varias herramientas de descifrar contraseñas que puede usar. Si conoce las contraseñas de los archivos, puede abrirlos y quitar la protección con contraseña.

8. Vuelva a eDiscovery avanzado y al Asistente para corrección de errores y, a continuación, haga clic en **Siguiente: Cargar archivos.**  Esto pasa a la página siguiente, donde ahora puede cargar los archivos.

    ![Cargar archivos](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Especifique la carpeta principal donde se encuentran los archivos corregidos en el cuadro de texto Ruta de acceso **a la** ubicación de los archivos. De nuevo, la carpeta principal debe tener la misma estructura de subcarpetas que se creó al descargar los archivos.

    La ruta de acceso a la carpeta principal se agrega automáticamente al comando AzCopy (como el valor del **parámetro /Source).**

10. Copie el comando predefinido haciendo clic en **Copiar en el Portapapeles.** Abra un símbolo del sistema de Windows, pegue el comando AzCopy y, a continuación, presione **Entrar**. cargar los archivos.

    ![Resultados de la carga correcta de archivos corregidos en Azcopy](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Después de ejecutar el comando AzCopy, haga clic en **Siguiente: Procesar archivos.**

    Una vez completado el procesamiento, puede ir a revisar el conjunto y ver los archivos corregidos. 

## <a name="remediating-errors-in-container-files"></a>Corrección de errores en archivos contenedor

En situaciones en las que la exhibición avanzada de documentos electrónicos no puede extraer el contenido de un archivo contenedor (como un archivo .zip), los contenedores se pueden descargar y expandir el contenido en la misma carpeta en la que reside el contenedor original. Los archivos expandidos se atribuirán al contenedor primario como si se hubiera expandido originalmente mediante eDiscovery avanzado. El proceso funciona como se describió anteriormente, excepto para cargar un único archivo como archivo de reemplazo.  Cuando cargue archivos corregidos, no incluya el archivo contenedor original.

## <a name="remediating-errors-by-uploading-the-extracted-text"></a>Corrección de errores al cargar el texto extraído

A veces no es posible corregir un archivo en formato nativo que la exhibición avanzada de documentos electrónicos puede interpretar. Pero puedes reemplazar el archivo original con un archivo de texto que contenga el texto original del archivo nativo (en un proceso denominado *superposición de texto).* Para ello, siga los pasos descritos en este artículo, pero en lugar de corregir el archivo original en el formato nativo, crearía un archivo de texto que contiene el texto extraído del archivo original y, a continuación, cargaría el archivo de texto con el nombre de archivo original anexado con un sufijo .txt. Por ejemplo, puede descargar un archivo durante la corrección de errores con el nombre de archivo 335850cc-6602-4af0-acfa-1d14d9128ca2.abc. Abra el archivo en la aplicación nativa, copie el texto y, a continuación, péguelo en un nuevo archivo denominado 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt. Al hacerlo, asegúrese de quitar el archivo original en el formato nativo de la ubicación del archivo corregido en el equipo local antes de cargar el archivo de texto corregido en eDiscovery avanzado.

## <a name="what-happens-when-files-are-remediated"></a>Qué sucede cuando se corrigen los archivos

Cuando se cargan los archivos corregidos, los metadatos originales se conservan excepto para los siguientes campos: 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- Texto
- WordCount
- WorkingsetId

Para obtener una definición de todos los campos de metadatos en eDiscovery avanzado, vea [Campos de metadatos del documento.](document-metadata-fields-in-advanced-ediscovery.md)
