---
title: Probar cómo funcionan las características de Microsoft Defender para endpoint en modo auditoría
description: El modo auditoría le ayuda a ver cómo Microsoft Defender para Endpoint protegería sus dispositivos si estaba habilitado.
keywords: protección contra vulnerabilidades de seguridad, auditoría, auditoría, modo, habilitado, deshabilitado, prueba, demostración, evaluación, laboratorio
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ce652d58be2d9ff28d82c088d5471a7bffdf6dc
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570977"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a><span data-ttu-id="cbfd0-104">Probar cómo funcionan las características de Microsoft Defender para endpoint en modo auditoría</span><span class="sxs-lookup"><span data-stu-id="cbfd0-104">Test how Microsoft Defender for Endpoint features work in audit mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cbfd0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="cbfd0-105">**Applies to:**</span></span>
- [<span data-ttu-id="cbfd0-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="cbfd0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="cbfd0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cbfd0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="cbfd0-108">Puedes habilitar reglas de reducción de superficie de ataque, protección contra vulnerabilidades, protección de red y acceso controlado a carpetas en modo auditoría.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-108">You can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="cbfd0-109">El modo auditoría te permite ver un registro de lo *que hubiera* ocurrido si hubieras habilitado la característica.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-109">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="cbfd0-110">Es posible que desee habilitar el modo de auditoría al probar cómo funcionarán las características en su organización.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-110">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="cbfd0-111">Esto te ayudará a asegurarte de que tus aplicaciones de línea de negocio no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-111">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="cbfd0-112">También puede obtener una idea de cuántos intentos de modificación de archivos sospechosos se producen durante un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-112">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="cbfd0-113">Las características no bloquearán ni impedirán que se modifiquen aplicaciones, scripts o archivos.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-113">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="cbfd0-114">Sin embargo, el Registro de eventos de Windows registrará eventos como si las características estuvieran totalmente habilitadas.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-114">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="cbfd0-115">Con el modo de auditoría, puedes revisar el registro de eventos para ver qué impacto habría tenido la característica si se hubiera habilitado.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-115">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="cbfd0-116">Para buscar las entradas auditadas, vaya a **Aplicaciones y servicios**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-116">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="cbfd0-117">Puedes usar Defender para endpoint para obtener más detalles para cada evento, especialmente para investigar reglas de reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-117">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="cbfd0-118">El uso de la consola defender para endpoint te permite investigar problemas como parte de la escala de tiempo de alerta y [los escenarios de investigación.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="cbfd0-118">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="cbfd0-119">Puede usar la directiva de grupo, PowerShell y los proveedores de servicios de configuración (CSP) para habilitar el modo de auditoría.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-119">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="cbfd0-120">También puedes visitar el sitio web Windows Defender Testground en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las características funcionan y ver cómo funcionan.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-120">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="cbfd0-121">**Opciones de auditoría**</span><span class="sxs-lookup"><span data-stu-id="cbfd0-121">**Audit options**</span></span> | <span data-ttu-id="cbfd0-122">**Cómo habilitar el modo de auditoría**</span><span class="sxs-lookup"><span data-stu-id="cbfd0-122">**How to enable audit mode**</span></span> | <span data-ttu-id="cbfd0-123">**Cómo ver eventos**</span><span class="sxs-lookup"><span data-stu-id="cbfd0-123">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="cbfd0-124">La auditoría se aplica a todos los eventos</span><span class="sxs-lookup"><span data-stu-id="cbfd0-124">Audit applies to all events</span></span> | [<span data-ttu-id="cbfd0-125">Habilitar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="cbfd0-125">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="cbfd0-126">Eventos de acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="cbfd0-126">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="cbfd0-127">La auditoría se aplica a reglas individuales</span><span class="sxs-lookup"><span data-stu-id="cbfd0-127">Audit applies to individual rules</span></span> | [<span data-ttu-id="cbfd0-128">Habilitar las reglas de la reducción de superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="cbfd0-128">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="cbfd0-129">Eventos de regla de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="cbfd0-129">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="cbfd0-130">La auditoría se aplica a todos los eventos</span><span class="sxs-lookup"><span data-stu-id="cbfd0-130">Audit applies to all events</span></span> | [<span data-ttu-id="cbfd0-131">Habilitar la protección de red</span><span class="sxs-lookup"><span data-stu-id="cbfd0-131">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="cbfd0-132">Eventos de protección de red</span><span class="sxs-lookup"><span data-stu-id="cbfd0-132">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="cbfd0-133">La auditoría se aplica a mitigaciones individuales</span><span class="sxs-lookup"><span data-stu-id="cbfd0-133">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="cbfd0-134">Habilitar la protección contra vulnerabilidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="cbfd0-134">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="cbfd0-135">Eventos de protección contra vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="cbfd0-135">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a><span data-ttu-id="cbfd0-136">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cbfd0-136">Related topics</span></span>

* [<span data-ttu-id="cbfd0-137">Proteger los dispositivos contra vulnerabilidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="cbfd0-137">Protect devices from exploits</span></span>](exploit-protection.md)
* [<span data-ttu-id="cbfd0-138">Reducir superficies de ataque con reglas de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="cbfd0-138">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="cbfd0-139">Proteger la red</span><span class="sxs-lookup"><span data-stu-id="cbfd0-139">Protect your network</span></span>](network-protection.md)
* [<span data-ttu-id="cbfd0-140">Proteger carpetas importantes</span><span class="sxs-lookup"><span data-stu-id="cbfd0-140">Protect important folders</span></span>](controlled-folders.md)
