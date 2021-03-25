---
title: Evaluar reglas de reducción de superficie de ataque
description: Vea cómo la reducción de superficie de ataque bloquearía e impediría ataques con la herramienta de demostración personalizada.
keywords: Reducción de superficie de ataque, caderas, sistema de prevención de intrusiones de host, reglas de protección, antiexploit, vulnerabilidad, prevención de infecciones, evaluación, prueba, demostración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 13b1ac5f71f2bc24ad6f52af6722e12fab935270
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075832"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="56998-104">Evaluar reglas de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="56998-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="56998-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="56998-105">**Applies to:**</span></span>
- [<span data-ttu-id="56998-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="56998-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="56998-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56998-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="56998-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="56998-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="56998-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="56998-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="56998-110">Las reglas de reducción de superficie de ataque ayudan a evitar las acciones que suele usar el malware para poner en peligro dispositivos o redes.</span><span class="sxs-lookup"><span data-stu-id="56998-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="56998-111">Establecer reglas de reducción de superficie de ataque para dispositivos que ejecuten cualquiera de las siguientes ediciones y versiones de Windows:</span><span class="sxs-lookup"><span data-stu-id="56998-111">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="56998-112">Windows 10 Pro, [versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o posterior</span><span class="sxs-lookup"><span data-stu-id="56998-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="56998-113">Windows 10 Enterprise, [versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o posterior</span><span class="sxs-lookup"><span data-stu-id="56998-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="56998-114">Windows Server, [versión 1803 (canal semianual)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) o posterior</span><span class="sxs-lookup"><span data-stu-id="56998-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="56998-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="56998-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="56998-116">Aprende a evaluar las reglas de reducción de superficie de ataque habilitando el modo de auditoría para probar la característica directamente en tu organización.</span><span class="sxs-lookup"><span data-stu-id="56998-116">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="56998-117">También puede visitar el sitio web de escenario de demostración de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que la característica funciona y ver cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="56998-117">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="56998-118">Usar el modo de auditoría para medir el impacto</span><span class="sxs-lookup"><span data-stu-id="56998-118">Use audit mode to measure impact</span></span>

<span data-ttu-id="56998-119">Habilita las reglas de reducción de superficie de ataque en modo auditoría para ver un registro de aplicaciones que se habrían bloqueado si la característica estaba totalmente habilitada.</span><span class="sxs-lookup"><span data-stu-id="56998-119">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="56998-120">Pruebe cómo funcionará la característica en su organización para asegurarse de que no afecta a las aplicaciones de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="56998-120">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="56998-121">También puedes obtener una idea de la frecuencia con la que se dispararán las reglas durante el uso normal.</span><span class="sxs-lookup"><span data-stu-id="56998-121">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="56998-122">Para habilitar una regla de reducción de superficie de ataque en modo auditoría, use el siguiente cmdlet de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="56998-122">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="56998-123">Donde `<rule ID>` es un valor GUID de la regla de [reducción de superficie de ataque](attack-surface-reduction.md#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="56998-123">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="56998-124">Para habilitar todas las reglas de reducción de superficie de ataque agregadas en modo auditoría, use el siguiente cmdlet de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="56998-124">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="56998-125">Si quieres auditar completamente cómo funcionarán las reglas de reducción de superficie de ataque en tu organización, tendrás que usar una herramienta de administración para implementar esta configuración en dispositivos de tus redes.</span><span class="sxs-lookup"><span data-stu-id="56998-125">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="56998-126">También puedes usar la directiva de grupo, Intune o los proveedores de servicios de configuración (CSP) de administración de dispositivos móviles (MDM) para configurar e implementar la configuración.</span><span class="sxs-lookup"><span data-stu-id="56998-126">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="56998-127">Obtenga más información en el artículo [principal Reglas de reducción de superficie de](attack-surface-reduction.md) ataque.</span><span class="sxs-lookup"><span data-stu-id="56998-127">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="56998-128">Revisar los eventos de reducción de superficie de ataque en el Visor de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="56998-128">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="56998-129">Para revisar las aplicaciones que se habrían bloqueado, abra el Visor de eventos y filtre el identificador de evento 1121 en el registro de Microsoft-Windows-Windows Defender/Operativo.</span><span class="sxs-lookup"><span data-stu-id="56998-129">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="56998-130">En la tabla siguiente se enumeran todos los eventos de protección de red.</span><span class="sxs-lookup"><span data-stu-id="56998-130">The following table lists all network protection events.</span></span>

<span data-ttu-id="56998-131">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="56998-131">Event ID</span></span> | <span data-ttu-id="56998-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="56998-132">Description</span></span>
-|-
 <span data-ttu-id="56998-133">5007</span><span class="sxs-lookup"><span data-stu-id="56998-133">5007</span></span> | <span data-ttu-id="56998-134">Evento cuando se cambia la configuración</span><span class="sxs-lookup"><span data-stu-id="56998-134">Event when settings are changed</span></span>
 <span data-ttu-id="56998-135">1121</span><span class="sxs-lookup"><span data-stu-id="56998-135">1121</span></span> | <span data-ttu-id="56998-136">Evento cuando una regla de reducción de superficie de ataque se dispara en modo de bloqueo</span><span class="sxs-lookup"><span data-stu-id="56998-136">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="56998-137">1122</span><span class="sxs-lookup"><span data-stu-id="56998-137">1122</span></span> | <span data-ttu-id="56998-138">Evento cuando se desangre una regla de reducción de superficie de ataque en modo auditoría</span><span class="sxs-lookup"><span data-stu-id="56998-138">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="56998-139">Personalizar reglas de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="56998-139">Customize attack surface reduction rules</span></span>

<span data-ttu-id="56998-140">Durante la evaluación, es posible que desee configurar cada regla individualmente o excluir determinados archivos y procesos para que la característica evalúe.</span><span class="sxs-lookup"><span data-stu-id="56998-140">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="56998-141">Consulta [Personalizar reglas de reducción de](customize-attack-surface-reduction.md) superficie de ataque para obtener información sobre cómo configurar la característica con herramientas de administración, incluidas directivas de grupo y directivas de CSP de MDM.</span><span class="sxs-lookup"><span data-stu-id="56998-141">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="56998-142">Ver también</span><span class="sxs-lookup"><span data-stu-id="56998-142">See also</span></span>

* [<span data-ttu-id="56998-143">Reducir superficies de ataque con reglas de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="56998-143">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="56998-144">Use el modo de auditoría para evaluar Windows Defender</span><span class="sxs-lookup"><span data-stu-id="56998-144">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="56998-145">Preguntas frecuentes sobre reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="56998-145">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
