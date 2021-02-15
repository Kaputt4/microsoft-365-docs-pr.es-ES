---
title: Información de actualización de seguridad de Windows
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941446"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="0ea06-103">Información de actualización de seguridad de Windows</span><span class="sxs-lookup"><span data-stu-id="0ea06-103">Windows security update insights</span></span>
<span data-ttu-id="0ea06-104">En esta vista se proporciona información general sobre el estado de las actualizaciones de seguridad de los dispositivos de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ea06-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="0ea06-105">Para ver los datos de uso, selecciona la pestaña <strong>Actualizaciones de seguridad de Windows.</strong></span><span class="sxs-lookup"><span data-stu-id="0ea06-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Panel de actualizaciones de seguridad de Windows: gráficos de barras del estado del dispositivo y la versión de actualización en la columna izquierda, el progreso de la implementación de actualización a lo largo del tiempo en la columna central y el porcentaje de dispositivos activos por grupo de implementación, así como el número de días que se han necesitado para alcanzar el objetivo de implementación del 95 % en la columna derecha.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="0ea06-107">Estado del dispositivo</span><span class="sxs-lookup"><span data-stu-id="0ea06-107">Device status</span></span>

<span data-ttu-id="0ea06-108">Para que Windows Update actualice los dispositivos, deben estar conectados a Internet y no hibernarse durante un mínimo de seis horas, dos de las cuales deben ser continuas.</span><span class="sxs-lookup"><span data-stu-id="0ea06-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="0ea06-109">Aunque es posible que se actualice un dispositivo que no cumpla estos requisitos, los dispositivos que los cumplan tienen la mayor probabilidad de actualizarse.</span><span class="sxs-lookup"><span data-stu-id="0ea06-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="0ea06-110">Categorizamos la actividad del dispositivo en el contexto de Windows Update con estos términos:</span><span class="sxs-lookup"><span data-stu-id="0ea06-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="0ea06-111"><strong>Activo:</strong> Dispositivos que cumplen los criterios mínimos de actividad (seis horas, dos continuas) para la versión de actualización de seguridad más reciente y que se han registrado con Microsoft Intune al menos cada cinco días</span><span class="sxs-lookup"><span data-stu-id="0ea06-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="0ea06-112"><strong>Sincronizado:</strong> Dispositivos que se han registrado con Intune en los últimos 28 días</span><span class="sxs-lookup"><span data-stu-id="0ea06-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="0ea06-113"><strong>Sin sincronización:</strong> Dispositivos que <i>no se</i> han registrado con Intune en los últimos 28 días</span><span class="sxs-lookup"><span data-stu-id="0ea06-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="0ea06-114">Actualizar el estado de la versión</span><span class="sxs-lookup"><span data-stu-id="0ea06-114">Update version status</span></span>

<span data-ttu-id="0ea06-115">Microsoft publica actualizaciones de seguridad cada segundo martes del mes.</span><span class="sxs-lookup"><span data-stu-id="0ea06-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="0ea06-116">Cada versión agrega actualizaciones importantes para vulnerabilidades de seguridad conocidas.</span><span class="sxs-lookup"><span data-stu-id="0ea06-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="0ea06-117">Escritorio administrado de Microsoft garantiza que el 95 % de sus dispositivos administrados se actualicen con la última actualización de seguridad disponible cada mes.</span><span class="sxs-lookup"><span data-stu-id="0ea06-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="0ea06-118">A veces, las actualizaciones de seguridad se lanzan en otros momentos para abordar de forma urgente nuevas amenazas.</span><span class="sxs-lookup"><span data-stu-id="0ea06-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="0ea06-119">Escritorio administrado de Microsoft implementa estas actualizaciones de forma similar.</span><span class="sxs-lookup"><span data-stu-id="0ea06-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="0ea06-120">Categorizamos el estado de las versiones de actualización de seguridad con estos términos:</span><span class="sxs-lookup"><span data-stu-id="0ea06-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="0ea06-121"><strong>Actual:</strong> Dispositivos que ejecutan la actualización publicada en el mes actual</span><span class="sxs-lookup"><span data-stu-id="0ea06-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="0ea06-122"><strong>Anterior:</strong> Dispositivos que ejecutan la actualización que se publicó el mes anterior</span><span class="sxs-lookup"><span data-stu-id="0ea06-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="0ea06-123"><strong>Más antiguo:</strong> Dispositivos que ejecutan cualquier actualización de seguridad publicada antes del mes anterior</span><span class="sxs-lookup"><span data-stu-id="0ea06-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="0ea06-124">Debería ver pocos dispositivos en la categoría Anterior: una población grande o creciente probablemente indica un problema sistémico que debe notificar al Escritorio administrado de Microsoft para que podamos investigar. <strong></strong></span><span class="sxs-lookup"><span data-stu-id="0ea06-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="0ea06-125">Progreso de la implementación</span><span class="sxs-lookup"><span data-stu-id="0ea06-125">Deployment progress</span></span>

<span data-ttu-id="0ea06-126">Al principio de cada ciclo de lanzamiento de actualización de seguridad, Escritorio administrado de Microsoft toma una instantánea de la población del dispositivo y establece su destino de implementación en el 95 % de esa población.</span><span class="sxs-lookup"><span data-stu-id="0ea06-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="0ea06-127">El <strong>área de progreso de</strong> la implementación muestra una tendencia histórica, actualizada diariamente, que hace un seguimiento de la proximidad con la que la implementación de la actualización cumple este objetivo para cada versión.</span><span class="sxs-lookup"><span data-stu-id="0ea06-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="0ea06-128">Este gráfico solo muestra los dispositivos con estado Activo.</span><span class="sxs-lookup"><span data-stu-id="0ea06-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="0ea06-129">Puedes ver estos datos de ciclos de actualización anteriores mediante el menú desplegable de la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="0ea06-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="0ea06-130">El período seleccionado en este menú se aplica a toda la información de toda la página.</span><span class="sxs-lookup"><span data-stu-id="0ea06-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="0ea06-131">El <strong>área De dispositivos activos</strong> actualizados por área de grupo de implementación ofrece una vista diferente mostrando el progreso de la instalación de la actualización para cada uno de los grupos de implementación de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ea06-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="0ea06-132">Los <strong>días para alcanzar el área</strong> de destino muestran el tiempo que se tardó en actualizar el 95 % del número total de dispositivos con la actualización de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="0ea06-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="0ea06-133">Mientras la implementación está en curso, esta área muestra <strong>Aún</strong> actualizando hasta que se alcanza el objetivo del 95 % para la actualización seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0ea06-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="0ea06-134">Área de detalles del dispositivo</span><span class="sxs-lookup"><span data-stu-id="0ea06-134">Device details area</span></span>

<span data-ttu-id="0ea06-135">La parte inferior del panel es una tabla que [](#device-status) muestra información detallada de los dispositivos, incluido el estado del dispositivo y el estado [de la versión de actualización.](#update-version-status)</span><span class="sxs-lookup"><span data-stu-id="0ea06-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="0ea06-136">Puede buscar en esta lista o filtrarla por cualquier valor enumerado.</span><span class="sxs-lookup"><span data-stu-id="0ea06-136">You can search this list or filter it by any listed value.</span></span>


![Tabla de detalles del dispositivo que muestra las columnas para el nombre del dispositivo, el usuario asignado, el estado del dispositivo, la versión de actualización, la versión del sistema operativo y la fecha en que el dispositivo se sincronizó por última vez.](../../media/security-update-insights-device-table-sterile.png)
