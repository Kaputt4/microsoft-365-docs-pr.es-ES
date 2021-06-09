---
title: Informe de cumplimiento y estado del dispositivo en Microsoft Defender para endpoint
description: Realizar un seguimiento de las detecciones de estado de estado del dispositivo, el estado del antivirus, la plataforma del sistema operativo y las Windows 10 con el informe de estado y cumplimiento del dispositivo
keywords: estado de mantenimiento, antivirus, plataforma del sistema operativo, versión de Windows 10, versión, estado, estado
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
ms.openlocfilehash: 35100a4b8bdaee23c427816450e948ced9ed3191
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860296"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="86917-104">Informe de cumplimiento y estado del dispositivo en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="86917-104">Device health and compliance report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="86917-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="86917-105">**Applies to:**</span></span>
- [<span data-ttu-id="86917-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="86917-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="86917-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86917-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="86917-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="86917-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="86917-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="86917-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="86917-110">El informe de estado de dispositivos proporciona información de alto nivel sobre los dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="86917-110">The devices status report provides high-level information about the devices in your organization.</span></span> <span data-ttu-id="86917-111">El informe incluye información de tendencias que muestra el estado de mantenimiento del sensor, el estado del antivirus, las plataformas del sistema operativo y Windows 10 versiones.</span><span class="sxs-lookup"><span data-stu-id="86917-111">The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.</span></span>

<span data-ttu-id="86917-112">El panel está estructurado en dos secciones: ![ Imagen del informe del dispositivo](images/device-reports.png)</span><span class="sxs-lookup"><span data-stu-id="86917-112">The dashboard is structured into two sections: ![Image of the device report](images/device-reports.png)</span></span>
 
<span data-ttu-id="86917-113">Sección</span><span class="sxs-lookup"><span data-stu-id="86917-113">Section</span></span> | <span data-ttu-id="86917-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="86917-114">Description</span></span>
:---|:---
<span data-ttu-id="86917-115">1</span><span class="sxs-lookup"><span data-stu-id="86917-115">1</span></span> | <span data-ttu-id="86917-116">Tendencias de dispositivos</span><span class="sxs-lookup"><span data-stu-id="86917-116">Device trends</span></span>
<span data-ttu-id="86917-117">2</span><span class="sxs-lookup"><span data-stu-id="86917-117">2</span></span> | <span data-ttu-id="86917-118">Resumen del dispositivo (día actual)</span><span class="sxs-lookup"><span data-stu-id="86917-118">Device summary (current day)</span></span>
 
 
## <a name="device-trends"></a><span data-ttu-id="86917-119">Tendencias de dispositivos</span><span class="sxs-lookup"><span data-stu-id="86917-119">Device trends</span></span> 
<span data-ttu-id="86917-120">De forma predeterminada, las tendencias del dispositivo muestran información del dispositivo del período de 30 días que termina en el último día completo.</span><span class="sxs-lookup"><span data-stu-id="86917-120">By default, the device trends displays device information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="86917-121">Para obtener una mejor perspectiva de las tendencias que se producen en su organización, puede ajustar el período de informes ajustando el período de tiempo que se muestra.</span><span class="sxs-lookup"><span data-stu-id="86917-121">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="86917-122">Para ajustar el período de tiempo, seleccione un intervalo de tiempo en las opciones desplegables:</span><span class="sxs-lookup"><span data-stu-id="86917-122">To adjust the time period, select a time range from the drop-down options:</span></span>
 
- <span data-ttu-id="86917-123">30 días</span><span class="sxs-lookup"><span data-stu-id="86917-123">30 days</span></span>
- <span data-ttu-id="86917-124">3 meses</span><span class="sxs-lookup"><span data-stu-id="86917-124">3 months</span></span>
- <span data-ttu-id="86917-125">6 meses</span><span class="sxs-lookup"><span data-stu-id="86917-125">6 months</span></span>
- <span data-ttu-id="86917-126">Personalizado</span><span class="sxs-lookup"><span data-stu-id="86917-126">Custom</span></span>

>[!NOTE]
><span data-ttu-id="86917-127">Estos filtros solo se aplican en la sección de tendencias de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="86917-127">These filters are only applied on the device trends section.</span></span> <span data-ttu-id="86917-128">No afecta a la sección de resumen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="86917-128">It doesn't affect the device summary section.</span></span>

## <a name="device-summary"></a><span data-ttu-id="86917-129">Resumen del dispositivo</span><span class="sxs-lookup"><span data-stu-id="86917-129">Device summary</span></span> 
<span data-ttu-id="86917-130">Aunque las tendencias de dispositivos muestran información de dispositivos de tendencia, el resumen del dispositivo muestra información del dispositivo en el ámbito del día actual.</span><span class="sxs-lookup"><span data-stu-id="86917-130">While the devices trends shows trending device information, the device summary shows device information scoped to the current day.</span></span> 

>[!NOTE]
><span data-ttu-id="86917-131">Los datos reflejados en la sección de resumen están en el ámbito de 180 días antes de la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="86917-131">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="86917-132">Por ejemplo, si la fecha de hoy es el 27 de marzo de 2019, los datos de la sección de resumen reflejarán números a partir del 28 de septiembre de 2018 al 27 de marzo de 2019.</span><span class="sxs-lookup"><span data-stu-id="86917-132">For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.</span></span><br>
> <span data-ttu-id="86917-133">El filtro aplicado en la sección tendencias no se aplica en la sección de resumen.</span><span class="sxs-lookup"><span data-stu-id="86917-133">The filter applied on the trends section is not applied on the summary section.</span></span> 
 
<span data-ttu-id="86917-134">La sección de tendencias de dispositivos te permite explorar en profundidad la lista de dispositivos con el filtro correspondiente aplicado.</span><span class="sxs-lookup"><span data-stu-id="86917-134">The device trends section allows you to drill down to the devices list with the corresponding filter applied to it.</span></span> <span data-ttu-id="86917-135">Por ejemplo, al hacer clic en la barra Inactiva de la tarjeta de estado estado del sensor, aparecerá la lista de dispositivos con resultados que muestran solo los dispositivos cuyo estado del sensor está inactivo.</span><span class="sxs-lookup"><span data-stu-id="86917-135">For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.</span></span> 
 
 
 
## <a name="device-attributes"></a><span data-ttu-id="86917-136">Atributos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="86917-136">Device attributes</span></span>
<span data-ttu-id="86917-137">El informe está hecho de tarjetas que muestran los siguientes atributos de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="86917-137">The report is made up of cards that display the following device attributes:</span></span>
 
- <span data-ttu-id="86917-138">**Estado de** mantenimiento: muestra información sobre el estado del sensor en los dispositivos, lo que proporciona una vista agregada de los dispositivos que están activos, que experimentan comunicaciones deficientes, inactivos o donde no se ven datos del sensor.</span><span class="sxs-lookup"><span data-stu-id="86917-138">**Health state**: shows information about the sensor state on devices, providing an aggregated view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.</span></span>
  
- <span data-ttu-id="86917-139">**Estado del antivirus para dispositivos Windows 10** activos: muestra el número de dispositivos y el estado de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="86917-139">**Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.</span></span>
    
- <span data-ttu-id="86917-140">**Plataformas del sistema** operativo: muestra la distribución de las plataformas del sistema operativo que existen en la organización.</span><span class="sxs-lookup"><span data-stu-id="86917-140">**OS platforms**: shows the distribution of OS platforms that exists within your organization.</span></span> 
 
- <span data-ttu-id="86917-141">**Windows 10:** muestra la distribución de Windows 10 dispositivos y sus versiones en la organización.</span><span class="sxs-lookup"><span data-stu-id="86917-141">**Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.</span></span>
 
 
 
## <a name="filter-data"></a><span data-ttu-id="86917-142">Filtrar datos</span><span class="sxs-lookup"><span data-stu-id="86917-142">Filter data</span></span>
 
<span data-ttu-id="86917-143">Usa los filtros proporcionados para incluir o excluir dispositivos con determinados atributos.</span><span class="sxs-lookup"><span data-stu-id="86917-143">Use the provided filters to include or exclude devices with certain attributes.</span></span>

<span data-ttu-id="86917-144">Puedes seleccionar varios filtros para aplicar desde los atributos del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="86917-144">You can select multiple filters to apply from the device attributes.</span></span> 
 
>[!NOTE]
><span data-ttu-id="86917-145">Estos filtros se aplican a **todas** las tarjetas del informe.</span><span class="sxs-lookup"><span data-stu-id="86917-145">These filters apply to **all** the cards in the report.</span></span>
 
<span data-ttu-id="86917-146">Por ejemplo, para mostrar datos sobre Windows 10 dispositivos con estado de mantenimiento del sensor activo:</span><span class="sxs-lookup"><span data-stu-id="86917-146">For example, to show data about Windows 10 devices with Active sensor health state:</span></span>
 
1. <span data-ttu-id="86917-147">En **Filtros > Estado de mantenimiento del sensor > Active**.</span><span class="sxs-lookup"><span data-stu-id="86917-147">Under **Filters > Sensor health state > Active**.</span></span>
2. <span data-ttu-id="86917-148">A continuación, seleccione **Plataformas del sistema operativo > Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="86917-148">Then select **OS platforms > Windows 10**.</span></span>
3. <span data-ttu-id="86917-149">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="86917-149">Select **Apply**.</span></span>


## <a name="related-topic"></a><span data-ttu-id="86917-150">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="86917-150">Related topic</span></span>
- [<span data-ttu-id="86917-151">Informe de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="86917-151">Threat protection report</span></span>](threat-protection-reports.md)
