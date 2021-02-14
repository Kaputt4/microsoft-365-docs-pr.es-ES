---
title: Solucionar problemas de AzCopy en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Solucionar errores de Azure AzCopy al cargar datos que no son de Office 365 para la corrección de errores en eDiscovery avanzado.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 4a4499bb9790ffeaec6a2be36b5eaff030afc010
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546460"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="4a69c-103">Solucionar problemas de AzCopy en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="4a69c-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="4a69c-104">Al cargar datos que no son de Microsoft 365 o documentos para corregir errores en eDiscovery avanzado, la interfaz de usuario proporciona un comando AzCopy de Azure que contiene parámetros con la ubicación en la que se almacenan los archivos que desea cargar y la ubicación de Azure Storage en la que se cargarán los archivos.</span><span class="sxs-lookup"><span data-stu-id="4a69c-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="4a69c-105">Para cargar los documentos, copie este comando y, a continuación, ejecutarlo en un símbolo del sistema en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="4a69c-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="4a69c-106">La captura de pantalla siguiente muestra un ejemplo de un comando AzCopy:</span><span class="sxs-lookup"><span data-stu-id="4a69c-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Cargar archivos que no son de Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="4a69c-108">Normalmente, el comando que se proporciona funciona al ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="4a69c-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="4a69c-109">Sin embargo, puede haber casos en los que el comando que se muestra no se ejecutará correctamente.</span><span class="sxs-lookup"><span data-stu-id="4a69c-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="4a69c-110">Estas son algunas posibles razones.</span><span class="sxs-lookup"><span data-stu-id="4a69c-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="4a69c-111">La versión compatible de AzCopy no está instalada en el equipo local</span><span class="sxs-lookup"><span data-stu-id="4a69c-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="4a69c-112">En este momento, debe usar AzCopy v8.1 para cargar datos que no son de Microsoft 365 en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="4a69c-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="4a69c-113">El comando AzCopy que se  muestra en la página Cargar archivos que se muestra en la captura de pantalla anterior devuelve un error si no usa AzCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="4a69c-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="4a69c-114">Para instalar esta versión, vea [Transferir datos con AzCopy v8.1 en Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="4a69c-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="4a69c-115">AzCopy no está instalado en el equipo local o no está instalado en la ubicación predeterminada</span><span class="sxs-lookup"><span data-stu-id="4a69c-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="4a69c-116">Si AzCopy no está instalado o está instalado en una ubicación que no sea la ubicación de instalación predeterminada (que es), es posible que reciba el siguiente error al ejecutar el comando `%ProgramFiles(x86)%` AzCopy:</span><span class="sxs-lookup"><span data-stu-id="4a69c-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="4a69c-117">El sistema no puede encontrar la ruta de acceso especificada.</span><span class="sxs-lookup"><span data-stu-id="4a69c-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="4a69c-118">Si AzCopy no está instalado en el equipo local, puede encontrar información de instalación en Transferir datos con [AzCopy v8.1 en Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="4a69c-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="4a69c-119">Asegúrese de instalarlo en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4a69c-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="4a69c-120">Si AzCopy está instalado, pero está instalado en una ubicación diferente de la ubicación predeterminada, puede copiar el comando, pegarlo en un archivo de texto y, a continuación, cambiar la ruta de acceso a la ubicación donde está instalado AzCopy.</span><span class="sxs-lookup"><span data-stu-id="4a69c-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="4a69c-121">Por ejemplo, si Azcopy se encuentra en , puede cambiar la `%ProgramFiles%` primera parte del comando de a `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` .</span><span class="sxs-lookup"><span data-stu-id="4a69c-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="4a69c-122">Después de realizar este cambio, cópielo desde el archivo de texto y, a continuación, ejecute un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4a69c-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="4a69c-123">Si AzCopy está instalado en otra ubicación, la ubicación de instalación predeterminada, considere la posibilidad de desinstalarla y, a continuación, volver a instalarla en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4a69c-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="4a69c-124">Esto ayudará a evitar este problema en el futuro.</span><span class="sxs-lookup"><span data-stu-id="4a69c-124">This will help prevent this issue in the future.</span></span>
