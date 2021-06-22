---
title: Detección de dispositivos de red y administración de vulnerabilidades
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
ms.openlocfilehash: 86b8a37fd6b2d6f9906321b5d74de0e21c45fca3
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062140"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="189e8-104">Detección de dispositivos de red y administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="189e8-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="189e8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="189e8-105">**Applies to:**</span></span>

- [<span data-ttu-id="189e8-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="189e8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="189e8-107">Amenaza y administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="189e8-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="189e8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="189e8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="189e8-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="189e8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="189e8-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="189e8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]  
> <span data-ttu-id="189e8-111">El Blog sobre detección de [dispositivos](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) de red y evaluaciones de vulnerabilidad publicado \( el 04-13-2021 proporciona información sobre las nuevas capacidades de detección de dispositivos de red en \) Defender para endpoint. </span><span class="sxs-lookup"><span data-stu-id="189e8-111">The [Network device discovery and vulnerability assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) Blog \(published 04-13-2021\) provides insights into the new **Network device discovery** capabilities in Defender for Endpoint.</span></span> <span data-ttu-id="189e8-112">En este artículo se proporciona  información general sobre el desafío que la detección de dispositivos de red está diseñada para abordar e información detallada sobre cómo empezar a usar estas nuevas funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="189e8-112">This article provides an overview of the challenge that **Network device discovery** is designed to address, and detailed information about how get started using these new capabilities.</span></span>

<span data-ttu-id="189e8-113">Las funcionalidades de detección de red están disponibles en la sección **Inventario** de dispositivos del centro Microsoft 365 seguridad y Centro de seguridad de Microsoft Defender consolas.</span><span class="sxs-lookup"><span data-stu-id="189e8-113">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="189e8-114">Se usará un dispositivo designado de Microsoft Defender para endpoint en cada segmento de red para realizar exámenes periódicos autenticados de dispositivos de red preconfigurados.</span><span class="sxs-lookup"><span data-stu-id="189e8-114">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="189e8-115">Una vez descubierto, las capacidades de Defender for Endpoint Administración de amenazas y vulnerabilidades proporcionan flujos de trabajo integrados para proteger conmutadores detectados, enrutadores, controladores WLAN, firewalls y puertas de enlace VPN.</span><span class="sxs-lookup"><span data-stu-id="189e8-115">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="189e8-116">Una vez detectados y clasificados los dispositivos de red, los administradores de seguridad podrán recibir las recomendaciones de seguridad más recientes y revisar las vulnerabilidades detectadas recientemente en los dispositivos de red implementados en sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="189e8-116">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="189e8-117">Enfoque</span><span class="sxs-lookup"><span data-stu-id="189e8-117">Approach</span></span>

<span data-ttu-id="189e8-118">Los dispositivos de red no se administran como puntos de conexión estándar, ya que Defender for Endpoint no tiene un sensor integrado en los propios dispositivos de red.</span><span class="sxs-lookup"><span data-stu-id="189e8-118">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="189e8-119">Estos tipos de dispositivos requieren un enfoque sin agente donde un examen remoto obtendrá la información necesaria de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="189e8-119">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="189e8-120">Según la topología y las características de red, un solo dispositivo o algunos dispositivos incorporados a Microsoft Defender para Endpoint realizarán exámenes autenticados de dispositivos de red mediante SNMP (solo lectura).</span><span class="sxs-lookup"><span data-stu-id="189e8-120">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="189e8-121">Habrá dos tipos de dispositivos a tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="189e8-121">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="189e8-122">**Dispositivo de evaluación:** un dispositivo que ya está incorporado y que usarás para examinar los dispositivos de red.</span><span class="sxs-lookup"><span data-stu-id="189e8-122">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="189e8-123">**Dispositivos de** red: los dispositivos de red que tiene previsto examinar e incorporar.</span><span class="sxs-lookup"><span data-stu-id="189e8-123">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="189e8-124">Administración de vulnerabilidades para dispositivos de red</span><span class="sxs-lookup"><span data-stu-id="189e8-124">Vulnerability management for network devices</span></span> 

<span data-ttu-id="189e8-125">Una vez detectados y clasificados los dispositivos de red, los administradores de seguridad podrán recibir las recomendaciones de seguridad más recientes y revisar las vulnerabilidades detectadas recientemente en los dispositivos de red implementados en sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="189e8-125">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="189e8-126">Sistemas operativos compatibles</span><span class="sxs-lookup"><span data-stu-id="189e8-126">Operating systems that are supported</span></span>

<span data-ttu-id="189e8-127">Actualmente se admiten los siguientes sistemas operativos:</span><span class="sxs-lookup"><span data-stu-id="189e8-127">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="189e8-128">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="189e8-128">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="189e8-129">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="189e8-129">Juniper JUNOS</span></span>
- <span data-ttu-id="189e8-130">HPE ArubaOS, Software de conmutador procurve</span><span class="sxs-lookup"><span data-stu-id="189e8-130">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="189e8-131">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="189e8-131">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="189e8-132">Se agregarán más proveedores de redes y sos con el tiempo, en función de los datos recopilados por el uso del cliente.</span><span class="sxs-lookup"><span data-stu-id="189e8-132">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="189e8-133">Por lo tanto, se recomienda configurar todos los dispositivos de red, incluso si no están especificados en esta lista.</span><span class="sxs-lookup"><span data-stu-id="189e8-133">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="189e8-134">Como empezar</span><span class="sxs-lookup"><span data-stu-id="189e8-134">How to get started</span></span>

<span data-ttu-id="189e8-135">El primer paso es seleccionar un dispositivo que realizará los exámenes de red autenticados.</span><span class="sxs-lookup"><span data-stu-id="189e8-135">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="189e8-136">Decide un dispositivo integrado de Defender for Endpoint (cliente o servidor) que tenga una conexión de red al puerto de administración de los dispositivos de red que planeas examinar.</span><span class="sxs-lookup"><span data-stu-id="189e8-136">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="189e8-137">Se debe permitir el tráfico SNMP entre el dispositivo de evaluación de Defender para endpoints y los dispositivos de red de destino (por ejemplo, mediante el Firewall).</span><span class="sxs-lookup"><span data-stu-id="189e8-137">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="189e8-138">Decida qué dispositivos de red se evaluarán para las vulnerabilidades (por ejemplo: un conmutador cisco o un firewall de Palo Alto Networks).</span><span class="sxs-lookup"><span data-stu-id="189e8-138">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="189e8-139">Asegúrese de que SNMP de solo lectura está habilitado en todos los dispositivos de red configurados para permitir que el dispositivo de evaluación de Defender for Endpoint consulte los dispositivos de red configurados.</span><span class="sxs-lookup"><span data-stu-id="189e8-139">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="189e8-140">La "escritura SNMP" no es necesaria para la funcionalidad adecuada de esta característica.</span><span class="sxs-lookup"><span data-stu-id="189e8-140">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="189e8-141">Obtener las direcciones IP de los dispositivos de red que se van a examinar (o las subredes donde se implementan estos dispositivos).</span><span class="sxs-lookup"><span data-stu-id="189e8-141">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="189e8-142">Obtenga las credenciales SNMP de los dispositivos de red (por ejemplo: Community String, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="189e8-142">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="189e8-143">Tendrás que proporcionar las credenciales al configurar un nuevo trabajo de evaluación.</span><span class="sxs-lookup"><span data-stu-id="189e8-143">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="189e8-144">Configuración del cliente proxy: no se requiere ninguna configuración adicional que no sea los requisitos de proxy de dispositivo defender para extremo.</span><span class="sxs-lookup"><span data-stu-id="189e8-144">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="189e8-145">Para permitir que el escáner de red se autentique y funcione correctamente, es esencial que agregue los siguientes dominios o direcciones URL:</span><span class="sxs-lookup"><span data-stu-id="189e8-145">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="189e8-146">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="189e8-146">login.windows.net</span></span>  
    - <span data-ttu-id="189e8-147">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="189e8-147">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="189e8-148">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="189e8-148">login.microsoftonline.com</span></span>
    - <span data-ttu-id="189e8-149">\*.blob.core.windows.net/networkscannerstable/ \*</span><span class="sxs-lookup"><span data-stu-id="189e8-149">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    > [!NOTE]
    > <span data-ttu-id="189e8-150">No todas las direcciones URL se especifican en la lista documentada Defender for Endpoint de la colección de datos permitida.</span><span class="sxs-lookup"><span data-stu-id="189e8-150">Not all URLs are specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="189e8-151">Permisos</span><span class="sxs-lookup"><span data-stu-id="189e8-151">Permissions</span></span>

<span data-ttu-id="189e8-152">Para configurar trabajos de evaluación, se requiere la siguiente opción de permiso de usuario: **Administrar la configuración de seguridad en el Centro de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="189e8-152">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="189e8-153">Para encontrar el permiso, vaya a **Configuración**  >  **Roles**.</span><span class="sxs-lookup"><span data-stu-id="189e8-153">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="189e8-154">Para obtener más información, vea [Create and manage roles for role-based access control](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="189e8-154">For more information, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="189e8-155">Instalar el escáner de red</span><span class="sxs-lookup"><span data-stu-id="189e8-155">Install the network scanner</span></span>

1. <span data-ttu-id="189e8-156">Vaya a Microsoft 365 **de Configuración** de evaluación de puntos de conexión  >    >    >   (en **Evaluaciones de red).**</span><span class="sxs-lookup"><span data-stu-id="189e8-156">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under **Network assessments**).</span></span>
    1. <span data-ttu-id="189e8-157">En la Centro de seguridad de Microsoft Defender, vaya a Configuración > de trabajos de evaluación.</span><span class="sxs-lookup"><span data-stu-id="189e8-157">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="189e8-158">Descargue el escáner de red e instállo en el dispositivo de evaluación de Defender para endpoint designado.</span><span class="sxs-lookup"><span data-stu-id="189e8-158">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="189e8-159">![Botón Descargar escáner](images/assessment-jobs-download-scanner.png)</span><span class="sxs-lookup"><span data-stu-id="189e8-159">![Download scanner button](images/assessment-jobs-download-scanner.png)</span></span>

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="189e8-160">Instalación del escáner de red & registro</span><span class="sxs-lookup"><span data-stu-id="189e8-160">Network scanner installation & registration</span></span>

<span data-ttu-id="189e8-161">El proceso de inicio de sesión se puede completar en el propio dispositivo de evaluación designado o en cualquier otro dispositivo (por ejemplo, el dispositivo cliente personal).</span><span class="sxs-lookup"><span data-stu-id="189e8-161">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="189e8-162">Para completar el proceso de registro del escáner de red:</span><span class="sxs-lookup"><span data-stu-id="189e8-162">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="189e8-163">Copie y siga la dirección URL que aparece en la línea de comandos y use el código de instalación proporcionado para completar el proceso de registro.</span><span class="sxs-lookup"><span data-stu-id="189e8-163">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="189e8-164">Es posible que deba cambiar la configuración del símbolo del sistema para poder copiar la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="189e8-164">You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="189e8-165">Escriba el código e inicie sesión con una cuenta de Microsoft que tenga el permiso Defender for Endpoint denominado "Administrar la configuración de seguridad en el Centro de seguridad".</span><span class="sxs-lookup"><span data-stu-id="189e8-165">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="189e8-166">Cuando haya terminado, debería ver un mensaje que confirme que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="189e8-166">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="189e8-167">Configurar un nuevo trabajo de evaluación</span><span class="sxs-lookup"><span data-stu-id="189e8-167">Configure a new assessment job</span></span>  

<span data-ttu-id="189e8-168">En la página Trabajos de evaluación **de Configuración**, seleccione Agregar trabajo de evaluación **de red**.</span><span class="sxs-lookup"><span data-stu-id="189e8-168">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="189e8-169">Siga el proceso de configuración para elegir los dispositivos de red que se examinarán periódicamente y se agregarán al inventario de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="189e8-169">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="189e8-170">Para evitar la duplicación de dispositivos en el inventario de dispositivos de red, asegúrese de que cada dirección IP esté configurada solo una vez en varios dispositivos de evaluación.</span><span class="sxs-lookup"><span data-stu-id="189e8-170">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="189e8-171">![Botón Agregar trabajo de evaluación de red](images/assessment-jobs-add.png)</span><span class="sxs-lookup"><span data-stu-id="189e8-171">![Add network assessment job button](images/assessment-jobs-add.png)</span></span>

<span data-ttu-id="189e8-172">Adición de pasos de trabajo de evaluación de red:</span><span class="sxs-lookup"><span data-stu-id="189e8-172">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="189e8-173">Elige un nombre de "Trabajo de evaluación" y el "Dispositivo de evaluación" en el que se instaló el escáner de red.</span><span class="sxs-lookup"><span data-stu-id="189e8-173">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="189e8-174">Este dispositivo realizará los exámenes periódicos autenticados.</span><span class="sxs-lookup"><span data-stu-id="189e8-174">This device will perform the periodic authenticated scans.</span></span>

2. <span data-ttu-id="189e8-175">Agregue las direcciones IP de los dispositivos de red de destino que se van a examinar (o las subredes donde se implementan estos dispositivos).</span><span class="sxs-lookup"><span data-stu-id="189e8-175">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 

3. <span data-ttu-id="189e8-176">Agregue las credenciales SNMP necesarias de los dispositivos de red de destino.</span><span class="sxs-lookup"><span data-stu-id="189e8-176">Add required SNMP credentials of the target network devices.</span></span> 

4. <span data-ttu-id="189e8-177">Guarde el trabajo de evaluación de red recién configurado para iniciar el examen periódico de red.</span><span class="sxs-lookup"><span data-stu-id="189e8-177">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="189e8-178">Examinar y agregar dispositivos de red</span><span class="sxs-lookup"><span data-stu-id="189e8-178">Scan and add network devices</span></span>

<span data-ttu-id="189e8-179">Durante el proceso de configuración, puede realizar un examen de prueba de una sola vez para comprobar que:</span><span class="sxs-lookup"><span data-stu-id="189e8-179">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="189e8-180">Hay conectividad entre el dispositivo de evaluación de Defender para endpoints y los dispositivos de red de destino configurados.</span><span class="sxs-lookup"><span data-stu-id="189e8-180">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="189e8-181">Las credenciales SNMP configuradas son correctas.</span><span class="sxs-lookup"><span data-stu-id="189e8-181">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="189e8-182">Cada dispositivo de evaluación puede admitir hasta 1.500 direcciones IP correctas.</span><span class="sxs-lookup"><span data-stu-id="189e8-182">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="189e8-183">Por ejemplo, si analiza 10 subredes diferentes donde solo 100 direcciones IP devuelven resultados correctos, podrá examinar 1.400 direcciones IP adicionales de otras subredes en el mismo dispositivo de evaluación.</span><span class="sxs-lookup"><span data-stu-id="189e8-183">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="189e8-184">Si hay varios intervalos de direcciones IP/subredes que examinar, los resultados del examen de prueba tardarán varios minutos en aparecer.</span><span class="sxs-lookup"><span data-stu-id="189e8-184">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="189e8-185">Un examen de prueba estará disponible para hasta 1.024 direcciones.</span><span class="sxs-lookup"><span data-stu-id="189e8-185">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="189e8-186">Una vez que se muestren los resultados, puedes elegir qué dispositivos se incluirán en el examen periódico.</span><span class="sxs-lookup"><span data-stu-id="189e8-186">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="189e8-187">Si omites ver los resultados del examen, todas las direcciones IP configuradas se agregarán al trabajo de evaluación de red (independientemente de la respuesta del dispositivo).</span><span class="sxs-lookup"><span data-stu-id="189e8-187">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="189e8-188">Los resultados del examen también se pueden exportar.</span><span class="sxs-lookup"><span data-stu-id="189e8-188">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="189e8-189">Inventario de dispositivos</span><span class="sxs-lookup"><span data-stu-id="189e8-189">Device inventory</span></span>

<span data-ttu-id="189e8-190">Los dispositivos recién detectados se mostrarán en la nueva **pestaña Dispositivos de** red en la **página Inventario de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="189e8-190">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="189e8-191">Puede tardar hasta dos horas después de agregar un trabajo de evaluación hasta que los dispositivos se actualicen.</span><span class="sxs-lookup"><span data-stu-id="189e8-191">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="189e8-192">![Sección Dispositivos de red en el inventario de dispositivos](images/assessment-jobs-device-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="189e8-192">![Network devices section in the Device inventory](images/assessment-jobs-device-inventory.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="189e8-193">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="189e8-193">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="189e8-194">Error en la instalación del escáner de red</span><span class="sxs-lookup"><span data-stu-id="189e8-194">Network scanner installation has failed</span></span>

<span data-ttu-id="189e8-195">Compruebe que las direcciones URL necesarias se agregan a los dominios permitidos en la configuración del firewall.</span><span class="sxs-lookup"><span data-stu-id="189e8-195">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="189e8-196">Además, asegúrate de que las opciones de proxy estén configuradas como se describe en [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="189e8-196">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="189e8-197">La Microsoft.com/devicelogin web no se hizo</span><span class="sxs-lookup"><span data-stu-id="189e8-197">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="189e8-198">Compruebe que las direcciones URL necesarias se agregan a los dominios permitidos en el firewall.</span><span class="sxs-lookup"><span data-stu-id="189e8-198">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="189e8-199">Además, asegúrate de que las opciones de proxy estén configuradas como se describe en [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="189e8-199">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="189e8-200">Los dispositivos de red no se muestran en el inventario de dispositivos después de varias horas</span><span class="sxs-lookup"><span data-stu-id="189e8-200">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="189e8-201">Los resultados del examen deben actualizarse unas horas después del examen inicial que se realizó después de completar la configuración del trabajo de evaluación.</span><span class="sxs-lookup"><span data-stu-id="189e8-201">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="189e8-202">Si aún no se muestran dispositivos, compruebe que el servicio 'MdatpNetworkScanService' se está ejecutando en los dispositivos de evaluación, en los que instaló el escáner de red, y realice un "Examen de ejecución" en la configuración del trabajo de evaluación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="189e8-202">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="189e8-203">Si aún no obtiene resultados después de 5 minutos, reinicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="189e8-203">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="189e8-204">El tiempo de vista por última vez de los dispositivos es de más de 24 horas</span><span class="sxs-lookup"><span data-stu-id="189e8-204">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="189e8-205">Valide que el escáner se está ejecutando correctamente.</span><span class="sxs-lookup"><span data-stu-id="189e8-205">Validate that the scanner is running properly.</span></span> <span data-ttu-id="189e8-206">A continuación, vaya a la definición de examen y seleccione "Ejecutar prueba".</span><span class="sxs-lookup"><span data-stu-id="189e8-206">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="189e8-207">Compruebe qué mensajes de error devuelven de las direcciones IP relevantes.</span><span class="sxs-lookup"><span data-stu-id="189e8-207">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="189e8-208">Permiso Administración de amenazas y vulnerabilidades usuario requerido</span><span class="sxs-lookup"><span data-stu-id="189e8-208">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="189e8-209">El registro finalizó con un error: "Parece que no tiene permisos suficientes para agregar un nuevo agente.</span><span class="sxs-lookup"><span data-stu-id="189e8-209">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="189e8-210">El permiso requerido es "Administrar la configuración de seguridad en el Centro de seguridad".</span><span class="sxs-lookup"><span data-stu-id="189e8-210">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="189e8-211">Presione cualquier tecla para salir.</span><span class="sxs-lookup"><span data-stu-id="189e8-211">Press any key to exit.</span></span>

<span data-ttu-id="189e8-212">Pida al administrador del sistema que le asigne los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="189e8-212">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="189e8-213">Como alternativa, pida a otro miembro relevante que le ayude con el proceso de inicio de sesión proporcionando el código de inicio de sesión y el vínculo.</span><span class="sxs-lookup"><span data-stu-id="189e8-213">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="189e8-214">Error en el proceso de registro mediante el vínculo proporcionado en la línea de comandos en el proceso de registro</span><span class="sxs-lookup"><span data-stu-id="189e8-214">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="189e8-215">Pruebe con otro explorador o copie el vínculo de inicio de sesión y el código en un dispositivo diferente.</span><span class="sxs-lookup"><span data-stu-id="189e8-215">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="189e8-216">Texto demasiado pequeño o no puede copiar texto de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="189e8-216">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="189e8-217">Cambia la configuración de la línea de comandos en el dispositivo para permitir la copia y el tamaño del texto.</span><span class="sxs-lookup"><span data-stu-id="189e8-217">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="189e8-218">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="189e8-218">Related articles</span></span>

- [<span data-ttu-id="189e8-219">Inventario de dispositivos</span><span class="sxs-lookup"><span data-stu-id="189e8-219">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="189e8-220">Configurar funciones avanzadas</span><span class="sxs-lookup"><span data-stu-id="189e8-220">Configure advanced features</span></span>](advanced-features.md)
