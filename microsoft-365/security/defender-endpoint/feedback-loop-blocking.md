---
title: Bloqueo de bucle de comentarios
description: El bloqueo de bucle de comentarios, también denominado protección rápida, forma parte de las capacidades de contención y bloqueo de comportamiento en Microsoft Defender para endpoint
keywords: bloqueo de comportamiento, protección rápida, bloqueo de comentarios, Microsoft Defender para endpoint
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
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: b1ec879a2f05a0354b1a49cf94fccacb4a382193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076611"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="234a8-104">Bloqueo de bucle de comentarios</span><span class="sxs-lookup"><span data-stu-id="234a8-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="234a8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="234a8-105">**Applies to:**</span></span>
- [<span data-ttu-id="234a8-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="234a8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="234a8-107">Información general</span><span class="sxs-lookup"><span data-stu-id="234a8-107">Overview</span></span>

<span data-ttu-id="234a8-108">El bloqueo de bucle de comentarios, también conocido como protección rápida, es un componente de las capacidades de bloqueo y [contención](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) del comportamiento en [Microsoft Defender para endpoint](https://docs.microsoft.com/windows/security/threat-protection/).</span><span class="sxs-lookup"><span data-stu-id="234a8-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/).</span></span> <span data-ttu-id="234a8-109">Con el bloqueo de bucle de comentarios, los dispositivos de toda la organización están mejor protegidos contra ataques.</span><span class="sxs-lookup"><span data-stu-id="234a8-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="234a8-110">Cómo funciona el bloqueo de bucle de comentarios</span><span class="sxs-lookup"><span data-stu-id="234a8-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="234a8-111">Cuando se detecta un comportamiento o archivo sospechoso, como por ejemplo Antivirus de [Microsoft Defender,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)la información sobre ese artefacto se envía a varios clasificadores.</span><span class="sxs-lookup"><span data-stu-id="234a8-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="234a8-112">El motor de bucle de protección rápida inspecciona y correlaciona la información con otras señales para tomar una decisión sobre si se va a bloquear un archivo.</span><span class="sxs-lookup"><span data-stu-id="234a8-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="234a8-113">La comprobación y clasificación de artefactos se produce rápidamente.</span><span class="sxs-lookup"><span data-stu-id="234a8-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="234a8-114">Esto da como resultado un bloqueo rápido del malware confirmado e impulsa la protección en todo el ecosistema.</span><span class="sxs-lookup"><span data-stu-id="234a8-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="234a8-115">Con la protección rápida en su lugar, se puede detener un ataque en un dispositivo, otros dispositivos de la organización y dispositivos de otras organizaciones, mientras un ataque intenta ampliar su posición.</span><span class="sxs-lookup"><span data-stu-id="234a8-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="234a8-116">Configuración del bloqueo de bucle de comentarios</span><span class="sxs-lookup"><span data-stu-id="234a8-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="234a8-117">Si su organización usa Defender para endpoint, el bloqueo de bucle de comentarios está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="234a8-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="234a8-118">Sin embargo, la protección rápida se produce a través de una combinación de funcionalidades de Defender para endpoints, características de protección de aprendizaje automático y uso compartido de señales en los servicios de seguridad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="234a8-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="234a8-119">Asegúrese de que las siguientes características y funcionalidades de Defender for Endpoint están habilitadas y configuradas:</span><span class="sxs-lookup"><span data-stu-id="234a8-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="234a8-120">Líneas base de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="234a8-120">Microsoft Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="234a8-121">Dispositivos incorporados a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="234a8-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="234a8-122">EDR en modo de bloqueo</span><span class="sxs-lookup"><span data-stu-id="234a8-122">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="234a8-123">Reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="234a8-123">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="234a8-124">[Protección de última generación](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span><span class="sxs-lookup"><span data-stu-id="234a8-124">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="234a8-125">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="234a8-125">Related articles</span></span>

- [<span data-ttu-id="234a8-126">Bloqueo y contención del comportamiento</span><span class="sxs-lookup"><span data-stu-id="234a8-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="234a8-127">(Blog) Bloqueo y contención de comportamiento: transformar la óptica en protección</span><span class="sxs-lookup"><span data-stu-id="234a8-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="234a8-128">ÚtilEs recursos de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="234a8-128">Helpful Microsoft Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
