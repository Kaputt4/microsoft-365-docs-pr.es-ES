---
title: Cambiar el tamaño de los archivos PST al exportar los resultados de la búsqueda de exhibición de documentos electrónicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Puede cambiar el tamaño predeterminado de los archivos PST que se descargan en el equipo al exportar los resultados de la búsqueda de exhibición de documentos electrónicos.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942923"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="9f68f-103">Cambiar el tamaño de los archivos PST al exportar los resultados de la búsqueda de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="9f68f-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="9f68f-104">Cuando usa la herramienta de exportación de exhibición de documentos electrónicos para exportar los resultados de correo electrónico de una búsqueda de exhibición de documentos electrónicos desde las diferentes herramientas de exhibición de documentos electrónicos de Microsoft, el tamaño predeterminado de un archivo PST que se puede exportar es de 10 GB.</span><span class="sxs-lookup"><span data-stu-id="9f68f-104">When you use the eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="9f68f-105">Si desea cambiar este tamaño predeterminado, puede editar el Registro de Windows en el equipo que usa para exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9f68f-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="9f68f-106">Una razón para hacerlo es que un archivo PST puede caber en un medio extraíble, como un DVD, un disco compacto o una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="9f68f-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9f68f-107">La herramienta de exportación de exhibición de documentos electrónicos se usa para exportar los resultados de la búsqueda cuando se usa la herramienta de búsqueda de contenido en el Centro de seguridad y cumplimiento de &, la exhibición de documentos electrónicos de In-Place en Exchange Online y el Centro de exhibición de documentos electrónicos en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9f68f-107">The eDiscovery Export tool is used to export the search results when using the Content Search tool in the Security & Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="9f68f-108">Crear una configuración del Registro para cambiar el tamaño de los archivos PST al exportar los resultados de la búsqueda de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="9f68f-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="9f68f-109">Realice el siguiente procedimiento en el equipo que usará para exportar los resultados de una búsqueda de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="9f68f-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="9f68f-110">Cierre la herramienta de exportación de exhibición de documentos electrónicos si está abierta.</span><span class="sxs-lookup"><span data-stu-id="9f68f-110">Close the eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="9f68f-111">Guarde el siguiente texto en un archivo del Registro de la ventana con el sufijo de nombre de archivo .reg; por ejemplo, PstExportSize.reg.</span><span class="sxs-lookup"><span data-stu-id="9f68f-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="9f68f-112">En el ejemplo anterior, el valor se establece en  `PstSizeLimitInBytes` 1.073.741.824 bytes o aproximadamente 1 GB.</span><span class="sxs-lookup"><span data-stu-id="9f68f-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="9f68f-113">Estos son algunos otros valores de ejemplo para la  `PstSizeLimitInBytes` configuración.</span><span class="sxs-lookup"><span data-stu-id="9f68f-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="9f68f-114">**Tamaño en GB (aproximadamente).**</span><span class="sxs-lookup"><span data-stu-id="9f68f-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="9f68f-115">**Tamaño en bytes**</span><span class="sxs-lookup"><span data-stu-id="9f68f-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9f68f-116">0,7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="9f68f-116">0.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="9f68f-117">751619277</span><span class="sxs-lookup"><span data-stu-id="9f68f-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="9f68f-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="9f68f-118">2 GB</span></span>  <br/> |<span data-ttu-id="9f68f-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="9f68f-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="9f68f-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="9f68f-120">4 GB</span></span>  <br/> |<span data-ttu-id="9f68f-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="9f68f-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="9f68f-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="9f68f-122">8 GB</span></span>  <br/> |<span data-ttu-id="9f68f-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="9f68f-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="9f68f-124">Cambie el valor al tamaño máximo deseado de un archivo PST al exportar los resultados de la búsqueda `PstSizeLimitInBytes` y, a continuación, guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="9f68f-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="9f68f-125">En el Explorador de Windows, haga clic o haga doble clic en el archivo .reg que creó en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="9f68f-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="9f68f-126">En la ventana Control de acceso de usuario, haga clic en **Sí** para permitir que el Editor del Registro realice el cambio.</span><span class="sxs-lookup"><span data-stu-id="9f68f-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="9f68f-127">Cuando se le pida que continúe, haga clic **en Sí.**</span><span class="sxs-lookup"><span data-stu-id="9f68f-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="9f68f-128">El Editor del Registro muestra un mensaje que indica que la configuración se agregó correctamente al Registro.</span><span class="sxs-lookup"><span data-stu-id="9f68f-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="9f68f-129">Puede repetir los pasos del 3 al 6 para cambiar el valor de la configuración  `PstSizeLimitInBytes` del Registro.</span><span class="sxs-lookup"><span data-stu-id="9f68f-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="9f68f-130">Preguntas más frecuentes sobre cómo cambiar el tamaño predeterminado de los archivos PST al exportar los resultados de la búsqueda de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="9f68f-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="9f68f-131">**¿Por qué el tamaño predeterminado es de 10 GB?**</span><span class="sxs-lookup"><span data-stu-id="9f68f-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="9f68f-132">El tamaño predeterminado de 10 GB se basaba en los comentarios de los clientes; 10 GB es un buen equilibrio entre la cantidad óptima de contenido en un único PST y con una mínima probabilidad de daños en el archivo.</span><span class="sxs-lookup"><span data-stu-id="9f68f-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="9f68f-133">**¿Debo aumentar o disminuir el tamaño predeterminado de los archivos PST?**</span><span class="sxs-lookup"><span data-stu-id="9f68f-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="9f68f-134">Los clientes tienden a reducir el límite de tamaño para que los resultados de la búsqueda se ajusten a los medios extraíbles que pueden enviar físicamente a otras ubicaciones de su organización.</span><span class="sxs-lookup"><span data-stu-id="9f68f-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship to other locations in their organization.</span></span> <span data-ttu-id="9f68f-135">No se recomienda aumentar el tamaño predeterminado porque los archivos PST de más de 10 GB pueden tener problemas de daños.</span><span class="sxs-lookup"><span data-stu-id="9f68f-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="9f68f-136">**¿En qué equipo tengo que hacer esto?**</span><span class="sxs-lookup"><span data-stu-id="9f68f-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="9f68f-137">Debe cambiar la configuración del Registro en cualquier equipo local en el que ejecute la herramienta de exportación de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="9f68f-137">You need to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="9f68f-138">**Después de cambiar esta configuración, ¿tengo que reiniciar el equipo?**</span><span class="sxs-lookup"><span data-stu-id="9f68f-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="9f68f-139">No, no es necesario reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="9f68f-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="9f68f-140">Pero, si la herramienta de exportación de exhibición de documentos electrónicos se está ejecutando, tendrá que cerrarla y reiniciarla después de cambiar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="9f68f-140">But, if the eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="9f68f-141">**¿Se edita una clave del Registro existente o se crea una clave nueva?**</span><span class="sxs-lookup"><span data-stu-id="9f68f-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="9f68f-142">Se crea una nueva clave del Registro la primera vez que ejecuta el archivo .reg que creó en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9f68f-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="9f68f-143">A continuación, la configuración se edita cada vez que cambia y vuelve a ejecutar el archivo de edición .reg.</span><span class="sxs-lookup"><span data-stu-id="9f68f-143">Then the setting is edited each time you change and rerun the .reg edit file.</span></span>
