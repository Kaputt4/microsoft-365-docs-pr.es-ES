---
title: Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Los administradores pueden habilitar la compatibilidad con la etiqueta de confidencialidad para los archivos de Word, Excel y PowerPoint en SharePoint y OneDrive.
ms.openlocfilehash: c050aefb9feebbb3ff37a8504ba1b8385fb0ff49
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "38687791"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="51dc1-103">Habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive (vista previa pública)</span><span class="sxs-lookup"><span data-stu-id="51dc1-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="51dc1-104">Anteriormente, al aplicar las etiquetas de confidencialidad que incluían cifrado a los archivos de Office almacenados en SharePoint y OneDrive, el servicio no podía procesar el contenido de estos archivos.</span><span class="sxs-lookup"><span data-stu-id="51dc1-104">Previously, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="51dc1-105">La coautoría, la exhibición de documentos electrónicos, la prevención de pérdida de datos, la búsqueda, Delve y otras características de colaboración no funcionarán en estas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="51dc1-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="51dc1-106">Esta vista previa permite estas características:</span><span class="sxs-lookup"><span data-stu-id="51dc1-106">This preview enables these features:</span></span>

- <span data-ttu-id="51dc1-107">SharePoint reconoce las etiquetas de confidencialidad que se aplican a los archivos de Word, Excel y PowerPoint en SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="51dc1-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="51dc1-108">SharePoint también aplica la configuración que corresponde a cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="51dc1-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="51dc1-109">Cuando descarga un archivo desde SharePoint o desde OneDrive, la etiqueta de confidencialidad se desplaza con el archivo y la configuración sigue aplicándose.</span><span class="sxs-lookup"><span data-stu-id="51dc1-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="51dc1-110">Aplicar etiquetas de confidencialidad a los archivos de Office y abrir y editar los archivos que tienen las etiquetas de confidencialidad aplicadas (si los permisos de la etiqueta lo permiten) mediante las versiones web de Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="51dc1-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="51dc1-111">Con Word en la web, también puede usar la etiqueta automática al editar documentos.</span><span class="sxs-lookup"><span data-stu-id="51dc1-111">With Word on the web, you can also use Auto labeling when you edit documents.</span></span>

- <span data-ttu-id="51dc1-112">Office 365 eDiscovery admite la búsqueda de texto completo en los archivos a los que se han aplicado etiquetas de distinción.</span><span class="sxs-lookup"><span data-stu-id="51dc1-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="51dc1-113">Las directivas de prevención de pérdida de datos (DLP) cubren el contenido de estos archivos.</span><span class="sxs-lookup"><span data-stu-id="51dc1-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="51dc1-114">Hay tres nuevos eventos de auditoría disponibles para supervisar las etiquetas de confidencialidad:</span><span class="sxs-lookup"><span data-stu-id="51dc1-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="51dc1-115">FileSensitivityApplied</span><span class="sxs-lookup"><span data-stu-id="51dc1-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="51dc1-116">FileSensitivityLabelChanged</span><span class="sxs-lookup"><span data-stu-id="51dc1-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="51dc1-117">FileSensitivityLabelRemoved</span><span class="sxs-lookup"><span data-stu-id="51dc1-117">FileSensitivityLabelRemoved</span></span>

