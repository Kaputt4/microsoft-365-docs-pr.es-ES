---
title: Upload Binarios de aplicación
description: Cómo empezar a usar Test Base para M365
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
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323168"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a><span data-ttu-id="fbd06-103">Paso 3: Upload archivos binarios, dependencias y scripts</span><span class="sxs-lookup"><span data-stu-id="fbd06-103">Step 3: Upload your binaries, dependencies, and scripts</span></span>

<span data-ttu-id="fbd06-104">En esta pestaña, cargará un único paquete zip que contenga los archivos binarios, dependencias y scripts usados para ejecutar el conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="fbd06-104">On this tab, you will upload a single zip package containing your binaries, dependencies and scripts used to run your test suite.</span></span>

## <a name="upload-package-zip-file"></a><span data-ttu-id="fbd06-105">Upload archivo zip del paquete</span><span class="sxs-lookup"><span data-stu-id="fbd06-105">Upload package zip file</span></span>

![Upload archivos binarios](Media/AddBinaries.png)

  - <span data-ttu-id="fbd06-107">Las dependencias cargadas pueden incluir marcos de prueba, motores de scripting o datos a los que se tendrá acceso para ejecutar los casos de prueba o aplicación.</span><span class="sxs-lookup"><span data-stu-id="fbd06-107">Uploaded dependencies can include test frameworks, scripting engines or data that will be accessed to run your application or test cases.</span></span> <span data-ttu-id="fbd06-108">Por ejemplo, puede cargar Selenio y un instalador de webdriver para ayudar a ejecutar pruebas basadas en explorador.</span><span class="sxs-lookup"><span data-stu-id="fbd06-108">For example, you can upload Selenium and a webdriver installer to help run browser-based tests.</span></span>
  - <span data-ttu-id="fbd06-109">Es una práctica recomendada asegurarse de que las actividades de script se mantienen modulares, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fbd06-109">It is best practice to ensure your script activities are kept modular i.e.</span></span> 
    - <span data-ttu-id="fbd06-110">El ```Install``` script solo realiza operaciones de instalación.</span><span class="sxs-lookup"><span data-stu-id="fbd06-110">The ```Install``` script only performs install operations.</span></span>
    - <span data-ttu-id="fbd06-111">El ```Launch``` script solo inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fbd06-111">The ```Launch``` script only launches the application.</span></span>
    - <span data-ttu-id="fbd06-112">El ```Close``` script solo cierra la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fbd06-112">The ```Close``` script only closes the application.</span></span>
    - <span data-ttu-id="fbd06-113">El ```Uninstall``` script opcional solo desinstala la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fbd06-113">The optional ```Uninstall``` script only uninstalls the application.</span></span>

<span data-ttu-id="fbd06-114">**Actualmente, el portal solo admite scripts de PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="fbd06-114">**Currently, the portal only supports PowerShell scripts.**</span></span>


## <a name="next-steps"></a><span data-ttu-id="fbd06-115">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fbd06-115">Next steps</span></span> 

<span data-ttu-id="fbd06-116">Vaya al siguiente artículo para ir al Paso 4: **Establecer las tareas de prueba**.</span><span class="sxs-lookup"><span data-stu-id="fbd06-116">Advance to the next article to go onto Step 4: **Set your Test Tasks**.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="fbd06-117">Volver</span><span class="sxs-lookup"><span data-stu-id="fbd06-117">Go back</span></span>](uploadApplication.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="fbd06-118">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="fbd06-118">Next step</span></span>](testtask.md)

