<a name="crit-windows10-step1"></a>
### <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="69b30-101">Necesario: Los dominios de Microsoft 365 se agregan y comprueban</span><span class="sxs-lookup"><span data-stu-id="69b30-101">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="69b30-102">El inquilino de Azure AD para sus suscripciones de Office 365 e Intune está configurado con sus nombres de dominio de Internet (por ejemplo, contoso.com), en lugar de solo un nombre de dominio que incluya "onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="69b30-102">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="69b30-p101">Si no lo hace, estará limitando los métodos de autenticación que puede configurar. Por ejemplo, el paso a través y la autenticación federada no pueden usar el nombre de dominio de "onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="69b30-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="69b30-105">Si es necesario, el [paso 1](../windows10-prepare-your-org.md) puede ayudarle con este requisito.</span><span class="sxs-lookup"><span data-stu-id="69b30-105">If needed, [Step 1](../windows10-prepare-your-org.md) can help you with this requirement.</span></span>

### <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="69b30-106">Opcional: Los usuarios se agregan y reciben una licencia</span><span class="sxs-lookup"><span data-stu-id="69b30-106">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="69b30-107">Se agregan las cuentas correspondientes a los usuarios, ya sea directamente a su inquilino de Azure AD para sus suscripciones de Office 365 e Intune o a partir de la sincronización de directorios del servidor local de los servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="69b30-107">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Active Directory Domain Services (AD DS).</span></span>

