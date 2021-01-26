---
title: Etiquetado de imágenes en SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga más información sobre el etiquetado de imágenes en SharePoint Syntex
ms.openlocfilehash: 0fba54db6a16a9a8571c7e1ced61b7620cf5113e
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975870"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="f5502-103">Etiquetado de imágenes en SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="f5502-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="f5502-104">(Próximamente)</span><span class="sxs-lookup"><span data-stu-id="f5502-104">(Coming soon)</span></span>

<span data-ttu-id="f5502-105">Con el etiquetado de imágenes en SharePoint Syntex, los usuarios pueden encontrar las imágenes mediante la búsqueda. Pare ello, pueden buscar en etiquetas de imagen y crear flujos de trabajo basados en etiquetas de imagen.</span><span class="sxs-lookup"><span data-stu-id="f5502-105">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="f5502-106">De forma predeterminada, el etiquetado básico de imágenes está activado para SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f5502-106">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="f5502-107">Las imágenes cargadas en cualquiera de las ubicaciones se digitalizan automáticamente y se aplican las etiquetas aplicables, si están disponibles, en una lista de 37 etiquetas básicas.</span><span class="sxs-lookup"><span data-stu-id="f5502-107">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="f5502-108">Los usuarios pueden encontrar las imágenes mediante búsquedas en las etiquetas de imagen.</span><span class="sxs-lookup"><span data-stu-id="f5502-108">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="f5502-109">Cuando un usuario carga una imagen, el proceso de etiquetado se ejecutará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f5502-109">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="f5502-110">Si edita una imagen, el proceso de etiquetado se ejecuta nuevamente para actualizar las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="f5502-110">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="f5502-111">Los usuarios con permisos para el archivo de imagen pueden ver y editar las etiquetas en el panel de información de archivo o en la página de resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f5502-111">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="f5502-112">Cuando un usuario edita las etiquetas de una imagen, el sistema ya no realiza el etiquetado automático de la imagen, incluso si se edita.</span><span class="sxs-lookup"><span data-stu-id="f5502-112">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="f5502-113">Si desactiva el etiquetado, las imágenes ya no se etiquetarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f5502-113">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="f5502-114">Las etiquetas existentes no se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="f5502-114">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="f5502-115">Las etiquetas generadas por el sistema pueden cambiar con actualizaciones de la imagen o nuestra tecnología de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="f5502-115">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="f5502-116">Configurar el etiquetado de imágenes</span><span class="sxs-lookup"><span data-stu-id="f5502-116">Configure image tagging</span></span>

<span data-ttu-id="f5502-117">Después de [configurar SharePoint Syntex](set-up-content-understanding.md), puede configurar el etiquetado de imágenes en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5502-117">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="f5502-118">Para activar o desactivar el etiquetado de imágenes</span><span class="sxs-lookup"><span data-stu-id="f5502-118">To turn image tagging on or off</span></span>

1. <span data-ttu-id="f5502-119">En el Centro de administración de Microsoft 365, haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="f5502-119">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="f5502-120">En **Información de la organización**, haga clic en **Automatizar el contenido**.</span><span class="sxs-lookup"><span data-stu-id="f5502-120">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="f5502-121">Haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="f5502-121">Click **Manage**.</span></span>

4. <span data-ttu-id="f5502-122">En la pestaña **Etiquetado de imágenes**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f5502-122">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="f5502-123">Elija permitir **Etiquetado básico** o **Desactivar** etiquetado.</span><span class="sxs-lookup"><span data-stu-id="f5502-123">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="f5502-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f5502-124">Click **Save**.</span></span>

    ![Captura de pantalla del control de etiquetado de imágenes](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
