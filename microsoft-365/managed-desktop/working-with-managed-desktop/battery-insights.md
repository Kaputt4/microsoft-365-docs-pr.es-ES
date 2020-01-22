---
title: Información sobre las baterías
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b14ef9970aa709ad5e23fdae467992497a1331e8
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260165"
---
# <a name="battery-insights"></a><span data-ttu-id="ee30b-103">Información sobre las baterías</span><span class="sxs-lookup"><span data-stu-id="ee30b-103">Battery insights</span></span>
<span data-ttu-id="ee30b-104">Esta vista proporciona métricas de uso de energía, batería y aplicaciones para los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ee30b-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ee30b-105">Por estos motivos, una aplicación se considera "en uso" si está en ejecución y en enfoque.</span><span class="sxs-lookup"><span data-stu-id="ee30b-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="ee30b-106">Para ver los datos de uso, seleccione la pestaña **batería** .</span><span class="sxs-lookup"><span data-stu-id="ee30b-106">To view usage data, select the **Battery** tab.</span></span>

![Panel batería: duración prevista de la batería por modelo de dispositivo en la parte superior izquierda y los principales consumidores de energía (por aplicación) en la parte superior derecha y en la tabla información en la parte inferior.](images/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="ee30b-109">Duración prevista de la batería</span><span class="sxs-lookup"><span data-stu-id="ee30b-109">Predicted battery life</span></span>

<span data-ttu-id="ee30b-110">En el área de duración de la **batería prevista** , proporcionamos predicciones para la duración prevista de la batería de los dispositivos, organizadas por modelo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ee30b-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="ee30b-111">Estos datos se derivan del uso de energía de muestreo, el tiempo de uso y la capacidad de la batería desde una <em>selección</em> aleatoria de los dispositivos en su implementación de escritorio administrada de Microsoft que también son datos de informes.</span><span class="sxs-lookup"><span data-stu-id="ee30b-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="ee30b-112">La tabla proporciona la duración prevista de la batería (en horas), la duración media de la batería para los mismos modelos en otras implementaciones de escritorio administradas por Microsoft y el número de dispositivos que notifican estos datos en el entorno.</span><span class="sxs-lookup"><span data-stu-id="ee30b-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="ee30b-113">Ordene los datos seleccionando los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="ee30b-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="ee30b-114">Principales consumidores de energía</span><span class="sxs-lookup"><span data-stu-id="ee30b-114">Top energy consumers</span></span>

<span data-ttu-id="ee30b-115">En el área de los **principales consumidores de energía** , encontrará las aplicaciones de su entorno que consumen más energía en milliWatt-horas (MWh).</span><span class="sxs-lookup"><span data-stu-id="ee30b-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="ee30b-116">Las aplicaciones que se muestran son por dispositivo específico, que se seleccionan en la sección duración de la **batería de previsiones** a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="ee30b-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="ee30b-117">Por ejemplo, para ver el consumo por aplicación para los dispositivos de la libreta de direcciones 2 de todos, seleccione esa fila en el área duración de la batería.</span><span class="sxs-lookup"><span data-stu-id="ee30b-117">For example, to see the per-app consumption for your Microsft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="ee30b-118">Si no selecciona ningún modelo, los datos de consumo de la aplicación mostrados son para todas las aplicaciones para las que tenemos datos colectivamente.</span><span class="sxs-lookup"><span data-stu-id="ee30b-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="ee30b-119">Para cada aplicación, los segmentos de color muestran la distribución del uso de energía de la aplicación entre estas categorías:</span><span class="sxs-lookup"><span data-stu-id="ee30b-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="ee30b-120">CPU</span><span class="sxs-lookup"><span data-stu-id="ee30b-120">CPU</span></span>
- <span data-ttu-id="ee30b-121">Visualización</span><span class="sxs-lookup"><span data-stu-id="ee30b-121">Display</span></span>
- <span data-ttu-id="ee30b-122">Red</span><span class="sxs-lookup"><span data-stu-id="ee30b-122">Network</span></span>
- <span data-ttu-id="ee30b-123">Otros</span><span class="sxs-lookup"><span data-stu-id="ee30b-123">Other</span></span>

<span data-ttu-id="ee30b-124">"Otros" podrían incluir consumo energético por una variedad de orígenes, como la actividad de disco, el uso de banda ancha móvil y la pérdida de energía de resistencia interna.</span><span class="sxs-lookup"><span data-stu-id="ee30b-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="ee30b-125">Las aplicaciones que se muestran en \* \* principales consumidores de energía</span><span class="sxs-lookup"><span data-stu-id="ee30b-125">The apps displayed in \*\*Top energy consumers"</span></span>

<span data-ttu-id="ee30b-126">Puede filtrar esta vista para mostrar solo las aplicaciones en primer plano, las aplicaciones en segundo plano o ambas mediante el menú de la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="ee30b-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="ee30b-127">Las aplicaciones en primer plano son aquellas en las que se ha producido la interacción del usuario en los últimos 28 días, como seleccionar algo con un mouse (ratón).</span><span class="sxs-lookup"><span data-stu-id="ee30b-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="ee30b-128">Información</span><span class="sxs-lookup"><span data-stu-id="ee30b-128">Insights</span></span>

<span data-ttu-id="ee30b-129">El área de **información** muestra los tres consumidores de energía principales en las categorías CPU y red.</span><span class="sxs-lookup"><span data-stu-id="ee30b-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="ee30b-130">Estos elementos consumen más de una energía media en comparación con todas las implementaciones de escritorio administradas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ee30b-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="ee30b-131">No se muestra el recurso para mostrar porque depende en gran medida del tiempo de uso del dispositivo y la configuración del brillo de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="ee30b-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="ee30b-132">Seleccione los listados en la columna **detalles** para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ee30b-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="ee30b-133">Optimización de la batería</span><span class="sxs-lookup"><span data-stu-id="ee30b-133">Battery optimization</span></span>

<span data-ttu-id="ee30b-134">Windows 10 ofrece varias [Opciones de configuración de dispositivo](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) para mejorar el uso de energía y aumentar la duración de la batería de los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ee30b-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ee30b-135">Algunas de estas opciones de configuración pueden disminuir otras funciones de Windows, por lo que también tendrá que tener en cuenta otros factores, como la función del dispositivo en su organización.</span><span class="sxs-lookup"><span data-stu-id="ee30b-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="ee30b-136">El soporte técnico de Windows mantiene una lista de estas [sugerencias de ahorro de batería](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span><span class="sxs-lookup"><span data-stu-id="ee30b-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="ee30b-137">Los usuarios pueden ajustar algunas opciones de configuración por su cuenta sin necesidad de elevación o soporte administrativo.</span><span class="sxs-lookup"><span data-stu-id="ee30b-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="ee30b-138">Otras opciones requieren la asistencia del administrador de TI de la organización.</span><span class="sxs-lookup"><span data-stu-id="ee30b-138">Other settings require support from your organization's IT administrator.</span></span>
