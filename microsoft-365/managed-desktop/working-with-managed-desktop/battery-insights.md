---
title: Información sobre las baterías
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f339fc98ea94c291c533045e9906f626f4b74e2a
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529844"
---
# <a name="battery-insights"></a><span data-ttu-id="c5693-103">Información sobre las baterías</span><span class="sxs-lookup"><span data-stu-id="c5693-103">Battery insights</span></span>
<span data-ttu-id="c5693-104">Esta vista proporciona métricas de uso de energía, batería y aplicaciones para los dispositivos de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5693-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5693-105">Para estos fines, una aplicación se considera "en uso" si se está ejecutando y en foco.</span><span class="sxs-lookup"><span data-stu-id="c5693-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="c5693-106">Para ver los datos de uso, selecciona la **pestaña** Batería.</span><span class="sxs-lookup"><span data-stu-id="c5693-106">To view usage data, select the **Battery** tab.</span></span>

![Panel de batería: duración de la batería pronosticada por modelo de dispositivo en la parte superior izquierda, consumidores de energía superiores (por aplicación) en la parte superior derecha, tabla insights en la parte inferior.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="c5693-109">Duración de la batería pronosticada</span><span class="sxs-lookup"><span data-stu-id="c5693-109">Predicted battery life</span></span>

<span data-ttu-id="c5693-110">En el **área de duración prevista** de la batería, proporcionamos las previsiones para la duración prevista de la batería de los dispositivos, organizadas por modelo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c5693-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="c5693-111">Estos datos se derivan del uso de energía de <em></em> muestreo, el tiempo de uso y la capacidad de la batería de una selección aleatoria de los dispositivos de la implementación de Escritorio administrado de Microsoft que también informan de los datos.</span><span class="sxs-lookup"><span data-stu-id="c5693-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="c5693-112">La tabla proporciona la duración de la batería pronosticada (en horas), la duración media de la batería para los mismos modelos en otras implementaciones de Escritorio administrado de Microsoft y el número de dispositivos que informan de estos datos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="c5693-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="c5693-113">Ordene los datos seleccionando los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="c5693-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="c5693-114">Principales consumidores de energía</span><span class="sxs-lookup"><span data-stu-id="c5693-114">Top energy consumers</span></span>

<span data-ttu-id="c5693-115">En el **área de consumidores** principales de energía, encontrarás las aplicaciones de tu entorno que consumen la mayor cantidad de energía en milisegundos-hora (mWh).</span><span class="sxs-lookup"><span data-stu-id="c5693-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="c5693-116">Las aplicaciones que se muestran son por dispositivo específico, que seleccionas en la sección **Duración** de la batería previsto a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="c5693-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="c5693-117">Por ejemplo, para ver el consumo por aplicación de los dispositivos Microsoft Surface Book 2, selecciona esa fila en el área de duración de la batería.</span><span class="sxs-lookup"><span data-stu-id="c5693-117">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="c5693-118">Si no seleccionas ningún modelo, los datos de consumo de aplicaciones que se muestran son para todas las aplicaciones para las que tenemos datos de forma colectiva.</span><span class="sxs-lookup"><span data-stu-id="c5693-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="c5693-119">Para cada aplicación, los segmentos de colores muestran la distribución del uso de energía de la aplicación entre estas categorías:</span><span class="sxs-lookup"><span data-stu-id="c5693-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="c5693-120">CPU</span><span class="sxs-lookup"><span data-stu-id="c5693-120">CPU</span></span>
- <span data-ttu-id="c5693-121">Visualización</span><span class="sxs-lookup"><span data-stu-id="c5693-121">Display</span></span>
- <span data-ttu-id="c5693-122">Red</span><span class="sxs-lookup"><span data-stu-id="c5693-122">Network</span></span>
- <span data-ttu-id="c5693-123">Otros</span><span class="sxs-lookup"><span data-stu-id="c5693-123">Other</span></span>

<span data-ttu-id="c5693-124">"Otros" podría incluir el consumo de energía por parte de una variedad de fuentes, como la actividad de disco, el uso de banda ancha móvil y la energía perdida a la resistencia interna.</span><span class="sxs-lookup"><span data-stu-id="c5693-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="c5693-125">Puedes filtrar esta vista para mostrar solo aplicaciones en primer plano, aplicaciones en segundo plano o ambas mediante el menú de la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="c5693-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="c5693-126">Las aplicaciones en primer plano son aquellas que han tenido interacción del usuario en los últimos 28 días, como seleccionar algo con un mouse.</span><span class="sxs-lookup"><span data-stu-id="c5693-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="c5693-127">Insights</span><span class="sxs-lookup"><span data-stu-id="c5693-127">Insights</span></span>

<span data-ttu-id="c5693-128">El **área Insights** muestra los tres principales consumidores de energía en las categorías de CPU y red.</span><span class="sxs-lookup"><span data-stu-id="c5693-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="c5693-129">Estos elementos consumen una energía superior a la media en comparación con todas las implementaciones de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5693-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="c5693-130">No se muestra el recurso de pantalla porque depende en gran medida del tiempo de uso del dispositivo y de la configuración de brillo de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="c5693-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="c5693-131">Seleccione los listados en la **columna Detalles** para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c5693-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="c5693-132">Optimización de la batería</span><span class="sxs-lookup"><span data-stu-id="c5693-132">Battery optimization</span></span>

<span data-ttu-id="c5693-133">Windows 10 ofrece numerosas opciones de [configuración de dispositivos](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) para mejorar el uso de energía y aumentar la duración de la batería de los dispositivos de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5693-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5693-134">Algunas de estas opciones de configuración pueden disminuir otras funciones de Windows, por lo que también tendrás que tener en cuenta otros factores, como el rol del dispositivo en la organización.</span><span class="sxs-lookup"><span data-stu-id="c5693-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="c5693-135">El soporte técnico de Windows mantiene una lista de estas sugerencias [de ahorro de batería.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="c5693-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="c5693-136">Los usuarios pueden ajustar algunas opciones de configuración por sí mismos sin necesidad de elevación o soporte técnico de administrador.</span><span class="sxs-lookup"><span data-stu-id="c5693-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="c5693-137">Otras opciones requieren soporte técnico del administrador de TI de la organización.</span><span class="sxs-lookup"><span data-stu-id="c5693-137">Other settings require support from your organization's IT administrator.</span></span>
