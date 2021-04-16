---
title: Configurar grupos de dispositivos en Jamf Pro
description: Obtenga información sobre cómo configurar grupos de dispositivos en Jamf Pro para Microsoft Defender para endpoint para macOS
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
ms.openlocfilehash: 80dcb4ff73edd5e95603b15e097232a43dc0e05e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861616"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="b4e3c-104">Configurar Microsoft Defender para endpoint en grupos de dispositivos macOS en Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="b4e3c-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b4e3c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b4e3c-105">**Applies to:**</span></span>
- [<span data-ttu-id="b4e3c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b4e3c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b4e3c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4e3c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b4e3c-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b4e3c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b4e3c-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b4e3c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b4e3c-110">Configure los grupos de dispositivos de forma similar a la organización de directivas de grupo unirse (UNIDADES), la colección de dispositivos de Microsoft Endpoint Configuration Manager y los grupos de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="b4e3c-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="b4e3c-111">Vaya a **Grupos de equipos estáticos**.</span><span class="sxs-lookup"><span data-stu-id="b4e3c-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="b4e3c-112">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b4e3c-112">Select **New**.</span></span> 

    ![Imagen de Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="b4e3c-114">Proporcione un nombre para mostrar y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b4e3c-114">Provide a display name and select **Save**.</span></span>

    ![Imagen de Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="b4e3c-116">Ahora verá el grupo de máquinas **de Contoso en** Grupos de equipos **estáticos**.</span><span class="sxs-lookup"><span data-stu-id="b4e3c-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Imagen de Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="b4e3c-118">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="b4e3c-118">Next step</span></span>
- [<span data-ttu-id="b4e3c-119">Configurar Microsoft Defender para endpoint en directivas de macOS en Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="b4e3c-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
