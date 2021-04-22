---
title: Introducción a la reducción de la superficie expuesta a ataques
ms.reviewer: ''
description: Obtenga información sobre las capacidades de reducción de superficie de ataque de Microsoft Defender para endpoint.
keywords: asr, reducción de superficie de ataque, Microsoft Defender para endpoint, microsoft defender, antivirus, av, windows defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: asr
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 68c9bad95e36863a57d27d49adc2ad46744cbd4a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933534"
---
# <a name="overview-of-attack-surface-reduction"></a><span data-ttu-id="99f3c-104">Introducción a la reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="99f3c-104">Overview of attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="99f3c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="99f3c-105">**Applies to:**</span></span>
- [<span data-ttu-id="99f3c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="99f3c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="99f3c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99f3c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="99f3c-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="99f3c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="99f3c-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="99f3c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="99f3c-110">Ayuda a reducir las superficies de ataque minimizando los lugares en los que tu organización es vulnerable a ataques y ciberamenazas.</span><span class="sxs-lookup"><span data-stu-id="99f3c-110">Help reduce your attack surfaces, by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="99f3c-111">Use los siguientes recursos para configurar la protección de los dispositivos y aplicaciones de su organización.</span><span class="sxs-lookup"><span data-stu-id="99f3c-111">Use the following resources to configure protection for the devices and applications in your organization.</span></span>


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]


<span data-ttu-id="99f3c-112">Artículo</span><span class="sxs-lookup"><span data-stu-id="99f3c-112">Article</span></span> | <span data-ttu-id="99f3c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="99f3c-113">Description</span></span>
-|-
[<span data-ttu-id="99f3c-114">Reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="99f3c-114">Attack surface reduction</span></span>](./attack-surface-reduction.md) | <span data-ttu-id="99f3c-115">Reduzca los puntos vulnerables (las superficies de ataque) en sus aplicaciones con reglas inteligentes que le ayudarán a detener el malware.</span><span class="sxs-lookup"><span data-stu-id="99f3c-115">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="99f3c-116">(Requiere Antivirus de Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="99f3c-116">(Requires Microsoft Defender Antivirus).</span></span>
[<span data-ttu-id="99f3c-117">Aislamiento basado en hardware</span><span class="sxs-lookup"><span data-stu-id="99f3c-117">Hardware-based isolation</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | <span data-ttu-id="99f3c-118">Proteger y mantener la integridad de un sistema cuando se inicia y mientras se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="99f3c-118">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="99f3c-119">Validar la integridad del sistema mediante la atestación local y remota.</span><span class="sxs-lookup"><span data-stu-id="99f3c-119">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="99f3c-120">Además, use el aislamiento de contenedores para Microsoft Edge para ayudar a proteger contra sitios web malintencionados.</span><span class="sxs-lookup"><span data-stu-id="99f3c-120">And, use container isolation for Microsoft Edge to help guard against malicious websites.</span></span>
[<span data-ttu-id="99f3c-121">Control de la aplicación</span><span class="sxs-lookup"><span data-stu-id="99f3c-121">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | <span data-ttu-id="99f3c-122">Use el control de aplicaciones para que las aplicaciones deben ganar confianza para poder ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="99f3c-122">Use application control so that your applications must earn trust in order to run.</span></span>
[<span data-ttu-id="99f3c-123">Protección contra vulnerabilidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="99f3c-123">Exploit protection</span></span>](./exploit-protection.md) | <span data-ttu-id="99f3c-124">Ayude a proteger los sistemas operativos y las aplicaciones que usa su organización para evitar que se aprovechen.</span><span class="sxs-lookup"><span data-stu-id="99f3c-124">Help protect operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="99f3c-125">La protección contra vulnerabilidades de seguridad también funciona con soluciones antivirus de terceros.</span><span class="sxs-lookup"><span data-stu-id="99f3c-125">Exploit protection also works with third-party antivirus solutions.</span></span>
[<span data-ttu-id="99f3c-126">Protección de red</span><span class="sxs-lookup"><span data-stu-id="99f3c-126">Network protection</span></span>](./network-protection.md) | <span data-ttu-id="99f3c-127">Amplíe la protección al tráfico de red y la conectividad en los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="99f3c-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="99f3c-128">(Requiere Antivirus de Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="99f3c-128">(Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="99f3c-129">Protección web</span><span class="sxs-lookup"><span data-stu-id="99f3c-129">Web protection</span></span>](./web-protection-overview.md) | <span data-ttu-id="99f3c-130">Proteja los dispositivos contra amenazas web y le ayudará a regular el contenido no deseado.</span><span class="sxs-lookup"><span data-stu-id="99f3c-130">Secure your devices against web threats and help you regulate unwanted content.</span></span>
[<span data-ttu-id="99f3c-131">Acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="99f3c-131">Controlled folder access</span></span>](./controlled-folders.md) | <span data-ttu-id="99f3c-132">Ayudar a evitar que las aplicaciones malintencionadas o sospechosas (incluido el malware ransomware de cifrado de archivos) realicen cambios en los archivos de las carpetas clave del sistema (requiere Antivirus de Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="99f3c-132">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="99f3c-133">Firewall de red</span><span class="sxs-lookup"><span data-stu-id="99f3c-133">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | <span data-ttu-id="99f3c-134">Impedir que el tráfico no autorizado fluya hacia o desde los dispositivos de la organización con el filtrado de tráfico de red en dos direcciones.</span><span class="sxs-lookup"><span data-stu-id="99f3c-134">Prevent unauthorized traffic from flowing to or from your organization's devices with two-way network traffic filtering.</span></span>
[<span data-ttu-id="99f3c-135">Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="99f3c-135">Attack surface reduction FAQ</span></span>](./attack-surface-reduction-faq.md) | <span data-ttu-id="99f3c-136">Preguntas más frecuentes sobre las reglas de reducción de superficie de ataque, las licencias y mucho más.</span><span class="sxs-lookup"><span data-stu-id="99f3c-136">Frequently asked questions about Attack surface reduction rules, licensing, and more.</span></span>
