---
title: 'Informe de dispositivos vulnerables: administración de amenazas y vulnerabilidades'
description: Un informe que muestra tendencias de dispositivos vulnerables y estadísticas actuales. El objetivo es que comprendas la respiración y el alcance de la exposición del dispositivo.
keywords: Microsoft Defender para dispositivos vulnerables de Endpoint-tvm, Microsoft Defender para endpoint, tvm, reducir la exposición a la vulnerabilidad & amenazas, reducir la amenaza y la vulnerabilidad, supervisar la configuración de seguridad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4b2b581d570bd0924970a845c66a599495ff9829
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933714"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a><span data-ttu-id="28a08-105">Informe de dispositivos vulnerables: administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="28a08-105">Vulnerable devices report - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="28a08-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="28a08-106">**Applies to:**</span></span>

- [<span data-ttu-id="28a08-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28a08-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="28a08-108">Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="28a08-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="28a08-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28a08-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="28a08-110">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="28a08-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="28a08-111">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="28a08-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="28a08-112">El informe muestra gráficos y gráficos de barras con tendencias de dispositivo vulnerables y estadísticas actuales.</span><span class="sxs-lookup"><span data-stu-id="28a08-112">The report shows graphs and bar charts with vulnerable device trends and current statistics.</span></span> <span data-ttu-id="28a08-113">El objetivo es que comprendas la respiración y el alcance de la exposición del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28a08-113">The goal is for you to understand the breath and scope of your device exposure.</span></span> 

<span data-ttu-id="28a08-114">Para obtener acceso al informe en el Centro de seguridad de Microsoft Defender, vaya **a Informes > dispositivos vulnerables**</span><span class="sxs-lookup"><span data-stu-id="28a08-114">Access the report in the Microsoft Defender Security Center by going to **Reports > Vulnerable devices**</span></span>

<span data-ttu-id="28a08-115">Hay dos columnas:</span><span class="sxs-lookup"><span data-stu-id="28a08-115">There are two columns:</span></span>

- <span data-ttu-id="28a08-116">Tendencias (con el tiempo).</span><span class="sxs-lookup"><span data-stu-id="28a08-116">Trends (over time).</span></span> <span data-ttu-id="28a08-117">Puede mostrar los últimos 30 días, 3 meses, 6 meses o un intervalo de fechas personalizado.</span><span class="sxs-lookup"><span data-stu-id="28a08-117">Can show the past 30 days, 3 months, 6 months, or a custom date range.</span></span>
- <span data-ttu-id="28a08-118">Hoy (información actual)</span><span class="sxs-lookup"><span data-stu-id="28a08-118">Today (current information)</span></span>

<span data-ttu-id="28a08-119">**Filtro:** puedes filtrar los datos por niveles de gravedad de vulnerabilidad, disponibilidad de vulnerabilidad, antigüedad de vulnerabilidad, plataforma del sistema operativo, versión de Windows 10 o grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="28a08-119">**Filter**: You can filter the data by vulnerability severity levels, exploit availability, vulnerability age, operating system platform, Windows 10 version, or device group.</span></span>

<span data-ttu-id="28a08-120">**Explorar en profundidad:** si hay una información que desea explorar más adelante, seleccione el gráfico de barras relevante para ver una lista filtrada de dispositivos en la página Inventario de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="28a08-120">**Drill down**: If there is an insight you want to explore further, select the relevant bar chart to view a filtered list of devices in the Device inventory page.</span></span> <span data-ttu-id="28a08-121">Desde allí, puede exportar la lista.</span><span class="sxs-lookup"><span data-stu-id="28a08-121">From there, you can export the list.</span></span>

## <a name="severity-level-graphs"></a><span data-ttu-id="28a08-122">Gráficos de nivel de gravedad</span><span class="sxs-lookup"><span data-stu-id="28a08-122">Severity level graphs</span></span>

<span data-ttu-id="28a08-123">Cada dispositivo se cuenta solo una vez de acuerdo con la vulnerabilidad más grave encontrada en ese dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28a08-123">Each device is counted only once according to the most severe vulnerability found on that device.</span></span>

![Un gráfico de los niveles actuales de gravedad de vulnerabilidad del dispositivo y un gráfico que muestra los niveles con el tiempo.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a><span data-ttu-id="28a08-125">Gráficos de disponibilidad de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="28a08-125">Exploit availability graphs</span></span>

<span data-ttu-id="28a08-126">Cada dispositivo se cuenta solo una vez en función del nivel más alto de vulnerabilidad conocida.</span><span class="sxs-lookup"><span data-stu-id="28a08-126">Each device is counted only once based on the highest level of known exploit.</span></span>

![Un gráfico de disponibilidad actual de vulnerabilidades de seguridad del dispositivo y un gráfico que muestra la disponibilidad con el tiempo.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a><span data-ttu-id="28a08-128">Gráficos de antigüedad de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="28a08-128">Vulnerability age graphs</span></span>

<span data-ttu-id="28a08-129">Cada dispositivo se cuenta solo una vez en la fecha de publicación de vulnerabilidad más antigua.</span><span class="sxs-lookup"><span data-stu-id="28a08-129">Each device is counted only once under the oldest vulnerability publication date.</span></span> <span data-ttu-id="28a08-130">Las vulnerabilidades más antiguas tienen más posibilidades de ser aprovechadas.</span><span class="sxs-lookup"><span data-stu-id="28a08-130">Older vulnerabilities have a higher chance of being exploited.</span></span>

![Un gráfico de la antigüedad de vulnerabilidad del dispositivo actual y un gráfico que muestra la antigüedad con el tiempo.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a><span data-ttu-id="28a08-132">Dispositivos vulnerables por gráficos de plataforma de sistema operativo</span><span class="sxs-lookup"><span data-stu-id="28a08-132">Vulnerable devices by operating system platform graphs</span></span>

<span data-ttu-id="28a08-133">El número de dispositivos en cada sistema operativo que se exponen debido a vulnerabilidades de software.</span><span class="sxs-lookup"><span data-stu-id="28a08-133">The number of devices on each operating system that are exposed due to software vulnerabilities.</span></span>

![Un gráfico de dispositivos vulnerables actuales por plataforma del sistema operativo y un gráfico que muestra los dispositivos vulnerables de las plataformas del sistema operativo a lo largo del tiempo.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a><span data-ttu-id="28a08-135">Dispositivos vulnerables por gráficos de versión de Windows 10</span><span class="sxs-lookup"><span data-stu-id="28a08-135">Vulnerable devices by Windows 10 version graphs</span></span>

<span data-ttu-id="28a08-136">El número de dispositivos en cada versión de Windows 10 que se exponen debido a aplicaciones vulnerables u sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="28a08-136">The number of devices on each Windows 10 version that are exposed due to vulnerable applications or OS.</span></span>

![Un gráfico de dispositivos vulnerables actuales de la versión de Windows 10 y un gráfico que muestra los dispositivos vulnerables de la versión de Windows 10 con el tiempo.](images/tvm-report-version.png)

## <a name="related-topics"></a><span data-ttu-id="28a08-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="28a08-138">Related topics</span></span>

- [<span data-ttu-id="28a08-139">Introducción a la administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="28a08-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="28a08-140">Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="28a08-140">Security recommendations</span></span>](tvm-security-recommendation.md)
