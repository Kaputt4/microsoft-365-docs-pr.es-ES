---
title: Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Los administradores pueden habilitar la compatibilidad con la etiqueta de confidencialidad para los archivos de Word, Excel y PowerPoint en SharePoint y OneDrive.
ms.openlocfilehash: fea28683136ae72603b3e7a6954d7d6ecf0ffbe4
ms.sourcegitcommit: 2eb4539291f5035b7bef746df89fbcc6faa17257
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2020
ms.locfileid: "41263342"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="3f6aa-103">Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive (vista previa)</span><span class="sxs-lookup"><span data-stu-id="3f6aa-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="3f6aa-104">Antes de esta vista previa, al aplicar las etiquetas de confidencialidad que incluían cifrado a los archivos de Office almacenados en SharePoint y OneDrive, el servicio no podía procesar el contenido de estos archivos.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-104">Before this preview, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="3f6aa-105">La coautoría, la exhibición de documentos electrónicos, la prevención de pérdida de datos, la búsqueda, Delve y otras características de colaboración no funcionarán en estas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="3f6aa-106">Esta vista previa habilita estas características cuando se ha aplicado el cifrado con una clave basada en la nube:</span><span class="sxs-lookup"><span data-stu-id="3f6aa-106">This preview enables these features when the encryption has been applied with a cloud-based key:</span></span>

- <span data-ttu-id="3f6aa-107">SharePoint reconoce las etiquetas de confidencialidad que se aplican a los archivos de Word, Excel y PowerPoint en SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="3f6aa-108">SharePoint también aplica la configuración que corresponde a cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="3f6aa-109">Cuando descarga un archivo desde SharePoint o desde OneDrive, la etiqueta de confidencialidad se desplaza con el archivo y la configuración sigue aplicándose.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="3f6aa-110">Aplicar etiquetas de confidencialidad a los archivos de Office y abrir y editar los archivos que tienen las etiquetas de confidencialidad aplicadas (si los permisos de la etiqueta lo permiten) mediante las versiones web de Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="3f6aa-111">Con Word en la web, también puede usar la etiqueta automática al editar documentos.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-111">With Word on the web, you can also use auto labeling when you edit documents.</span></span>

- <span data-ttu-id="3f6aa-112">Office 365 eDiscovery admite la búsqueda de texto completo en los archivos a los que se han aplicado etiquetas de distinción.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="3f6aa-113">Las directivas de prevención de pérdida de datos (DLP) cubren el contenido de estos archivos.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="3f6aa-114">Hay tres nuevos eventos de auditoría disponibles para supervisar las etiquetas de confidencialidad:</span><span class="sxs-lookup"><span data-stu-id="3f6aa-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="3f6aa-115">FileSensitivityApplied</span><span class="sxs-lookup"><span data-stu-id="3f6aa-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="3f6aa-116">FileSensitivityLabelChanged</span><span class="sxs-lookup"><span data-stu-id="3f6aa-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="3f6aa-117">FileSensitivityLabelRemoved</span><span class="sxs-lookup"><span data-stu-id="3f6aa-117">FileSensitivityLabelRemoved</span></span>

> [!NOTE]
> <span data-ttu-id="3f6aa-118">Si no se ha aplicado el cifrado con una clave basada en la nube, pero con una clave local, una topología de administración de claves a menudo denominada "retener su propia clave" (HYOK), el comportamiento de SharePoint no cambia con esta vista previa.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-118">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior doesn't change with this preview.</span></span> 

<span data-ttu-id="3f6aa-119">Ahora también puede aplicar etiquetas de confidencialidad a Microsoft Teams, a los grupos de Office 365 y a los sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-119">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="3f6aa-120">Para obtener más información sobre esta vista previa independiente, vea [usar etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint (vista previa pública)](sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="3f6aa-120">For more information about this separate preview, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="3f6aa-121">Siempre tiene la opción de optar por no participar en esta vista previa en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-121">You always have the choice to opt out of this preview at any time.</span></span>

<span data-ttu-id="3f6aa-122">Vea el siguiente vídeo (sin audio) para ver estas nuevas funciones en acción:</span><span class="sxs-lookup"><span data-stu-id="3f6aa-122">Watch the following video (no audio) to see these new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a><span data-ttu-id="3f6aa-123">Requirements</span><span class="sxs-lookup"><span data-stu-id="3f6aa-123">Requirements</span></span>

