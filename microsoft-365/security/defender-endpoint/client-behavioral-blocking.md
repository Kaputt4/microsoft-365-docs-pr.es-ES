---
title: Bloqueo de comportamiento del cliente
description: El bloqueo de comportamiento del cliente forma parte de las capacidades de contención y bloqueo de comportamiento en Microsoft Defender para endpoint
keywords: bloqueo de comportamiento, protección rápida, comportamiento del cliente, Microsoft Defender para endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: c58c81cd4623ec03850c167cad285e052413174c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933426"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="30c53-104">Bloqueo de comportamiento del cliente</span><span class="sxs-lookup"><span data-stu-id="30c53-104">Client behavioral blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="30c53-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="30c53-105">**Applies to:**</span></span>
- [<span data-ttu-id="30c53-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="30c53-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="30c53-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30c53-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="30c53-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="30c53-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="30c53-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="30c53-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="30c53-110">Información general</span><span class="sxs-lookup"><span data-stu-id="30c53-110">Overview</span></span>

<span data-ttu-id="30c53-111">El bloqueo de comportamiento del cliente es un componente de las capacidades de [contención](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) y bloqueo de comportamiento en Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="30c53-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span></span> <span data-ttu-id="30c53-112">A medida que se detectan comportamientos sospechosos en dispositivos (también denominados clientes o extremos), los artefactos (como archivos o aplicaciones) se bloquean, comprueban y corrigen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="30c53-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Protección de cliente y nube":::

<span data-ttu-id="30c53-114">La protección antivirus funciona mejor cuando se combina con la protección en la nube.</span><span class="sxs-lookup"><span data-stu-id="30c53-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="30c53-115">Cómo funciona el bloqueo de comportamiento del cliente</span><span class="sxs-lookup"><span data-stu-id="30c53-115">How client behavioral blocking works</span></span>

<span data-ttu-id="30c53-116">[Antivirus de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) puede detectar comportamientos sospechosos, código malintencionado, ataques sin archivos y en memoria, y mucho más en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="30c53-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="30c53-117">Cuando se detectan comportamientos sospechosos, Antivirus de Microsoft Defender supervisa y envía esos comportamientos sospechosos y sus árboles de proceso al servicio de protección en la nube.</span><span class="sxs-lookup"><span data-stu-id="30c53-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="30c53-118">El aprendizaje automático diferencia entre aplicaciones malintencionadas y comportamientos buenos en milisegundos y clasifica cada artefacto.</span><span class="sxs-lookup"><span data-stu-id="30c53-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="30c53-119">En tiempo casi real, tan pronto como se encuentra que un artefacto es malintencionado, se bloquea en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="30c53-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="30c53-120">Cada vez que se detecta un comportamiento sospechoso, se [genera](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) una alerta y está visible en el Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="30c53-120">Whenever a suspicious behavior is detected, an [alert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="30c53-121">El bloqueo de comportamiento del cliente es eficaz porque no solo ayuda a evitar que se inicie un ataque, sino que puede ayudar a detener un ataque que se ha comenzado a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="30c53-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="30c53-122">Además, con el [bloqueo de bucle de comentarios](feedback-loop-blocking.md) (otra capacidad de bloqueo y contención del comportamiento), se evitan ataques en otros dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="30c53-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="30c53-123">Detecciones basadas en comportamiento</span><span class="sxs-lookup"><span data-stu-id="30c53-123">Behavior-based detections</span></span>

<span data-ttu-id="30c53-124">Las detecciones basadas en comportamiento se denominan de acuerdo con el&[MATRIZ DE CK para empresas de MITRE ATT.](https://attack.mitre.org/matrices/enterprise)</span><span class="sxs-lookup"><span data-stu-id="30c53-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="30c53-125">La convención de nomenclatura ayuda a identificar la fase de ataque donde se observó el comportamiento malintencionado:</span><span class="sxs-lookup"><span data-stu-id="30c53-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="30c53-126">Táctica</span><span class="sxs-lookup"><span data-stu-id="30c53-126">Tactic</span></span> |   <span data-ttu-id="30c53-127">Nombre de la amenaza de detección</span><span class="sxs-lookup"><span data-stu-id="30c53-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="30c53-128">Acceso inicial</span><span class="sxs-lookup"><span data-stu-id="30c53-128">Initial Access</span></span> | <span data-ttu-id="30c53-129">Behavior:Win32/InitialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-129">Behavior:Win32/InitialAccess.\*!ml</span></span> |
|<span data-ttu-id="30c53-130">Ejecución</span><span class="sxs-lookup"><span data-stu-id="30c53-130">Execution</span></span>  | <span data-ttu-id="30c53-131">Behavior:Win32/Execution.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-131">Behavior:Win32/Execution.\*!ml</span></span> |
|<span data-ttu-id="30c53-132">Persistencia</span><span class="sxs-lookup"><span data-stu-id="30c53-132">Persistence</span></span>    | <span data-ttu-id="30c53-133">Behavior:Win32/Persistence.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-133">Behavior:Win32/Persistence.\*!ml</span></span> |
|<span data-ttu-id="30c53-134">Escalamiento de privilegios</span><span class="sxs-lookup"><span data-stu-id="30c53-134">Privilege Escalation</span></span>   | <span data-ttu-id="30c53-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span></span> |
|<span data-ttu-id="30c53-136">Evasión de defensa</span><span class="sxs-lookup"><span data-stu-id="30c53-136">Defense Evasion</span></span>    | <span data-ttu-id="30c53-137">Behavior:Win32/DefenseEvasion.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-137">Behavior:Win32/DefenseEvasion.\*!ml</span></span> |
|<span data-ttu-id="30c53-138">Acceso a credenciales</span><span class="sxs-lookup"><span data-stu-id="30c53-138">Credential Access</span></span>  | <span data-ttu-id="30c53-139">Behavior:Win32/CredentialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-139">Behavior:Win32/CredentialAccess.\*!ml</span></span> |
|<span data-ttu-id="30c53-140">Descubrimiento</span><span class="sxs-lookup"><span data-stu-id="30c53-140">Discovery</span></span>  | <span data-ttu-id="30c53-141">Behavior:Win32/Discovery.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-141">Behavior:Win32/Discovery.\*!ml</span></span> |
|<span data-ttu-id="30c53-142">Movimiento lateral</span><span class="sxs-lookup"><span data-stu-id="30c53-142">Lateral Movement</span></span> | <span data-ttu-id="30c53-143">Behavior:Win32/LateralMovement.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-143">Behavior:Win32/LateralMovement.\*!ml</span></span> |
|<span data-ttu-id="30c53-144">Colección</span><span class="sxs-lookup"><span data-stu-id="30c53-144">Collection</span></span> |   <span data-ttu-id="30c53-145">Behavior:Win32/Collection.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-145">Behavior:Win32/Collection.\*!ml</span></span> |
|<span data-ttu-id="30c53-146">Comando y control</span><span class="sxs-lookup"><span data-stu-id="30c53-146">Command and Control</span></span> | <span data-ttu-id="30c53-147">Behavior:Win32/CommandAndControl.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-147">Behavior:Win32/CommandAndControl.\*!ml</span></span> |
|<span data-ttu-id="30c53-148">Exfiltración</span><span class="sxs-lookup"><span data-stu-id="30c53-148">Exfiltration</span></span>   | <span data-ttu-id="30c53-149">Behavior:Win32/Exfiltration.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-149">Behavior:Win32/Exfiltration.\*!ml</span></span> |
|<span data-ttu-id="30c53-150">Impacto</span><span class="sxs-lookup"><span data-stu-id="30c53-150">Impact</span></span> | <span data-ttu-id="30c53-151">Behavior:Win32/Impact.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-151">Behavior:Win32/Impact.\*!ml</span></span> |
|<span data-ttu-id="30c53-152">Sin categorizar</span><span class="sxs-lookup"><span data-stu-id="30c53-152">Uncategorized</span></span>  | <span data-ttu-id="30c53-153">Behavior:Win32/Generic.\*!ml</span><span class="sxs-lookup"><span data-stu-id="30c53-153">Behavior:Win32/Generic.\*!ml</span></span> |

> [!TIP]
> <span data-ttu-id="30c53-154">Para obtener más información acerca de las amenazas específicas, **[vea actividad de amenazas globales recientes](https://www.microsoft.com/wdsi/threats)**.</span><span class="sxs-lookup"><span data-stu-id="30c53-154">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="30c53-155">Configuración del bloqueo de comportamiento del cliente</span><span class="sxs-lookup"><span data-stu-id="30c53-155">Configuring client behavioral blocking</span></span>

<span data-ttu-id="30c53-156">Si su organización usa Defender para endpoint, el bloqueo de comportamiento del cliente está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="30c53-156">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="30c53-157">Sin embargo, para beneficiarse de todas las capacidades de Defender for Endpoint, incluido el bloqueo y la contención del [comportamiento,](behavioral-blocking-containment.md)asegúrese de que las siguientes características y capacidades de Defender para endpoint están habilitadas y configuradas:</span><span class="sxs-lookup"><span data-stu-id="30c53-157">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="30c53-158">Defender for Endpoint baselines</span><span class="sxs-lookup"><span data-stu-id="30c53-158">Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="30c53-159">Dispositivos incorporados a Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="30c53-159">Devices onboarded to Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="30c53-160">EDR en modo bloqueo</span><span class="sxs-lookup"><span data-stu-id="30c53-160">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="30c53-161">Reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="30c53-161">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="30c53-162">[Protección de última generación](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span><span class="sxs-lookup"><span data-stu-id="30c53-162">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="30c53-163">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="30c53-163">Related articles</span></span>

- [<span data-ttu-id="30c53-164">Bloqueo y contención de comportamientos</span><span class="sxs-lookup"><span data-stu-id="30c53-164">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="30c53-165">Bloqueo de bucles de distribución de comentarios</span><span class="sxs-lookup"><span data-stu-id="30c53-165">Feedback-loop blocking</span></span>](feedback-loop-blocking.md)

- [<span data-ttu-id="30c53-166">(Blog) Bloqueo y contención de comportamiento: transformar la óptica en protección</span><span class="sxs-lookup"><span data-stu-id="30c53-166">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="30c53-167">Helpful Defender for Endpoint resources</span><span class="sxs-lookup"><span data-stu-id="30c53-167">Helpful Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
