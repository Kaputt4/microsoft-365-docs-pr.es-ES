---
title: Solucionar problemas y encontrar respuestas en preguntas frecuentes relacionadas con Microsoft Defender para endpoint en iOS
description: 'Solución de problemas y preguntas frecuentes: Microsoft Defender para endpoint en iOS'
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, troubleshoot, faq, how to
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2f9d56b7e72befb8acddf6d9f810a7ba5cec1083
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694370"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="082b3-104">Solucionar problemas y encontrar respuestas a preguntas frecuentes en Microsoft Defender para endpoint en iOS</span><span class="sxs-lookup"><span data-stu-id="082b3-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="082b3-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="082b3-105">**Applies to:**</span></span>
- [<span data-ttu-id="082b3-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="082b3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="082b3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="082b3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="082b3-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="082b3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="082b3-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="082b3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="082b3-110">En este tema se proporciona información de solución de problemas que le ayudará a solucionar los problemas que pueden surgir al usar Microsoft Defender para Endpoint en iOS.</span><span class="sxs-lookup"><span data-stu-id="082b3-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="082b3-111">Defender para endpoint en iOS usaría una VPN para proporcionar la característica de protección web.</span><span class="sxs-lookup"><span data-stu-id="082b3-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="082b3-112">No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="082b3-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="082b3-113">Las aplicaciones no funcionan cuando la VPN está activada</span><span class="sxs-lookup"><span data-stu-id="082b3-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="082b3-114">Hay algunas aplicaciones que dejan de funcionar cuando se detecta una VPN activa.</span><span class="sxs-lookup"><span data-stu-id="082b3-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="082b3-115">Puedes deshabilitar la VPN durante el tiempo que estás usando estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="082b3-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="082b3-116">De forma predeterminada, Defender para endpoint en iOS incluye y habilita la característica de protección web.</span><span class="sxs-lookup"><span data-stu-id="082b3-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="082b3-117">[La protección web](web-protection-overview.md) ayuda a proteger los dispositivos contra amenazas web y a proteger a los usuarios de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="082b3-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="082b3-118">Defender para endpoint en iOS usa una VPN para proporcionar esta protección.</span><span class="sxs-lookup"><span data-stu-id="082b3-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="082b3-119">Tenga en cuenta que se trata de una VPN local y, a diferencia de la VPN tradicional, el tráfico de red no se envía fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="082b3-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="082b3-120">Aunque está habilitado de forma predeterminada, puede haber algunos casos que requieran deshabilitar VPN.</span><span class="sxs-lookup"><span data-stu-id="082b3-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="082b3-121">Por ejemplo, quieres ejecutar algunas aplicaciones que no funcionan cuando se configura una VPN.</span><span class="sxs-lookup"><span data-stu-id="082b3-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="082b3-122">En tales casos, puedes optar por deshabilitar VPN desde la aplicación en el dispositivo siguiendo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="082b3-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="082b3-123">En el dispositivo iOS, abre la **aplicación Configuración,** haz clic o pulsa **General** y, a continuación, **VPN.**</span><span class="sxs-lookup"><span data-stu-id="082b3-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="082b3-124">Haga clic o pulse en el botón "i" de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="082b3-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="082b3-125">Desactiva la **Conectar a petición** para deshabilitar VPN.</span><span class="sxs-lookup"><span data-stu-id="082b3-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="082b3-126">![Configuración de VPN conectarse a petición](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="082b3-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="082b3-127">La protección web no estará disponible cuando la VPN esté deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="082b3-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="082b3-128">Para volver a habilitar Protección web, abra la aplicación Microsoft Defender para endpoint en el dispositivo y haga clic o pulse **Iniciar VPN**.</span><span class="sxs-lookup"><span data-stu-id="082b3-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="082b3-129">Problemas con varios perfiles de VPN</span><span class="sxs-lookup"><span data-stu-id="082b3-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="082b3-130">Apple iOS no admite varias VPN de todo **el** dispositivo para estar activas simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="082b3-130">Apple iOS does not support multiple **device-wide** VPNs to be active simultaneously.</span></span> <span data-ttu-id="082b3-131">Aunque pueden existir varios perfiles de VPN en el dispositivo, solo una VPN puede estar activa a la vez.</span><span class="sxs-lookup"><span data-stu-id="082b3-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

<span data-ttu-id="082b3-132">Microsoft Defender para endpoint VPN puede coexistir con otras VPN configuradas como *por aplicación* o *"Personal".*</span><span class="sxs-lookup"><span data-stu-id="082b3-132">Microsoft Defender for Endpoint VPN can co-exist with other VPNs that are configured as *per-app* or *"Personal"*.</span></span>

## <a name="battery-consumption"></a><span data-ttu-id="082b3-133">Consumo de batería</span><span class="sxs-lookup"><span data-stu-id="082b3-133">Battery consumption</span></span>

<span data-ttu-id="082b3-134">En la Configuración, iOS solo muestra el uso de batería de aplicaciones que son visibles para el usuario durante un período de tiempo específico.</span><span class="sxs-lookup"><span data-stu-id="082b3-134">In the Settings app, iOS only shows battery usage of apps that are visible to the user for a specific duration of time.</span></span> <span data-ttu-id="082b3-135">El uso de la batería por parte de las aplicaciones que se muestran en la pantalla es solo durante ese tiempo y lo calcula iOS en función de una gran variedad de factores, incluido el uso de la CPU y la red.</span><span class="sxs-lookup"><span data-stu-id="082b3-135">The battery usage by apps shown on the screen are only for that time duration and is computed by iOS based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="082b3-136">Microsoft Defender para endpoint usa una VPN local/loop-back en segundo plano para comprobar el tráfico web en busca de sitios web o conexiones malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="082b3-136">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="082b3-137">Los paquetes de red de cualquier aplicación pasan por esta comprobación y eso hace que el uso de la batería de Microsoft Defender para Endpoint se calcule incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="082b3-137">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="082b3-138">El consumo real de batería de Microsoft Defender para Endpoint es mucho menor que lo que se muestra en la página Battery Configuración en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="082b3-138">The actual battery consumption of Microsoft Defender for Endpoint is much less than what is shown on the Battery Settings page on the device.</span></span>

<span data-ttu-id="082b3-139">En promedio, el uso de batería por día por parte de Microsoft Defender para endpoint que se ejecuta en segundo plano es aproximadamente el **8,81 %** de la batería total consumida en ese día.</span><span class="sxs-lookup"><span data-stu-id="082b3-139">On an average, per-day battery usage by Microsoft Defender for Endpoint running on the background is **approximately 8.81% of overall battery consumed in that day**.</span></span> <span data-ttu-id="082b3-140">Apple informa de esta métrica en función del uso real de Microsoft Defender para Endpoint en dispositivos de usuario final y debido a los motivos mencionados anteriormente también se pueden tener en cuenta en otras aplicaciones que tienen actividad de red.</span><span class="sxs-lookup"><span data-stu-id="082b3-140">This metric is reported by Apple based on actual usage of Microsoft Defender for Endpoint on end-user devices and due to reasons mentioned above can also be accounted to other apps that have network activity.</span></span>

<span data-ttu-id="082b3-141">Además, la VPN usada es una VPN local y, a diferencia de una VPN tradicional, el tráfico de red no se envía fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="082b3-141">Also, the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="082b3-142">Uso de datos</span><span class="sxs-lookup"><span data-stu-id="082b3-142">Data usage</span></span>

<span data-ttu-id="082b3-143">Microsoft Defender para endpoint usa una VPN local/loopback para comprobar el tráfico web en busca de sitios web o conexiones malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="082b3-143">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="082b3-144">Debido a este motivo, el uso de datos de Microsoft Defender para puntos de conexión puede tenerse en cuenta de forma inexacta.</span><span class="sxs-lookup"><span data-stu-id="082b3-144">Due to this reason, Microsoft Defender for Endpoint data usage can be inaccurately accounted for.</span></span> <span data-ttu-id="082b3-145">El uso real de datos por Parte de Microsoft Defender para Endpoint no es significativo y menor que lo que se muestra en el Configuración de uso de datos en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="082b3-145">The actual data usage by Microsoft Defender for Endpoint is not significant and lesser than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="082b3-146">Informe de sitio no seguro</span><span class="sxs-lookup"><span data-stu-id="082b3-146">Report unsafe site</span></span>

<span data-ttu-id="082b3-147">Los sitios web de suplantación de identidad suplantan sitios web de confianza con el fin de obtener su información personal o financiera.</span><span class="sxs-lookup"><span data-stu-id="082b3-147">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="082b3-148">Visite la [página Proporcionar comentarios sobre la protección de](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) red para informar de un sitio web que podría ser un sitio de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="082b3-148">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="082b3-149">Sitio malintencionado detectado</span><span class="sxs-lookup"><span data-stu-id="082b3-149">Malicious site detected</span></span>

<span data-ttu-id="082b3-150">Microsoft Defender para endpoint le protege contra la suplantación de identidad (phishing) u otros ataques basados en web.</span><span class="sxs-lookup"><span data-stu-id="082b3-150">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="082b3-151">Si se detecta un sitio malintencionado, la conexión se bloquea y se envía una alerta al portal del Centro de seguridad de la organización.</span><span class="sxs-lookup"><span data-stu-id="082b3-151">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="082b3-152">La alerta incluye el nombre de dominio de la conexión, la dirección IP remota y los detalles del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="082b3-152">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="082b3-153">Además, se muestra una notificación en el dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="082b3-153">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="082b3-154">Al pulsar en la notificación se abre la siguiente pantalla para que el usuario revise los detalles.</span><span class="sxs-lookup"><span data-stu-id="082b3-154">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="082b3-155">![Imagen del sitio notificado como notificación no segura](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="082b3-155">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="082b3-156">Datos y privacidad</span><span class="sxs-lookup"><span data-stu-id="082b3-156">Data and Privacy</span></span>

<span data-ttu-id="082b3-157">Para obtener más información acerca de los datos recopilados y la privacidad, consulte [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="082b3-157">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

