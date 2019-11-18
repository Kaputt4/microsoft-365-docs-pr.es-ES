---
title: Corrección de errores de un único elemento
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
description: Puede corregir un error de procesamiento en un documento en un conjunto de revisión en eDiscovery avanzado sin tener que seguir el proceso de corrección de errores en masa.
ms.openlocfilehash: 922c0e4b0ab30bae6507fac7e97080a5951ea750
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "38687763"
---
# <a name="single-item-error-remediation"></a><span data-ttu-id="36d61-103">Corrección de errores de un único elemento</span><span class="sxs-lookup"><span data-stu-id="36d61-103">Single item error remediation</span></span>

<span data-ttu-id="36d61-104">La corrección de errores proporciona a los usuarios avanzados de eDiscovery la capacidad de rectificar problemas de datos que impiden que eDiscovery avanzado procese correctamente el contenido.</span><span class="sxs-lookup"><span data-stu-id="36d61-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="36d61-105">Por ejemplo, los archivos protegidos con contraseña no se pueden procesar porque estos archivos están bloqueados o cifrados.</span><span class="sxs-lookup"><span data-stu-id="36d61-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="36d61-106">Anteriormente, solo podían corregirse los errores en masa con [este flujo de trabajo](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="36d61-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="36d61-107">Pero, a veces, no tiene sentido corregir los errores en varios archivos cuando no está seguro de si alguno de estos archivos responde al caso que está investigando.</span><span class="sxs-lookup"><span data-stu-id="36d61-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="36d61-108">También es posible que no tenga sentido corregir los errores antes de que haya tenido la oportunidad de revisar los metadatos del archivo (como la ubicación del archivo o quién tenía acceso) para ayudarle a tomar decisiones delanteras sobre la capacidad de respuesta.</span><span class="sxs-lookup"><span data-stu-id="36d61-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="36d61-109">Una nueva característica denominada *corrección de errores de elemento único* proporciona a los administradores de eDiscovery la capacidad de ver los metadatos de los archivos con un error de procesamiento y, si es necesario, corregir el error directamente en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="36d61-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="36d61-110">En el artículo se describe cómo identificar, omitir y solucionar los archivos con errores de procesamiento en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="36d61-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="36d61-111">Identificación de documentos con errores</span><span class="sxs-lookup"><span data-stu-id="36d61-111">Identify documents with errors</span></span>

<span data-ttu-id="36d61-112">Los documentos con errores de procesamiento en un conjunto de revisiones ahora están identificados (con un banner).</span><span class="sxs-lookup"><span data-stu-id="36d61-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="36d61-113">Puede corregir o ignorar el error.</span><span class="sxs-lookup"><span data-stu-id="36d61-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="36d61-114">En la siguiente captura de pantalla se muestra el mensaje de error de procesamiento de un documento de Word en un conjunto de revisión protegido con contraseña.</span><span class="sxs-lookup"><span data-stu-id="36d61-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="36d61-115">Observe también que puede ver los metadatos de archivo de los documentos con errores de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="36d61-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![Banner mostrado para un documento con un error de procesamiento](media/SIERimage1.png)

<span data-ttu-id="36d61-117">También puede buscar documentos que tienen errores de procesamiento mediante la condición de **Estado de procesamiento** cuando [consulta los documentos en un conjunto de revisión](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="36d61-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![Usar la condición estado de procesamiento para buscar documentos de error](media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="36d61-119">Omitir errores</span><span class="sxs-lookup"><span data-stu-id="36d61-119">Ignore errors</span></span>

<span data-ttu-id="36d61-120">Puede omitir un error de procesamiento haciendo clic en **omitir** en el banner de error de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="36d61-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="36d61-121">Cuando se omite un error, el documento se quita del [flujo de trabajo de corrección de errores en masa](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="36d61-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="36d61-122">Después de omitir un error, el titular del documento cambia de color e indica que se ha omitido el error de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="36d61-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="36d61-123">En cualquier momento, puede revertir la decisión para omitir el error; para ello, haga clic en **revertir**.</span><span class="sxs-lookup"><span data-stu-id="36d61-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![Haga clic en Omitir para omitir el error de procesamiento](media/SIERimage3.png)

<span data-ttu-id="36d61-125">También puede buscar todos los documentos que tuvieron un error de procesamiento que se omitió mediante la condición *errores de procesamiento omitidos* al consultar los documentos en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="36d61-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![Use la condición errores de procesamiento omitidos para buscar documentos de error omitidos](media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="36d61-127">Corregir un documento con errores</span><span class="sxs-lookup"><span data-stu-id="36d61-127">Remediate a document with errors</span></span>

<span data-ttu-id="36d61-128">A veces, es posible que se le solicite corregir un error de procesamiento en los documentos (quitando una contraseña, descifrando un archivo cifrado o recuperando un documento dañado) y, a continuación, agregue el documento corregido al conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="36d61-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="36d61-129">Esto le permite revisar y exportar el documento de error junto con el resto de los documentos en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="36d61-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="36d61-130">Para corregir un único documento, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="36d61-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="36d61-131">Haga clic en **Descargar** > **Descargar original** para descargar una copia del archivo en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="36d61-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![Descargar el documento con el error de procesamiento](media/SIERimage5.png)

2. <span data-ttu-id="36d61-133">Corrija el error en el archivo sin conexión.</span><span class="sxs-lookup"><span data-stu-id="36d61-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="36d61-134">En el caso de los archivos cifrados, sería necesario el software de descifrado para quitar la protección con contraseña, proporcionar la contraseña y guardar el archivo o usar un Cracker con contraseña.</span><span class="sxs-lookup"><span data-stu-id="36d61-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="36d61-135">Una vez corregido el archivo, vaya al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="36d61-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="36d61-136">En el conjunto de revisiones, seleccione el archivo con el error de procesamiento que ha corregido y, a continuación, haga clic en **corrección**.</span><span class="sxs-lookup"><span data-stu-id="36d61-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![Hacer clic en corrección en el encabezado del documento con error de procesamiento](media/SIERimage6.png)


4. <span data-ttu-id="36d61-138">Haga clic en **examinar**, vaya a la ubicación del archivo corregido en el equipo local y, a continuación, seleccione el archivo.</span><span class="sxs-lookup"><span data-stu-id="36d61-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![Haga clic en examinar y seleccione el archivo corregido en el equipo local.](media/SIERimage7.png)

    <span data-ttu-id="36d61-140">Después de seleccionar el archivo corregido, éste se carga automáticamente en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="36d61-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="36d61-141">Puede realizar un seguimiento del estado de procesamiento del archivo.</span><span class="sxs-lookup"><span data-stu-id="36d61-141">You can track the processing status of the file.</span></span>

    ![Se muestra el estado del proceso de corrección](media/SIERimage8.png)

   <span data-ttu-id="36d61-143">Una vez finalizado el procesamiento, puede ver el documento corregido.</span><span class="sxs-lookup"><span data-stu-id="36d61-143">After processing is completed, you can view the remediated document.</span></span>

    ![Puede ver el archivo corregido en el formato nativo en el conjunto de revisiones](media/SIERimage9.png)

<span data-ttu-id="36d61-145">Para obtener más información sobre lo que sucede cuando se corrige un documento, vea [lo que ocurre cuando se corrigen los archivos](error-remediation.md#what-happens-when-files-are-remediated).</span><span class="sxs-lookup"><span data-stu-id="36d61-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="36d61-146">Buscar documentos corregidos</span><span class="sxs-lookup"><span data-stu-id="36d61-146">Search for remediated documents</span></span>

<span data-ttu-id="36d61-147">Puede buscar todos los documentos en un conjunto de revisión corregido con la condición **palabras clave** y especificando el siguiente par de propiedad: valor: **IsFromErrorRemediation: true**.</span><span class="sxs-lookup"><span data-stu-id="36d61-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="36d61-148">Esta propiedad también está disponible en el archivo de carga de exportación al exportar documentos de un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="36d61-148">This property is also available in the export load file when you export documents from a review set.</span></span>
