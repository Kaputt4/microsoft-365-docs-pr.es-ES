---
title: Configurar grupos de dispositivos en Jamf Pro
description: Obtenga información sobre cómo configurar grupos de dispositivos en Jamf Pro para Microsoft Defender para Endpoint en macOS
keywords: device, group, microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 6f9d62aed2940f95be3a65fcb0fa785f8bacc6d5
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53657080"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Configurar Microsoft Defender para endpoint en grupos de dispositivos macOS en Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Configure los grupos de dispositivos de forma similar a La organización de directivas de grupo unirse (UNIDADES), la colección de dispositivos de Microsoft Endpoint Configuration Manager y los grupos de dispositivos de Intune.

1. Vaya a **Grupos de equipos estáticos**.

2. Seleccione **Nuevo**. 

    ![Imagen de Jamf Pro1](images/jamf-pro-static-group.png)

3. Proporcione un nombre para mostrar y seleccione **Guardar**.

    ![Imagen de Jamf Pro2](images/jamfpro-machine-group.png)

4. Ahora verá el grupo de máquinas **de Contoso en** Grupos de equipos **estáticos**.

    ![Imagen de Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a>Paso siguiente
- [Configurar Microsoft Defender para endpoint en directivas de macOS en Jamf Pro](mac-jamfpro-policies.md)
