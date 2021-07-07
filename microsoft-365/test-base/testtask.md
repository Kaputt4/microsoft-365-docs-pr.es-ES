---
title: Establecer las tareas de prueba
description: Establecer las tareas de prueba
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322948"
---
# <a name="step-4-the-tasks-tab"></a><span data-ttu-id="212af-103">Paso 4: pestaña Tareas</span><span class="sxs-lookup"><span data-stu-id="212af-103">Step 4: The tasks tab</span></span>

<span data-ttu-id="212af-104">En la pestaña tareas, se espera que proporcione las rutas de acceso a los scripts de prueba que se encuentran en la carpeta zip que ha cargado en la pestaña archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="212af-104">On the tasks tab, you are expected to provide the paths to your test scripts which are in the zip folder you uploaded under the binaries tab.</span></span>

  - <span data-ttu-id="212af-105">**Scripts de pruebas sin formato:** Escriba las rutas de acceso relativas a los scripts de instalación, inicio, cierre y desinstalación.</span><span class="sxs-lookup"><span data-stu-id="212af-105">**Out of Box Test Scripts:** Type in the relative paths to your install, launch, close and uninstall scripts.</span></span> <span data-ttu-id="212af-106">También tiene la opción de seleccionar opciones adicionales para el script de instalación.</span><span class="sxs-lookup"><span data-stu-id="212af-106">You also have the option to select additional settings for the install script.</span></span>
  - <span data-ttu-id="212af-107">**Scripts de prueba funcionales:** Escriba la ruta de acceso relativa a cada script de prueba funcional cargado.</span><span class="sxs-lookup"><span data-stu-id="212af-107">**Functional Test Scripts:** Type in the relative path to each functional test script uploaded.</span></span> <span data-ttu-id="212af-108">Se pueden agregar scripts de prueba funcionales adicionales con el ```Add Script``` botón.</span><span class="sxs-lookup"><span data-stu-id="212af-108">Additional functional test scripts can be added using the ```Add Script``` button.</span></span> <span data-ttu-id="212af-109">Necesita un mínimo de un script (1) y puede agregar hasta ocho (8) scripts de prueba funcionales.</span><span class="sxs-lookup"><span data-stu-id="212af-109">You need a minimum of one (1) script and can add up to eight (8) functional test scripts.</span></span> 
  
    <span data-ttu-id="212af-110">Los scripts se ejecutan en secuencia de carga y un error en un script determinado impedirá que se ejecuten scripts posteriores.</span><span class="sxs-lookup"><span data-stu-id="212af-110">The scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>
    <span data-ttu-id="212af-111">También tiene la opción de seleccionar opciones adicionales para cada script proporcionado.</span><span class="sxs-lookup"><span data-stu-id="212af-111">You also have the option of selecting additional settings for each script provided.</span></span>

## <a name="set-script-path"></a><span data-ttu-id="212af-112">Establecer ruta de acceso de script</span><span class="sxs-lookup"><span data-stu-id="212af-112">Set script path</span></span>

![Imagen de la tarea de prueba](Media/testtask.png)

<span data-ttu-id="212af-114">A continuación se muestra un ejemplo de cómo proporcionar la ruta de acceso relativa en una estructura de carpetas:</span><span class="sxs-lookup"><span data-stu-id="212af-114">Sample of how to provide the relative path on a folder structure is below:</span></span>

<span data-ttu-id="212af-115">_**Zip_file_uploaded**_</span><span class="sxs-lookup"><span data-stu-id="212af-115">_**Zip_file_uploaded**_</span></span>
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="212af-116">**ScriptX.ps1** habría sido así.</span><span class="sxs-lookup"><span data-stu-id="212af-116">**ScriptX.ps1** would have.</span></span> <span data-ttu-id="212af-117">_ScriptX.ps1_ como la ruta de acceso relativa.</span><span class="sxs-lookup"><span data-stu-id="212af-117">_ScriptX.ps1_ as the relative path.</span></span>
  - <span data-ttu-id="212af-118">**Script.ps1** _carpeta1/script.ps1_ como ruta de acceso relativa.</span><span class="sxs-lookup"><span data-stu-id="212af-118">**Script.ps1** would have _folder1/script.ps1_ as the relative path.</span></span>


## <a name="next-steps"></a><span data-ttu-id="212af-119">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="212af-119">Next steps</span></span>

<span data-ttu-id="212af-120">Vea los detalles de la pestaña Opciones de prueba en el siguiente artículo</span><span class="sxs-lookup"><span data-stu-id="212af-120">View details of the Test Options tab in the next article</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="212af-121">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="212af-121">Next step</span></span>](testoptions.md)
