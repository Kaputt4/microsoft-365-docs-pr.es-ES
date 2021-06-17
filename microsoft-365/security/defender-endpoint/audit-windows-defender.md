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
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985101"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="74635-104">Probar la reducción de superficie de ataque en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="74635-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="74635-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="74635-105">**Applies to:**</span></span>

- [<span data-ttu-id="74635-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="74635-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="74635-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74635-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="74635-108">Como parte del equipo de seguridad de la organización, puedes configurar las capacidades de reducción de superficie de ataque para que se ejecuten en modo auditoría para ver cómo funcionarán.</span><span class="sxs-lookup"><span data-stu-id="74635-108">As part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work.</span></span> <span data-ttu-id="74635-109">En el modo de auditoría, puede habilitar:</span><span class="sxs-lookup"><span data-stu-id="74635-109">In audit mode, you can enable:</span></span>

- <span data-ttu-id="74635-110">Reglas de reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="74635-110">Attack surface reduction rules</span></span>
- <span data-ttu-id="74635-111">Protección contra vulnerabilidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="74635-111">Exploit protection</span></span>
- <span data-ttu-id="74635-112">Protección de red</span><span class="sxs-lookup"><span data-stu-id="74635-112">Network protection</span></span>
- <span data-ttu-id="74635-113">Acceso controlado a carpetas en modo auditoría</span><span class="sxs-lookup"><span data-stu-id="74635-113">And controlled folder access in audit mode</span></span>

<span data-ttu-id="74635-114">El modo auditoría te permite ver un registro de lo *que hubiera* ocurrido si hubieras habilitado la característica.</span><span class="sxs-lookup"><span data-stu-id="74635-114">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="74635-115">Puedes habilitar el modo de auditoría al probar cómo funcionarán las características.</span><span class="sxs-lookup"><span data-stu-id="74635-115">You can enable audit mode when testing how the features will work.</span></span> <span data-ttu-id="74635-116">Esto te ayudará a asegurarte de que tus aplicaciones de línea de negocio no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="74635-116">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="74635-117">También puede obtener una idea de cuántos intentos de modificación de archivos sospechosos se producen durante un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="74635-117">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="74635-118">Las características no bloquearán ni impedirán que se modifiquen aplicaciones, scripts o archivos.</span><span class="sxs-lookup"><span data-stu-id="74635-118">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="74635-119">Sin embargo, el Windows de eventos registrará eventos como si las características estuvieran totalmente habilitadas.</span><span class="sxs-lookup"><span data-stu-id="74635-119">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="74635-120">Con el modo de auditoría, puedes revisar el registro de eventos para ver qué efecto habría tenido la característica si se hubiera habilitado.</span><span class="sxs-lookup"><span data-stu-id="74635-120">With audit mode, you can review the event log to see what affect the feature would have had if it was enabled.</span></span>

<span data-ttu-id="74635-121">Para buscar las entradas auditadas, vaya a **Aplicaciones y servicios** de  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="74635-121">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="74635-122">Usa Defender para Endpoint para obtener más detalles para cada evento, especialmente para investigar reglas de reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="74635-122">Use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="74635-123">El uso de la consola defender para endpoint te permite investigar problemas como parte de la escala de tiempo de alerta y [los escenarios de investigación.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="74635-123">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="74635-124">Puede habilitar el modo de auditoría mediante la directiva de grupo, PowerShell y los proveedores de servicios de configuración (CSP).</span><span class="sxs-lookup"><span data-stu-id="74635-124">You can enable audit mode using Group Policy, PowerShell, and configuration service providers (CSPs).</span></span>

> [!TIP]
> <span data-ttu-id="74635-125">También puedes visitar el sitio web Windows Defender Testground en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las características funcionan y ver cómo funcionan.</span><span class="sxs-lookup"><span data-stu-id="74635-125">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="74635-126">Opciones de auditoría</span><span class="sxs-lookup"><span data-stu-id="74635-126">Audit options</span></span> | <span data-ttu-id="74635-127">Cómo habilitar el modo de auditoría</span><span class="sxs-lookup"><span data-stu-id="74635-127">How to enable audit mode</span></span> | <span data-ttu-id="74635-128">Cómo ver eventos</span><span class="sxs-lookup"><span data-stu-id="74635-128">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="74635-129">La auditoría se aplica a todos los eventos</span><span class="sxs-lookup"><span data-stu-id="74635-129">Audit applies to all events</span></span> | [<span data-ttu-id="74635-130">Habilitar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="74635-130">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="74635-131">Eventos de acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="74635-131">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="74635-132">La auditoría se aplica a reglas individuales</span><span class="sxs-lookup"><span data-stu-id="74635-132">Audit applies to individual rules</span></span> | [<span data-ttu-id="74635-133">Habilitar las reglas de la reducción de superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="74635-133">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="74635-134">Eventos de regla de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="74635-134">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="74635-135">La auditoría se aplica a todos los eventos</span><span class="sxs-lookup"><span data-stu-id="74635-135">Audit applies to all events</span></span> | [<span data-ttu-id="74635-136">Habilitar la protección de red</span><span class="sxs-lookup"><span data-stu-id="74635-136">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="74635-137">Eventos de protección de red</span><span class="sxs-lookup"><span data-stu-id="74635-137">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="74635-138">La auditoría se aplica a mitigaciones individuales</span><span class="sxs-lookup"><span data-stu-id="74635-138">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="74635-139">Habilitar la protección contra vulnerabilidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="74635-139">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="74635-140">Eventos de protección contra vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="74635-140">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
