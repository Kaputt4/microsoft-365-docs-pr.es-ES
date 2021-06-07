---
title: Configurar capacidades de reducción de superficie de ataque
description: Use Microsoft Intune, Microsoft Endpoint Configuration Manager, cmdlets de PowerShell y directiva de grupo para configurar la reducción de superficie de ataque.
keywords: asr, reducción de superficie de ataque, Windows Defender, Microsoft Defender, antivirus, av
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
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: d2f984e21338e2f9a4ed579cde2d74339031d649
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770966"
---
# <a name="configure-attack-surface-reduction-capabilities"></a><span data-ttu-id="d06ce-104">Configurar capacidades de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="d06ce-104">Configure attack surface reduction capabilities</span></span>

<span data-ttu-id="d06ce-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d06ce-105">**Applies to:**</span></span>
- [<span data-ttu-id="d06ce-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d06ce-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d06ce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d06ce-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="d06ce-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d06ce-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="d06ce-109">[Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="d06ce-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="d06ce-110">Defender for Endpoint incluye varias capacidades de reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="d06ce-110">Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="d06ce-111">Para obtener más información, vea [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="d06ce-111">To learn more, see [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span></span> <span data-ttu-id="d06ce-112">Para configurar la reducción de superficie de ataque en el entorno, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d06ce-112">To configure attack surface reduction in your environment, follow these steps:</span></span> 

1. <span data-ttu-id="d06ce-113">[Habilitar el aislamiento basado en hardware para Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span><span class="sxs-lookup"><span data-stu-id="d06ce-113">[Enable hardware-based isolation for Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span></span>

2. <span data-ttu-id="d06ce-114">Habilitar el control de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d06ce-114">Enable application control.</span></span> 

   1. <span data-ttu-id="d06ce-115">Revise las directivas base en Windows.</span><span class="sxs-lookup"><span data-stu-id="d06ce-115">Review base policies in Windows.</span></span> <span data-ttu-id="d06ce-116">Vea [el ejemplo de directivas base](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span><span class="sxs-lookup"><span data-stu-id="d06ce-116">See [example base policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span></span>
   2. <span data-ttu-id="d06ce-117">Consulte la [guía de diseño del control de aplicaciones](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span><span class="sxs-lookup"><span data-stu-id="d06ce-117">See the [application control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span></span>
   3. <span data-ttu-id="d06ce-118">Consulte la guía [de diseño del control de aplicaciones](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span><span class="sxs-lookup"><span data-stu-id="d06ce-118">Refer to the [application control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span></span>

3. <span data-ttu-id="d06ce-119">[Habilitar el acceso controlado a carpetas](enable-controlled-folders.md).</span><span class="sxs-lookup"><span data-stu-id="d06ce-119">[Enable controlled folder access](enable-controlled-folders.md).</span></span>

4. <span data-ttu-id="d06ce-120">[Activar Protección de red](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="d06ce-120">[Turn on Network protection](enable-network-protection.md).</span></span>

5. <span data-ttu-id="d06ce-121">[Habilitar protección contra vulnerabilidades](enable-exploit-protection.md)de seguridad .</span><span class="sxs-lookup"><span data-stu-id="d06ce-121">[Enable exploit protection](enable-exploit-protection.md).</span></span>

6. <span data-ttu-id="d06ce-122">[Configurar reglas de reducción de superficie de ataque](enable-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="d06ce-122">[Configure attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

7. <span data-ttu-id="d06ce-123">Configurar el firewall de red.</span><span class="sxs-lookup"><span data-stu-id="d06ce-123">Set up your network firewall.</span></span>

   1. <span data-ttu-id="d06ce-124">Obtenga una introducción a [Firewall de Windows Defender con seguridad avanzada](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span><span class="sxs-lookup"><span data-stu-id="d06ce-124">Get an overview of [Windows Defender Firewall with advanced security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span>
   2. <span data-ttu-id="d06ce-125">Use la [Firewall de Windows Defender de diseño para](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) decidir cómo desea diseñar las directivas de firewall.</span><span class="sxs-lookup"><span data-stu-id="d06ce-125">Use the [Windows Defender Firewall design guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) to decide how you want to design your firewall policies.</span></span>
   3. <span data-ttu-id="d06ce-126">Use la [Firewall de Windows Defender de implementación para](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) configurar el firewall de su organización con seguridad avanzada.</span><span class="sxs-lookup"><span data-stu-id="d06ce-126">Use the [Windows Defender Firewall deployment guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) to set up your organization's firewall with advanced security.</span></span> 

> [!TIP]
> <span data-ttu-id="d06ce-127">En la mayoría de los casos, al configurar las capacidades de reducción de superficie de ataque, puedes elegir entre varios métodos:</span><span class="sxs-lookup"><span data-stu-id="d06ce-127">In most cases, when you configure attack surface reduction capabilities, you can choose from among several methods:</span></span>
> - <span data-ttu-id="d06ce-128">Microsoft Endpoint Manager (que ahora incluye Microsoft Intune y Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="d06ce-128">Microsoft Endpoint Manager (which now includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
> - <span data-ttu-id="d06ce-129">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="d06ce-129">Group Policy</span></span>
> - <span data-ttu-id="d06ce-130">Cmdlets de PowerShell</span><span class="sxs-lookup"><span data-stu-id="d06ce-130">PowerShell cmdlets</span></span>
