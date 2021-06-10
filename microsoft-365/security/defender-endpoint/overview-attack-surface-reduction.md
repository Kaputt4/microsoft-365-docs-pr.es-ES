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
ms.date: 06/02/2021
ms.openlocfilehash: b6fb9bb327816b7e166a443a0d07932d30421a19
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771698"
---
# <a name="overview-of-attack-surface-reduction-capabilities"></a><span data-ttu-id="b5072-104">Información general sobre las capacidades de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="b5072-104">Overview of attack surface reduction capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b5072-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b5072-105">**Applies to:**</span></span>
- [<span data-ttu-id="b5072-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b5072-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b5072-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5072-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="b5072-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="b5072-108">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="b5072-109">[Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="b5072-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink).</span></span>

<span data-ttu-id="b5072-110">Las superficies de ataque son todos los lugares donde su organización es vulnerable a ciberamenazas y ataques.</span><span class="sxs-lookup"><span data-stu-id="b5072-110">Your attack surfaces are all the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="b5072-111">Defender for Endpoint incluye varias funcionalidades para ayudar a reducir las superficies de ataque.</span><span class="sxs-lookup"><span data-stu-id="b5072-111">Defender for Endpoint includes several capabilities to help reduce your attack surfaces.</span></span> <span data-ttu-id="b5072-112">Vea el siguiente vídeo para obtener más información sobre la reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="b5072-112">Watch the following video to learn more about attack surface reduction.</span></span><p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a><span data-ttu-id="b5072-113">Recursos para obtener más información sobre la reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="b5072-113">Resources to learn more about attack surface reduction</span></span>

<span data-ttu-id="b5072-114">Como se mencionó en el vídeo, Defender for Endpoint incluye varias funcionalidades de reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="b5072-114">As mentioned in the video, Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="b5072-115">Use los siguientes recursos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="b5072-115">Use the following resources to learn more:</span></span>

| <span data-ttu-id="b5072-116">Artículo</span><span class="sxs-lookup"><span data-stu-id="b5072-116">Article</span></span> | <span data-ttu-id="b5072-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5072-117">Description</span></span> |
|:---|:---|
| [<span data-ttu-id="b5072-118">Aislamiento basado en hardware</span><span class="sxs-lookup"><span data-stu-id="b5072-118">Hardware-based isolation</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | <span data-ttu-id="b5072-119">Proteger y mantener la integridad de un sistema cuando se inicia y mientras se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="b5072-119">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="b5072-120">Validar la integridad del sistema mediante la atestación local y remota.</span><span class="sxs-lookup"><span data-stu-id="b5072-120">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="b5072-121">Además, use el aislamiento de contenedores Microsoft Edge para ayudar a protegerse de sitios web malintencionados.</span><span class="sxs-lookup"><span data-stu-id="b5072-121">And, use container isolation for Microsoft Edge to help guard against malicious websites.</span></span> |
| [<span data-ttu-id="b5072-122">Control de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b5072-122">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | <span data-ttu-id="b5072-123">Use el control de aplicaciones para que las aplicaciones deben ganar confianza para poder ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="b5072-123">Use application control so that your applications must earn trust in order to run.</span></span> |
| [<span data-ttu-id="b5072-124">Acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="b5072-124">Controlled folder access</span></span>](controlled-folders.md) | <span data-ttu-id="b5072-125">Ayudar a evitar que las aplicaciones malintencionadas o sospechosas (incluido el malware ransomware cifrado de archivos) realicen cambios en los archivos de las carpetas clave del sistema (requiere Antivirus de Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="b5072-125">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="b5072-126">Protección de red</span><span class="sxs-lookup"><span data-stu-id="b5072-126">Network protection</span></span>](network-protection.md) | <span data-ttu-id="b5072-127">Amplíe la protección al tráfico de red y la conectividad en los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="b5072-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="b5072-128">(Requiere Antivirus de Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="b5072-128">(Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="b5072-129">Protección contra vulnerabilidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="b5072-129">Exploit protection</span></span>](exploit-protection.md) | <span data-ttu-id="b5072-130">Ayude a proteger los sistemas operativos y las aplicaciones que usa su organización para evitar que se aprovechen.</span><span class="sxs-lookup"><span data-stu-id="b5072-130">Help protect operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="b5072-131">La protección contra vulnerabilidades de seguridad también funciona con soluciones antivirus de terceros.</span><span class="sxs-lookup"><span data-stu-id="b5072-131">Exploit protection also works with third-party antivirus solutions.</span></span> |
| [<span data-ttu-id="b5072-132">Reglas de la reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="b5072-132">Attack surface reduction rules</span></span>](attack-surface-reduction.md) | <span data-ttu-id="b5072-133">Reduzca los puntos vulnerables (las superficies de ataque) en sus aplicaciones con reglas inteligentes que le ayudarán a detener el malware.</span><span class="sxs-lookup"><span data-stu-id="b5072-133">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="b5072-134">(Requiere Antivirus de Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="b5072-134">(Requires Microsoft Defender Antivirus).</span></span> |
| [<span data-ttu-id="b5072-135">Control de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b5072-135">Device control</span></span>](device-control-report.md) | <span data-ttu-id="b5072-136">Protege contra la pérdida de datos mediante la supervisión y el control de los medios usados en dispositivos, como el almacenamiento extraíble y las unidades USB, en la organización.</span><span class="sxs-lookup"><span data-stu-id="b5072-136">Protects against data loss by monitoring and controlling media used on devices, such as removable storage and USB drives, in your organization.</span></span> |