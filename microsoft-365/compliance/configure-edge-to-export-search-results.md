---
title: Use la herramienta de exportación de exhibición de documentos electrónicos en Microsoft Edge
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
description: Debe habilitar la compatibilidad ClickOnce para usar la versión más reciente de Microsoft Edge para descargar los resultados de búsqueda de la búsqueda de contenido y la exhibición de documentos electrónicos en el centro de seguridad y cumplimiento.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546824"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="49d78-103">Use la herramienta de exportación de exhibición de documentos electrónicos en Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="49d78-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="49d78-104">Como resultado de los cambios recientes en la versión más reciente de Microsoft Edge, ClickOnce soporte técnico ya no está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="49d78-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="49d78-105">Para seguir usando la herramienta de exportación de exhibición de documentos electrónicos para descargar resultados de búsqueda de búsqueda de contenido o exhibición de documentos electrónicos, debe usar [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) o habilitar la compatibilidad ClickOnce en la versión más reciente de Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="49d78-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="49d78-106">Habilitar ClickOnce soporte técnico en Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="49d78-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="49d78-107">En Microsoft Edge, vaya **a edge://flags/#edge-click-once**.</span><span class="sxs-lookup"><span data-stu-id="49d78-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="49d78-108">Si el valor existente se establece en **Predeterminado** o Deshabilitado **en** la lista desplegable, cámbilo a **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="49d78-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![Seleccionar habilitado en la lista desplegable](../media/ClickOnceimage1.png)

3. <span data-ttu-id="49d78-110">Desplácese hacia abajo hasta la parte inferior de la ventana del explorador y haga clic **en Reiniciar** para reiniciar Edge.</span><span class="sxs-lookup"><span data-stu-id="49d78-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![Haga clic en Reiniciar](../media/ClickOnceimage2.png)

<span data-ttu-id="49d78-112">**Nota:** Las organizaciones pueden usar la directiva de grupo para deshabilitar ClickOnce compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="49d78-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="49d78-113">Para comprobar si hay una directiva organizativa para la ClickOnce, vaya a **edge://policy**.</span><span class="sxs-lookup"><span data-stu-id="49d78-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="49d78-114">La siguiente captura de pantalla muestra ClickOnce está habilitada en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="49d78-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="49d78-115">Si este valor de directiva se establece en **false,** deberá ponerse en contacto con un administrador de la organización.</span><span class="sxs-lookup"><span data-stu-id="49d78-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![Lista de directivas organizativas perimetrales](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="49d78-117">Instalar y ejecutar la herramienta de exportación de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="49d78-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="49d78-118">Haga clic en Descargar **resultados** en la página desplegable de una exportación en Búsqueda de contenido o en un caso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="49d78-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Haga clic en Descargar resultados en la página desplegable para descargar los resultados de búsqueda](../media/ClickOnceExport1.png)

2. <span data-ttu-id="49d78-120">Se le pedirá una confirmación para iniciar la herramienta, Haga clic **en Abrir**.</span><span class="sxs-lookup"><span data-stu-id="49d78-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Haga clic en Abrir para iniciar la herramienta de exportación de exhibición de documentos electrónicos](../media/ClickOnceimage4.png)

   <span data-ttu-id="49d78-122">Si la herramienta de exportación de exhibición de documentos electrónicos no está instalada, se le pedirá una advertencia de seguridad,</span><span class="sxs-lookup"><span data-stu-id="49d78-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Haga clic en Instalar para instalar la herramienta de exportación de exhibición de documentos electrónicos](../media/ClickOnceimage5.png)

3. <span data-ttu-id="49d78-124">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="49d78-124">Click **Install**.</span></span> <span data-ttu-id="49d78-125">Una vez instalada, la herramienta de exportación se iniciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="49d78-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="49d78-126">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="49d78-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="49d78-127">Exportar resultados de la búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="49d78-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="49d78-128">Cómo habilitar las marcas de experimento en Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="49d78-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
