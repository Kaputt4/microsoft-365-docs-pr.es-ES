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
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: 2ef3fbeec65be512dfe07f1d533df4d8e9b31532
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644505"
---
# <a name="protect-your-network"></a><span data-ttu-id="33b86-104">Proteger la red</span><span class="sxs-lookup"><span data-stu-id="33b86-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="33b86-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="33b86-105">**Applies to:**</span></span>
- [<span data-ttu-id="33b86-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="33b86-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="33b86-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33b86-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="33b86-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="33b86-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="33b86-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="33b86-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="33b86-110">La protección de red ayuda a reducir la superficie de ataque de los dispositivos a partir de eventos basados en Internet.</span><span class="sxs-lookup"><span data-stu-id="33b86-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="33b86-111">Impide que los empleados utilicen cualquier aplicación para tener acceso a dominios peligrosos que pueden hospedar estafas de suplantación de identidad (phishing), vulnerabilidades de seguridad y otro contenido malintencionado en Internet.</span><span class="sxs-lookup"><span data-stu-id="33b86-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="33b86-112">La protección de red expande el ámbito de [SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) de Microsoft Defender para bloquear todo el tráfico HTTP saliente que intente conectarse a orígenes de baja reputación (según el dominio o el nombre de host).</span><span class="sxs-lookup"><span data-stu-id="33b86-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="33b86-113">La protección de red se admite en Windows, a partir de Windows 10, versión 1709.</span><span class="sxs-lookup"><span data-stu-id="33b86-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> 

<span data-ttu-id="33b86-114">Para obtener más información acerca de cómo habilitar la protección de red, vea [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="33b86-114">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="33b86-115">Use directivas de grupo, PowerShell o CSP mdm para habilitar y administrar la protección de red en la red.</span><span class="sxs-lookup"><span data-stu-id="33b86-115">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="33b86-116">Consulta el sitio de prueba de ATP de Microsoft Defender en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para ver cómo funciona la protección de red.</span><span class="sxs-lookup"><span data-stu-id="33b86-116">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="33b86-117">La protección de red funciona mejor con [Microsoft Defender para endpoint,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)lo que le ofrece informes detallados sobre eventos y bloques de protección contra vulnerabilidades como parte de escenarios de [investigación de alertas.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="33b86-117">Network protection works best with [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="33b86-118">Cuando la protección de red bloquea una conexión, se muestra una notificación desde el Centro de acciones.</span><span class="sxs-lookup"><span data-stu-id="33b86-118">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="33b86-119">El equipo de operaciones de seguridad [puede personalizar la notificación](customize-attack-surface-reduction.md#customize-the-notification) con los detalles de la organización y la información de contacto.</span><span class="sxs-lookup"><span data-stu-id="33b86-119">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="33b86-120">Además, las reglas de reducción de superficie de ataque individuales se pueden habilitar y personalizar para adaptarse a determinadas técnicas que se deben supervisar.</span><span class="sxs-lookup"><span data-stu-id="33b86-120">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="33b86-121">También puede usar el modo [de auditoría para](audit-windows-defender.md) evaluar cómo afectaría la protección de red a su organización si estuviera habilitada.</span><span class="sxs-lookup"><span data-stu-id="33b86-121">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="33b86-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33b86-122">Requirements</span></span>

<span data-ttu-id="33b86-123">La protección de red requiere Windows 10 Pro o Enterprise y la protección en tiempo real del Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="33b86-123">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="33b86-124">Versión de Windows</span><span class="sxs-lookup"><span data-stu-id="33b86-124">Windows version</span></span> | <span data-ttu-id="33b86-125">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="33b86-125">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="33b86-126">Windows 10 versión 1709 o posterior</span><span class="sxs-lookup"><span data-stu-id="33b86-126">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="33b86-127">Windows Server 1803 o posterior</span><span class="sxs-lookup"><span data-stu-id="33b86-127">Windows Server 1803 or later</span></span> | <span data-ttu-id="33b86-128">[La protección en tiempo real de Antivirus](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) de Microsoft Defender y la protección [en](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) la nube deben estar habilitadas</span><span class="sxs-lookup"><span data-stu-id="33b86-128">[Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="33b86-129">Después de habilitar los servicios, es posible que deba configurar la red o firewall para permitir las conexiones entre los servicios y los dispositivos (también denominados puntos de conexión).</span><span class="sxs-lookup"><span data-stu-id="33b86-129">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- <span data-ttu-id="33b86-130">.smartscreen.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="33b86-130">.smartscreen.microsoft.com</span></span>
- <span data-ttu-id="33b86-131">.smartscreen-prod.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="33b86-131">.smartscreen-prod.microsoft.com</span></span>

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="33b86-132">Revisar los eventos de protección de red en el Centro de seguridad de Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="33b86-132">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="33b86-133">Microsoft Defender para endpoint proporciona informes detallados sobre eventos y bloques como parte de sus escenarios de [investigación de alertas.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="33b86-133">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="33b86-134">Puede consultar datos de punto de conexión de Microsoft Defender mediante [búsqueda avanzada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="33b86-134">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="33b86-135">Si usa el modo [de auditoría,](audit-windows-defender.md)puede usar la búsqueda avanzada para ver cómo la configuración de protección de red afectaría al entorno si estuvieran habilitadas.</span><span class="sxs-lookup"><span data-stu-id="33b86-135">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="33b86-136">Esta es una consulta de ejemplo</span><span class="sxs-lookup"><span data-stu-id="33b86-136">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="33b86-137">Revisar eventos de protección de red en el Visor de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="33b86-137">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="33b86-138">Puedes revisar el registro de eventos de Windows para ver los eventos que se crean cuando la protección de red bloquea (o audita) el acceso a un dominio o IP malintencionado:</span><span class="sxs-lookup"><span data-stu-id="33b86-138">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="33b86-139">[Copie el XML directamente](event-views.md).</span><span class="sxs-lookup"><span data-stu-id="33b86-139">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="33b86-140">Elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="33b86-140">Select **OK**.</span></span>

<span data-ttu-id="33b86-141">Este procedimiento crea una vista personalizada que filtra para mostrar solo los siguientes eventos relacionados con la protección de red:</span><span class="sxs-lookup"><span data-stu-id="33b86-141">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="33b86-142">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="33b86-142">Event ID</span></span> | <span data-ttu-id="33b86-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="33b86-143">Description</span></span> |
|:---|:---|
| <span data-ttu-id="33b86-144">5007</span><span class="sxs-lookup"><span data-stu-id="33b86-144">5007</span></span> | <span data-ttu-id="33b86-145">Evento cuando se cambia la configuración</span><span class="sxs-lookup"><span data-stu-id="33b86-145">Event when settings are changed</span></span> |
| <span data-ttu-id="33b86-146">1125</span><span class="sxs-lookup"><span data-stu-id="33b86-146">1125</span></span> | <span data-ttu-id="33b86-147">Evento cuando la protección de red se dispara en modo auditoría</span><span class="sxs-lookup"><span data-stu-id="33b86-147">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="33b86-148">1126</span><span class="sxs-lookup"><span data-stu-id="33b86-148">1126</span></span> | <span data-ttu-id="33b86-149">Evento cuando la protección de red se desen llamas en modo de bloqueo</span><span class="sxs-lookup"><span data-stu-id="33b86-149">Event when network protection fires in block mode</span></span> |

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="33b86-150">Solución de problemas de protección de red</span><span class="sxs-lookup"><span data-stu-id="33b86-150">Network protection troubleshooting</span></span>

<span data-ttu-id="33b86-151">Debido al entorno en el que se ejecuta Network Protection, Es posible que Microsoft no pueda detectar la configuración de proxy del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="33b86-151">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="33b86-152">En algunos casos, los clientes de Protección de red no pueden llegar al servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="33b86-152">In some cases, Network Protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="33b86-153">Para resolver el problema de conectividad, los clientes con licencias E5 deben configurar una de las siguientes claves del Registro de Defender:</span><span class="sxs-lookup"><span data-stu-id="33b86-153">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="33b86-154">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="33b86-154">Related articles</span></span>

- <span data-ttu-id="33b86-155">[Evaluar la protección de](evaluate-network-protection.md) red | Realice un escenario rápido que demuestre cómo funciona la característica y qué eventos se crearían normalmente.</span><span class="sxs-lookup"><span data-stu-id="33b86-155">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="33b86-156">[Habilitar la protección de](enable-network-protection.md) red | Use directivas de grupo, PowerShell o CSP mdm para habilitar y administrar la protección de red en la red.</span><span class="sxs-lookup"><span data-stu-id="33b86-156">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
