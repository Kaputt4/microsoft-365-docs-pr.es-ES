---
title: Usar la herramienta de exportación de exhibición de documentos electrónicos en Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Debe habilitar la compatibilidad de ClickOnce para usar la versión más reciente de Microsoft Edge para descargar los resultados de búsqueda de la búsqueda de contenido y la exhibición de documentos electrónicos en el centro de seguridad y cumplimiento.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546824"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="39c3d-103">Usar la herramienta de exportación de exhibición de documentos electrónicos en Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="39c3d-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="39c3d-104">Como resultado de los últimos cambios en la versión más reciente de Microsoft Edge, la compatibilidad con ClickOnce ya no está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="39c3d-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="39c3d-105">Para seguir usando la herramienta de exportación de exhibición de documentos electrónicos para descargar los resultados de búsqueda de contenido o de exhibición de documentos electrónicos, debe usar [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) o habilitar la compatibilidad con ClickOnce en la versión más reciente de Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="39c3d-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="39c3d-106">Habilitar la compatibilidad con ClickOnce en Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="39c3d-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="39c3d-107">En Microsoft Edge, ve a **edge://flags/#edge clic una vez**.</span><span class="sxs-lookup"><span data-stu-id="39c3d-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="39c3d-108">Si el valor existente se establece en **predeterminado** o está **deshabilitado** en la lista desplegable, cámbielo a **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="39c3d-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![Seleccionar habilitado en la lista desplegable](../media/ClickOnceimage1.png)

3. <span data-ttu-id="39c3d-110">Desplácese hacia abajo hasta la parte inferior de la ventana del explorador y haga clic en **reiniciar** para reiniciar el perímetro.</span><span class="sxs-lookup"><span data-stu-id="39c3d-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![Haga clic en reiniciar](../media/ClickOnceimage2.png)

<span data-ttu-id="39c3d-112">**Nota:** Las organizaciones pueden usar la Directiva de grupo para deshabilitar la compatibilidad con ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="39c3d-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="39c3d-113">Para comprobar si hay una directiva de la organización para la compatibilidad con ClickOnce, vaya a **Edge://Policy**.</span><span class="sxs-lookup"><span data-stu-id="39c3d-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="39c3d-114">En la siguiente captura de pantalla se muestra que ClickOnce está habilitado en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="39c3d-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="39c3d-115">Si el valor de esta Directiva se establece en **false**, deberá ponerse en contacto con un administrador de la organización.</span><span class="sxs-lookup"><span data-stu-id="39c3d-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![Lista de directivas de organización perimetral](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="39c3d-117">Instalar y ejecutar la herramienta de exportación de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="39c3d-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="39c3d-118">Haga clic en **Descargar resultados** en la página de flotante de una exportación en una búsqueda de contenido o un caso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="39c3d-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Haga clic en descargar resultados en la página de flotante para descargar los resultados de la búsqueda](../media/ClickOnceExport1.png)

2. <span data-ttu-id="39c3d-120">Se le pedirá que confirme que desea iniciar la herramienta; para ello, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="39c3d-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Haga clic en abrir para iniciar la herramienta de exportación de exhibición de documentos electrónicos](../media/ClickOnceimage4.png)

   <span data-ttu-id="39c3d-122">Si la herramienta de exportación de exhibición de documentos electrónicos no está instalada, se le mostrará una advertencia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="39c3d-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Haga clic en instalar para instalar la herramienta de exportación de exhibición de documentos electrónicos](../media/ClickOnceimage5.png)

3. <span data-ttu-id="39c3d-124">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="39c3d-124">Click **Install**.</span></span> <span data-ttu-id="39c3d-125">Una vez instalada, la herramienta de exportación se iniciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="39c3d-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="39c3d-126">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="39c3d-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="39c3d-127">Exportar resultados del Contenido de búsqueda</span><span class="sxs-lookup"><span data-stu-id="39c3d-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="39c3d-128">Cómo habilitar las marcas de experimento en Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="39c3d-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