<span data-ttu-id="3f6aa-124">Estas características solo funcionan con las [etiquetas de confidencialidad](sensitivity-labels.md) .</span><span class="sxs-lookup"><span data-stu-id="3f6aa-124">These features work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="3f6aa-125">Si tiene etiquetas de Azure Information Protection, primero deberá migrarlas a las etiquetas de confidencialidad para que pueda habilitarlas para los nuevos archivos que cargue.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-125">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="3f6aa-126">Para obtener instrucciones, consulte [How to Migrate Azure Information Protection Labels to Unified Sensitivity Labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span><span class="sxs-lookup"><span data-stu-id="3f6aa-126">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="3f6aa-127">Para esta vista previa, use la versión 19.002.0121.0008 o posterior de la aplicación de sincronización de OneDrive en Windows y la versión 19.002.0107.0008 o posterior en Mac.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-127">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="3f6aa-128">Ambas versiones se han lanzado el 28 de enero de 2019 y actualmente están publicadas para todos los anillos.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-128">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="3f6aa-129">Para obtener más información, vea las notas de la [versión de OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span><span class="sxs-lookup"><span data-stu-id="3f6aa-129">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="3f6aa-130">Una vez habilitada esta vista previa, se pedirá a los usuarios que ejecuten una versión anterior de la aplicación de sincronización que la actualicen.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-130">After you enable this preview, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="3f6aa-131">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="3f6aa-131">Limitations</span></span>

- <span data-ttu-id="3f6aa-132">Cuando se habilita esta vista previa, los usuarios que cambian una etiqueta a un archivo en una carpeta de sincronización de OneDrive podrían no ser capaces de guardar otros cambios realizados en el archivo.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-132">When you enable this preview, users who change a label to a file in a OneDrive Sync folder might be unable to save other changes they make to the file.</span></span>  <span data-ttu-id="3f6aa-133">Los usuarios ven un [círculo rojo con un error de icono en forma de cruz blanca](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)y se les pide que guarden los cambios nuevos como una copia independiente.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-133">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span>  <span data-ttu-id="3f6aa-134">Además de los cambios de etiqueta que inician los usuarios, se puede producir el mismo comportamiento si un administrador cambia la configuración de una etiqueta publicada que ya se ha aplicado a los archivos descargados en el cliente de sincronización de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-134">In addition to label changes that are initiated by users, the same behavior can occur if an admin changes settings for a published label that's already applied to files downloaded to users' sync client.</span></span>
    
    <span data-ttu-id="3f6aa-135">Para evitar la pérdida de trabajo en estos escenarios, realice una de estas acciones:</span><span class="sxs-lookup"><span data-stu-id="3f6aa-135">To avoid losing work for these scenarios, do one of these actions:</span></span>
    - <span data-ttu-id="3f6aa-136">Para aplicar etiquetas, use las versiones web de las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-136">To apply labels, use the web versions of the Office apps.</span></span>
    - <span data-ttu-id="3f6aa-137">Cierre un archivo después de aplicar una etiqueta y, a continuación, vuelva a abrir el archivo para realizar otros cambios.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-137">Close a file after you apply a label, and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="3f6aa-138">SharePoint no aplica automáticamente las nuevas etiquetas a los archivos existentes que ya se han cifrado con las etiquetas de Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-138">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="3f6aa-139">En su lugar, para que las características funcionen después de habilitar esta vista previa, complete estas tareas:</span><span class="sxs-lookup"><span data-stu-id="3f6aa-139">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>
    
    1. <span data-ttu-id="3f6aa-140">Asegúrese de que ha migrado las etiquetas de Azure Information Protection a las etiquetas de confidencialidad y las ha publicado en el centro de cumplimiento de Microsoft 365, o bien en el centro de administración de etiquetas equivalente.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-140">Make sure you have migrated the Azure Information Protection labels to sensitivity labels and published them from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="3f6aa-141">Descargue los archivos y cárguelos en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-141">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="3f6aa-142">SharePoint no puede procesar archivos cifrados cuando la etiqueta que ha aplicado el cifrado tiene alguna de las siguientes configuraciones para el cifrado:</span><span class="sxs-lookup"><span data-stu-id="3f6aa-142">SharePoint can't process encrypted files when the label that applied the encryption has either of the following configurations for encryption:</span></span>
    - <span data-ttu-id="3f6aa-143">**Permitir que los usuarios asignen permisos cuando apliquen la etiqueta** y **en Word, PowerPoint y Excel, pida a los usuarios que especifiquen permisos** .</span><span class="sxs-lookup"><span data-stu-id="3f6aa-143">**Let users assign permissions when they apply the label** and **In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>
    - <span data-ttu-id="3f6aa-144">El **acceso del usuario a las expiraciones de contenido** se establece en un valor que no es **nunca**.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-144">**User access to content expires** is set to a value other than **Never**.</span></span>

