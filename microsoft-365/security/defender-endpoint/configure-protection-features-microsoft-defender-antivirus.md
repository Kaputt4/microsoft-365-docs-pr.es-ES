---
title: Habilitar y configurar las Antivirus de Microsoft Defender de protección
description: Habilite la protección heurística, heurística y en tiempo real en av. de Microsoft Defender.
keywords: heuristic, machine-learning, behavior monitor, real-time protection, always-on, Antivirus de Microsoft Defender, antimalware, security, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925568"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="e17f1-104">Configurar la protección en tiempo real, heurística y de comportamiento</span><span class="sxs-lookup"><span data-stu-id="e17f1-104">Configure behavioral, heuristic, and real-time protection</span></span>


<span data-ttu-id="e17f1-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e17f1-105">**Applies to:**</span></span>

- [<span data-ttu-id="e17f1-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e17f1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e17f1-107">Antivirus de Microsoft Defender varios métodos para proporcionar protección contra amenazas:</span><span class="sxs-lookup"><span data-stu-id="e17f1-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="e17f1-108">Protección entregada en la nube para la detección casi instantánea y el bloqueo de amenazas nuevas y emergentes</span><span class="sxs-lookup"><span data-stu-id="e17f1-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="e17f1-109">Análisis siempre en tiempo real, con supervisión del comportamiento de archivos y procesos y otra heurística (también conocida como "protección en tiempo real")</span><span class="sxs-lookup"><span data-stu-id="e17f1-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="e17f1-110">Actualizaciones de protección dedicadas que se basan en el aprendizaje automático, los análisis humanos y automatizados de macrodatos y el estudio detallado de la resistencia ante amenazas.</span><span class="sxs-lookup"><span data-stu-id="e17f1-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="e17f1-111">Puede configurar cómo Antivirus de Microsoft Defender estos métodos con la directiva de grupo, la administración System Center configuración, los cmdlets de PowerShell y Windows Instrumental de administración (WMI).</span><span class="sxs-lookup"><span data-stu-id="e17f1-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="e17f1-112">En esta sección se describe la configuración del análisis siempre en marcha, incluido cómo detectar y bloquear aplicaciones que se consideran no seguras, pero que no se pueden detectar como malware.</span><span class="sxs-lookup"><span data-stu-id="e17f1-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="e17f1-113">Consulte [Use next-gen Antivirus de Microsoft Defender a través](cloud-protection-microsoft-defender-antivirus.md) de la protección entregada en la nube para obtener información sobre cómo habilitar y configurar la Antivirus de Microsoft Defender de entrega en la nube.</span><span class="sxs-lookup"><span data-stu-id="e17f1-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e17f1-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e17f1-114">In this section</span></span>

 <span data-ttu-id="e17f1-115">Tema</span><span class="sxs-lookup"><span data-stu-id="e17f1-115">Topic</span></span> | <span data-ttu-id="e17f1-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="e17f1-116">Description</span></span>
---|---
[<span data-ttu-id="e17f1-117">Detectar y bloquear aplicaciones potencialmente no deseadas</span><span class="sxs-lookup"><span data-stu-id="e17f1-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="e17f1-118">Detectar y bloquear aplicaciones que pueden no ser deseadas en la red, como el software publicitario, modificadores de explorador y barras de herramientas, y aplicaciones antivirus falsas o falsas</span><span class="sxs-lookup"><span data-stu-id="e17f1-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="e17f1-119">Habilitar y configurar las Antivirus de Microsoft Defender de protección</span><span class="sxs-lookup"><span data-stu-id="e17f1-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="e17f1-120">Habilitar y configurar la protección en tiempo real, la heurística y otras características de supervisión Antivirus de Microsoft Defender siempre activas</span><span class="sxs-lookup"><span data-stu-id="e17f1-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>