<span data-ttu-id="51dc1-118">Ahora también puede aplicar etiquetas de confidencialidad a Microsoft Teams, a los grupos de Office 365 y a los sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="51dc1-118">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="51dc1-119">[Obtenga más información](sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="51dc1-119">[Learn more](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="51dc1-120">Si es necesario, puede optar por no tener la vista previa en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="51dc1-120">If necessary, you can opt out of the preview at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="51dc1-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51dc1-121">Requirements</span></span>

<span data-ttu-id="51dc1-122">Estas características solo funcionan con las [etiquetas de confidencialidad](sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="51dc1-122">These features work only with [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="51dc1-123">Si usó las etiquetas de Azure Information Protection, puede convertirlas en etiquetas de confidencialidad para habilitar estas características para los archivos nuevos que cargue.</span><span class="sxs-lookup"><span data-stu-id="51dc1-123">If you used Azure Information Protection labels, you can convert them to sensitivity labels to enable these features for new files that you upload.</span></span> [<span data-ttu-id="51dc1-124">Obtenga información sobre cómo</span><span class="sxs-lookup"><span data-stu-id="51dc1-124">Learn how</span></span>](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

<span data-ttu-id="51dc1-125">Para esta vista previa, use la versión 19.002.0121.0008 o posterior de la aplicación de sincronización de OneDrive en Windows y la versión 19.002.0107.0008 o posterior en Mac.</span><span class="sxs-lookup"><span data-stu-id="51dc1-125">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="51dc1-126">Ambas versiones se publicaron el 28 de enero de 2019 y actualmente se publican en todos los anillos.</span><span class="sxs-lookup"><span data-stu-id="51dc1-126">Both of these versions were released on January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="51dc1-127">[Consulte las notas de la versión de OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span><span class="sxs-lookup"><span data-stu-id="51dc1-127">[See the OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="51dc1-128">Después de habilitar esta vista previa, se pedirá a los usuarios que ejecuten una versión anterior de la aplicación de sincronización que la actualicen.</span><span class="sxs-lookup"><span data-stu-id="51dc1-128">After you enable this preview, users who run an older version of the sync app will be prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="51dc1-129">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="51dc1-129">Limitations</span></span>

- <span data-ttu-id="51dc1-130">Cuando se habilita esta vista previa, los usuarios que apliquen una etiqueta a un archivo con las aplicaciones móviles o el escritorio de Office podrían no ser capaces de guardar otros cambios realizados en el archivo.</span><span class="sxs-lookup"><span data-stu-id="51dc1-130">When you enable this preview, users who apply a label to a file by using the Office desktop or mobile apps might be unable to save other changes they make to the file.</span></span> <span data-ttu-id="51dc1-131">En su lugar, la aplicación solicita a los usuarios que guarden o descarten los cambios locales.</span><span class="sxs-lookup"><span data-stu-id="51dc1-131">Instead, the app prompts users to Save As or Discard local changes.</span></span> <span data-ttu-id="51dc1-132">Para evitar la pérdida de trabajo, realice una de estas acciones:</span><span class="sxs-lookup"><span data-stu-id="51dc1-132">To avoid losing work, do one of these actions:</span></span>

  - <span data-ttu-id="51dc1-133">Para aplicar etiquetas, use las versiones web de las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="51dc1-133">To apply labels, use the web versions of the Office apps.</span></span>

  - <span data-ttu-id="51dc1-134">Cierre un archivo después de aplicar una etiqueta y, a continuación, vuelva a abrir el archivo para realizar otros cambios.</span><span class="sxs-lookup"><span data-stu-id="51dc1-134">Close a file after you apply a label and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="51dc1-135">SharePoint no aplica automáticamente las nuevas etiquetas a los archivos existentes que ya se han cifrado con las etiquetas de Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="51dc1-135">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="51dc1-136">En su lugar, para que las características funcionen después de habilitar esta vista previa, complete estas tareas:</span><span class="sxs-lookup"><span data-stu-id="51dc1-136">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>

  - <span data-ttu-id="51dc1-137">Convierta las etiquetas de Azure Information Protection a etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="51dc1-137">Convert the Azure Information Protection labels to sensitivity labels.</span></span>

  - <span data-ttu-id="51dc1-138">Descargue los archivos y cárguelos en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="51dc1-138">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="51dc1-139">SharePoint no puede procesar etiquetas con permisos y etiquetas personalizados con fechas de expiración.</span><span class="sxs-lookup"><span data-stu-id="51dc1-139">SharePoint can't process labels with custom permissions and labels with expiration dates.</span></span>

- <span data-ttu-id="51dc1-140">Cuando los usuarios tienen permisos de edición, las versiones web de las aplicaciones de Office permiten la copia independientemente de la configuración de la Directiva de copia en la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="51dc1-140">When users have edit permissions, the web versions of the Office apps allow copying regardless of the copy policy setting in the label.</span></span>

- <span data-ttu-id="51dc1-141">No se admite la revocación, el seguimiento ni el informe de RMS.</span><span class="sxs-lookup"><span data-stu-id="51dc1-141">RMS revocation, tracking, and reporting are unsupported.</span></span>

- <span data-ttu-id="51dc1-142">Las aplicaciones de escritorio y las aplicaciones móviles de Office no admiten la coautoría.</span><span class="sxs-lookup"><span data-stu-id="51dc1-142">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="51dc1-143">En su lugar, estas aplicaciones continúan a la vez que los archivos se abren en el modo de edición exclusivo.</span><span class="sxs-lookup"><span data-stu-id="51dc1-143">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="51dc1-144">Si una etiqueta incluye cifrado, Microsoft Cloud App Security no puede leer la información de etiqueta de los archivos en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="51dc1-144">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="51dc1-145">Preparar el shell de administración de SharePoint Online para la versión preliminar</span><span class="sxs-lookup"><span data-stu-id="51dc1-145">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="51dc1-146">Antes de habilitar la vista previa, asegúrese de que está ejecutando el shell de administración de SharePoint Online más reciente.</span><span class="sxs-lookup"><span data-stu-id="51dc1-146">Before you enable the preview, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="51dc1-147">Si ya tiene la versión más reciente, puede seguir adelante y habilitar la vista previa.</span><span class="sxs-lookup"><span data-stu-id="51dc1-147">If you already have the latest version, you can go ahead and enable the preview.</span></span>

<span data-ttu-id="51dc1-148">Para preparar el shell de administración de SharePoint Online para la vista previa:</span><span class="sxs-lookup"><span data-stu-id="51dc1-148">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="51dc1-149">Si ha instalado una versión anterior del shell de administración de SharePoint Online, vaya a **Agregar o quitar programas** y desinstale el shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="51dc1-149">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell.”</span></span>

2. <span data-ttu-id="51dc1-150">En un explorador Web, vaya a la página del centro de descarga y [Descargue el shell de administración de SharePoint Online más reciente](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="51dc1-150">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="51dc1-151">Seleccione su idioma y, a continuación, haga clic en **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="51dc1-151">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="51dc1-152">Elija entre el archivo x64 y x86. msi.</span><span class="sxs-lookup"><span data-stu-id="51dc1-152">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="51dc1-153">Descargue el archivo x64 si ejecuta la versión de 64 bits de Windows o el archivo x86 si ejecuta la versión de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="51dc1-153">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="51dc1-154">Si no lo sabe, consulte ¿ [qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="51dc1-154">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="51dc1-155">Una vez descargado el archivo, ejecute el archivo y siga los pasos del Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="51dc1-155">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="51dc1-156">Habilitación de la vista previa mediante PowerShell de Microsoft (opción opcional)</span><span class="sxs-lookup"><span data-stu-id="51dc1-156">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="51dc1-157">Para habilitar la vista previa, use el cmdlet Set-SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="51dc1-157">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="51dc1-158">Con una cuenta profesional o educativa con privilegios de administrador global o de administrador de SharePoint en Office 365, conéctese a SharePoint.</span><span class="sxs-lookup"><span data-stu-id="51dc1-158">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="51dc1-159">Para saber cómo hacerlo, vea [Introducción al Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="51dc1-159">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="51dc1-160">Ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="51dc1-160">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="51dc1-161">Programar la distribución después de crear o cambiar una etiqueta de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="51dc1-161">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="51dc1-162">Después de crear o cambiar una etiqueta de confidencialidad en el centro de cumplimiento de Microsoft 365, publíquela en fases.</span><span class="sxs-lookup"><span data-stu-id="51dc1-162">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="51dc1-163">Si publica etiquetas que no se han sincronizado completamente, cuando los usuarios aplican las etiquetas a los archivos y los cargan en SharePoint, los archivos no se pueden abrir en las versiones web de las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="51dc1-163">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="51dc1-164">La búsqueda y la exhibición de documentos electrónicos tampoco funcionan para los archivos.</span><span class="sxs-lookup"><span data-stu-id="51dc1-164">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="51dc1-165">Le recomendamos que siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51dc1-165">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="51dc1-166">Publicar la etiqueta de confidencialidad nueva o modificada solo para una o dos personas.</span><span class="sxs-lookup"><span data-stu-id="51dc1-166">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="51dc1-167">Espere al menos 24 horas después de la publicación inicial.</span><span class="sxs-lookup"><span data-stu-id="51dc1-167">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="51dc1-168">Compruebe que la etiqueta se haya sincronizado completamente.</span><span class="sxs-lookup"><span data-stu-id="51dc1-168">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="51dc1-169">Publique la etiqueta de forma general.</span><span class="sxs-lookup"><span data-stu-id="51dc1-169">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="51dc1-170">Deshabilitar la vista previa mediante PowerShell de Microsoft (no participar)</span><span class="sxs-lookup"><span data-stu-id="51dc1-170">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="51dc1-171">Si deshabilita esta vista previa, los archivos que cargó en la vista previa seguirán protegidos por la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="51dc1-171">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="51dc1-172">La configuración correspondiente se sigue aplicando.</span><span class="sxs-lookup"><span data-stu-id="51dc1-172">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="51dc1-173">Cuando se aplican etiquetas a nuevos archivos después de deshabilitar la vista previa, la búsqueda de texto completo, la exhibición de documentos electrónicos y la coautoría dejarán de funcionar.</span><span class="sxs-lookup"><span data-stu-id="51dc1-173">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="51dc1-174">Para deshabilitar la vista previa, use el cmdlet Set-SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="51dc1-174">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="51dc1-175">Con una cuenta profesional o educativa con privilegios de administrador global o de administrador de SharePoint en Office 365, conéctese a SharePoint.</span><span class="sxs-lookup"><span data-stu-id="51dc1-175">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="51dc1-176">Para saber cómo hacerlo, vea [Introducción al Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="51dc1-176">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="51dc1-177">Ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="51dc1-177">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
