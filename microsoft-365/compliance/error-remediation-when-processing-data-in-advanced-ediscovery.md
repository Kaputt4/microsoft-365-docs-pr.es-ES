---
title: Corrección de errores al procesar los datos
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
ms.openlocfilehash: 02fa8870d6edb4e1a6616604ee0e98638b217237
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37092567"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="60528-102">Corrección de errores al procesar los datos</span><span class="sxs-lookup"><span data-stu-id="60528-102">Error remediation when processing data</span></span>

<span data-ttu-id="60528-103">La corrección de errores permite que los administradores de eDiscovery puedan rectificar problemas de datos que impiden que eDiscovery avanzado procese correctamente el contenido.</span><span class="sxs-lookup"><span data-stu-id="60528-103">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="60528-104">Por ejemplo, no se pueden procesar archivos protegidos con contraseña, ya que los archivos están bloqueados o cifrados.</span><span class="sxs-lookup"><span data-stu-id="60528-104">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="60528-105">Mediante la corrección de errores, los administradores de eDiscovery pueden descargar archivos con estos errores, quitar la protección con contraseña y, a continuación, cargar los archivos corregidos.</span><span class="sxs-lookup"><span data-stu-id="60528-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="60528-106">Use el siguiente flujo de trabajo para corregir los archivos con errores en casos de exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="60528-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="60528-107">Crear una sesión de corrección de errores para corregir los archivos con errores de procesamiento</span><span class="sxs-lookup"><span data-stu-id="60528-107">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="60528-108">Si el Asistente para la corrección de errores se cierra en cualquier momento durante el siguiente procedimiento, puede volver a la sesión de corrección de errores desde la pestaña **procesando** seleccionando **soluciones** en el menú desplegable **vista** .</span><span class="sxs-lookup"><span data-stu-id="60528-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="60528-109">En la pestaña **procesamiento** del caso de eDiscovery avanzado, seleccione **errores** en el menú desplegable **Ver** y, a continuación, seleccione un conjunto de revisiones o todo el caso en el menú desplegable **ámbito** .</span><span class="sxs-lookup"><span data-stu-id="60528-109">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="60528-110">En esta sección se muestran todos los errores del caso o del error de un conjunto de revisión específico.</span><span class="sxs-lookup"><span data-stu-id="60528-110">This section displays all errors from the case or error from a specific review set.</span></span>

   ![Corrección de errores](media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="60528-112">Seleccione los errores que desea corregir haciendo clic en el botón de opción situado junto a tipo de error o tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="60528-112">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="60528-113">En el siguiente ejemplo, estamos corrigiendo un archivo protegido con contraseña.</span><span class="sxs-lookup"><span data-stu-id="60528-113">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="60528-114">Haga clic en **nueva corrección de errores**.</span><span class="sxs-lookup"><span data-stu-id="60528-114">Click **New error remediation**.</span></span>

    <span data-ttu-id="60528-115">El flujo de trabajo de corrección de errores comienza con una etapa de preparación donde los archivos con errores se copian en una ubicación de almacenamiento de Azure proporcionada por Microsoft para que pueda descargarlos en el equipo local para corregirlos.</span><span class="sxs-lookup"><span data-stu-id="60528-115">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![Preparación de la corrección de errores](media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="60528-117">Una vez completada la preparación, haga clic en **siguiente: descargar archivos** para continuar con la descarga.</span><span class="sxs-lookup"><span data-stu-id="60528-117">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![Descargar archivos](media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="60528-119">Para descargar archivos, especifique la **ruta de destino de la descarga**.</span><span class="sxs-lookup"><span data-stu-id="60528-119">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="60528-120">Se trata de una ruta de acceso a la carpeta principal en el equipo local donde se descargará el archivo.</span><span class="sxs-lookup"><span data-stu-id="60528-120">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="60528-121">La ruta de acceso predeterminada,%USERPROFILE%\Downloads\errors, apunta a la carpeta descargas del usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="60528-121">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="60528-122">Si lo desea, puede cambiar esta ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="60528-122">You can change this path if desired.</span></span> <span data-ttu-id="60528-123">Si lo cambia, le recomendamos que use una ruta de acceso de archivo local para obtener el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="60528-123">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="60528-124">No use una ruta de acceso de red remota.</span><span class="sxs-lookup"><span data-stu-id="60528-124">Don't use a remote network path.</span></span> <span data-ttu-id="60528-125">Por ejemplo, puede usar la ruta de acceso **C:\Remediation**.</span><span class="sxs-lookup"><span data-stu-id="60528-125">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="60528-126">La ruta de acceso a la carpeta principal se agrega automáticamente a comando AzCopy (como el valor del parámetro **/dest** ).</span><span class="sxs-lookup"><span data-stu-id="60528-126">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="60528-127">Copie el comando predefinido; para ello, haga clic en **copiar al portapapeles**.</span><span class="sxs-lookup"><span data-stu-id="60528-127">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="60528-128">Abra un símbolo del sistema de Windows, pegue el comando AzCopy y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="60528-128">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![Preparar la corrección de errores](media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="60528-130">Debe usar AzCopy v 8.1 para usar correctamente el comando que se proporciona en la página **descargar archivos** .</span><span class="sxs-lookup"><span data-stu-id="60528-130">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="60528-131">También debe usar AzCopy v 8.1 para cargar los archivos en el paso 10.</span><span class="sxs-lookup"><span data-stu-id="60528-131">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="60528-132">Para instalar esta versión de AzCopy, consulte [transferir datos con AzCopy v 8.1 en Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="60528-132">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="60528-133">Si el comando AzCopy proporcionado no se produce, consulte [solucionar problemas de azcopy en EDiscovery avanzado](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="60528-133">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="60528-134">Los archivos que ha seleccionado se descargan en la ubicación que especificó en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="60528-134">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="60528-135">En la carpeta principal (por ejemplo, **C:\Remediation**), se crea automáticamente la siguiente estructura de subcarpetas:</span><span class="sxs-lookup"><span data-stu-id="60528-135">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="60528-136">La *subcarpeta 1* tiene el mismo nombre que el identificador del caso o el conjunto de revisión, según el ámbito que seleccionó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="60528-136">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="60528-137">La *subcarpeta 2* tiene el mismo nombre que el archivo del archivo descargado.</span><span class="sxs-lookup"><span data-stu-id="60528-137">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="60528-138">El archivo descargado se encuentra en la *subcarpeta 2* y también se denomina con el identificador de archivo.</span><span class="sxs-lookup"><span data-stu-id="60528-138">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="60528-139">A continuación, se muestra un ejemplo de la ruta de acceso de la carpeta y el nombre del archivo de error que se crea cuando los elementos se descargan en la carpeta principal **C:\Remediation** :</span><span class="sxs-lookup"><span data-stu-id="60528-139">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="60528-140">Si se descargan varios archivos, cada uno de ellos se descarga en una subcarpeta que se nombra con el identificador de archivo.</span><span class="sxs-lookup"><span data-stu-id="60528-140">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="60528-141">Al cargar archivos en el paso 9 y el paso 10, los archivos corregidos deben tener el mismo nombre de archivo y estar ubicados en la misma estructura de subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="60528-141">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="60528-142">La subcarpeta y los nombres de archivo se usan para asociar el archivo corregido con el archivo de errores original.</span><span class="sxs-lookup"><span data-stu-id="60528-142">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="60528-143">Si se modifica la estructura de la carpeta o los nombres de archivo, recibirá el `Cannot apply Error Remediation to the current Workingset`siguiente error:.</span><span class="sxs-lookup"><span data-stu-id="60528-143">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="60528-144">Para evitar problemas, le recomendamos que conserve los archivos corregidos en la misma estructura de carpetas primarias y subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="60528-144">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="60528-145">Después de descargar los archivos, puede corregirlos con una herramienta adecuada.</span><span class="sxs-lookup"><span data-stu-id="60528-145">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="60528-146">Para los archivos protegidos con contraseña, hay varias herramientas de averiguación de contraseñas que puede usar.</span><span class="sxs-lookup"><span data-stu-id="60528-146">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="60528-147">Si conoce las contraseñas de los archivos, puede abrirlas y quitar la protección con contraseña.</span><span class="sxs-lookup"><span data-stu-id="60528-147">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="60528-148">Vuelva a eDiscovery avanzado y el Asistente para la corrección de errores y, a continuación, haga clic en **siguiente: cargar archivos**.</span><span class="sxs-lookup"><span data-stu-id="60528-148">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="60528-149">Se desplaza a la página siguiente, donde ahora puede cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="60528-149">This moves to the next page where you can now upload the files.</span></span>

    ![Cargar archivos](media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="60528-151">Especifique la carpeta principal donde se encuentran los archivos corregidos en el cuadro **de texto Ruta de acceso a la ubicación de los archivos** .</span><span class="sxs-lookup"><span data-stu-id="60528-151">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="60528-152">Una vez más, la carpeta principal debe tener la misma estructura de subcarpetas que se creó cuando se descargaron los archivos.</span><span class="sxs-lookup"><span data-stu-id="60528-152">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="60528-153">La ruta de acceso a la carpeta principal se agrega automáticamente a comando AzCopy (como el valor del parámetro **/source** ).</span><span class="sxs-lookup"><span data-stu-id="60528-153">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="60528-154">Copie el comando predefinido; para ello, haga clic en **copiar al portapapeles**.</span><span class="sxs-lookup"><span data-stu-id="60528-154">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="60528-155">Abra un símbolo del sistema de Windows, pegue el comando AzCopy y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="60528-155">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="60528-156">cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="60528-156">upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="60528-158">Después de ejecutar el comando AzCopy, haga clic en **siguiente: procesar archivos**.</span><span class="sxs-lookup"><span data-stu-id="60528-158">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="60528-159">Una vez finalizado el procesamiento, puede ir a revisar establecer y ver los archivos corregidos.</span><span class="sxs-lookup"><span data-stu-id="60528-159">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="60528-160">Qué sucede cuando se corrigen los archivos</span><span class="sxs-lookup"><span data-stu-id="60528-160">What happens when files are remediated</span></span>

<span data-ttu-id="60528-161">Cuando se cargan los archivos corregidos, se conservan los metadatos originales excepto los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="60528-161">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="60528-162">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="60528-162">ExtractedTextSize</span></span>
- <span data-ttu-id="60528-163">HasText</span><span class="sxs-lookup"><span data-stu-id="60528-163">HasText</span></span>
- <span data-ttu-id="60528-164">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="60528-164">IsErrorRemediate</span></span>
- <span data-ttu-id="60528-165">LoadId</span><span class="sxs-lookup"><span data-stu-id="60528-165">LoadId</span></span>
- <span data-ttu-id="60528-166">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="60528-166">ProcessingErrorMessage</span></span>
- <span data-ttu-id="60528-167">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="60528-167">ProcessingStatus</span></span>
- <span data-ttu-id="60528-168">Texto</span><span class="sxs-lookup"><span data-stu-id="60528-168">Text</span></span>
- <span data-ttu-id="60528-169">WordCount</span><span class="sxs-lookup"><span data-stu-id="60528-169">WordCount</span></span>
- <span data-ttu-id="60528-170">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="60528-170">WorkingsetId</span></span>

<span data-ttu-id="60528-171">Para obtener una definición de todos los campos de metadatos en eDiscovery avanzado, consulte [campos de metadatos del documento](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="60528-171">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
