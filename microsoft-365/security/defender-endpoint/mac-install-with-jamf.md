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
ms.openlocfilehash: a8015221f26250451a6cbcab8e66f35aafdc0767
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689718"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="99597-104">Implementación de Microsoft Defender para endpoint en macOS con Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="99597-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="99597-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="99597-105">**Applies to:**</span></span>
- [<span data-ttu-id="99597-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="99597-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="99597-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99597-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="99597-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="99597-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="99597-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="99597-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="99597-110">Aprende a implementar Microsoft Defender para Endpoint en macOS con Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="99597-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="99597-111">Si usa macOS Catalina (10.15.4) o versiones más recientes de macOS, consulte [New configuration profiles for macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)y las versiones más recientes de macOS .</span><span class="sxs-lookup"><span data-stu-id="99597-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="99597-112">Este es un proceso de varios pasos.</span><span class="sxs-lookup"><span data-stu-id="99597-112">This is a multi step process.</span></span> <span data-ttu-id="99597-113">Deberá completar todos los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="99597-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="99597-114">Iniciar sesión en el Portal de Jamf</span><span class="sxs-lookup"><span data-stu-id="99597-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="99597-115">Configurar Microsoft Defender para endpoint en grupos de dispositivos macOS en Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="99597-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="99597-116">Configurar Microsoft Defender para endpoint en directivas de macOS en Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="99597-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="99597-117">Inscribir Microsoft Defender para endpoint en dispositivos macOS en Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="99597-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




