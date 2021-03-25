---
title: Implementación de ATP de Microsoft Defender para macOS con Jamf Pro
description: Implementación de ATP de Microsoft Defender para macOS con Jamf Pro
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 56f5e860bd2a9dd47ce16379b5e1ca1a263d62d0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187414"
---
# <a name="deploying-microsoft-defender-for-endpoint-for-macos-with-jamf-pro"></a><span data-ttu-id="6c6e5-104">Implementación de Microsoft Defender para endpoint para macOS con Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="6c6e5-104">Deploying Microsoft Defender for Endpoint for macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6c6e5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6c6e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="6c6e5-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6c6e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6c6e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c6e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6c6e5-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6c6e5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6c6e5-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6c6e5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="6c6e5-110">Obtenga información sobre cómo implementar Microsoft Defender para Endpoint para macOS con Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="6c6e5-110">Learn how to deploy Microsoft Defender for Endpoint for macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="6c6e5-111">Si usa macOS Catalina (10.15.4) o versiones más recientes de macOS, consulte [New configuration profiles for macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)y las versiones más recientes de macOS .</span><span class="sxs-lookup"><span data-stu-id="6c6e5-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="6c6e5-112">Este es un proceso de varios pasos.</span><span class="sxs-lookup"><span data-stu-id="6c6e5-112">This is a multi step process.</span></span> <span data-ttu-id="6c6e5-113">Deberá completar todos los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c6e5-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="6c6e5-114">Iniciar sesión en el Portal de Jamf</span><span class="sxs-lookup"><span data-stu-id="6c6e5-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="6c6e5-115">Configurar Microsoft Defender para endpoint para grupos de dispositivos macOS en Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="6c6e5-115">Setup the Microsoft Defender for Endpoint for macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="6c6e5-116">Configurar Microsoft Defender para endpoint para directivas de macOS en Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="6c6e5-116">Setup the Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="6c6e5-117">Inscribir Microsoft Defender para endpoint para dispositivos macOS en Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="6c6e5-117">Enroll the Microsoft Defender for Endpoint for macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