<span data-ttu-id="69b30-108">Cuando se agregan los usuarios, puede asignarles licencias de Microsoft 365 Enterprise, directamente como un administrador global o de usuarios, o automáticamente a través de la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="69b30-108">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="69b30-109">Si es necesario, el [paso 1](../windows10-prepare-your-org.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="69b30-109">If needed, [Step 1](../windows10-prepare-your-org.md) can help you with this option.</span></span>

### <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="69b30-110">Opcional: el diagnóstico está habilitado</span><span class="sxs-lookup"><span data-stu-id="69b30-110">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="69b30-111">Se ha habilitado la configuración de datos de diagnóstico mediante Directiva de grupo, Microsoft Intune, el Editor del Registro o en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="69b30-111">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="69b30-112">Si es necesario, el [paso 1](../windows10-prepare-your-org.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="69b30-112">If needed, [Step 1](../windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
### <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="69b30-113">Para la actualización local: crear una secuencia de tareas de Configuration Manager para una implementación de sistema operativo</span><span class="sxs-lookup"><span data-stu-id="69b30-113">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="69b30-114">Para iniciar una secuencia de tareas de Configuration Manager con el fin de realizar una actualización local en un dispositivo con Windows 7 o Windows 8.1, debe:</span><span class="sxs-lookup"><span data-stu-id="69b30-114">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="69b30-115">Establecer el nivel de datos de diagnóstico de Windows adecuado</span><span class="sxs-lookup"><span data-stu-id="69b30-115">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="69b30-116">Haber comprobado la preparación para actualizar Windows</span><span class="sxs-lookup"><span data-stu-id="69b30-116">Verified the readiness to upgrade Windows</span></span>
- <span data-ttu-id="69b30-117">Haber creado la secuencia de tareas de Configuration Manager que incluya una colección de dispositivos y una implementación de sistema operativo con una imagen de sistema operativo de Windows 10</span><span class="sxs-lookup"><span data-stu-id="69b30-117">Created a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="69b30-p102">Una vez hecho todo esto, puede realizar actualizaciones en los dispositivos que están preparados para actualizar Windows. Para obtener el máximo partido de Microsoft 365 Enterprise, actualice tantos dispositivos que utilicen Windows 7 y Windows 8.1 como sea posible.</span><span class="sxs-lookup"><span data-stu-id="69b30-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="69b30-p103">Cada dispositivo con Windows 10 Enterprise puede beneficiarse de las ventajas de la solución integrada de Microsoft 365 Enterprise. Los dispositivos con Windows 7 o Windows 8.1 restantes no pueden usar las tecnologías conectadas a la nube ni las características de seguridad avanzadas de Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="69b30-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="69b30-122">Si es necesario, el [paso 2](../windows10-deploy-inplaceupgrade.md) puede ayudarle con este requisito.</span><span class="sxs-lookup"><span data-stu-id="69b30-122">If needed, [Step 2](../windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
### <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="69b30-123">Necesario para los nuevos dispositivos: configurar Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="69b30-123">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="69b30-124">Para usar Windows Autopilot con el fin de implementar y personalizar Windows 10 Enterprise en un dispositivo nuevo, debe:</span><span class="sxs-lookup"><span data-stu-id="69b30-124">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="69b30-125">Haber configurado el nivel de datos de diagnóstico de Windows adecuado</span><span class="sxs-lookup"><span data-stu-id="69b30-125">Configured the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="69b30-126">Haber configurado los requisitos previos de Windows Autopilot, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="69b30-126">Configured the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="69b30-127">El registro de dispositivos y la personalización de la configuración rápida</span><span class="sxs-lookup"><span data-stu-id="69b30-127">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="69b30-128">Personalización de marca para configuración rápida</span><span class="sxs-lookup"><span data-stu-id="69b30-128">Company branding for OOBE</span></span>
   - <span data-ttu-id="69b30-129">Inscripción automática de MDM en Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="69b30-129">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="69b30-130">Conectividad de red a servicios en la nube usados por Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="69b30-130">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="69b30-131">Los dispositivos que tienen preinstalado Windows 10, versión 1703 o posterior</span><span class="sxs-lookup"><span data-stu-id="69b30-131">Devices that are pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="69b30-132">Seleccionado el Programa de implementación de Windows Autopilot para su organización</span><span class="sxs-lookup"><span data-stu-id="69b30-132">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="69b30-133">Una vez que se ha realizado la configuración de Windows Autopilot, puede usarlo para configurar y personalizar Windows 10 Enterprise para la configuración rápida (OOBE) de:</span><span class="sxs-lookup"><span data-stu-id="69b30-133">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="69b30-134">Nuevos dispositivos</span><span class="sxs-lookup"><span data-stu-id="69b30-134">New devices</span></span>
- <span data-ttu-id="69b30-135">Dispositivos que ya han completado una configuración de fábrica en su organización.</span><span class="sxs-lookup"><span data-stu-id="69b30-135">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="69b30-136">Windows Autopilot configura el dispositivo y lo conecta a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="69b30-136">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="69b30-137">Sin Windows Autopilot, debe configurar manualmente los nuevos dispositivos, incluida la conexión a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="69b30-137">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="69b30-138">Si es necesario, el [paso 3](../windows10-deploy-autopilot.md) puede ayudarle con este requisito.</span><span class="sxs-lookup"><span data-stu-id="69b30-138">If needed, [Step 3](../windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
### <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="69b30-139">Opcional: Usa Estado de dispositivos de Windows Analytics para supervisar los dispositivos con Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="69b30-139">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="69b30-p104">Usó la información de Supervisar el estado de los dispositivos con Estado del dispositivo para detectar y solucionar los problemas que afectan a los usuarios finales. Tratar rápidamente los problemas de los usuarios finales puede reducir los costos de soporte técnico y mostrar a los usuarios el compromiso de TI con Windows 10 Enterprise, lo que puede ayudarle a impulsar la adopción en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="69b30-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="69b30-142">Si es necesario, el [paso 4](../windows10-enable-windows-analytics.md) puede ayudarle con esta opción.</span><span class="sxs-lookup"><span data-stu-id="69b30-142">If needed, [Step 4](../windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
### <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="69b30-143">Necesario: Usa Antivirus de Windows Defender o su propia solución antimalware</span><span class="sxs-lookup"><span data-stu-id="69b30-143">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="69b30-p105">Implementó Antivirus de Windows Defender o su propia solución antivirus para proteger los dispositivos que ejecutan Windows 10 Enterprise contra software malintencionado. Si implementó el Antivirus de Windows Defender, ha implementado un método de creación de informes, como Microsoft Endpoint Configuration Manager o Microsoft Intune, para supervisar la actividad y los eventos del antivirus.</span><span class="sxs-lookup"><span data-stu-id="69b30-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as Microsoft Endpoint Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="69b30-146">Si es necesario, el [paso 5](../windows10-enable-security-features.md#windows10-sec-av) puede ayudarle con este requisito.</span><span class="sxs-lookup"><span data-stu-id="69b30-146">If needed, [Step 5](../windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
### <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="69b30-147">Necesario: Usa Protección contra vulnerabilidades de seguridad de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="69b30-147">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="69b30-148">Implementó Protección contra vulnerabilidades de seguridad de Windows Defender para proteger los dispositivos que ejecutan Windows 10 Enterprise contra intrusiones y ha implementado un método de creación de informes, como Administrador de configuración o Microsoft Intune, para supervisar la actividad y los eventos de intrusión.</span><span class="sxs-lookup"><span data-stu-id="69b30-148">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="69b30-149">Si es necesario, el [paso 5](../windows10-enable-security-features.md#windows10-sec-eg) puede ayudarle con este requisito.</span><span class="sxs-lookup"><span data-stu-id="69b30-149">If needed, [Step 5](../windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
### <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a><span data-ttu-id="69b30-150">Necesario: Usa Protección contra amenazas avanzada de Microsoft Defender (solo Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="69b30-150">Required: You are using Microsoft Defender Advanced Threat Protection (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="69b30-151">Implementó Protección contra amenazas avanzada de Microsoft Defender (ATP) para detectar, investigar y responder a las amenazas avanzadas contra su red y los dispositivos que ejecutan Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="69b30-151">You deployed Microsoft Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="69b30-152">Opcionalmente, ha integrado Microsoft Defender ATP con otras herramientas para ampliar sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="69b30-152">Optionally, you have integrated Microsoft Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="69b30-153">Si es necesario, el [paso 5](../windows10-enable-security-features.md#windows10-sec-atp) puede ayudarle con este requisito.</span><span class="sxs-lookup"><span data-stu-id="69b30-153">If needed, [Step 5](../windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>
