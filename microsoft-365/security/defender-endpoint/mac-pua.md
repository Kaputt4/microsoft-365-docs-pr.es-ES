---
title: Detección y bloqueo de aplicaciones potencialmente no deseadas con Microsoft Defender para punto de conexión en Mac
description: Detecte y bloquee aplicaciones potencialmente no deseadas (PUA) mediante Microsoft Defender para punto de conexión en macOS.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, pua, pus, catalina, big sur, monterey, ventura, mde for mac
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
ms.openlocfilehash: 6469537490dfafff5aa3ea62874e4293fe810547
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68769037"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a>Detección y bloqueo de aplicaciones potencialmente no deseadas con Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

La característica de protección de aplicaciones potencialmente no deseadas (PUA) en Microsoft Defender para punto de conexión en macOS puede detectar y bloquear archivos PUA en los puntos de conexión de la red.

Estas aplicaciones no se consideran virus, malware u otros tipos de amenazas, pero pueden realizar acciones en puntos de conexión que afecten negativamente a su rendimiento o uso. PUA también puede hacer referencia a aplicaciones que se consideran de mala reputación.

Estas aplicaciones pueden aumentar el riesgo de que la red se infecte con malware, hacer que las infecciones de malware sean más difíciles de identificar y pueden desperdiciar recursos de TI en la limpieza de las aplicaciones.

## <a name="how-it-works"></a>Cómo funciona

Microsoft Defender para punto de conexión en macOS puede detectar y notificar archivos PUA. Cuando se configura en modo de bloqueo, los archivos PUA se mueven a la cuarentena.

Cuando se detecta una PUA en un punto de conexión, Microsoft Defender para punto de conexión en macOS presenta una notificación al usuario, a menos que se hayan deshabilitado las notificaciones. El nombre de la amenaza contendrá la palabra "Application".

## <a name="configure-pua-protection"></a>Configuración de la protección de PUA

La protección pua en Microsoft Defender para punto de conexión en macOS se puede configurar de una de las siguientes maneras:

- **Desactivado**: la protección pua está deshabilitada.
- **Auditoría**: los archivos PUA se notifican en los registros de productos, pero no en Microsoft 365 Defender portal. No se presenta ninguna notificación al usuario y el producto no realiza ninguna acción.
- **Bloquear**: los archivos PUA se notifican en los registros de productos y en Microsoft 365 Defender portal. El usuario se presenta con una notificación y el producto realiza una acción.

> [!WARNING]
> De forma predeterminada, la protección pua está configurada en modo **auditoría** .

Puede configurar cómo se controlan los archivos PUA desde la línea de comandos o desde la consola de administración.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Use la herramienta de línea de comandos para configurar la protección pua:

En Terminal, ejecute el siguiente comando para configurar la protección pua:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Use la consola de administración para configurar la protección pua:

En la empresa, puede configurar la protección de PUA desde una consola de administración, como JAMF o Intune, de forma similar a cómo se configuran otras opciones de configuración del producto. Para obtener más información, vea la sección [Configuración del tipo de amenaza](mac-preferences.md#threat-type-settings) del tema [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md).

## <a name="related-topics"></a>Temas relacionados

- [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
