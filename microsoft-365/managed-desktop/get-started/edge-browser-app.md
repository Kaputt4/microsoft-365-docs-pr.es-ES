---
title: Nuevo Microsoft Edge
description: ''
keywords: explorador, escritorio administrado por Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f4bc5f85b21148c5a923ca1fc18879a193191c4b
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094791"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="cb61d-103">Nueva aplicación Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cb61d-103">New Microsoft Edge app</span></span>

<span data-ttu-id="cb61d-104">El nuevo [Explorador de Microsoft Edge](https://www.microsoft.com/edge) proporciona un rendimiento de primera clase con más privacidad, más productividad y más valor mientras se navega.</span><span class="sxs-lookup"><span data-stu-id="cb61d-104">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="cb61d-105">El escritorio administrado de Microsoft ofrece una vista previa pública de la implementación del nuevo explorador perimetral en su entorno.</span><span class="sxs-lookup"><span data-stu-id="cb61d-105">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="cb61d-106">Implementación inicial</span><span class="sxs-lookup"><span data-stu-id="cb61d-106">Initial deployment</span></span>

<span data-ttu-id="cb61d-107">Para migrar los dispositivos de escritorio administrados por Microsoft al nuevo explorador Microsoft Edge, archivo un vale de soporte técnico de ti a través del portal de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cb61d-107">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="cb61d-108">Se implementará el canal estable del perímetro en el grupo de prueba cuando se archiva el vale y, a continuación, se implementa en cada grupo de implementación subsiguiente cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="cb61d-108">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="cb61d-109">Para pausar la implementación, archivo otro que pregunte a las operaciones que hay que conservar.</span><span class="sxs-lookup"><span data-stu-id="cb61d-109">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="cb61d-110">Actualizaciones de Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cb61d-110">Updates to Microsoft Edge</span></span>

<span data-ttu-id="cb61d-111">Microsoft Managed Desktop implementa el [canal estable](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) de Microsoft Edge, que se actualiza automáticamente cada seis semanas.</span><span class="sxs-lookup"><span data-stu-id="cb61d-111">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge which is auto-updated about every six weeks.</span></span> <span data-ttu-id="cb61d-112">El grupo de productos Microsoft Edge distribuye [progresivamente](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) las actualizaciones en el canal estable para garantizar la mejor experiencia para los clientes.</span><span class="sxs-lookup"><span data-stu-id="cb61d-112">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> <span data-ttu-id="cb61d-113">El canal de la versión beta de Microsoft Edge no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="cb61d-113">The Microsoft Edge Beta channel is not currently available.</span></span>

<span data-ttu-id="cb61d-114">Para asegurarse de que Microsoft Edge se actualiza correctamente, no modifique las [directivas de actualización](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)de Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="cb61d-114">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="cb61d-115">Configuración administrada por el escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="cb61d-115">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="cb61d-116">Microsoft Managed Desktop ha creado un conjunto de directivas predeterminado para Microsoft Edge para proteger el explorador.</span><span class="sxs-lookup"><span data-stu-id="cb61d-116">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="cb61d-117">La configuración predeterminada del explorador es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="cb61d-117">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="cb61d-118">Extensiones de Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cb61d-118">Microsoft Edge extensions</span></span>

<span data-ttu-id="cb61d-119">La línea base de seguridad para Microsoft Edge en dispositivos de escritorio administrados de Microsoft establece dos directivas para deshabilitar todas las extensiones de Chrome y los usuarios finales seguros.</span><span class="sxs-lookup"><span data-stu-id="cb61d-119">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure end users.</span></span> <span data-ttu-id="cb61d-120">Para habilitar e implementar extensiones en su entorno, vea la configuración que administre.</span><span class="sxs-lookup"><span data-stu-id="cb61d-120">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="cb61d-121">Lista de bloqueo de instalación de extensión</span><span class="sxs-lookup"><span data-stu-id="cb61d-121">Extension installation blocklist</span></span>
<span data-ttu-id="cb61d-122">**Valor predeterminado:** Todos</span><span class="sxs-lookup"><span data-stu-id="cb61d-122">**Default value:** All</span></span>

<span data-ttu-id="cb61d-123">El escritorio administrado de Microsoft establece esta directiva para evitar que se instalen extensiones de Chrome en los extremos administrados.</span><span class="sxs-lookup"><span data-stu-id="cb61d-123">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="cb61d-124">Se conocen risksassociated con el modelo de extensión de cromo, incluida la protección contra la pérdida de datos, la privacidad y otros riesgos que pueden poner en peligro los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="cb61d-124">There are known risksassociated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="cb61d-125">Permitir hosts de mensajería nativa en el nivel de usuario (instalado sin permisos de administrador)</span><span class="sxs-lookup"><span data-stu-id="cb61d-125">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="cb61d-126">**Valor predeterminado:** Capacidad</span><span class="sxs-lookup"><span data-stu-id="cb61d-126">**Default value:** Disabled</span></span>

<span data-ttu-id="cb61d-127">Al deshabilitar esta Directiva, Microsoft Edge solo usará los hosts de mensajería nativa instalados en el nivel del sistema.</span><span class="sxs-lookup"><span data-stu-id="cb61d-127">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="cb61d-128">Los hosts de mensajería nativa forman parte de las extensiones de Chrome que permiten al explorador interactuar con otras partes del extremo del usuario, lo que crea una gran variedad de problemas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cb61d-128">Native messaging hosts are a part of Chrome extensions which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-ssl"></a><span data-ttu-id="cb61d-129">Capa de sockets seguros (SSL)</span><span class="sxs-lookup"><span data-stu-id="cb61d-129">Secure Sockets Layer (SSL)</span></span>

#### <a name="minimum-ssl-version"></a><span data-ttu-id="cb61d-130">Versión mínima de SSL</span><span class="sxs-lookup"><span data-stu-id="cb61d-130">Minimum SSL version</span></span>

<span data-ttu-id="cb61d-131">**Valor predeterminado:** Compatible con TLS 1,2 mínimo</span><span class="sxs-lookup"><span data-stu-id="cb61d-131">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="cb61d-132">Si desea usar el TLS 1,1 menos seguro, puede solicitar esto.</span><span class="sxs-lookup"><span data-stu-id="cb61d-132">If you want to use the less secure TLS 1.1, you can request this.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="cb61d-133">Permite a los usuarios continuar desde la página de advertencia de SSL</span><span class="sxs-lookup"><span data-stu-id="cb61d-133">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="cb61d-134">**Valor predeterminado:** Capacidad</span><span class="sxs-lookup"><span data-stu-id="cb61d-134">**Default value:** Disabled</span></span>

<span data-ttu-id="cb61d-135">No se recomienda habilitar esta configuración, ya que permite a los usuarios visitar sitios con errores de SSL.</span><span class="sxs-lookup"><span data-stu-id="cb61d-135">We don't recommend enabling this setting since it allows users to visit sites with SSL errors.</span></span>

### <a name="microsoft-defender-smart-screen"></a><span data-ttu-id="cb61d-136">Pantalla inteligente de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="cb61d-136">Microsoft Defender Smart Screen</span></span>

#### <a name="configure-microsoft-defender-smartscreen"></a><span data-ttu-id="cb61d-137">Configurar SmartScreen de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="cb61d-137">Configure Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="cb61d-138">**Valor predeterminado:** Preparado</span><span class="sxs-lookup"><span data-stu-id="cb61d-138">**Default value:** Enabled</span></span>

<span data-ttu-id="cb61d-139">Está habilitado de forma predeterminada para ayudar a proteger a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="cb61d-139">Enabled by default to help protect end users.</span></span>

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="cb61d-140">Avisos SmartScreen de Microsoft defender para sitios</span><span class="sxs-lookup"><span data-stu-id="cb61d-140">Microsoft Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="cb61d-141">**Valor predeterminado:** Preparado</span><span class="sxs-lookup"><span data-stu-id="cb61d-141">**Default value:** Enabled</span></span>

<span data-ttu-id="cb61d-142">No se recomienda deshabilitar esta configuración, ya que permite a los usuarios omitir las advertencias y continuar con sitios potencialmente malintencionados.</span><span class="sxs-lookup"><span data-stu-id="cb61d-142">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="cb61d-143">Impedir la omisión de advertencias de SmartScreen de Microsoft defender sobre descargas</span><span class="sxs-lookup"><span data-stu-id="cb61d-143">Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="cb61d-144">**Valor predeterminado:** Preparado</span><span class="sxs-lookup"><span data-stu-id="cb61d-144">**Default value:** Enabled</span></span>

<span data-ttu-id="cb61d-145">No se recomienda deshabilitar esta configuración, ya que permite a los usuarios omitir las advertencias y completar las descargas sin comprobar.</span><span class="sxs-lookup"><span data-stu-id="cb61d-145">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="cb61d-146">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="cb61d-146">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="cb61d-147">Configuración predeterminada de Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="cb61d-147">Default Adobe Flash setting</span></span>

<span data-ttu-id="cb61d-148">**Valor predeterminado:** Capacidad</span><span class="sxs-lookup"><span data-stu-id="cb61d-148">**Default value:** Disabled</span></span>

<span data-ttu-id="cb61d-149">No se recomienda usar flash debido a los riesgos de seguridad asociados.</span><span class="sxs-lookup"><span data-stu-id="cb61d-149">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="cb61d-150">Si sigue teniendo procesos que dependen de Flash, establezca la Directiva de **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar Flash para los sitios que la necesiten.</span><span class="sxs-lookup"><span data-stu-id="cb61d-150">If you still have processes which depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites which need it.</span></span> <span data-ttu-id="cb61d-151">Si no puede mantener una lista de sitios permitida para usar Flash, archivo una solicitud de cambio para cambiar el valor a **click to Play**, lo que permite a los usuarios elegir cuándo es adecuado ejecutar Flash.</span><span class="sxs-lookup"><span data-stu-id="cb61d-151">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="cb61d-152">Administrador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="cb61d-152">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="cb61d-153">Habilitar el guardado de contraseñas en el administrador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="cb61d-153">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="cb61d-154">**Valor predeterminado:** Capacidad</span><span class="sxs-lookup"><span data-stu-id="cb61d-154">**Default value:** Disabled</span></span>

<span data-ttu-id="cb61d-155">No se recomienda permitir que los usuarios finales guarden contraseñas en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cb61d-155">We do not recommend allowing end users to save passwords on their device.</span></span>

### <a name="other-settings"></a><span data-ttu-id="cb61d-156">Otras opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="cb61d-156">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="cb61d-157">Habilitar el aislamiento del sitio para cada sitio</span><span class="sxs-lookup"><span data-stu-id="cb61d-157">Enable site isolation for every site</span></span>

<span data-ttu-id="cb61d-158">**Valor predeterminado:** Preparado</span><span class="sxs-lookup"><span data-stu-id="cb61d-158">**Default value:** Enabled</span></span>

<span data-ttu-id="cb61d-159">Cuando esta directiva está habilitada, los usuarios no pueden optar por el comportamiento predeterminado en el que cada sitio se ejecuta en su propio proceso.</span><span class="sxs-lookup"><span data-stu-id="cb61d-159">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="cb61d-160">Esquemas de autenticación admitidos</span><span class="sxs-lookup"><span data-stu-id="cb61d-160">Supported authentication schemes</span></span>

<span data-ttu-id="cb61d-161">**Valor predeterminado:** NTLM, Negotiate</span><span class="sxs-lookup"><span data-stu-id="cb61d-161">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="cb61d-162">El escritorio administrado de Microsoft no es compatible con esquemas de autenticación básica o implícita.</span><span class="sxs-lookup"><span data-stu-id="cb61d-162">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="cb61d-163">Importar automáticamente los datos y la configuración de otro explorador al ejecutarse por primera vez</span><span class="sxs-lookup"><span data-stu-id="cb61d-163">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="cb61d-164">**Valor predeterminado:** Importar automáticamente todos los tipos de configuración y los tipos de los tipos de los idiomas admitidos del explorador predeterminado</span><span class="sxs-lookup"><span data-stu-id="cb61d-164">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="cb61d-165">Con esta Directiva aplicada, la primera experiencia de ejecución omitirá la sección de importación, lo que minimizará la interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="cb61d-165">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="cb61d-166">Los datos del explorador de versiones anteriores de Microsoft Edge siempre se migrarán silenciosamente en la primera ejecución, independientemente de esta configuración.</span><span class="sxs-lookup"><span data-stu-id="cb61d-166">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="cb61d-167">Configuración que administra</span><span class="sxs-lookup"><span data-stu-id="cb61d-167">Settings you manage</span></span>

<span data-ttu-id="cb61d-168">Puede implementar cualquier configuración de Microsoft Edge que no se haya descrito anteriormente mediante el perfil plantillas administrativas de Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="cb61d-168">You can deploy any Microsft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="cb61d-169">Para obtener más información, vea [Configure Microsoft Edge Policy Settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span><span class="sxs-lookup"><span data-stu-id="cb61d-169">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="cb61d-170">Si quiere evaluar una directiva que no está incluida actualmente en las plantillas administrativas de Microsoft Edge en Intune, puede usar la configuración personalizada para dispositivos Windows 10 en Intune.</span><span class="sxs-lookup"><span data-stu-id="cb61d-170">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="cb61d-171">Habilitación de extensiones de Chrome específicas</span><span class="sxs-lookup"><span data-stu-id="cb61d-171">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="cb61d-172">La plantilla administrativa ofrece una configuración para implementar extensiones de Chrome específicas con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="cb61d-172">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="cb61d-173">Puede encontrarlo en **configuración del equipo > Microsoft Edge > extensiones > permitir que se instalen extensiones específicas**.</span><span class="sxs-lookup"><span data-stu-id="cb61d-173">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="cb61d-174">Instalar extensiones en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="cb61d-174">Install extensions silently</span></span>

<span data-ttu-id="cb61d-175">También puede usar la plantilla administrativa para configurar Microsoft Edge para que instale extensiones sin avisar al usuario.</span><span class="sxs-lookup"><span data-stu-id="cb61d-175">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="cb61d-176">Puede encontrarlo en **configuración del equipo > Microsoft Edge > extensiones > controlar qué extensiones se instalan silenciosamente**.</span><span class="sxs-lookup"><span data-stu-id="cb61d-176">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="cb61d-177">Otras directivas de empresa comunes</span><span class="sxs-lookup"><span data-stu-id="cb61d-177">Other common enterprise policies</span></span>

<span data-ttu-id="cb61d-178">Microsoft Edge ofrece una gran cantidad de directivas adicionales.</span><span class="sxs-lookup"><span data-stu-id="cb61d-178">Microsoft Edge offers a great many additional policies.</span></span> <span data-ttu-id="cb61d-179">Estos son algunos de los más comunes:</span><span class="sxs-lookup"><span data-stu-id="cb61d-179">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="cb61d-180">Configurar sitios en la lista de sitios de empresa y en el modo IE</span><span class="sxs-lookup"><span data-stu-id="cb61d-180">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="cb61d-181">Configurar las opciones de página de inicio, Página principal y nueva pestaña</span><span class="sxs-lookup"><span data-stu-id="cb61d-181">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="cb61d-182">Configurar la configuración del juego surf</span><span class="sxs-lookup"><span data-stu-id="cb61d-182">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="cb61d-183">Configurar opciones de servidor proxy</span><span class="sxs-lookup"><span data-stu-id="cb61d-183">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

