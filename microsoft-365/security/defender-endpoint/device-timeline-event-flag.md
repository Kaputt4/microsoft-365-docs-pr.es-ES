---
title: Marcas de eventos de escala de tiempo de dispositivo de Microsoft Defender para punto de conexión
description: Usar Microsoft Defender para las marcas de eventos de escala de tiempo del dispositivo de punto de conexión para
keywords: Defender para la escala de tiempo del dispositivo de punto de conexión, marcas de evento
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165158"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a><span data-ttu-id="da955-104">Marcas de eventos de escala de tiempo de dispositivo de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="da955-104">Microsoft Defender for Endpoint device timeline event flags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="da955-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="da955-105">**Applies to:**</span></span>
- [<span data-ttu-id="da955-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="da955-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="da955-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da955-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="da955-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="da955-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="da955-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="da955-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="da955-110">Las marcas de eventos en la escala de tiempo del dispositivo Defender para endpoint te ayudan a filtrar y organizar eventos específicos cuando se investigan posibles ataques.</span><span class="sxs-lookup"><span data-stu-id="da955-110">Event flags in the Defender for Endpoint device timeline help you filter and organize specific events when you're  investigate potential attacks.</span></span>

<span data-ttu-id="da955-111">La escala de tiempo del dispositivo Defender for Endpoint proporciona una vista cronológica de los eventos y las alertas asociadas observadas en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="da955-111">The Defender for Endpoint device timeline provides a chronological view of the events and associated alerts observed on a device.</span></span> <span data-ttu-id="da955-112">Esta lista de eventos proporciona visibilidad completa de los eventos, archivos y direcciones IP observados en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="da955-112">This list of events provides full visibility into any events, files, and IP addresses observed on the device.</span></span> <span data-ttu-id="da955-113">La lista a veces puede ser larga.</span><span class="sxs-lookup"><span data-stu-id="da955-113">The list can sometimes be lengthy.</span></span> <span data-ttu-id="da955-114">Las marcas de eventos de escala de tiempo del dispositivo te ayudan a realizar un seguimiento de los eventos que podrían estar relacionados.</span><span class="sxs-lookup"><span data-stu-id="da955-114">Device timeline event flags help you track events that could be related.</span></span> 

<span data-ttu-id="da955-115">Después de pasar por una escala de tiempo del dispositivo, puedes ordenar, filtrar y exportar los eventos específicos marcados.</span><span class="sxs-lookup"><span data-stu-id="da955-115">After you've gone through a device timeline, you can sort, filter, and export the specific events that you flagged.</span></span>

<span data-ttu-id="da955-116">Al navegar por la escala de tiempo del dispositivo, puedes buscar y filtrar eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="da955-116">While navigating the device timeline, you can search and filter for specific events.</span></span> <span data-ttu-id="da955-117">Puede establecer las marcas de eventos mediante:</span><span class="sxs-lookup"><span data-stu-id="da955-117">You can set event flags by:</span></span> 

- <span data-ttu-id="da955-118">Resaltar los eventos más importantes</span><span class="sxs-lookup"><span data-stu-id="da955-118">Highlighting the most important events</span></span> 
- <span data-ttu-id="da955-119">Marcar eventos que requieren profundizar</span><span class="sxs-lookup"><span data-stu-id="da955-119">Marking events that requires deep dive</span></span> 
- <span data-ttu-id="da955-120">Creación de una escala de tiempo de vulneración limpia</span><span class="sxs-lookup"><span data-stu-id="da955-120">Building a clean breach timeline</span></span>



## <a name="flag-an-event"></a><span data-ttu-id="da955-121">Marcar un evento</span><span class="sxs-lookup"><span data-stu-id="da955-121">Flag an event</span></span>
1. <span data-ttu-id="da955-122">Buscar el evento que desea marcar</span><span class="sxs-lookup"><span data-stu-id="da955-122">Find the event that you want to flag</span></span>
2. <span data-ttu-id="da955-123">Haga clic en el icono de marca de la columna Marca.</span><span class="sxs-lookup"><span data-stu-id="da955-123">Click the flag icon in the Flag column.</span></span> 
<span data-ttu-id="da955-124">![Imagen de la marca de escala de tiempo del dispositivo](images/device-flags.png)</span><span class="sxs-lookup"><span data-stu-id="da955-124">![Image of device timeline flag](images/device-flags.png)</span></span>

## <a name="view-flagged-events"></a><span data-ttu-id="da955-125">Ver eventos marcados</span><span class="sxs-lookup"><span data-stu-id="da955-125">View flagged events</span></span>  
1. <span data-ttu-id="da955-126">En la sección **Filtros de** escala de tiempo, habilite **Eventos marcados**.</span><span class="sxs-lookup"><span data-stu-id="da955-126">In the timeline **Filters** section, enable **Flagged events**.</span></span>
2. <span data-ttu-id="da955-127">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="da955-127">Click **Apply**.</span></span> <span data-ttu-id="da955-128">Solo se muestran los eventos marcados.</span><span class="sxs-lookup"><span data-stu-id="da955-128">Only flagged events are displayed.</span></span>
<span data-ttu-id="da955-129">Puede aplicar filtros adicionales haciendo clic en la barra de horas.</span><span class="sxs-lookup"><span data-stu-id="da955-129">You can apply additional filters by clicking on the time bar.</span></span> <span data-ttu-id="da955-130">Solo se mostrarán los eventos anteriores al evento marcado.</span><span class="sxs-lookup"><span data-stu-id="da955-130">This will only show events prior to the flagged event.</span></span>  
<span data-ttu-id="da955-131">![Imagen de la marca de escala de tiempo del dispositivo con el filtro en](images/device-flag-filter.png)</span><span class="sxs-lookup"><span data-stu-id="da955-131">![Image of device timeline flag with filter on](images/device-flag-filter.png)</span></span>
