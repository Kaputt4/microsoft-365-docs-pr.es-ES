---
title: Información sobre las baterías
description: Un informe que muestra datos sobre la duración de la batería y los principales consumidores de energía
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739830"
---
# <a name="battery-insights"></a><span data-ttu-id="7b770-104">Información sobre las baterías</span><span class="sxs-lookup"><span data-stu-id="7b770-104">Battery insights</span></span>
<span data-ttu-id="7b770-105">Esta vista proporciona métricas de consumo de energía, batería y aplicaciones para los Escritorio administrado de Microsoft dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7b770-105">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="7b770-106">Para estos fines, una aplicación se considera "en uso" si se está ejecutando y en foco.</span><span class="sxs-lookup"><span data-stu-id="7b770-106">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="7b770-107">Para ver los datos de uso, seleccione la **pestaña** Batería.</span><span class="sxs-lookup"><span data-stu-id="7b770-107">To view usage data, select the **Battery** tab.</span></span>

![Panel de batería: duración de la batería pronosticada por modelo de dispositivo en la parte superior izquierda, consumidores de energía superiores (por aplicación) en la parte superior derecha, tabla de información en la parte inferior.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="7b770-110">Duración de la batería pronosticada</span><span class="sxs-lookup"><span data-stu-id="7b770-110">Predicted battery life</span></span>

<span data-ttu-id="7b770-111">En el **área Duración de la batería** predicho, proporcionamos previsiones para la duración de la batería esperada para los dispositivos, organizadas por el modelo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7b770-111">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="7b770-112">Estos datos se derivan del uso de energía de <em></em> muestreo, el tiempo de uso y la capacidad de batería de una selección aleatoria de los dispositivos de la implementación de Escritorio administrado de Microsoft que también están informando datos.</span><span class="sxs-lookup"><span data-stu-id="7b770-112">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="7b770-113">La tabla proporciona la duración de la batería predicho (en horas), la duración media de la batería de los mismos modelos en otras implementaciones de Escritorio administrado de Microsoft y el número de dispositivos que informan de estos datos en el entorno.</span><span class="sxs-lookup"><span data-stu-id="7b770-113">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="7b770-114">Para ordenar los datos, seleccione los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="7b770-114">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="7b770-115">Principales consumidores de energía</span><span class="sxs-lookup"><span data-stu-id="7b770-115">Top energy consumers</span></span>

<span data-ttu-id="7b770-116">En el **área Principales consumidores** de energía, encontrarás las aplicaciones de tu entorno que consumen más energía en milivavatio-hora (mWh).</span><span class="sxs-lookup"><span data-stu-id="7b770-116">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="7b770-117">Las aplicaciones que se muestran son por dispositivo específico, que seleccionas en la sección **Duración** de la batería predicho a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="7b770-117">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="7b770-118">Por ejemplo, para ver el consumo por aplicación de los dispositivos de Microsoft Surface Book 2, selecciona esa fila en el área de duración de la batería.</span><span class="sxs-lookup"><span data-stu-id="7b770-118">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="7b770-119">Si no seleccionas ningún modelo, los datos de consumo de aplicaciones que se muestran son para todas las aplicaciones para las que tenemos datos de forma colectiva.</span><span class="sxs-lookup"><span data-stu-id="7b770-119">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="7b770-120">Para cada aplicación, los segmentos de color muestran la distribución del uso de energía de la aplicación entre estas categorías:</span><span class="sxs-lookup"><span data-stu-id="7b770-120">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="7b770-121">CPU</span><span class="sxs-lookup"><span data-stu-id="7b770-121">CPU</span></span>
- <span data-ttu-id="7b770-122">Pantalla</span><span class="sxs-lookup"><span data-stu-id="7b770-122">Display</span></span>
- <span data-ttu-id="7b770-123">Red</span><span class="sxs-lookup"><span data-stu-id="7b770-123">Network</span></span>
- <span data-ttu-id="7b770-124">Otros</span><span class="sxs-lookup"><span data-stu-id="7b770-124">Other</span></span>

<span data-ttu-id="7b770-125">"Otros" podría incluir el consumo de energía por una variedad de fuentes, como la actividad de disco, el uso de banda ancha móvil y la energía perdida por la resistencia interna.</span><span class="sxs-lookup"><span data-stu-id="7b770-125">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="7b770-126">Puedes filtrar esta vista para mostrar solo aplicaciones en primer plano, aplicaciones en segundo plano o ambas mediante el menú de la parte superior derecha.</span><span class="sxs-lookup"><span data-stu-id="7b770-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="7b770-127">Las aplicaciones en primer plano son aquellas que han tenido interacción del usuario en los últimos 28 días, como seleccionar algo con un mouse.</span><span class="sxs-lookup"><span data-stu-id="7b770-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="7b770-128">Insights</span><span class="sxs-lookup"><span data-stu-id="7b770-128">Insights</span></span>

<span data-ttu-id="7b770-129">El **área Insights** muestra los tres principales consumidores de energía en las categorías de CPU y red.</span><span class="sxs-lookup"><span data-stu-id="7b770-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="7b770-130">Estos elementos consumen energía superior a la media en comparación con todas Escritorio administrado de Microsoft implementaciones.</span><span class="sxs-lookup"><span data-stu-id="7b770-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="7b770-131">No mostramos el recurso de presentación porque depende en gran medida del tiempo de uso del dispositivo y de la configuración de brillo de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="7b770-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="7b770-132">Seleccione los listados de la columna **Detalles** para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7b770-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="7b770-133">Optimización de batería</span><span class="sxs-lookup"><span data-stu-id="7b770-133">Battery optimization</span></span>

<span data-ttu-id="7b770-134">Windows 10 ofrece numerosas [configuraciones de dispositivos](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) para mejorar el uso de energía y aumentar la duración de la batería de los Escritorio administrado de Microsoft dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7b770-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="7b770-135">Algunas de estas opciones pueden disminuir otras funciones Windows, por lo que también tendrás que tener en cuenta otros factores, como el rol del dispositivo en tu organización.</span><span class="sxs-lookup"><span data-stu-id="7b770-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="7b770-136">Windows soporte técnico mantiene una lista de estas sugerencias [de ahorro de batería.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="7b770-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="7b770-137">Los usuarios pueden ajustar algunas configuraciones por su cuenta sin necesidad de elevación de administrador o soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="7b770-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="7b770-138">Otras opciones requieren soporte técnico del administrador de TI de la organización.</span><span class="sxs-lookup"><span data-stu-id="7b770-138">Other settings require support from your organization's IT administrator.</span></span>
