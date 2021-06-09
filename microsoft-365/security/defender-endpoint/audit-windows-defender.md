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
ms.technology: mde
ms.date: 06/02/2021
ms.topic: article
ms.openlocfilehash: 10351d97ba72945f929e042dc72a37724a1df291
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769610"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="6959c-104">Probar la reducción de superficie de ataque en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="6959c-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6959c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6959c-105">**Applies to:**</span></span>
- [<span data-ttu-id="6959c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6959c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6959c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6959c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="6959c-108">Si formas parte del equipo de seguridad de la organización, puedes configurar las capacidades de reducción de superficie de ataque para que se ejecuten en modo auditoría para ver cómo funcionarán en la organización.</span><span class="sxs-lookup"><span data-stu-id="6959c-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="6959c-109">En particular, puedes habilitar reglas de reducción de superficie de ataque, protección contra vulnerabilidades, protección de red y acceso controlado a carpetas en modo auditoría.</span><span class="sxs-lookup"><span data-stu-id="6959c-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="6959c-110">El modo auditoría te permite ver un registro de lo *que hubiera* ocurrido si hubieras habilitado la característica.</span><span class="sxs-lookup"><span data-stu-id="6959c-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="6959c-111">Es posible que desee habilitar el modo de auditoría al probar cómo funcionarán las características en su organización.</span><span class="sxs-lookup"><span data-stu-id="6959c-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="6959c-112">Esto te ayudará a asegurarte de que tus aplicaciones de línea de negocio no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="6959c-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="6959c-113">También puede obtener una idea de cuántos intentos de modificación de archivos sospechosos se producen durante un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="6959c-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="6959c-114">Las características no bloquearán ni impedirán que se modifiquen aplicaciones, scripts o archivos.</span><span class="sxs-lookup"><span data-stu-id="6959c-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="6959c-115">Sin embargo, el Windows de eventos registrará eventos como si las características estuvieran totalmente habilitadas.</span><span class="sxs-lookup"><span data-stu-id="6959c-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="6959c-116">Con el modo de auditoría, puedes revisar el registro de eventos para ver qué impacto habría tenido la característica si se hubiera habilitado.</span><span class="sxs-lookup"><span data-stu-id="6959c-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="6959c-117">Para buscar las entradas auditadas, vaya a **Aplicaciones y servicios** de  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="6959c-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="6959c-118">Puedes usar Defender para endpoint para obtener más detalles para cada evento, especialmente para investigar reglas de reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="6959c-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="6959c-119">El uso de la consola defender para endpoint te permite investigar problemas como parte de la escala de tiempo de alerta y [los escenarios de investigación.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="6959c-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="6959c-120">Puede usar la directiva de grupo, PowerShell y los proveedores de servicios de configuración (CSP) para habilitar el modo de auditoría.</span><span class="sxs-lookup"><span data-stu-id="6959c-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="6959c-121">También puedes visitar el sitio web Windows Defender Testground en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las características funcionan y ver cómo funcionan.</span><span class="sxs-lookup"><span data-stu-id="6959c-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="6959c-122">**Opciones de auditoría**</span><span class="sxs-lookup"><span data-stu-id="6959c-122">**Audit options**</span></span> | <span data-ttu-id="6959c-123">**Cómo habilitar el modo de auditoría**</span><span class="sxs-lookup"><span data-stu-id="6959c-123">**How to enable audit mode**</span></span> | <span data-ttu-id="6959c-124">**Cómo ver eventos**</span><span class="sxs-lookup"><span data-stu-id="6959c-124">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="6959c-125">La auditoría se aplica a todos los eventos</span><span class="sxs-lookup"><span data-stu-id="6959c-125">Audit applies to all events</span></span> | [<span data-ttu-id="6959c-126">Habilitar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="6959c-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="6959c-127">Eventos de acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="6959c-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="6959c-128">La auditoría se aplica a reglas individuales</span><span class="sxs-lookup"><span data-stu-id="6959c-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="6959c-129">Habilitar las reglas de la reducción de superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="6959c-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="6959c-130">Eventos de regla de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="6959c-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="6959c-131">La auditoría se aplica a todos los eventos</span><span class="sxs-lookup"><span data-stu-id="6959c-131">Audit applies to all events</span></span> | [<span data-ttu-id="6959c-132">Habilitar la protección de red</span><span class="sxs-lookup"><span data-stu-id="6959c-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="6959c-133">Eventos de protección de red</span><span class="sxs-lookup"><span data-stu-id="6959c-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="6959c-134">La auditoría se aplica a mitigaciones individuales</span><span class="sxs-lookup"><span data-stu-id="6959c-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="6959c-135">Habilitar la protección contra vulnerabilidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="6959c-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="6959c-136">Eventos de protección contra vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="6959c-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


