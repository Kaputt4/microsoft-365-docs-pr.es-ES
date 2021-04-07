---
title: Administración de vulnerabilidades y detección de dispositivos de red
description: Las recomendaciones de seguridad y la detección de vulnerabilidades ya están disponibles para sistemas operativos de conmutadores, enrutadores, controladores WLAN y firewalls.
keywords: dispositivos de red, detección de vulnerabilidades de dispositivos de red, sistemas operativos de conmutadores, enrutadores, controladores WLAN y firewalls
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 06b52e937dd0260a50883c45c36389a6a955ad0e
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604533"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="08400-104">Administración de vulnerabilidades y detección de dispositivos de red</span><span class="sxs-lookup"><span data-stu-id="08400-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="08400-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="08400-105">**Applies to:**</span></span>

- [<span data-ttu-id="08400-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="08400-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="08400-107">Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="08400-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="08400-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08400-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="08400-109">**El examen y la administración de dispositivos de red se encuentra actualmente en versión preliminar pública**</span><span class="sxs-lookup"><span data-stu-id="08400-109">**Scanning and managing network devices is currently in public preview**</span></span><br>
> <span data-ttu-id="08400-110">Esta versión preliminar se proporciona sin un contrato de nivel de servicio y no se recomienda para cargas de trabajo de producción.</span><span class="sxs-lookup"><span data-stu-id="08400-110">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="08400-111">Es posible que algunas características no sean compatibles o que tengan capacidades limitadas.</span><span class="sxs-lookup"><span data-stu-id="08400-111">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="08400-112">Para obtener más información, vea Características de vista previa [de Microsoft Defender para endpoint](preview.md).</span><span class="sxs-lookup"><span data-stu-id="08400-112">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="08400-113">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="08400-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="08400-114">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="08400-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="08400-115">Las funcionalidades de detección de red están disponibles en la sección **Inventario** de dispositivos del Centro de seguridad de Microsoft 365 y las consolas del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="08400-115">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="08400-116">Se usará un dispositivo designado de Microsoft Defender para endpoint en cada segmento de red para realizar exámenes periódicos autenticados de dispositivos de red preconfigurados.</span><span class="sxs-lookup"><span data-stu-id="08400-116">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="08400-117">Una vez descubierto, las capacidades de administración de amenazas y vulnerabilidades de Defender for Endpoint proporcionan flujos de trabajo integrados para proteger los conmutadores detectados, enrutadores, controladores WLAN, firewalls y puertas de enlace VPN.</span><span class="sxs-lookup"><span data-stu-id="08400-117">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="08400-118">Una vez que se descubran y clasifiquen los dispositivos de red, los administradores de seguridad podrán recibir las recomendaciones de seguridad más recientes y revisar las vulnerabilidades detectadas recientemente para los dispositivos de red implementados en sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="08400-118">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities foron network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="08400-119">Enfoque</span><span class="sxs-lookup"><span data-stu-id="08400-119">Approach</span></span>

<span data-ttu-id="08400-120">Los dispositivos de red no se administran como puntos de conexión estándar, ya que Defender for Endpoint no tiene un sensor integrado en los propios dispositivos de red.</span><span class="sxs-lookup"><span data-stu-id="08400-120">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="08400-121">Estos tipos de dispositivos requieren un enfoque sin agente donde un examen remoto obtendrá la información necesaria de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="08400-121">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="08400-122">Según la topología y las características de red, un solo dispositivo o algunos dispositivos incorporados a Microsoft Defender para Endpoint realizarán exámenes autenticados de dispositivos de red mediante SNMP (solo lectura).</span><span class="sxs-lookup"><span data-stu-id="08400-122">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="08400-123">Habrá dos tipos de dispositivos a tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="08400-123">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="08400-124">**Dispositivo de evaluación:** un dispositivo que ya está incorporado y que usarás para examinar los dispositivos de red.</span><span class="sxs-lookup"><span data-stu-id="08400-124">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="08400-125">**Dispositivos de** red: los dispositivos de red que tiene previsto examinar e incorporar.</span><span class="sxs-lookup"><span data-stu-id="08400-125">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="08400-126">Administración de vulnerabilidades para dispositivos de red</span><span class="sxs-lookup"><span data-stu-id="08400-126">Vulnerability management for network devices</span></span> 

<span data-ttu-id="08400-127">Una vez detectados y clasificados los dispositivos de red, los administradores de seguridad podrán recibir las recomendaciones de seguridad más recientes y revisar las vulnerabilidades detectadas recientemente en los dispositivos de red implementados en sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="08400-127">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="08400-128">Sistemas operativos compatibles</span><span class="sxs-lookup"><span data-stu-id="08400-128">Operating systems that are supported</span></span>

<span data-ttu-id="08400-129">Actualmente se admiten los siguientes sistemas operativos:</span><span class="sxs-lookup"><span data-stu-id="08400-129">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="08400-130">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="08400-130">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="08400-131">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="08400-131">Juniper JUNOS</span></span>
- <span data-ttu-id="08400-132">HPE ArubaOS, Software de conmutador procurve</span><span class="sxs-lookup"><span data-stu-id="08400-132">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="08400-133">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="08400-133">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="08400-134">Se agregarán más proveedores de redes y sos con el tiempo, en función de los datos recopilados por el uso del cliente.</span><span class="sxs-lookup"><span data-stu-id="08400-134">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="08400-135">Por lo tanto, se recomienda configurar todos los dispositivos de red, incluso si no están especificados en esta lista.</span><span class="sxs-lookup"><span data-stu-id="08400-135">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="08400-136">Como empezar</span><span class="sxs-lookup"><span data-stu-id="08400-136">How to get started</span></span>

<span data-ttu-id="08400-137">El primer paso es seleccionar un dispositivo que realizará los exámenes de red autenticados.</span><span class="sxs-lookup"><span data-stu-id="08400-137">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="08400-138">Decide un dispositivo integrado de Defender for Endpoint (cliente o servidor) que tenga una conexión de red al puerto de administración de los dispositivos de red que planeas examinar.</span><span class="sxs-lookup"><span data-stu-id="08400-138">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="08400-139">Se debe permitir el tráfico SNMP entre el dispositivo de evaluación de Defender para endpoints y los dispositivos de red de destino (por ejemplo, mediante el Firewall).</span><span class="sxs-lookup"><span data-stu-id="08400-139">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="08400-140">Decida qué dispositivos de red se evaluarán para las vulnerabilidades (por ejemplo: un conmutador cisco o un firewall de Palo Alto Networks).</span><span class="sxs-lookup"><span data-stu-id="08400-140">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="08400-141">Asegúrese de que SNMP de solo lectura está habilitado en todos los dispositivos de red configurados para permitir que el dispositivo de evaluación de Defender for Endpoint consulte los dispositivos de red configurados.</span><span class="sxs-lookup"><span data-stu-id="08400-141">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="08400-142">La "escritura SNMP" no es necesaria para la funcionalidad adecuada de esta característica.</span><span class="sxs-lookup"><span data-stu-id="08400-142">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="08400-143">Obtener las direcciones IP de los dispositivos de red que se van a examinar (o las subredes donde se implementan estos dispositivos).</span><span class="sxs-lookup"><span data-stu-id="08400-143">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="08400-144">Obtenga las credenciales SNMP de los dispositivos de red (por ejemplo: Community String, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="08400-144">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="08400-145">Tendrás que proporcionar las credenciales al configurar un nuevo trabajo de evaluación.</span><span class="sxs-lookup"><span data-stu-id="08400-145">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="08400-146">Configuración del cliente proxy: no se requiere ninguna configuración adicional que no sea los requisitos de proxy de dispositivo defender para extremo.</span><span class="sxs-lookup"><span data-stu-id="08400-146">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="08400-147">Para permitir que el escáner de red se autentique y funcione correctamente, es esencial que agregue los siguientes dominios o direcciones URL:</span><span class="sxs-lookup"><span data-stu-id="08400-147">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="08400-148">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="08400-148">login.windows.net</span></span>  
    - <span data-ttu-id="08400-149">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="08400-149">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="08400-150">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="08400-150">login.microsoftonline.com</span></span>
    - <span data-ttu-id="08400-151">*.blob.core.windows.net/networkscannerstable/*</span><span class="sxs-lookup"><span data-stu-id="08400-151">*.blob.core.windows.net/networkscannerstable/*</span></span>

    <span data-ttu-id="08400-152">Nota: Estas direcciones URL no se especifican en la lista documentada defender para endpoint de la colección de datos permitida.</span><span class="sxs-lookup"><span data-stu-id="08400-152">Note: These URLs are not specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="08400-153">Permisos</span><span class="sxs-lookup"><span data-stu-id="08400-153">Permissions</span></span>

<span data-ttu-id="08400-154">Para configurar trabajos de evaluación, se requiere la siguiente opción de permiso de usuario: **Administrar la configuración de seguridad en el Centro de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="08400-154">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="08400-155">Para encontrar el permiso, vaya a **Roles**  >  **de configuración**.</span><span class="sxs-lookup"><span data-stu-id="08400-155">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="08400-156">Para obtener más información, vea [Create and manage roles for role-based access control](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="08400-156">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="08400-157">Instalar el escáner de red</span><span class="sxs-lookup"><span data-stu-id="08400-157">Install the network scanner</span></span>

1. <span data-ttu-id="08400-158">Vaya a Trabajos de evaluación de puntos de conexión de configuración de seguridad de **Microsoft 365**  >    >    >   (en "Evaluaciones de red").</span><span class="sxs-lookup"><span data-stu-id="08400-158">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under 'Network assessments').</span></span>
    1. <span data-ttu-id="08400-159">En el Centro de seguridad de Microsoft Defender, vaya a Configuración y > de evaluación.</span><span class="sxs-lookup"><span data-stu-id="08400-159">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="08400-160">Descargue el escáner de red e instállo en el dispositivo de evaluación de Defender para endpoint designado.</span><span class="sxs-lookup"><span data-stu-id="08400-160">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

![Botón Descargar escáner](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="08400-162">Instalación del escáner de red & registro</span><span class="sxs-lookup"><span data-stu-id="08400-162">Network scanner installation & registration</span></span>

<span data-ttu-id="08400-163">El proceso de inicio de sesión se puede completar en el propio dispositivo de evaluación designado o en cualquier otro dispositivo (por ejemplo, el dispositivo cliente personal).</span><span class="sxs-lookup"><span data-stu-id="08400-163">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="08400-164">Para completar el proceso de registro del escáner de red:</span><span class="sxs-lookup"><span data-stu-id="08400-164">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="08400-165">Copie y siga la dirección URL que aparece en la línea de comandos y use el código de instalación proporcionado para completar el proceso de registro.</span><span class="sxs-lookup"><span data-stu-id="08400-165">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>
    - <span data-ttu-id="08400-166">Nota: Es posible que deba cambiar la configuración del símbolo del sistema para poder copiar la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="08400-166">Note: You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="08400-167">Escriba el código e inicie sesión con una cuenta de Microsoft que tenga el permiso Defender for Endpoint denominado "Administrar la configuración de seguridad en el Centro de seguridad".</span><span class="sxs-lookup"><span data-stu-id="08400-167">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="08400-168">Cuando haya terminado, debería ver un mensaje que confirme que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="08400-168">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="08400-169">Configurar un nuevo trabajo de evaluación</span><span class="sxs-lookup"><span data-stu-id="08400-169">Configure a new assessment job</span></span>  

<span data-ttu-id="08400-170">En la página Trabajos de evaluación **de Configuración,** seleccione **Agregar trabajo de evaluación de red**.</span><span class="sxs-lookup"><span data-stu-id="08400-170">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="08400-171">Siga el proceso de configuración para elegir los dispositivos de red que se examinarán periódicamente y se agregarán al inventario de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="08400-171">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="08400-172">Para evitar la duplicación de dispositivos en el inventario de dispositivos de red, asegúrese de que cada dirección IP esté configurada solo una vez en varios dispositivos de evaluación.</span><span class="sxs-lookup"><span data-stu-id="08400-172">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

![Botón Agregar trabajo de evaluación de red](images/assessment-jobs-add.png)

<span data-ttu-id="08400-174">Adición de pasos de trabajo de evaluación de red:</span><span class="sxs-lookup"><span data-stu-id="08400-174">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="08400-175">Elige un nombre de "Trabajo de evaluación" y el "Dispositivo de evaluación" en el que se instaló el escáner de red.</span><span class="sxs-lookup"><span data-stu-id="08400-175">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="08400-176">Este dispositivo realizará los exámenes periódicos autenticados.</span><span class="sxs-lookup"><span data-stu-id="08400-176">This device will perform the periodic authenticated scans.</span></span> 
2. <span data-ttu-id="08400-177">Agregue las direcciones IP de los dispositivos de red de destino que se van a examinar (o las subredes donde se implementan estos dispositivos).</span><span class="sxs-lookup"><span data-stu-id="08400-177">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 
3. <span data-ttu-id="08400-178">Agregue las credenciales SNMP necesarias de los dispositivos de red de destino.</span><span class="sxs-lookup"><span data-stu-id="08400-178">Add required SNMP credentials of the target network devices.</span></span> 
4. <span data-ttu-id="08400-179">Guarde el trabajo de evaluación de red recién configurado para iniciar el examen periódico de red.</span><span class="sxs-lookup"><span data-stu-id="08400-179">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="08400-180">Examinar y agregar dispositivos de red</span><span class="sxs-lookup"><span data-stu-id="08400-180">Scan and add network devices</span></span>

<span data-ttu-id="08400-181">Durante el proceso de configuración, puede realizar un examen de prueba de una sola vez para comprobar que:</span><span class="sxs-lookup"><span data-stu-id="08400-181">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="08400-182">Hay conectividad entre el dispositivo de evaluación de Defender para endpoints y los dispositivos de red de destino configurados.</span><span class="sxs-lookup"><span data-stu-id="08400-182">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="08400-183">Las credenciales SNMP configuradas son correctas.</span><span class="sxs-lookup"><span data-stu-id="08400-183">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="08400-184">Cada dispositivo de evaluación puede admitir hasta 1.500 direcciones IP correctas.</span><span class="sxs-lookup"><span data-stu-id="08400-184">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="08400-185">Por ejemplo, si analiza 10 subredes diferentes donde solo 100 direcciones IP devuelven resultados correctos, podrá examinar 1.400 direcciones IP adicionales de otras subredes en el mismo dispositivo de evaluación.</span><span class="sxs-lookup"><span data-stu-id="08400-185">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="08400-186">Si hay varios intervalos de direcciones IP/subredes que examinar, los resultados del examen de prueba tardarán varios minutos en aparecer.</span><span class="sxs-lookup"><span data-stu-id="08400-186">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="08400-187">Un examen de prueba estará disponible para hasta 1.024 direcciones.</span><span class="sxs-lookup"><span data-stu-id="08400-187">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="08400-188">Una vez que se muestren los resultados, puedes elegir qué dispositivos se incluirán en el examen periódico.</span><span class="sxs-lookup"><span data-stu-id="08400-188">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="08400-189">Si omites ver los resultados del examen, todas las direcciones IP configuradas se agregarán al trabajo de evaluación de red (independientemente de la respuesta del dispositivo).</span><span class="sxs-lookup"><span data-stu-id="08400-189">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="08400-190">Los resultados del examen también se pueden exportar.</span><span class="sxs-lookup"><span data-stu-id="08400-190">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="08400-191">Inventario de dispositivos</span><span class="sxs-lookup"><span data-stu-id="08400-191">Device inventory</span></span>

<span data-ttu-id="08400-192">Los dispositivos recién detectados se mostrarán en la nueva **pestaña Dispositivos de** red en la **página Inventario de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="08400-192">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="08400-193">Puede tardar hasta dos horas después de agregar un trabajo de evaluación hasta que los dispositivos se actualicen.</span><span class="sxs-lookup"><span data-stu-id="08400-193">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

![Sección Dispositivos de red en el inventario de dispositivos](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a><span data-ttu-id="08400-195">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="08400-195">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="08400-196">Error en la instalación del escáner de red</span><span class="sxs-lookup"><span data-stu-id="08400-196">Network scanner installation has failed</span></span>

<span data-ttu-id="08400-197">Compruebe que las direcciones URL necesarias se agregan a los dominios permitidos en la configuración del firewall.</span><span class="sxs-lookup"><span data-stu-id="08400-197">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="08400-198">Además, asegúrate de que las opciones de proxy estén configuradas como se describe en Configurar el proxy de dispositivo y [la configuración de conectividad a Internet](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="08400-198">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md)</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="08400-199">La Microsoft.com/devicelogin web no se hizo</span><span class="sxs-lookup"><span data-stu-id="08400-199">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="08400-200">Compruebe que las direcciones URL necesarias se agregan a los dominios permitidos en el firewall.</span><span class="sxs-lookup"><span data-stu-id="08400-200">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="08400-201">Además, asegúrate de que las opciones de proxy estén configuradas como se describe en [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="08400-201">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="08400-202">Los dispositivos de red no se muestran en el inventario de dispositivos después de varias horas</span><span class="sxs-lookup"><span data-stu-id="08400-202">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="08400-203">Los resultados del examen deben actualizarse unas horas después del examen inicial que se realizó después de completar la configuración del trabajo de evaluación.</span><span class="sxs-lookup"><span data-stu-id="08400-203">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="08400-204">Si aún no se muestran dispositivos, compruebe que el servicio 'MdatpNetworkScanService' se está ejecutando en los dispositivos de evaluación, en los que instaló el escáner de red, y realice un "Examen de ejecución" en la configuración del trabajo de evaluación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="08400-204">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="08400-205">Si aún no obtiene resultados después de 5 minutos, reinicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="08400-205">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="08400-206">El tiempo de vista por última vez de los dispositivos es de más de 24 horas</span><span class="sxs-lookup"><span data-stu-id="08400-206">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="08400-207">Valide que el escáner se está ejecutando correctamente.</span><span class="sxs-lookup"><span data-stu-id="08400-207">Validate that the scanner is running properly.</span></span> <span data-ttu-id="08400-208">A continuación, vaya a la definición de examen y seleccione "Ejecutar prueba".</span><span class="sxs-lookup"><span data-stu-id="08400-208">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="08400-209">Compruebe qué mensajes de error devuelven de las direcciones IP relevantes.</span><span class="sxs-lookup"><span data-stu-id="08400-209">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="08400-210">Permiso de usuario de administración de vulnerabilidades y amenazas requerido</span><span class="sxs-lookup"><span data-stu-id="08400-210">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="08400-211">El registro finalizó con un error: "Parece que no tiene permisos suficientes para agregar un nuevo agente.</span><span class="sxs-lookup"><span data-stu-id="08400-211">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="08400-212">El permiso requerido es "Administrar la configuración de seguridad en el Centro de seguridad".</span><span class="sxs-lookup"><span data-stu-id="08400-212">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="08400-213">Presione cualquier tecla para salir.</span><span class="sxs-lookup"><span data-stu-id="08400-213">Press any key to exit.</span></span>

<span data-ttu-id="08400-214">Pida al administrador del sistema que le asigne los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="08400-214">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="08400-215">Como alternativa, pida a otro miembro relevante que le ayude con el proceso de inicio de sesión proporcionando el código de inicio de sesión y el vínculo.</span><span class="sxs-lookup"><span data-stu-id="08400-215">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="08400-216">Error en el proceso de registro mediante el vínculo proporcionado en la línea de comandos en el proceso de registro</span><span class="sxs-lookup"><span data-stu-id="08400-216">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="08400-217">Pruebe con otro explorador o copie el vínculo de inicio de sesión y el código en un dispositivo diferente.</span><span class="sxs-lookup"><span data-stu-id="08400-217">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="08400-218">Texto demasiado pequeño o no puede copiar texto de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="08400-218">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="08400-219">Cambia la configuración de la línea de comandos en el dispositivo para permitir la copia y el tamaño del texto.</span><span class="sxs-lookup"><span data-stu-id="08400-219">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="08400-220">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="08400-220">Related articles</span></span>

- [<span data-ttu-id="08400-221">Inventario de dispositivos</span><span class="sxs-lookup"><span data-stu-id="08400-221">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="08400-222">Configurar funciones avanzadas</span><span class="sxs-lookup"><span data-stu-id="08400-222">Configure advanced features</span></span>](advanced-features.md)
