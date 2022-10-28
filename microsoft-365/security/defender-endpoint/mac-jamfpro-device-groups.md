---
title: Configuración de grupos de dispositivos en Jamf Pro
description: Aprenda a configurar grupos de dispositivos en Jamf Pro para Microsoft Defender para punto de conexión en macOS
keywords: device, group, microsoft, defender, Microsoft Defender para punto de conexión, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, big sur, monterey, ventura, mde for mac
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 16247ae629423fd8dd2028455c6d45c894eca77f
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68767871"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Configuración de Microsoft Defender para punto de conexión en grupos de dispositivos macOS en Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> La creación de grupos de dispositivos se admite en El plan 1 y el plan 2 de Defender para punto de conexión.  

Configure los grupos de dispositivos de forma similar a La organización de la directiva de grupo une (unidades organizativas), la recopilación de dispositivos de Microsoft Endpoint Configuration Manager y los grupos de dispositivos de Intune.

1. Vaya a **Grupos de equipos estáticos**.

2. Seleccione **Nuevo**. 

   :::image type="content" source="images/jamf-pro-static-group.png" alt-text="Página Jamf Pro1" lightbox="images/jamf-pro-static-group.png":::

3. Proporcione un nombre para mostrar y seleccione **Guardar**.

   :::image type="content" source="images/jamfpro-machine-group.png" alt-text="Página Jamf Pro2" lightbox="images/jamfpro-machine-group.png":::

4. Ahora verá el **grupo de máquinas de Contoso** en **Grupos de equipos estáticos**.

   :::image type="content" source="images/contoso-machine-group.png" alt-text="Página Jamf Pro3" lightbox="images/contoso-machine-group.png":::

## <a name="next-step"></a>Paso siguiente
- [Configuración de Microsoft Defender para punto de conexión en directivas de macOS en Jamf Pro](mac-jamfpro-policies.md)
