---
title: Corregir sensores incorrectos en Microsoft Defender para endpoint
description: Corrige los sensores de dispositivo que se informan como mal configurados o inactivos para que el servicio reciba datos del dispositivo.
keywords: mal configurado, inactivo, sensor de corrección, estado del sensor, sin datos del sensor, datos del sensor, comunicaciones deficientes, comunicación
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: c4cdc80170b49a111f476d2d17222c41e2b5c55f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935370"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="92880-104">Corregir sensores incorrectos en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="92880-104">Fix unhealthy sensors in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="92880-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="92880-105">**Applies to:**</span></span>
- [<span data-ttu-id="92880-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="92880-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="92880-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="92880-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="92880-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="92880-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="92880-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="92880-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

<span data-ttu-id="92880-110">Los dispositivos que se clasifican como mal configurados o inactivos se pueden marcar debido a distintas causas.</span><span class="sxs-lookup"><span data-stu-id="92880-110">Devices that are categorized as misconfigured or inactive can be flagged due to varying causes.</span></span> <span data-ttu-id="92880-111">En esta sección se proporcionan algunas explicaciones sobre lo que podría haber provocado que un dispositivo se clasificara como inactivo o mal configurado.</span><span class="sxs-lookup"><span data-stu-id="92880-111">This section provides some explanations as to what might have caused a device to be categorized as inactive or misconfigured.</span></span>

## <a name="inactive-devices"></a><span data-ttu-id="92880-112">Dispositivos inactivos</span><span class="sxs-lookup"><span data-stu-id="92880-112">Inactive devices</span></span>

<span data-ttu-id="92880-113">Un dispositivo inactivo no está marcado necesariamente debido a un problema.</span><span class="sxs-lookup"><span data-stu-id="92880-113">An inactive device is not necessarily flagged due to an issue.</span></span> <span data-ttu-id="92880-114">Las siguientes acciones realizadas en un dispositivo pueden hacer que un dispositivo se clasifice como inactivo:</span><span class="sxs-lookup"><span data-stu-id="92880-114">The following actions taken on a device can cause a device to be categorized as inactive:</span></span>

### <a name="device-is-not-in-use"></a><span data-ttu-id="92880-115">El dispositivo no está en uso</span><span class="sxs-lookup"><span data-stu-id="92880-115">Device is not in use</span></span>

<span data-ttu-id="92880-116">Si el dispositivo no se ha utilizado durante más de siete días por cualquier motivo, permanecerá en estado "Inactivo" en el portal.</span><span class="sxs-lookup"><span data-stu-id="92880-116">If the device has not been in use for more than seven days for any reason, it will remain in an ‘Inactive’ status in the portal.</span></span>

### <a name="device-was-reinstalled-or-renamed"></a><span data-ttu-id="92880-117">El dispositivo se reinstaló o cambió el nombre</span><span class="sxs-lookup"><span data-stu-id="92880-117">Device was reinstalled or renamed</span></span>
<span data-ttu-id="92880-118">Un dispositivo reinstalado o cambiado de nombre generará una nueva entidad de dispositivo en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="92880-118">A reinstalled or renamed device will generate a new device entity in Microsoft Defender Security Center.</span></span> <span data-ttu-id="92880-119">La entidad de dispositivo anterior permanecerá con el estado "Inactivo" en el portal.</span><span class="sxs-lookup"><span data-stu-id="92880-119">The previous device entity will remain with an ‘Inactive’ status in the portal.</span></span> <span data-ttu-id="92880-120">Si reinstalaste un dispositivo e implementaste el paquete Defender for Endpoint, busca el nuevo nombre del dispositivo para comprobar que el dispositivo está informando normalmente.</span><span class="sxs-lookup"><span data-stu-id="92880-120">If you reinstalled a device and deployed the Defender for Endpoint package, search for the new device name to verify that the device is reporting normally.</span></span>

### <a name="device-was-offboarded"></a><span data-ttu-id="92880-121">El dispositivo se ha desactivado</span><span class="sxs-lookup"><span data-stu-id="92880-121">Device was offboarded</span></span>
<span data-ttu-id="92880-122">Si el dispositivo se ha desactivado, seguirá apareciendo en la lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="92880-122">If the device was offboarded, it will still appear in devices list.</span></span> <span data-ttu-id="92880-123">Después de siete días, el estado de mantenimiento del dispositivo debe cambiar a inactivo.</span><span class="sxs-lookup"><span data-stu-id="92880-123">After seven days, the device health state should change to inactive.</span></span>

### <a name="device-is-not-sending-signals"></a><span data-ttu-id="92880-124">El dispositivo no envía señales</span><span class="sxs-lookup"><span data-stu-id="92880-124">Device is not sending signals</span></span>
<span data-ttu-id="92880-125">Si el dispositivo no envía señales durante más de siete días a ninguno de los canales de Microsoft Defender para Endpoint por cualquier motivo, incluidas las condiciones que se incluyen en la clasificación de dispositivos mal configurados, un dispositivo puede considerarse inactivo.</span><span class="sxs-lookup"><span data-stu-id="92880-125">If the device is not sending any signals for more than seven days to any of the Microsoft Defender for Endpoint channels for any reason including conditions that fall under misconfigured devices classification, a device can be considered inactive.</span></span> 

<span data-ttu-id="92880-126">¿Esperas que un dispositivo esté en estado "Activo"?</span><span class="sxs-lookup"><span data-stu-id="92880-126">Do you expect a device to be in ‘Active’ status?</span></span> <span data-ttu-id="92880-127">[Abra un vale de soporte](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)técnico .</span><span class="sxs-lookup"><span data-stu-id="92880-127">[Open a support ticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span></span>

## <a name="misconfigured-devices"></a><span data-ttu-id="92880-128">Dispositivos mal configurados</span><span class="sxs-lookup"><span data-stu-id="92880-128">Misconfigured devices</span></span>
<span data-ttu-id="92880-129">Los dispositivos mal configurados se pueden clasificar en:</span><span class="sxs-lookup"><span data-stu-id="92880-129">Misconfigured devices can further be classified to:</span></span>
- <span data-ttu-id="92880-130">Comunicaciones deficientes</span><span class="sxs-lookup"><span data-stu-id="92880-130">Impaired communications</span></span>
- <span data-ttu-id="92880-131">Sin datos del sensor</span><span class="sxs-lookup"><span data-stu-id="92880-131">No sensor data</span></span>

### <a name="impaired-communications"></a><span data-ttu-id="92880-132">Comunicaciones deficientes</span><span class="sxs-lookup"><span data-stu-id="92880-132">Impaired communications</span></span>
<span data-ttu-id="92880-133">Este estado indica que hay una comunicación limitada entre el dispositivo y el servicio.</span><span class="sxs-lookup"><span data-stu-id="92880-133">This status indicates that there's limited communication between the device and the service.</span></span>

<span data-ttu-id="92880-134">Las siguientes acciones sugeridas pueden ayudar a solucionar problemas relacionados con un dispositivo mal configurado con comunicaciones deficientes:</span><span class="sxs-lookup"><span data-stu-id="92880-134">The following suggested actions can help fix issues related to a misconfigured device with impaired communications:</span></span>

- [<span data-ttu-id="92880-135">Asegurarse de que el dispositivo tiene conexión a Internet</span><span class="sxs-lookup"><span data-stu-id="92880-135">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="92880-136">El sensor de Microsoft Defender para punto de conexión requiere HTTP de Microsoft Windows (WinHTTP) para informar los datos del sensor y comunicarse con el servicio Microsoft Defender para punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="92880-136">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="92880-137">Comprobar la conectividad del cliente a Microsoft Defender para las direcciones URL del servicio endpoint</span><span class="sxs-lookup"><span data-stu-id="92880-137">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="92880-138">Compruebe que la configuración de proxy se haya completado correctamente, que WinHTTP pueda detectar y comunicarse a través del servidor proxy de su entorno y que el servidor proxy permita el tráfico a las direcciones URL del servicio de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="92880-138">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

<span data-ttu-id="92880-139">Si has tomado medidas correctivas y el estado del dispositivo sigue mal configurado, [abre un vale de soporte técnico.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="92880-139">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

### <a name="no-sensor-data"></a><span data-ttu-id="92880-140">Sin datos del sensor</span><span class="sxs-lookup"><span data-stu-id="92880-140">No sensor data</span></span>
<span data-ttu-id="92880-141">Un dispositivo mal configurado con el estado "Sin datos de sensor" tiene comunicación con el servicio, pero solo puede informar de datos parciales del sensor.</span><span class="sxs-lookup"><span data-stu-id="92880-141">A misconfigured device with status ‘No sensor data’ has communication with the service but can only report partial sensor data.</span></span>
<span data-ttu-id="92880-142">Siga estas acciones para corregir problemas conocidos relacionados con un dispositivo mal configurado con el estado "Sin datos de sensor":</span><span class="sxs-lookup"><span data-stu-id="92880-142">Follow theses actions to correct known issues related to a misconfigured device with status ‘No sensor data’:</span></span>

- [<span data-ttu-id="92880-143">Asegurarse de que el dispositivo tiene conexión a Internet</span><span class="sxs-lookup"><span data-stu-id="92880-143">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="92880-144">El sensor de Microsoft Defender para punto de conexión requiere HTTP de Microsoft Windows (WinHTTP) para informar los datos del sensor y comunicarse con el servicio Microsoft Defender para punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="92880-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="92880-145">Comprobar la conectividad del cliente a Microsoft Defender para las direcciones URL del servicio endpoint</span><span class="sxs-lookup"><span data-stu-id="92880-145">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="92880-146">Compruebe que la configuración de proxy se haya completado correctamente, que WinHTTP pueda detectar y comunicarse a través del servidor proxy de su entorno y que el servidor proxy permita el tráfico a las direcciones URL del servicio de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="92880-146">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

- [<span data-ttu-id="92880-147">Asegurarse de que el servicio de datos de diagnóstico está habilitado</span><span class="sxs-lookup"><span data-stu-id="92880-147">Ensure the diagnostic data service is enabled</span></span>](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
<span data-ttu-id="92880-148">Si los dispositivos no están informando correctamente, es posible que deba comprobar que el servicio de datos de diagnóstico de Windows 10 está configurado para iniciarse automáticamente y se está ejecutando en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="92880-148">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the endpoint.</span></span>

- [<span data-ttu-id="92880-149">Asegúrese de que el Antivirus de Microsoft Defender no está deshabilitado por la directiva</span><span class="sxs-lookup"><span data-stu-id="92880-149">Ensure that Microsoft Defender Antivirus is not disabled by policy</span></span>](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
<span data-ttu-id="92880-150">Si los dispositivos ejecutan un cliente antimalware de terceros, el agente de Defender for Endpoint necesita que se habilite el controlador antimalware de inicio anticipado (ELAM) de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="92880-150">If your devices are running a third-party antimalware client, the Defender for Endpoint agent needs the Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver to be enabled.</span></span>

<span data-ttu-id="92880-151">Si has tomado medidas correctivas y el estado del dispositivo sigue mal configurado, [abre un vale de soporte técnico.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="92880-151">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

## <a name="see-also"></a><span data-ttu-id="92880-152">Ver también</span><span class="sxs-lookup"><span data-stu-id="92880-152">See also</span></span>
- [<span data-ttu-id="92880-153">Comprobar el estado del sensor en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="92880-153">Check sensor health state in Microsoft Defender for Endpoint</span></span>](check-sensor-status.md)
