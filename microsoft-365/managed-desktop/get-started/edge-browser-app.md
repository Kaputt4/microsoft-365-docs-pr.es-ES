---
title: Nuevo Microsoft Edge
description: Explica cómo se implementa y actualiza el nuevo explorador perimetral
keywords: explorador, Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2bf1fab504ae77a1e66235f49333c3b123e38904
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822255"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="31d1b-104">Nueva Microsoft Edge aplicación</span><span class="sxs-lookup"><span data-stu-id="31d1b-104">New Microsoft Edge app</span></span>

<span data-ttu-id="31d1b-105">El nuevo [Microsoft Edge ofrece](https://www.microsoft.com/edge) un rendimiento de clase mundial con más privacidad, más productividad y más valor mientras explora.</span><span class="sxs-lookup"><span data-stu-id="31d1b-105">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="31d1b-106">Escritorio administrado de Microsoft ofrece una vista previa pública de la implementación del nuevo explorador perimetral en su entorno.</span><span class="sxs-lookup"><span data-stu-id="31d1b-106">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="31d1b-107">Implementación inicial</span><span class="sxs-lookup"><span data-stu-id="31d1b-107">Initial deployment</span></span>

<span data-ttu-id="31d1b-108">Para migrar los dispositivos Escritorio administrado de Microsoft al nuevo explorador de Microsoft Edge, file an IT Support Ticket through the Escritorio administrado de Microsoft Portal.</span><span class="sxs-lookup"><span data-stu-id="31d1b-108">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="31d1b-109">Implementaremos el canal estable perimetral en el grupo de prueba al presentar el vale y, a continuación, lo implementaremos en cada grupo de implementación posterior cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="31d1b-109">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="31d1b-110">Para pausar la implementación, file another ticket asking Operations to hold.</span><span class="sxs-lookup"><span data-stu-id="31d1b-110">To pause the deployment, file another ticket asking Operations to hold.</span></span>

<span data-ttu-id="31d1b-111">El [canal beta](/deployedge/microsoft-edge-channels#beta-channel) también está disponible a petición de validación representativa en su organización.</span><span class="sxs-lookup"><span data-stu-id="31d1b-111">The [Beta Channel](/deployedge/microsoft-edge-channels#beta-channel) is also available upon request for representative validation within your organization.</span></span> <span data-ttu-id="31d1b-112">Escritorio administrado de Microsoft implementará la aplicación según sea necesario en los grupos Test y First para que todos esos usuarios tengan el Canal Beta además del canal estable.</span><span class="sxs-lookup"><span data-stu-id="31d1b-112">Microsoft Managed Desktop will deploy the application as required to the Test and First Groups so that all of those users have the Beta Channel in addition to the Stable Channel.</span></span> <span data-ttu-id="31d1b-113">Para cualquier otro usuario que necesite acceso al canal beta, agrégrelos al grupo **Modern Workplace - Edge Beta Users** y haga que lo instalen desde el Portal de empresa</span><span class="sxs-lookup"><span data-stu-id="31d1b-113">For any other users who need access to the Beta Channel, add them to the **Modern Workplace - Edge Beta Users** group and have them install it from the Company Portal</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="31d1b-114">Actualizaciones de Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="31d1b-114">Updates to Microsoft Edge</span></span>

<span data-ttu-id="31d1b-115">Escritorio administrado de Microsoft implementa el [canal](/deployedge/microsoft-edge-channels#stable-channel) estable de Microsoft Edge, que se actualiza automáticamente cada seis semanas.</span><span class="sxs-lookup"><span data-stu-id="31d1b-115">Microsoft Managed Desktop deploys the [Stable channel](/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge, which is auto-updated about every six weeks.</span></span> <span data-ttu-id="31d1b-116">Las actualizaciones en el [](/deployedge/microsoft-edge-update-progressive-rollout) canal estable se revierte progresivamente por el grupo de productos Microsoft Edge para garantizar la mejor experiencia para los clientes.</span><span class="sxs-lookup"><span data-stu-id="31d1b-116">Updates on the Stable channel are rolled out [progressively](/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> 

<span data-ttu-id="31d1b-117">El [canal beta](/deployedge/microsoft-edge-channels#beta-channel) se implementa en dispositivos de los grupos Test y First para la validación representativa dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="31d1b-117">The [Beta Channel](/deployedge/microsoft-edge-channels#beta-channel) is deployed to devices in both the Test and First groups for representative validation within the organization.</span></span> <span data-ttu-id="31d1b-118">Este canal es totalmente compatible y se actualiza automáticamente con nuevas características aproximadamente cada seis semanas.</span><span class="sxs-lookup"><span data-stu-id="31d1b-118">This channel is fully supported and is auto-updated with new features approximately every six weeks.</span></span>

<span data-ttu-id="31d1b-119">Para asegurarse de que Microsoft Edge actualizaciones correctamente, no modifique las Microsoft Edge [de actualización.](/deployedge/microsoft-edge-update-policies)</span><span class="sxs-lookup"><span data-stu-id="31d1b-119">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](/deployedge/microsoft-edge-update-policies).</span></span>



## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="31d1b-120">Configuración administrado por Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="31d1b-120">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="31d1b-121">Escritorio administrado de Microsoft ha creado un conjunto predeterminado de directivas para Microsoft Edge proteger el explorador.</span><span class="sxs-lookup"><span data-stu-id="31d1b-121">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="31d1b-122">La configuración predeterminada del explorador es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="31d1b-122">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="31d1b-123">Microsoft Edge de Microsoft Edge de datos</span><span class="sxs-lookup"><span data-stu-id="31d1b-123">Microsoft Edge extensions</span></span>

<span data-ttu-id="31d1b-124">La línea base de seguridad Microsoft Edge dispositivos Escritorio administrado de Microsoft establece dos directivas para deshabilitar todas las extensiones de Chrome y proteger a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="31d1b-124">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure users.</span></span> <span data-ttu-id="31d1b-125">Para habilitar e implementar extensiones en el entorno, consulte Configuración puede administrar.</span><span class="sxs-lookup"><span data-stu-id="31d1b-125">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="31d1b-126">Lista de bloqueo de instalación de extensión</span><span class="sxs-lookup"><span data-stu-id="31d1b-126">Extension installation blocklist</span></span>
<span data-ttu-id="31d1b-127">**Valor predeterminado:** Todos</span><span class="sxs-lookup"><span data-stu-id="31d1b-127">**Default value:** All</span></span>

<span data-ttu-id="31d1b-128">Escritorio administrado de Microsoft esta directiva para evitar que las extensiones de Chrome se instalen en puntos de conexión administrados.</span><span class="sxs-lookup"><span data-stu-id="31d1b-128">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="31d1b-129">Existen riesgos conocidos asociados con el modelo de extensión Chromium de datos, incluida la protección contra pérdida de datos, la privacidad y otros riesgos que pueden poner en peligro los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="31d1b-129">There are known risks associated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="31d1b-130">Permitir hosts de mensajería nativa de nivel de usuario (instalados sin permisos de administrador)</span><span class="sxs-lookup"><span data-stu-id="31d1b-130">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="31d1b-131">**Valor predeterminado:** Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="31d1b-131">**Default value:** Disabled</span></span>

<span data-ttu-id="31d1b-132">Al deshabilitar esta directiva, Microsoft Edge solo usará hosts de mensajería nativos instalados en el nivel del sistema.</span><span class="sxs-lookup"><span data-stu-id="31d1b-132">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="31d1b-133">Los hosts de mensajería nativa forman parte de las extensiones de Chrome, que permiten que el explorador interactúe con otras partes del extremo del usuario, lo que crea una variedad de problemas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="31d1b-133">Native messaging hosts are a part of Chrome extensions, which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-tlsssl"></a><span data-ttu-id="31d1b-134">Capa de sockets seguros (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="31d1b-134">Secure Sockets Layer (TLS/SSL)</span></span>

#### <a name="minimum-tls-version"></a><span data-ttu-id="31d1b-135">Versión mínima de TLS</span><span class="sxs-lookup"><span data-stu-id="31d1b-135">Minimum TLS version</span></span>

<span data-ttu-id="31d1b-136">**Valor predeterminado:** Tls 1.2 mínimo compatible</span><span class="sxs-lookup"><span data-stu-id="31d1b-136">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="31d1b-137">Si desea usar la TLS 1.1 menos segura, puede presentar una solicitud para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="31d1b-137">If you want to use the less secure TLS 1.1, you can file a request to do so.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="31d1b-138">Permite a los usuarios continuar desde la página de advertencia de SSL</span><span class="sxs-lookup"><span data-stu-id="31d1b-138">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="31d1b-139">**Valor predeterminado:** Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="31d1b-139">**Default value:** Disabled</span></span>

<span data-ttu-id="31d1b-140">No se recomienda habilitar esta configuración, ya que permite a los usuarios visitar sitios con errores de TSL.</span><span class="sxs-lookup"><span data-stu-id="31d1b-140">We don't recommend enabling this setting since it allows users to visit sites with TSL errors.</span></span>

### <a name="microsoft-defender-smartscreen"></a><span data-ttu-id="31d1b-141">SmartScreen de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="31d1b-141">Microsoft Defender SmartScreen</span></span>

#### <a name="configure-windows-defender-smartscreen"></a><span data-ttu-id="31d1b-142">Configurar Windows Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="31d1b-142">Configure Windows Defender SmartScreen</span></span>

<span data-ttu-id="31d1b-143">**Valor predeterminado:** Habilitado</span><span class="sxs-lookup"><span data-stu-id="31d1b-143">**Default value:** Enabled</span></span>

<span data-ttu-id="31d1b-144">Habilitado de forma predeterminada para ayudar a proteger a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="31d1b-144">Enabled by default to help protect users.</span></span>

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="31d1b-145">Windows Defender Mensajes de SmartScreen para sitios</span><span class="sxs-lookup"><span data-stu-id="31d1b-145">Windows Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="31d1b-146">**Valor predeterminado:** Habilitado</span><span class="sxs-lookup"><span data-stu-id="31d1b-146">**Default value:** Enabled</span></span>

<span data-ttu-id="31d1b-147">No se recomienda deshabilitar esta configuración, ya que permitiría a los usuarios omitir las advertencias y continuar con sitios potencialmente malintencionados.</span><span class="sxs-lookup"><span data-stu-id="31d1b-147">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="31d1b-148">Impedir la omisión de Windows Defender advertencias de SmartScreen sobre descargas</span><span class="sxs-lookup"><span data-stu-id="31d1b-148">Prevent bypassing of Windows Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="31d1b-149">**Valor predeterminado:** Habilitado</span><span class="sxs-lookup"><span data-stu-id="31d1b-149">**Default value:** Enabled</span></span>

<span data-ttu-id="31d1b-150">No se recomienda deshabilitar esta configuración, ya que permitiría a los usuarios omitir advertencias y completar descargas no verificados.</span><span class="sxs-lookup"><span data-stu-id="31d1b-150">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="31d1b-151">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="31d1b-151">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="31d1b-152">Configuración predeterminada de Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="31d1b-152">Default Adobe Flash setting</span></span>

<span data-ttu-id="31d1b-153">**Valor predeterminado:** Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="31d1b-153">**Default value:** Disabled</span></span>

<span data-ttu-id="31d1b-154">No se recomienda usar Flash debido a los riesgos de seguridad asociados.</span><span class="sxs-lookup"><span data-stu-id="31d1b-154">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="31d1b-155">Si todavía tiene procesos que dependen de Flash, establezca la directiva **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar Flash para los sitios que lo necesiten.</span><span class="sxs-lookup"><span data-stu-id="31d1b-155">If you still have processes that depend on Flash, set the **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites that need it.</span></span> <span data-ttu-id="31d1b-156">Si no puedes mantener una lista permitida de sitios para usar Flash, presentar una solicitud de cambio para cambiar el valor a **Hacer** clic para reproducir, lo que permite a los usuarios elegir cuándo es adecuado ejecutar Flash.</span><span class="sxs-lookup"><span data-stu-id="31d1b-156">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="31d1b-157">Administrador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="31d1b-157">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="31d1b-158">Habilitar el guardado de contraseñas en el administrador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="31d1b-158">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="31d1b-159">**Valor predeterminado:** Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="31d1b-159">**Default value:** Disabled</span></span>

<span data-ttu-id="31d1b-160">El administrador de contraseñas está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="31d1b-160">The password manager is disabled by default.</span></span> <span data-ttu-id="31d1b-161">Si te gusta esta característica habilitada, presenta una solicitud de soporte técnico y nuestros ingenieros de servicio pueden habilitar la configuración en tu entorno.</span><span class="sxs-lookup"><span data-stu-id="31d1b-161">If you's like this feature enabled, file a support request and our service engineers can enable the setting in your environment.</span></span> 

### <a name="internet-explorer-mode-in-microsoft-edge"></a><span data-ttu-id="31d1b-162">Modo internet Explorer en Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="31d1b-162">Internet Explorer Mode in Microsoft Edge</span></span>
<span data-ttu-id="31d1b-163">El modo IE en Microsoft Edge facilita el uso de todos los sitios que su organización necesita en un solo explorador.</span><span class="sxs-lookup"><span data-stu-id="31d1b-163">IE mode on Microsoft Edge makes it easy to use all of the sites your organization needs in a single browser.</span></span> <span data-ttu-id="31d1b-164">Usa el motor Chromium integrado para sitios compatibles con el motor de representación de Chromium y usa el motor MSHTML trident de Internet Explorer 11 (IE11) para sitios que no son o tienen dependencias de la funcionalidad de IE.</span><span class="sxs-lookup"><span data-stu-id="31d1b-164">It uses the integrated Chromium engine for sites that are compatible with the Chromium rendering engine and it uses the Trident MSHTML engine from Internet Explorer 11 (IE11) for sites that aren't or have dependencies on IE functionality.</span></span> [<span data-ttu-id="31d1b-165">Más información</span><span class="sxs-lookup"><span data-stu-id="31d1b-165">Learn more</span></span>](/DeployEdge/edge-ie-mode) 

<span data-ttu-id="31d1b-166">Escritorio administrado de Microsoft habilita el modo de Internet Explorer para los dispositivos de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="31d1b-166">Microsoft Managed Desktop enables Internet Explorer mode for your devices by default</span></span> 

#### <a name="internet-explorer-mode-integration"></a><span data-ttu-id="31d1b-167">Integración del modo de Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="31d1b-167">Internet Explorer mode integration</span></span>
<span data-ttu-id="31d1b-168">**Valor predeterminado:** Modo de Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="31d1b-168">**Default Value:** Internet Explorer mode</span></span>

<span data-ttu-id="31d1b-169">De forma predeterminada, los dispositivos están configurados para usar el modo Internet Explorer, pero puedes establecerlos para que abran sitios en una ventana independiente de Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="31d1b-169">By default, devices are set to use Internet Explorer mode, but you can set them to open sites in a standalone Internet Explorer 11 window instead.</span></span> <span data-ttu-id="31d1b-170">Para cambiar este comportamiento, presente una solicitud de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="31d1b-170">To change this behavior, file a support request.</span></span>

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a><span data-ttu-id="31d1b-171">Agregar sitios a la lista Enterprise sitio de modo de acceso</span><span class="sxs-lookup"><span data-stu-id="31d1b-171">Add sites to the Enterprise Mode Site list</span></span>
<span data-ttu-id="31d1b-172">Para que los sitios se abran en modo Internet Explorer, debe incluirlos en la [lista Enterprise sitio](/DeployEdge/edge-ie-mode-sitelist).</span><span class="sxs-lookup"><span data-stu-id="31d1b-172">For sites to open in Internet Explorer mode you must include them on the [Enterprise Site list](/DeployEdge/edge-ie-mode-sitelist).</span></span> <span data-ttu-id="31d1b-173">Mantener e implementar la lista Enterprise sitio es su responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="31d1b-173">Maintaining and deploying the Enterprise Site list is your responsibility.</span></span> <span data-ttu-id="31d1b-174">Para obtener más información, vea [Configure using the Configure Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span><span class="sxs-lookup"><span data-stu-id="31d1b-174">For details, see [Configure using the Configure Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span></span>

### <a name="other-settings"></a><span data-ttu-id="31d1b-175">Otras opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="31d1b-175">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="31d1b-176">Habilitar el aislamiento de sitios para cada sitio</span><span class="sxs-lookup"><span data-stu-id="31d1b-176">Enable site isolation for every site</span></span>

<span data-ttu-id="31d1b-177">**Valor predeterminado:** Habilitado</span><span class="sxs-lookup"><span data-stu-id="31d1b-177">**Default value:** Enabled</span></span>

<span data-ttu-id="31d1b-178">Cuando esta directiva está habilitada, los usuarios no pueden optar por el comportamiento predeterminado en el que cada sitio se ejecuta en su propio proceso.</span><span class="sxs-lookup"><span data-stu-id="31d1b-178">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="31d1b-179">Esquemas de autenticación compatibles</span><span class="sxs-lookup"><span data-stu-id="31d1b-179">Supported authentication schemes</span></span>

<span data-ttu-id="31d1b-180">**Valor predeterminado:** NTLM, Negociar</span><span class="sxs-lookup"><span data-stu-id="31d1b-180">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="31d1b-181">Escritorio administrado de Microsoft no admite esquemas de autenticación básica o implícita.</span><span class="sxs-lookup"><span data-stu-id="31d1b-181">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="31d1b-182">Importar automáticamente los datos y la configuración de otro explorador en la primera ejecución</span><span class="sxs-lookup"><span data-stu-id="31d1b-182">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="31d1b-183">**Valor predeterminado:** Importar automáticamente todos los tipos de datos y la configuración admitidos desde el explorador predeterminado</span><span class="sxs-lookup"><span data-stu-id="31d1b-183">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="31d1b-184">Con esta directiva aplicada, la primera experiencia de ejecución omitirá la sección de importación, lo que minimizará la interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="31d1b-184">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="31d1b-185">Los datos del explorador de versiones anteriores de Microsoft Edge se migrarán siempre silenciosamente en la primera ejecución, independientemente de esta configuración.</span><span class="sxs-lookup"><span data-stu-id="31d1b-185">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="31d1b-186">Configuración administrar</span><span class="sxs-lookup"><span data-stu-id="31d1b-186">Settings you manage</span></span>

<span data-ttu-id="31d1b-187">Puede implementar cualquier configuración Microsoft Edge no descrita anteriormente mediante el perfil Plantillas administrativas en Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="31d1b-187">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="31d1b-188">Para obtener más información, [vea Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune).</span><span class="sxs-lookup"><span data-stu-id="31d1b-188">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="31d1b-189">Si desea evaluar una directiva que no se incluye actualmente en las plantillas administrativas de Microsoft Edge en Intune, puede usar la configuración personalizada para los dispositivos Windows 10 en Intune.</span><span class="sxs-lookup"><span data-stu-id="31d1b-189">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune, you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="31d1b-190">Habilitar extensiones específicas de Chrome</span><span class="sxs-lookup"><span data-stu-id="31d1b-190">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="31d1b-191">La plantilla administrativa ofrece una configuración para implementar extensiones de Chrome determinadas con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="31d1b-191">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="31d1b-192">Puede encontrarlo en Configuración del **equipo > Microsoft Edge > extensiones > Permitir** que se instalen extensiones específicas .</span><span class="sxs-lookup"><span data-stu-id="31d1b-192">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="31d1b-193">Instalar extensiones de forma silenciosa</span><span class="sxs-lookup"><span data-stu-id="31d1b-193">Install extensions silently</span></span>

<span data-ttu-id="31d1b-194">También puede usar la plantilla administrativa para establecer Microsoft Edge para instalar extensiones sin avisar al usuario.</span><span class="sxs-lookup"><span data-stu-id="31d1b-194">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="31d1b-195">Puede encontrarlo en Configuración del equipo > Microsoft Edge > extensiones > Control de extensiones que **se instalan silenciosamente**.</span><span class="sxs-lookup"><span data-stu-id="31d1b-195">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="microsoft-edge-update-policies"></a><span data-ttu-id="31d1b-196">Microsoft Edge de actualización</span><span class="sxs-lookup"><span data-stu-id="31d1b-196">Microsoft Edge update policies</span></span>
<span data-ttu-id="31d1b-197">Para asegurarse de que Microsoft Edge actualizaciones correctamente, no modifique las Microsoft Edge [de actualización.](/deployedge/microsoft-edge-update-policies)</span><span class="sxs-lookup"><span data-stu-id="31d1b-197">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](/deployedge/microsoft-edge-update-policies).</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="31d1b-198">Otras directivas de empresa comunes</span><span class="sxs-lookup"><span data-stu-id="31d1b-198">Other common enterprise policies</span></span>

<span data-ttu-id="31d1b-199">Microsoft Edge ofrece muchas otras directivas.</span><span class="sxs-lookup"><span data-stu-id="31d1b-199">Microsoft Edge offers a great many other policies.</span></span> <span data-ttu-id="31d1b-200">Estas son algunas de las más comunes:</span><span class="sxs-lookup"><span data-stu-id="31d1b-200">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="31d1b-201">Configurar sitios en la lista Enterprise sitio y el modo IE</span><span class="sxs-lookup"><span data-stu-id="31d1b-201">Configure Sites on the Enterprise Site List and IE Mode</span></span>](/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="31d1b-202">Configurar la configuración de inicio, página principal y nueva página de pestañas</span><span class="sxs-lookup"><span data-stu-id="31d1b-202">Configure start-up, home page, and new tab page settings</span></span>](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="31d1b-203">Configurar configuración de juego de surf</span><span class="sxs-lookup"><span data-stu-id="31d1b-203">Configure Surf game setting</span></span>](/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="31d1b-204">Configurar la configuración del servidor proxy</span><span class="sxs-lookup"><span data-stu-id="31d1b-204">Configure proxy server settings</span></span>](/deployedge/microsoft-edge-policies#proxy-server)
