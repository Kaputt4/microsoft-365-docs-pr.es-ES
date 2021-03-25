---
title: Configuración de zona horaria del Centro de seguridad de Microsoft Defender
description: Usa la información que se incluye aquí para configurar la configuración de zona horaria del Centro de seguridad de Microsoft Defender y ver la información de licencia.
keywords: configuración, Microsoft Defender, inteligencia contra amenazas de ciberseguridad, protección contra amenazas avanzada, zona horaria, utc, hora local, licencia
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
ms.openlocfilehash: c6338155aae3605ac5721958363b8c2d86618d9b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183854"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="cf374-104">Configuración de zona horaria del Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cf374-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cf374-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="cf374-105">**Applies to:**</span></span>
- [<span data-ttu-id="cf374-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="cf374-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cf374-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf374-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)




><span data-ttu-id="cf374-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="cf374-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cf374-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="cf374-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="cf374-110">Use el **icono 1 de** configuración de zona horaria del menú Zona ![ horaria para configurar la zona horaria y ver la información de ](images/atp-time-zone.png) licencia.</span><span class="sxs-lookup"><span data-stu-id="cf374-110">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="cf374-111">Configuración de zona horaria</span><span class="sxs-lookup"><span data-stu-id="cf374-111">Time zone settings</span></span>
<span data-ttu-id="cf374-112">El aspecto del tiempo es importante en la evaluación y el análisis de los ciberataques percibidos y reales.</span><span class="sxs-lookup"><span data-stu-id="cf374-112">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="cf374-113">Las investigaciones ciberforensicas suelen basarse en marcas de tiempo para unir la secuencia de eventos.</span><span class="sxs-lookup"><span data-stu-id="cf374-113">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="cf374-114">Es importante que el sistema refleje la configuración de zona horaria correcta.</span><span class="sxs-lookup"><span data-stu-id="cf374-114">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="cf374-115">Microsoft Defender para endpoint puede mostrar la hora universal coordinada (UTC) o la hora local.</span><span class="sxs-lookup"><span data-stu-id="cf374-115">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="cf374-116">La configuración actual de la zona horaria se muestra en el menú Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="cf374-116">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="cf374-117">Puede cambiar la zona horaria mostrada en el **menú Zona** horaria.</span><span class="sxs-lookup"><span data-stu-id="cf374-117">You can change the displayed time zone in the **Time zone** menu.</span></span>

![Icono de configuración de zona horaria2](images/atp-time-zone-menu.png)<span data-ttu-id="cf374-119">.</span><span class="sxs-lookup"><span data-stu-id="cf374-119">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="cf374-120">Zona horaria UTC</span><span class="sxs-lookup"><span data-stu-id="cf374-120">UTC time zone</span></span>
<span data-ttu-id="cf374-121">Microsoft Defender para endpoint usa la hora UTC de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cf374-121">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="cf374-122">Al establecer la zona horaria de Microsoft Defender para endpoint en UTC, se mostrarán todas las marcas de tiempo del sistema (alertas, eventos y otros) en UTC para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="cf374-122">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="cf374-123">Esto puede ayudar a los analistas de seguridad que trabajan en diferentes ubicaciones de todo el mundo a usar las mismas marcas de tiempo mientras investigan eventos.</span><span class="sxs-lookup"><span data-stu-id="cf374-123">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="cf374-124">Zona horaria local</span><span class="sxs-lookup"><span data-stu-id="cf374-124">Local time zone</span></span>
<span data-ttu-id="cf374-125">Puedes elegir que Microsoft Defender para endpoint use la configuración de zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="cf374-125">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="cf374-126">Todas las alertas y eventos se mostrarán con la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="cf374-126">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="cf374-127">La zona horaria local se toma de la configuración regional del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cf374-127">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="cf374-128">Si cambia la configuración regional, también cambiará la zona horaria de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="cf374-128">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="cf374-129">Elegir esta configuración significa que las marcas de tiempo mostradas en Microsoft Defender para endpoint se alinearán a la hora local para todos los usuarios de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="cf374-129">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="cf374-130">Los analistas ubicados en diferentes ubicaciones globales ahora verán las alertas de Microsoft Defender para endpoint según su configuración regional.</span><span class="sxs-lookup"><span data-stu-id="cf374-130">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="cf374-131">Elegir usar la hora local puede ser útil si los analistas se encuentran en una única ubicación.</span><span class="sxs-lookup"><span data-stu-id="cf374-131">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="cf374-132">En este caso, puede ser más fácil correlacionar eventos con la hora local, por ejemplo, cuando un usuario local hizo clic en un vínculo de correo electrónico sospechoso.</span><span class="sxs-lookup"><span data-stu-id="cf374-132">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="cf374-133">Establecer la zona horaria</span><span class="sxs-lookup"><span data-stu-id="cf374-133">Set the time zone</span></span>
<span data-ttu-id="cf374-134">La zona horaria de Microsoft Defender para extremo se establece de forma predeterminada en UTC.</span><span class="sxs-lookup"><span data-stu-id="cf374-134">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="cf374-135">Establecer la zona horaria también cambia las horas de todas las vistas de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="cf374-135">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="cf374-136">Para establecer la zona horaria:</span><span class="sxs-lookup"><span data-stu-id="cf374-136">To set the time zone:</span></span>

