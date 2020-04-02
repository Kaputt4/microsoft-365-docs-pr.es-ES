---
title: Cargar datos que no son de Office 365 en pruebas
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
description: ''
ms.openlocfilehash: 7d2f4fe685e17690b76124517468e0eceec8b414
ms.sourcegitcommit: 825037f166eea3ba70f8980cedc5492f90c1cc56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "43097223"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="acbae-102">Cargar datos que no son de Office 365 en pruebas</span><span class="sxs-lookup"><span data-stu-id="acbae-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="acbae-103">No todos los documentos que puede que deba analizar en una investigación de datos se ubicarán en Office 365.</span><span class="sxs-lookup"><span data-stu-id="acbae-103">Not all documents that you may need to analyze in a data investigation will be located in Office 365.</span></span> <span data-ttu-id="acbae-104">Con la característica de importación de contenido no de Office 365, puede cargar documentos que no vivan en Office 365 en pruebas para que se puedan analizar en una investigación de datos.</span><span class="sxs-lookup"><span data-stu-id="acbae-104">With the Non-Office 365 content import feature you can upload documents that don't live in Office 365 into evidence so they can be analyzed in a data investigation.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="acbae-105">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="acbae-105">Before you begin</span></span>

<span data-ttu-id="acbae-106">El uso de la característica cargar no de Office 365 tal y como se describe en este procedimiento requiere que tenga:</span><span class="sxs-lookup"><span data-stu-id="acbae-106">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="acbae-107">Una suscripción A Microsoft 365 o A Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="acbae-107">A Microsoft 365 or Office 365 E5 subscription.</span></span>

- <span data-ttu-id="acbae-108">Todas las personas de interés cuyo contenido no de Office 365 se cargará deben tener la licencia del complemento E5 o E5 adecuada.</span><span class="sxs-lookup"><span data-stu-id="acbae-108">All people of interest whose non-Office 365 content will be uploaded must have the appropriate E5 or E5 add-on license.</span></span>

- <span data-ttu-id="acbae-109">Un caso de eDiscovery existente.</span><span class="sxs-lookup"><span data-stu-id="acbae-109">An existing eDiscovery case.</span></span>

- <span data-ttu-id="acbae-110">Todos los archivos para carga recopilados en carpetas en las que hay una carpeta por custodio y el nombre de las carpetas se encuentran en este formato *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="acbae-110">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="acbae-111">Los *alias@domainname* deben ser usuarios alias y dominio Office 365.</span><span class="sxs-lookup"><span data-stu-id="acbae-111">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="acbae-112">Puede recopilar todas las carpetas de *alias@domainname* en una carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="acbae-112">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="acbae-113">La carpeta raíz solo puede contener las carpetas *alias@domainname* , no debe haber archivos sueltos en la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="acbae-113">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="acbae-114">Una cuenta que sea un administrador de eDiscovery o un administrador de exhibición de documentos electrónicos herramientas de almacenamiento de Microsoft Azure instaladas en un equipo que tenga acceso a la estructura de carpetas de contenido no Office 365.</span><span class="sxs-lookup"><span data-stu-id="acbae-114">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="acbae-115">Instale AzCopy, que puede hacer desde aquí:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="acbae-115">Install AzCopy, which you can do from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-in-to-a-data-investigation"></a><span data-ttu-id="acbae-116">Cargar contenido no de Office 365 en una investigación de datos</span><span class="sxs-lookup"><span data-stu-id="acbae-116">Upload non-Office 365 content in to a data investigation</span></span>

1. <span data-ttu-id="acbae-117">Abra **investigaciones de datos** y vaya a la investigación en la que se cargarán los datos que no son de Office 365.</span><span class="sxs-lookup"><span data-stu-id="acbae-117">Open **Data Investigations** and go to the investigation that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="acbae-118">Haga clic en la pestaña **evidencia** y, a continuación, seleccione el conjunto de evidencia en el que desea cargar los datos que no son de Office 365.</span><span class="sxs-lookup"><span data-stu-id="acbae-118">Click the **Evidence** tab, then select the evidence set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="acbae-119">Si aún no ha creado un conjunto de evidencias, puede hacerlo ahora.</span><span class="sxs-lookup"><span data-stu-id="acbae-119">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="acbae-120">Por último, haga clic en **administrar pruebas** y, a continuación, en **cargas** en la sección de datos que no son de Office 365</span><span class="sxs-lookup"><span data-stu-id="acbae-120">Finally, click **Manage evidence** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="acbae-121">Haga clic en el botón **cargar archivos** para iniciar el Asistente para importación de datos no perteneciente a Office 365.</span><span class="sxs-lookup"><span data-stu-id="acbae-121">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="acbae-123">El primer paso del asistente simplemente prepara un BLOB seguro de Azure para los archivos que se van a cargar.</span><span class="sxs-lookup"><span data-stu-id="acbae-123">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="acbae-124">Una vez completada la preparación, haga clic en el botón **cargar archivos** .</span><span class="sxs-lookup"><span data-stu-id="acbae-124">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![Preparación para la importación de datos que no son de Office 365](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="acbae-126">En el paso **cargar archivos** , especifique la **ruta de acceso a la ubicación de los archivos**, aquí es donde se ubican los datos que no son de Office 365 que tiene previsto importar.</span><span class="sxs-lookup"><span data-stu-id="acbae-126">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="acbae-127">La configuración de la ubicación correcta asegura que el comando AzCopy se haya actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="acbae-127">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="acbae-128">Si todavía no ha instalado AzCopy, puede hacerlo desde aquí:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="acbae-128">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="acbae-129">Copie el comando predefinido haciendo clic en el vínculo **copiar al portapapeles** .</span><span class="sxs-lookup"><span data-stu-id="acbae-129">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="acbae-130">Inicie un símbolo del sistema de Windows, pegue el comando y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="acbae-130">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="acbae-131">Los archivos se cargarán en el almacenamiento de blobs seguro de Azure para el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="acbae-131">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Cargar archivos para importación de datos que no son de Office 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Usar AzCopy para importar datos que no son de Office 365](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="acbae-134">Por último, vuelva al cumplimiento de & de seguridad y haga clic en el botón **siguiente: procesar archivos** .</span><span class="sxs-lookup"><span data-stu-id="acbae-134">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="acbae-135">Esto inicia el procesamiento, la extracción de texto y la indización de los archivos cargados.</span><span class="sxs-lookup"><span data-stu-id="acbae-135">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="acbae-136">Puede realizar un seguimiento del progreso del procesamiento aquí o en la pestaña **trabajos** .  Una vez completados, los nuevos archivos están disponibles en el conjunto de evidencias.</span><span class="sxs-lookup"><span data-stu-id="acbae-136">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="acbae-137">Una vez finalizado el procesamiento, puede descartar el asistente.</span><span class="sxs-lookup"><span data-stu-id="acbae-137">After processing is complete, you can dismiss the wizard.</span></span>

![Archivos de proceso de importación que no son de Office 365](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