- <span data-ttu-id="3f6aa-145">En el caso de un documento cifrado que concede permisos de edición a un usuario, no se puede bloquear la copia en las versiones web de las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-145">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="3f6aa-146">No se admite el sitio de seguimiento de documentos de Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-146">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="3f6aa-147">Las aplicaciones de escritorio y las aplicaciones móviles de Office no admiten la coautoría.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-147">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="3f6aa-148">En su lugar, estas aplicaciones continúan a la vez que los archivos se abren en el modo de edición exclusivo.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-148">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="3f6aa-149">Si una etiqueta incluye cifrado, Microsoft Cloud App Security no puede leer la información de etiqueta de los archivos en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-149">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="3f6aa-150">Preparar el shell de administración de SharePoint Online para la versión preliminar</span><span class="sxs-lookup"><span data-stu-id="3f6aa-150">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="3f6aa-151">Antes de habilitar la vista previa, asegúrese de que está ejecutando la versión 16.0.19418.12000 o posterior del shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-151">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="3f6aa-152">Si ya tiene la versión más reciente, puede seguir adelante y habilitar la vista previa.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-152">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="3f6aa-153">Si ha instalado una versión anterior del shell de administración de SharePoint Online desde la galería de PowerShell, puede actualizar el módulo mediante la ejecución del siguiente cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-153">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="3f6aa-154">Como alternativa, si ha instalado una versión anterior del shell de administración de SharePoint Online desde el centro de descarga de Microsoft, también puede ir a **Agregar o quitar programas** y desinstalar el shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-154">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="3f6aa-155">En un explorador web, vaya a la página del centro de descargas y [Descargue el Shell más reciente de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="3f6aa-155">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="3f6aa-156">Seleccione el idioma y, a continuación, haga clic en **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-156">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="3f6aa-157">Elija entre el archivo .msi x64 y x86.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-157">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="3f6aa-158">Descargue el archivo x64 si ejecuta la versión de 64 bits de Windows o el archivo x86 si ejecuta la versión de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-158">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="3f6aa-159">Si no lo sabe, consulte ¿ [qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="3f6aa-159">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="3f6aa-160">Una vez que haya descargado el archivo, ejecute el archivo y siga los pasos del Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-160">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="3f6aa-161">Habilitación de la vista previa mediante PowerShell de Microsoft (opción opcional)</span><span class="sxs-lookup"><span data-stu-id="3f6aa-161">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="3f6aa-162">Para habilitar la vista previa, use el cmdlet Set-SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="3f6aa-162">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="3f6aa-163">Con una cuenta profesional o educativa con privilegios de administrador global o de administrador de SharePoint en Office 365, conéctese a SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-163">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="3f6aa-164">Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="3f6aa-164">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="3f6aa-165">Ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f6aa-165">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="3f6aa-166">Programar la distribución después de crear o cambiar una etiqueta de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="3f6aa-166">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="3f6aa-167">Después de crear o cambiar una etiqueta de confidencialidad en el centro de cumplimiento de Microsoft 365, publíquela en fases.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-167">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="3f6aa-168">Si publica etiquetas que no se han sincronizado completamente, cuando los usuarios aplican las etiquetas a los archivos y los cargan en SharePoint, los archivos no se pueden abrir en las versiones web de las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-168">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="3f6aa-169">La búsqueda y la exhibición de documentos electrónicos tampoco funcionan para los archivos.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-169">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="3f6aa-170">Le recomendamos que siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3f6aa-170">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="3f6aa-171">Publicar la etiqueta de confidencialidad nueva o modificada solo para una o dos personas.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-171">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="3f6aa-172">Espere al menos 24 horas después de la publicación inicial.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-172">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="3f6aa-173">Compruebe que la etiqueta se haya sincronizado completamente.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-173">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="3f6aa-174">Publique la etiqueta de forma general.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-174">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="3f6aa-175">Deshabilitar la vista previa mediante PowerShell de Microsoft (no participar)</span><span class="sxs-lookup"><span data-stu-id="3f6aa-175">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="3f6aa-176">Si deshabilita esta vista previa, los archivos que cargó en la vista previa seguirán protegidos por la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-176">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="3f6aa-177">La configuración correspondiente se sigue aplicando.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-177">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="3f6aa-178">Cuando se aplican etiquetas a nuevos archivos después de deshabilitar la vista previa, la búsqueda de texto completo, la exhibición de documentos electrónicos y la coautoría dejarán de funcionar.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-178">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="3f6aa-179">Para deshabilitar la vista previa, use el cmdlet Set-SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="3f6aa-179">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="3f6aa-180">Con una cuenta profesional o educativa con privilegios de administrador global o de administrador de SharePoint en Office 365, conéctese a SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3f6aa-180">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="3f6aa-181">Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="3f6aa-181">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="3f6aa-182">Ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f6aa-182">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
