---
title: Solucionar problemas con reglas de reducción de superficie de ataque
description: Recursos y código de ejemplo para solucionar problemas con reglas de reducción de superficie de ataque en Microsoft Defender para endpoint.
keywords: troubleshoot, error, fix, windows defender, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: c5c76553ff3f0b32def5fbafbf2c8f010e49eeb2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845428"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a><span data-ttu-id="083de-104">Solucionar problemas de reglas de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="083de-104">Troubleshoot attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="083de-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="083de-105">**Applies to:**</span></span>
- [<span data-ttu-id="083de-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="083de-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="083de-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="083de-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="083de-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="083de-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="083de-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="083de-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="083de-110">Cuando usas [reglas de reducción de](attack-surface-reduction.md) superficie de ataque, puedes encontrar problemas, como:</span><span class="sxs-lookup"><span data-stu-id="083de-110">When you use [attack surface reduction rules](attack-surface-reduction.md) you may run into issues, such as:</span></span>

- <span data-ttu-id="083de-111">Una regla bloquea un archivo, proceso o realiza alguna otra acción que no debería (falso positivo)</span><span class="sxs-lookup"><span data-stu-id="083de-111">A rule blocks a file, process, or performs some other action that it shouldn't (false positive)</span></span>

- <span data-ttu-id="083de-112">Una regla no funciona como se describe o no bloquea un archivo o proceso que debe (falso negativo)</span><span class="sxs-lookup"><span data-stu-id="083de-112">A rule doesn't work as described, or doesn't block a file or process that it should (false negative)</span></span>

<span data-ttu-id="083de-113">Hay cuatro pasos para solucionar estos problemas:</span><span class="sxs-lookup"><span data-stu-id="083de-113">There are four steps to troubleshooting these problems:</span></span>

1. [<span data-ttu-id="083de-114">Confirmar requisitos previos</span><span class="sxs-lookup"><span data-stu-id="083de-114">Confirm prerequisites</span></span>](#confirm-prerequisites)

2. [<span data-ttu-id="083de-115">Usar el modo de auditoría para probar la regla</span><span class="sxs-lookup"><span data-stu-id="083de-115">Use audit mode to test the rule</span></span>](#use-audit-mode-to-test-the-rule)

3. <span data-ttu-id="083de-116">[Agregar exclusiones para la regla especificada](#add-exclusions-for-a-false-positive) (para falsos positivos)</span><span class="sxs-lookup"><span data-stu-id="083de-116">[Add exclusions for the specified rule](#add-exclusions-for-a-false-positive) (for false positives)</span></span>

4. [<span data-ttu-id="083de-117">Enviar registros de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="083de-117">Submit support logs</span></span>](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a><span data-ttu-id="083de-118">Confirmar requisitos previos</span><span class="sxs-lookup"><span data-stu-id="083de-118">Confirm prerequisites</span></span>

<span data-ttu-id="083de-119">Las reglas de reducción de superficie de ataque solo funcionarán en dispositivos con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="083de-119">Attack surface reduction rules will only work on devices with the following conditions:</span></span>

- <span data-ttu-id="083de-120">Los puntos de conexión Windows 10 Enterprise, versión 1709 (también conocida como fall Creators Update).</span><span class="sxs-lookup"><span data-stu-id="083de-120">Endpoints are running Windows 10 Enterprise, version 1709 (also known as the Fall Creators Update).</span></span>

- <span data-ttu-id="083de-121">Los puntos de conexión usan Antivirus de Microsoft Defender como la única aplicación de protección antivirus.</span><span class="sxs-lookup"><span data-stu-id="083de-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="083de-122">[El uso de cualquier otra aplicación antivirus hará que Microsoft Defender AV se deshabilite a sí mismo.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="083de-122">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

- <span data-ttu-id="083de-123">[La protección en tiempo real](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="083de-123">[Real-time protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>

- <span data-ttu-id="083de-124">El modo auditoría no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="083de-124">Audit mode isn't enabled.</span></span> <span data-ttu-id="083de-125">Use la directiva de grupo para establecer la regla en **Deshabilitado** (valor: **0**) como se describe en Habilitar reglas de reducción [de superficie de ataque](enable-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="083de-125">Use Group Policy to set the rule to **Disabled** (value: **0**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

<span data-ttu-id="083de-126">Si se han cumplido todos estos requisitos previos, continúe con el siguiente paso para probar la regla en modo auditoría.</span><span class="sxs-lookup"><span data-stu-id="083de-126">If these prerequisites have all been met, proceed to the next step to test the rule in audit mode.</span></span>

## <a name="use-audit-mode-to-test-the-rule"></a><span data-ttu-id="083de-127">Usar el modo de auditoría para probar la regla</span><span class="sxs-lookup"><span data-stu-id="083de-127">Use audit mode to test the rule</span></span>

<span data-ttu-id="083de-128">Puedes visitar el sitio web de prueba de Windows Defender en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las reglas de reducción de superficie de ataques suelen funcionar para escenarios y procesos preconfigurados en un dispositivo, o puedes usar el modo de auditoría, que permite reglas solo para informes.</span><span class="sxs-lookup"><span data-stu-id="083de-128">You can visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm attack surface reduction rules are generally working for pre-configured scenarios and processes on a device, or you can use audit mode, which enables rules for reporting only.</span></span>

<span data-ttu-id="083de-129">Sigue estas instrucciones en [Use the demo tool to see how attack surface reduction rules work](evaluate-attack-surface-reduction.md) to test the specific rule you're encountering problems with.</span><span class="sxs-lookup"><span data-stu-id="083de-129">Follow these instructions in [Use the demo tool to see how attack surface reduction rules work](evaluate-attack-surface-reduction.md) to test the specific rule you're encountering problems with.</span></span>

1. <span data-ttu-id="083de-130">Habilite el modo de auditoría para la regla específica que desea probar.</span><span class="sxs-lookup"><span data-stu-id="083de-130">Enable audit mode for the specific rule you want to test.</span></span> <span data-ttu-id="083de-131">Use la directiva de grupo para establecer la regla en **modo auditoría** (valor: **2**) como se describe en Habilitar reglas de reducción de [superficie de ataque](enable-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="083de-131">Use Group Policy to set the rule to **Audit mode** (value: **2**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span> <span data-ttu-id="083de-132">El modo auditoría permite que la regla informe del archivo o proceso, pero aún así le permitirá ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="083de-132">Audit mode allows the rule to report the file or process, but will still allow it to run.</span></span>

2. <span data-ttu-id="083de-133">Realice la actividad que está causando un problema (por ejemplo, abra o ejecute el archivo o proceso que se debe bloquear pero que se está permitido).</span><span class="sxs-lookup"><span data-stu-id="083de-133">Perform the activity that is causing an issue (for example, open or execute the file or process that should be blocked but is being allowed).</span></span>

3. <span data-ttu-id="083de-134">[Revise los registros de eventos](attack-surface-reduction.md) de la regla de reducción de superficie de ataque para ver si la regla habría bloqueado el archivo o el proceso si la regla se hubiera establecido en **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="083de-134">[Review the attack surface reduction rule event logs](attack-surface-reduction.md) to see if the rule would have blocked the file or process if the rule had been set to **Enabled**.</span></span>

<span data-ttu-id="083de-135">Si una regla no bloquea un archivo o proceso que espera que se bloquee, compruebe primero si el modo de auditoría está habilitado.</span><span class="sxs-lookup"><span data-stu-id="083de-135">If a rule isn't blocking a file or process that you're expecting it should block, first check if audit mode is enabled.</span></span>

<span data-ttu-id="083de-136">Es posible que el modo auditoría se haya habilitado para probar otra característica, o mediante un script de PowerShell automatizado, y puede que no se haya deshabilitado después de que se hayan completado las pruebas.</span><span class="sxs-lookup"><span data-stu-id="083de-136">Audit mode may have been enabled for testing another feature, or by an automated PowerShell script, and may not have been disabled after the tests were completed.</span></span>

<span data-ttu-id="083de-137">Si ha probado la regla con la herramienta de demostración y con el modo de auditoría, y las reglas de reducción de superficie de ataque funcionan en escenarios preconfigurados, pero la regla no funciona como se esperaba, continúe con cualquiera de las siguientes secciones en función de su situación:</span><span class="sxs-lookup"><span data-stu-id="083de-137">If you've tested the rule with the demo tool and with audit mode, and attack surface reduction rules are working on pre-configured scenarios, but the rule isn't working as expected, proceed to either of the following sections based on your situation:</span></span>

1. <span data-ttu-id="083de-138">Si la regla de reducción de superficie de ataque bloquea algo que no debe bloquear (también conocido como falso positivo), primero puedes agregar una exclusión de regla de reducción de superficie [de ataque.](#add-exclusions-for-a-false-positive)</span><span class="sxs-lookup"><span data-stu-id="083de-138">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can [first add an attack surface reduction rule exclusion](#add-exclusions-for-a-false-positive).</span></span>

2. <span data-ttu-id="083de-139">Si la regla de reducción de superficie de ataque no bloquea algo que debería bloquear (también conocido como falso negativo), puede continuar inmediatamente con el último [paso,](#collect-diagnostic-data-for-file-submissions)recopilando datos de diagnóstico y enviando el problema a nosotros .</span><span class="sxs-lookup"><span data-stu-id="083de-139">If the attack surface reduction rule isn't blocking something that it should block (also known as a false negative), you can proceed immediately to the last step, [collecting diagnostic data and submitting the issue to us](#collect-diagnostic-data-for-file-submissions).</span></span>

## <a name="add-exclusions-for-a-false-positive"></a><span data-ttu-id="083de-140">Agregar exclusiones para un falso positivo</span><span class="sxs-lookup"><span data-stu-id="083de-140">Add exclusions for a false positive</span></span>

<span data-ttu-id="083de-141">Si la regla de reducción de superficie de ataque bloquea algo que no debe bloquear (también conocido como falso positivo), puedes agregar exclusiones para evitar que las reglas de reducción de superficie de ataque evalúen los archivos o carpetas excluidos.</span><span class="sxs-lookup"><span data-stu-id="083de-141">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can add exclusions to prevent attack surface reduction rules from evaluating the excluded files or folders.</span></span>

<span data-ttu-id="083de-142">Para agregar una exclusión, consulta [Personalizar reducción de superficie de ataque](customize-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="083de-142">To add an exclusion, see [Customize Attack surface reduction](customize-attack-surface-reduction.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="083de-143">Puede especificar archivos y carpetas individuales que se excluirán, pero no puede especificar reglas individuales.</span><span class="sxs-lookup"><span data-stu-id="083de-143">You can specify individual files and folders to be excluded, but you cannot specify individual rules.</span></span>
><span data-ttu-id="083de-144">Esto significa que los archivos o carpetas que se excluyen se excluirán de todas las reglas ASR.</span><span class="sxs-lookup"><span data-stu-id="083de-144">This means any files or folders that are excluded will be excluded from all ASR rules.</span></span>

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="083de-145">Informar de un falso positivo o falso negativo</span><span class="sxs-lookup"><span data-stu-id="083de-145">Report a false positive or false negative</span></span>

<span data-ttu-id="083de-146">Use el [Windows Defender de](https://www.microsoft.com/wdsi/filesubmission) envío basado en web de Inteligencia de seguridad para informar de un falso negativo o falso positivo para la protección de red.</span><span class="sxs-lookup"><span data-stu-id="083de-146">Use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="083de-147">Con una Windows de E5, también puede proporcionar [un vínculo a cualquier alerta asociada](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="083de-147">With a Windows E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="083de-148">Recopilar datos de diagnóstico para envíos de archivos</span><span class="sxs-lookup"><span data-stu-id="083de-148">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="083de-149">Cuando informes de un problema con las reglas de reducción de superficie de ataque, se te pedirá que recopile y envíe datos de diagnóstico que puedan usar los equipos de soporte técnico e ingeniería de Microsoft para ayudar a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="083de-149">When you report a problem with attack surface reduction rules, you're asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="083de-150">Abra un símbolo del sistema con privilegios elevados y cambie al Windows Defender directorio:</span><span class="sxs-lookup"><span data-stu-id="083de-150">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd "c:\program files\windows defender"
   ```

2. <span data-ttu-id="083de-151">Ejecute este comando para generar los registros de diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="083de-151">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="083de-152">De forma predeterminada, se guardan en `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="083de-152">By default, they're saved to `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> <span data-ttu-id="083de-153">Adjunte el archivo al formulario de envío.</span><span class="sxs-lookup"><span data-stu-id="083de-153">Attach the file to the submission form.</span></span>

## <a name="related-articles"></a><span data-ttu-id="083de-154">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="083de-154">Related articles</span></span>

- [<span data-ttu-id="083de-155">Reglas de la reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="083de-155">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="083de-156">Habilitar las reglas de la reducción de superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="083de-156">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)

- [<span data-ttu-id="083de-157">Evaluar las reglas de la reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="083de-157">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
