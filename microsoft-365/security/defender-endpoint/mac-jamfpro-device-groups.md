---
title: Configurar grupos de dispositivos en Jamf Pro
description: Obtenga información sobre cómo configurar grupos de dispositivos en Jamf Pro para Microsoft Defender para Endpoint en macOS
keywords: device, group, microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d35cd0ecba75be5f6546840e5c80177f950b7193
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171058"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Configurar Microsoft Defender para endpoint en grupos de dispositivos macOS en Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Configure los grupos de dispositivos de forma similar a La organización de directivas de grupo unirse (UNIDADES), la colección de dispositivos de Microsoft Endpoint Configuration Manager y los grupos de dispositivos de Intune.

1. Vaya a **Grupos de equipos estáticos**.

2. Seleccione **Nuevo**. 

    ![Imagen de Jamf Pro1.](images/jamf-pro-static-group.png)

3. Proporcione un nombre para mostrar y seleccione **Guardar**.

    ![Imagen de Jamf Pro2.](images/jamfpro-machine-group.png)

4. Ahora verá el grupo de máquinas **de Contoso en** Grupos de equipos **estáticos**.

    ![Imagen de Jamf Pro3.](images/contoso-machine-group.png)

## <a name="next-step"></a>Paso siguiente
- [Configurar Microsoft Defender para endpoint en directivas de macOS en Jamf Pro](mac-jamfpro-policies.md)
