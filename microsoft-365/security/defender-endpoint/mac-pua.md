---
title: Detectar y bloquear aplicaciones potencialmente no deseadas con Microsoft Defender para Endpoint en Mac
description: Detectar y bloquear aplicaciones potencialmente no deseadas (PUA) con Microsoft Defender en endpoint para Mac.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, pua, pus
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
ms.openlocfilehash: e21407ada85dbed1395f4be9cb943835d563ae8a
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2021
ms.locfileid: "53624085"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a>Detectar y bloquear aplicaciones potencialmente no deseadas con Microsoft Defender para endpoint en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


La característica de protección de aplicaciones potencialmente no deseadas (PUA) en Microsoft Defender para endpoint en macOS puede detectar y bloquear archivos PUA en puntos de conexión de la red.

Estas aplicaciones no se consideran virus, malware u otros tipos de amenazas, pero pueden realizar acciones en puntos de conexión que afecten negativamente a su rendimiento o uso. PUA también puede hacer referencia a aplicaciones que se consideran de mala reputación.

Estas aplicaciones pueden aumentar el riesgo de que la red se infecte con malware, hacer que las infecciones de malware sean más difíciles de identificar y pueden desperdiciar recursos de TI en la limpieza de las aplicaciones.

## <a name="how-it-works"></a>Cómo funciona

Microsoft Defender para endpoint en macOS puede detectar e informar de archivos PUA. Cuando se configura en modo de bloqueo, los archivos PUA se mueven a la cuarentena.

Cuando se detecta una PUA en un punto de conexión, Microsoft Defender para Endpoint en macOS presenta una notificación al usuario, a menos que se hayan deshabilitado las notificaciones. El nombre de la amenaza contendrá la palabra "Application".

## <a name="configure-pua-protection"></a>Configurar la protección de LA PUA

La protección de PUA en Microsoft Defender para endpoint en macOS se puede configurar de una de las siguientes maneras:

- **Desactivado:** la protección de LA PUA está deshabilitada.
- **Auditoría:** los archivos PUA se notifican en los registros del producto, pero no en Microsoft 365 Defender portal. No se presenta ninguna notificación al usuario y el producto no hace ninguna acción.
- **Bloquear:** los archivos PUA se notifican en los registros del producto y en Microsoft 365 Defender portal. El usuario recibe una notificación y el producto toma una acción.

>[!WARNING]
>De forma predeterminada, la protección pua está configurada en **modo auditoría.**

Puede configurar cómo se controlan los archivos PUA desde la línea de comandos o desde la consola de administración.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Use la herramienta de línea de comandos para configurar la protección pua:

En Terminal, ejecute el siguiente comando para configurar la protección pua:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Use la consola de administración para configurar la protección pua:

En su empresa, puede configurar la protección de PUA desde una consola de administración, como JAMF o Intune, de forma similar a la configuración de otros productos. Para obtener más información, consulta la sección Configuración del [tipo](mac-preferences.md#threat-type-settings) de amenaza del tema Establecer preferencias [para Microsoft Defender para Endpoint en macOS.](mac-preferences.md)

## <a name="related-topics"></a>Temas relacionados

- [Establecer preferencias para Microsoft Defender para endpoint en macOS](mac-preferences.md)
