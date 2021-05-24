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
ms.openlocfilehash: 13c0a575fd2614f58eb6a2163cda04118c2a391d
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636283"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="a9ab2-104">Solucionar problemas y encontrar respuestas a preguntas frecuentes en Microsoft Defender para endpoint en iOS</span><span class="sxs-lookup"><span data-stu-id="a9ab2-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a9ab2-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a9ab2-105">**Applies to:**</span></span>
- [<span data-ttu-id="a9ab2-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a9ab2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a9ab2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9ab2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a9ab2-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a9ab2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a9ab2-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="a9ab2-110">En este tema se proporciona información de solución de problemas que le ayudará a solucionar los problemas que pueden surgir al usar Microsoft Defender para Endpoint en iOS.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="a9ab2-111">Defender para endpoint en iOS usaría una VPN para proporcionar la característica de protección web.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="a9ab2-112">No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="a9ab2-113">Las aplicaciones no funcionan cuando la VPN está activada</span><span class="sxs-lookup"><span data-stu-id="a9ab2-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="a9ab2-114">Hay algunas aplicaciones que dejan de funcionar cuando se detecta una VPN activa.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="a9ab2-115">Puedes deshabilitar la VPN durante el tiempo que estás usando estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="a9ab2-116">De forma predeterminada, Defender para endpoint en iOS incluye y habilita la característica de protección web.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="a9ab2-117">[La protección web](web-protection-overview.md) ayuda a proteger los dispositivos contra amenazas web y a proteger a los usuarios de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="a9ab2-118">Defender para endpoint en iOS usa una VPN para proporcionar esta protección.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="a9ab2-119">Tenga en cuenta que se trata de una VPN local y, a diferencia de la VPN tradicional, el tráfico de red no se envía fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="a9ab2-120">Aunque está habilitado de forma predeterminada, puede haber algunos casos que requieran deshabilitar VPN.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="a9ab2-121">Por ejemplo, quieres ejecutar algunas aplicaciones que no funcionan cuando se configura una VPN.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="a9ab2-122">En tales casos, puedes optar por deshabilitar VPN desde la aplicación en el dispositivo siguiendo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a9ab2-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="a9ab2-123">En el dispositivo iOS, abre la **aplicación Configuración,** haz clic o pulsa **General** y, a continuación, **VPN.**</span><span class="sxs-lookup"><span data-stu-id="a9ab2-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="a9ab2-124">Haga clic o pulse en el botón "i" de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="a9ab2-125">Desactiva la **Conectar a petición** para deshabilitar VPN.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a9ab2-126">![Configuración de VPN conectarse a petición](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="a9ab2-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="a9ab2-127">La protección web no estará disponible cuando la VPN esté deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="a9ab2-128">Para volver a habilitar Protección web, abra la aplicación Microsoft Defender para endpoint en el dispositivo y haga clic o pulse **Iniciar VPN**.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="a9ab2-129">Problemas con varios perfiles de VPN</span><span class="sxs-lookup"><span data-stu-id="a9ab2-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="a9ab2-130">Apple iOS no admite varias VPN de todo el dispositivo para estar activas simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-130">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="a9ab2-131">Aunque pueden existir varios perfiles de VPN en el dispositivo, solo una VPN puede estar activa a la vez.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="battery-consumption"></a><span data-ttu-id="a9ab2-132">Consumo de batería</span><span class="sxs-lookup"><span data-stu-id="a9ab2-132">Battery consumption</span></span>

<span data-ttu-id="a9ab2-133">Apple calcula el uso de la batería por parte de una aplicación en función de una gran variedad de factores, como el uso de la CPU y la red.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-133">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="a9ab2-134">Microsoft Defender para endpoint usa una VPN local/loop-back en segundo plano para comprobar el tráfico web en busca de sitios web o conexiones malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-134">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="a9ab2-135">Los paquetes de red de cualquier aplicación pasan por esta comprobación y eso hace que el uso de la batería de Microsoft Defender para Endpoint se calcule incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-135">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="a9ab2-136">Esto da una impresión falsa al usuario.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-136">This gives a false impression to the user.</span></span> <span data-ttu-id="a9ab2-137">El consumo real de batería de Microsoft Defender para Endpoint es menor que lo que se muestra en la página De Configuración batería en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-137">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="a9ab2-138">Esto se basa en pruebas realizadas en la aplicación Microsoft Defender para Endpoint para comprender el consumo de batería.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-138">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="a9ab2-139">Además, la VPN usada es una VPN local y, a diferencia de una VPN tradicional, el tráfico de red no se envía fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-139">Also the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="a9ab2-140">Uso de datos</span><span class="sxs-lookup"><span data-stu-id="a9ab2-140">Data usage</span></span>

<span data-ttu-id="a9ab2-141">Microsoft Defender para endpoint usa una VPN local/loopback para comprobar el tráfico web en busca de sitios web o conexiones malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-141">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="a9ab2-142">Debido a este motivo, Apple cuenta el uso de datos en Microsoft Defender para endpoint de forma inexacta.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-142">Due to this reason Apple accounts data usage to Microsoft Defender for Endpoint inaccurately.</span></span> <span data-ttu-id="a9ab2-143">El uso real de datos por Parte de Microsoft Defender para Endpoint no es significativo y mucho menor que lo que se muestra en el Configuración uso de datos en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-143">The actual data usage by Microsoft Defender for Endpoint is not significant and much less than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="a9ab2-144">Informe de sitio no seguro</span><span class="sxs-lookup"><span data-stu-id="a9ab2-144">Report unsafe site</span></span>

<span data-ttu-id="a9ab2-145">Los sitios web de suplantación de identidad suplantan sitios web de confianza con el fin de obtener su información personal o financiera.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-145">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="a9ab2-146">Visite la [página Proporcionar comentarios sobre la protección de](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) red para informar de un sitio web que podría ser un sitio de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-146">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="a9ab2-147">Sitio malintencionado detectado</span><span class="sxs-lookup"><span data-stu-id="a9ab2-147">Malicious site detected</span></span>

<span data-ttu-id="a9ab2-148">Microsoft Defender para endpoint le protege contra la suplantación de identidad (phishing) u otros ataques basados en web.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-148">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="a9ab2-149">Si se detecta un sitio malintencionado, la conexión se bloquea y se envía una alerta al portal del Centro de seguridad de la organización.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-149">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="a9ab2-150">La alerta incluye el nombre de dominio de la conexión, la dirección IP remota y los detalles del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-150">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="a9ab2-151">Además, se muestra una notificación en el dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-151">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="a9ab2-152">Al pulsar en la notificación se abre la siguiente pantalla para que el usuario revise los detalles.</span><span class="sxs-lookup"><span data-stu-id="a9ab2-152">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a9ab2-153">![Imagen del sitio notificado como notificación no segura](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="a9ab2-153">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="a9ab2-154">Datos y privacidad</span><span class="sxs-lookup"><span data-stu-id="a9ab2-154">Data and Privacy</span></span>

<span data-ttu-id="a9ab2-155">Para obtener más información acerca de los datos recopilados y la privacidad, consulte [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="a9ab2-155">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

