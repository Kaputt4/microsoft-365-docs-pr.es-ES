---
title: Comprobar el estado de mantenimiento del sensor en Microsoft Defender para endpoint
description: Compruebe el estado del sensor en los dispositivos para identificar cuáles están mal configurados, inactivos o no están informando datos del sensor.
keywords: sensor, estado del sensor, mal configurado, inactivo, sin datos de sensor, datos de sensor, comunicaciones deficientes, comunicación
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904169"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8c788-104">Comprobar el estado del sensor en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="8c788-104">Check sensor health state in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c788-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8c788-105">**Applies to:**</span></span>
- [<span data-ttu-id="8c788-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="8c788-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8c788-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c788-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8c788-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8c788-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8c788-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="8c788-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

<span data-ttu-id="8c788-110">El **icono Dispositivos con problemas de sensor** se encuentra en el panel Operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8c788-110">The **Devices with sensor issues** tile is found on the Security Operations dashboard.</span></span> <span data-ttu-id="8c788-111">Este icono proporciona información sobre la capacidad del dispositivo individual para proporcionar datos del sensor y comunicarse con el servicio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8c788-111">This tile provides information on the individual device’s ability to provide sensor data and communicate with the Defender for Endpoint service.</span></span> <span data-ttu-id="8c788-112">Informa de cuántos dispositivos requieren atención y le ayuda a identificar dispositivos problemáticos y a tomar medidas para corregir problemas conocidos.</span><span class="sxs-lookup"><span data-stu-id="8c788-112">It reports how many devices require attention and helps you identify problematic devices and take action to correct known issues.</span></span>

<span data-ttu-id="8c788-113">Hay dos indicadores de estado en el icono que proporcionan información sobre el número de dispositivos que no están informando correctamente al servicio:</span><span class="sxs-lookup"><span data-stu-id="8c788-113">There are two status indicators on the tile that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="8c788-114">**Mal configurados:** estos dispositivos podrían estar informando parcialmente los datos del sensor al servicio Defender for Endpoint y podrían tener errores de configuración que deben corregirse.</span><span class="sxs-lookup"><span data-stu-id="8c788-114">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="8c788-115">**Inactivo:** dispositivos que han dejado de informar al servicio Defender for Endpoint durante más de siete días en el último mes.</span><span class="sxs-lookup"><span data-stu-id="8c788-115">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="8c788-116">Hacer clic en cualquiera de los grupos te dirige a **la lista Dispositivos,** filtrada según tu elección.</span><span class="sxs-lookup"><span data-stu-id="8c788-116">Clicking any of the groups directs you to **Devices list**, filtered according to your choice.</span></span>

![Captura de pantalla de dispositivos con icono de problemas de sensor](images/atp-devices-with-sensor-issues-tile.png)

<span data-ttu-id="8c788-118">En **la lista dispositivos,** puede filtrar la lista de estado de mantenimiento por el siguiente estado:</span><span class="sxs-lookup"><span data-stu-id="8c788-118">On **Devices list**, you can filter the health state list by the following status:</span></span>
- <span data-ttu-id="8c788-119">**Activo:** dispositivos que están informando activamente al servicio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8c788-119">**Active** - Devices that are actively reporting to the Defender for Endpoint service.</span></span>
- <span data-ttu-id="8c788-120">**Mal configurado: estos** dispositivos pueden estar informando parcialmente los datos del sensor al servicio defender para endpoints, pero tienen errores de configuración que deben corregirse.</span><span class="sxs-lookup"><span data-stu-id="8c788-120">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service but have configuration errors that need to be corrected.</span></span> <span data-ttu-id="8c788-121">Los dispositivos mal configurados pueden tener uno o una combinación de los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="8c788-121">Misconfigured devices can have either one or a combination of the following issues:</span></span>
  - <span data-ttu-id="8c788-122">**Sin datos de sensor:** los dispositivos han dejado de enviar datos del sensor.</span><span class="sxs-lookup"><span data-stu-id="8c788-122">**No sensor data** - Devices has stopped sending sensor data.</span></span> <span data-ttu-id="8c788-123">Las alertas limitadas se pueden desencadenar desde el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c788-123">Limited alerts can be triggered from the device.</span></span>
  - <span data-ttu-id="8c788-124">**Comunicaciones deficientes:** la capacidad de comunicarse con el dispositivo se ve afectada.</span><span class="sxs-lookup"><span data-stu-id="8c788-124">**Impaired communications** - Ability to communicate with device is impaired.</span></span> <span data-ttu-id="8c788-125">Es posible que el envío de archivos para un análisis profundo, el bloqueo de archivos, el aislamiento del dispositivo de la red y otras acciones que requieran comunicación con el dispositivo no funcionen.</span><span class="sxs-lookup"><span data-stu-id="8c788-125">Sending files for deep analysis, blocking files, isolating device from network and other actions that require communication with the device may not work.</span></span>
- <span data-ttu-id="8c788-126">**Inactivo:** dispositivos que han dejado de informar al servicio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8c788-126">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service.</span></span>

<span data-ttu-id="8c788-127">También puede descargar toda la lista en formato CSV mediante la **característica** Exportar.</span><span class="sxs-lookup"><span data-stu-id="8c788-127">You can also download the entire list in CSV format using the **Export** feature.</span></span> <span data-ttu-id="8c788-128">Para obtener más información sobre los filtros, [vea Ver y organizar la lista Dispositivos](machines-view-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8c788-128">For more information on filters, see [View and organize the Devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="8c788-129">Exporte la lista en formato CSV para mostrar los datos sin filtrar.</span><span class="sxs-lookup"><span data-stu-id="8c788-129">Export the list in CSV format to display the unfiltered data.</span></span> <span data-ttu-id="8c788-130">El archivo CSV incluirá todos los dispositivos de la organización, independientemente de cualquier filtrado aplicado en la vista en sí y puede tardar una cantidad significativa de tiempo en descargarse, según el tamaño de la organización.</span><span class="sxs-lookup"><span data-stu-id="8c788-130">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself and can take a significant amount of time to download, depending on how large your organization is.</span></span>

![Captura de pantalla de la página de lista Dispositivos](images/atp-devices-list-page.png)

<span data-ttu-id="8c788-132">Puedes ver los detalles del dispositivo al hacer clic en un dispositivo mal configurado o inactivo.</span><span class="sxs-lookup"><span data-stu-id="8c788-132">You can view the device details when you click on a misconfigured or inactive device.</span></span>

## <a name="related-topic"></a><span data-ttu-id="8c788-133">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="8c788-133">Related topic</span></span>
- [<span data-ttu-id="8c788-134">Corregir sensores incorrectos en Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8c788-134">Fix unhealthy sensors in Defender for Endpoint</span></span>](fix-unhealthy-sensors.md)
