---
title: Cargar datos que no son de Microsoft 365 en un conjunto de revisión
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo importar datos no Microsoft 365 a un conjunto de revisión para su análisis en un Advanced eDiscovery caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903506"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="fbe51-103">Cargar datos que no son de Microsoft 365 en un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="fbe51-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="fbe51-104">No todos los documentos que necesita analizar en Advanced eDiscovery se encuentran en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbe51-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="fbe51-105">Con la característica de importación de datos que no son de Microsoft 365 en eDiscovery avanzado, puede cargar documentos que no se encuentren en Microsoft 365 a un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="fbe51-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="fbe51-106">En este artículo se muestra cómo llevar los documentos que no Microsoft 365 a Advanced eDiscovery para su análisis.</span><span class="sxs-lookup"><span data-stu-id="fbe51-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="fbe51-107">Requisitos para cargar contenido que no Office 365 contenido</span><span class="sxs-lookup"><span data-stu-id="fbe51-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="fbe51-108">El uso de la característica de carga no Microsoft 365 descrita en este artículo requiere que tenga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fbe51-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="fbe51-109">Todos los custodios a los que desea asociar contenido que no Microsoft 365 deben tener asignada la licencia adecuada.</span><span class="sxs-lookup"><span data-stu-id="fbe51-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="fbe51-110">Para obtener más información, vea [Introducción a Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span><span class="sxs-lookup"><span data-stu-id="fbe51-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="fbe51-111">Un caso Advanced eDiscovery existente.</span><span class="sxs-lookup"><span data-stu-id="fbe51-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="fbe51-112">Los custodios deben agregarse al caso para poder cargar y asociar los datos que no Microsoft 365 a ellos.</span><span class="sxs-lookup"><span data-stu-id="fbe51-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="fbe51-113">Los datos que no son de Microsoft 365 deben ser un tipo de archivo compatible con eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="fbe51-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="fbe51-114">Para más información, consulte [Tipos de archivo admitidos en eDiscovery avanzado](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="fbe51-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="fbe51-115">Todos los archivos que se cargan en un conjunto de revisión deben encontrarse en carpetas, donde cada carpeta está asociada a un custodio específico.</span><span class="sxs-lookup"><span data-stu-id="fbe51-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="fbe51-116">Los nombres de estas carpetas deben usar el siguiente formato de nomenclatura: *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="fbe51-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="fbe51-117">El alias@domainname debe ser el dominio y el alias de Microsoft 365 del usuario.</span><span class="sxs-lookup"><span data-stu-id="fbe51-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="fbe51-118">Puede recopilar todas las alias@domainname carpetas de una carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="fbe51-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="fbe51-119">La carpeta raíz solo puede contener las alias@domainname carpetas.</span><span class="sxs-lookup"><span data-stu-id="fbe51-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="fbe51-120">No se admiten archivos sueltos en la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="fbe51-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="fbe51-121">La estructura de carpetas para los datos que no Microsoft 365 que desea cargar sería similar al siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fbe51-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="fbe51-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fbe51-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="fbe51-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fbe51-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="fbe51-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fbe51-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="fbe51-125">Donde abraham.mcmahon@contoso.com, jewell.gordon@contoso.com y staci.gonzalez@contoso.com son las direcciones SMTP de los custodios en el caso.</span><span class="sxs-lookup"><span data-stu-id="fbe51-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Estructura de carpetas Microsoft 365 carga de datos no Microsoft 365 datos](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="fbe51-127">Una cuenta que se asigna al grupo de roles administrador de exhibición de documentos electrónicos (y se agrega como administrador de exhibición de documentos electrónicos).</span><span class="sxs-lookup"><span data-stu-id="fbe51-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="fbe51-128">La herramienta AzCopy v8.1 instalada en un equipo que tiene acceso a la estructura de carpetas de contenido que no Microsoft 365 de contenido.</span><span class="sxs-lookup"><span data-stu-id="fbe51-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="fbe51-129">Para instalar AzCopy, vea [Transferir datos con AzCopy v8.1 en Windows](/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="fbe51-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="fbe51-130">Asegúrese de instalar AzCopy en la ubicación predeterminada, que es **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span><span class="sxs-lookup"><span data-stu-id="fbe51-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="fbe51-131">Debe usar AzCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="fbe51-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="fbe51-132">Es posible que otras versiones de AzCopy no funcionen al cargar datos que no Microsoft 365 en Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="fbe51-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="fbe51-133">Upload contenido no Microsoft 365 contenido en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fbe51-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="fbe51-134">Como administrador de exhibición de documentos electrónicos o administrador de exhibición de documentos electrónicos, abra Advanced eDiscovery y vaya al caso de que los datos no Microsoft 365 se cargarán en.</span><span class="sxs-lookup"><span data-stu-id="fbe51-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="fbe51-135">Haga **clic en** Conjuntos de revisión y, a continuación, seleccione el conjunto de revisión en el que se cargarán los Microsoft 365 no seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fbe51-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="fbe51-136">Si no tiene un conjunto de revisión, puede crear uno.</span><span class="sxs-lookup"><span data-stu-id="fbe51-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="fbe51-137">En el conjunto de revisión, haga clic en **Administrar conjunto de revisión** y, después, haga clic en **Ver cargas** en el mosaico **Datos que no son de Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="fbe51-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="fbe51-138">Haga clic **Cargar archivos** para iniciar el asistente para importar datos.</span><span class="sxs-lookup"><span data-stu-id="fbe51-138">Click **Upload files** to start the data import wizard.</span></span>

   ![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="fbe51-140">El primer paso del asistente prepara una ubicación segura de Azure Storage proporcionada por Microsoft en la que se pueden cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="fbe51-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="fbe51-141">Cuando se complete la preparación, se activará el botón **Siguiente: cargar archivos**.</span><span class="sxs-lookup"><span data-stu-id="fbe51-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Importación no Microsoft 365: Preparar](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="fbe51-143">Haga clic en **Siguiente: Cargar archivos**.</span><span class="sxs-lookup"><span data-stu-id="fbe51-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="fbe51-144">En la **página Upload archivos,** haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fbe51-144">On the **Upload files** page, do the following:</span></span>

   ![Importación sin Microsoft 365: Upload archivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="fbe51-146">a.</span><span class="sxs-lookup"><span data-stu-id="fbe51-146">a.</span></span> <span data-ttu-id="fbe51-147">En el **cuadro Ruta** de acceso a la ubicación de los archivos, compruebe o escriba la ubicación de la carpeta raíz donde ha almacenado los datos que no Microsoft 365 desea cargar.</span><span class="sxs-lookup"><span data-stu-id="fbe51-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="fbe51-148">Por ejemplo, para la ubicación de los archivos de ejemplo que se muestran en la sección Antes de **empezar,** escriba **%USERPROFILE\Downloads\nonO365**.</span><span class="sxs-lookup"><span data-stu-id="fbe51-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="fbe51-149">Al proporcionar la ubicación correcta, se garantiza que el comando AzCopy que se muestra en el cuadro debajo de la ruta de acceso se actualice correctamente.</span><span class="sxs-lookup"><span data-stu-id="fbe51-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="fbe51-150">b.</span><span class="sxs-lookup"><span data-stu-id="fbe51-150">b.</span></span> <span data-ttu-id="fbe51-151">Haga **clic en Copiar en** el Portapapeles para copiar el comando que se muestra en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="fbe51-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="fbe51-152">Inicie un Windows de comandos, pegue el comando que copió en el paso anterior y, a continuación, presione **ENTRAR** para iniciar el comando AzCopy.</span><span class="sxs-lookup"><span data-stu-id="fbe51-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="fbe51-153">Después de iniciar el comando, los archivos que no Microsoft 365 se cargarán en la ubicación Azure Storage que se preparó en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="fbe51-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Importación sin Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="fbe51-155">Como se ha indicado anteriormente, debe usar AzCopy v8.1 para usar correctamente el comando que se proporciona en la **página Upload archivos.**</span><span class="sxs-lookup"><span data-stu-id="fbe51-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="fbe51-156">Si se produce un error en el comando AzCopy proporcionado, consulte [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="fbe51-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="fbe51-157">Vuelva al Centro de seguridad & cumplimiento y haga clic en **Siguiente: Procesar archivos** en el asistente.</span><span class="sxs-lookup"><span data-stu-id="fbe51-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="fbe51-158">Se iniciará el procesamiento, la extracción de texto y la indexación de los archivos que no son de Microsoft 365 y que se cargaron en la ubicación de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="fbe51-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="fbe51-159">Realice un seguimiento del progreso  del procesamiento de  los archivos en la página Archivos de proceso o en la pestaña Trabajos al ver un trabajo denominado Agregar datos no Microsoft 365 a un conjunto **de revisión**.</span><span class="sxs-lookup"><span data-stu-id="fbe51-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="fbe51-160">Una vez finalizado el trabajo, los nuevos archivos estarán disponibles en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="fbe51-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Importación sin Microsoft 365: procesar archivos](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="fbe51-162">Una vez finalizado el proceso, puede cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="fbe51-162">After the processing is finished, you can close the wizard.</span></span>