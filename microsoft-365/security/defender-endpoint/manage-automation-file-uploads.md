---
title: Administrar cargas de archivos de automatización
description: Habilitar el análisis de contenido y configurar las extensiones de archivo y datos adjuntos de correo electrónico que se enviarán para su análisis
keywords: automatización, archivo, cargas, contenido, análisis, archivo, extensión, correo electrónico, datos adjuntos
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
ms.openlocfilehash: 72405ad7500bf5d672f66ea64634e60c29ad1704
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076912"
---
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="847b6-104">Administrar cargas de archivos de automatización</span><span class="sxs-lookup"><span data-stu-id="847b6-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="847b6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="847b6-105">**Applies to:**</span></span>
- [<span data-ttu-id="847b6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="847b6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="847b6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="847b6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="847b6-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="847b6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="847b6-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="847b6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="847b6-110">Habilite la funcionalidad de análisis de contenido para que determinados archivos y datos adjuntos de correo electrónico se puedan cargar automáticamente en la nube para una inspección adicional en la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="847b6-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="847b6-111">Identifique los archivos y los datos adjuntos de correo electrónico especificando los nombres de extensión de archivo y los nombres de extensión de datos adjuntos de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="847b6-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="847b6-112">Por ejemplo, si agrega *exe* y *bat* como nombres de extensión de archivo o datos adjuntos, todos los archivos o datos adjuntos con esas extensiones se enviarán automáticamente a la nube para una inspección adicional durante la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="847b6-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="847b6-113">Agregue nombres de extensión de archivo y nombres de extensión de datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="847b6-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="847b6-114">En el panel de navegación, seleccione **Settings**  >  **Automation file uploads**.</span><span class="sxs-lookup"><span data-stu-id="847b6-114">In the navigation pane, select **Settings** > **Automation file uploads**.</span></span> 

2. <span data-ttu-id="847b6-115">Alterna la configuración del análisis de contenido **entre On** y **Off**.</span><span class="sxs-lookup"><span data-stu-id="847b6-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="847b6-116">Configure los siguientes nombres de extensión y separe los nombres de extensión con una coma:</span><span class="sxs-lookup"><span data-stu-id="847b6-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="847b6-117">**Nombres de extensión de archivo:** los archivos sospechosos, excepto los datos adjuntos de correo electrónico, se enviarán para inspección adicional</span><span class="sxs-lookup"><span data-stu-id="847b6-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="847b6-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="847b6-118">Related topics</span></span>
- [<span data-ttu-id="847b6-119">Administrar exclusiones de carpetas de automatización</span><span class="sxs-lookup"><span data-stu-id="847b6-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)
