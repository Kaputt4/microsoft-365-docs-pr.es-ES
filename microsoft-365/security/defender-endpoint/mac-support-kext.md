---
title: Solución de problemas de extensión de kernel en Microsoft Defender para punto de conexión en macOS
description: Solución de problemas relacionados con la extensión del kernel en Microsoft Defender para punto de conexión en macOS.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, kernel, extension
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
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 29f84a51f8156f3a238130ebd2b33f84c7ea5ef0
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851774"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-on-macos"></a>Solución de problemas de extensión de kernel en Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión en macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este artículo se proporciona información sobre cómo solucionar problemas con la extensión de kernel instalada como parte de Microsoft Defender para punto de conexión en macOS.

A partir de macOS High Sierra (10.13), macOS requiere que todas las extensiones de kernel se aprueben explícitamente antes de que se puedan ejecutar en el dispositivo.

Si no aprobó la extensión del kernel durante la implementación o instalación de Microsoft Defender para punto de conexión en macOS, la aplicación muestra un banner que le pide que la habilite:

:::image type="content" source="images/mdatp-32-main-app-fix.png" alt-text="RTP deshabilitado" lightbox="images/mdatp-32-main-app-fix.png":::

También puede ejecutar ```mdatp health```. Notifica si la protección en tiempo real está habilitada pero no está disponible. Esto indica que la extensión del kernel no está aprobada para ejecutarse en el dispositivo.

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : true
real_time_protection_available              : false
...
```

En las secciones siguientes se proporcionan instrucciones sobre cómo solucionar este problema, en función del método que usó para implementar Microsoft Defender para punto de conexión en macOS.

## <a name="managed-deployment"></a>Implementación administrada

Consulte las instrucciones correspondientes a la herramienta de administración que usó para implementar el producto:

- [Implementación basada en JAMF](mac-install-with-jamf.md)
- [Implementación basada en Microsoft Intune](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a>Implementación manual

Si han transcurrido menos de 30 minutos desde que se instaló el producto, vaya a **Preferencias** \> del sistema **Seguridad & privacidad**, donde tiene que **permitir** el software del sistema de los desarrolladores "Microsoft Corporation".

Si no ve este mensaje, significa que han transcurrido 30 o más minutos y que la extensión del kernel todavía no se ha aprobado para ejecutarse en el dispositivo:

:::image type="content" source="images/mdatp-33-securityprivacysettings-noprompt.png" alt-text="Ventana seguridad y privacidad después de que el símbolo del sistema haya expirado" lightbox="images/mdatp-33-securityprivacysettings-noprompt.png":::

En este caso, debe realizar los pasos siguientes para desencadenar de nuevo el flujo de aprobación.

1. En Terminal, intente instalar el controlador. Se producirá un error en la siguiente operación, ya que la extensión del kernel no se aprobó para ejecutarse en el dispositivo. Sin embargo, desencadenará de nuevo el flujo de aprobación.

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. Abra **Preferencias** \> del sistema **Seguridad & privacidad** en el menú. (Ciérrelo primero, si está abierto).

3. **Permitir** software del sistema de desarrolladores "Microsoft Corporation"

4. En Terminal, vuelva a instalar el controlador. Esta vez la operación se realizará correctamente:

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    El banner debe desaparecer de la aplicación Defender y ```mdatp health``` ahora debería informar de que la protección en tiempo real está habilitada y disponible:

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
