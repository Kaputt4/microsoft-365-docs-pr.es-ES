---
title: Importar contenido que no es de Microsoft 365 para el análisis avanzado de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Pasos para importar contenido que no está almacenado en Microsoft 365 en un BLOB de Azure para que se pueda analizar con AeD
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 03220e6baf16662ad8dfa970ef4d7077d08b0826
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662905"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="01467-103">Importar contenido que no es de Microsoft 365 para el análisis avanzado de exhibición de documentos electrónicos (Classic)</span><span class="sxs-lookup"><span data-stu-id="01467-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="01467-104">No todos los documentos que puede que necesite analizar con eDiscovery avanzado residirán en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01467-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="01467-105">Con la característica de importación de contenido que no es de Microsoft 365 en eDiscovery avanzado, puede cargar documentos que no vivan en Microsoft 365 (excepto los archivos PST) en un caso vinculado al BLOB de Azure Storage y analizarlos con la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="01467-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="01467-106">En este procedimiento se muestra cómo traer documentos que no son de Microsoft 365 en eDiscovery avanzado para su análisis.</span><span class="sxs-lookup"><span data-stu-id="01467-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="01467-p102">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="01467-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="01467-109">Puede adquirir una suscripción de complemento de almacenamiento de datos de eDiscovery avanzada para el contenido que no es de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01467-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="01467-110">Esto está disponible exclusivamente para el contenido que se va a analizar con la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="01467-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="01467-111">Siga los pasos que se indican en [comprar o editar un complemento para Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) y compre el complemento de almacenamiento avanzado de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="01467-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="01467-112">Requisitos para cargar contenido no de Office 365</span><span class="sxs-lookup"><span data-stu-id="01467-112">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="01467-113">El uso de la característica cargar no de Office 365 tal y como se describe en este procedimiento requiere que tenga:</span><span class="sxs-lookup"><span data-stu-id="01467-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="01467-114">Una suscripción a Office 365 E3 con Advanced Compliance Add-on o E5.</span><span class="sxs-lookup"><span data-stu-id="01467-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>
    
- <span data-ttu-id="01467-115">Todos los custodios cuyo contenido que no pertenezca a Office 365 se cargarán deben tener E3 con las licencias del complemento de cumplimiento avanzado o E5.</span><span class="sxs-lookup"><span data-stu-id="01467-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>
    
- <span data-ttu-id="01467-116">Un caso de eDiscovery existente.</span><span class="sxs-lookup"><span data-stu-id="01467-116">An existing eDiscovery case.</span></span>
    
- <span data-ttu-id="01467-117">Todos los archivos para carga recopilados en carpetas en las que hay una carpeta por custodio y el nombre de las carpetas se encuentran en este formato  *alias@domainname*  .</span><span class="sxs-lookup"><span data-stu-id="01467-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="01467-118">Los  *alias@domainname*  deben ser usuarios alias y dominio Office 365.</span><span class="sxs-lookup"><span data-stu-id="01467-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="01467-119">Puede recopilar todas las carpetas de  *alias@domainname*  en una carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="01467-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="01467-120">La carpeta raíz solo puede contener las carpetas  *alias@domainname*  , no debe haber archivos sueltos en la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="01467-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder.</span></span>
    
- <span data-ttu-id="01467-121">Una cuenta que sea administrador de exhibición de documentos electrónicos o administrador de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="01467-121">An account that is either an eDiscovery Manager or eDiscovery Administrator.</span></span>
    
