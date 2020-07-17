---
title: Deshabilitar informes al exportar los resultados de búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Edite el registro de Windows en el equipo local para deshabilitar los informes al exportar los resultados de una búsqueda de contenido desde el centro de seguridad & cumplimiento.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817859"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="95f35-103">Deshabilitar informes al exportar los resultados de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="95f35-103">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="95f35-104">Cuando se usa la herramienta de exportación de exhibición de documentos electrónicos para exportar los resultados de una búsqueda de contenido en el centro de seguridad & cumplimiento, la herramienta crea y exporta automáticamente dos informes que contienen información adicional acerca del contenido exportado.</span><span class="sxs-lookup"><span data-stu-id="95f35-104">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="95f35-105">Estos informes son el archivo de Results.csv y el archivo de Manifest.xml (consulte la sección [preguntas más frecuentes acerca de cómo deshabilitar los informes de exportación](#frequently-asked-questions-about-disabling-export-reports) de este tema para obtener descripciones detalladas de estos informes).</span><span class="sxs-lookup"><span data-stu-id="95f35-105">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="95f35-106">Como estos archivos pueden ser muy grandes, puede acelerar el tiempo de descarga y ahorrar espacio en disco al impedir que se exporten estos archivos.</span><span class="sxs-lookup"><span data-stu-id="95f35-106">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="95f35-107">Para ello, puede cambiar el registro de Windows en el equipo que usa para exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="95f35-107">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="95f35-108">Si desea incluir los informes más adelante, puede editar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="95f35-108">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="95f35-109">Crear una configuración del registro para deshabilitar los informes de exportación</span><span class="sxs-lookup"><span data-stu-id="95f35-109">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="95f35-110">Lleve a cabo el siguiente procedimiento en el equipo que va a usar para exportar los resultados de una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="95f35-110">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="95f35-111">Cierre la herramienta de exportación de exhibición de documentos electrónicos si está abierta.</span><span class="sxs-lookup"><span data-stu-id="95f35-111">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="95f35-112">Realice uno o ambos de los pasos siguientes, según el informe de exportación que quiera deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="95f35-112">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="95f35-113">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="95f35-113">**Results.csv**</span></span>
    
      <span data-ttu-id="95f35-114">Guarde el siguiente texto en un archivo de registro de Windows mediante un sufijo de nombre de archivo. reg; por ejemplo, DisableResultsCsv. reg.</span><span class="sxs-lookup"><span data-stu-id="95f35-114">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="95f35-115">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="95f35-115">**Manifest.xml**</span></span>
    
      <span data-ttu-id="95f35-116">Guarde el siguiente texto en un archivo de registro de Windows mediante un sufijo de nombre de archivo. reg; por ejemplo, DisableManifestXml. reg.</span><span class="sxs-lookup"><span data-stu-id="95f35-116">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="95f35-117">En el explorador de Windows, haga clic o doble clic en el archivo. reg que creó en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="95f35-117">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="95f35-118">En la ventana control de acceso de usuario, haga clic en **sí** para permitir que el editor del registro realice los cambios.</span><span class="sxs-lookup"><span data-stu-id="95f35-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="95f35-119">Cuando se le pregunte si desea continuar, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="95f35-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="95f35-120">El editor del registro muestra un mensaje que indica que la configuración se agregó correctamente al registro.</span><span class="sxs-lookup"><span data-stu-id="95f35-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="95f35-121">Editar la configuración del registro para volver a habilitar los informes de exportación</span><span class="sxs-lookup"><span data-stu-id="95f35-121">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="95f35-122">Si ha deshabilitado la Results.csv y Manifest.xml informes creando los archivos. reg en el procedimiento anterior, puede editar esos archivos para volver a habilitar un informe de manera que se exporte con los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="95f35-122">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="95f35-123">De nuevo, realice el siguiente procedimiento en el equipo que va a usar para exportar los resultados de una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="95f35-123">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="95f35-124">Cierre la herramienta de exportación de exhibición de documentos electrónicos si está abierta.</span><span class="sxs-lookup"><span data-stu-id="95f35-124">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="95f35-125">Edite uno o ambos de los archivos. reg Edit que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="95f35-125">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="95f35-126">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="95f35-126">**Results.csv**</span></span>
    
        <span data-ttu-id="95f35-127">Abra el archivo DisableResultsCsv. reg en el Bloc de notas, cambie el valor `False` a `True` y, a continuación, guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="95f35-127">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="95f35-128">Por ejemplo, después de editar el archivo, tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="95f35-128">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="95f35-129">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="95f35-129">**Manifest.xml**</span></span>
    
        <span data-ttu-id="95f35-130">Abra el archivo DisableManifestXml. reg en el Bloc de notas, cambie el valor `False` a `True` y, a continuación, guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="95f35-130">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="95f35-131">Por ejemplo, después de editar el archivo, tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="95f35-131">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="95f35-132">En el explorador de Windows, haga clic o doble clic en un archivo. reg que modificó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="95f35-132">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="95f35-133">En la ventana control de acceso de usuario, haga clic en **sí** para permitir que el editor del registro realice los cambios.</span><span class="sxs-lookup"><span data-stu-id="95f35-133">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="95f35-134">Cuando se le pregunte si desea continuar, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="95f35-134">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="95f35-135">El editor del registro muestra un mensaje que indica que la configuración se agregó correctamente al registro.</span><span class="sxs-lookup"><span data-stu-id="95f35-135">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="95f35-136">Preguntas más frecuentes sobre la deshabilitación de informes de exportación</span><span class="sxs-lookup"><span data-stu-id="95f35-136">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="95f35-137">**¿Cuáles son los informes de Results.csv y Manifest.xml?**</span><span class="sxs-lookup"><span data-stu-id="95f35-137">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="95f35-138">Los archivos Results.csv y Manifest.xml contienen información adicional acerca del contenido que se exportó.</span><span class="sxs-lookup"><span data-stu-id="95f35-138">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="95f35-139">**Results.csv** Un documento de Excel que contiene información acerca de cada elemento que se descarga como resultado de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="95f35-139">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="95f35-140">Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos:</span><span class="sxs-lookup"><span data-stu-id="95f35-140">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="95f35-141">La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).</span><span class="sxs-lookup"><span data-stu-id="95f35-141">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="95f35-142">La fecha en que se envió o se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="95f35-142">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="95f35-143">La línea Asunto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="95f35-143">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="95f35-144">El remitente y los destinatarios del mensaje.</span><span class="sxs-lookup"><span data-stu-id="95f35-144">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="95f35-145">Si el mensaje es un mensaje duplicado si ha habilitado la desduplicación al exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="95f35-145">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="95f35-146">Los mensajes duplicados tendrán un valor en la columna **principal de Itemid** que identifica el mensaje como duplicado.</span><span class="sxs-lookup"><span data-stu-id="95f35-146">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="95f35-147">El valor de la columna **principal de Itemid** es el mismo que el valor de la columna DocumentId del **elemento** del mensaje que se exportó.</span><span class="sxs-lookup"><span data-stu-id="95f35-147">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="95f35-148">Para los documentos de los sitios de SharePoint y OneDrive para la empresa, el registro de resultados contiene información sobre cada documento, incluidos:</span><span class="sxs-lookup"><span data-stu-id="95f35-148">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="95f35-149">La dirección URL del documento.</span><span class="sxs-lookup"><span data-stu-id="95f35-149">The URL for the document.</span></span>
    
  - <span data-ttu-id="95f35-150">La dirección URL de la colección de sitio donde se ubica el documento.</span><span class="sxs-lookup"><span data-stu-id="95f35-150">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="95f35-151">La fecha en la que el documento se modificó por última vez.</span><span class="sxs-lookup"><span data-stu-id="95f35-151">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="95f35-152">El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).</span><span class="sxs-lookup"><span data-stu-id="95f35-152">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="95f35-153">**Manifest.xml** Un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="95f35-153">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="95f35-154">La información de este informe es la misma que la del informe de Results.csv, pero está en el formato especificado por el modelo de referencia de detección electrónica (EDRM).</span><span class="sxs-lookup"><span data-stu-id="95f35-154">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="95f35-155">Para obtener más información acerca de EDRM, vaya a [https://www.edrm.net](https://www.edrm.net) .</span><span class="sxs-lookup"><span data-stu-id="95f35-155">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="95f35-156">**¿Cuándo debo deshabilitar la exportación de estos informes?**</span><span class="sxs-lookup"><span data-stu-id="95f35-156">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="95f35-157">Depende de sus necesidades específicas.</span><span class="sxs-lookup"><span data-stu-id="95f35-157">It depends on your specific needs.</span></span> <span data-ttu-id="95f35-158">Muchas organizaciones no necesitan más información sobre los resultados de la búsqueda y no necesitan estos informes.</span><span class="sxs-lookup"><span data-stu-id="95f35-158">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="95f35-159">**¿En qué equipo tengo que hacerlo?**</span><span class="sxs-lookup"><span data-stu-id="95f35-159">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="95f35-160">Tiene que cambiar la configuración del registro en cualquier equipo local en el que ejecute la herramienta de exportación de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="95f35-160">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="95f35-161">**Después de cambiar esta configuración, ¿tengo que reiniciar el equipo?**</span><span class="sxs-lookup"><span data-stu-id="95f35-161">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="95f35-162">No, no es necesario reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="95f35-162">No, you don't have to restart the computer.</span></span> <span data-ttu-id="95f35-163">Pero si se está ejecutando la herramienta de exportación de exhibición de documentos electrónicos, debe cerrarla y reiniciarla después de cambiar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="95f35-163">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="95f35-164">**¿Se modifica una clave del registro existente o se crea una nueva clave?**</span><span class="sxs-lookup"><span data-stu-id="95f35-164">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="95f35-165">La primera vez que ejecute el archivo. reg que creó en el procedimiento de este tema, se creará una nueva clave del registro.</span><span class="sxs-lookup"><span data-stu-id="95f35-165">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="95f35-166">A continuación, la configuración se edita cada vez que cambia y vuelve a ejecutar el archivo de edición. reg.</span><span class="sxs-lookup"><span data-stu-id="95f35-166">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
