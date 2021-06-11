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
ms.openlocfilehash: 4e416aa9484f251280649035247a59dcc82ce750
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795963"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="77669-104">Bloqueo de comportamiento del cliente</span><span class="sxs-lookup"><span data-stu-id="77669-104">Client behavioral blocking</span></span>

<span data-ttu-id="77669-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="77669-105">**Applies to:**</span></span>
- [<span data-ttu-id="77669-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="77669-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="77669-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77669-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="77669-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="77669-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="77669-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="77669-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="77669-110">Información general</span><span class="sxs-lookup"><span data-stu-id="77669-110">Overview</span></span>

<span data-ttu-id="77669-111">El bloqueo de comportamiento del cliente es un componente de las capacidades de [contención](behavioral-blocking-containment.md) y bloqueo de comportamiento en Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="77669-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](behavioral-blocking-containment.md) in Defender for Endpoint.</span></span> <span data-ttu-id="77669-112">A medida que se detectan comportamientos sospechosos en dispositivos (también denominados clientes o extremos), los artefactos (como archivos o aplicaciones) se bloquean, comprueban y corrigen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="77669-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Protección de cliente y nube":::

<span data-ttu-id="77669-114">La protección antivirus funciona mejor cuando se combina con la protección en la nube.</span><span class="sxs-lookup"><span data-stu-id="77669-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="77669-115">Cómo funciona el bloqueo de comportamiento del cliente</span><span class="sxs-lookup"><span data-stu-id="77669-115">How client behavioral blocking works</span></span>

<span data-ttu-id="77669-116">[Antivirus de Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md) detectar comportamientos sospechosos, código malintencionado, ataques sin archivos y en memoria, y mucho más en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="77669-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="77669-117">Cuando se detectan comportamientos sospechosos, Antivirus de Microsoft Defender supervisa y envía esos comportamientos sospechosos y sus árboles de proceso al servicio de protección en la nube.</span><span class="sxs-lookup"><span data-stu-id="77669-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="77669-118">El aprendizaje automático diferencia entre aplicaciones malintencionadas y comportamientos buenos en milisegundos y clasifica cada artefacto.</span><span class="sxs-lookup"><span data-stu-id="77669-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="77669-119">En tiempo casi real, tan pronto como se encuentra que un artefacto es malintencionado, se bloquea en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="77669-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="77669-120">Cada vez que se detecta un comportamiento sospechoso, [se genera](alerts-queue.md) una alerta y está visible en el Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="77669-120">Whenever a suspicious behavior is detected, an [alert](alerts-queue.md) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="77669-121">El bloqueo de comportamiento del cliente es eficaz porque no solo ayuda a evitar que se inicie un ataque, sino que puede ayudar a detener un ataque que se ha comenzado a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="77669-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="77669-122">Además, con el [bloqueo de bucle de comentarios](feedback-loop-blocking.md) (otra capacidad de bloqueo y contención del comportamiento), se evitan ataques en otros dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="77669-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="77669-123">Detecciones basadas en comportamiento</span><span class="sxs-lookup"><span data-stu-id="77669-123">Behavior-based detections</span></span>

<span data-ttu-id="77669-124">Las detecciones basadas en comportamiento se denominan según la [matriz de CK&MITRE ATT para Enterprise](https://attack.mitre.org/matrices/enterprise).</span><span class="sxs-lookup"><span data-stu-id="77669-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="77669-125">La convención de nomenclatura ayuda a identificar la fase de ataque donde se observó el comportamiento malintencionado:</span><span class="sxs-lookup"><span data-stu-id="77669-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="77669-126">Táctica</span><span class="sxs-lookup"><span data-stu-id="77669-126">Tactic</span></span> |   <span data-ttu-id="77669-127">Nombre de la amenaza de detección</span><span class="sxs-lookup"><span data-stu-id="77669-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="77669-128">Acceso inicial</span><span class="sxs-lookup"><span data-stu-id="77669-128">Initial Access</span></span> | `Behavior:Win32/InitialAccess.*!ml` |
|<span data-ttu-id="77669-129">Ejecución</span><span class="sxs-lookup"><span data-stu-id="77669-129">Execution</span></span>  | `Behavior:Win32/Execution.*!ml` |
|<span data-ttu-id="77669-130">Persistencia</span><span class="sxs-lookup"><span data-stu-id="77669-130">Persistence</span></span>    | `Behavior:Win32/Persistence.*!ml` |
|<span data-ttu-id="77669-131">Escalamiento de privilegios</span><span class="sxs-lookup"><span data-stu-id="77669-131">Privilege Escalation</span></span>   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|<span data-ttu-id="77669-132">Evasión de defensa</span><span class="sxs-lookup"><span data-stu-id="77669-132">Defense Evasion</span></span>    | `Behavior:Win32/DefenseEvasion.*!ml` |
|<span data-ttu-id="77669-133">Acceso a credenciales</span><span class="sxs-lookup"><span data-stu-id="77669-133">Credential Access</span></span>  | `Behavior:Win32/CredentialAccess.*!ml` |
|<span data-ttu-id="77669-134">Descubrimiento</span><span class="sxs-lookup"><span data-stu-id="77669-134">Discovery</span></span>  | `Behavior:Win32/Discovery.*!ml` |
|<span data-ttu-id="77669-135">Movimiento lateral</span><span class="sxs-lookup"><span data-stu-id="77669-135">Lateral Movement</span></span> | `Behavior:Win32/LateralMovement.*!ml` |
|<span data-ttu-id="77669-136">Colección</span><span class="sxs-lookup"><span data-stu-id="77669-136">Collection</span></span> |   `Behavior:Win32/Collection.*!ml` |
|<span data-ttu-id="77669-137">Comando y control</span><span class="sxs-lookup"><span data-stu-id="77669-137">Command and Control</span></span> | `Behavior:Win32/CommandAndControl.*!ml` |
|<span data-ttu-id="77669-138">Exfiltración</span><span class="sxs-lookup"><span data-stu-id="77669-138">Exfiltration</span></span>   | `Behavior:Win32/Exfiltration.*!ml` |
|<span data-ttu-id="77669-139">Impacto</span><span class="sxs-lookup"><span data-stu-id="77669-139">Impact</span></span> | `Behavior:Win32/Impact.*!ml` |
|<span data-ttu-id="77669-140">Sin categorizar</span><span class="sxs-lookup"><span data-stu-id="77669-140">Uncategorized</span></span>  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> <span data-ttu-id="77669-141">Para obtener más información acerca de las amenazas específicas, **[vea actividad de amenazas globales recientes](https://www.microsoft.com/wdsi/threats)**.</span><span class="sxs-lookup"><span data-stu-id="77669-141">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="77669-142">Configuración del bloqueo de comportamiento del cliente</span><span class="sxs-lookup"><span data-stu-id="77669-142">Configuring client behavioral blocking</span></span>

<span data-ttu-id="77669-143">Si su organización usa Defender para endpoint, el bloqueo de comportamiento del cliente está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="77669-143">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="77669-144">Sin embargo, para beneficiarse de todas las capacidades de Defender for Endpoint, incluido el bloqueo y la contención del [comportamiento,](behavioral-blocking-containment.md)asegúrese de que las siguientes características y capacidades de Defender para endpoint están habilitadas y configuradas:</span><span class="sxs-lookup"><span data-stu-id="77669-144">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="77669-145">Defender for Endpoint baselines</span><span class="sxs-lookup"><span data-stu-id="77669-145">Defender for Endpoint baselines</span></span>](configure-machines-security-baseline.md)

- [<span data-ttu-id="77669-146">Dispositivos incorporados a Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="77669-146">Devices onboarded to Defender for Endpoint</span></span>](onboard-configure.md)

- [<span data-ttu-id="77669-147">EDR en modo bloqueo</span><span class="sxs-lookup"><span data-stu-id="77669-147">EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="77669-148">Reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="77669-148">Attack surface reduction</span></span>](attack-surface-reduction.md)

- <span data-ttu-id="77669-149">[Protección de última generación](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware y otras funcionalidades de protección contra amenazas)</span><span class="sxs-lookup"><span data-stu-id="77669-149">[Next-generation protection](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware, and other threat protection capabilities)</span></span>

