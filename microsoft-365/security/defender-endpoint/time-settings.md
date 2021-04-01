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
ms.openlocfilehash: e395420b92c29977f1c802d1c10683492c1aba10
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470470"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="a62b0-104">Configuración de zona horaria del Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a62b0-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a62b0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a62b0-105">**Applies to:**</span></span>
- [<span data-ttu-id="a62b0-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a62b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="a62b0-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="a62b0-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a62b0-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="a62b0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="a62b0-109">Use el **icono 1 de** configuración de zona horaria del menú Zona ![ horaria para configurar la zona horaria y ver la información de ](images/atp-time-zone.png) licencia.</span><span class="sxs-lookup"><span data-stu-id="a62b0-109">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="a62b0-110">Configuración de zona horaria</span><span class="sxs-lookup"><span data-stu-id="a62b0-110">Time zone settings</span></span>
<span data-ttu-id="a62b0-111">El aspecto del tiempo es importante en la evaluación y el análisis de los ciberataques percibidos y reales.</span><span class="sxs-lookup"><span data-stu-id="a62b0-111">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="a62b0-112">Las investigaciones ciberforensicas suelen basarse en marcas de tiempo para unir la secuencia de eventos.</span><span class="sxs-lookup"><span data-stu-id="a62b0-112">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="a62b0-113">Es importante que el sistema refleje la configuración de zona horaria correcta.</span><span class="sxs-lookup"><span data-stu-id="a62b0-113">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="a62b0-114">Microsoft Defender para endpoint puede mostrar la hora universal coordinada (UTC) o la hora local.</span><span class="sxs-lookup"><span data-stu-id="a62b0-114">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="a62b0-115">La configuración actual de la zona horaria se muestra en el menú Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="a62b0-115">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="a62b0-116">Puede cambiar la zona horaria mostrada en el **menú Zona** horaria.</span><span class="sxs-lookup"><span data-stu-id="a62b0-116">You can change the displayed time zone in the **Time zone** menu.</span></span>

![Icono de configuración de zona horaria2](images/atp-time-zone-menu.png)<span data-ttu-id="a62b0-118">.</span><span class="sxs-lookup"><span data-stu-id="a62b0-118">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="a62b0-119">Zona horaria UTC</span><span class="sxs-lookup"><span data-stu-id="a62b0-119">UTC time zone</span></span>
<span data-ttu-id="a62b0-120">Microsoft Defender para endpoint usa la hora UTC de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a62b0-120">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="a62b0-121">Al establecer la zona horaria de Microsoft Defender para endpoint en UTC, se mostrarán todas las marcas de tiempo del sistema (alertas, eventos y otros) en UTC para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a62b0-121">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="a62b0-122">Esto puede ayudar a los analistas de seguridad que trabajan en diferentes ubicaciones de todo el mundo a usar las mismas marcas de tiempo mientras investigan eventos.</span><span class="sxs-lookup"><span data-stu-id="a62b0-122">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="a62b0-123">Zona horaria local</span><span class="sxs-lookup"><span data-stu-id="a62b0-123">Local time zone</span></span>
<span data-ttu-id="a62b0-124">Puedes elegir que Microsoft Defender para endpoint use la configuración de zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="a62b0-124">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="a62b0-125">Todas las alertas y eventos se mostrarán con la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="a62b0-125">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="a62b0-126">La zona horaria local se toma de la configuración regional del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a62b0-126">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="a62b0-127">Si cambia la configuración regional, también cambiará la zona horaria de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="a62b0-127">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="a62b0-128">Elegir esta configuración significa que las marcas de tiempo mostradas en Microsoft Defender para endpoint se alinearán a la hora local para todos los usuarios de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="a62b0-128">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="a62b0-129">Los analistas ubicados en diferentes ubicaciones globales ahora verán las alertas de Microsoft Defender para endpoint según su configuración regional.</span><span class="sxs-lookup"><span data-stu-id="a62b0-129">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="a62b0-130">Elegir usar la hora local puede ser útil si los analistas se encuentran en una única ubicación.</span><span class="sxs-lookup"><span data-stu-id="a62b0-130">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="a62b0-131">En este caso, puede ser más fácil correlacionar eventos con la hora local, por ejemplo, cuando un usuario local hizo clic en un vínculo de correo electrónico sospechoso.</span><span class="sxs-lookup"><span data-stu-id="a62b0-131">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="a62b0-132">Establecer la zona horaria</span><span class="sxs-lookup"><span data-stu-id="a62b0-132">Set the time zone</span></span>
<span data-ttu-id="a62b0-133">La zona horaria de Microsoft Defender para extremo se establece de forma predeterminada en UTC.</span><span class="sxs-lookup"><span data-stu-id="a62b0-133">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="a62b0-134">Establecer la zona horaria también cambia las horas de todas las vistas de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="a62b0-134">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="a62b0-135">Para establecer la zona horaria:</span><span class="sxs-lookup"><span data-stu-id="a62b0-135">To set the time zone:</span></span>

1. <span data-ttu-id="a62b0-136">Haga clic en **el icono Configuración** de zona horaria del menú Zona ![ horaria3 ](images/atp-time-zone.png) .</span><span class="sxs-lookup"><span data-stu-id="a62b0-136">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="a62b0-137">Seleccione el **indicador UTC de zona** horaria.</span><span class="sxs-lookup"><span data-stu-id="a62b0-137">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="a62b0-138">Seleccione **Zona horaria UTC** o la zona horaria local, por ejemplo -7:00.</span><span class="sxs-lookup"><span data-stu-id="a62b0-138">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="a62b0-139">Configuración regional</span><span class="sxs-lookup"><span data-stu-id="a62b0-139">Regional settings</span></span>
<span data-ttu-id="a62b0-140">Para aplicar diferentes formatos de fecha para Microsoft Defender para endpoint, usa la configuración regional para Internet Explorer (IE) y Microsoft Edge (Edge).</span><span class="sxs-lookup"><span data-stu-id="a62b0-140">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="a62b0-141">Si usas otro explorador como Google Chrome, sigue los pasos necesarios para cambiar la configuración de hora y fecha de ese explorador.</span><span class="sxs-lookup"><span data-stu-id="a62b0-141">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="a62b0-142">**Internet Explorer (IE) y Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="a62b0-142">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="a62b0-143">IE y Microsoft Edge usan la **configuración de** región configurada en la **opción Relojes, Idioma y Región** del panel de control.</span><span class="sxs-lookup"><span data-stu-id="a62b0-143">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="a62b0-144">Problemas conocidos con formatos regionales</span><span class="sxs-lookup"><span data-stu-id="a62b0-144">Known issues with regional formats</span></span>

<span data-ttu-id="a62b0-145">**Formatos de fecha y hora**</span><span class="sxs-lookup"><span data-stu-id="a62b0-145">**Date and time formats**</span></span><br>
<span data-ttu-id="a62b0-146">Hay algunos problemas conocidos con los formatos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="a62b0-146">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="a62b0-147">Si configura la configuración regional en cualquier otro formato que no sea compatible, es posible que el portal no refleje correctamente la configuración.</span><span class="sxs-lookup"><span data-stu-id="a62b0-147">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="a62b0-148">Se admiten los siguientes formatos de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="a62b0-148">The following date and time formats are supported:</span></span>
- <span data-ttu-id="a62b0-149">Formato de fecha MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="a62b0-149">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="a62b0-150">Formato de fecha dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="a62b0-150">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="a62b0-151">Formato de hora hh:mm:ss (formato de 12 horas)</span><span class="sxs-lookup"><span data-stu-id="a62b0-151">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="a62b0-152">Actualmente no se admiten los siguientes formatos de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="a62b0-152">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="a62b0-153">Formato de fecha yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="a62b0-153">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="a62b0-154">Formato de fecha dd-MMM-yy</span><span class="sxs-lookup"><span data-stu-id="a62b0-154">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="a62b0-155">Formato de fecha dd/MM/aa</span><span class="sxs-lookup"><span data-stu-id="a62b0-155">Date format dd/MM/yy</span></span>
- <span data-ttu-id="a62b0-156">Formato de fecha MM/dd/aa</span><span class="sxs-lookup"><span data-stu-id="a62b0-156">Date format MM/dd/yy</span></span>
- <span data-ttu-id="a62b0-157">Formato de fecha con yy.</span><span class="sxs-lookup"><span data-stu-id="a62b0-157">Date format with yy.</span></span> <span data-ttu-id="a62b0-158">Solo se mostrará yyyy.</span><span class="sxs-lookup"><span data-stu-id="a62b0-158">Will only show yyyy.</span></span>
- <span data-ttu-id="a62b0-159">Formato de hora HH:mm:ss (formato de 24 horas)</span><span class="sxs-lookup"><span data-stu-id="a62b0-159">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="a62b0-160">**Símbolo decimal usado en números**</span><span class="sxs-lookup"><span data-stu-id="a62b0-160">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="a62b0-161">El símbolo decimal usado siempre es un punto, incluso si se selecciona una coma en la **configuración de** formato Números de la **configuración de** región.</span><span class="sxs-lookup"><span data-stu-id="a62b0-161">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="a62b0-162">Por ejemplo, 15,5K se muestra como 15,5K.</span><span class="sxs-lookup"><span data-stu-id="a62b0-162">For example, 15,5K is displayed as 15.5K.</span></span>


