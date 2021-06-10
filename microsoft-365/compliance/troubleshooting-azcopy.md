---
title: Solucionar problemas de AzCopy en Advanced eDiscovery
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
description: Solucionar errores de Azure AzCopy al cargar datos no Office 365 para la corrección de errores en Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919296"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="3ed33-103">Solucionar problemas de AzCopy en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3ed33-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="3ed33-104">Al cargar datos o documentos que no son de Microsoft 365 para la corrección de errores en Advanced eDiscovery, la interfaz de usuario proporciona un comando de Azure AzCopy que contiene parámetros con la ubicación de dónde se almacenan los archivos que desea cargar y la ubicación de almacenamiento de Azure en la que se cargarán los archivos.</span><span class="sxs-lookup"><span data-stu-id="3ed33-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="3ed33-105">Para cargar los documentos, copie este comando y, a continuación, ejecutarlo en un símbolo del sistema en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="3ed33-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="3ed33-106">La captura de pantalla siguiente muestra un ejemplo de un comando AzCopy:</span><span class="sxs-lookup"><span data-stu-id="3ed33-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Upload no Microsoft 365 archivos](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="3ed33-108">Normalmente, el comando que se proporciona funciona al ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="3ed33-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="3ed33-109">Sin embargo, puede haber casos en los que el comando que se muestra no se ejecutará correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ed33-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="3ed33-110">Estos son algunos motivos posibles.</span><span class="sxs-lookup"><span data-stu-id="3ed33-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="3ed33-111">La versión compatible de AzCopy no está instalada en el equipo local</span><span class="sxs-lookup"><span data-stu-id="3ed33-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="3ed33-112">En este momento, debe usar AzCopy v8.1 para cargar datos no Microsoft 365 en Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="3ed33-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="3ed33-113">El comando AzCopy que se muestra en la página de archivos **Upload** que se muestra en la captura de pantalla anterior devuelve un error si no usa AzCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="3ed33-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="3ed33-114">Para instalar esta versión, vea [Transferir datos con AzCopy v8.1 en Windows](/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="3ed33-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="3ed33-115">AzCopy no está instalado en el equipo local o no está instalado en la ubicación predeterminada</span><span class="sxs-lookup"><span data-stu-id="3ed33-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="3ed33-116">Si AzCopy no está instalado o está instalado en una ubicación que no sea la ubicación de instalación predeterminada (que es ), puede recibir el siguiente error al ejecutar el comando `%ProgramFiles(x86)%` AzCopy:</span><span class="sxs-lookup"><span data-stu-id="3ed33-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="3ed33-117">El sistema no puede encontrar la ruta de acceso especificada.</span><span class="sxs-lookup"><span data-stu-id="3ed33-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="3ed33-118">Si AzCopy no está instalado en el equipo local, puede encontrar información de instalación en Transferir datos con [azCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)en Windows .</span><span class="sxs-lookup"><span data-stu-id="3ed33-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="3ed33-119">Asegúrese de instalarlo en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3ed33-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="3ed33-120">Si AzCopy está instalado, pero está instalado en una ubicación diferente a la ubicación predeterminada, puede copiar el comando, pegarlo en un archivo de texto y, a continuación, cambiar la ruta de acceso a la ubicación donde está instalado AzCopy.</span><span class="sxs-lookup"><span data-stu-id="3ed33-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="3ed33-121">Por ejemplo, si Azcopy se encuentra en , puede cambiar la primera parte `%ProgramFiles%` del comando de a `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` .</span><span class="sxs-lookup"><span data-stu-id="3ed33-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="3ed33-122">Después de realizar este cambio, cópielo desde el archivo de texto y, a continuación, ejecute un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3ed33-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="3ed33-123">Si AzCopy está instalado en otra ubicación, la ubicación de instalación predeterminada, considere la posibilidad de desinstalarla y, a continuación, volver a instalarla en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3ed33-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="3ed33-124">Esto ayudará a evitar este problema en el futuro.</span><span class="sxs-lookup"><span data-stu-id="3ed33-124">This will help prevent this issue in the future.</span></span>