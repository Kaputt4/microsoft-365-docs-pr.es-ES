---
title: Nuevo Microsoft Edge
description: Explica cómo se implementa y actualiza el nuevo explorador Edge
keywords: explorador, Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841344"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="502d0-104">Nueva aplicación de Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="502d0-104">New Microsoft Edge app</span></span>

<span data-ttu-id="502d0-105">El nuevo [explorador Microsoft Edge proporciona](https://www.microsoft.com/edge) un rendimiento de primer nivel con más privacidad, más productividad y más valor mientras exploras.</span><span class="sxs-lookup"><span data-stu-id="502d0-105">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="502d0-106">Escritorio administrado de Microsoft ofrece una versión preliminar pública de la implementación del nuevo explorador Edge en su entorno.</span><span class="sxs-lookup"><span data-stu-id="502d0-106">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="502d0-107">Implementación inicial</span><span class="sxs-lookup"><span data-stu-id="502d0-107">Initial deployment</span></span>

<span data-ttu-id="502d0-108">Para migrar los dispositivos de Escritorio administrado de Microsoft al nuevo explorador Microsoft Edge, debe presentar un vale de soporte técnico de TI a través del Portal de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="502d0-108">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="502d0-109">Implementaremos el canal estable perimetral en el grupo de prueba al presentar el vale y, a continuación, lo implementaremos en cada grupo de implementación posterior cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="502d0-109">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="502d0-110">Para pausar la implementación, file another ticket asking Operations to hold.</span><span class="sxs-lookup"><span data-stu-id="502d0-110">To pause the deployment, file another ticket asking Operations to hold.</span></span>

<span data-ttu-id="502d0-111">El [canal beta](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) también está disponible cuando se solicita la validación representativa dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="502d0-111">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is also available upon request for representative validation within your organization.</span></span> <span data-ttu-id="502d0-112">Escritorio administrado de Microsoft implementará la aplicación según sea necesario para los grupos De prueba y Primeros grupos para que todos esos usuarios tengan el canal beta además del canal estable.</span><span class="sxs-lookup"><span data-stu-id="502d0-112">Microsoft Managed Desktop will deploy the application as required to the Test and First Groups so that all of those users have the Beta Channel in addition to the Stable Channel.</span></span> <span data-ttu-id="502d0-113">Para cualquier otro usuario que necesite acceso al canal beta, agrégrelos al grupo **Modern Workplace - Edge Beta Users** y haga que lo instalen desde el Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="502d0-113">For any other users who need access to the Beta Channel, add them to the **Modern Workplace - Edge Beta Users** group and have them install it from the Company Portal</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="502d0-114">Actualizaciones de Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="502d0-114">Updates to Microsoft Edge</span></span>

<span data-ttu-id="502d0-115">Escritorio administrado de Microsoft implementa el [canal estable](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) de Microsoft Edge, que se actualiza automáticamente cada seis semanas.</span><span class="sxs-lookup"><span data-stu-id="502d0-115">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge, which is auto-updated about every six weeks.</span></span> <span data-ttu-id="502d0-116">El grupo de productos [](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) de Microsoft Edge implanta las actualizaciones en el canal estable de forma progresiva para garantizar la mejor experiencia para los clientes.</span><span class="sxs-lookup"><span data-stu-id="502d0-116">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> 

<span data-ttu-id="502d0-117">El [canal beta](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) se implementa en dispositivos de los grupos Test y First para la validación representativa dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="502d0-117">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is deployed to devices in both the Test and First groups for representative validation within the organization.</span></span> <span data-ttu-id="502d0-118">Este canal es totalmente compatible y se actualiza automáticamente con nuevas características aproximadamente cada seis semanas.</span><span class="sxs-lookup"><span data-stu-id="502d0-118">This channel is fully supported and is auto-updated with new features approximately every six weeks.</span></span>

<span data-ttu-id="502d0-119">Para asegurarse de que Microsoft Edge se actualiza correctamente, no modifique las directivas de actualización [de](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="502d0-119">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>



## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="502d0-120">Configuración administrada por Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="502d0-120">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="502d0-121">Escritorio administrado de Microsoft ha creado un conjunto predeterminado de directivas para Que Microsoft Edge proteja el explorador.</span><span class="sxs-lookup"><span data-stu-id="502d0-121">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="502d0-122">La configuración predeterminada del explorador es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="502d0-122">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="502d0-123">Extensiones de Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="502d0-123">Microsoft Edge extensions</span></span>

<span data-ttu-id="502d0-124">La línea base de seguridad para Microsoft Edge en dispositivos de Escritorio administrado de Microsoft establece dos directivas para deshabilitar todas las extensiones de Chrome y proteger a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="502d0-124">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure users.</span></span> <span data-ttu-id="502d0-125">Para habilitar e implementar extensiones en su entorno, consulte Configuración que administra.</span><span class="sxs-lookup"><span data-stu-id="502d0-125">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="502d0-126">Lista de bloqueados de instalación de extensión</span><span class="sxs-lookup"><span data-stu-id="502d0-126">Extension installation blocklist</span></span>
<span data-ttu-id="502d0-127">**Valor predeterminado:** Todos</span><span class="sxs-lookup"><span data-stu-id="502d0-127">**Default value:** All</span></span>

<span data-ttu-id="502d0-128">Escritorio administrado de Microsoft establece esta directiva para evitar que se instalen extensiones de Chrome en los puntos de conexión administrados.</span><span class="sxs-lookup"><span data-stu-id="502d0-128">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="502d0-129">Existen riesgos conocidos asociados con el modelo de extensión chromium, como la protección contra la pérdida de datos, la privacidad y otros riesgos que pueden poner en peligro los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="502d0-129">There are known risks associated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="502d0-130">Permitir hosts de mensajería nativa de nivel de usuario (instalados sin permisos de administrador)</span><span class="sxs-lookup"><span data-stu-id="502d0-130">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="502d0-131">**Valor predeterminado:** Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="502d0-131">**Default value:** Disabled</span></span>

<span data-ttu-id="502d0-132">Al deshabilitar esta directiva, Microsoft Edge solo usará hosts de mensajería nativos instalados en el nivel del sistema.</span><span class="sxs-lookup"><span data-stu-id="502d0-132">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="502d0-133">Los hosts de mensajería nativa forman parte de las extensiones de Chrome, que permiten que el explorador interactúe con otras partes del extremo del usuario, lo que crea una variedad de problemas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="502d0-133">Native messaging hosts are a part of Chrome extensions, which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-tlsssl"></a><span data-ttu-id="502d0-134">Capa de sockets seguros (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="502d0-134">Secure Sockets Layer (TLS/SSL)</span></span>

#### <a name="minimum-tls-version"></a><span data-ttu-id="502d0-135">Versión mínima de TLS</span><span class="sxs-lookup"><span data-stu-id="502d0-135">Minimum TLS version</span></span>

<span data-ttu-id="502d0-136">**Valor predeterminado:** Tls 1.2 mínimo compatible</span><span class="sxs-lookup"><span data-stu-id="502d0-136">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="502d0-137">Si desea usar tls 1.1 menos seguro, puede presentar una solicitud para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="502d0-137">If you want to use the less secure TLS 1.1, you can file a request to do so.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="502d0-138">Permite a los usuarios continuar desde la página de advertencia de SSL</span><span class="sxs-lookup"><span data-stu-id="502d0-138">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="502d0-139">**Valor predeterminado:** Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="502d0-139">**Default value:** Disabled</span></span>

<span data-ttu-id="502d0-140">No se recomienda habilitar esta configuración, ya que permite a los usuarios visitar sitios con errores de TSL.</span><span class="sxs-lookup"><span data-stu-id="502d0-140">We don't recommend enabling this setting since it allows users to visit sites with TSL errors.</span></span>

### <a name="microsoft-defender-smartscreen"></a><span data-ttu-id="502d0-141">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="502d0-141">Microsoft Defender SmartScreen</span></span>

#### <a name="configure-windows-defender-smartscreen"></a><span data-ttu-id="502d0-142">Configurar Windows Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="502d0-142">Configure Windows Defender SmartScreen</span></span>

<span data-ttu-id="502d0-143">**Valor predeterminado:** Habilitado</span><span class="sxs-lookup"><span data-stu-id="502d0-143">**Default value:** Enabled</span></span>

<span data-ttu-id="502d0-144">Habilitado de forma predeterminada para ayudar a proteger a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="502d0-144">Enabled by default to help protect users.</span></span>

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="502d0-145">Windows Defender de SmartScreen para sitios</span><span class="sxs-lookup"><span data-stu-id="502d0-145">Windows Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="502d0-146">**Valor predeterminado:** Habilitado</span><span class="sxs-lookup"><span data-stu-id="502d0-146">**Default value:** Enabled</span></span>

<span data-ttu-id="502d0-147">No se recomienda deshabilitar esta configuración, ya que esto permitiría a los usuarios ignorar las advertencias y seguir usando sitios potencialmente malintencionados.</span><span class="sxs-lookup"><span data-stu-id="502d0-147">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="502d0-148">Evitar la omisión de Windows Defender advertencias de SmartScreen sobre descargas</span><span class="sxs-lookup"><span data-stu-id="502d0-148">Prevent bypassing of Windows Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="502d0-149">**Valor predeterminado:** Habilitado</span><span class="sxs-lookup"><span data-stu-id="502d0-149">**Default value:** Enabled</span></span>

<span data-ttu-id="502d0-150">No se recomienda deshabilitar esta configuración, ya que esto permitiría a los usuarios omitir las advertencias y completar descargas no verificados.</span><span class="sxs-lookup"><span data-stu-id="502d0-150">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="502d0-151">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="502d0-151">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="502d0-152">Configuración predeterminada de Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="502d0-152">Default Adobe Flash setting</span></span>

<span data-ttu-id="502d0-153">**Valor predeterminado:** Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="502d0-153">**Default value:** Disabled</span></span>

<span data-ttu-id="502d0-154">No recomendamos usar Flash debido a riesgos de seguridad asociados.</span><span class="sxs-lookup"><span data-stu-id="502d0-154">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="502d0-155">Si todavía tiene procesos que dependen de Flash, establezca la directiva **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar Flash para los sitios que la necesiten.</span><span class="sxs-lookup"><span data-stu-id="502d0-155">If you still have processes that depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites that need it.</span></span> <span data-ttu-id="502d0-156">Si no puedes mantener una lista de sitios permitidos para usar Flash, presentar una solicitud de cambio para cambiar el valor a **Hacer** clic y reproducir, lo que permite a los usuarios elegir cuándo es adecuado ejecutar Flash.</span><span class="sxs-lookup"><span data-stu-id="502d0-156">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="502d0-157">Administrador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="502d0-157">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="502d0-158">Habilitar el almacenamiento de contraseñas en el administrador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="502d0-158">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="502d0-159">**Valor predeterminado:** Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="502d0-159">**Default value:** Disabled</span></span>

<span data-ttu-id="502d0-160">No se recomienda permitir que los usuarios guarden contraseñas en su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="502d0-160">We do not recommend allowing users to save passwords on their device.</span></span>

### <a name="internet-explorer-mode-in-microsoft-edge"></a><span data-ttu-id="502d0-161">Modo de Internet Explorer en Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="502d0-161">Internet Explorer Mode in Microsoft Edge</span></span>
<span data-ttu-id="502d0-162">El modo IE en Microsoft Edge facilita el uso de todos los sitios que la organización necesita en un único explorador.</span><span class="sxs-lookup"><span data-stu-id="502d0-162">IE mode on Microsoft Edge makes it easy to use all of the sites your organization needs in a single browser.</span></span> <span data-ttu-id="502d0-163">Usa el motor chromium integrado para sitios que son compatibles con el motor de representación de Chromium y usa el motor MSHTML trident de Internet Explorer 11 (IE11) para sitios que no son o tienen dependencias en la funcionalidad de IE.</span><span class="sxs-lookup"><span data-stu-id="502d0-163">It uses the integrated Chromium engine for sites that are compatible with the Chromium rendering engine and it uses the Trident MSHTML engine from Internet Explorer 11 (IE11) for sites that aren't or have dependencies on IE functionality.</span></span> <span data-ttu-id="502d0-164">[Más información] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span><span class="sxs-lookup"><span data-stu-id="502d0-164">[Learn more] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span></span> 

<span data-ttu-id="502d0-165">Escritorio administrado de Microsoft habilita el modo Internet Explorer para sus dispositivos de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="502d0-165">Microsoft Managed Desktop enables Internet Explorer mode for your devices by default</span></span> 

#### <a name="internet-explorer-mode-integration"></a><span data-ttu-id="502d0-166">Integración del modo Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="502d0-166">Internet Explorer mode integration</span></span>
<span data-ttu-id="502d0-167">**Valor predeterminado:** Modo internet Explorer</span><span class="sxs-lookup"><span data-stu-id="502d0-167">**Default Value:** Internet Explorer mode</span></span>

<span data-ttu-id="502d0-168">De forma predeterminada, los dispositivos están configurados para usar el modo Internet Explorer, pero puedes configurarlos para que abran sitios en una ventana independiente de Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="502d0-168">By default, devices are set to use Internet Explorer mode, but you can set them to open sites in a standalone Internet Explorer 11 window instead.</span></span> <span data-ttu-id="502d0-169">Para cambiar este comportamiento, presente una solicitud de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="502d0-169">To change this behavior, file a support request.</span></span>

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a><span data-ttu-id="502d0-170">Agregar sitios a la lista de sitios del Modo de empresa</span><span class="sxs-lookup"><span data-stu-id="502d0-170">Add sites to the Enterprise Mode Site list</span></span>
<span data-ttu-id="502d0-171">Para que los sitios se abran en modo Internet Explorer, debe incluirlos en la lista [De sitios de empresa.](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist)</span><span class="sxs-lookup"><span data-stu-id="502d0-171">For sites to open in Internet Explorer mode you must include them on the [Enterprise Site list](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist).</span></span> <span data-ttu-id="502d0-172">Mantener e implementar la lista de sitios de empresa es su responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="502d0-172">Maintaining and deploying the Enterprise Site list is your responsibility.</span></span> <span data-ttu-id="502d0-173">Para obtener más información, consulta [Configurar mediante la directiva Configurar la lista de sitios del Modo de empresa](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span><span class="sxs-lookup"><span data-stu-id="502d0-173">For details, see [Configure using the Configure Enterprise Mode Site List policy](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span></span>

### <a name="other-settings"></a><span data-ttu-id="502d0-174">Otras opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="502d0-174">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="502d0-175">Habilitar el aislamiento de sitios para cada sitio</span><span class="sxs-lookup"><span data-stu-id="502d0-175">Enable site isolation for every site</span></span>

<span data-ttu-id="502d0-176">**Valor predeterminado:** Habilitado</span><span class="sxs-lookup"><span data-stu-id="502d0-176">**Default value:** Enabled</span></span>

<span data-ttu-id="502d0-177">Cuando esta directiva está habilitada, los usuarios no pueden optar por no participar en el comportamiento predeterminado en el que cada sitio se ejecuta en su propio proceso.</span><span class="sxs-lookup"><span data-stu-id="502d0-177">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="502d0-178">Esquemas de autenticación admitidos</span><span class="sxs-lookup"><span data-stu-id="502d0-178">Supported authentication schemes</span></span>

<span data-ttu-id="502d0-179">**Valor predeterminado:** NTLM, Negociar</span><span class="sxs-lookup"><span data-stu-id="502d0-179">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="502d0-180">El Escritorio administrado de Microsoft no admite esquemas de autenticación básica o implícita.</span><span class="sxs-lookup"><span data-stu-id="502d0-180">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="502d0-181">Importar automáticamente los datos y la configuración de otro explorador en la primera ejecución</span><span class="sxs-lookup"><span data-stu-id="502d0-181">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="502d0-182">**Valor predeterminado:** Importar automáticamente todos los tipos de datos y la configuración admitidos desde el explorador predeterminado</span><span class="sxs-lookup"><span data-stu-id="502d0-182">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="502d0-183">Con esta directiva aplicada, la experiencia de primera ejecución omitirá la sección de importación, minimizando la interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="502d0-183">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="502d0-184">Los datos del explorador de versiones anteriores de Microsoft Edge siempre se migrarán silenciosamente en la primera ejecución, independientemente de esta configuración.</span><span class="sxs-lookup"><span data-stu-id="502d0-184">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="502d0-185">Configuración que administra</span><span class="sxs-lookup"><span data-stu-id="502d0-185">Settings you manage</span></span>

<span data-ttu-id="502d0-186">Puedes implementar cualquier configuración de Microsoft Edge que no se describió anteriormente mediante el perfil plantillas administrativas de Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="502d0-186">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="502d0-187">Para obtener más información, [vea Configurar las opciones de directiva de Microsoft Edge con Microsoft Intune.](https://docs.microsoft.com/deployedge/configure-edge-with-intune)</span><span class="sxs-lookup"><span data-stu-id="502d0-187">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="502d0-188">Si quieres evaluar una directiva que actualmente no está incluida en las plantillas administrativas de Microsoft Edge en Intune, puedes usar la configuración personalizada para dispositivos Windows 10 en Intune.</span><span class="sxs-lookup"><span data-stu-id="502d0-188">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune, you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="502d0-189">Habilitar extensiones específicas de Chrome</span><span class="sxs-lookup"><span data-stu-id="502d0-189">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="502d0-190">La plantilla administrativa ofrece una configuración para implementar extensiones de Chrome concretas con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="502d0-190">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="502d0-191">Puede encontrarlo en Configuración del equipo > Microsoft Edge > extensiones > permitir la instalación **de extensiones específicas.**</span><span class="sxs-lookup"><span data-stu-id="502d0-191">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="502d0-192">Instalar extensiones en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="502d0-192">Install extensions silently</span></span>

<span data-ttu-id="502d0-193">También puede usar la plantilla administrativa para configurar Microsoft Edge para instalar extensiones sin avisar al usuario.</span><span class="sxs-lookup"><span data-stu-id="502d0-193">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="502d0-194">Puede encontrarlo en Configuración del equipo > Microsoft Edge > Extensiones > control de qué extensiones se **instalan en modo silencioso.**</span><span class="sxs-lookup"><span data-stu-id="502d0-194">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="microsoft-edge-update-policies"></a><span data-ttu-id="502d0-195">Directivas de actualización de Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="502d0-195">Microsoft Edge update policies</span></span>
<span data-ttu-id="502d0-196">Para asegurarse de que Microsoft Edge se actualiza correctamente, no modifique las directivas de actualización [de](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="502d0-196">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="502d0-197">Otras directivas de empresa comunes</span><span class="sxs-lookup"><span data-stu-id="502d0-197">Other common enterprise policies</span></span>

<span data-ttu-id="502d0-198">Microsoft Edge ofrece muchas otras directivas.</span><span class="sxs-lookup"><span data-stu-id="502d0-198">Microsoft Edge offers a great many other policies.</span></span> <span data-ttu-id="502d0-199">Estas son algunas de las más comunes:</span><span class="sxs-lookup"><span data-stu-id="502d0-199">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="502d0-200">Configurar sitios en la lista de sitios de empresa y el modo IE</span><span class="sxs-lookup"><span data-stu-id="502d0-200">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="502d0-201">Configurar las opciones de inicio, página principal y página de nueva pestaña</span><span class="sxs-lookup"><span data-stu-id="502d0-201">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="502d0-202">Configurar la configuración del juego de surf</span><span class="sxs-lookup"><span data-stu-id="502d0-202">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="502d0-203">Configuración de las opciones del servidor proxy</span><span class="sxs-lookup"><span data-stu-id="502d0-203">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

