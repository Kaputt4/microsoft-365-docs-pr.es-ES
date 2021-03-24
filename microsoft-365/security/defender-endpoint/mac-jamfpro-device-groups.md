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
ms.openlocfilehash: 3e330f135e391214ffe25289d58c2d0de3257be0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070320"
---
# <a name="set-up-microsoft-defender-for-endpoint-for-macos-device-groups-in-jamf-pro"></a>Configurar Microsoft Defender para endpoint para grupos de dispositivos macOS en Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Configure los grupos de dispositivos de forma similar a la organización de directivas de grupo unirse (UNIDADES), la colección de dispositivos de Microsoft Endpoint Configuration Manager y los grupos de dispositivos de Intune.

1. Vaya a **Grupos de equipos estáticos**.

2. Seleccione **Nuevo**. 

    ![Imagen de Jamf Pro1](images/jamf-pro-static-group.png)

3. Proporcione un nombre para mostrar y seleccione **Guardar**.

    ![Imagen de Jamf Pro2](images/jamfpro-machine-group.png)

4. Ahora verá el grupo de máquinas **de Contoso en** Grupos de equipos **estáticos**.

    ![Imagen de Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a>Paso siguiente
- [Configurar Microsoft Defender para endpoint para directivas de macOS en Jamf Pro](mac-jamfpro-policies.md)
