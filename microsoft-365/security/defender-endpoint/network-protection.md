---
title: Usar la protección de red para ayudar a evitar conexiones a sitios con problemas
description: Proteger la red evitando que los usuarios accedan a direcciones de red malintencionadas y sospechosas conocidas
keywords: Protección de red, vulnerabilidades, sitio web malintencionado, ip, dominio, dominios
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b6b664d471e238e2feb1e1aedd100c1299fc5bbe
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844267"
---
# <a name="protect-your-network"></a><span data-ttu-id="884c7-104">Proteger la red</span><span class="sxs-lookup"><span data-stu-id="884c7-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="884c7-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="884c7-105">**Applies to:**</span></span>
- [<span data-ttu-id="884c7-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="884c7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="884c7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="884c7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="884c7-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="884c7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="884c7-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="884c7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="884c7-110">La protección de red ayuda a reducir la superficie de ataque de los dispositivos a partir de eventos basados en Internet.</span><span class="sxs-lookup"><span data-stu-id="884c7-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="884c7-111">Impide que los empleados utilicen cualquier aplicación para tener acceso a dominios peligrosos que pueden hospedar estafas de suplantación de identidad (phishing), vulnerabilidades de seguridad y otro contenido malintencionado en Internet.</span><span class="sxs-lookup"><span data-stu-id="884c7-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="884c7-112">La protección de red expande el ámbito de [SmartScreen de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) para bloquear todo el tráfico HTTP saliente que intente conectarse a orígenes de reputación baja (según el dominio o el nombre de host).</span><span class="sxs-lookup"><span data-stu-id="884c7-112">Network protection expands the scope of [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="884c7-113">La protección de red se admite Windows, empezando por Windows 10, versión 1709.</span><span class="sxs-lookup"><span data-stu-id="884c7-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> <span data-ttu-id="884c7-114">La protección de red aún no se admite en otros sistemas operativos, pero la protección web se admite mediante el nuevo Microsoft Edge según Chromium.</span><span class="sxs-lookup"><span data-stu-id="884c7-114">Network protection is not yet supported on other operating systems, but web protection is supported using the new Microsoft Edge based on Chromium.</span></span> <span data-ttu-id="884c7-115">Para obtener más información, vea [Protección web](web-protection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="884c7-115">To learn more, see [Web protection](web-protection-overview.md).</span></span>

<span data-ttu-id="884c7-116">La protección de red amplía la protección de [la protección web](web-protection-overview.md) al nivel del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="884c7-116">Network protection extends the protection in [Web protection](web-protection-overview.md) to the operating system level.</span></span> <span data-ttu-id="884c7-117">Proporciona funcionalidad de protección web en Edge a otros exploradores compatibles y aplicaciones que no son exploradores.</span><span class="sxs-lookup"><span data-stu-id="884c7-117">It provides web protection functionality in Edge to other supported browsers and non-browser applications.</span></span> <span data-ttu-id="884c7-118">Además, la protección de red proporciona visibilidad y bloqueo de indicadores de peligro (IIC) cuando se usa con detección [y respuesta de extremos.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="884c7-118">In addition, network protection provides visibility and blocking of indicators of compromise (IOCs) when used with [Endpoint detection and response](overview-endpoint-detection-response.md).</span></span> <span data-ttu-id="884c7-119">Por ejemplo, la protección de red funciona con los [indicadores personalizados](manage-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="884c7-119">For example, network protection works with your [custom indicators](manage-indicators.md).</span></span>

<span data-ttu-id="884c7-120">Para obtener más información acerca de cómo habilitar la protección de red, vea [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="884c7-120">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="884c7-121">Use directivas de grupo, PowerShell o CSP mdm para habilitar y administrar la protección de red en la red.</span><span class="sxs-lookup"><span data-stu-id="884c7-121">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="884c7-122">Consulta el sitio de prueba de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para ver cómo funciona la protección de red.</span><span class="sxs-lookup"><span data-stu-id="884c7-122">See the Microsoft Defender for Endpoint testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="884c7-123">La protección de red funciona mejor con [Microsoft Defender para endpoint,](microsoft-defender-endpoint.md)lo que le ofrece informes detallados sobre eventos y bloques de protección contra vulnerabilidades como parte de escenarios de [investigación de alertas.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="884c7-123">Network protection works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="884c7-124">Cuando la protección de red bloquea una conexión, se muestra una notificación desde el Centro de acciones.</span><span class="sxs-lookup"><span data-stu-id="884c7-124">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="884c7-125">El equipo de operaciones de seguridad [puede personalizar la notificación](customize-attack-surface-reduction.md#customize-the-notification) con los detalles de la organización y la información de contacto.</span><span class="sxs-lookup"><span data-stu-id="884c7-125">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="884c7-126">Además, las reglas de reducción de superficie de ataque individuales se pueden habilitar y personalizar para adaptarse a determinadas técnicas que se deben supervisar.</span><span class="sxs-lookup"><span data-stu-id="884c7-126">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="884c7-127">También puede usar el modo [de auditoría para](audit-windows-defender.md) evaluar cómo afectaría la protección de red a su organización si estuviera habilitada.</span><span class="sxs-lookup"><span data-stu-id="884c7-127">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="884c7-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="884c7-128">Requirements</span></span>

<span data-ttu-id="884c7-129">La protección de red Windows 10 Pro o Enterprise y Antivirus de Microsoft Defender protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="884c7-129">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="884c7-130">Versión de Windows</span><span class="sxs-lookup"><span data-stu-id="884c7-130">Windows version</span></span> | <span data-ttu-id="884c7-131">Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="884c7-131">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="884c7-132">Windows 10 versión 1709 o posterior</span><span class="sxs-lookup"><span data-stu-id="884c7-132">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="884c7-133">Windows Servidor 1803 o posterior</span><span class="sxs-lookup"><span data-stu-id="884c7-133">Windows Server 1803 or later</span></span> | <span data-ttu-id="884c7-134">[Antivirus de Microsoft Defender la protección en tiempo real](configure-real-time-protection-microsoft-defender-antivirus.md) y la protección [en](enable-cloud-protection-microsoft-defender-antivirus.md) la nube deben estar habilitadas</span><span class="sxs-lookup"><span data-stu-id="884c7-134">[Microsoft Defender Antivirus real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="884c7-135">Después de habilitar los servicios, es posible que deba configurar la red o firewall para permitir las conexiones entre los servicios y los dispositivos (también denominados puntos de conexión).</span><span class="sxs-lookup"><span data-stu-id="884c7-135">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="884c7-136">Revisar los eventos de protección de red en el Centro de seguridad de Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="884c7-136">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="884c7-137">Microsoft Defender para endpoint proporciona informes detallados sobre eventos y bloques como parte de sus escenarios de [investigación de alertas.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="884c7-137">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="884c7-138">Puede consultar datos de punto de conexión de Microsoft Defender mediante la [búsqueda avanzada](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="884c7-138">You can query Microsoft Defender for Endpoint data by using [advanced hunting](advanced-hunting-overview.md).</span></span> <span data-ttu-id="884c7-139">Si usa el modo [de auditoría,](audit-windows-defender.md)puede usar la búsqueda avanzada para ver cómo la configuración de protección de red afectaría al entorno si estuvieran habilitadas.</span><span class="sxs-lookup"><span data-stu-id="884c7-139">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="884c7-140">Esta es una consulta de ejemplo</span><span class="sxs-lookup"><span data-stu-id="884c7-140">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="884c7-141">Revisar eventos de protección de red en Windows visor de eventos</span><span class="sxs-lookup"><span data-stu-id="884c7-141">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="884c7-142">Puede revisar el registro Windows eventos para ver los eventos que se crean cuando la protección de red bloquea (o audita) el acceso a una IP o dominio malintencionado:</span><span class="sxs-lookup"><span data-stu-id="884c7-142">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="884c7-143">[Copie el XML directamente](event-views.md).</span><span class="sxs-lookup"><span data-stu-id="884c7-143">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="884c7-144">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="884c7-144">Select **OK**.</span></span>

<span data-ttu-id="884c7-145">Este procedimiento crea una vista personalizada que filtra para mostrar solo los siguientes eventos relacionados con la protección de red:</span><span class="sxs-lookup"><span data-stu-id="884c7-145">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="884c7-146">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="884c7-146">Event ID</span></span> | <span data-ttu-id="884c7-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="884c7-147">Description</span></span> |
|:---|:---|
| <span data-ttu-id="884c7-148">5007</span><span class="sxs-lookup"><span data-stu-id="884c7-148">5007</span></span> | <span data-ttu-id="884c7-149">Evento cuando se cambia la configuración</span><span class="sxs-lookup"><span data-stu-id="884c7-149">Event when settings are changed</span></span> |
| <span data-ttu-id="884c7-150">1125</span><span class="sxs-lookup"><span data-stu-id="884c7-150">1125</span></span> | <span data-ttu-id="884c7-151">Evento cuando la protección de red se dispara en modo auditoría</span><span class="sxs-lookup"><span data-stu-id="884c7-151">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="884c7-152">1126</span><span class="sxs-lookup"><span data-stu-id="884c7-152">1126</span></span> | <span data-ttu-id="884c7-153">Evento cuando la protección de red se desen llamas en modo de bloqueo</span><span class="sxs-lookup"><span data-stu-id="884c7-153">Event when network protection fires in block mode</span></span> |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a><span data-ttu-id="884c7-154">Consideraciones para Windows escritorio virtual que se Windows 10 Enterprise multi-sesión</span><span class="sxs-lookup"><span data-stu-id="884c7-154">Considerations for Windows virtual desktop running Windows 10 Enterprise Multi-Session</span></span>

<span data-ttu-id="884c7-155">Debido a la naturaleza de varios usuarios de Windows 10 Enterprise, tenga en cuenta los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="884c7-155">Due to the multi-user nature of Windows 10 Enterprise, keep the following points in mind:</span></span>

1. <span data-ttu-id="884c7-156">La protección de red es una característica de todo el dispositivo y no se puede dirigir a sesiones de usuario específicas.</span><span class="sxs-lookup"><span data-stu-id="884c7-156">Network protection is a device-wide feature and cannot be targeted to specific user sessions.</span></span>

2. <span data-ttu-id="884c7-157">Las directivas de filtrado de contenido web también están en todo el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="884c7-157">Web content filtering policies are also device wide.</span></span>

3. <span data-ttu-id="884c7-158">Si necesita diferenciar entre grupos de usuarios, considere la posibilidad de crear asignaciones Windows grupos de host de Escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="884c7-158">If you need to differentiate between user groups, consider creating separate Windows Virtual Desktop host pools and assignments.</span></span>

4. <span data-ttu-id="884c7-159">Pruebe la protección de red en modo auditoría para evaluar su comportamiento antes de implementarla.</span><span class="sxs-lookup"><span data-stu-id="884c7-159">Test network protection in audit mode to assess its behavior before rolling out.</span></span> 

5. <span data-ttu-id="884c7-160">Considere la posibilidad de redimensionar la implementación si tiene un gran número de usuarios o un gran número de sesiones de varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="884c7-160">Consider resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span></span>

### <a name="alternative-option-for-network-protection"></a><span data-ttu-id="884c7-161">Opción alternativa para la protección de red</span><span class="sxs-lookup"><span data-stu-id="884c7-161">Alternative option for network protection</span></span>

<span data-ttu-id="884c7-162">Para Windows 10 Enterprise Multi-Session 1909 y versiones 2010, que se usan en Windows Virtual Desktop en Azure, la protección de red para Microsoft Edge puede habilitarse mediante el siguiente método:</span><span class="sxs-lookup"><span data-stu-id="884c7-162">For Windows 10 Enterprise Multi-Session 1909 and up, used in Windows Virtual Desktop on Azure, network protection for Microsoft Edge can be enabled using the following method:</span></span>

1. <span data-ttu-id="884c7-163">Use [Activar la protección de red](enable-network-protection.md) y siga las instrucciones para aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="884c7-163">Use [Turn on network protection](enable-network-protection.md) and follow the instructions to apply your policy.</span></span>

2. <span data-ttu-id="884c7-164">Ejecute el siguiente comando de PowerShell: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span><span class="sxs-lookup"><span data-stu-id="884c7-164">Execute the following PowerShell command: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span></span>

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="884c7-165">Solución de problemas de protección de red</span><span class="sxs-lookup"><span data-stu-id="884c7-165">Network protection troubleshooting</span></span>

<span data-ttu-id="884c7-166">Debido al entorno en el que se ejecuta Network Protection, Es posible que Microsoft no pueda detectar la configuración de proxy del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="884c7-166">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="884c7-167">En algunos casos, los clientes de protección de red no pueden llegar al servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="884c7-167">In some cases, network protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="884c7-168">Para resolver el problema de conectividad, los clientes con licencias E5 deben configurar una de las siguientes claves del Registro de Defender:</span><span class="sxs-lookup"><span data-stu-id="884c7-168">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="884c7-169">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="884c7-169">Related articles</span></span>

- <span data-ttu-id="884c7-170">[Evaluar la protección de](evaluate-network-protection.md) red | Realice un escenario rápido que demuestre cómo funciona la característica y qué eventos se crearían normalmente.</span><span class="sxs-lookup"><span data-stu-id="884c7-170">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="884c7-171">[Habilitar la protección de](enable-network-protection.md) red | Use directivas de grupo, PowerShell o CSP mdm para habilitar y administrar la protección de red en la red.</span><span class="sxs-lookup"><span data-stu-id="884c7-171">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
