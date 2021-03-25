---
title: Proteger las carpetas importantes contra ransomware de cifrar los archivos con acceso controlado a carpetas
description: Los archivos de las carpetas predeterminadas se pueden proteger para que no los cambien las aplicaciones malintencionadas. Impedir que el ransomware cifre los archivos.
keywords: acceso controlado a carpetas, windows 10, Windows Defender, ransomware, protect, files, folders
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: cd662dc130adc37b3bf8bd06839242ccc9a49f8e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185974"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a><span data-ttu-id="bfc18-105">Proteger carpetas importantes con acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="bfc18-105">Protect important folders with controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bfc18-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bfc18-106">**Applies to:**</span></span>
- [<span data-ttu-id="bfc18-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bfc18-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bfc18-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfc18-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bfc18-109">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="bfc18-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bfc18-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="bfc18-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a><span data-ttu-id="bfc18-111">¿Qué es el acceso controlado a carpetas?</span><span class="sxs-lookup"><span data-stu-id="bfc18-111">What is controlled folder access?</span></span>

<span data-ttu-id="bfc18-112">El acceso controlado a carpetas ayuda a proteger los datos valiosos de las amenazas y aplicaciones malintencionadas, como el ransomware.</span><span class="sxs-lookup"><span data-stu-id="bfc18-112">Controlled folder access helps protect your valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="bfc18-113">El acceso controlado a carpetas protege los datos comprobando las aplicaciones en una lista de aplicaciones conocidas y de confianza.</span><span class="sxs-lookup"><span data-stu-id="bfc18-113">Controlled folder access protects your data by checking apps against a list of known, trusted apps.</span></span> <span data-ttu-id="bfc18-114">Compatible con clientes de Windows Server 2019 y Windows 10, el acceso controlado a carpetas puede estar activado mediante la aplicación de seguridad de Windows, Microsoft Endpoint Configuration Manager o Intune (para dispositivos administrados).</span><span class="sxs-lookup"><span data-stu-id="bfc18-114">Supported on Windows Server 2019 and Windows 10 clients, controlled folder access can be turned on using the Windows Security App, Microsoft Endpoint Configuration Manager, or Intune (for managed devices).</span></span> 

> [!NOTE]
> <span data-ttu-id="bfc18-115">Los motores de scripting no son de confianza y no se les puede permitir el acceso a carpetas protegidas controladas.</span><span class="sxs-lookup"><span data-stu-id="bfc18-115">Scripting engines are not trusted and you cannot allow them access to controlled protected folders.</span></span>  <span data-ttu-id="bfc18-116">Por ejemplo, PowerShell no es de confianza mediante el acceso controlado a carpetas, incluso si permite con indicadores de certificado [e archivo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span><span class="sxs-lookup"><span data-stu-id="bfc18-116">For example, PowerShell is not trusted by controlled folder access, even if you allow with [certificate and file indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span> 

<span data-ttu-id="bfc18-117">El acceso controlado a carpetas funciona mejor con [Microsoft Defender para](microsoft-defender-endpoint.md)endpoint, lo que le ofrece informes detallados sobre los eventos y bloques de acceso controlado a carpetas como parte de los escenarios habituales de investigación de [alertas.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="bfc18-117">Controlled folder access works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into controlled folder access events and blocks as part of the usual [alert investigation scenarios](investigate-alerts.md).</span></span>

> [!TIP]
> <span data-ttu-id="bfc18-118">Los bloques de acceso a carpetas controladas no generan alertas en la cola [De alertas.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="bfc18-118">Controlled folder access blocks don't generate alerts in the [Alerts queue](alerts-queue.md).</span></span> <span data-ttu-id="bfc18-119">Sin embargo, puedes ver información sobre los bloques de acceso controlados a carpetas en la vista de escala de tiempo del [dispositivo,](investigate-machines.md)mientras usas la búsqueda [avanzada](advanced-hunting-overview.md)o con reglas [de detección personalizadas.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="bfc18-119">However, you can view information about controlled folder access blocks in the [device timeline view](investigate-machines.md), while using [advanced hunting](advanced-hunting-overview.md), or with [custom detection rules](custom-detection-rules.md).</span></span>

## <a name="how-does-controlled-folder-access-work"></a><span data-ttu-id="bfc18-120">¿Cómo funciona el acceso controlado a carpetas?</span><span class="sxs-lookup"><span data-stu-id="bfc18-120">How does controlled folder access work?</span></span>

<span data-ttu-id="bfc18-121">El acceso controlado a carpetas solo permite que las aplicaciones de confianza accedan a carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="bfc18-121">Controlled folder access works by only allowing trusted apps to access protected folders.</span></span> <span data-ttu-id="bfc18-122">Las carpetas protegidas se especifican cuando se configura el acceso controlado a carpetas.</span><span class="sxs-lookup"><span data-stu-id="bfc18-122">Protected folders are specified when controlled folder access is configured.</span></span> <span data-ttu-id="bfc18-123">Normalmente, las carpetas usadas normalmente, como las que se usan para documentos, imágenes, descargas, entre otras, se incluyen en la lista de carpetas controladas.</span><span class="sxs-lookup"><span data-stu-id="bfc18-123">Typically, commonly used folders, such as those used for documents, pictures, downloads, and so on, are included in the list of controlled folders.</span></span> 

<span data-ttu-id="bfc18-124">El acceso controlado a carpetas funciona con una lista de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="bfc18-124">Controlled folder access works with a list of trusted apps.</span></span> <span data-ttu-id="bfc18-125">Las aplicaciones que se incluyen en la lista de software de confianza funcionan según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="bfc18-125">Apps that are included in the list of trusted software work as expected.</span></span> <span data-ttu-id="bfc18-126">Las aplicaciones que no se incluyen en la lista no pueden realizar cambios en archivos dentro de carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="bfc18-126">Apps that are not included in the list are prevented from making any changes to files inside protected folders.</span></span> 

<span data-ttu-id="bfc18-127">Las aplicaciones se agregan a la lista en función de su prevalencia y reputación.</span><span class="sxs-lookup"><span data-stu-id="bfc18-127">Apps are added to the list based upon their prevalence and reputation.</span></span> <span data-ttu-id="bfc18-128">Las aplicaciones que son muy frecuentes en toda la organización y que nunca han mostrado ningún comportamiento que se considere malintencionado se consideran confiables.</span><span class="sxs-lookup"><span data-stu-id="bfc18-128">Apps that are highly prevalent throughout your organization and that have never displayed any behavior deemed malicious are considered trustworthy.</span></span> <span data-ttu-id="bfc18-129">Esas aplicaciones se agregan a la lista automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bfc18-129">Those apps are added to the list automatically.</span></span>

<span data-ttu-id="bfc18-130">Las aplicaciones también se pueden agregar manualmente a la lista de confianza mediante Configuration Manager o Intune.</span><span class="sxs-lookup"><span data-stu-id="bfc18-130">Apps can also be added manually to the trusted list by using Configuration Manager or Intune.</span></span> <span data-ttu-id="bfc18-131">Se pueden realizar acciones adicionales, como agregar un indicador [de archivo](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) para una aplicación, desde la consola del Centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bfc18-131">Additional actions, such as [adding a file indicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) for an app, can be performed from the Security Center Console.</span></span>

## <a name="why-controlled-folder-access-is-important"></a><span data-ttu-id="bfc18-132">Por qué es importante el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="bfc18-132">Why controlled folder access is important</span></span>

<span data-ttu-id="bfc18-133">El acceso controlado a carpetas es especialmente útil para ayudar a proteger los documentos y la información de [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span><span class="sxs-lookup"><span data-stu-id="bfc18-133">Controlled folder access is especially useful in helping to protect your documents and information from [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span></span> <span data-ttu-id="bfc18-134">En un ataque de ransomware, los archivos pueden ser cifrados y retenidos como rehenes.</span><span class="sxs-lookup"><span data-stu-id="bfc18-134">In a ransomware attack, your files can get encrypted and held hostage.</span></span> <span data-ttu-id="bfc18-135">Con el acceso controlado a carpetas, aparece una notificación en el equipo donde una aplicación intentó realizar cambios en un archivo de una carpeta protegida.</span><span class="sxs-lookup"><span data-stu-id="bfc18-135">With controlled folder access in place, a notification appears on the computer where an app attempted to make changes to a file in a protected folder.</span></span> <span data-ttu-id="bfc18-136">Puede personalizar [la notificación con los](customize-attack-surface-reduction.md#customize-the-notification) detalles de su empresa y la información de contacto.</span><span class="sxs-lookup"><span data-stu-id="bfc18-136">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span> <span data-ttu-id="bfc18-137">También puede habilitar las reglas individualmente para personalizar las técnicas que supervisan las características.</span><span class="sxs-lookup"><span data-stu-id="bfc18-137">You can also enable the rules individually to customize what techniques the feature monitors.</span></span>

<span data-ttu-id="bfc18-138">Las [carpetas protegidas](#review-controlled-folder-access-events-in-windows-event-viewer) incluyen carpetas comunes del sistema (incluidos los sectores de arranque) y puede [agregar más carpetas.](customize-controlled-folders.md#protect-additional-folders)</span><span class="sxs-lookup"><span data-stu-id="bfc18-138">The [protected folders](#review-controlled-folder-access-events-in-windows-event-viewer) include common system folders (including boot sectors), and you can [add more folders](customize-controlled-folders.md#protect-additional-folders).</span></span> <span data-ttu-id="bfc18-139">También puedes permitir [que las aplicaciones](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) les den acceso a las carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="bfc18-139">You can also [allow apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) to give them access to the protected folders.</span></span>

<span data-ttu-id="bfc18-140">Puede usar el [modo de auditoría para](audit-windows-defender.md) evaluar cómo el acceso controlado a carpetas afectaría a su organización si estuviera habilitado.</span><span class="sxs-lookup"><span data-stu-id="bfc18-140">You can use [audit mode](audit-windows-defender.md) to evaluate how controlled folder access would impact your organization if it were enabled.</span></span> <span data-ttu-id="bfc18-141">También puede visitar el sitio web Windows Defender prueba en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que la característica funciona y ver cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="bfc18-141">You can also visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

<span data-ttu-id="bfc18-142">El acceso controlado a carpetas se admite en las siguientes versiones de Windows:</span><span class="sxs-lookup"><span data-stu-id="bfc18-142">Controlled folder access is supported on the following versions of Windows:</span></span>
- <span data-ttu-id="bfc18-143">[Windows 10, versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="bfc18-143">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) and later</span></span>
- [<span data-ttu-id="bfc18-144">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="bfc18-144">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a><span data-ttu-id="bfc18-145">Las carpetas del sistema Windows están protegidas de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="bfc18-145">Windows system folders are protected by default</span></span>

<span data-ttu-id="bfc18-146">Las carpetas del sistema windows están protegidas de forma predeterminada, junto con otras carpetas:</span><span class="sxs-lookup"><span data-stu-id="bfc18-146">Windows system folders are protected by default, along with several other folders:</span></span> 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> <span data-ttu-id="bfc18-147">Puedes configurar carpetas adicionales como protegidas, pero no puedes quitar las carpetas del sistema windows que están protegidas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bfc18-147">You can configure additional folders as protected, but you cannot remove the Windows system folders that are protected by default.</span></span>

## <a name="requirements-for-controlled-folder-access"></a><span data-ttu-id="bfc18-148">Requisitos para el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="bfc18-148">Requirements for controlled folder access</span></span>

<span data-ttu-id="bfc18-149">El acceso controlado a carpetas requiere habilitar la protección [en tiempo real de Antivirus de Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="bfc18-149">Controlled folder access requires enabling [Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="bfc18-150">Revisar eventos de acceso controlado a carpetas en el Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bfc18-150">Review controlled folder access events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="bfc18-151">Defender for Endpoint proporciona informes detallados sobre eventos y bloques como parte de sus escenarios de [investigación de alertas.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="bfc18-151">Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="bfc18-152">Puede consultar datos de punto de conexión de Microsoft Defender mediante [búsqueda avanzada](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="bfc18-152">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="bfc18-153">Si usa el modo [de auditoría,](audit-windows-defender.md)puede usar la búsqueda avanzada para ver cómo la configuración de acceso controlado a carpetas afectaría al entorno si estuvieran habilitadas. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bfc18-153">If you're using [audit mode](audit-windows-defender.md), you can use [advanced hunting](advanced-hunting-overview.md) to see how controlled folder access settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="bfc18-154">Consulta de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bfc18-154">Example query:</span></span>

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="bfc18-155">Revisar eventos de acceso controlado a carpetas en el Visor de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="bfc18-155">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="bfc18-156">Puedes revisar el registro de eventos de Windows para ver los eventos que se crean cuando el acceso controlado a carpetas bloquea (o audita) una aplicación:</span><span class="sxs-lookup"><span data-stu-id="bfc18-156">You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:</span></span>

1. <span data-ttu-id="bfc18-157">Descargue el [paquete de evaluación](https://aka.ms/mp7z2w) y extraiga el archivo *cfa-events.xml* a una ubicación de fácil acceso en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bfc18-157">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="bfc18-158">Escribe **Visor de eventos** en el menú Inicio para abrir el Visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="bfc18-158">Type **Event viewer** in the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="bfc18-159">En el panel izquierdo, en **Acciones**, seleccione **Importar vista personalizada...**.</span><span class="sxs-lookup"><span data-stu-id="bfc18-159">On the left panel, under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="bfc18-160">Navegue hasta donde ha extraído *cfa-events.xml* y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="bfc18-160">Navigate to where you extracted *cfa-events.xml* and select it.</span></span> <span data-ttu-id="bfc18-161">Como alternativa, [copie el XML directamente](event-views.md).</span><span class="sxs-lookup"><span data-stu-id="bfc18-161">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="bfc18-162">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bfc18-162">Select **OK**.</span></span>

<span data-ttu-id="bfc18-163">En la tabla siguiente se muestran los eventos relacionados con el acceso controlado a carpetas:</span><span class="sxs-lookup"><span data-stu-id="bfc18-163">The following table shows events related to controlled folder access:</span></span>

|<span data-ttu-id="bfc18-164">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="bfc18-164">Event ID</span></span> | <span data-ttu-id="bfc18-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfc18-165">Description</span></span> |
|:---|:---|
|<span data-ttu-id="bfc18-166">5007</span><span class="sxs-lookup"><span data-stu-id="bfc18-166">5007</span></span> | <span data-ttu-id="bfc18-167">Evento cuando se cambia la configuración</span><span class="sxs-lookup"><span data-stu-id="bfc18-167">Event when settings are changed</span></span> |
|<span data-ttu-id="bfc18-168">1124</span><span class="sxs-lookup"><span data-stu-id="bfc18-168">1124</span></span> | <span data-ttu-id="bfc18-169">Evento de acceso a carpetas controladas auditada</span><span class="sxs-lookup"><span data-stu-id="bfc18-169">Audited controlled folder access event</span></span> | 
|<span data-ttu-id="bfc18-170">1123</span><span class="sxs-lookup"><span data-stu-id="bfc18-170">1123</span></span> | <span data-ttu-id="bfc18-171">Evento de acceso controlado a carpetas bloqueadas</span><span class="sxs-lookup"><span data-stu-id="bfc18-171">Blocked controlled folder access event</span></span> |

## <a name="view-or-change-the-list-of-protected-folders"></a><span data-ttu-id="bfc18-172">Ver o cambiar la lista de carpetas protegidas</span><span class="sxs-lookup"><span data-stu-id="bfc18-172">View or change the list of protected folders</span></span>

<span data-ttu-id="bfc18-173">Puedes usar la aplicación Seguridad de Windows para ver la lista de carpetas protegidas por el acceso controlado a carpetas.</span><span class="sxs-lookup"><span data-stu-id="bfc18-173">You can use the Windows Security app to view the list of folders that are protected by controlled folder access.</span></span> 

1. <span data-ttu-id="bfc18-174">En el dispositivo Windows 10, abre la aplicación Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="bfc18-174">On your Windows 10 device, open the Windows Security app.</span></span>
2. <span data-ttu-id="bfc18-175">Seleccione **Protección contra & virus**.</span><span class="sxs-lookup"><span data-stu-id="bfc18-175">Select **Virus & threat protection**.</span></span>
3. <span data-ttu-id="bfc18-176">En **Protección contra ransomware,** seleccione **Administrar protección contra ransomware**.</span><span class="sxs-lookup"><span data-stu-id="bfc18-176">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>
4. <span data-ttu-id="bfc18-177">Si el acceso controlado a carpetas está desactivado, tendrás que activarlo.</span><span class="sxs-lookup"><span data-stu-id="bfc18-177">If controlled folder access is turned off, you'll need to turn it on.</span></span> <span data-ttu-id="bfc18-178">Seleccione **carpetas protegidas**.</span><span class="sxs-lookup"><span data-stu-id="bfc18-178">Select **protected folders**.</span></span>
5. <span data-ttu-id="bfc18-179">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bfc18-179">Do one of the following steps:</span></span>
   - <span data-ttu-id="bfc18-180">Para agregar una carpeta, seleccione **+ Agregar una carpeta protegida.**</span><span class="sxs-lookup"><span data-stu-id="bfc18-180">To add a folder, select **+ Add a protected folder**.</span></span>
   - <span data-ttu-id="bfc18-181">Para quitar una carpeta, selecciónelo y, a continuación, **seleccione Quitar**.</span><span class="sxs-lookup"><span data-stu-id="bfc18-181">To remove a folder, select it, and then select **Remove**.</span></span> 

> [!NOTE]
> <span data-ttu-id="bfc18-182">[Las carpetas del](#windows-system-folders-are-protected-by-default) sistema windows están protegidas de forma predeterminada y no puedes quitarlas de la lista.</span><span class="sxs-lookup"><span data-stu-id="bfc18-182">[Windows system folders](#windows-system-folders-are-protected-by-default) are protected by default, and you cannot remove them from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfc18-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfc18-183">See also</span></span>

- [<span data-ttu-id="bfc18-184">Evaluar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="bfc18-184">Evaluate controlled folder access</span></span>](evaluate-controlled-folder-access.md)
- [<span data-ttu-id="bfc18-185">Personalizar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="bfc18-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
- [<span data-ttu-id="bfc18-186">Proteger más carpetas</span><span class="sxs-lookup"><span data-stu-id="bfc18-186">Protect more folders</span></span>](customize-controlled-folders.md#protect-additional-folders)