1. <span data-ttu-id="cf374-137">Haga clic en **el icono Configuración** de zona horaria del menú Zona ![ horaria3 ](images/atp-time-zone.png) .</span><span class="sxs-lookup"><span data-stu-id="cf374-137">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="cf374-138">Seleccione el **indicador UTC de zona** horaria.</span><span class="sxs-lookup"><span data-stu-id="cf374-138">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="cf374-139">Seleccione **Zona horaria UTC** o la zona horaria local, por ejemplo -7:00.</span><span class="sxs-lookup"><span data-stu-id="cf374-139">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="cf374-140">Configuración regional</span><span class="sxs-lookup"><span data-stu-id="cf374-140">Regional settings</span></span>
<span data-ttu-id="cf374-141">Para aplicar diferentes formatos de fecha para Microsoft Defender para endpoint, usa la configuración regional para Internet Explorer (IE) y Microsoft Edge (Edge).</span><span class="sxs-lookup"><span data-stu-id="cf374-141">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="cf374-142">Si usas otro explorador como Google Chrome, sigue los pasos necesarios para cambiar la configuración de hora y fecha de ese explorador.</span><span class="sxs-lookup"><span data-stu-id="cf374-142">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="cf374-143">**Internet Explorer (IE) y Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="cf374-143">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="cf374-144">IE y Microsoft Edge usan la **configuración de** región configurada en la **opción Relojes, Idioma y Región** del panel de control.</span><span class="sxs-lookup"><span data-stu-id="cf374-144">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="cf374-145">Problemas conocidos con formatos regionales</span><span class="sxs-lookup"><span data-stu-id="cf374-145">Known issues with regional formats</span></span>

<span data-ttu-id="cf374-146">**Formatos de fecha y hora**</span><span class="sxs-lookup"><span data-stu-id="cf374-146">**Date and time formats**</span></span><br>
<span data-ttu-id="cf374-147">Hay algunos problemas conocidos con los formatos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="cf374-147">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="cf374-148">Si configura la configuración regional en cualquier otro formato que no sea compatible, es posible que el portal no refleje correctamente la configuración.</span><span class="sxs-lookup"><span data-stu-id="cf374-148">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="cf374-149">Se admiten los siguientes formatos de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="cf374-149">The following date and time formats are supported:</span></span>
- <span data-ttu-id="cf374-150">Formato de fecha MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="cf374-150">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="cf374-151">Formato de fecha dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="cf374-151">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="cf374-152">Formato de hora hh:mm:ss (formato de 12 horas)</span><span class="sxs-lookup"><span data-stu-id="cf374-152">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="cf374-153">Actualmente no se admiten los siguientes formatos de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="cf374-153">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="cf374-154">Formato de fecha yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="cf374-154">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="cf374-155">Formato de fecha dd-MMM-yy</span><span class="sxs-lookup"><span data-stu-id="cf374-155">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="cf374-156">Formato de fecha dd/MM/aa</span><span class="sxs-lookup"><span data-stu-id="cf374-156">Date format dd/MM/yy</span></span>
- <span data-ttu-id="cf374-157">Formato de fecha MM/dd/aa</span><span class="sxs-lookup"><span data-stu-id="cf374-157">Date format MM/dd/yy</span></span>
- <span data-ttu-id="cf374-158">Formato de fecha con yy.</span><span class="sxs-lookup"><span data-stu-id="cf374-158">Date format with yy.</span></span> <span data-ttu-id="cf374-159">Solo se mostrará yyyy.</span><span class="sxs-lookup"><span data-stu-id="cf374-159">Will only show yyyy.</span></span>
- <span data-ttu-id="cf374-160">Formato de hora HH:mm:ss (formato de 24 horas)</span><span class="sxs-lookup"><span data-stu-id="cf374-160">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="cf374-161">**Símbolo decimal usado en números**</span><span class="sxs-lookup"><span data-stu-id="cf374-161">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="cf374-162">El símbolo decimal usado siempre es un punto, incluso si se selecciona una coma en la **configuración de** formato Números de la **configuración de** región.</span><span class="sxs-lookup"><span data-stu-id="cf374-162">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="cf374-163">Por ejemplo, 15,5K se muestra como 15,5K.</span><span class="sxs-lookup"><span data-stu-id="cf374-163">For example, 15,5K is displayed as 15.5K.</span></span>


