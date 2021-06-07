---
title: Proteger los datos de la organización con el control de dispositivos
description: Supervisar la seguridad de datos de la organización a través de informes de control de dispositivos.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 47eb80af58c948db5997dc9f5edfa5737a796837
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772370"
---
# <a name="protect-your-organizations-data-with-device-control"></a><span data-ttu-id="004f8-103">Proteger los datos de la organización con el control de dispositivos</span><span class="sxs-lookup"><span data-stu-id="004f8-103">Protect your organization’s data with device control</span></span>

<span data-ttu-id="004f8-104">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span><span class="sxs-lookup"><span data-stu-id="004f8-104">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span></span>

<span data-ttu-id="004f8-105">El control de dispositivos de Microsoft Defender para endpoints protege contra la pérdida de datos mediante la supervisión y el control del uso de medios por parte de los dispositivos de la organización, como el uso de dispositivos de almacenamiento extraíbles y unidades USB.</span><span class="sxs-lookup"><span data-stu-id="004f8-105">Microsoft Defender for Endpoint device control protects against data loss, by monitoring and controlling media use by devices in your organization, such as the use of removable storage devices and USB drives.</span></span>

<span data-ttu-id="004f8-106">Con el informe de control de dispositivos, puedes ver eventos relacionados con el uso de medios, como:</span><span class="sxs-lookup"><span data-stu-id="004f8-106">With the device control report, you can view events that relate to media usage, such as:</span></span>

- <span data-ttu-id="004f8-107">**Eventos de auditoría:** Muestra el número de eventos de auditoría que se producen cuando se conectan medios externos.</span><span class="sxs-lookup"><span data-stu-id="004f8-107">**Audit events:** Shows the number of audit events that occur when external media is connected.</span></span>
- <span data-ttu-id="004f8-108">**Eventos de directiva:** Muestra el número de eventos de directiva que se producen cuando se desencadena una directiva de control de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="004f8-108">**Policy events:** Shows the number of policy events that occur when a device control policy is triggered.</span></span>

> [!NOTE]
> <span data-ttu-id="004f8-109">El evento de auditoría para realizar un seguimiento del uso de medios está habilitado de forma predeterminada para los dispositivos incorporados a Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="004f8-109">The audit event to track media usage is enabled by default for devices onboarded to Microsoft Defender for Endpoint.</span></span>

## <a name="understanding-the-audit-events"></a><span data-ttu-id="004f8-110">Descripción de los eventos de auditoría</span><span class="sxs-lookup"><span data-stu-id="004f8-110">Understanding the audit events</span></span>

<span data-ttu-id="004f8-111">Los eventos de auditoría incluyen:</span><span class="sxs-lookup"><span data-stu-id="004f8-111">The audit events include:</span></span>

- <span data-ttu-id="004f8-112">**Montaje y desmontaje de la unidad USB:** Audite los eventos que se generan cuando se monta o desmonta una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="004f8-112">**USB drive mount and unmount:** Audit events that are generated when a USB drive is mounted or unmounted.</span></span>
- <span data-ttu-id="004f8-113">**PnP:** Los eventos de auditoría plug and play se generan cuando se conecta un almacenamiento extraíble, una impresora o Bluetooth multimedia.</span><span class="sxs-lookup"><span data-stu-id="004f8-113">**PnP:** Plug and Play audit events are generated when removable storage, a printer, or Bluetooth media is connected.</span></span>

## <a name="monitor-device-control-security"></a><span data-ttu-id="004f8-114">Supervisar la seguridad del control de dispositivos</span><span class="sxs-lookup"><span data-stu-id="004f8-114">Monitor device control security</span></span>

<span data-ttu-id="004f8-115">El control de dispositivos en Microsoft Defender para endpoint habilita a los administradores de seguridad con herramientas que les permiten realizar un seguimiento de la seguridad del control de dispositivos de su organización a través de informes.</span><span class="sxs-lookup"><span data-stu-id="004f8-115">Device control in Microsoft Defender for Endpoint empowers security administrators with tools that enable them to track their organization’s device control security through reports.</span></span> <span data-ttu-id="004f8-116">Puedes encontrar el informe de control de dispositivos en el centro de Microsoft 365 de seguridad yendo a **Informes > Protección de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="004f8-116">You can find the device control report in the Microsoft 365 security center by going to **Reports > Device protection**.</span></span>