- <span data-ttu-id="01467-122">[Herramientas de almacenamiento de Microsoft Azure](https://aka.ms/downloadazcopy) instaladas en un equipo que tiene acceso a la estructura de carpetas de contenido no Office 365.</span><span class="sxs-lookup"><span data-stu-id="01467-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="01467-123">Cargar contenido no de Office 365 en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="01467-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="01467-124">Como administrador de eDiscovery o administrador de exhibición de documentos electrónicos, Abra **eDiscovery** y abra el caso en el que se cargarán los datos que no son de Office 365.</span><span class="sxs-lookup"><span data-stu-id="01467-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="01467-125">Si necesita crear un caso, consulte [administrar casos de eDiscovery en el &amp; centro de seguridad y cumplimiento](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="01467-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
    
2. <span data-ttu-id="01467-126">Haga clic en **cambiar a exhibición avanzada de** documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="01467-126">Click **Switch to Advanced eDiscovery**.</span></span>

3. <span data-ttu-id="01467-127">Seleccione **Review sets** en el menú.</span><span class="sxs-lookup"><span data-stu-id="01467-127">Select **Review Sets** from the menu.</span></span>

4. <span data-ttu-id="01467-128">Seleccione un conjunto de revisiones existente o elija **Agregar conjunto de revisión**.</span><span class="sxs-lookup"><span data-stu-id="01467-128">Select an existing Review Set or choose **Add Review Set**.</span></span>

5. <span data-ttu-id="01467-129">Seleccione **administrar conjunto de revisión**.</span><span class="sxs-lookup"><span data-stu-id="01467-129">Select **Manage review set**.</span></span>

6. <span data-ttu-id="01467-130">En la tarjeta de datos que no son de Office 365, seleccione **Ver cargas**.</span><span class="sxs-lookup"><span data-stu-id="01467-130">In the Non-Office 365 data card, select **View Uploads**.</span></span>

7. <span data-ttu-id="01467-131">Elija **cargar archivos** para iniciar el Asistente para carga de archivos.</span><span class="sxs-lookup"><span data-stu-id="01467-131">Choose **Upload files** to start the file upload wizard.</span></span>

8. <span data-ttu-id="01467-132">La primera pestaña es **1. Paso de preparación**.</span><span class="sxs-lookup"><span data-stu-id="01467-132">The first tab is **1. Prepare step**.</span></span> <span data-ttu-id="01467-133">Seleccione **siguiente: cargar archivos**.</span><span class="sxs-lookup"><span data-stu-id="01467-133">Select **Next: Upload files**.</span></span>

9. <span data-ttu-id="01467-134">En la **2. Ficha cargar archivos** se le pedirá que descargue AzCopy.exe si todavía no lo ha hecho y, a continuación, para proporcionar la ruta de acceso a la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="01467-134">On the **2. Upload files** tab you will be prompted to download AzCopy.exe if you have not done so already, and then to provide the path to the file location.</span></span> <span data-ttu-id="01467-135">Por ejemplo, le `C:\Upload`  dará el comando para ejecutar AzCopy.exe.</span><span class="sxs-lookup"><span data-stu-id="01467-135">For example, `C:\Upload`  will give you the command to execute AzCopy.exe.</span></span> <span data-ttu-id="01467-136">Con el `C:\Upload` , verá:</span><span class="sxs-lookup"><span data-stu-id="01467-136">Using `C:\Upload`, you will see:</span></span>

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. <span data-ttu-id="01467-137">Abra una ventana de símbolo del sistema y ejecute el comando AzCopy.exe para importar los datos en Azure.</span><span class="sxs-lookup"><span data-stu-id="01467-137">Open a command prompt window and execute the AzCopy.exe command to import the data into Azure.</span></span> <span data-ttu-id="01467-138">Una vez que haya cargado todos los datos, seleccione **siguiente: procesar archivos**.</span><span class="sxs-lookup"><span data-stu-id="01467-138">Once it has loaded all of the data, select **Next: Process files**.</span></span>

11. <span data-ttu-id="01467-139">La siguiente ficha es **3. Procese los archivos** en los que verá los custodios que tienen datos asociados y también le mostrarán el progreso de los datos que se van a importar.</span><span class="sxs-lookup"><span data-stu-id="01467-139">The next tab is **3. Process files** where you will see the custodians that have data associated with them and will also show you the progress of the data being imported.</span></span>
        
    <span data-ttu-id="01467-140">Para obtener más información sobre la sintaxis de Azcopy, vea [transferir datos con Azcopy en Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="01467-140">For more information on Azcopy syntax, see [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span> 
    
    <span data-ttu-id="01467-141">Para obtener más información sobre el procesamiento avanzado de eDiscovery, consulte [ejecutar el módulo de proceso y cargar datos en la exhibición avanzada de documentos electrónicos (Classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="01467-141">For more details on Advanced eDiscovery Processing, see [Run the Process module and load data in Advanced eDiscovery (classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="01467-142">Debe haber una carpeta raíz por usuario y el nombre de la carpeta debe tener el formato <b>alias@domainname</b>  .</span><span class="sxs-lookup"><span data-stu-id="01467-142">There must be one root folder per user and the folder name must be in the <b>alias@domainname</b>  format.</span></span> 
   
    > [!IMPORTANT]
    > <span data-ttu-id="01467-143">Una vez que el contenedor se procesa correctamente en eDiscovery avanzado, ya no podrá agregar nuevo contenido al almacenamiento SAS en Azure.</span><span class="sxs-lookup"><span data-stu-id="01467-143">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="01467-144">Si recopila contenido adicional y desea agregarlo al análisis de eDiscovery avanzado, debe crear un nuevo contenedor de **datos distinto de Office 365** y repetir este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01467-144">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="01467-145">Si el contenedor  *no se procesa correctamente debido a problemas de nombres de carpeta*  y, a continuación, soluciona los problemas, deberá crear un nuevo contenedor y volver a conectar y cargar de nuevo con los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="01467-145">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
