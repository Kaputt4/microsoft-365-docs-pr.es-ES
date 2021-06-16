---
title: Evaluar protección de red
description: Vea cómo funciona la protección de red probando escenarios comunes contra los que protege.
keywords: Protección de red, vulnerabilidades, sitio web malintencionado, ip, dominio, dominios, evaluación, prueba, demostración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 03d05966401c8f3a8bdcec413e85c9a6d2a3ec5c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926576"
---
# <a name="evaluate-network-protection"></a><span data-ttu-id="8aef5-104">Evaluar protección de red</span><span class="sxs-lookup"><span data-stu-id="8aef5-104">Evaluate network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8aef5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8aef5-105">**Applies to:**</span></span>
- [<span data-ttu-id="8aef5-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="8aef5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [<span data-ttu-id="8aef5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8aef5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="8aef5-108">[La protección de](network-protection.md) red ayuda a evitar que los empleados utilicen cualquier aplicación para tener acceso a dominios peligrosos que pueden hospedar estafas de suplantación de identidad(phishing), vulnerabilidades de seguridad y otro contenido malintencionado en Internet.</span><span class="sxs-lookup"><span data-stu-id="8aef5-108">[Network protection](network-protection.md) helps prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the Internet.</span></span>

<span data-ttu-id="8aef5-109">Este artículo le ayuda a evaluar la protección de red habilitando la característica y guiándolo a un sitio de prueba.</span><span class="sxs-lookup"><span data-stu-id="8aef5-109">This article helps you evaluate network protection by enabling the feature and guiding you to a testing site.</span></span> <span data-ttu-id="8aef5-110">Los sitios de este artículo de evaluación no son malintencionados.</span><span class="sxs-lookup"><span data-stu-id="8aef5-110">The sites in this evaluation article aren't malicious.</span></span> <span data-ttu-id="8aef5-111">Son sitios web especialmente creados que pretenden ser malintencionados.</span><span class="sxs-lookup"><span data-stu-id="8aef5-111">They're specially created websites that pretend to be malicious.</span></span> <span data-ttu-id="8aef5-112">El sitio replicará el comportamiento que se produciría si un usuario visitase un sitio o dominio malintencionado.</span><span class="sxs-lookup"><span data-stu-id="8aef5-112">The site will replicate the behavior that would happen if a user visited a malicious site or domain.</span></span>

> [!TIP]
> <span data-ttu-id="8aef5-113">También puedes visitar el sitio web del campo de prueba de Microsoft Defender [en demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para ver cómo funcionan otras características de protección.</span><span class="sxs-lookup"><span data-stu-id="8aef5-113">You can also visit the Microsoft Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how other protection features work.</span></span>

## <a name="enable-network-protection-in-audit-mode"></a><span data-ttu-id="8aef5-114">Habilitar la protección de red en modo auditoría</span><span class="sxs-lookup"><span data-stu-id="8aef5-114">Enable network protection in audit mode</span></span>

<span data-ttu-id="8aef5-115">Habilite la protección de red en modo auditoría para ver qué direcciones IP y dominios se habrían bloqueado.</span><span class="sxs-lookup"><span data-stu-id="8aef5-115">Enable network protection in audit mode to see which IP addresses and domains would have been blocked.</span></span> <span data-ttu-id="8aef5-116">Puedes asegurarte de que no afecta a las aplicaciones de línea de negocio u obtener una idea de la frecuencia con la que se producen los bloqueos.</span><span class="sxs-lookup"><span data-stu-id="8aef5-116">You can make sure it doesn't affect line-of-business apps, or get an idea of how often blocks occur.</span></span>

1. <span data-ttu-id="8aef5-117">Escriba **powershell** en el menú Inicio, haga clic con el botón Windows PowerShell **y** seleccione Ejecutar como **administrador**</span><span class="sxs-lookup"><span data-stu-id="8aef5-117">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="8aef5-118">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8aef5-118">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a><span data-ttu-id="8aef5-119">Visitar un dominio malintencionado (falso)</span><span class="sxs-lookup"><span data-stu-id="8aef5-119">Visit a (fake) malicious domain</span></span>

1. <span data-ttu-id="8aef5-120">Abre Internet Explorer, Google Chrome o cualquier otro explorador de tu elección.</span><span class="sxs-lookup"><span data-stu-id="8aef5-120">Open Internet Explorer, Google Chrome, or any other browser of your choice.</span></span>

1. <span data-ttu-id="8aef5-121">Vaya a [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span><span class="sxs-lookup"><span data-stu-id="8aef5-121">Go to [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span></span>

<span data-ttu-id="8aef5-122">Se permitirá la conexión de red y se mostrará un mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="8aef5-122">The network connection will be allowed and a test message will be displayed.</span></span>

![Notificación de ejemplo que indica Conexión bloqueada: el administrador de TI Seguridad de Windows bloquear esta conexión de red.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="8aef5-125">Revisar eventos de protección de red en Windows visor de eventos</span><span class="sxs-lookup"><span data-stu-id="8aef5-125">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="8aef5-126">Para revisar las aplicaciones que se habrían bloqueado, abra el Visor de eventos y filtre el identificador de evento 1125 en el registro de Microsoft-Windows-Windows-Defender/Operational.</span><span class="sxs-lookup"><span data-stu-id="8aef5-126">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1125 in the Microsoft-Windows-Windows-Defender/Operational log.</span></span> <span data-ttu-id="8aef5-127">En la tabla siguiente se enumeran todos los eventos de protección de red.</span><span class="sxs-lookup"><span data-stu-id="8aef5-127">The following table lists all network protection events.</span></span>

| <span data-ttu-id="8aef5-128">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8aef5-128">Event ID</span></span> | <span data-ttu-id="8aef5-129">Provide/Source</span><span class="sxs-lookup"><span data-stu-id="8aef5-129">Provide/Source</span></span> | <span data-ttu-id="8aef5-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="8aef5-130">Description</span></span> |
|-|-|-|
|<span data-ttu-id="8aef5-131">5007</span><span class="sxs-lookup"><span data-stu-id="8aef5-131">5007</span></span> | <span data-ttu-id="8aef5-132">Windows Defender (operativo)</span><span class="sxs-lookup"><span data-stu-id="8aef5-132">Windows Defender (Operational)</span></span> | <span data-ttu-id="8aef5-133">Evento cuando se cambia la configuración</span><span class="sxs-lookup"><span data-stu-id="8aef5-133">Event when settings are changed</span></span> |
|<span data-ttu-id="8aef5-134">1125</span><span class="sxs-lookup"><span data-stu-id="8aef5-134">1125</span></span> | <span data-ttu-id="8aef5-135">Windows Defender (operativo)</span><span class="sxs-lookup"><span data-stu-id="8aef5-135">Windows Defender (Operational)</span></span> | <span data-ttu-id="8aef5-136">Evento cuando se audita una conexión de red</span><span class="sxs-lookup"><span data-stu-id="8aef5-136">Event when a network connection is audited</span></span> |
|<span data-ttu-id="8aef5-137">1126</span><span class="sxs-lookup"><span data-stu-id="8aef5-137">1126</span></span> | <span data-ttu-id="8aef5-138">Windows Defender (operativo)</span><span class="sxs-lookup"><span data-stu-id="8aef5-138">Windows Defender (Operational)</span></span> | <span data-ttu-id="8aef5-139">Evento cuando se bloquea una conexión de red</span><span class="sxs-lookup"><span data-stu-id="8aef5-139">Event when a network connection is blocked</span></span> |

## <a name="see-also"></a><span data-ttu-id="8aef5-140">Ver también</span><span class="sxs-lookup"><span data-stu-id="8aef5-140">See also</span></span>

* [<span data-ttu-id="8aef5-141">Protección de red</span><span class="sxs-lookup"><span data-stu-id="8aef5-141">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="8aef5-142">Habilitar la protección de red</span><span class="sxs-lookup"><span data-stu-id="8aef5-142">Enable network protection</span></span>](enable-network-protection.md)
* [<span data-ttu-id="8aef5-143">Solucionar problemas de protección de red</span><span class="sxs-lookup"><span data-stu-id="8aef5-143">Troubleshoot network protection</span></span>](troubleshoot-np.md)