<span data-ttu-id="004f8-117">La tarjeta de protección de dispositivos del panel **Informes** muestra el número de eventos de auditoría generados por tipo de medio en los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="004f8-117">The Device protection card on the **Reports** dashboard shows the number of audit events generated by media type, over the last 180 days.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="004f8-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span><span class="sxs-lookup"><span data-stu-id="004f8-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span></span>

<span data-ttu-id="004f8-119">El **botón Ver detalles** muestra más datos de uso multimedia en la página del informe de control **de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="004f8-119">The **View details** button shows more media usage data in the **device control report** page.</span></span>

<span data-ttu-id="004f8-120">La página proporciona un panel con un número agregado de eventos por tipo y una lista de eventos.</span><span class="sxs-lookup"><span data-stu-id="004f8-120">The page provides a dashboard with aggregated number of events per type and a list of events.</span></span> <span data-ttu-id="004f8-121">Los administradores pueden filtrar por intervalo de tiempo, nombre de clase multimedia e identificador de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="004f8-121">Administrators can filter on time range, media class name, and device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="004f8-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span><span class="sxs-lookup"><span data-stu-id="004f8-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span></span>

<span data-ttu-id="004f8-123">Al seleccionar un evento, aparece un flyout que muestra más información:</span><span class="sxs-lookup"><span data-stu-id="004f8-123">When you select an event, a flyout appears that shows you more information:</span></span>

- <span data-ttu-id="004f8-124">**Detalles generales:** Fecha, modo acción y directiva de este evento.</span><span class="sxs-lookup"><span data-stu-id="004f8-124">**General details:** Date, Action mode, and the policy of this event.</span></span>
- <span data-ttu-id="004f8-125">**Información multimedia:** La información multimedia incluye Nombre de medios, Nombre de clase, GUID de clase, Id. de dispositivo, Id. de proveedor, Volumen, Número de serie y Tipo de bus.</span><span class="sxs-lookup"><span data-stu-id="004f8-125">**Media information:** Media information includes Media name, Class name, Class GUID, Device ID, Vendor ID, Volume, Serial number, and Bus type.</span></span>
- <span data-ttu-id="004f8-126">**Detalles de ubicación:** Nombre del dispositivo y MDATP id. del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="004f8-126">**Location details:** Device name and MDATP device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="004f8-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span><span class="sxs-lookup"><span data-stu-id="004f8-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span></span>

<span data-ttu-id="004f8-128">Para ver la actividad en tiempo real de este medio en toda la organización, seleccione el **botón Abrir búsqueda** avanzada.</span><span class="sxs-lookup"><span data-stu-id="004f8-128">To see real-time activity for this media across the organization, select the **Open Advanced hunting** button.</span></span> <span data-ttu-id="004f8-129">Esto incluye una consulta incrustada y predefinida.</span><span class="sxs-lookup"><span data-stu-id="004f8-129">This includes an embedded, pre-defined query.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="004f8-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span><span class="sxs-lookup"><span data-stu-id="004f8-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span></span>

<span data-ttu-id="004f8-131">Para ver la seguridad del dispositivo, selecciona el botón **Abrir página del** dispositivo en el control desplegable.</span><span class="sxs-lookup"><span data-stu-id="004f8-131">To see the security of the device, select the **Open device page** button on the flyout.</span></span> <span data-ttu-id="004f8-132">Este botón abre la página de entidad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="004f8-132">This button opens the device entity page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="004f8-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span><span class="sxs-lookup"><span data-stu-id="004f8-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span></span>

## <a name="reporting-delays"></a><span data-ttu-id="004f8-134">Retrasos en la presentación de informes</span><span class="sxs-lookup"><span data-stu-id="004f8-134">Reporting delays</span></span>

<span data-ttu-id="004f8-135">El informe de control de dispositivos puede tener un retraso de 12 horas desde el momento en que se produce una conexión multimedia hasta el momento en que el evento se refleja en la tarjeta o en la lista de dominios.</span><span class="sxs-lookup"><span data-stu-id="004f8-135">The device control report can have a 12-hour delay from the time a media connection occurs to the time the event is reflected in the card or in the domain list.</span></span>
