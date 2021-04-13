---
title: Configurar grupos de dispositivos en Jamf Pro
description: Obtenga información sobre cómo configurar grupos de dispositivos en Jamf Pro para ATP de Microsoft Defender para macOS
keywords: device, group, microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 6c1d6ae5d4635186bf0a1cbb55c7f906e8584f01
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689694"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="0978f-104">Configurar Microsoft Defender para endpoint en grupos de dispositivos macOS en Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="0978f-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0978f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0978f-105">**Applies to:**</span></span>
- [<span data-ttu-id="0978f-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0978f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0978f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0978f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0978f-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0978f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0978f-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="0978f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="0978f-110">Configure los grupos de dispositivos de forma similar a la organización de directivas de grupo unirse (UNIDADES), la colección de dispositivos de Microsoft Endpoint Configuration Manager y los grupos de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="0978f-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="0978f-111">Vaya a **Grupos de equipos estáticos**.</span><span class="sxs-lookup"><span data-stu-id="0978f-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="0978f-112">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0978f-112">Select **New**.</span></span> 

    ![Imagen de Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="0978f-114">Proporcione un nombre para mostrar y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0978f-114">Provide a display name and select **Save**.</span></span>

    ![Imagen de Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="0978f-116">Ahora verá el grupo de máquinas **de Contoso en** Grupos de equipos **estáticos**.</span><span class="sxs-lookup"><span data-stu-id="0978f-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Imagen de Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="0978f-118">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="0978f-118">Next step</span></span>
- [<span data-ttu-id="0978f-119">Configurar Microsoft Defender para endpoint en directivas de macOS en Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="0978f-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
