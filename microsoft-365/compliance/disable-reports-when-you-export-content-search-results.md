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
description: Edite el Windows en el equipo local para deshabilitar los informes al exportar los resultados de una búsqueda de contenido desde el Centro de seguridad & cumplimiento.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817859"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="76e47-103">Deshabilitar informes al exportar los resultados de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="76e47-103">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="76e47-104">Cuando se usa la herramienta de exportación de exhibición de documentos electrónicos para exportar los resultados de una búsqueda de contenido en el Centro de cumplimiento de seguridad &, la herramienta crea y exporta automáticamente dos informes que contienen información adicional sobre el contenido exportado.</span><span class="sxs-lookup"><span data-stu-id="76e47-104">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="76e47-105">Estos informes son el archivo Results.csv y el archivo [](#frequently-asked-questions-about-disabling-export-reports) Manifest.xml (consulte la sección Preguntas más frecuentes sobre cómo deshabilitar informes de exportación en este tema para obtener descripciones detalladas de estos informes).</span><span class="sxs-lookup"><span data-stu-id="76e47-105">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="76e47-106">Dado que estos archivos pueden ser muy grandes, puede acelerar el tiempo de descarga y ahorrar espacio en disco al impedir que estos archivos se exporten.</span><span class="sxs-lookup"><span data-stu-id="76e47-106">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="76e47-107">Para ello, cambie el registro de Windows en el equipo que use para exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76e47-107">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="76e47-108">Si desea incluir los informes más adelante, puede editar la configuración del Registro.</span><span class="sxs-lookup"><span data-stu-id="76e47-108">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="76e47-109">Crear la configuración del Registro para deshabilitar los informes de exportación</span><span class="sxs-lookup"><span data-stu-id="76e47-109">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="76e47-110">Realice el siguiente procedimiento en el equipo que usará para exportar los resultados de una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="76e47-110">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="76e47-111">Cierre la herramienta de exportación de exhibición de documentos electrónicos si está abierta.</span><span class="sxs-lookup"><span data-stu-id="76e47-111">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="76e47-112">Realice uno o ambos de los pasos siguientes, según el informe de exportación que desee deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="76e47-112">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="76e47-113">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="76e47-113">**Results.csv**</span></span>
    
      <span data-ttu-id="76e47-114">Guarde el texto siguiente en un archivo Windows del Registro mediante un sufijo de nombre de archivo de .reg; por ejemplo, DisableResultsCsv.reg.</span><span class="sxs-lookup"><span data-stu-id="76e47-114">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="76e47-115">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="76e47-115">**Manifest.xml**</span></span>
    
      <span data-ttu-id="76e47-116">Guarde el texto siguiente en un archivo Windows del Registro mediante un sufijo de nombre de archivo de .reg; por ejemplo, DisableManifestXml.reg.</span><span class="sxs-lookup"><span data-stu-id="76e47-116">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="76e47-117">En Windows, haga clic o haga doble clic en el archivo .reg que creó en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="76e47-117">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="76e47-118">En la ventana Control de acceso de usuario, haga clic **en Sí** para permitir que el Editor del Registro realice el cambio.</span><span class="sxs-lookup"><span data-stu-id="76e47-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="76e47-119">Cuando se le pida que continúe, haga clic **en Sí**.</span><span class="sxs-lookup"><span data-stu-id="76e47-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="76e47-120">El Editor del Registro muestra un mensaje que indica que la configuración se agregó correctamente al Registro.</span><span class="sxs-lookup"><span data-stu-id="76e47-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="76e47-121">Editar la configuración del Registro para volver a habilitar los informes de exportación</span><span class="sxs-lookup"><span data-stu-id="76e47-121">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="76e47-122">Si deshabilitó los informes Results.csv y Manifest.xml mediante la creación de los archivos .reg en el procedimiento anterior, puede editar esos archivos para volver a habilitar un informe para que se exporte con los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76e47-122">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="76e47-123">De nuevo, realice el siguiente procedimiento en el equipo que usará para exportar los resultados de una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="76e47-123">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="76e47-124">Cierre la herramienta de exportación de exhibición de documentos electrónicos si está abierta.</span><span class="sxs-lookup"><span data-stu-id="76e47-124">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="76e47-125">Edite uno o ambos archivos de edición .reg que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="76e47-125">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="76e47-126">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="76e47-126">**Results.csv**</span></span>
    
        <span data-ttu-id="76e47-127">Abra el archivo DisableResultsCsv.reg en Bloc de notas, cambie el valor a y, a `False` continuación, guarde el `True` archivo.</span><span class="sxs-lookup"><span data-stu-id="76e47-127">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="76e47-128">Por ejemplo, después de editar el archivo, tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="76e47-128">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="76e47-129">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="76e47-129">**Manifest.xml**</span></span>
    
        <span data-ttu-id="76e47-130">Abra el archivo DisableManifestXml.reg en Bloc de notas, cambie el valor a y, a `False` continuación, guarde el `True` archivo.</span><span class="sxs-lookup"><span data-stu-id="76e47-130">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="76e47-131">Por ejemplo, después de editar el archivo, tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="76e47-131">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="76e47-132">En Windows, haga clic o haga doble clic en un archivo .reg que editó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="76e47-132">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="76e47-133">En la ventana Control de acceso de usuario, haga clic **en Sí** para permitir que el Editor del Registro realice el cambio.</span><span class="sxs-lookup"><span data-stu-id="76e47-133">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="76e47-134">Cuando se le pida que continúe, haga clic **en Sí**.</span><span class="sxs-lookup"><span data-stu-id="76e47-134">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="76e47-135">El Editor del Registro muestra un mensaje que indica que la configuración se agregó correctamente al Registro.</span><span class="sxs-lookup"><span data-stu-id="76e47-135">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="76e47-136">Preguntas más frecuentes sobre cómo deshabilitar informes de exportación</span><span class="sxs-lookup"><span data-stu-id="76e47-136">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="76e47-137">**¿Cuáles son Results.csv y Manifest.xml informes?**</span><span class="sxs-lookup"><span data-stu-id="76e47-137">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="76e47-138">Los Results.csv archivos Manifest.xml contienen información adicional sobre el contenido exportado.</span><span class="sxs-lookup"><span data-stu-id="76e47-138">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="76e47-139">**Results.csv** Un Excel que contiene información sobre cada elemento que se descarga como resultado de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76e47-139">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="76e47-140">Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos:</span><span class="sxs-lookup"><span data-stu-id="76e47-140">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="76e47-141">La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).</span><span class="sxs-lookup"><span data-stu-id="76e47-141">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="76e47-142">La fecha en que se envió o se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="76e47-142">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="76e47-143">La línea Asunto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="76e47-143">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="76e47-144">El remitente y los destinatarios del mensaje.</span><span class="sxs-lookup"><span data-stu-id="76e47-144">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="76e47-145">Si el mensaje es un mensaje duplicado si habilitó la desduplicación al exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76e47-145">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="76e47-146">Los mensajes duplicados tendrán un valor en la **columna ItemId** principal que identifica el mensaje como duplicado.</span><span class="sxs-lookup"><span data-stu-id="76e47-146">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="76e47-147">El valor de la **columna ItemId** primario es el mismo que el valor de la columna **Item DocumentId** del mensaje exportado.</span><span class="sxs-lookup"><span data-stu-id="76e47-147">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="76e47-148">Para los documentos de SharePoint y OneDrive para la Empresa, el registro de resultados contiene información sobre cada documento, incluidos:</span><span class="sxs-lookup"><span data-stu-id="76e47-148">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="76e47-149">La dirección URL del documento.</span><span class="sxs-lookup"><span data-stu-id="76e47-149">The URL for the document.</span></span>
    
  - <span data-ttu-id="76e47-150">La dirección URL de la colección de sitio donde se ubica el documento.</span><span class="sxs-lookup"><span data-stu-id="76e47-150">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="76e47-151">La fecha en la que el documento se modificó por última vez.</span><span class="sxs-lookup"><span data-stu-id="76e47-151">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="76e47-152">El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).</span><span class="sxs-lookup"><span data-stu-id="76e47-152">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="76e47-153">**Manifest.xml** Un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76e47-153">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="76e47-154">La información de este informe es la misma que el informe Results.csv, pero está en el formato especificado por el Modelo de referencia de detección electrónica (EDRM).</span><span class="sxs-lookup"><span data-stu-id="76e47-154">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="76e47-155">Para obtener más información acerca de EDRM, vaya a [https://www.edrm.net](https://www.edrm.net) .</span><span class="sxs-lookup"><span data-stu-id="76e47-155">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="76e47-156">**¿Cuándo debo deshabilitar la exportación de estos informes?**</span><span class="sxs-lookup"><span data-stu-id="76e47-156">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="76e47-157">Depende de sus necesidades específicas.</span><span class="sxs-lookup"><span data-stu-id="76e47-157">It depends on your specific needs.</span></span> <span data-ttu-id="76e47-158">Muchas organizaciones no requieren información adicional sobre los resultados de búsqueda y no necesitan estos informes.</span><span class="sxs-lookup"><span data-stu-id="76e47-158">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="76e47-159">**¿En qué equipo tengo que hacerlo?**</span><span class="sxs-lookup"><span data-stu-id="76e47-159">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="76e47-160">Debe cambiar la configuración del Registro en cualquier equipo local en el que ejecute la herramienta de exportación de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="76e47-160">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="76e47-161">**Después de cambiar esta configuración, ¿tengo que reiniciar el equipo?**</span><span class="sxs-lookup"><span data-stu-id="76e47-161">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="76e47-162">No, no es necesario reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="76e47-162">No, you don't have to restart the computer.</span></span> <span data-ttu-id="76e47-163">Pero si la herramienta de exportación de exhibición de documentos electrónicos se está ejecutando, debe cerrarla y reiniciarla después de cambiar la configuración del Registro.</span><span class="sxs-lookup"><span data-stu-id="76e47-163">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="76e47-164">**¿Se edita una clave del Registro existente o se crea una clave nueva?**</span><span class="sxs-lookup"><span data-stu-id="76e47-164">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="76e47-165">Se crea una nueva clave del Registro la primera vez que se ejecuta el archivo .reg que creó en el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="76e47-165">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="76e47-166">A continuación, la configuración se modifica cada vez que cambia y vuelve a ejecutar el archivo de edición .reg.</span><span class="sxs-lookup"><span data-stu-id="76e47-166">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
