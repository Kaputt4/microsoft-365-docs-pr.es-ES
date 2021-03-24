---
title: Solucionar problemas del servicio de extremo de Microsoft Defender
description: Busque soluciones y soluciones para problemas conocidos, como errores de servidor al intentar obtener acceso al servicio.
keywords: solucionar problemas de microsoft defender para el punto de conexión, solucionar problemas de Windows ATP, error de servidor, acceso denegado, credenciales no válidas, sin datos, portal de panel, permitir, visor de eventos
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: bd211a56ee9ed6aa871c8d55149247a4755bc863
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072904"
---
# <a name="troubleshoot-service-issues"></a><span data-ttu-id="6194b-104">Solucionar problemas de servicio</span><span class="sxs-lookup"><span data-stu-id="6194b-104">Troubleshoot service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6194b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6194b-105">**Applies to:**</span></span>
- [<span data-ttu-id="6194b-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6194b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="6194b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6194b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6194b-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6194b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6194b-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6194b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="6194b-110">En esta sección se abordan los problemas que pueden surgir al usar el servicio de amenazas avanzadas de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="6194b-110">This section addresses issues that might arise as you use the Microsoft Defender Advanced Threat service.</span></span>

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a><span data-ttu-id="6194b-111">Error del servidor: se deniega el acceso debido a credenciales no válidas</span><span class="sxs-lookup"><span data-stu-id="6194b-111">Server error - Access is denied due to invalid credentials</span></span>
<span data-ttu-id="6194b-112">Si se produce un error de servidor al intentar acceder al servicio, deberá cambiar la configuración de cookies del explorador.</span><span class="sxs-lookup"><span data-stu-id="6194b-112">If you encounter a server error when trying to access the service, you’ll need to change your browser cookie settings.</span></span>
<span data-ttu-id="6194b-113">Configure el explorador para permitir cookies.</span><span class="sxs-lookup"><span data-stu-id="6194b-113">Configure your browser to allow cookies.</span></span>

## <a name="elements-or-data-missing-on-the-portal"></a><span data-ttu-id="6194b-114">Faltan elementos o datos en el portal</span><span class="sxs-lookup"><span data-stu-id="6194b-114">Elements or data missing on the portal</span></span>
<span data-ttu-id="6194b-115">Si faltan algunos elementos o datos de la interfaz de usuario en el Centro de seguridad de Microsoft Defender, es posible que la configuración de proxy lo bloquee.</span><span class="sxs-lookup"><span data-stu-id="6194b-115">If some UI elements or data is missing on Microsoft Defender Security Center it’s possible that proxy settings are blocking it.</span></span>

<span data-ttu-id="6194b-116">Asegúrese de que `*.securitycenter.windows.com` se incluye la lista de proxy permitidos.</span><span class="sxs-lookup"><span data-stu-id="6194b-116">Make sure that `*.securitycenter.windows.com` is included the proxy allow list.</span></span>


> [!NOTE]
> <span data-ttu-id="6194b-117">Debe usar el protocolo HTTPS al agregar los siguientes extremos.</span><span class="sxs-lookup"><span data-stu-id="6194b-117">You must use the HTTPS protocol when adding the following endpoints.</span></span>

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a><span data-ttu-id="6194b-118">El servicio de Microsoft Defender para endpoints muestra registros de eventos o errores en el Visor de eventos</span><span class="sxs-lookup"><span data-stu-id="6194b-118">Microsoft Defender for Endpoint service shows event or error logs in the Event Viewer</span></span>

<span data-ttu-id="6194b-119">Consulte el tema Revisar eventos [y errores](event-error-codes.md) mediante el Visor de eventos para obtener una lista de los IDs de eventos que notifica el servicio De endpoint de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="6194b-119">See the topic [Review events and errors using Event Viewer](event-error-codes.md) for a list of event IDs that are reported by the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="6194b-120">El tema también contiene pasos de solución de problemas para errores de evento.</span><span class="sxs-lookup"><span data-stu-id="6194b-120">The topic also contains troubleshooting steps for event errors.</span></span>

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a><span data-ttu-id="6194b-121">Microsoft Defender para el servicio de extremo no se inicia después de un reinicio y muestra el error 577</span><span class="sxs-lookup"><span data-stu-id="6194b-121">Microsoft Defender for Endpoint service fails to start after a reboot and shows error 577</span></span>

<span data-ttu-id="6194b-122">Si los dispositivos de incorporación se completan correctamente, pero Microsoft Defender para endpoint no se inicia después de un reinicio y muestra el error 577, compruebe que Windows Defender no está deshabilitado por una directiva.</span><span class="sxs-lookup"><span data-stu-id="6194b-122">If onboarding devices successfully completes but Microsoft Defender for Endpoint does not start after a reboot and shows error 577, check that Windows Defender is not disabled by a policy.</span></span>

<span data-ttu-id="6194b-123">Para obtener más información, vea [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="6194b-123">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

## <a name="known-issues-with-regional-formats"></a><span data-ttu-id="6194b-124">Problemas conocidos con formatos regionales</span><span class="sxs-lookup"><span data-stu-id="6194b-124">Known issues with regional formats</span></span>

<span data-ttu-id="6194b-125">**Formatos de fecha y hora**</span><span class="sxs-lookup"><span data-stu-id="6194b-125">**Date and time formats**</span></span><br>
<span data-ttu-id="6194b-126">Hay algunos problemas conocidos con los formatos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="6194b-126">There are some known issues with the time and date formats.</span></span> 

<span data-ttu-id="6194b-127">Se admiten los siguientes formatos de fecha:</span><span class="sxs-lookup"><span data-stu-id="6194b-127">The following date formats are supported:</span></span>
- <span data-ttu-id="6194b-128">MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="6194b-128">MM/dd/yyyy</span></span>
- <span data-ttu-id="6194b-129">dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="6194b-129">dd/MM/yyyy</span></span>

<span data-ttu-id="6194b-130">Actualmente no se admiten los siguientes formatos de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="6194b-130">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="6194b-131">Formato de fechayyy/MM/dd</span><span class="sxs-lookup"><span data-stu-id="6194b-131">Date format yyyy/MM/dd</span></span>
- <span data-ttu-id="6194b-132">Formato de fecha dd/MM/aa</span><span class="sxs-lookup"><span data-stu-id="6194b-132">Date format dd/MM/yy</span></span>
- <span data-ttu-id="6194b-133">Formato de fecha con yy.</span><span class="sxs-lookup"><span data-stu-id="6194b-133">Date format with yy.</span></span> <span data-ttu-id="6194b-134">Solo se mostrará yyyy.</span><span class="sxs-lookup"><span data-stu-id="6194b-134">Will only show yyyy.</span></span>
- <span data-ttu-id="6194b-135">No se admite el formato de hora HH:mm:ss (no se admite el formato de 12 horas a.m./pm).</span><span class="sxs-lookup"><span data-stu-id="6194b-135">Time format HH:mm:ss is not supported (the 12 hour AM/PM format is not supported).</span></span> <span data-ttu-id="6194b-136">Solo se admite el formato de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="6194b-136">Only the 24-hour format is supported.</span></span>

<span data-ttu-id="6194b-137">**Uso de comas para indicar miles**</span><span class="sxs-lookup"><span data-stu-id="6194b-137">**Use of comma to indicate thousand**</span></span><br>
<span data-ttu-id="6194b-138">No se admite el uso de comas como separador en números.</span><span class="sxs-lookup"><span data-stu-id="6194b-138">Support of use of comma as a separator in numbers are not supported.</span></span> <span data-ttu-id="6194b-139">Las regiones donde un número está separado con una coma para indicar mil, solo verán el uso de un punto como separador.</span><span class="sxs-lookup"><span data-stu-id="6194b-139">Regions where a number is separated with a comma to indicate a thousand, will only see the use of a dot as a separator.</span></span> <span data-ttu-id="6194b-140">Por ejemplo, 15,5K se muestra como 15,5K.</span><span class="sxs-lookup"><span data-stu-id="6194b-140">For example, 15,5K is displayed as 15.5K.</span></span>

><span data-ttu-id="6194b-141">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="6194b-141">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6194b-142">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6194b-142">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a><span data-ttu-id="6194b-143">El inquilino de Microsoft Defender para endpoint se creó automáticamente en Europa</span><span class="sxs-lookup"><span data-stu-id="6194b-143">Microsoft Defender for Endpoint tenant was automatically created in Europe</span></span>
<span data-ttu-id="6194b-144">Cuando usa Azure Security Center para supervisar los servidores, se crea automáticamente un inquilino de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="6194b-144">When you use Azure Security Center to monitor servers, a Microsoft Defender for Endpoint tenant is automatically created.</span></span> <span data-ttu-id="6194b-145">Los datos de Microsoft Defender para endpoint se almacenan en Europa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6194b-145">The Microsoft Defender for Endpoint data is stored in Europe by default.</span></span>





## <a name="related-topics"></a><span data-ttu-id="6194b-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6194b-146">Related topics</span></span>
- [<span data-ttu-id="6194b-147">Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6194b-147">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
- [<span data-ttu-id="6194b-148">Revisar eventos y errores con el Visor de eventos</span><span class="sxs-lookup"><span data-stu-id="6194b-148">Review events and errors using Event Viewer</span></span>](event-error-codes.md)
