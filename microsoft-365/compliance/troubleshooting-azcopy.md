---
title: Solucionar problemas de AzCopy en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Solucione los errores de Azure AzCopy al cargar datos que no son de Office 365 para la corrección de errores en la exhibición avanzada de documentos electrónicos.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 0185c179039b7aec72bc400709225ef42489f620
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819150"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="97b3c-103">Solucionar problemas de AzCopy en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="97b3c-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="97b3c-104">Al cargar datos o documentos que no son de Microsoft 365 para la corrección de errores en eDiscovery avanzado, la interfaz de usuario proporciona un comando de Azure AzCopy que contiene parámetros con la ubicación en la que se almacenan los archivos que desea cargar y la ubicación de almacenamiento de Azure en la que se cargarán los archivos.</span><span class="sxs-lookup"><span data-stu-id="97b3c-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="97b3c-105">Para cargar los documentos, copie este comando y, a continuación, ejecútelo en un símbolo del sistema en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="97b3c-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="97b3c-106">La captura de pantalla siguiente muestra un ejemplo de un comando AzCopy:</span><span class="sxs-lookup"><span data-stu-id="97b3c-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Cargar archivos que no son de Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="97b3c-108">Normalmente, el comando que se proporciona funciona cuando se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="97b3c-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="97b3c-109">Sin embargo, puede haber casos en los que el comando que se muestra no se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="97b3c-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="97b3c-110">Estas son algunas de las razones posibles.</span><span class="sxs-lookup"><span data-stu-id="97b3c-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="97b3c-111">La versión compatible de AzCopy no está instalada en el equipo local</span><span class="sxs-lookup"><span data-stu-id="97b3c-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="97b3c-112">En este momento, debe usar AzCopy v 8.1 para cargar datos que no son de Microsoft 365 en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="97b3c-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="97b3c-113">El comando AzCopy que se muestra en la página **cargar archivos** que se muestra en la captura de pantalla anterior devuelve un error si no está usando AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="97b3c-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="97b3c-114">Para instalar esta versión, vea [transferir datos con AzCopy v 8.1 en Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="97b3c-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="97b3c-115">AzCopy no está instalado en el equipo local o no está instalado en la ubicación predeterminada</span><span class="sxs-lookup"><span data-stu-id="97b3c-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="97b3c-116">Si AzCopy no está instalado o está instalado en una ubicación distinta de la ubicación de instalación predeterminada (que es `%ProgramFiles(x86)%` ), es posible que reciba el siguiente error al ejecutar el comando AzCopy:</span><span class="sxs-lookup"><span data-stu-id="97b3c-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

    The system cannot find the path specified.

<span data-ttu-id="97b3c-117">Si AzCopy no está instalado en el equipo local, puede encontrar información de instalación en [transferir datos con AzCopy v 8.1 en Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="97b3c-117">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="97b3c-118">Asegúrese de instalarlo en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="97b3c-118">Be sure to install it in the default location.</span></span>

<span data-ttu-id="97b3c-119">Si AzCopy está instalado, pero se instala en una ubicación distinta de la ubicación predeterminada, puede copiar el comando, pegarlo en un archivo de texto y, a continuación, cambiar la ruta de acceso a la ubicación en la que se instaló AzCopy.</span><span class="sxs-lookup"><span data-stu-id="97b3c-119">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="97b3c-120">Por ejemplo, si Azcopy se encuentra en `%ProgramFiles%` , puede cambiar la primera parte del comando de `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` a `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` .</span><span class="sxs-lookup"><span data-stu-id="97b3c-120">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="97b3c-121">Después de realizar este cambio, cópielo del archivo de texto y, a continuación, ejecútelo desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="97b3c-121">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="97b3c-122">Si AzCopy está instalado en una ubicación distinta de la ubicación de instalación predeterminada, considere la posibilidad de desinstalarlo y volver a instalarlo en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="97b3c-122">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="97b3c-123">Esto le ayudará a evitar este problema en el futuro.</span><span class="sxs-lookup"><span data-stu-id="97b3c-123">This will help prevent this issue in the future.</span></span>
