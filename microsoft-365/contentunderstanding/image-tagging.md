---
title: Etiquetado de imágenes en SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Obtenga más información sobre el etiquetado de imágenes en SharePoint Syntex
ms.openlocfilehash: 7b41422633934593de881bdb0c04f0a845a3fe5f
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321258"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="35d75-103">Etiquetado de imágenes en SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="35d75-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="35d75-104">Con el etiquetado de imágenes en SharePoint Syntex, los usuarios pueden encontrar las imágenes mediante la búsqueda. Pare ello, pueden buscar en etiquetas de imagen y crear flujos de trabajo basados en etiquetas de imagen.</span><span class="sxs-lookup"><span data-stu-id="35d75-104">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="35d75-105">De forma predeterminada, el etiquetado básico de imágenes está activado para SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="35d75-105">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="35d75-106">Las imágenes cargadas en cualquiera de las ubicaciones se digitalizan automáticamente y se aplican las etiquetas aplicables, si están disponibles, en una lista de 37 etiquetas básicas.</span><span class="sxs-lookup"><span data-stu-id="35d75-106">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="35d75-107">Los usuarios pueden encontrar las imágenes mediante búsquedas en las etiquetas de imagen.</span><span class="sxs-lookup"><span data-stu-id="35d75-107">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="35d75-108">Cuando un usuario carga una imagen, el proceso de etiquetado se ejecutará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="35d75-108">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="35d75-109">Si edita una imagen, el proceso de etiquetado se ejecuta nuevamente para actualizar las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="35d75-109">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="35d75-110">Los usuarios con permisos para el archivo de imagen pueden ver y editar las etiquetas en el panel de información de archivo o en la página de resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="35d75-110">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="35d75-111">Cuando un usuario edita las etiquetas de una imagen, el sistema ya no realiza el etiquetado automático de la imagen, incluso si se edita.</span><span class="sxs-lookup"><span data-stu-id="35d75-111">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="35d75-112">Si desactiva el etiquetado, las imágenes ya no se etiquetarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="35d75-112">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="35d75-113">Las etiquetas existentes no se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="35d75-113">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="35d75-114">Las etiquetas generadas por el sistema pueden cambiar con actualizaciones de la imagen o nuestra tecnología de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="35d75-114">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="35d75-115">Configurar el etiquetado de imágenes</span><span class="sxs-lookup"><span data-stu-id="35d75-115">Configure image tagging</span></span>

<span data-ttu-id="35d75-116">Después de [configurar SharePoint Syntex](set-up-content-understanding.md), puede configurar el etiquetado de imágenes en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35d75-116">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="35d75-117">Para activar o desactivar el etiquetado de imágenes</span><span class="sxs-lookup"><span data-stu-id="35d75-117">To turn image tagging on or off</span></span>

1. <span data-ttu-id="35d75-118">En el Centro de administración de Microsoft 365, haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="35d75-118">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="35d75-119">En **Información de la organización**, haga clic en **Automatizar el contenido**.</span><span class="sxs-lookup"><span data-stu-id="35d75-119">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="35d75-120">Haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="35d75-120">Click **Manage**.</span></span>

4. <span data-ttu-id="35d75-121">En la pestaña **Etiquetado de imágenes**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="35d75-121">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="35d75-122">Elija permitir **Etiquetado básico** o **Desactivar** etiquetado.</span><span class="sxs-lookup"><span data-stu-id="35d75-122">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="35d75-123">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="35d75-123">Click **Save**.</span></span>

    ![Captura de pantalla del control de etiquetado de imágenes](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
