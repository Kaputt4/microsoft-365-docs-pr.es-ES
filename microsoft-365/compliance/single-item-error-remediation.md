---
title: Corrección de errores en un único elemento
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
description: Puede corregir un error de procesamiento en un documento en un conjunto de Advanced eDiscovery sin tener que seguir el proceso de corrección masiva de errores.
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751587"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a><span data-ttu-id="09382-103">Corrección de errores de elemento único en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="09382-103">Single item error remediation in Advanced eDiscovery</span></span>

<span data-ttu-id="09382-104">La corrección de errores proporciona a Advanced eDiscovery usuarios la capacidad de corregir problemas de datos que impiden Advanced eDiscovery procesar correctamente el contenido.</span><span class="sxs-lookup"><span data-stu-id="09382-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="09382-105">Por ejemplo, los archivos protegidos con contraseña no se pueden procesar porque están bloqueados o cifrados.</span><span class="sxs-lookup"><span data-stu-id="09382-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="09382-106">Anteriormente, solo podía corregir errores en masa mediante [este flujo de trabajo](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="09382-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="09382-107">Pero a veces, no tiene sentido corregir errores en varios archivos cuando no está seguro de si alguno de esos archivos responde al caso que está investigando.</span><span class="sxs-lookup"><span data-stu-id="09382-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="09382-108">También puede que no tenga sentido corregir errores antes de que haya tenido la oportunidad de revisar los metadatos del archivo (como la ubicación del archivo o quién tuvo acceso) para ayudarle a tomar decisiones previas acerca de la capacidad de respuesta.</span><span class="sxs-lookup"><span data-stu-id="09382-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="09382-109">Una nueva característica denominada corrección de *errores* de elemento único ofrece a los administradores de exhibición de documentos electrónicos la capacidad de ver los metadatos de los archivos con un error de procesamiento y, si es necesario, corregir el error directamente en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="09382-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="09382-110">En el artículo se describe cómo identificar, omitir y corregir archivos con errores de procesamiento en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="09382-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="09382-111">Identificar documentos con errores</span><span class="sxs-lookup"><span data-stu-id="09382-111">Identify documents with errors</span></span>

<span data-ttu-id="09382-112">Los documentos con errores de procesamiento en un conjunto de revisión ahora se identifican (con un banner).</span><span class="sxs-lookup"><span data-stu-id="09382-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="09382-113">Puede corregir o omitir el error.</span><span class="sxs-lookup"><span data-stu-id="09382-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="09382-114">La siguiente captura de pantalla muestra el banner de error de procesamiento de un documento de Word en un conjunto de revisión protegido con contraseña.</span><span class="sxs-lookup"><span data-stu-id="09382-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="09382-115">Observe también que puede ver los metadatos de archivo de documentos con errores de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="09382-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![Banner que se muestra para el documento con error de procesamiento](../media/SIERimage1.png)

<span data-ttu-id="09382-117">También puede buscar documentos con errores de  procesamiento mediante la condición Estado de procesamiento al consultar los [documentos de un conjunto de revisión.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="09382-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![Usar la condición Estado de procesamiento para buscar documentos de error](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="09382-119">Omitir errores</span><span class="sxs-lookup"><span data-stu-id="09382-119">Ignore errors</span></span>

<span data-ttu-id="09382-120">Puede omitir un error de procesamiento haciendo clic en **Omitir** en el banner de error de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="09382-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="09382-121">Cuando se omite un error, el documento se quita del flujo [de trabajo de corrección](error-remediation-when-processing-data-in-advanced-ediscovery.md)masiva de errores .</span><span class="sxs-lookup"><span data-stu-id="09382-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="09382-122">Después de omitir un error, el banner del documento cambia de color e indica que se ha omitido el error de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="09382-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="09382-123">En cualquier momento, puede revertir la decisión de omitir el error haciendo clic en **Revertir**.</span><span class="sxs-lookup"><span data-stu-id="09382-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![Haga clic en Omitir para omitir el error de procesamiento](../media/SIERimage3.png)

<span data-ttu-id="09382-125">También puede buscar todos los documentos que tenían un error de procesamiento que se omitió mediante la condición *Omitir* errores de procesamiento al consultar documentos de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="09382-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![Usar la condición Errores de procesamiento omitido para buscar documentos de error omitido](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="09382-127">Corregir un documento con errores</span><span class="sxs-lookup"><span data-stu-id="09382-127">Remediate a document with errors</span></span>

<span data-ttu-id="09382-128">En ocasiones, es posible que deba corregir un error de procesamiento en documentos (quitando una contraseña, descifrando un archivo cifrado o recuperando un documento dañado) y, a continuación, agregue el documento corregido al conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="09382-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="09382-129">Esto le permite revisar y exportar el documento de error junto con los demás documentos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="09382-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="09382-130">Para corregir un solo documento, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="09382-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="09382-131">Haga **clic en** Descargar descargar  >  **original** para descargar una copia del archivo en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="09382-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![Descargar el documento con el error de procesamiento](../media/SIERimage5.png)

2. <span data-ttu-id="09382-133">Corrija el error en el archivo sin conexión.</span><span class="sxs-lookup"><span data-stu-id="09382-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="09382-134">Para los archivos cifrados, que requerirían software de descifrado, para quitar la protección con contraseña, proporcione la contraseña y guarde el archivo o use un descifrador de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="09382-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="09382-135">Después de corregir el archivo, vaya al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="09382-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="09382-136">En el conjunto de revisión, seleccione el archivo con el error de procesamiento que ha corregido y, a continuación, haga clic en **Corrección**.</span><span class="sxs-lookup"><span data-stu-id="09382-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![Haga clic en Corrección en el banner del documento con error de procesamiento](../media/SIERimage6.png)


4. <span data-ttu-id="09382-138">Haga **clic en** Examinar, vaya a la ubicación del archivo corregido en el equipo local y, a continuación, seleccione el archivo.</span><span class="sxs-lookup"><span data-stu-id="09382-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![Haga clic en Examinar y seleccione el archivo corregido en el equipo local](../media/SIERimage7.png)

    <span data-ttu-id="09382-140">Después de seleccionar el archivo corregido, se carga automáticamente en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="09382-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="09382-141">Puede realizar un seguimiento del estado de procesamiento del archivo.</span><span class="sxs-lookup"><span data-stu-id="09382-141">You can track the processing status of the file.</span></span>

    ![Se muestra el estado del proceso de corrección](../media/SIERimage8.png)

   <span data-ttu-id="09382-143">Una vez completado el procesamiento, puede ver el documento corregido.</span><span class="sxs-lookup"><span data-stu-id="09382-143">After processing is completed, you can view the remediated document.</span></span>

    ![Puede ver el archivo corregido en formato nativo en el conjunto de revisión](../media/SIERimage9.png)

<span data-ttu-id="09382-145">Para obtener más información acerca de lo que sucede cuando se corrige un documento, vea [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span><span class="sxs-lookup"><span data-stu-id="09382-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="09382-146">Buscar documentos corregidos</span><span class="sxs-lookup"><span data-stu-id="09382-146">Search for remediated documents</span></span>

<span data-ttu-id="09382-147">Puede buscar todos los documentos de un conjunto de revisión corregidos mediante la condición **Keywords** y especificando el siguiente par property:value: **IsFromErrorRemediation:true**.</span><span class="sxs-lookup"><span data-stu-id="09382-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="09382-148">Esta propiedad también está disponible en el archivo de carga de exportación al exportar documentos de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="09382-148">This property is also available in the export load file when you export documents from a review set.</span></span>
