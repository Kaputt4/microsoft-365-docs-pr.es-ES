---
title: Administrar exclusiones de carpetas de automatización
description: Agregue exclusiones de carpetas de automatización para controlar los archivos que se excluyen de una investigación automatizada.
keywords: administrar, automatización, exclusión, bloquear, limpiar, malintencionada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fb398f1acbea4bd8f388c072f9706f9b2ca25175
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070195"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="f999e-104">Administrar exclusiones de carpetas de automatización</span><span class="sxs-lookup"><span data-stu-id="f999e-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f999e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f999e-105">**Applies to:**</span></span>
- [<span data-ttu-id="f999e-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f999e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f999e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f999e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f999e-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f999e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f999e-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f999e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="f999e-110">Las exclusiones de carpetas de automatización permiten especificar carpetas que omitirá la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="f999e-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="f999e-111">Puede controlar los siguientes atributos acerca de la carpeta que desea omitir:</span><span class="sxs-lookup"><span data-stu-id="f999e-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="f999e-112">Folders</span><span class="sxs-lookup"><span data-stu-id="f999e-112">Folders</span></span> 
- <span data-ttu-id="f999e-113">Extensiones de los archivos</span><span class="sxs-lookup"><span data-stu-id="f999e-113">Extensions of the files</span></span>
- <span data-ttu-id="f999e-114">Nombres de archivo</span><span class="sxs-lookup"><span data-stu-id="f999e-114">File names</span></span>


<span data-ttu-id="f999e-115">**Folders**</span><span class="sxs-lookup"><span data-stu-id="f999e-115">**Folders**</span></span><br>
<span data-ttu-id="f999e-116">Puede especificar una carpeta y sus subcarpetas que se omitirán.</span><span class="sxs-lookup"><span data-stu-id="f999e-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="f999e-117">En este momento, aún no se admite el uso de comodines como forma de excluir archivos en un directorio.</span><span class="sxs-lookup"><span data-stu-id="f999e-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="f999e-118">**Extensiones**</span><span class="sxs-lookup"><span data-stu-id="f999e-118">**Extensions**</span></span><br>
<span data-ttu-id="f999e-119">Puede especificar las extensiones que se excluirán en un directorio específico.</span><span class="sxs-lookup"><span data-stu-id="f999e-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="f999e-120">Las extensiones son una forma de impedir que un atacante use una carpeta excluida para ocultar una vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="f999e-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="f999e-121">Las extensiones definen explícitamente los archivos que se deben omitir.</span><span class="sxs-lookup"><span data-stu-id="f999e-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="f999e-122">**Nombres de archivo**</span><span class="sxs-lookup"><span data-stu-id="f999e-122">**File names**</span></span><br>
<span data-ttu-id="f999e-123">Puede especificar los nombres de archivo que desea excluir en un directorio específico.</span><span class="sxs-lookup"><span data-stu-id="f999e-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="f999e-124">Los nombres son una forma de impedir que un atacante use una carpeta excluida para ocultar una vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="f999e-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="f999e-125">Los nombres definen explícitamente los archivos que se deben omitir.</span><span class="sxs-lookup"><span data-stu-id="f999e-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="f999e-126">Agregar una exclusión de carpeta de automatización</span><span class="sxs-lookup"><span data-stu-id="f999e-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="f999e-127">En el panel de navegación, seleccione **Configuración**  >  **Exclusiones de carpeta Automatización.**</span><span class="sxs-lookup"><span data-stu-id="f999e-127">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="f999e-128">Haga **clic en Nueva exclusión de carpeta**.</span><span class="sxs-lookup"><span data-stu-id="f999e-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="f999e-129">Escriba los detalles de la carpeta:</span><span class="sxs-lookup"><span data-stu-id="f999e-129">Enter the folder details:</span></span>

    - <span data-ttu-id="f999e-130">Folder</span><span class="sxs-lookup"><span data-stu-id="f999e-130">Folder</span></span>
    - <span data-ttu-id="f999e-131">Extensiones</span><span class="sxs-lookup"><span data-stu-id="f999e-131">Extensions</span></span>
    - <span data-ttu-id="f999e-132">Nombres de archivo</span><span class="sxs-lookup"><span data-stu-id="f999e-132">File names</span></span>
    - <span data-ttu-id="f999e-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="f999e-133">Description</span></span>
    

4. <span data-ttu-id="f999e-134">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f999e-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="f999e-135">Los comandos live response para recopilar o examinar archivos excluidos producirán un error: "Se excluye el archivo".</span><span class="sxs-lookup"><span data-stu-id="f999e-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="f999e-136">Además, las investigaciones automatizadas omitirán los elementos excluidos.</span><span class="sxs-lookup"><span data-stu-id="f999e-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="f999e-137">Editar una exclusión de carpetas de automatización</span><span class="sxs-lookup"><span data-stu-id="f999e-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="f999e-138">En el panel de navegación, seleccione **Configuración**  >  **Exclusiones de carpeta Automatización.**</span><span class="sxs-lookup"><span data-stu-id="f999e-138">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="f999e-139">Haga **clic en Editar** en la exclusión de carpetas.</span><span class="sxs-lookup"><span data-stu-id="f999e-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="f999e-140">Actualice los detalles de la regla y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f999e-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="f999e-141">Quitar una exclusión de carpetas de automatización</span><span class="sxs-lookup"><span data-stu-id="f999e-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="f999e-142">En el panel de navegación, seleccione **Configuración**  >  **Exclusiones de carpeta Automatización.**</span><span class="sxs-lookup"><span data-stu-id="f999e-142">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="f999e-143">Haga clic **en Quitar exclusión**.</span><span class="sxs-lookup"><span data-stu-id="f999e-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="f999e-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f999e-144">Related topics</span></span>
- [<span data-ttu-id="f999e-145">Administrar listas de automatización permitidas o bloqueadas</span><span class="sxs-lookup"><span data-stu-id="f999e-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="f999e-146">Administrar cargas de archivos de automatización</span><span class="sxs-lookup"><span data-stu-id="f999e-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
