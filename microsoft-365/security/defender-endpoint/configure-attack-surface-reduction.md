---
title: Configurar la reducción de superficie de ataque
description: Use Microsoft Intune, Microsoft Endpoint Configuration Manager, cmdlets de PowerShell y directiva de grupo para configurar la reducción de superficie de ataque.
keywords: asr, reducción de superficie de ataque, Windows Defender, Microsoft Defender, antivirus, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6129fb889e2bd42f177c4e3be30f676854119f91
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166174"
---
# <a name="configure-attack-surface-reduction"></a><span data-ttu-id="2a927-104">Configurar la reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="2a927-104">Configure attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2a927-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2a927-105">**Applies to:**</span></span>
- [<span data-ttu-id="2a927-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2a927-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2a927-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a927-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2a927-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2a927-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2a927-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2a927-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="2a927-110">Puedes configurar la reducción de superficie de ataque con muchas herramientas, como:</span><span class="sxs-lookup"><span data-stu-id="2a927-110">You can configure attack surface reduction with many tools, including:</span></span>

* <span data-ttu-id="2a927-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2a927-111">Microsoft Intune</span></span>
* <span data-ttu-id="2a927-112">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2a927-112">Microsoft Endpoint Configuration Manager</span></span>
* <span data-ttu-id="2a927-113">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="2a927-113">Group Policy</span></span>
* <span data-ttu-id="2a927-114">Cmdlets de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a927-114">PowerShell cmdlets</span></span>

<span data-ttu-id="2a927-115">Artículo</span><span class="sxs-lookup"><span data-stu-id="2a927-115">Article</span></span> | <span data-ttu-id="2a927-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a927-116">Description</span></span>
-|-
[<span data-ttu-id="2a927-117">Habilitar el aislamiento basado en hardware para Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2a927-117">Enable hardware-based isolation for Microsoft Edge</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard) | <span data-ttu-id="2a927-118">Cómo preparar e instalar Application Guard, incluidos los requisitos de hardware y software</span><span class="sxs-lookup"><span data-stu-id="2a927-118">How to prepare for and install Application Guard, including hardware and software requirements</span></span>
[<span data-ttu-id="2a927-119">Habilitar el control de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2a927-119">Enable application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)|<span data-ttu-id="2a927-120">Cómo controlar las aplicaciones ejecutadas por los usuarios y proteger los procesos del modo kernel</span><span class="sxs-lookup"><span data-stu-id="2a927-120">How to control applications run by users and protect kernel mode processes</span></span>
[<span data-ttu-id="2a927-121">Protección contra vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="2a927-121">Exploit protection</span></span>](./enable-exploit-protection.md)|<span data-ttu-id="2a927-122">Cómo aplicar automáticamente técnicas de mitigación de vulnerabilidades en procesos del sistema operativo y en aplicaciones individuales</span><span class="sxs-lookup"><span data-stu-id="2a927-122">How to automatically apply exploit mitigation techniques on both operating system processes and on individual apps</span></span>
[<span data-ttu-id="2a927-123">Protección de red</span><span class="sxs-lookup"><span data-stu-id="2a927-123">Network protection</span></span>](./enable-network-protection.md)|<span data-ttu-id="2a927-124">Cómo evitar que los usuarios utilicen aplicaciones para acceder a dominios peligrosos</span><span class="sxs-lookup"><span data-stu-id="2a927-124">How to prevent users from using any apps to access dangerous domains</span></span>
[<span data-ttu-id="2a927-125">Acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="2a927-125">Controlled folder access</span></span>](./enable-controlled-folders.md)|<span data-ttu-id="2a927-126">Cómo proteger datos valiosos de aplicaciones malintencionadas</span><span class="sxs-lookup"><span data-stu-id="2a927-126">How to protect valuable data from malicious apps</span></span>
[<span data-ttu-id="2a927-127">Reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="2a927-127">Attack surface reduction</span></span>](./enable-attack-surface-reduction.md)|<span data-ttu-id="2a927-128">Cómo evitar acciones y aplicaciones que normalmente usan malware que buscan vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="2a927-128">How to prevent actions and apps that are typically used by exploit-seeking malware</span></span>
[<span data-ttu-id="2a927-129">Firewall de red</span><span class="sxs-lookup"><span data-stu-id="2a927-129">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)|<span data-ttu-id="2a927-130">Cómo proteger dispositivos y datos en una red</span><span class="sxs-lookup"><span data-stu-id="2a927-130">How to protect devices and data across a network</span></span>

