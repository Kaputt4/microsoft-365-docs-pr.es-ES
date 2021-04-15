---
title: Solucionar problemas con la protección de red
description: Recursos y código de ejemplo para solucionar problemas con la protección de red en Microsoft Defender para endpoint.
keywords: troubleshoot, error, fix, windows defender, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, microsoft defender for endpoint, microsoft defender advanced threat protection
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 9efc42441c2cb30f35abf658071088f7f7bbaf00
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760103"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="7e029-104">Solucionar problemas de protección de red</span><span class="sxs-lookup"><span data-stu-id="7e029-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7e029-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7e029-105">**Applies to:**</span></span>
- [<span data-ttu-id="7e029-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7e029-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7e029-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e029-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="7e029-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7e029-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7e029-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="7e029-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="7e029-110">Cuando usa la [protección de red,](network-protection.md) puede encontrar problemas, como:</span><span class="sxs-lookup"><span data-stu-id="7e029-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="7e029-111">La protección de red bloquea un sitio web seguro (falso positivo)</span><span class="sxs-lookup"><span data-stu-id="7e029-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="7e029-112">La protección de red no puede bloquear un sitio web malintencionado sospechoso o conocido (falso negativo)</span><span class="sxs-lookup"><span data-stu-id="7e029-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="7e029-113">Hay cuatro pasos para solucionar estos problemas:</span><span class="sxs-lookup"><span data-stu-id="7e029-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="7e029-114">Confirmar requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7e029-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="7e029-115">Usar el modo de auditoría para probar la regla</span><span class="sxs-lookup"><span data-stu-id="7e029-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="7e029-116">Agregar exclusiones para la regla especificada (para falsos positivos)</span><span class="sxs-lookup"><span data-stu-id="7e029-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="7e029-117">Enviar registros de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="7e029-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="7e029-118">Confirmar requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7e029-118">Confirm prerequisites</span></span>

<span data-ttu-id="7e029-119">La protección de red solo funcionará en dispositivos con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="7e029-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="7e029-120">Los puntos de conexión ejecutan Windows 10 Pro o Enterprise edition, versión 1709 o posterior.</span><span class="sxs-lookup"><span data-stu-id="7e029-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="7e029-121">Los puntos de conexión usan Antivirus de Microsoft Defender como única aplicación de protección antivirus.</span><span class="sxs-lookup"><span data-stu-id="7e029-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="7e029-122">[Vea lo que sucede cuando usa una solución antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)que no sea de Microsoft .</span><span class="sxs-lookup"><span data-stu-id="7e029-122">[See what happens when you are using a non-Microsoft antivirus solution](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="7e029-123">[La protección en tiempo real](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7e029-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="7e029-124">[La protección entregada en la nube](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7e029-124">[Cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="7e029-125">El modo auditoría no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="7e029-125">Audit mode is not enabled.</span></span> <span data-ttu-id="7e029-126">Use [la directiva de](enable-network-protection.md#group-policy) grupo para establecer la regla en **Deshabilitado** (valor: **0**).</span><span class="sxs-lookup"><span data-stu-id="7e029-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="7e029-127">Usar modo de auditoría</span><span class="sxs-lookup"><span data-stu-id="7e029-127">Use audit mode</span></span>

<span data-ttu-id="7e029-128">Puede habilitar la protección de red en modo auditoría y, a continuación, visitar un sitio web que hemos creado para realizar una demostración de la característica.</span><span class="sxs-lookup"><span data-stu-id="7e029-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="7e029-129">La protección de red permitirá todas las conexiones de sitios web, pero se registrará un evento para indicar cualquier conexión que se hubiera bloqueado si la protección de red estaba habilitada.</span><span class="sxs-lookup"><span data-stu-id="7e029-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="7e029-130">Establezca la protección de red en **modo auditoría**.</span><span class="sxs-lookup"><span data-stu-id="7e029-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="7e029-131">Realice la actividad de conexión que está causando un problema (por ejemplo, intentar visitar el sitio o conectarse a la dirección IP que hace o no desea bloquear).</span><span class="sxs-lookup"><span data-stu-id="7e029-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="7e029-132">[Revise los registros de](network-protection.md#review-network-protection-events-in-windows-event-viewer) eventos de protección de red para ver si la característica hubiera bloqueado la conexión si se hubiera establecido en **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="7e029-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="7e029-133">Si la protección de red no bloquea una conexión que espera que se bloquee, habilite la característica.</span><span class="sxs-lookup"><span data-stu-id="7e029-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="7e029-134">Informar de un falso positivo o falso negativo</span><span class="sxs-lookup"><span data-stu-id="7e029-134">Report a false positive or false negative</span></span>

<span data-ttu-id="7e029-135">Si ha probado la característica con el sitio de demostración y con el modo de auditoría, y la protección de red funciona en escenarios preconfigurados, pero no funciona como se esperaba para una conexión específica, use el formulario de envío basado en web de inteligencia de seguridad de [Windows Defender](https://www.microsoft.com/wdsi/filesubmission) para informar de un falso negativo o falso positivo para la protección de red.</span><span class="sxs-lookup"><span data-stu-id="7e029-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="7e029-136">Con una suscripción A5, también puede proporcionar [un vínculo a cualquier alerta asociada.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="7e029-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="7e029-137">Consulta [Dirección de falsos positivos/negativos en Microsoft Defender para Endpoint](defender-endpoint-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="7e029-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="7e029-138">Excluir sitio web del ámbito de protección de red</span><span class="sxs-lookup"><span data-stu-id="7e029-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="7e029-139">Para permitir el sitio web que se está bloqueando (falso positivo), agregue su dirección URL a la [lista de sitios de confianza](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span><span class="sxs-lookup"><span data-stu-id="7e029-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="7e029-140">Los recursos web de esta lista omiten la comprobación de protección de red.</span><span class="sxs-lookup"><span data-stu-id="7e029-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="7e029-141">Recopilar datos de diagnóstico para envíos de archivos</span><span class="sxs-lookup"><span data-stu-id="7e029-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="7e029-142">Cuando informe de un problema con la protección de red, se le pedirá que recopile y envíe datos de diagnóstico que puedan usar los equipos de soporte técnico e ingeniería de Microsoft para ayudar a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="7e029-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="7e029-143">Abra un símbolo del sistema con privilegios elevados y cambie al Windows Defender:</span><span class="sxs-lookup"><span data-stu-id="7e029-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="7e029-144">Ejecute este comando para generar los registros de diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="7e029-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="7e029-145">Adjunte el archivo al formulario de envío.</span><span class="sxs-lookup"><span data-stu-id="7e029-145">Attach the file to the submission form.</span></span> <span data-ttu-id="7e029-146">De forma predeterminada, los registros de diagnóstico se guardan en `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="7e029-146">By default, diagnostic logs are saved at `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a><span data-ttu-id="7e029-147">Resolver problemas de conectividad con la protección de red (para clientes de E5)</span><span class="sxs-lookup"><span data-stu-id="7e029-147">Resolve connectivity issues with network protection (for E5 customers)</span></span>

<span data-ttu-id="7e029-148">Debido al entorno donde se ejecuta la protección de red, Microsoft no puede ver la configuración de proxy del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7e029-148">Due to the environment where network protection runs, Microsoft is unable to see your operating system proxy settings.</span></span> <span data-ttu-id="7e029-149">En algunos casos, los clientes de protección de red no pueden llegar al servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="7e029-149">In some cases, network protection clients are unable to reach the cloud service.</span></span> <span data-ttu-id="7e029-150">Para resolver problemas de conectividad con la protección de red, configure una de las siguientes claves del Registro para que la protección de red tenga en cuenta la configuración de proxy:</span><span class="sxs-lookup"><span data-stu-id="7e029-150">To resolve connectivity issues with network protection, configure one of the following registry keys so that network protection becomes aware of the proxy configuration:</span></span>

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

<span data-ttu-id="7e029-151">---OR---</span><span class="sxs-lookup"><span data-stu-id="7e029-151">---OR---</span></span>


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

<span data-ttu-id="7e029-152">Puede configurar la clave del Registro mediante PowerShell, Microsoft Endpoint Manager o la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="7e029-152">You can configure the registry key by using PowerShell, Microsoft Endpoint Manager, or Group Policy.</span></span> <span data-ttu-id="7e029-153">Estos son algunos recursos para ayudar:</span><span class="sxs-lookup"><span data-stu-id="7e029-153">Here are some resources to help:</span></span>
- [<span data-ttu-id="7e029-154">Trabajar con claves del Registro</span><span class="sxs-lookup"><span data-stu-id="7e029-154">Working with Registry Keys</span></span>](/powershell/scripting/samples/working-with-registry-keys)
- [<span data-ttu-id="7e029-155">Configurar opciones de cliente personalizadas para Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="7e029-155">Configure custom client settings for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [<span data-ttu-id="7e029-156">Usar la configuración de directiva de grupo para administrar Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="7e029-156">Use Group Policy settings to manage Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a><span data-ttu-id="7e029-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e029-157">See also</span></span>

- [<span data-ttu-id="7e029-158">Protección de red</span><span class="sxs-lookup"><span data-stu-id="7e029-158">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="7e029-159">Evaluar protección de red</span><span class="sxs-lookup"><span data-stu-id="7e029-159">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="7e029-160">Habilitar la protección de red</span><span class="sxs-lookup"><span data-stu-id="7e029-160">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="7e029-161">Dirección de falsos positivos/negativos en Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7e029-161">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
